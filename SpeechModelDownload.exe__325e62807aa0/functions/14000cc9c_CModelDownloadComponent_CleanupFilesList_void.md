# CModelDownloadComponent::CleanupFilesList(void)

- ea: `0x14000cc9c`
- end: `0x14000cd12`
- name: `?CleanupFilesList@CModelDownloadComponent@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(CModelDownloadComponent *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000b274`
- `0x1400104b0`

## callees

- `0x1400028d8`
- `0x14000cc9c`

## pseudocode

```c
void __fastcall CModelDownloadComponent::CleanupFilesList(CModelDownloadComponent *this)
{
  _DWORD *v1; // rdi
  int i; // ebp

  v1 = (_DWORD *)((char *)this + 24600);
  if ( *((_QWORD *)this + 3074) )
  {
    for ( i = 0; i < *v1; ++i )
    {
      operator delete(*(void **)(*((_QWORD *)this + 3074) + 16LL * i + 8));
      operator delete(*(void **)(*((_QWORD *)this + 3074) + 16LL * i));
    }
    operator delete(*((void **)this + 3074));
  }
  *((_QWORD *)this + 3074) = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x14000cc9c  push    rbx
0x14000cc9e  push    rbp
0x14000cc9f  push    rsi
0x14000cca0  push    rdi
0x14000cca1  sub     rsp, 28h
0x14000cca5  cmp     qword ptr [rcx+6010h], 0
0x14000ccad  lea     rdi, [rcx+6018h]
0x14000ccb4  mov     rsi, rcx
0x14000ccb7  jz      short loc_14000CCF8
0x14000ccb9  xor     ebp, ebp
0x14000ccbb  cmp     [rdi], ebp
0x14000ccbd  jle     short loc_14000CCEC
0x14000ccbf  mov     rcx, [rsi+6010h]
0x14000ccc6  movsxd  rbx, ebp
0x14000ccc9  add     rbx, rbx
0x14000cccc  mov     rcx, [rcx+rbx*8+8]; Block
0x14000ccd1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ccd6  mov     rcx, [rsi+6010h]
0x14000ccdd  mov     rcx, [rcx+rbx*8]; Block
0x14000cce1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000cce6  inc     ebp
0x14000cce8  cmp     ebp, [rdi]
0x14000ccea  jl      short loc_14000CCBF
0x14000ccec  mov     rcx, [rsi+6010h]; Block
0x14000ccf3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ccf8  mov     qword ptr [rsi+6010h], 0
0x14000cd03  mov     dword ptr [rdi], 0
0x14000cd09  add     rsp, 28h
0x14000cd0d  pop     rdi
0x14000cd0e  pop     rsi
0x14000cd0f  pop     rbp
0x14000cd10  pop     rbx
0x14000cd11  retn
```
