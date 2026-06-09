# UninstallRootDevice

- ea: `0x1400149e0`
- end: `0x140014bd4`
- name: `UninstallRootDevice`
- size: `500`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400147d4`

## callees

- `0x140012d44`
- `0x1400149e0`
- `0x140026d24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014ba0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014aa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014aa5`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140014a3f`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140014a3f`
- `CFGMGR32!CM_MapCrToSpErr` at `0x140014a52`
- `CFGMGR32!CM_MapCrToSpErr` at `0x140014a52`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014a2f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014a72`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014acb`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014b0a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014b89`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014bbd`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014a2f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014a72`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014acb`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014b0a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014b89`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014bbd`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140014a0e`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140014a0e`

## string_xrefs

- `0x140014a14`: `{Uninstall Root Device: %ws}`
- `0x140014b64`: `Unable to uninstall device. Error = 0x%08X`
- `0x140014b76`: `Device requires reboot to complete uninstallation.`
- `0x140014ba6`: `{Uninstall Root Device: exit(0x%08X)}`

## pseudocode

```c
__int64 __fastcall UninstallRootDevice(WCHAR *a1)
{
  __int64 ThreadLogToken; // rsi
  CONFIGRET v3; // eax
  CONFIGRET v4; // edi
  unsigned int v5; // ebx
  int v6; // eax
  _WORD *v7; // rdi
  DWORD LastError; // eax
  const char *v9; // r9
  _WORD *v10; // rbx
  const char *v11; // r9
  __int64 v12; // rax
  DWORD dwMilliseconds[2]; // [rsp+20h] [rbp-30h]
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-8h]
  DEVNODE pdnDevInst; // [rsp+98h] [rbp+48h] BYREF
  __int64 v18; // [rsp+A0h] [rbp+50h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+A8h] [rbp+58h] BYREF

  PropertyType = 1;
  pdnDevInst = 0;
  lpMem = 0;
  LODWORD(v18) = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  DevRtlWriteTextLog(ThreadLogToken, 1, 196612, "{Uninstall Root Device: %ws}", a1);
  v3 = CM_Locate_DevNodeW(&pdnDevInst, a1, 1u);
  v4 = v3;
  if ( v3 )
  {
    v5 = CM_MapCrToSpErr(v3, 3758096907LL);
    DevRtlWriteTextLog(ThreadLogToken, 1, 1, "Failed to locate device. Error = 0x%08X (0x%02X)", v5, v4);
    goto LABEL_22;
  }
  v6 = DevUtilsAllocDeviceProperty(pdnDevInst, (DEVPROPKEY *)&DEVPKEY_Device_Owners, &PropertyType, (__int64)&v15);
  v7 = lpMem;
  if ( v6 || (LastError = GetLastError(), v5 = LastError, LastError == 1168) )
  {
    if ( v7 && *v7 )
    {
      v10 = v7;
      do
      {
        v11 = "Device is still in use by: %ws";
        if ( v10 != v7 )
          v11 = "                           %ws";
        DevRtlWriteTextLog(ThreadLogToken, 1, 4, v11, v10);
        v12 = -1;
        do
          ++v12;
        while ( v10[v12] );
        v10 += v12 + 1;
      }
      while ( *v10 );
      v5 = 2404;
      goto LABEL_20;
    }
    LastError = DispatchRootDeviceOperation(
                  (int)a1,
                  pdnDevInst,
                  (int)UninstallRootDeviceWorker,
                  0,
                  0xEA60u,
                  (__int64)&v18,
                  ThreadLogToken);
    v5 = LastError;
    if ( !LastError )
    {
      if ( (_DWORD)v18 )
        DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Device requires reboot to complete uninstallation.");
      goto LABEL_20;
    }
    v9 = "Unable to uninstall device. Error = 0x%08X";
  }
  else
  {
    v9 = "Unable to query device owners. Error = 0x%08X";
  }
  dwMilliseconds[0] = LastError;
  DevRtlWriteTextLog(ThreadLogToken, 1, 2, v9, *(_QWORD *)dwMilliseconds);
