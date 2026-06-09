# BdeCfgpAcquireNamedPrivilege(ushort *)

- ea: `0x180008020`
- end: `0x1800080ea`
- name: `?BdeCfgpAcquireNamedPrivilege@@YAJPEAG@Z`
- size: `202`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180007070`
- `0x180007e60`
- `0x1800086f8`

## callees

- `0x180008020`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!AdjustTokenPrivileges` at `0x1800080a5`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800080a5`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180008070`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180008070`
- `ADVAPI32!OpenProcessToken` at `0x18000805c`
- `ADVAPI32!OpenProcessToken` at `0x18000805c`
- `KERNEL32!GetLastError` at `0x1800080af`
- `KERNEL32!GetLastError` at `0x1800080af`
- `KERNEL32!CloseHandle` at `0x1800080cf`
- `KERNEL32!CloseHandle` at `0x1800080cf`
- `KERNEL32!GetCurrentProcess` at `0x180008049`
- `KERNEL32!GetCurrentProcess` at `0x180008049`

## pseudocode

```c
__int64 __fastcall BdeCfgpAcquireNamedPrivilege(LPCWSTR lpName)
{
  HANDLE CurrentProcess; // rax
  unsigned int v3; // ebx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = (void *)-1LL;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    || !LookupPrivilegeValueW(0, lpName, (PLUID)&Luid[0].HighPart)
    || (v3 = 0,
        Luid[0].LowPart = 1,
        Luid[1].HighPart = 2,
        !AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0)) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x180008020  push    rbx
0x180008022  sub     rsp, 50h
0x180008026  mov     rax, cs:__security_cookie
0x18000802d  xor     rax, rsp
0x180008030  mov     [rsp+58h+var_10], rax
0x180008035  xorps   xmm0, xmm0
0x180008038  mov     [rsp+58h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180008041  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x180008046  mov     rbx, rcx
0x180008049  call    cs:__imp_GetCurrentProcess
0x18000804f  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180008054  mov     edx, 28h ; '('; DesiredAccess
0x180008059  mov     rcx, rax; ProcessHandle
0x18000805c  call    cs:__imp_OpenProcessToken
0x180008062  test    eax, eax
0x180008064  jz      short loc_1800080AF
0x180008066  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x18000806b  mov     rdx, rbx; lpName
0x18000806e  xor     ecx, ecx; lpSystemName
0x180008070  call    cs:__imp_LookupPrivilegeValueW
0x180008076  test    eax, eax
0x180008078  jz      short loc_1800080AF
0x18000807a  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000807f  lea     r8, [rsp+58h+Luid]; NewState
0x180008084  xor     ebx, ebx
0x180008086  mov     [rsp+58h+Luid.LowPart], 1
0x18000808e  mov     [rsp+58h+ReturnLength], rbx; ReturnLength
0x180008093  xor     r9d, r9d; BufferLength
0x180008096  xor     edx, edx; DisableAllPrivileges
0x180008098  mov     [rsp+58h+PreviousState], rbx; PreviousState
0x18000809d  mov     [rsp+58h+Luid.HighPart+8], 2
0x1800080a5  call    cs:__imp_AdjustTokenPrivileges
0x1800080ab  test    eax, eax
0x1800080ad  jnz     short loc_1800080C4
0x1800080af  call    cs:__imp_GetLastError
0x1800080b5  mov     ebx, eax
0x1800080b7  test    eax, eax
0x1800080b9  jle     short loc_1800080C4
0x1800080bb  movzx   ebx, ax
0x1800080be  or      ebx, 80070000h
0x1800080c4  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1800080c9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800080cd  jz      short loc_1800080D5
0x1800080cf  call    cs:__imp_CloseHandle
0x1800080d5  mov     eax, ebx
0x1800080d7  mov     rcx, [rsp+58h+var_10]
0x1800080dc  xor     rcx, rsp; StackCookie
0x1800080df  call    __security_check_cookie
0x1800080e4  add     rsp, 50h
0x1800080e8  pop     rbx
0x1800080e9  retn
```
