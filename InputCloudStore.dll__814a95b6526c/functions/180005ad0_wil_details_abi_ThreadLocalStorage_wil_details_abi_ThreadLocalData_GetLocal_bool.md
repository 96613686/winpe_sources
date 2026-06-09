# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x180005ad0`
- end: `0x180005b7e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005da0`

## callees

- `0x180005ad0`
- `0x180006778`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005adf`

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
0x180005ad0  push    rbx
0x180005ad2  push    rbp
0x180005ad3  push    rsi
0x180005ad4  push    rdi
0x180005ad5  sub     rsp, 28h
0x180005ad9  mov     bpl, dl
0x180005adc  mov     rdi, rcx
0x180005adf  call    cs:__imp_GetCurrentThreadId
0x180005ae5  mov     ebx, eax
0x180005ae7  mov     esi, eax
0x180005ae9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005af3  shr     rbx, 2
0x180005af7  mul     rbx
0x180005afa  shr     rdx, 3
0x180005afe  lea     r8, [rdx+rdx*4]
0x180005b02  add     r8, r8; unsigned __int64
0x180005b05  sub     rbx, r8
0x180005b08  mov     rax, [rdi+rbx*8]
0x180005b0c  test    rax, rax
0x180005b0f  jz      short loc_180005B21
0x180005b11  cmp     [rax], esi
0x180005b13  jz      short loc_180005B1B
0x180005b15  mov     rax, [rax+8]
0x180005b19  jmp     short loc_180005B0C
0x180005b1b  add     rax, 10h
0x180005b1f  jmp     short loc_180005B75
0x180005b21  test    bpl, bpl
0x180005b24  jz      short loc_180005B73
0x180005b26  mov     edx, 38h ; '8'; dwBytes
0x180005b2b  xor     ecx, ecx; dwFlags
0x180005b2d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005b32  mov     rcx, rax
0x180005b35  test    rax, rax
0x180005b38  jz      short loc_180005B73
0x180005b3a  mov     [rax], esi
0x180005b3c  xor     eax, eax
0x180005b3e  mov     [rcx+4], eax
0x180005b41  mov     [rcx+8], rax
0x180005b45  mov     qword ptr [rcx+10h], 28h ; '('
0x180005b4d  mov     [rcx+18h], rax
0x180005b51  mov     [rcx+20h], rax
0x180005b55  mov     [rcx+28h], rax
0x180005b59  mov     [rcx+30h], rax
0x180005b5d  mov     rax, [rdi+rbx*8]
0x180005b61  mov     [rcx+8], rax
0x180005b65  lock cmpxchg [rdi+rbx*8], rcx
0x180005b6b  jnz     short loc_180005B5D
0x180005b6d  lea     rax, [rcx+10h]
0x180005b71  jmp     short loc_180005B75
0x180005b73  xor     eax, eax
0x180005b75  add     rsp, 28h
0x180005b79  pop     rdi
0x180005b7a  pop     rsi
0x180005b7b  pop     rbp
0x180005b7c  pop     rbx
0x180005b7d  retn
```
