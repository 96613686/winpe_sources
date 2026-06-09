# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180042b6c`
- end: `0x180042c02`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `150`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e6e4`
- `0x18005caf4`

## callees

- `0x18002d1c8`
- `0x180042b6c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180042baa`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180042baa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042b88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042b88`

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
0x180042b6c  mov     [rsp+arg_8], rbx
0x180042b71  mov     [rsp+arg_10], rsi
0x180042b76  mov     [rsp+ppMalloc], rcx
0x180042b7b  push    rdi
0x180042b7c  sub     rsp, 20h
0x180042b80  mov     rcx, r8; cb
0x180042b83  mov     rdi, r9
0x180042b86  mov     esi, edx
0x180042b88  call    cs:__imp_CoTaskMemAlloc
0x180042b8e  mov     [rdi], rax
0x180042b91  mov     rbx, rax
0x180042b94  test    rax, rax
0x180042b97  jz      short loc_180042BED
0x180042b99  mov     ecx, 1; dwMemContext
0x180042b9e  test    cl, sil
0x180042ba1  jz      short loc_180042BE9
0x180042ba3  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180042ba8  xor     esi, esi
0x180042baa  call    cs:__imp_CoGetMalloc
0x180042bb0  test    eax, eax
0x180042bb2  js      short loc_180042BDC
0x180042bb4  mov     rcx, [rsp+28h+ppMalloc]
0x180042bb9  mov     rdx, rbx
0x180042bbc  mov     rax, [rcx]
0x180042bbf  mov     rax, [rax+30h]
0x180042bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bc8  mov     rcx, [rsp+28h+ppMalloc]
0x180042bcd  mov     rsi, rax
0x180042bd0  mov     rdx, [rcx]
0x180042bd3  mov     rax, [rdx+10h]
0x180042bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bdc  mov     rcx, [rdi]; void *
0x180042bdf  mov     r8, rsi; Size
0x180042be2  xor     edx, edx; Val
0x180042be4  call    memset_0
0x180042be9  xor     eax, eax
0x180042beb  jmp     short loc_180042BF2
0x180042bed  mov     eax, 8007000Eh
0x180042bf2  mov     rbx, [rsp+28h+arg_8]
0x180042bf7  mov     rsi, [rsp+28h+arg_10]
0x180042bfc  add     rsp, 20h
0x180042c00  pop     rdi
0x180042c01  retn
```
