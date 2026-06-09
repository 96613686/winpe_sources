# InstallNullDriver

- ea: `0x14001190c`
- end: `0x140011a22`
- name: `InstallNullDriver`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x140012258`

## callees

- `0x14001190c`
- `0x140011f24`
- `0x14001dc80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001197c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001197c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400119a8`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1400119a8`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140011995`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140011995`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001194b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400119cf`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001194b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400119cf`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001192f`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001192f`

## string_xrefs

- `0x14001193a`: `Installing NULL driver`

## pseudocode

```c
__int64 __fastcall InstallNullDriver(void *a1, WCHAR *a2, int a3)
{
  __int64 ThreadLogToken; // rbp
  CONFIGRET v8; // eax
  unsigned int v9; // ebx
  unsigned __int16 *v11; // [rsp+28h] [rbp-30h]
  CONFIGRET v12; // [rsp+30h] [rbp-28h]
  DEVNODE pdnDevInst; // [rsp+78h] [rbp+20h] BYREF

  pdnDevInst = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Installing NULL driver");
  if ( !IsDriverInstallAllowed(ThreadLogToken, a1, a2, 0, 0, 0) )
    return GetLastError();
  v8 = CM_Locate_DevNodeW(&pdnDevInst, a2, 1u);
  if ( !v8 )
    return (unsigned int)CoreDeviceInstall((__int64)a1, pdnDevInst, (int *)a2, 0, 0, a3);
  v12 = v8;
  LODWORD(v11) = CM_MapCrToWin32Err(v8, 0x490u);
  v9 = (unsigned int)v11;
  DevRtlWriteTextLog(ThreadLogToken, 1, 1, "Unable to locate device '%ws'. Error = 0x%08X (0x%02X)", a2, v11, v12);
  return v9;
}

```

## disassembly

```asm
0x14001190c  mov     [rsp+arg_0], rbx
0x140011911  mov     [rsp+arg_8], rbp
0x140011916  push    rsi
0x140011917  push    rdi
0x140011918  push    r14
0x14001191a  sub     rsp, 40h
0x14001191e  mov     ebx, r8d
0x140011921  mov     [rsp+58h+pdnDevInst], 0
0x140011929  mov     rsi, rdx
0x14001192c  mov     r14, rcx
0x14001192f  call    cs:__imp_DevRtlGetThreadLogToken
0x140011935  mov     edx, 1
0x14001193a  lea     r9, aInstallingNull; "Installing NULL driver"
0x140011941  mov     rcx, rax
0x140011944  mov     rbp, rax
0x140011947  lea     r8d, [rdx+1]
0x14001194b  call    cs:__imp_DevRtlWriteTextLog
0x140011951  mov     [rsp+58h+var_28], ebx; int
0x140011955  xor     r9d, r9d; int
0x140011958  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x140011961  mov     r8, rsi; int
0x140011964  mov     rdx, r14; int
0x140011967  mov     [rsp+58h+var_38], 0; __int64
0x140011970  mov     rcx, rbp; int
0x140011973  call    IsDriverInstallAllowed
0x140011978  test    eax, eax
0x14001197a  jnz     short loc_140011987
0x14001197c  call    cs:__imp_GetLastError
0x140011982  jmp     loc_140011A0B
0x140011987  mov     r8d, 1; ulFlags
0x14001198d  lea     rcx, [rsp+58h+pdnDevInst]; pdnDevInst
0x140011992  mov     rdx, rsi; pDeviceID
0x140011995  call    cs:__imp_CM_Locate_DevNodeW
0x14001199b  mov     edi, eax
0x14001199d  test    eax, eax
0x14001199f  jz      short loc_1400119D7
0x1400119a1  mov     edx, 490h; DefaultErr
0x1400119a6  mov     ecx, eax; CmReturnCode
0x1400119a8  call    cs:__imp_CM_MapCrToWin32Err
0x1400119ae  mov     edx, 1
0x1400119b3  mov     [rsp+58h+var_28], edi
0x1400119b7  mov     dword ptr [rsp+58h+var_30], eax
0x1400119bb  lea     r9, aUnableToLocate; "Unable to locate device '%ws'. Error = "...
0x1400119c2  mov     r8d, edx
0x1400119c5  mov     [rsp+58h+var_38], rsi
0x1400119ca  mov     rcx, rbp
0x1400119cd  mov     ebx, eax
0x1400119cf  call    cs:__imp_DevRtlWriteTextLog
0x1400119d5  jmp     short loc_140011A0D
0x1400119d7  mov     edx, [rsp+58h+pdnDevInst]
0x1400119db  lea     rax, DrvInstActionCallback
0x1400119e2  mov     [rsp+58h+var_20], 0
0x1400119eb  xor     r9d, r9d
0x1400119ee  mov     qword ptr [rsp+58h+var_28], rax
0x1400119f3  mov     r8, rsi
0x1400119f6  mov     dword ptr [rsp+58h+var_30], ebx
0x1400119fa  mov     rcx, r14
0x1400119fd  mov     [rsp+58h+var_38], 0
0x140011a06  call    CoreDeviceInstall
0x140011a0b  mov     ebx, eax
0x140011a0d  mov     rbp, [rsp+58h+arg_8]
0x140011a12  mov     eax, ebx
0x140011a14  mov     rbx, [rsp+58h+arg_0]
0x140011a19  add     rsp, 40h
0x140011a1d  pop     r14
0x140011a1f  pop     rdi
0x140011a20  pop     rsi
0x140011a21  retn
```
