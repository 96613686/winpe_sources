# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18001e740`
- end: `0x18001e7db`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e150`
- `0x180038914`
- `0x180046e6c`

## callees

- `0x180003e00`
- `0x18001e740`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e75c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e75c`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001e783`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001e783`

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
0x18001e740  mov     [rsp+arg_8], rbx
0x18001e745  mov     [rsp+arg_10], rsi
0x18001e74a  mov     [rsp+ppMalloc], rcx
0x18001e74f  push    rdi
0x18001e750  sub     rsp, 20h
0x18001e754  mov     rcx, r8; cb
0x18001e757  mov     rdi, r9
0x18001e75a  mov     esi, edx
0x18001e75c  call    cs:__imp_CoTaskMemAlloc
0x18001e762  mov     [rdi], rax
0x18001e765  mov     rbx, rax
0x18001e768  test    rax, rax
0x18001e76b  jz      short loc_18001E7C6
0x18001e76d  mov     ecx, 1; dwMemContext
0x18001e772  test    cl, sil
0x18001e775  jz      short loc_18001E7C2
0x18001e777  xor     esi, esi
0x18001e779  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18001e77e  mov     [rsp+28h+ppMalloc], rsi
0x18001e783  call    cs:__imp_CoGetMalloc
0x18001e789  test    eax, eax
0x18001e78b  js      short loc_18001E7B5
0x18001e78d  mov     rcx, [rsp+28h+ppMalloc]
0x18001e792  mov     rdx, rbx
0x18001e795  mov     rax, [rcx]
0x18001e798  mov     rax, [rax+30h]
0x18001e79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7a1  mov     rcx, [rsp+28h+ppMalloc]
0x18001e7a6  mov     rsi, rax
0x18001e7a9  mov     rdx, [rcx]
0x18001e7ac  mov     rax, [rdx+10h]
0x18001e7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7b5  mov     rcx, [rdi]; void *
0x18001e7b8  mov     r8, rsi; Size
0x18001e7bb  xor     edx, edx; Val
0x18001e7bd  call    memset_0
0x18001e7c2  xor     eax, eax
0x18001e7c4  jmp     short loc_18001E7CB
0x18001e7c6  mov     eax, 8007000Eh
0x18001e7cb  mov     rbx, [rsp+28h+arg_8]
0x18001e7d0  mov     rsi, [rsp+28h+arg_10]
0x18001e7d5  add     rsp, 20h
0x18001e7d9  pop     rdi
0x18001e7da  retn
```
