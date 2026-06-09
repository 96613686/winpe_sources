# Microsoft::WRL::SimpleClassFactory<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006d50`
- end: `0x180006df8`
- name: `?CreateInstance@?$SimpleClassFactory@VParentalControlsAppInventory@AppLimits@FamilySafety@Internal@Windows@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004eb4`
- `0x180006d50`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006d7a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006d7a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory,IUnknown,>(&v10);
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
0x180006d50  mov     [rsp+arg_0], rbx
0x180006d55  mov     [rsp+arg_10], rsi
0x180006d5a  push    rdi
0x180006d5b  sub     rsp, 20h
0x180006d5f  mov     rdi, r9
0x180006d62  mov     rsi, r8
0x180006d65  mov     qword ptr [r9], 0
0x180006d6c  test    rdx, rdx
0x180006d6f  jz      short loc_180006D84
0x180006d71  xor     edx, edx
0x180006d73  mov     ebx, 80040110h
0x180006d78  mov     ecx, ebx
0x180006d7a  call    cs:__imp_RoOriginateError
0x180006d80  mov     eax, ebx
0x180006d82  jmp     short loc_180006DE8
0x180006d84  mov     [rsp+28h+arg_8], 0
0x180006d8d  lea     rcx, [rsp+28h+arg_8]
0x180006d92  call    ??$MakeAndInitialize@VParentalControlsAppInventory@AppLimits@FamilySafety@Internal@Windows@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory,IUnknown,>(IUnknown * *)
0x180006d97  mov     ebx, eax
0x180006d99  test    eax, eax
0x180006d9b  jns     short loc_180006DB6
0x180006d9d  mov     rcx, [rsp+28h+arg_8]
0x180006da2  test    rcx, rcx
0x180006da5  jz      short loc_180006DB4
0x180006da7  mov     rdx, [rcx]
0x180006daa  mov     rax, [rdx+10h]
0x180006dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db3  nop
0x180006db4  jmp     short loc_180006D80
0x180006db6  mov     rbx, [rsp+28h+arg_8]
0x180006dbb  mov     rax, [rbx]
0x180006dbe  mov     r8, rdi
0x180006dc1  mov     rdx, rsi
0x180006dc4  mov     rcx, rbx
0x180006dc7  mov     rax, [rax]
0x180006dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dcf  mov     edi, eax
0x180006dd1  test    rbx, rbx
0x180006dd4  jz      short loc_180006DE6
0x180006dd6  mov     rdx, [rbx]
0x180006dd9  mov     rcx, rbx
0x180006ddc  mov     rax, [rdx+10h]
0x180006de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006de5  nop
0x180006de6  mov     eax, edi
0x180006de8  mov     rbx, [rsp+28h+arg_0]
0x180006ded  mov     rsi, [rsp+28h+arg_10]
0x180006df2  add     rsp, 20h
0x180006df6  pop     rdi
0x180006df7  retn
```
