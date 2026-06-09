# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18002f410`
- end: `0x18002f4ab`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ff5c`
- `0x180048ee4`
- `0x18006940c`
- `0x180069574`
- `0x180072930`
- `0x180087c38`
- `0x180087f24`

## callees

- `0x180004a70`
- `0x18002f410`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f42c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f42c`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18002f453`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18002f453`

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
0x18002f410  mov     [rsp+arg_8], rbx
0x18002f415  mov     [rsp+arg_10], rsi
0x18002f41a  mov     [rsp+ppMalloc], rcx
0x18002f41f  push    rdi
0x18002f420  sub     rsp, 20h
0x18002f424  mov     rcx, r8; cb
0x18002f427  mov     rdi, r9
0x18002f42a  mov     esi, edx
0x18002f42c  call    cs:__imp_CoTaskMemAlloc
0x18002f432  mov     [rdi], rax
0x18002f435  mov     rbx, rax
0x18002f438  test    rax, rax
0x18002f43b  jz      short loc_18002F496
0x18002f43d  mov     ecx, 1; dwMemContext
0x18002f442  test    cl, sil
0x18002f445  jz      short loc_18002F492
0x18002f447  xor     esi, esi
0x18002f449  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18002f44e  mov     [rsp+28h+ppMalloc], rsi
0x18002f453  call    cs:__imp_CoGetMalloc
0x18002f459  test    eax, eax
0x18002f45b  js      short loc_18002F485
0x18002f45d  mov     rcx, [rsp+28h+ppMalloc]
0x18002f462  mov     rdx, rbx
0x18002f465  mov     rax, [rcx]
0x18002f468  mov     rax, [rax+30h]
0x18002f46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f471  mov     rcx, [rsp+28h+ppMalloc]
0x18002f476  mov     rsi, rax
0x18002f479  mov     rdx, [rcx]
0x18002f47c  mov     rax, [rdx+10h]
0x18002f480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f485  mov     rcx, [rdi]; void *
0x18002f488  mov     r8, rsi; Size
0x18002f48b  xor     edx, edx; Val
0x18002f48d  call    memset_0
0x18002f492  xor     eax, eax
0x18002f494  jmp     short loc_18002F49B
0x18002f496  mov     eax, 8007000Eh
0x18002f49b  mov     rbx, [rsp+28h+arg_8]
0x18002f4a0  mov     rsi, [rsp+28h+arg_10]
0x18002f4a5  add     rsp, 20h
0x18002f4a9  pop     rdi
0x18002f4aa  retn
```
