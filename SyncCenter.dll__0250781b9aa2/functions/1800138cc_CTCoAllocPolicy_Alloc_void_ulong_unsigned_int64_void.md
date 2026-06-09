# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x1800138cc`
- end: `0x180013967`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001330c`
- `0x180032dc4`
- `0x180034e4c`
- `0x180035aec`
- `0x180036fc4`
- `0x18003721c`
- `0x18003f220`
- `0x18004efa8`

## callees

- `0x1800138cc`
- `0x18005292a`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001390f`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001390f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800138e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800138e8`

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
0x1800138cc  mov     [rsp+arg_8], rbx
0x1800138d1  mov     [rsp+arg_10], rsi
0x1800138d6  mov     [rsp+ppMalloc], rcx
0x1800138db  push    rdi
0x1800138dc  sub     rsp, 20h
0x1800138e0  mov     rcx, r8; cb
0x1800138e3  mov     rdi, r9
0x1800138e6  mov     esi, edx
0x1800138e8  call    cs:__imp_CoTaskMemAlloc
0x1800138ee  mov     [rdi], rax
0x1800138f1  mov     rbx, rax
0x1800138f4  test    rax, rax
0x1800138f7  jz      short loc_180013952
0x1800138f9  mov     ecx, 1; dwMemContext
0x1800138fe  test    cl, sil
0x180013901  jz      short loc_18001394E
0x180013903  xor     esi, esi
0x180013905  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18001390a  mov     [rsp+28h+ppMalloc], rsi
0x18001390f  call    cs:__imp_CoGetMalloc
0x180013915  test    eax, eax
0x180013917  js      short loc_180013941
0x180013919  mov     rcx, [rsp+28h+ppMalloc]
0x18001391e  mov     rdx, rbx
0x180013921  mov     rax, [rcx]
0x180013924  mov     rax, [rax+30h]
0x180013928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001392d  mov     rcx, [rsp+28h+ppMalloc]
0x180013932  mov     rsi, rax
0x180013935  mov     rdx, [rcx]
0x180013938  mov     rax, [rdx+10h]
0x18001393c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013941  mov     rcx, [rdi]; void *
0x180013944  mov     r8, rsi; Size
0x180013947  xor     edx, edx; Val
0x180013949  call    memset_0
0x18001394e  xor     eax, eax
0x180013950  jmp     short loc_180013957
0x180013952  mov     eax, 8007000Eh
0x180013957  mov     rbx, [rsp+28h+arg_8]
0x18001395c  mov     rsi, [rsp+28h+arg_10]
0x180013961  add     rsp, 20h
0x180013965  pop     rdi
0x180013966  retn
```
