# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800078e0`
- end: `0x18000798e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007cd0`

## callees

- `0x1800078e0`
- `0x180008ee8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800078ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800078ef`

## pseudocode

```c
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(
        __int64 a1,
        char a2)
{
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rbx
  __int64 i; // rax
  DWORD *v10; // rax
  signed __int64 v11; // rcx
  signed __int64 v12; // rax

  CurrentThreadId = GetCurrentThreadId();
  v5 = (unsigned __int64)CurrentThreadId >> 2;
  v6 = 10 * (v5 / 0xA);
  v7 = v5 % 0xA;
  for ( i = *(_QWORD *)(a1 + 8 * v7); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == CurrentThreadId )
      return i + 16;
  }
  if ( !a2 )
    return 0;
  v10 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x38u, v6);
  v11 = (signed __int64)v10;
  if ( !v10 )
    return 0;
  *v10 = CurrentThreadId;
  v10[1] = 0;
  *((_QWORD *)v10 + 1) = 0;
  *((_QWORD *)v10 + 2) = 40;
  *((_QWORD *)v10 + 3) = 0;
  *((_QWORD *)v10 + 4) = 0;
  *((_QWORD *)v10 + 5) = 0;
  *((_QWORD *)v10 + 6) = 0;
  do
  {
    v12 = *(_QWORD *)(a1 + 8 * v7);
    *(_QWORD *)(v11 + 8) = v12;
  }
  while ( v12 != _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8 * v7), v11, v12) );
  return v11 + 16;
}

```

## disassembly

```asm
0x1800078e0  push    rbx
0x1800078e2  push    rbp
0x1800078e3  push    rsi
0x1800078e4  push    rdi
0x1800078e5  sub     rsp, 28h
0x1800078e9  mov     bpl, dl
0x1800078ec  mov     rdi, rcx
0x1800078ef  call    cs:__imp_GetCurrentThreadId
0x1800078f5  mov     ebx, eax
0x1800078f7  mov     esi, eax
0x1800078f9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007903  shr     rbx, 2
0x180007907  mul     rbx
0x18000790a  shr     rdx, 3
0x18000790e  lea     r8, [rdx+rdx*4]
0x180007912  add     r8, r8; unsigned __int64
0x180007915  sub     rbx, r8
0x180007918  mov     rax, [rdi+rbx*8]
0x18000791c  test    rax, rax
0x18000791f  jz      short loc_180007931
0x180007921  cmp     [rax], esi
0x180007923  jz      short loc_18000792B
0x180007925  mov     rax, [rax+8]
0x180007929  jmp     short loc_18000791C
0x18000792b  add     rax, 10h
0x18000792f  jmp     short loc_180007985
0x180007931  test    bpl, bpl
0x180007934  jz      short loc_180007983
0x180007936  mov     edx, 38h ; '8'; dwBytes
0x18000793b  xor     ecx, ecx; dwFlags
0x18000793d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007942  mov     rcx, rax
0x180007945  test    rax, rax
0x180007948  jz      short loc_180007983
0x18000794a  mov     [rax], esi
0x18000794c  xor     eax, eax
0x18000794e  mov     [rcx+4], eax
0x180007951  mov     [rcx+8], rax
0x180007955  mov     qword ptr [rcx+10h], 28h ; '('
0x18000795d  mov     [rcx+18h], rax
0x180007961  mov     [rcx+20h], rax
0x180007965  mov     [rcx+28h], rax
0x180007969  mov     [rcx+30h], rax
0x18000796d  mov     rax, [rdi+rbx*8]
0x180007971  mov     [rcx+8], rax
0x180007975  lock cmpxchg [rdi+rbx*8], rcx
0x18000797b  jnz     short loc_18000796D
0x18000797d  lea     rax, [rcx+10h]
0x180007981  jmp     short loc_180007985
0x180007983  xor     eax, eax
0x180007985  add     rsp, 28h
0x180007989  pop     rdi
0x18000798a  pop     rsi
0x18000798b  pop     rbp
0x18000798c  pop     rbx
0x18000798d  retn
```
