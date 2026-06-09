# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x1800bb5b0`
- end: `0x1800bb658`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `168`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bb17c`
- `0x1800d3f1c`

## callees

- `0x1800bb5b0`
- `0x1800e6af4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800bb5f9`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800bb5f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb5cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb5cc`

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
0x1800bb5b0  mov     [rsp+arg_8], rbx
0x1800bb5b5  mov     [rsp+arg_10], rsi
0x1800bb5ba  mov     [rsp+ppMalloc], rcx
0x1800bb5bf  push    rdi
0x1800bb5c0  sub     rsp, 20h
0x1800bb5c4  mov     rcx, r8; cb
0x1800bb5c7  mov     rdi, r9
0x1800bb5ca  mov     esi, edx
0x1800bb5cc  call    cs:__imp_CoTaskMemAlloc
0x1800bb5d3  nop     dword ptr [rax+rax+00h]
0x1800bb5d8  mov     [rdi], rax
0x1800bb5db  mov     rbx, rax
0x1800bb5de  test    rax, rax
0x1800bb5e1  jz      short loc_1800BB642
0x1800bb5e3  mov     ecx, 1; dwMemContext
0x1800bb5e8  test    cl, sil
0x1800bb5eb  jz      short loc_1800BB63E
0x1800bb5ed  xor     esi, esi
0x1800bb5ef  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x1800bb5f4  mov     [rsp+28h+ppMalloc], rsi
0x1800bb5f9  call    cs:__imp_CoGetMalloc
0x1800bb600  nop     dword ptr [rax+rax+00h]
0x1800bb605  test    eax, eax
0x1800bb607  js      short loc_1800BB631
0x1800bb609  mov     rcx, [rsp+28h+ppMalloc]
0x1800bb60e  mov     rdx, rbx
0x1800bb611  mov     rax, [rcx]
0x1800bb614  mov     rax, [rax+30h]
0x1800bb618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb61d  mov     rcx, [rsp+28h+ppMalloc]
0x1800bb622  mov     rsi, rax
0x1800bb625  mov     rdx, [rcx]
0x1800bb628  mov     rax, [rdx+10h]
0x1800bb62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb631  mov     rcx, [rdi]; void *
0x1800bb634  mov     r8, rsi; Size
0x1800bb637  xor     edx, edx; Val
0x1800bb639  call    memset_0
0x1800bb63e  xor     eax, eax
0x1800bb640  jmp     short loc_1800BB647
0x1800bb642  mov     eax, 8007000Eh
0x1800bb647  mov     rbx, [rsp+28h+arg_8]
0x1800bb64c  mov     rsi, [rsp+28h+arg_10]
0x1800bb651  add     rsp, 20h
0x1800bb655  pop     rdi
0x1800bb656  retn
```
