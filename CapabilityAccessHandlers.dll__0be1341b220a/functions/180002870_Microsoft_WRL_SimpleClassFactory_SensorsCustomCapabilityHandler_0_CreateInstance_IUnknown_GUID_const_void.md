# Microsoft::WRL::SimpleClassFactory<SensorsCustomCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002870`
- end: `0x180002918`
- name: `?CreateInstance@?$SimpleClassFactory@VSensorsCustomCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002870`
- `0x180002920`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000289a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000289a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<SensorsCustomCapabilityHandler,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<SensorsCustomCapabilityHandler,IUnknown,>(&v10);
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
0x180002870  mov     [rsp+arg_0], rbx
0x180002875  mov     [rsp+arg_10], rsi
0x18000287a  push    rdi
0x18000287b  sub     rsp, 20h
0x18000287f  mov     rdi, r9
0x180002882  mov     rsi, r8
0x180002885  mov     qword ptr [r9], 0
0x18000288c  test    rdx, rdx
0x18000288f  jz      short loc_1800028A4
0x180002891  xor     edx, edx
0x180002893  mov     ebx, 80040110h
0x180002898  mov     ecx, ebx
0x18000289a  call    cs:__imp_RoOriginateError
0x1800028a0  mov     eax, ebx
0x1800028a2  jmp     short loc_180002908
0x1800028a4  mov     [rsp+28h+arg_8], 0
0x1800028ad  lea     rcx, [rsp+28h+arg_8]
0x1800028b2  call    ??$MakeAndInitialize@VSensorsCustomCapabilityHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SensorsCustomCapabilityHandler,IUnknown,>(IUnknown * *)
0x1800028b7  mov     ebx, eax
0x1800028b9  test    eax, eax
0x1800028bb  jns     short loc_1800028D6
0x1800028bd  mov     rcx, [rsp+28h+arg_8]
0x1800028c2  test    rcx, rcx
0x1800028c5  jz      short loc_1800028D4
0x1800028c7  mov     rdx, [rcx]
0x1800028ca  mov     rax, [rdx+10h]
0x1800028ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d3  nop
0x1800028d4  jmp     short loc_1800028A0
0x1800028d6  mov     rbx, [rsp+28h+arg_8]
0x1800028db  mov     rax, [rbx]
0x1800028de  mov     r8, rdi
0x1800028e1  mov     rdx, rsi
0x1800028e4  mov     rcx, rbx
0x1800028e7  mov     rax, [rax]
0x1800028ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ef  mov     edi, eax
0x1800028f1  test    rbx, rbx
0x1800028f4  jz      short loc_180002906
0x1800028f6  mov     rdx, [rbx]
0x1800028f9  mov     rcx, rbx
0x1800028fc  mov     rax, [rdx+10h]
0x180002900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002905  nop
0x180002906  mov     eax, edi
0x180002908  mov     rbx, [rsp+28h+arg_0]
0x18000290d  mov     rsi, [rsp+28h+arg_10]
0x180002912  add     rsp, 20h
0x180002916  pop     rdi
0x180002917  retn
```
