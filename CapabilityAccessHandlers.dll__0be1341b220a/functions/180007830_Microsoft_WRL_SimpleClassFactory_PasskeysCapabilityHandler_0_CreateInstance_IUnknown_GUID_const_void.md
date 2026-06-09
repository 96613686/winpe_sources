# Microsoft::WRL::SimpleClassFactory<PasskeysCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180007830`
- end: `0x1800078d8`
- name: `?CreateInstance@?$SimpleClassFactory@VPasskeysCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006364`
- `0x180007830`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000785a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000785a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<PasskeysCapabilityHandler,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v6; // ebx
  __int64 v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
    return (unsigned int)v6;
  }
  v10 = 0;
  v6 = Microsoft::WRL::Details::MakeAndInitialize<PasskeysCapabilityHandler,IUnknown,>(&v10);
  if ( v6 < 0 )
  {
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)v6;
  }
  v8 = v10;
  v9 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v10)(v10, a3, a4);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x180007830  mov     [rsp+arg_0], rbx
0x180007835  mov     [rsp+arg_10], rsi
0x18000783a  push    rdi
0x18000783b  sub     rsp, 20h
0x18000783f  mov     rdi, r9
0x180007842  mov     rsi, r8
0x180007845  mov     qword ptr [r9], 0
0x18000784c  test    rdx, rdx
0x18000784f  jz      short loc_180007864
0x180007851  xor     edx, edx
0x180007853  mov     ebx, 80040110h
0x180007858  mov     ecx, ebx
0x18000785a  call    cs:__imp_RoOriginateError
0x180007860  mov     eax, ebx
0x180007862  jmp     short loc_1800078C8
0x180007864  mov     [rsp+28h+arg_8], 0
0x18000786d  lea     rcx, [rsp+28h+arg_8]
0x180007872  call    ??$MakeAndInitialize@VPasskeysCapabilityHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<PasskeysCapabilityHandler,IUnknown,>(IUnknown * *)
0x180007877  mov     ebx, eax
0x180007879  test    eax, eax
0x18000787b  jns     short loc_180007896
0x18000787d  mov     rcx, [rsp+28h+arg_8]
0x180007882  test    rcx, rcx
0x180007885  jz      short loc_180007894
0x180007887  mov     rdx, [rcx]
0x18000788a  mov     rax, [rdx+10h]
0x18000788e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007893  nop
0x180007894  jmp     short loc_180007860
0x180007896  mov     rbx, [rsp+28h+arg_8]
0x18000789b  mov     rax, [rbx]
0x18000789e  mov     r8, rdi
0x1800078a1  mov     rdx, rsi
0x1800078a4  mov     rcx, rbx
0x1800078a7  mov     rax, [rax]
0x1800078aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078af  mov     edi, eax
0x1800078b1  test    rbx, rbx
0x1800078b4  jz      short loc_1800078C6
0x1800078b6  mov     rdx, [rbx]
0x1800078b9  mov     rcx, rbx
0x1800078bc  mov     rax, [rdx+10h]
0x1800078c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c5  nop
0x1800078c6  mov     eax, edi
0x1800078c8  mov     rbx, [rsp+28h+arg_0]
0x1800078cd  mov     rsi, [rsp+28h+arg_10]
0x1800078d2  add     rsp, 20h
0x1800078d6  pop     rdi
0x1800078d7  retn
```