LABEL_20:
  if ( v7 )
    HeapFree(hHeap, 0, v7);
LABEL_22:
  DevRtlWriteTextLog(ThreadLogToken, 1, 327684, "{Uninstall Root Device: exit(0x%08X)}", v5);
  return v5;
}

```

## disassembly

```asm
0x1400149e0  push    rbp
0x1400149e2  push    rbx
0x1400149e3  push    rsi
0x1400149e4  push    rdi
0x1400149e5  push    r12
0x1400149e7  push    r14
0x1400149e9  push    r15
0x1400149eb  mov     rbp, rsp
0x1400149ee  sub     rsp, 50h
0x1400149f2  xor     r15d, r15d
0x1400149f5  mov     r12d, 1
0x1400149fb  mov     [rbp+PropertyType], r12d
0x1400149ff  mov     r14, rcx
0x140014a02  mov     [rbp+pdnDevInst], r15d
0x140014a06  mov     [rbp+lpMem], r15
0x140014a0a  mov     dword ptr [rbp+arg_10], r15d
0x140014a0e  call    cs:__imp_DevRtlGetThreadLogToken
0x140014a14  lea     r9, aUninstallRootD; "{Uninstall Root Device: %ws}"
0x140014a1b  mov     qword ptr [rsp+50h+dwMilliseconds], r14
0x140014a20  mov     rcx, rax
0x140014a23  mov     r8d, 30004h
0x140014a29  mov     edx, r12d
0x140014a2c  mov     rsi, rax
0x140014a2f  call    cs:__imp_DevRtlWriteTextLog
0x140014a35  mov     r8d, r12d; ulFlags
0x140014a38  lea     rcx, [rbp+pdnDevInst]; pdnDevInst
0x140014a3c  mov     rdx, r14; pDeviceID
0x140014a3f  call    cs:__imp_CM_Locate_DevNodeW
0x140014a45  mov     edi, eax
0x140014a47  test    eax, eax
0x140014a49  jz      short loc_140014A7D
0x140014a4b  mov     edx, 0E000020Bh
0x140014a50  mov     ecx, eax
0x140014a52  call    cs:__imp_CM_MapCrToSpErr
0x140014a58  lea     r9, aFailedToLocate_0; "Failed to locate device. Error = 0x%08X"...
0x140014a5f  mov     dword ptr [rsp+50h+var_28], edi
0x140014a63  mov     r8d, r12d
0x140014a66  mov     [rsp+50h+dwMilliseconds], eax
0x140014a6a  mov     edx, r12d
0x140014a6d  mov     rcx, rsi
0x140014a70  mov     ebx, eax
0x140014a72  call    cs:__imp_DevRtlWriteTextLog
0x140014a78  jmp     loc_140014BA6
0x140014a7d  mov     ecx, [rbp+pdnDevInst]; dnDevInst
0x140014a80  lea     rax, [rbp+var_10]
0x140014a84  lea     r9, [rbp+lpMem]
0x140014a88  mov     qword ptr [rsp+50h+dwMilliseconds], rax; __int64
0x140014a8d  lea     r8, [rbp+PropertyType]; PropertyType
0x140014a91  lea     rdx, DEVPKEY_Device_Owners; PropertyKey
0x140014a98  call    DevUtilsAllocDeviceProperty
0x140014a9d  mov     rdi, [rbp+lpMem]
0x140014aa1  test    eax, eax
0x140014aa3  jnz     short loc_140014AD6
0x140014aa5  call    cs:__imp_GetLastError
0x140014aab  mov     ebx, eax
0x140014aad  cmp     eax, 490h
0x140014ab2  jz      short loc_140014AD6
0x140014ab4  lea     r9, aUnableToQueryD; "Unable to query device owners. Error = "...
0x140014abb  mov     r8d, 2
0x140014ac1  mov     [rsp+50h+dwMilliseconds], eax
0x140014ac5  mov     edx, r12d
0x140014ac8  mov     rcx, rsi
0x140014acb  call    cs:__imp_DevRtlWriteTextLog
0x140014ad1  jmp     loc_140014B8F
0x140014ad6  test    rdi, rdi
0x140014ad9  jz      short loc_140014B33
0x140014adb  cmp     [rdi], r15w
0x140014adf  jz      short loc_140014B33
0x140014ae1  mov     rbx, rdi
0x140014ae4  lea     rax, aWs_0; "                           %ws"
0x140014aeb  mov     qword ptr [rsp+50h+dwMilliseconds], rbx
0x140014af0  cmp     rbx, rdi
0x140014af3  lea     r9, aDeviceIsStillI; "Device is still in use by: %ws"
0x140014afa  mov     r8d, 4
0x140014b00  mov     edx, r12d
0x140014b03  cmovnz  r9, rax
0x140014b07  mov     rcx, rsi
0x140014b0a  call    cs:__imp_DevRtlWriteTextLog
0x140014b10  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014b14  inc     rax
0x140014b17  cmp     [rbx+rax*2], r15w
0x140014b1c  jnz     short loc_140014B14
0x140014b1e  lea     rbx, [rbx+rax*2]
0x140014b22  add     rbx, 2
0x140014b26  cmp     [rbx], r15w
0x140014b2a  jnz     short loc_140014AE4
0x140014b2c  mov     ebx, 964h
0x140014b31  jmp     short loc_140014B8F
0x140014b33  mov     edx, [rbp+pdnDevInst]; int
0x140014b36  lea     rax, [rbp+arg_10]
0x140014b3a  mov     [rsp+50h+var_20], rsi; __int64
0x140014b3f  lea     r8, UninstallRootDeviceWorker; int
0x140014b46  mov     [rsp+50h+var_28], rax; __int64
0x140014b4b  xor     r9d, r9d; int
0x140014b4e  mov     rcx, r14; int
0x140014b51  mov     [rsp+50h+dwMilliseconds], 0EA60h; dwMilliseconds
0x140014b59  call    DispatchRootDeviceOperation
0x140014b5e  mov     ebx, eax
0x140014b60  test    eax, eax
0x140014b62  jz      short loc_140014B70
0x140014b64  lea     r9, aUnableToUninst; "Unable to uninstall device. Error = 0x%"...
0x140014b6b  jmp     loc_140014ABB
0x140014b70  cmp     dword ptr [rbp+arg_10], r15d
0x140014b74  jz      short loc_140014B8F
0x140014b76  lea     r9, aDeviceRequires; "Device requires reboot to complete unin"...
0x140014b7d  mov     r8d, 2
0x140014b83  mov     edx, r12d
0x140014b86  mov     rcx, rsi
0x140014b89  call    cs:__imp_DevRtlWriteTextLog
0x140014b8f  test    rdi, rdi
0x140014b92  jz      short loc_140014BA6
0x140014b94  mov     rcx, cs:hHeap; hHeap
0x140014b9b  mov     r8, rdi; lpMem
0x140014b9e  xor     edx, edx; dwFlags
0x140014ba0  call    cs:__imp_HeapFree
0x140014ba6  lea     r9, aUninstallRootD_0; "{Uninstall Root Device: exit(0x%08X)}"
0x140014bad  mov     [rsp+50h+dwMilliseconds], ebx
0x140014bb1  mov     r8d, 50004h
0x140014bb7  mov     edx, r12d
0x140014bba  mov     rcx, rsi
0x140014bbd  call    cs:__imp_DevRtlWriteTextLog
0x140014bc3  mov     eax, ebx
0x140014bc5  add     rsp, 50h
0x140014bc9  pop     r15
0x140014bcb  pop     r14
0x140014bcd  pop     r12
0x140014bcf  pop     rdi
0x140014bd0  pop     rsi
0x140014bd1  pop     rbx
0x140014bd2  pop     rbp
0x140014bd3  retn
```
