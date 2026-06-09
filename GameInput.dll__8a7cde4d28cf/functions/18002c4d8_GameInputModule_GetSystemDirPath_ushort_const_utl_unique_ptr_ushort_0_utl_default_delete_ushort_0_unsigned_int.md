# GameInputModule::GetSystemDirPath(ushort const *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &,unsigned __int64 *)

- ea: `0x18002c4d8`
- end: `0x18002c665`
- name: `?GetSystemDirPath@GameInputModule@@CAJPEBGAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@PEA_K@Z`
- size: `397`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18002c6fc`
- `0x18002ca98`

## callees

- `0x18000c11c`
- `0x18002c4d8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18002c56e`
- `ntdll!RtlAllocateHeap` at `0x18002c56e`
- `ntdll!towlower` at `0x18002c5b4`
- `ntdll!towlower` at `0x18002c5e7`
- `ntdll!towlower` at `0x18002c5b4`
- `ntdll!towlower` at `0x18002c5e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c511`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c591`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c511`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c632`

## pseudocode

```c
signed int __fastcall GameInputModule::GetSystemDirPath(
        __int64 a1,
        const struct std::nothrow_t *a2,
        unsigned __int64 *a3)
{
  void *v4; // rcx
  UINT SystemDirectoryW; // eax
  __int64 v8; // rbp
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rdi
  SIZE_T v11; // rax
  WCHAR *Heap; // rax
  WCHAR *v13; // rbx
  signed int result; // eax
  const struct std::nothrow_t *v15; // rdx
  unsigned __int64 v16; // rdi
  unsigned __int64 i; // rbp
  unsigned __int64 v18; // rbp
  void *v19; // rcx

  v4 = *(void **)a2;
  *(_QWORD *)a2 = 0;
  if ( v4 )
    operator delete(v4, a2);
  if ( a3 )
    *a3 = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v8 = SystemDirectoryW;
  if ( SystemDirectoryW )
  {
    if ( a1 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(a1 + 2 * v9) );
    }
    else
    {
      v9 = 0;
    }
    v10 = v9 + SystemDirectoryW + 1LL;
    if ( !a1 )
      v10 = SystemDirectoryW;
    v11 = 2 * v10;
    if ( !is_mul_ok(v10, 2u) )
      v11 = -1;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    v13 = Heap;
    if ( !Heap )
      return -2147024882;
    v16 = GetSystemDirectoryW(Heap, v10);
    if ( v16 == v8 - 1 )
    {
      for ( i = 0; i < v16; ++i )
        v13[i] = towlower(v13[i]);
      if ( a1 )
      {
        v13[v16] = 92;
        v18 = 0;
        ++v16;
        if ( v9 )
        {
          do
            v13[v16++] = towlower(*(_WORD *)(a1 + 2 * v18++));
          while ( v18 < v9 );
        }
      }
      v13[v16] = 0;
      v19 = *(void **)a2;
      *(_QWORD *)a2 = v13;
      if ( v19 )
        operator delete(v19, v15);
      if ( a3 )
        *a3 = v16;
      return 0;
    }
    operator delete(v13, v15);
    if ( v16 )
      return -2147418113;
  }
  result = GetLastError();
  if ( !result )
    return -2147418113;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002c4d8  push    rbx
0x18002c4da  push    rbp
0x18002c4db  push    rsi
0x18002c4dc  push    rdi
0x18002c4dd  push    r12
0x18002c4df  push    r13
0x18002c4e1  push    r14
0x18002c4e3  push    r15
0x18002c4e5  sub     rsp, 28h
0x18002c4e9  xor     r13d, r13d
0x18002c4ec  mov     r15, rcx
0x18002c4ef  mov     rcx, [rdx]; P
0x18002c4f2  mov     r14, r8
0x18002c4f5  mov     [rdx], r13
0x18002c4f8  mov     r12, rdx
0x18002c4fb  test    rcx, rcx
0x18002c4fe  jz      short loc_18002C505
0x18002c500  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c505  test    r14, r14
0x18002c508  jz      short loc_18002C50D
0x18002c50a  mov     [r14], r13
0x18002c50d  xor     edx, edx; uSize
0x18002c50f  xor     ecx, ecx; lpBuffer
0x18002c511  call    cs:__imp_GetSystemDirectoryW
0x18002c518  nop     dword ptr [rax+rax+00h]
0x18002c51d  mov     ebp, eax
0x18002c51f  test    eax, eax
0x18002c521  jz      loc_18002C632
0x18002c527  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002c52b  test    r15, r15
0x18002c52e  jz      short loc_18002C53F
0x18002c530  mov     rsi, rcx
0x18002c533  inc     rsi
0x18002c536  cmp     [r15+rsi*2], r13w
0x18002c53b  jnz     short loc_18002C533
0x18002c53d  jmp     short loc_18002C542
0x18002c53f  mov     rsi, r13
0x18002c542  lea     rdi, [rbp+1]
0x18002c546  mov     eax, 2
0x18002c54b  add     rdi, rsi
0x18002c54e  test    r15, r15
0x18002c551  cmovz   rdi, rbp
0x18002c555  mul     rdi
0x18002c558  cmovb   rax, rcx
0x18002c55c  mov     rcx, gs:60h
0x18002c565  mov     r8, rax; Size
0x18002c568  xor     edx, edx; Flags
0x18002c56a  mov     rcx, [rcx+30h]; HeapHandle
0x18002c56e  call    cs:__imp_RtlAllocateHeap
0x18002c575  nop     dword ptr [rax+rax+00h]
0x18002c57a  mov     rbx, rax
0x18002c57d  test    rax, rax
0x18002c580  jnz     short loc_18002C58C
0x18002c582  mov     eax, 8007000Eh
0x18002c587  jmp     loc_18002C653
0x18002c58c  mov     edx, edi; uSize
0x18002c58e  mov     rcx, rbx; lpBuffer
0x18002c591  call    cs:__imp_GetSystemDirectoryW
0x18002c598  nop     dword ptr [rax+rax+00h]
0x18002c59d  mov     edi, eax
0x18002c59f  lea     rax, [rbp-1]
0x18002c5a3  cmp     rdi, rax
0x18002c5a6  jnz     short loc_18002C625
0x18002c5a8  mov     rbp, r13
0x18002c5ab  test    rdi, rdi
0x18002c5ae  jz      short loc_18002C5CC
0x18002c5b0  movzx   ecx, word ptr [rbx+rbp*2]; C
0x18002c5b4  call    cs:__imp_towlower
0x18002c5bb  nop     dword ptr [rax+rax+00h]
0x18002c5c0  mov     [rbx+rbp*2], ax
0x18002c5c4  inc     rbp
0x18002c5c7  cmp     rbp, rdi
0x18002c5ca  jb      short loc_18002C5B0
0x18002c5cc  test    r15, r15
0x18002c5cf  jz      short loc_18002C602
0x18002c5d1  mov     word ptr [rbx+rdi*2], 5Ch ; '\'
0x18002c5d7  mov     rbp, r13
0x18002c5da  inc     rdi
0x18002c5dd  test    rsi, rsi
0x18002c5e0  jz      short loc_18002C602
0x18002c5e2  movzx   ecx, word ptr [r15+rbp*2]; C
0x18002c5e7  call    cs:__imp_towlower
0x18002c5ee  nop     dword ptr [rax+rax+00h]
0x18002c5f3  mov     [rbx+rdi*2], ax
0x18002c5f7  inc     rbp
0x18002c5fa  inc     rdi
0x18002c5fd  cmp     rbp, rsi
0x18002c600  jb      short loc_18002C5E2
0x18002c602  mov     [rbx+rdi*2], r13w
0x18002c607  mov     rcx, [r12]; P
0x18002c60b  mov     [r12], rbx
0x18002c60f  test    rcx, rcx
0x18002c612  jz      short loc_18002C619
0x18002c614  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c619  test    r14, r14
0x18002c61c  jz      short loc_18002C621
0x18002c61e  mov     [r14], rdi
0x18002c621  xor     eax, eax
0x18002c623  jmp     short loc_18002C653
0x18002c625  mov     rcx, rbx; P
0x18002c628  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c62d  test    rdi, rdi
0x18002c630  jnz     short loc_18002C642
0x18002c632  call    cs:__imp_GetLastError
0x18002c639  nop     dword ptr [rax+rax+00h]
0x18002c63e  test    eax, eax
0x18002c640  jnz     short loc_18002C649
0x18002c642  mov     eax, 8000FFFFh
0x18002c647  jmp     short loc_18002C653
0x18002c649  jle     short loc_18002C653
0x18002c64b  movzx   eax, ax
0x18002c64e  or      eax, 80070000h
0x18002c653  add     rsp, 28h
0x18002c657  pop     r15
0x18002c659  pop     r14
0x18002c65b  pop     r13
0x18002c65d  pop     r12
0x18002c65f  pop     rdi
0x18002c660  pop     rsi
0x18002c661  pop     rbp
0x18002c662  pop     rbx
0x18002c663  retn
```
