# ShieldProvider::ComClientImpersonator::IsAlreadyImpersonating(bool *)

- ea: `0x1800d4214`
- end: `0x1800d42d5`
- name: `?IsAlreadyImpersonating@ComClientImpersonator@ShieldProvider@@AEAAJPEA_N@Z`
- size: `193`
- prototype: `__int64 __fastcall(ShieldProvider::ComClientImpersonator *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d412c`

## callees

- `0x18000d7fc`
- `0x1800d4214`
- `0x1800e1690`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800d4278`
- `KERNEL32!CloseHandle` at `0x1800d42cb`
- `KERNEL32!CloseHandle` at `0x1800d4278`
- `KERNEL32!CloseHandle` at `0x1800d42cb`
- `KERNEL32!GetCurrentThread` at `0x1800d4233`
- `KERNEL32!GetCurrentThread` at `0x1800d4233`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d424c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d424c`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ComClientImpersonator::IsAlreadyImpersonating(
        ShieldProvider::ComClientImpersonator *this,
        bool *a2)
{
  HANDLE CurrentThread; // rax
  bool v4; // di
  __int64 v5; // rdx
  __int64 v6; // rcx
  int LastFailure; // eax
  unsigned int v8; // ebx
  void *v9; // rcx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v4 = 1;
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
    || (LastFailure = HrGetLastFailure(v6, v5), v8 = LastFailure, LastFailure >= 0) )
  {
LABEL_5:
    v9 = TokenHandle;
    *a2 = v4;
    if ( v9 )
      CloseHandle(v9);
    return 0;
  }
  if ( LastFailure == -2147023888 )
  {
    v4 = 0;
    goto LABEL_5;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_e9ad2fe73d953ac4323a17feb709293e_Traceguids,
      (unsigned int)LastFailure);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v8;
}

```

## disassembly

```asm
0x1800d4214  mov     rax, rsp
0x1800d4217  mov     [rax+10h], rbx
0x1800d421b  mov     [rax+18h], rsi
0x1800d421f  mov     [rax+8], rcx
0x1800d4223  push    rdi
0x1800d4224  sub     rsp, 20h
0x1800d4228  mov     rsi, rdx
0x1800d422b  mov     qword ptr [rax+8], 0
0x1800d4233  call    cs:__imp_GetCurrentThread
0x1800d4239  mov     edi, 1
0x1800d423e  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800d4243  mov     r8d, edi; OpenAsSelf
0x1800d4246  mov     rcx, rax; ThreadHandle
0x1800d4249  lea     edx, [rdi+7]; DesiredAccess
0x1800d424c  call    cs:__imp_OpenThreadToken
0x1800d4252  test    eax, eax
0x1800d4254  jnz     short loc_1800D426B
0x1800d4256  call    HrGetLastFailure
0x1800d425b  mov     ebx, eax
0x1800d425d  test    eax, eax
0x1800d425f  jns     short loc_1800D426B
0x1800d4261  cmp     eax, 800703F0h
0x1800d4266  jnz     short loc_1800D4290
0x1800d4268  xor     dil, dil
0x1800d426b  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800d4270  mov     [rsi], dil
0x1800d4273  test    rcx, rcx
0x1800d4276  jz      short loc_1800D427E
0x1800d4278  call    cs:__imp_CloseHandle
0x1800d427e  xor     eax, eax
0x1800d4280  mov     rbx, [rsp+28h+arg_8]
0x1800d4285  mov     rsi, [rsp+28h+arg_10]
0x1800d428a  add     rsp, 20h
0x1800d428e  pop     rdi
0x1800d428f  retn
0x1800d4290  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4297  lea     rax, WPP_GLOBAL_Control
0x1800d429e  cmp     rcx, rax
0x1800d42a1  jz      short loc_1800D42C1
0x1800d42a3  test    [rcx+1Ch], dil
0x1800d42a7  jz      short loc_1800D42C1
0x1800d42a9  mov     rcx, [rcx+10h]
0x1800d42ad  lea     r8, WPP_e9ad2fe73d953ac4323a17feb709293e_Traceguids
0x1800d42b4  mov     edx, 11h
0x1800d42b9  mov     r9d, ebx
0x1800d42bc  call    WPP_SF_d
0x1800d42c1  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800d42c6  test    rcx, rcx
0x1800d42c9  jz      short loc_1800D42D1
0x1800d42cb  call    cs:__imp_CloseHandle
0x1800d42d1  mov     eax, ebx
0x1800d42d3  jmp     short loc_1800D4280
```
