# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x1400382b0`
- end: `0x140038342`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `146`
- prototype: `__int64 __fastcall(IMalloc *, __int64, SIZE_T, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140038c7c`

## callees

- `0x140004e28`
- `0x1400382b0`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1400382ea`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1400382ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400382ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400382ca`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(IMalloc *a1, __int64 a2, SIZE_T a3, void **a4)
{
  void *v5; // rax
  void *v6; // rbx
  size_t v7; // rsi
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  ppMalloc = a1;
  v5 = CoTaskMemAlloc(a3);
  *a4 = v5;
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v7 = 0;
  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v6);
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  memset_0(*a4, 0, v7);
  return 0;
}

```

## disassembly

```asm
0x1400382b0  mov     [rsp+arg_8], rbx
0x1400382b5  mov     [rsp+arg_10], rsi
0x1400382ba  mov     [rsp+ppMalloc], rcx
0x1400382bf  push    rdi
0x1400382c0  sub     rsp, 20h
0x1400382c4  mov     rcx, r8; cb
0x1400382c7  mov     rdi, r9
0x1400382ca  call    cs:__imp_CoTaskMemAlloc
0x1400382d0  mov     [rdi], rax
0x1400382d3  mov     rbx, rax
0x1400382d6  test    rax, rax
0x1400382d9  jz      short loc_14003832D
0x1400382db  xor     esi, esi
0x1400382dd  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x1400382e2  mov     [rsp+28h+ppMalloc], rsi
0x1400382e7  lea     ecx, [rsi+1]; dwMemContext
0x1400382ea  call    cs:__imp_CoGetMalloc
0x1400382f0  test    eax, eax
0x1400382f2  js      short loc_14003831C
0x1400382f4  mov     rcx, [rsp+28h+ppMalloc]
0x1400382f9  mov     rdx, rbx
0x1400382fc  mov     rax, [rcx]
0x1400382ff  mov     rax, [rax+30h]
0x140038303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038308  mov     rcx, [rsp+28h+ppMalloc]
0x14003830d  mov     rsi, rax
0x140038310  mov     rdx, [rcx]
0x140038313  mov     rax, [rdx+10h]
0x140038317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003831c  mov     rcx, [rdi]; void *
0x14003831f  mov     r8, rsi; Size
0x140038322  xor     edx, edx; Val
0x140038324  call    memset_0
0x140038329  xor     eax, eax
0x14003832b  jmp     short loc_140038332
0x14003832d  mov     eax, 8007000Eh
0x140038332  mov     rbx, [rsp+28h+arg_8]
0x140038337  mov     rsi, [rsp+28h+arg_10]
0x14003833c  add     rsp, 20h
0x140038340  pop     rdi
0x140038341  retn
```
