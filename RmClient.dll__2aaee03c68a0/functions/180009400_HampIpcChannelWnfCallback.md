# HampIpcChannelWnfCallback

- ea: `0x180009400`
- end: `0x18000958f`
- name: `HampIpcChannelWnfCallback`
- size: `399`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009400`
- `0x1800095a0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000941e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000945c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000952a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000941e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000945c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000952a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009442`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800094b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009507`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009546`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009442`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800094b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009507`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009546`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009418`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009456`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009524`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009418`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009456`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009524`

## pseudocode

```c
__int64 __fastcall HampIpcChannelWnfCallback(__int64 a1, __int64 a2)
{
  DWORD CurrentThreadId; // eax
  _QWORD **v5; // r15
  _QWORD *v6; // rbx
  __int64 result; // rax
  __int64 *v8; // rbx
  __int64 v9; // rbx
  int v10; // ebp
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // rcx

  RtlAcquireSRWLockExclusive(a1 + 8);
  CurrentThreadId = GetCurrentThreadId();
  v5 = (_QWORD **)(a1 + 40);
  while ( 1 )
  {
    *(_DWORD *)(a1 + 16) = CurrentThreadId;
    v6 = *v5;
    if ( *v5 == v5 )
      break;
    v13 = *v6;
    if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v14 = (_QWORD *)v6[1], (_QWORD *)*v14 != v6) )
      __fastfail(3u);
    *v14 = v13;
    *(_QWORD *)(v13 + 8) = v14;
    *(_OWORD *)v6 = 0;
    *(_DWORD *)(a1 + 16) = 0;
    RtlReleaseSRWLockExclusive(a1 + 8);
    (*(void (__fastcall **)(__int64, _QWORD *, _QWORD))(a1 + 56))(a1, v6 - 3, 0);
    RtlAcquireSRWLockExclusive(a1 + 8);
    CurrentThreadId = GetCurrentThreadId();
  }
  *(_DWORD *)(a1 + 16) = 0;
  result = RtlReleaseSRWLockExclusive(a1 + 8);
  if ( a2 )
  {
    RtlAcquireSRWLockExclusive(a1 + 8);
    *(_DWORD *)(a1 + 16) = GetCurrentThreadId();
    v8 = (__int64 *)(a1 + 24);
    if ( (*(_BYTE *)(a1 + 32) & 1) != 0 )
    {
      if ( !*v8 )
      {
LABEL_12:
        *(_DWORD *)(a1 + 16) = 0;
        return RtlReleaseSRWLockExclusive(a1 + 8);
      }
      v9 = *v8 ^ (unsigned __int64)v8;
    }
    else
    {
      v9 = *v8;
    }
    v10 = *(_BYTE *)(a1 + 32) & 1;
    if ( v9 )
    {
      while ( 1 )
      {
        v11 = HampIpcChannelObjectComparePayloadForTree(a2, v9);
        if ( v11 < 0 )
        {
          v12 = *(_QWORD *)v9;
          if ( v10 && v12 )
            goto LABEL_25;
        }
        else
        {
          if ( v11 <= 0 )
          {
            *(_DWORD *)(a1 + 16) = 0;
            RtlReleaseSRWLockExclusive(a1 + 8);
            return (*(__int64 (__fastcall **)(__int64, __int64, __int64))(a1 + 56))(a1, v9, a2);
          }
          v12 = *(_QWORD *)(v9 + 8);
          if ( v10 && v12 )
          {
LABEL_25:
            v9 ^= v12;
            goto LABEL_11;
          }
        }
        v9 = v12;
LABEL_11:
        if ( !v9 )
          goto LABEL_12;
      }
    }
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x180009400  push    rbx
0x180009402  push    rsi
0x180009403  push    rdi
0x180009404  push    r12
0x180009406  push    r14
0x180009408  push    r15
0x18000940a  sub     rsp, 28h
0x18000940e  mov     rdi, rcx
0x180009411  mov     r14, rdx
0x180009414  add     rcx, 8
0x180009418  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000941e  call    cs:__imp_GetCurrentThreadId
0x180009424  xor     r12d, r12d
0x180009427  lea     r15, [rdi+28h]
0x18000942b  mov     [rdi+10h], eax
0x18000942e  mov     rbx, [r15]
0x180009431  cmp     rbx, r15
0x180009434  jnz     loc_1800094E0
0x18000943a  lea     rcx, [rdi+8]
0x18000943e  mov     [rdi+10h], r12d
0x180009442  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009448  test    r14, r14
0x18000944b  jz      short loc_1800094C1
0x18000944d  lea     rcx, [rdi+8]
0x180009451  mov     [rsp+58h+arg_0], rbp
0x180009456  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000945c  call    cs:__imp_GetCurrentThreadId
0x180009462  mov     [rdi+10h], eax
0x180009465  lea     rbx, [rdi+18h]
0x180009469  test    byte ptr [rbx+8], 1
0x18000946d  lea     rax, [rbx+8]
0x180009471  jnz     loc_18000956A
0x180009477  mov     rbx, [rbx]
0x18000947a  movzx   ebp, byte ptr [rax]
0x18000947d  and     ebp, 1
0x180009480  test    rbx, rbx
0x180009483  jz      short loc_1800094AE
0x180009485  mov     rdx, rbx
0x180009488  mov     rcx, r14
0x18000948b  call    HampIpcChannelObjectComparePayloadForTree
0x180009490  test    eax, eax
0x180009492  js      short loc_1800094CF
0x180009494  jle     loc_180009535
0x18000949a  mov     rax, [rbx+8]
0x18000949e  test    ebp, ebp
0x1800094a0  jnz     loc_18000957E
0x1800094a6  mov     rbx, rax
0x1800094a9  test    rbx, rbx
0x1800094ac  jnz     short loc_180009485
0x1800094ae  lea     rcx, [rdi+8]
0x1800094b2  mov     [rdi+10h], r12d
0x1800094b6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800094bc  mov     rbp, [rsp+58h+arg_0]
0x1800094c1  add     rsp, 28h
0x1800094c5  pop     r15
0x1800094c7  pop     r14
0x1800094c9  pop     r12
0x1800094cb  pop     rdi
0x1800094cc  pop     rsi
0x1800094cd  pop     rbx
0x1800094ce  retn
0x1800094cf  mov     rax, [rbx]
0x1800094d2  test    ebp, ebp
0x1800094d4  jz      short loc_1800094A6
0x1800094d6  test    rax, rax
0x1800094d9  jz      short loc_1800094A6
0x1800094db  jmp     loc_180009587
0x1800094e0  mov     rax, [rbx]
0x1800094e3  cmp     [rax+8], rbx
0x1800094e7  jnz     short loc_180009563
0x1800094e9  mov     rcx, [rbx+8]
0x1800094ed  cmp     [rcx], rbx
0x1800094f0  jnz     short loc_180009563
0x1800094f2  mov     [rcx], rax
0x1800094f5  xorps   xmm0, xmm0
0x1800094f8  mov     [rax+8], rcx
0x1800094fc  lea     rcx, [rdi+8]
0x180009500  movups  xmmword ptr [rbx], xmm0
0x180009503  mov     [rdi+10h], r12d
0x180009507  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000950d  mov     rax, [rdi+38h]
0x180009511  lea     rdx, [rbx-18h]
0x180009515  xor     r8d, r8d
0x180009518  mov     rcx, rdi
0x18000951b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009520  lea     rcx, [rdi+8]
0x180009524  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000952a  call    cs:__imp_GetCurrentThreadId
0x180009530  jmp     loc_18000942B
0x180009535  test    rbx, rbx
0x180009538  jz      loc_1800094AE
0x18000953e  lea     rcx, [rdi+8]
0x180009542  mov     [rdi+10h], r12d
0x180009546  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000954c  mov     rax, [rdi+38h]
0x180009550  mov     r8, r14
0x180009553  mov     rdx, rbx
0x180009556  mov     rcx, rdi
0x180009559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000955e  jmp     loc_1800094BC
0x180009563  mov     ecx, 3
0x180009568  int     29h; Win8: RtlFailFast(ecx)
0x18000956a  mov     rcx, [rbx]
0x18000956d  test    rcx, rcx
0x180009570  jz      loc_1800094AE
0x180009576  xor     rbx, rcx
0x180009579  jmp     loc_18000947A
0x18000957e  test    rax, rax
0x180009581  jz      loc_1800094A6
0x180009587  xor     rbx, rax
0x18000958a  jmp     loc_1800094A9
```
