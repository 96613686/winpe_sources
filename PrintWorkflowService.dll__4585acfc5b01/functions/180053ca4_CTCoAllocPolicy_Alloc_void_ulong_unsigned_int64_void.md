# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180053ca4`
- end: `0x180053d3f`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005384c`
- `0x180056810`

## callees

- `0x18000495c`
- `0x180053ca4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053cc0`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180053ce7`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180053ce7`

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
0x180053ca4  mov     [rsp+arg_8], rbx
0x180053ca9  mov     [rsp+arg_10], rsi
0x180053cae  mov     [rsp+ppMalloc], rcx
0x180053cb3  push    rdi
0x180053cb4  sub     rsp, 20h
0x180053cb8  mov     rcx, r8; cb
0x180053cbb  mov     rdi, r9
0x180053cbe  mov     esi, edx
0x180053cc0  call    cs:__imp_CoTaskMemAlloc
0x180053cc6  mov     [rdi], rax
0x180053cc9  mov     rbx, rax
0x180053ccc  test    rax, rax
0x180053ccf  jz      short loc_180053D2A
0x180053cd1  mov     ecx, 1; dwMemContext
0x180053cd6  test    cl, sil
0x180053cd9  jz      short loc_180053D26
0x180053cdb  xor     esi, esi
0x180053cdd  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180053ce2  mov     [rsp+28h+ppMalloc], rsi
0x180053ce7  call    cs:__imp_CoGetMalloc
0x180053ced  test    eax, eax
0x180053cef  js      short loc_180053D19
0x180053cf1  mov     rcx, [rsp+28h+ppMalloc]
0x180053cf6  mov     rdx, rbx
0x180053cf9  mov     rax, [rcx]
0x180053cfc  mov     rax, [rax+30h]
0x180053d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d05  mov     rcx, [rsp+28h+ppMalloc]
0x180053d0a  mov     rsi, rax
0x180053d0d  mov     rdx, [rcx]
0x180053d10  mov     rax, [rdx+10h]
0x180053d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d19  mov     rcx, [rdi]; void *
0x180053d1c  mov     r8, rsi; Size
0x180053d1f  xor     edx, edx; Val
0x180053d21  call    memset_0
0x180053d26  xor     eax, eax
0x180053d28  jmp     short loc_180053D2F
0x180053d2a  mov     eax, 8007000Eh
0x180053d2f  mov     rbx, [rsp+28h+arg_8]
0x180053d34  mov     rsi, [rsp+28h+arg_10]
0x180053d39  add     rsp, 20h
0x180053d3d  pop     rdi
0x180053d3e  retn
```
