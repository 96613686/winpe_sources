# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x1800b92a8`
- end: `0x1800b9343`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b8e84`
- `0x1800d15b8`

## callees

- `0x1800b92a8`
- `0x1800e3c04`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800b92eb`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800b92eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b92c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b92c4`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(IMalloc *a1, char a2, SIZE_T a3, void **a4)
{
  void *v6; // rax
  void *v7; // rbx
  size_t v8; // rsi
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  ppMalloc = a1;
  v6 = CoTaskMemAlloc(a3);
  *a4 = v6;
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  if ( (a2 & 1) != 0 )
  {
    v8 = 0;
    ppMalloc = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v7);
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    memset_0(*a4, 0, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b92a8  mov     [rsp+arg_8], rbx
0x1800b92ad  mov     [rsp+arg_10], rsi
0x1800b92b2  mov     [rsp+ppMalloc], rcx
0x1800b92b7  push    rdi
0x1800b92b8  sub     rsp, 20h
0x1800b92bc  mov     rcx, r8; cb
0x1800b92bf  mov     rdi, r9
0x1800b92c2  mov     esi, edx
0x1800b92c4  call    cs:__imp_CoTaskMemAlloc
0x1800b92ca  mov     [rdi], rax
0x1800b92cd  mov     rbx, rax
0x1800b92d0  test    rax, rax
0x1800b92d3  jz      short loc_1800B932E
0x1800b92d5  mov     ecx, 1; dwMemContext
0x1800b92da  test    cl, sil
0x1800b92dd  jz      short loc_1800B932A
0x1800b92df  xor     esi, esi
0x1800b92e1  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x1800b92e6  mov     [rsp+28h+ppMalloc], rsi
0x1800b92eb  call    cs:__imp_CoGetMalloc
0x1800b92f1  test    eax, eax
0x1800b92f3  js      short loc_1800B931D
0x1800b92f5  mov     rcx, [rsp+28h+ppMalloc]
0x1800b92fa  mov     rdx, rbx
0x1800b92fd  mov     rax, [rcx]
0x1800b9300  mov     rax, [rax+30h]
0x1800b9304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9309  mov     rcx, [rsp+28h+ppMalloc]
0x1800b930e  mov     rsi, rax
0x1800b9311  mov     rdx, [rcx]
0x1800b9314  mov     rax, [rdx+10h]
0x1800b9318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b931d  mov     rcx, [rdi]; void *
0x1800b9320  mov     r8, rsi; Size
0x1800b9323  xor     edx, edx; Val
0x1800b9325  call    memset_0
0x1800b932a  xor     eax, eax
0x1800b932c  jmp     short loc_1800B9333
0x1800b932e  mov     eax, 8007000Eh
0x1800b9333  mov     rbx, [rsp+28h+arg_8]
0x1800b9338  mov     rsi, [rsp+28h+arg_10]
0x1800b933d  add     rsp, 20h
0x1800b9341  pop     rdi
0x1800b9342  retn
```
