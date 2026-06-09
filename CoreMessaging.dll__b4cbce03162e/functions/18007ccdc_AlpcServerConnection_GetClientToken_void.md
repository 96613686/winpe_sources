# AlpcServerConnection::GetClientToken(void * *)

- ea: `0x18007ccdc`
- end: `0x18007cd67`
- name: `?GetClientToken@AlpcServerConnection@@AEAAJPEAPEAX@Z`
- size: `139`
- prototype: `int(AlpcServerConnection *__hidden this, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007cbb0`
- `0x18007cc50`

## callees

- `0x18007ccdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cd50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cd50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007cd1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007cd1c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007cd31`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007cd31`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007cd3d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007cd3d`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18007cd0c`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18007cd0c`

## pseudocode

```c
__int64 __fastcall AlpcServerConnection::GetClientToken(AlpcServerConnection *this, void **a2)
{
  __int64 *v3; // rdx
  _QWORD *v4; // r9
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax

  *a2 = 0;
  v3 = (__int64 *)*((_QWORD *)this + 8);
  v4 = (_QWORD *)v3[3];
  v5 = *v3;
  if ( !v4 )
    v4 = (_QWORD *)((char *)this + 24);
  v6 = NtAlpcImpersonateClientOfPort(*v4, v5, 0);
  v7 = v6 | 0x10000000;
  if ( v6 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, a2) )
    {
      v7 = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    RevertToSelf();
  }
  return v7;
}

```

## disassembly

```asm
0x18007ccdc  mov     [rsp+arg_0], rbx
0x18007cce1  push    rdi
0x18007cce2  sub     rsp, 20h
0x18007cce6  mov     qword ptr [rdx], 0
0x18007cced  lea     rax, [rcx+18h]
0x18007ccf1  mov     rdi, rdx
0x18007ccf4  mov     rdx, [rcx+40h]
0x18007ccf8  mov     r9, [rdx+18h]
0x18007ccfc  mov     rdx, [rdx]
0x18007ccff  test    r9, r9
0x18007cd02  cmovz   r9, rax
0x18007cd06  xor     r8d, r8d
0x18007cd09  mov     rcx, [r9]
0x18007cd0c  call    cs:__imp_NtAlpcImpersonateClientOfPort
0x18007cd12  mov     ebx, eax
0x18007cd14  or      ebx, 10000000h
0x18007cd1a  jl      short loc_18007CD43
0x18007cd1c  call    cs:__imp_GetCurrentThread
0x18007cd22  mov     edx, 8; DesiredAccess
0x18007cd27  mov     r9, rdi; TokenHandle
0x18007cd2a  mov     rcx, rax; ThreadHandle
0x18007cd2d  lea     r8d, [rdx-7]; OpenAsSelf
0x18007cd31  call    cs:__imp_OpenThreadToken
0x18007cd37  test    eax, eax
0x18007cd39  jz      short loc_18007CD50
0x18007cd3b  xor     ebx, ebx
0x18007cd3d  call    cs:__imp_RevertToSelf
0x18007cd43  mov     eax, ebx
0x18007cd45  mov     rbx, [rsp+28h+arg_0]
0x18007cd4a  add     rsp, 20h
0x18007cd4e  pop     rdi
0x18007cd4f  retn
0x18007cd50  call    cs:__imp_GetLastError
0x18007cd56  mov     ebx, eax
0x18007cd58  test    eax, eax
0x18007cd5a  jle     short loc_18007CD3D
0x18007cd5c  movzx   ebx, ax
0x18007cd5f  or      ebx, 80070000h
0x18007cd65  jmp     short loc_18007CD3D
```
