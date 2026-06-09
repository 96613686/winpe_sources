# ProjectionIterator<ConfigLocationToRawConfigSelector>::get_Current(IXPathNavigator * *)

- ea: `0x180008b20`
- end: `0x180008c36`
- name: `?get_Current@?$ProjectionIterator@VConfigLocationToRawConfigSelector@@@@UEAAJPEAPEAUIXPathNavigator@@@Z`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180003a48`
- `0x180007b04`
- `0x180008b20`
- `0x18000fcd0`
- `0x180014010`

## string_xrefs

- `0x180008ba3`: `get-raw-config`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProjectionIterator<ConfigLocationToRawConfigSelector>::get_Current(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rcx
  int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp+38h] BYREF
  __int64 v9; // [rsp+60h] [rbp+40h] BYREF
  __int64 v10; // [rsp+68h] [rbp+48h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v4 = a1 + 32;
  if ( !*(_QWORD *)(a1 + 32) && *(_BYTE *)(a1 + 16) )
  {
    v5 = 0;
    v9 = 0;
    v6 = *(_QWORD *)(a1 + 24);
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 32LL))(v6, &v10);
    if ( v7 >= 0 )
    {
      v7 = AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::TryCastAsDerivedType(
             v10,
             &v9);
      v5 = v9;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
    if ( v7 < 0 )
      goto LABEL_13;
    if ( !v5 )
    {
      v7 = AppHostNavigatorException::SetFunctionEvaluationFailedDueToInvalidSourceNode(L"get-raw-config");
LABEL_13:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
      return (unsigned int)v7;
    }
    v8 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v5 + 176LL))(
           v5,
           &v8);
    if ( v7 < 0 || (v7 = (**v8)(v8, &GUID_38e2c24d_88c2_4bc5_a7d8_fb0211146dc8, v4), v7 < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
      goto LABEL_13;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  }
  return ATL::CComPtrBase<IXPathNavigator>::CopyTo(v4, a2);
}

```

## disassembly

```asm
0x180008b20  push    rbp
0x180008b22  push    rbx
0x180008b23  push    rsi
0x180008b24  push    rdi
0x180008b25  push    r14
0x180008b27  mov     rbp, rsp
0x180008b2a  sub     rsp, 20h
0x180008b2e  mov     r14, rdx
0x180008b31  test    rdx, rdx
0x180008b34  jnz     short loc_180008B40
0x180008b36  mov     eax, 80070057h
0x180008b3b  jmp     loc_180008C2B
0x180008b40  lea     rsi, [rcx+20h]
0x180008b44  cmp     qword ptr [rsi], 0
0x180008b48  jnz     loc_180008C20
0x180008b4e  cmp     byte ptr [rcx+10h], 0
0x180008b52  jz      loc_180008C20
0x180008b58  xor     edi, edi
0x180008b5a  mov     [rbp+arg_10], rdi
0x180008b5e  mov     rcx, [rcx+18h]
0x180008b62  mov     [rbp+arg_18], rdi
0x180008b66  mov     rax, [rcx]
0x180008b69  lea     rdx, [rbp+arg_18]
0x180008b6d  mov     rax, [rax+20h]
0x180008b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b76  mov     ebx, eax
0x180008b78  test    eax, eax
0x180008b7a  jns     short loc_180008B7E
0x180008b7c  jmp     short loc_180008B91
0x180008b7e  lea     rdx, [rbp+arg_10]
0x180008b82  mov     rcx, [rbp+arg_18]
0x180008b86  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostConfigLocationsNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostConfigLocationsNavigator * *)
0x180008b8b  mov     ebx, eax
0x180008b8d  mov     rdi, [rbp+arg_10]
0x180008b91  lea     rcx, [rbp+arg_18]
0x180008b95  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008b9a  test    ebx, ebx
0x180008b9c  js      short loc_180008C00
0x180008b9e  test    rdi, rdi
0x180008ba1  jnz     short loc_180008BB3
0x180008ba3  lea     rcx, aGetRawConfig; "get-raw-config"
0x180008baa  call    ?SetFunctionEvaluationFailedDueToInvalidSourceNode@AppHostNavigatorException@@SAJPEBG@Z; AppHostNavigatorException::SetFunctionEvaluationFailedDueToInvalidSourceNode(ushort const *)
0x180008baf  mov     ebx, eax
0x180008bb1  jmp     short loc_180008C00
0x180008bb3  mov     [rbp+arg_8], 0
0x180008bbb  mov     rax, [rdi]
0x180008bbe  lea     rdx, [rbp+arg_8]
0x180008bc2  mov     rcx, rdi
0x180008bc5  mov     rax, [rax+0B0h]
0x180008bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd1  mov     ebx, eax
0x180008bd3  test    eax, eax
0x180008bd5  js      short loc_180008BF6
0x180008bd7  mov     rcx, [rbp+arg_8]
0x180008bdb  mov     rax, [rcx]
0x180008bde  mov     r8, rsi
0x180008be1  lea     rdx, _GUID_38e2c24d_88c2_4bc5_a7d8_fb0211146dc8
0x180008be8  mov     rax, [rax]
0x180008beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bf0  mov     ebx, eax
0x180008bf2  test    eax, eax
0x180008bf4  jns     short loc_180008C0D
0x180008bf6  lea     rcx, [rbp+arg_8]
0x180008bfa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008bff  nop
0x180008c00  lea     rcx, [rbp+arg_10]
0x180008c04  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008c09  mov     eax, ebx
0x180008c0b  jmp     short loc_180008C2B
0x180008c0d  lea     rcx, [rbp+arg_8]
0x180008c11  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008c16  nop
0x180008c17  lea     rcx, [rbp+arg_10]
0x180008c1b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008c20  mov     rdx, r14
0x180008c23  mov     rcx, rsi
0x180008c26  call    ?CopyTo@?$CComPtrBase@UIXPathNavigator@@@ATL@@QEAAJPEAPEAUIXPathNavigator@@@Z; ATL::CComPtrBase<IXPathNavigator>::CopyTo(IXPathNavigator * *)
0x180008c2b  add     rsp, 20h
0x180008c2f  pop     r14
0x180008c31  pop     rdi
0x180008c32  pop     rsi
0x180008c33  pop     rbx
0x180008c34  pop     rbp
0x180008c35  retn
```
