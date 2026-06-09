# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18000ee6c`
- end: `0x18000eefe`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `146`
- prototype: `__int64 __fastcall(IMalloc *, __int64, SIZE_T, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006a90`
- `0x180006bd0`
- `0x18000ef04`

## callees

- `0x18000ee6c`
- `0x18001143a`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000eea6`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000eea6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ee86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ee86`

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
0x18000ee6c  mov     [rsp+arg_8], rbx
0x18000ee71  mov     [rsp+arg_10], rsi
0x18000ee76  mov     [rsp+ppMalloc], rcx
0x18000ee7b  push    rdi
0x18000ee7c  sub     rsp, 20h
0x18000ee80  mov     rcx, r8; cb
0x18000ee83  mov     rdi, r9
0x18000ee86  call    cs:__imp_CoTaskMemAlloc
0x18000ee8c  mov     [rdi], rax
0x18000ee8f  mov     rbx, rax
0x18000ee92  test    rax, rax
0x18000ee95  jz      short loc_18000EEE9
0x18000ee97  xor     esi, esi
0x18000ee99  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18000ee9e  mov     [rsp+28h+ppMalloc], rsi
0x18000eea3  lea     ecx, [rsi+1]; dwMemContext
0x18000eea6  call    cs:__imp_CoGetMalloc
0x18000eeac  test    eax, eax
0x18000eeae  js      short loc_18000EED8
0x18000eeb0  mov     rcx, [rsp+28h+ppMalloc]
0x18000eeb5  mov     rdx, rbx
0x18000eeb8  mov     rax, [rcx]
0x18000eebb  mov     rax, [rax+30h]
0x18000eebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eec4  mov     rcx, [rsp+28h+ppMalloc]
0x18000eec9  mov     rsi, rax
0x18000eecc  mov     rdx, [rcx]
0x18000eecf  mov     rax, [rdx+10h]
0x18000eed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eed8  mov     rcx, [rdi]; void *
0x18000eedb  mov     r8, rsi; Size
0x18000eede  xor     edx, edx; Val
0x18000eee0  call    memset_0
0x18000eee5  xor     eax, eax
0x18000eee7  jmp     short loc_18000EEEE
0x18000eee9  mov     eax, 8007000Eh
0x18000eeee  mov     rbx, [rsp+28h+arg_8]
0x18000eef3  mov     rsi, [rsp+28h+arg_10]
0x18000eef8  add     rsp, 20h
0x18000eefc  pop     rdi
0x18000eefd  retn
```
