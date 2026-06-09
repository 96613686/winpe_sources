# std::vector<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>,std::allocator<std::unique_ptr<SharedMemory,std::default_delete<SharedMemory>>>>::_Reallocate(unsigned __int64)

- ea: `0x18000d654`
- end: `0x18000d754`
- name: `?_Reallocate@?$vector@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@V?$allocator@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `256`
- prototype: `__int64 *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c9a8`

## callees

- `0x180002a88`
- `0x180002bc8`
- `0x18000c964`
- `0x18000d654`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d708`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d71e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d708`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d71e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6ff`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d6ec`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d6ec`

## pseudocode

```c
__int64 *__fastcall std::vector<std::unique_ptr<SharedMemory>>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  __int64 **v6; // rdi
  __int64 v7; // rcx
  __int64 *v8; // r14
  __int64 *v9; // r13
  __int64 v10; // r12
  __int64 v11; // rdi
  const void *v12; // rcx
  __int64 *result; // rax
  _QWORD *v14; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v14 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v5 = operator new(8 * a2), v4 = v5, (v14 = v5) == 0) )
      std::_Xbad_alloc();
  }
  v6 = (__int64 **)(a1 + 8);
  try
  {
    std::_Uninit_move<std::unique_ptr<SharedMemory> *,std::unique_ptr<SharedMemory> *,std::allocator<std::unique_ptr<SharedMemory>>,std::unique_ptr<SharedMemory>>(
      *(__int64 **)a1,
      *(__int64 **)(a1 + 8),
      v4);
    v8 = *(__int64 **)a1;
    v9 = *v6;
    v10 = ((__int64)*v6 - *(_QWORD *)a1) >> 3;
    if ( *(_QWORD *)a1 )
    {
      if ( v8 != v9 )
      {
        do
        {
          v11 = *v8;
          if ( *v8 )
          {
            v12 = *(const void **)(v11 + 8);
            if ( v12 )
              UnmapViewOfFile(v12);
            if ( (unsigned __int64)(*(_QWORD *)v11 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(*(HANDLE *)v11);
            operator delete((void *)v11);
          }
          ++v8;
        }
        while ( v8 != v9 );
        v6 = (__int64 **)(a1 + 8);
      }
      operator delete(*(void **)a1);
    }
    *(_QWORD *)(a1 + 16) = &v4[a2];
    result = &v4[v10];
    *v6 = result;
    *(_QWORD *)a1 = v4;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(v7, v14);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000d654  mov     [rsp+arg_0], rbx
0x18000d659  mov     [rsp+arg_10], rsi
0x18000d65e  push    rdi
0x18000d65f  push    r12
0x18000d661  push    r13
0x18000d663  push    r14
0x18000d665  push    r15
0x18000d667  sub     rsp, 30h
0x18000d66b  mov     r15, rdx
0x18000d66e  mov     rsi, rcx
0x18000d671  xor     ebx, ebx
0x18000d673  mov     [rsp+58h+arg_8], rbx
0x18000d678  test    rdx, rdx
0x18000d67b  jz      short loc_18000D6AE
0x18000d67d  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000d687  cmp     rdx, rax
0x18000d68a  ja      loc_18000D74E
0x18000d690  lea     rcx, ds:0[rdx*8]; Size
0x18000d698  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d69d  mov     rbx, rax
0x18000d6a0  mov     [rsp+58h+arg_8], rax
0x18000d6a5  test    rax, rax
0x18000d6a8  jz      loc_18000D74E
0x18000d6ae  lea     rdi, [rsi+8]
0x18000d6b2  mov     r8, rbx
0x18000d6b5  mov     rdx, [rdi]
0x18000d6b8  mov     rcx, [rsi]
0x18000d6bb  call    ??$_Uninit_move@PEAV?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<SharedMemory> *,std::unique_ptr<SharedMemory> *,std::allocator<std::unique_ptr<SharedMemory>>,std::unique_ptr<SharedMemory>>(std::unique_ptr<SharedMemory> *,std::unique_ptr<SharedMemory> *,std::unique_ptr<SharedMemory> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<SharedMemory>>> &,std::unique_ptr<SharedMemory> *,std::_Nonscalar_ptr_iterator_tag)
0x18000d6c0  nop
0x18000d6c1  mov     r14, [rsi]
0x18000d6c4  mov     r13, [rdi]
0x18000d6c7  mov     r12, r13
0x18000d6ca  sub     r12, r14
0x18000d6cd  sar     r12, 3
0x18000d6d1  test    r14, r14
0x18000d6d4  jz      short loc_18000D724
0x18000d6d6  cmp     r14, r13
0x18000d6d9  jz      short loc_18000D71B
0x18000d6db  mov     rdi, [r14]
0x18000d6de  test    rdi, rdi
0x18000d6e1  jz      short loc_18000D70E
0x18000d6e3  mov     rcx, [rdi+8]; lpBaseAddress
0x18000d6e7  test    rcx, rcx
0x18000d6ea  jz      short loc_18000D6F2
0x18000d6ec  call    cs:__imp_UnmapViewOfFile
0x18000d6f2  mov     rcx, [rdi]; hObject
0x18000d6f5  lea     rax, [rcx-1]
0x18000d6f9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d6fd  ja      short loc_18000D705
0x18000d6ff  call    cs:__imp_CloseHandle
0x18000d705  mov     rcx, rdi
0x18000d708  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d70e  add     r14, 8
0x18000d712  cmp     r14, r13
0x18000d715  jnz     short loc_18000D6DB
0x18000d717  lea     rdi, [rsi+8]
0x18000d71b  mov     rcx, [rsi]
0x18000d71e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d724  lea     rax, [rbx+r15*8]
0x18000d728  mov     [rsi+10h], rax
0x18000d72c  lea     rax, [rbx+r12*8]
0x18000d730  mov     [rdi], rax
0x18000d733  mov     [rsi], rbx
0x18000d736  mov     rbx, [rsp+58h+arg_0]
0x18000d73b  mov     rsi, [rsp+58h+arg_10]
0x18000d740  add     rsp, 30h
0x18000d744  pop     r15
0x18000d746  pop     r14
0x18000d748  pop     r13
0x18000d74a  pop     r12
0x18000d74c  pop     rdi
0x18000d74d  retn
0x18000d74e  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
