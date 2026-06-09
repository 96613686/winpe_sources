# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180020250`
- end: `0x1800202ec`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `156`
- prototype: `__int64 __fastcall(IMalloc *, char, SIZE_T, void **)`
- caller_count: `22`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d4b0`
- `0x18001e7b8`
- `0x18001e940`
- `0x180020218`
- `0x180020cb0`
- `0x1800304bc`
- `0x180032a28`
- `0x180033ea8`
- `0x1800390d0`
- `0x18003ba88`
- `0x18003bc28`
- `0x18004bb94`
- `0x180051538`
- `0x1800520f8`
- `0x1800535d0`
- `0x180055050`
- `0x180066628`
- `0x180066f18`
- `0x180067008`
- `0x180067218`
- `0x18006da58`
- `0x18006f504`

## callees

- `0x180020250`
- `0x18005e740`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180020294`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180020294`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002026c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002026c`

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
0x180020250  mov     [rsp+arg_8], rbx
0x180020255  mov     [rsp+arg_10], rsi
0x18002025a  mov     [rsp+ppMalloc], rcx
0x18002025f  push    rdi
0x180020260  sub     rsp, 20h
0x180020264  mov     rcx, r8; cb
0x180020267  mov     rdi, r9
0x18002026a  mov     esi, edx
0x18002026c  call    cs:__imp_CoTaskMemAlloc
0x180020272  mov     [rdi], rax
0x180020275  mov     rbx, rax
0x180020278  test    rax, rax
0x18002027b  jz      short loc_1800202E5
0x18002027d  test    sil, 1
0x180020281  jz      short loc_1800202D3
0x180020283  xor     esi, esi
0x180020285  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18002028a  mov     ecx, 1; dwMemContext
0x18002028f  mov     [rsp+28h+ppMalloc], rsi
0x180020294  call    cs:__imp_CoGetMalloc
0x18002029a  test    eax, eax
0x18002029c  js      short loc_1800202C6
0x18002029e  mov     rcx, [rsp+28h+ppMalloc]
0x1800202a3  mov     rdx, rbx
0x1800202a6  mov     rax, [rcx]
0x1800202a9  mov     rax, [rax+30h]
0x1800202ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202b2  mov     rcx, [rsp+28h+ppMalloc]
0x1800202b7  mov     rsi, rax
0x1800202ba  mov     rdx, [rcx]
0x1800202bd  mov     rax, [rdx+10h]
0x1800202c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202c6  mov     rcx, [rdi]; void *
0x1800202c9  mov     r8, rsi; Size
0x1800202cc  xor     edx, edx; Val
0x1800202ce  call    memset_0
0x1800202d3  xor     eax, eax
0x1800202d5  mov     rbx, [rsp+28h+arg_8]
0x1800202da  mov     rsi, [rsp+28h+arg_10]
0x1800202df  add     rsp, 20h
0x1800202e3  pop     rdi
0x1800202e4  retn
0x1800202e5  mov     eax, 8007000Eh
0x1800202ea  jmp     short loc_1800202D5
```
