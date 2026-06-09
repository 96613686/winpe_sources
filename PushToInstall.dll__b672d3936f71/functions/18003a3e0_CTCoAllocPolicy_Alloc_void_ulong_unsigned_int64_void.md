# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18003a3e0`
- end: `0x18003a472`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `146`
- prototype: `__int64 __fastcall(IMalloc *, __int64, SIZE_T, void **)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003dcbc`
- `0x18003ebd8`
- `0x18003ef6c`
- `0x180048c0c`

## callees

- `0x18000316c`
- `0x18003a3e0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003a41a`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003a41a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a3fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a3fa`

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
0x18003a3e0  mov     [rsp+arg_8], rbx
0x18003a3e5  mov     [rsp+arg_10], rsi
0x18003a3ea  mov     [rsp+ppMalloc], rcx
0x18003a3ef  push    rdi
0x18003a3f0  sub     rsp, 20h
0x18003a3f4  mov     rcx, r8; cb
0x18003a3f7  mov     rdi, r9
0x18003a3fa  call    cs:__imp_CoTaskMemAlloc
0x18003a400  mov     [rdi], rax
0x18003a403  mov     rbx, rax
0x18003a406  test    rax, rax
0x18003a409  jz      short loc_18003A45D
0x18003a40b  xor     esi, esi
0x18003a40d  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18003a412  mov     [rsp+28h+ppMalloc], rsi
0x18003a417  lea     ecx, [rsi+1]; dwMemContext
0x18003a41a  call    cs:__imp_CoGetMalloc
0x18003a420  test    eax, eax
0x18003a422  js      short loc_18003A44C
0x18003a424  mov     rcx, [rsp+28h+ppMalloc]
0x18003a429  mov     rdx, rbx
0x18003a42c  mov     rax, [rcx]
0x18003a42f  mov     rax, [rax+30h]
0x18003a433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a438  mov     rcx, [rsp+28h+ppMalloc]
0x18003a43d  mov     rsi, rax
0x18003a440  mov     rdx, [rcx]
0x18003a443  mov     rax, [rdx+10h]
0x18003a447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a44c  mov     rcx, [rdi]; void *
0x18003a44f  mov     r8, rsi; Size
0x18003a452  xor     edx, edx; Val
0x18003a454  call    memset_0
0x18003a459  xor     eax, eax
0x18003a45b  jmp     short loc_18003A462
0x18003a45d  mov     eax, 8007000Eh
0x18003a462  mov     rbx, [rsp+28h+arg_8]
0x18003a467  mov     rsi, [rsp+28h+arg_10]
0x18003a46c  add     rsp, 20h
0x18003a470  pop     rdi
0x18003a471  retn
```
