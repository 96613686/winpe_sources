# _AllocArray<IUnknown *,CTCoAllocPolicy>(void *,ulong,unsigned __int64,IUnknown * * *)

- ea: `0x18000a568`
- end: `0x18000a61d`
- name: `??$_AllocArray@PEAUIUnknown@@VCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAPEAUIUnknown@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000a474`

## callees

- `0x18000a568`
- `0x18000b5fe`
- `0x18000c010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000a59e`
- `ole32!CoTaskMemAlloc` at `0x18000a59e`
- `ole32!CoGetMalloc` at `0x18000a5be`
- `ole32!CoGetMalloc` at `0x18000a5be`

## pseudocode

```c
__int64 __fastcall _AllocArray<IUnknown *,CTCoAllocPolicy>(__int64 a1, __int64 a2, unsigned __int64 a3, void **a4)
{
  LPVOID v5; // rax
  LPVOID v6; // rbx
  size_t v7; // rsi
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  ppMalloc = 0;
  *a4 = 0;
  if ( !is_mul_ok(a3, 8u) )
    return 2147942934LL;
  v5 = CoTaskMemAlloc(8 * a3);
  *a4 = v5;
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v7 = 0;
  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(LPMALLOC, LPVOID))ppMalloc->lpVtbl->GetSize)(ppMalloc, v6);
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  memset_0(*a4, 0, v7);
  return 0;
}

```

## disassembly

```asm
0x18000a568  mov     rax, rsp
0x18000a56b  mov     [rax+10h], rbx
0x18000a56f  mov     [rax+18h], rsi
0x18000a573  mov     [rax+8], rcx
0x18000a577  push    rdi
0x18000a578  sub     rsp, 20h
0x18000a57c  mov     qword ptr [rax+8], 0
0x18000a584  mov     rdi, r9
0x18000a587  mov     eax, 8
0x18000a58c  mov     qword ptr [r9], 0
0x18000a593  mul     r8
0x18000a596  test    rdx, rdx
0x18000a599  jnz     short loc_18000A608
0x18000a59b  mov     rcx, rax; cb
0x18000a59e  call    cs:__imp_CoTaskMemAlloc
0x18000a5a4  mov     [rdi], rax
0x18000a5a7  mov     rbx, rax
0x18000a5aa  test    rax, rax
0x18000a5ad  jz      short loc_18000A601
0x18000a5af  xor     esi, esi
0x18000a5b1  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18000a5b6  mov     [rsp+28h+ppMalloc], rsi
0x18000a5bb  lea     ecx, [rsi+1]; dwMemContext
0x18000a5be  call    cs:__imp_CoGetMalloc
0x18000a5c4  test    eax, eax
0x18000a5c6  js      short loc_18000A5F0
0x18000a5c8  mov     rcx, [rsp+28h+ppMalloc]
0x18000a5cd  mov     rdx, rbx
0x18000a5d0  mov     rax, [rcx]
0x18000a5d3  mov     rax, [rax+30h]
0x18000a5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5dc  mov     rcx, [rsp+28h+ppMalloc]
0x18000a5e1  mov     rsi, rax
0x18000a5e4  mov     rdx, [rcx]
0x18000a5e7  mov     rax, [rdx+10h]
0x18000a5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5f0  mov     rcx, [rdi]; void *
0x18000a5f3  mov     r8, rsi; Size
0x18000a5f6  xor     edx, edx; Val
0x18000a5f8  call    memset_0
0x18000a5fd  xor     eax, eax
0x18000a5ff  jmp     short loc_18000A60D
0x18000a601  mov     eax, 8007000Eh
0x18000a606  jmp     short loc_18000A60D
0x18000a608  mov     eax, 80070216h
0x18000a60d  mov     rbx, [rsp+28h+arg_8]
0x18000a612  mov     rsi, [rsp+28h+arg_10]
0x18000a617  add     rsp, 20h
0x18000a61b  pop     rdi
0x18000a61c  retn
```
