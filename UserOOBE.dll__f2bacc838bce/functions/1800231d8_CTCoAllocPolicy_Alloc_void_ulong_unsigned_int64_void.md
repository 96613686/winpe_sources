# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x1800231d8`
- end: `0x180023273`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022a38`
- `0x180047420`

## callees

- `0x180004200`
- `0x1800231d8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800231f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800231f4`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18002321b`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18002321b`

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
0x1800231d8  mov     [rsp+arg_8], rbx
0x1800231dd  mov     [rsp+arg_10], rsi
0x1800231e2  mov     [rsp+ppMalloc], rcx
0x1800231e7  push    rdi
0x1800231e8  sub     rsp, 20h
0x1800231ec  mov     rcx, r8; cb
0x1800231ef  mov     rdi, r9
0x1800231f2  mov     esi, edx
0x1800231f4  call    cs:__imp_CoTaskMemAlloc
0x1800231fa  mov     [rdi], rax
0x1800231fd  mov     rbx, rax
0x180023200  test    rax, rax
0x180023203  jz      short loc_18002325E
0x180023205  mov     ecx, 1; dwMemContext
0x18002320a  test    cl, sil
0x18002320d  jz      short loc_18002325A
0x18002320f  xor     esi, esi
0x180023211  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180023216  mov     [rsp+28h+ppMalloc], rsi
0x18002321b  call    cs:__imp_CoGetMalloc
0x180023221  test    eax, eax
0x180023223  js      short loc_18002324D
0x180023225  mov     rcx, [rsp+28h+ppMalloc]
0x18002322a  mov     rdx, rbx
0x18002322d  mov     rax, [rcx]
0x180023230  mov     rax, [rax+30h]
0x180023234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023239  mov     rcx, [rsp+28h+ppMalloc]
0x18002323e  mov     rsi, rax
0x180023241  mov     rdx, [rcx]
0x180023244  mov     rax, [rdx+10h]
0x180023248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002324d  mov     rcx, [rdi]; void *
0x180023250  mov     r8, rsi; Size
0x180023253  xor     edx, edx; Val
0x180023255  call    memset_0
0x18002325a  xor     eax, eax
0x18002325c  jmp     short loc_180023263
0x18002325e  mov     eax, 8007000Eh
0x180023263  mov     rbx, [rsp+28h+arg_8]
0x180023268  mov     rsi, [rsp+28h+arg_10]
0x18002326d  add     rsp, 20h
0x180023271  pop     rdi
0x180023272  retn
```
