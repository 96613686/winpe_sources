# CExecSignalProcess

- ea: `0x14000f120`
- end: `0x14000f1a5`
- name: `CExecSignalProcess`
- size: `133`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002310`
- `0x14000becc`

## string_xrefs

- `0x14000f167`: `onecore\vm\compute\service\cexec\service\cexecrequestserver.cpp`

## pseudocode

```c
__int64 __fastcall CExecSignalProcess(__int64 a1, __int64 a2, int a3)
{
  _QWORD v4[2]; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v5[3]; // [rsp+30h] [rbp-40h] BYREF
  __int16 v6; // [rsp+48h] [rbp-28h]
  _QWORD v7[2]; // [rsp+50h] [rbp-20h] BYREF
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+8h]
  int v9; // [rsp+88h] [rbp+18h] BYREF
  int v10; // [rsp+90h] [rbp+20h] BYREF

  v10 = a3;
  v9 = a2;
  v5[2] = 0;
  v4[0] = &v9;
  v4[1] = &v10;
  v5[0] = retaddr;
  v5[1] = "onecore\\vm\\compute\\service\\cexec\\service\\cexecrequestserver.cpp";
  v6 = 168;
  v7[0] = &wil::details::functor_wrapper_void<_lambda_b5c30e5caab78b1ec9be6970e8f178a8_>::`vftable';
  v7[1] = v4;
  return wil::details::ResultFromException(v5, a2, v7);
}

```

## disassembly

```asm
0x14000f120  mov     [rsp-8+arg_10], r8d
0x14000f125  mov     [rsp-8+arg_8], edx
0x14000f129  push    rbp
0x14000f12a  mov     rbp, rsp
0x14000f12d  sub     rsp, 70h
0x14000f131  mov     rax, cs:__security_cookie
0x14000f138  xor     rax, rsp
0x14000f13b  mov     [rbp+var_10], rax
0x14000f13f  lea     rax, [rbp+arg_8]
0x14000f143  mov     [rbp+var_30], 0
0x14000f14b  mov     [rbp+var_50], rax
0x14000f14f  lea     r8, [rbp+var_20]
0x14000f153  lea     rax, [rbp+arg_10]
0x14000f157  mov     [rbp+var_48], rax
0x14000f15b  lea     rcx, [rbp+var_40]
0x14000f15f  mov     rax, [rbp+8]
0x14000f163  mov     [rbp+var_40], rax
0x14000f167  lea     rax, aOnecoreVmCompu_0; "onecore\\vm\\compute\\service\\cexec\\s"...
0x14000f16e  mov     [rbp+var_38], rax
0x14000f172  mov     eax, 0A8h
0x14000f177  mov     [rbp+var_28], ax
0x14000f17b  lea     rax, ??_7?$functor_wrapper_void@V_lambda_b5c30e5caab78b1ec9be6970e8f178a8_@@@details@wil@@6B@; const wil::details::functor_wrapper_void<_lambda_b5c30e5caab78b1ec9be6970e8f178a8_>::`vftable'
0x14000f182  mov     [rbp+var_20], rax
0x14000f186  lea     rax, [rbp+var_50]
0x14000f18a  mov     [rbp+var_18], rax
0x14000f18e  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x14000f193  mov     rcx, [rbp+var_10]
0x14000f197  xor     rcx, rsp; StackCookie
0x14000f19a  call    __security_check_cookie
0x14000f19f  add     rsp, 70h
0x14000f1a3  pop     rbp
0x14000f1a4  retn
```
