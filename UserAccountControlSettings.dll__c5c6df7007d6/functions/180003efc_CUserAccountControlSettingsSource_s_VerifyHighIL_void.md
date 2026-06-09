# CUserAccountControlSettingsSource::s_VerifyHighIL(void)

- ea: `0x180003efc`
- end: `0x180003fa2`
- name: `?s_VerifyHighIL@CUserAccountControlSettingsSource@@CAJXZ`
- size: `166`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000377c`

## callees

- `0x1800034cc`
- `0x180003efc`
- `0x18000b3d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003f0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003f0e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003f20`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003f20`

## pseudocode

```c
__int64 CUserAccountControlSettingsSource::s_VerifyHighIL(void)
{
  HANDLE CurrentProcess; // rax
  int v1; // ebx
  void *TokenHandle; // [rsp+38h] [rbp-10h] BYREF
  __int64 v4; // [rsp+68h] [rbp+20h] BYREF
  __int64 v5; // [rsp+70h] [rbp+28h] BYREF
  int v6; // [rsp+78h] [rbp+30h]

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
    v6 = 0;
    LODWORD(v5) = 0;
    LODWORD(v4) = 0;
    v1 = LUAIsElevatedTokenEx(TokenHandle, (__int64)&v5, (__int64)&v4);
    if ( v1 >= 0 )
      v1 = -2147467259;
    CloseHandle(TokenHandle);
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180003efc  push    rbp
0x180003efe  push    rbx
0x180003eff  mov     rbp, rsp
0x180003f02  sub     rsp, 48h
0x180003f06  mov     [rbp+TokenHandle], 0
0x180003f0e  call    cs:__imp_GetCurrentProcess
0x180003f14  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180003f18  mov     edx, 0Ah; DesiredAccess
0x180003f1d  mov     rcx, rax; ProcessHandle
0x180003f20  call    cs:__imp_OpenProcessToken
0x180003f26  test    eax, eax
0x180003f28  jz      short loc_180003F92
0x180003f2a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180003f2e  lea     rax, [rbp+arg_8]
0x180003f32  mov     [rsp+48h+var_20], rax; __int64
0x180003f37  lea     r9, [rbp+arg_18]
0x180003f3b  lea     rax, [rbp+arg_10]
0x180003f3f  mov     [rbp+arg_0], 0
0x180003f46  lea     r8, [rbp+var_18]
0x180003f4a  mov     [rsp+48h+var_28], rax; __int64
0x180003f4f  lea     rdx, [rbp+arg_0]
0x180003f53  mov     [rbp+var_18], 0
0x180003f5a  mov     [rbp+arg_18], 0
0x180003f61  mov     dword ptr [rbp+arg_10], 0
0x180003f68  mov     dword ptr [rbp+arg_8], 0
0x180003f6f  call    LUAIsElevatedTokenEx
0x180003f74  mov     ebx, eax
0x180003f76  test    eax, eax
0x180003f78  js      short loc_180003F86
0x180003f7a  cmp     [rbp+arg_0], 0
0x180003f7e  mov     eax, 80004005h
0x180003f83  cmovz   ebx, eax
0x180003f86  mov     rcx, [rbp+TokenHandle]; hObject
0x180003f8a  call    cs:__imp_CloseHandle
0x180003f90  jmp     short loc_180003F99
0x180003f92  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003f97  mov     ebx, eax
0x180003f99  mov     eax, ebx
0x180003f9b  add     rsp, 48h
0x180003f9f  pop     rbx
0x180003fa0  pop     rbp
0x180003fa1  retn
```
