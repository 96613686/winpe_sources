# InstallBestDriver

- ea: `0x14001170c`
- end: `0x140011905`
- name: `InstallBestDriver`
- size: `505`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140012258`

## callees

- `0x14001170c`
- `0x140011a78`
- `0x140027124`
- `0x1400276f8`
- `0x14002c2bc`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400118d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400118d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400117f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400117f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011849`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14001177e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14001177e`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14001176b`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14001176b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400117a2`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011869`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001188d`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400117a2`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011869`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001188d`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140011754`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140011754`
- `drvstore!DriverStoreOpenW` at `0x1400117e8`
- `drvstore!DriverStoreOpenW` at `0x1400117e8`
- `drvstore!DriverStoreClose` at `0x1400118bc`
- `drvstore!DriverStoreClose` at `0x1400118bc`

## string_xrefs

- `0x14001187f`: `No compatible drivers found.`

## pseudocode

```c
__int64 __fastcall InstallBestDriver(__int64 a1, WCHAR *a2, int a3)
{
  unsigned __int64 ThreadLogToken; // r14
  CONFIGRET v7; // eax
  unsigned int LastError; // ebx
  int ConfigFlags; // eax
  unsigned int v10; // edx
  struct HDRIVERSTORE__ *v11; // rax
  __int64 v12; // rsi
  BOOL v13; // eax
  unsigned __int16 *v14; // rdi
  int v16; // [rsp+30h] [rbp-D0h]
  CONFIGRET v17; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v18; // [rsp+48h] [rbp-B8h]
  DEVNODE pdnDevInst; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v20; // [rsp+64h] [rbp-9Ch] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v22[264]; // [rsp+70h] [rbp-90h] BYREF

  pdnDevInst = 0;
  v20 = 0;
  lpMem = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  v7 = CM_Locate_DevNodeW(&pdnDevInst, a2, 1u);
  if ( v7 )
  {
    v17 = v7;
    LastError = CM_MapCrToWin32Err(v7, 0x490u);
    DevRtlWriteTextLog(
      ThreadLogToken,
      1,
      1,
      "Unable to locate device '%ws'. Error = 0x%08X (0x%02X)",
      a2,
      LastError,
      v17);
  }
  else
  {
    if ( (a3 & 0x20) == 0 )
    {
      ConfigFlags = DevUtilsGetConfigFlags(pdnDevInst, &v20);
      v10 = 0;
      if ( ConfigFlags )
        v10 = v20;
      v20 = v10 & 0xFFFFFBDF;
      DevUtilsSetConfigFlags(pdnDevInst);
    }
    v11 = (struct HDRIVERSTORE__ *)DriverStoreOpenW(0, 0, 0, 0);
    v12 = (__int64)v11;
    if ( v11 )
    {
      LODWORD(v18) = 260;
      v13 = PnpUtilsSelectDriverForDevNode(v11, pdnDevInst, (__int64)a2, 0, 0, &lpMem, v16, 0, v22, v18, ThreadLogToken);
      v14 = (unsigned __int16 *)lpMem;
      if ( v13
        || (LastError = GetLastError(),
            DevRtlWriteTextLog(
              ThreadLogToken,
              1,
              1,
              "Unable to select best driver for device.  Error = 0x%08X",
              LastError),
            !LastError) )
      {
        if ( *v14 )
        {
          LastError = InstallSpecificDriver(a1, v12, (int *)a2, (__int64)v22, v14, a3);
        }
        else
        {
          DevRtlWriteTextLog(ThreadLogToken, 1, 2, "No compatible drivers found.");
          LastError = -536870360;
        }
      }
      DriverStoreClose(v12);
      if ( v14 )
        HeapFree(hHeap, 0, v14);
    }
    else
    {
      return GetLastError();
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x14001170c  mov     [rsp-8+arg_10], rbx
0x140011711  push    rbp
0x140011712  push    rsi
0x140011713  push    rdi
0x140011714  push    r12
0x140011716  push    r13
0x140011718  push    r14
0x14001171a  push    r15
0x14001171c  lea     rbp, [rsp-190h]
0x140011724  sub     rsp, 290h
0x14001172b  mov     rax, cs:__security_cookie
0x140011732  xor     rax, rsp
0x140011735  mov     [rbp+1C0h+var_40], rax
0x14001173c  xor     ebx, ebx
0x14001173e  mov     r12d, r8d
0x140011741  mov     [rsp+2C0h+pdnDevInst], ebx
0x140011745  mov     r15, rdx
0x140011748  mov     [rsp+2C0h+var_25C], ebx
0x14001174c  mov     r13, rcx
0x14001174f  mov     [rsp+2C0h+lpMem], rbx
0x140011754  call    cs:__imp_DevRtlGetThreadLogToken
0x14001175a  lea     esi, [rbx+1]
0x14001175d  mov     rdx, r15; pDeviceID
0x140011760  mov     r8d, esi; ulFlags
0x140011763  lea     rcx, [rsp+2C0h+pdnDevInst]; pdnDevInst
0x140011768  mov     r14, rax
0x14001176b  call    cs:__imp_CM_Locate_DevNodeW
0x140011771  mov     edi, eax
0x140011773  test    eax, eax
0x140011775  jz      short loc_1400117AD
0x140011777  mov     edx, 490h; DefaultErr
0x14001177c  mov     ecx, eax; CmReturnCode
0x14001177e  call    cs:__imp_CM_MapCrToWin32Err
0x140011784  mov     [rsp+2C0h+var_290], edi
0x140011788  lea     r9, aUnableToLocate; "Unable to locate device '%ws'. Error = "...
0x14001178f  mov     dword ptr [rsp+2C0h+var_298], eax
0x140011793  mov     r8d, esi
0x140011796  mov     edx, esi
0x140011798  mov     [rsp+2C0h+var_2A0], r15
0x14001179d  mov     rcx, r14
0x1400117a0  mov     ebx, eax
0x1400117a2  call    cs:__imp_DevRtlWriteTextLog
0x1400117a8  jmp     loc_1400118D9
0x1400117ad  test    r12b, 20h
0x1400117b1  jnz     short loc_1400117DE
0x1400117b3  mov     ecx, [rsp+2C0h+pdnDevInst]
0x1400117b7  lea     rdx, [rsp+2C0h+var_25C]
0x1400117bc  call    DevUtilsGetConfigFlags
0x1400117c1  mov     edx, ebx
0x1400117c3  test    eax, eax
0x1400117c5  jz      short loc_1400117CB
0x1400117c7  mov     edx, [rsp+2C0h+var_25C]
0x1400117cb  mov     ecx, [rsp+2C0h+pdnDevInst]
0x1400117cf  and     edx, 0FFFFFBDFh
0x1400117d5  mov     [rsp+2C0h+var_25C], edx
0x1400117d9  call    DevUtilsSetConfigFlags
0x1400117de  xor     r9d, r9d
0x1400117e1  xor     r8d, r8d
0x1400117e4  xor     edx, edx
0x1400117e6  xor     ecx, ecx
0x1400117e8  call    cs:__imp_DriverStoreOpenW
0x1400117ee  mov     rsi, rax
0x1400117f1  test    rax, rax
0x1400117f4  jnz     short loc_140011803
0x1400117f6  call    cs:__imp_GetLastError
0x1400117fc  mov     ebx, eax
0x1400117fe  jmp     loc_1400118D9
0x140011803  mov     edx, [rsp+2C0h+pdnDevInst]; int
0x140011807  lea     rax, [rsp+2C0h+var_250]
0x14001180c  mov     [rsp+2C0h+var_270], r14; unsigned __int64
0x140011811  xor     r9d, r9d; int
0x140011814  mov     dword ptr [rsp+2C0h+var_278], 104h; unsigned __int64
0x14001181c  mov     r8, r15; int
0x14001181f  mov     [rsp+2C0h+var_280], rax; __int64
0x140011824  mov     rcx, rsi; int
0x140011827  lea     rax, [rsp+2C0h+lpMem]
0x14001182c  mov     [rsp+2C0h+var_288], rbx; __int64
0x140011831  mov     [rsp+2C0h+var_298], rax; __int64
0x140011836  mov     [rsp+2C0h+var_2A0], rbx; struct _DRVUTILS_UPDATE_INFO *
0x14001183b  call    PnpUtilsSelectDriverForDevNode
0x140011840  mov     rdi, [rsp+2C0h+lpMem]
0x140011845  test    eax, eax
0x140011847  jnz     short loc_140011875
0x140011849  call    cs:__imp_GetLastError
0x14001184f  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x140011853  lea     r9, aUnableToSelect_0; "Unable to select best driver for device"...
0x14001185a  mov     ebx, eax
0x14001185c  mov     rcx, r14
0x14001185f  mov     eax, 1
0x140011864  mov     r8d, eax
0x140011867  mov     edx, eax
0x140011869  call    cs:__imp_DevRtlWriteTextLog
0x14001186f  test    ebx, ebx
0x140011871  jnz     short loc_1400118B9
0x140011873  xor     ebx, ebx
0x140011875  cmp     [rdi], bx
0x140011878  jnz     short loc_14001189A
0x14001187a  mov     edx, 1
0x14001187f  lea     r9, aNoCompatibleDr; "No compatible drivers found."
0x140011886  mov     rcx, r14
0x140011889  lea     r8d, [rdx+1]
0x14001188d  call    cs:__imp_DevRtlWriteTextLog
0x140011893  mov     ebx, 0E0000228h
0x140011898  jmp     short loc_1400118B9
0x14001189a  mov     dword ptr [rsp+2C0h+var_298], r12d
0x14001189f  lea     r9, [rsp+2C0h+var_250]
0x1400118a4  mov     r8, r15
0x1400118a7  mov     [rsp+2C0h+var_2A0], rdi
0x1400118ac  mov     rdx, rsi
0x1400118af  mov     rcx, r13
0x1400118b2  call    InstallSpecificDriver
0x1400118b7  mov     ebx, eax
0x1400118b9  mov     rcx, rsi
0x1400118bc  call    cs:__imp_DriverStoreClose
0x1400118c2  test    rdi, rdi
0x1400118c5  jz      short loc_1400118D9
0x1400118c7  mov     rcx, cs:hHeap; hHeap
0x1400118ce  mov     r8, rdi; lpMem
0x1400118d1  xor     edx, edx; dwFlags
0x1400118d3  call    cs:__imp_HeapFree
0x1400118d9  mov     eax, ebx
0x1400118db  mov     rcx, [rbp+1C0h+var_40]
0x1400118e2  xor     rcx, rsp; StackCookie
0x1400118e5  call    __security_check_cookie
0x1400118ea  mov     rbx, [rsp+2C0h+arg_10]
0x1400118f2  add     rsp, 290h
0x1400118f9  pop     r15
0x1400118fb  pop     r14
0x1400118fd  pop     r13
0x1400118ff  pop     r12
0x140011901  pop     rdi
0x140011902  pop     rsi
0x140011903  pop     rbp
0x140011904  retn
```
