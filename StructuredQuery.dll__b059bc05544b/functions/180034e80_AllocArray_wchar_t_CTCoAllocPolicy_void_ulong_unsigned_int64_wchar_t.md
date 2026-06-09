# _AllocArray<wchar_t,CTCoAllocPolicy>(void *,ulong,unsigned __int64,wchar_t * *)

- ea: `0x180034e80`
- end: `0x180034f48`
- name: `??$_AllocArray@_WVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEA_W@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, char, unsigned __int64, void **)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025e60`
- `0x18002ec44`
- `0x180034390`
- `0x180034bdc`
- `0x1800564f0`
- `0x1800694b0`
- `0x1800810fc`

## callees

- `0x180034e80`
- `0x18005e740`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180034ee4`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180034ee4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034ebc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034ebc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _AllocArray<wchar_t,CTCoAllocPolicy>(__int64 a1, char a2, unsigned __int64 a3, void **a4)
{
  LPVOID v6; // rax
  LPVOID v7; // rbx
  size_t v8; // rsi
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  *a4 = 0;
  ppMalloc = 0;
  if ( !is_mul_ok(a3, 2u) )
    return 2147942934LL;
  v6 = CoTaskMemAlloc(2 * a3);
  *a4 = v6;
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  if ( (a2 & 1) != 0 )
  {
    ppMalloc = 0;
    v8 = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(LPMALLOC, LPVOID))ppMalloc->lpVtbl->GetSize)(ppMalloc, v7);
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    memset_0(*a4, 0, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180034e80  mov     [rsp+arg_10], rbp
0x180034e85  mov     [rsp+arg_18], rsi
0x180034e8a  mov     [rsp+ppMalloc], rcx
0x180034e8f  push    rdi
0x180034e90  sub     rsp, 20h
0x180034e94  xor     ebp, ebp
0x180034e96  mov     eax, 2
0x180034e9b  mov     esi, edx
0x180034e9d  mov     [r9], rbp
0x180034ea0  mul     r8
0x180034ea3  mov     rdi, r9
0x180034ea6  mov     [rsp+28h+ppMalloc], rbp
0x180034eab  test    rdx, rdx
0x180034eae  jnz     loc_180034F41
0x180034eb4  mov     rcx, rax; cb
0x180034eb7  mov     [rsp+28h+arg_8], rbx
0x180034ebc  call    cs:__imp_CoTaskMemAlloc
0x180034ec2  mov     [rdi], rax
0x180034ec5  mov     rbx, rax
0x180034ec8  test    rax, rax
0x180034ecb  jz      short loc_180034F3A
0x180034ecd  test    sil, 1
0x180034ed1  jz      short loc_180034F23
0x180034ed3  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180034ed8  mov     [rsp+28h+ppMalloc], rbp
0x180034edd  mov     ecx, 1; dwMemContext
0x180034ee2  mov     esi, ebp
0x180034ee4  call    cs:__imp_CoGetMalloc
0x180034eea  test    eax, eax
0x180034eec  js      short loc_180034F16
0x180034eee  mov     rcx, [rsp+28h+ppMalloc]
0x180034ef3  mov     rdx, rbx
0x180034ef6  mov     rax, [rcx]
0x180034ef9  mov     rax, [rax+30h]
0x180034efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f02  mov     rcx, [rsp+28h+ppMalloc]
0x180034f07  mov     rsi, rax
0x180034f0a  mov     rdx, [rcx]
0x180034f0d  mov     rax, [rdx+10h]
0x180034f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f16  mov     rcx, [rdi]; void *
0x180034f19  mov     r8, rsi; Size
0x180034f1c  xor     edx, edx; Val
0x180034f1e  call    memset_0
0x180034f23  mov     eax, ebp
0x180034f25  mov     rbx, [rsp+28h+arg_8]
0x180034f2a  mov     rbp, [rsp+28h+arg_10]
0x180034f2f  mov     rsi, [rsp+28h+arg_18]
0x180034f34  add     rsp, 20h
0x180034f38  pop     rdi
0x180034f39  retn
0x180034f3a  mov     eax, 8007000Eh
0x180034f3f  jmp     short loc_180034F25
0x180034f41  mov     eax, 80070216h
0x180034f46  jmp     short loc_180034F2A
```
