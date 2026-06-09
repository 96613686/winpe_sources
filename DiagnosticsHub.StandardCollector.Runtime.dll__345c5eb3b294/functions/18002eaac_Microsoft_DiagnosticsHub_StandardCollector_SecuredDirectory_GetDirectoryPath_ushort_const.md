# Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(ushort const * *)

- ea: `0x18002eaac`
- end: `0x18002eb3b`
- name: `?GetDirectoryPath@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEAPEBG@Z`
- size: `143`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *__hidden this, const unsigned __int16 **)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004298`
- `0x18000d170`
- `0x18001b320`
- `0x18001c3b0`
- `0x180020004`
- `0x180020338`
- `0x18002a80c`

## callees

- `0x18002eaac`
- `0x180049b50`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18002eada`
- `KERNEL32!GetCurrentThread` at `0x18002eada`
- `KERNEL32!CloseHandle` at `0x18002eb03`
- `KERNEL32!CloseHandle` at `0x18002eb15`
- `KERNEL32!CloseHandle` at `0x18002eb03`
- `KERNEL32!CloseHandle` at `0x18002eb15`
- `ADVAPI32!OpenThreadToken` at `0x18002eaef`
- `ADVAPI32!OpenThreadToken` at `0x18002eaef`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(
        Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *this,
        const unsigned __int16 **a2)
{
  HANDLE CurrentThread; // rax
  HANDLE TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  if ( *((_BYTE *)this + 8) )
  {
LABEL_8:
    *a2 = *(const unsigned __int16 **)this;
    return 0;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle) )
  {
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    goto LABEL_8;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return 2147942405LL;
}

```

## disassembly

```asm
0x18002eaac  mov     [rsp+arg_0], rbx
0x18002eab1  push    rdi
0x18002eab2  sub     rsp, 30h
0x18002eab6  mov     rax, cs:__security_cookie
0x18002eabd  xor     rax, rsp
0x18002eac0  mov     [rsp+38h+var_10], rax
0x18002eac5  cmp     byte ptr [rcx+8], 0
0x18002eac9  mov     rdi, rdx
0x18002eacc  mov     rbx, rcx
0x18002eacf  jnz     short loc_18002EB1B
0x18002ead1  mov     [rsp+38h+TokenHandle], 0
0x18002eada  call    cs:__imp_GetCurrentThread
0x18002eae0  xor     r8d, r8d; OpenAsSelf
0x18002eae3  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18002eae8  mov     rcx, rax; ThreadHandle
0x18002eaeb  lea     edx, [r8+0Ch]; DesiredAccess
0x18002eaef  call    cs:__imp_OpenThreadToken
0x18002eaf5  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18002eafa  test    eax, eax
0x18002eafc  jnz     short loc_18002EB10
0x18002eafe  test    rcx, rcx
0x18002eb01  jz      short loc_18002EB09
0x18002eb03  call    cs:__imp_CloseHandle
0x18002eb09  mov     eax, 80070005h
0x18002eb0e  jmp     short loc_18002EB23
0x18002eb10  test    rcx, rcx
0x18002eb13  jz      short loc_18002EB1B
0x18002eb15  call    cs:__imp_CloseHandle
0x18002eb1b  mov     rax, [rbx]
0x18002eb1e  mov     [rdi], rax
0x18002eb21  xor     eax, eax
0x18002eb23  mov     rcx, [rsp+38h+var_10]
0x18002eb28  xor     rcx, rsp; StackCookie
0x18002eb2b  call    __security_check_cookie
0x18002eb30  mov     rbx, [rsp+38h+arg_0]
0x18002eb35  add     rsp, 30h
0x18002eb39  pop     rdi
0x18002eb3a  retn
```
