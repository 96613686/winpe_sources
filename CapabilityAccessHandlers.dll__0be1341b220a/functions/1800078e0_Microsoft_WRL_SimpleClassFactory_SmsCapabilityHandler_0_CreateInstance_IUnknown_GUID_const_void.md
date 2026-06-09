# Microsoft::WRL::SimpleClassFactory<SmsCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800078e0`
- end: `0x180007988`
- name: `?CreateInstance@?$SimpleClassFactory@VSmsCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000645c`
- `0x1800078e0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000790a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000790a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<SmsCapabilityHandler,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<SmsCapabilityHandler,IUnknown,>(&v10);
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
0x1800078e0  mov     [rsp+arg_0], rbx
0x1800078e5  mov     [rsp+arg_10], rsi
0x1800078ea  push    rdi
0x1800078eb  sub     rsp, 20h
0x1800078ef  mov     rdi, r9
0x1800078f2  mov     rsi, r8
0x1800078f5  mov     qword ptr [r9], 0
0x1800078fc  test    rdx, rdx
0x1800078ff  jz      short loc_180007914
0x180007901  xor     edx, edx
0x180007903  mov     ebx, 80040110h
0x180007908  mov     ecx, ebx
0x18000790a  call    cs:__imp_RoOriginateError
0x180007910  mov     eax, ebx
0x180007912  jmp     short loc_180007978
0x180007914  mov     [rsp+28h+arg_8], 0
0x18000791d  lea     rcx, [rsp+28h+arg_8]
0x180007922  call    ??$MakeAndInitialize@VSmsCapabilityHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SmsCapabilityHandler,IUnknown,>(IUnknown * *)
0x180007927  mov     ebx, eax
0x180007929  test    eax, eax
0x18000792b  jns     short loc_180007946
0x18000792d  mov     rcx, [rsp+28h+arg_8]
0x180007932  test    rcx, rcx
0x180007935  jz      short loc_180007944
0x180007937  mov     rdx, [rcx]
0x18000793a  mov     rax, [rdx+10h]
0x18000793e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007943  nop
0x180007944  jmp     short loc_180007910
0x180007946  mov     rbx, [rsp+28h+arg_8]
0x18000794b  mov     rax, [rbx]
0x18000794e  mov     r8, rdi
0x180007951  mov     rdx, rsi
0x180007954  mov     rcx, rbx
0x180007957  mov     rax, [rax]
0x18000795a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000795f  mov     edi, eax
0x180007961  test    rbx, rbx
0x180007964  jz      short loc_180007976
0x180007966  mov     rdx, [rbx]
0x180007969  mov     rcx, rbx
0x18000796c  mov     rax, [rdx+10h]
0x180007970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007975  nop
0x180007976  mov     eax, edi
0x180007978  mov     rbx, [rsp+28h+arg_0]
0x18000797d  mov     rsi, [rsp+28h+arg_10]
0x180007982  add     rsp, 20h
0x180007986  pop     rdi
0x180007987  retn
```
