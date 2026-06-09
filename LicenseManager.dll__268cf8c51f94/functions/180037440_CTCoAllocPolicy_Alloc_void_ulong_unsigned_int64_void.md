# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180037440`
- end: `0x1800374ea`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `170`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b3f0`
- `0x18003bf58`
- `0x18006a520`

## callees

- `0x180037440`
- `0x1800769f4`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003745c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003745c`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180037499`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180037499`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(IMalloc *a1, char a2, SIZE_T a3, void **a4)
{
  void *v6; // rax
  void *v7; // rbx
  size_t v9; // rsi
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  ppMalloc = a1;
  v6 = CoTaskMemAlloc(a3);
  *a4 = v6;
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  if ( (a2 & 1) != 0 )
  {
    v9 = 0;
    ppMalloc = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v7);
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    memset_0(*a4, 0, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180037440  mov     [rsp+arg_8], rbx
0x180037445  mov     [rsp+arg_10], rsi
0x18003744a  mov     [rsp+ppMalloc], rcx
0x18003744f  push    rdi
0x180037450  sub     rsp, 20h
0x180037454  mov     rcx, r8; cb
0x180037457  mov     rdi, r9
0x18003745a  mov     esi, edx
0x18003745c  call    cs:__imp_CoTaskMemAlloc
0x180037462  mov     [rdi], rax
0x180037465  mov     rbx, rax
0x180037468  test    rax, rax
0x18003746b  jnz     short loc_180037482
0x18003746d  mov     eax, 8007000Eh
0x180037472  mov     rbx, [rsp+28h+arg_8]
0x180037477  mov     rsi, [rsp+28h+arg_10]
0x18003747c  add     rsp, 20h
0x180037480  pop     rdi
0x180037481  retn
0x180037482  test    sil, 1
0x180037486  jz      short loc_1800374D8
0x180037488  xor     esi, esi
0x18003748a  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18003748f  mov     ecx, 1; dwMemContext
0x180037494  mov     [rsp+28h+ppMalloc], rsi
0x180037499  call    cs:__imp_CoGetMalloc
0x18003749f  test    eax, eax
0x1800374a1  js      short loc_1800374CB
0x1800374a3  mov     rcx, [rsp+28h+ppMalloc]
0x1800374a8  mov     rdx, rbx
0x1800374ab  mov     rax, [rcx]
0x1800374ae  mov     rax, [rax+30h]
0x1800374b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374b7  mov     rcx, [rsp+28h+ppMalloc]
0x1800374bc  mov     rsi, rax
0x1800374bf  mov     rdx, [rcx]
0x1800374c2  mov     rax, [rdx+10h]
0x1800374c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374cb  mov     rcx, [rdi]; void *
0x1800374ce  mov     r8, rsi; Size
0x1800374d1  xor     edx, edx; Val
0x1800374d3  call    memset_0
0x1800374d8  mov     rbx, [rsp+28h+arg_8]
0x1800374dd  xor     eax, eax
0x1800374df  mov     rsi, [rsp+28h+arg_10]
0x1800374e4  add     rsp, 20h
0x1800374e8  pop     rdi
0x1800374e9  retn
```
