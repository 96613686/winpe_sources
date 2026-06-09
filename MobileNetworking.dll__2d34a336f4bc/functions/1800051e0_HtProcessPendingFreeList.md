# HtProcessPendingFreeList

- ea: `0x1800051e0`
- end: `0x180005318`
- name: `HtProcessPendingFreeList`
- size: `312`
- prototype: `DWORD __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005110`

## callees

- `0x1800051e0`
- `0x18000c6f0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005299`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005299`

## pseudocode

```c
DWORD __fastcall HtProcessPendingFreeList(__int64 a1)
{
  DWORD result; // eax
  DWORD v3; // ebp
  unsigned int v4; // r10d
  __int64 v5; // rdx
  __int64 v6; // r9
  unsigned int v7; // r8d
  void (__fastcall *v8)(__int64); // r14
  __int64 v9; // r15
  __int64 v10; // rdx

  result = GetCurrentThreadId();
  v3 = result;
  if ( !*(_DWORD *)(a1 + 104) || *(_DWORD *)(a1 + 108) != result )
  {
    v4 = *(_DWORD *)(a1 + 112);
    if ( v4 != 0xFFFFFFF )
    {
      *(_DWORD *)(a1 + 104) = 1;
      *(_DWORD *)(a1 + 108) = result;
      do
      {
        v5 = 88;
        v6 = *(_QWORD *)(a1 + 64) + 32LL * v4;
        *(_DWORD *)(a1 + 112) = *(_DWORD *)(v6 + 28) >> 4;
        v7 = *(_DWORD *)(a1 + 80);
        v8 = *(void (__fastcall **)(__int64))(v6 + 16);
        if ( v4 >= v7 )
          v5 = 100;
        v9 = *(_QWORD *)(v6 + 8);
        *(_DWORD *)(v6 + 28) = (16 * *(_DWORD *)(v5 + a1)) | *(_DWORD *)(v6 + 28) & 0xF;
        *(_DWORD *)(v5 + a1) = v4;
        v10 = 84;
        if ( v4 >= v7 )
          v10 = 96;
        ++*(_DWORD *)(v10 + a1);
        if ( v8 )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
          v8(v9);
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
          if ( *(_DWORD *)(a1 + 108) != v3 )
            break;
        }
        v4 = *(_DWORD *)(a1 + 112);
      }
      while ( v4 != 0xFFFFFFF );
      if ( *(_DWORD *)(a1 + 108) == v3 )
        *(_DWORD *)(a1 + 104) = 0;
      result = *(_DWORD *)(a1 + 92);
      if ( result )
      {
        if ( result == *(_DWORD *)(a1 + 96) )
          return HtShrinkTable(a1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800051e0  push    rbx
0x1800051e2  push    rbp
0x1800051e3  push    rsi
0x1800051e4  sub     rsp, 30h
0x1800051e8  mov     rbx, rcx
0x1800051eb  call    cs:__imp_GetCurrentThreadId
0x1800051f1  cmp     dword ptr [rbx+68h], 0
0x1800051f5  mov     ebp, eax
0x1800051f7  jnz     loc_1800052FE
0x1800051fd  mov     r10d, [rbx+70h]
0x180005201  cmp     r10d, 0FFFFFFFh
0x180005208  jz      loc_1800052F6
0x18000520e  mov     [rsp+48h+arg_8], r12
0x180005213  mov     r12d, 64h ; 'd'
0x180005219  mov     [rsp+48h+arg_10], r13
0x18000521e  mov     r13d, 60h ; '`'
0x180005224  mov     [rsp+48h+var_20], r14
0x180005229  mov     [rsp+48h+var_28], r15
0x18000522e  mov     [rsp+48h+arg_0], rdi
0x180005233  mov     dword ptr [rbx+68h], 1
0x18000523a  mov     [rbx+6Ch], ebp
0x18000523d  mov     r9d, r10d
0x180005240  mov     edx, 58h ; 'X'
0x180005245  shl     r9, 5
0x180005249  add     r9, [rbx+40h]
0x18000524d  mov     eax, [r9+1Ch]
0x180005251  shr     eax, 4
0x180005254  mov     [rbx+70h], eax
0x180005257  mov     r8d, [rbx+50h]
0x18000525b  cmp     r10d, r8d
0x18000525e  mov     ecx, [r9+1Ch]
0x180005262  mov     r14, [r9+10h]
0x180005266  cmovnb  rdx, r12
0x18000526a  mov     r15, [r9+8]
0x18000526e  and     ecx, 0Fh
0x180005271  mov     eax, [rdx+rbx]
0x180005274  shl     eax, 4
0x180005277  or      ecx, eax
0x180005279  mov     [r9+1Ch], ecx
0x18000527d  cmp     r10d, r8d
0x180005280  mov     [rdx+rbx], r10d
0x180005284  mov     edx, 54h ; 'T'
0x180005289  cmovnb  rdx, r13
0x18000528d  inc     dword ptr [rdx+rbx]
0x180005290  test    r14, r14
0x180005293  jz      short loc_1800052B9
0x180005295  lea     rcx, [rbx+8]; lpCriticalSection
0x180005299  call    cs:__imp_LeaveCriticalSection
0x18000529f  mov     rcx, r15
0x1800052a2  mov     rax, r14
0x1800052a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052aa  lea     rcx, [rbx+8]; lpCriticalSection
0x1800052ae  call    cs:__imp_EnterCriticalSection
0x1800052b4  cmp     [rbx+6Ch], ebp
0x1800052b7  jnz     short loc_1800052CA
0x1800052b9  mov     r10d, [rbx+70h]
0x1800052bd  cmp     r10d, 0FFFFFFFh
0x1800052c4  jnz     loc_18000523D
0x1800052ca  mov     r15, [rsp+48h+var_28]
0x1800052cf  mov     r14, [rsp+48h+var_20]
0x1800052d4  mov     r13, [rsp+48h+arg_10]
0x1800052d9  mov     r12, [rsp+48h+arg_8]
0x1800052de  mov     rdi, [rsp+48h+arg_0]
0x1800052e3  cmp     [rbx+6Ch], ebp
0x1800052e6  jnz     short loc_1800052EF
0x1800052e8  mov     dword ptr [rbx+68h], 0
0x1800052ef  mov     eax, [rbx+5Ch]
0x1800052f2  test    eax, eax
0x1800052f4  jnz     short loc_180005309
0x1800052f6  add     rsp, 30h
0x1800052fa  pop     rsi
0x1800052fb  pop     rbp
0x1800052fc  pop     rbx
0x1800052fd  retn
0x1800052fe  cmp     [rbx+6Ch], ebp
0x180005301  jnz     loc_1800051FD
0x180005307  jmp     short loc_1800052F6
0x180005309  cmp     eax, [rbx+60h]
0x18000530c  jnz     short loc_1800052F6
0x18000530e  mov     rcx, rbx
0x180005311  call    HtShrinkTable
0x180005316  jmp     short loc_1800052F6
```
