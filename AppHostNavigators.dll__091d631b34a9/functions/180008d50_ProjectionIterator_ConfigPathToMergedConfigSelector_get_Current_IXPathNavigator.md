# ProjectionIterator<ConfigPathToMergedConfigSelector>::get_Current(IXPathNavigator * *)

- ea: `0x180008d50`
- end: `0x180008e4c`
- name: `?get_Current@?$ProjectionIterator@VConfigPathToMergedConfigSelector@@@@UEAAJPEAPEAUIXPathNavigator@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180007b04`
- `0x180008838`
- `0x180008d50`
- `0x18000fcd0`
- `0x180014010`

## string_xrefs

- `0x180008db0`: `get-config`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProjectionIterator<ConfigPathToMergedConfigSelector>::get_Current(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  int v5; // ebx
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp+10h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v4 = a1 + 32;
  if ( !*(_QWORD *)(a1 + 32) && *(_BYTE *)(a1 + 16) )
  {
    v7 = 0;
    v5 = AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastPositionAsDerivedType(
           *(_QWORD *)(a1 + 24),
           &v7);
    if ( v5 < 0 )
    {
LABEL_11:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
      return (unsigned int)v5;
    }
    if ( !v7 )
    {
      v5 = AppHostNavigatorException::SetFunctionEvaluationFailedDueToInvalidSourceNode(L"get-config");
      goto LABEL_11;
    }
    v6 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v7 + 192LL))(
           v7,
           &v6);
    if ( v5 < 0 || (v5 = (**v6)(v6, &GUID_38e2c24d_88c2_4bc5_a7d8_fb0211146dc8, v4), v5 < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
      goto LABEL_11;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  }
  return ATL::CComPtrBase<IXPathNavigator>::CopyTo(v4, a2);
}

```

## disassembly

```asm
0x180008d50  mov     [rsp+arg_0], rbx
0x180008d55  mov     [rsp+arg_18], rsi
0x180008d5a  push    rdi
0x180008d5b  sub     rsp, 20h
0x180008d5f  mov     rsi, rdx
0x180008d62  test    rdx, rdx
0x180008d65  jnz     short loc_180008D71
0x180008d67  mov     eax, 80070057h
0x180008d6c  jmp     loc_180008E3C
0x180008d71  lea     rdi, [rcx+20h]
0x180008d75  cmp     qword ptr [rdi], 0
0x180008d79  jnz     loc_180008E31
0x180008d7f  cmp     byte ptr [rcx+10h], 0
0x180008d83  jz      loc_180008E31
0x180008d89  mov     [rsp+28h+arg_10], 0
0x180008d92  lea     rdx, [rsp+28h+arg_10]
0x180008d97  mov     rcx, [rcx+18h]
0x180008d9b  call    ?TryCastPositionAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathNodeIterator@@PEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastPositionAsDerivedType(IXPathNodeIterator *,AppHostConfigPathNavigator * *)
0x180008da0  mov     ebx, eax
0x180008da2  test    eax, eax
0x180008da4  js      short loc_180008E0E
0x180008da6  mov     rcx, [rsp+28h+arg_10]
0x180008dab  test    rcx, rcx
0x180008dae  jnz     short loc_180008DC0
0x180008db0  lea     rcx, aGetConfig; "get-config"
0x180008db7  call    ?SetFunctionEvaluationFailedDueToInvalidSourceNode@AppHostNavigatorException@@SAJPEBG@Z; AppHostNavigatorException::SetFunctionEvaluationFailedDueToInvalidSourceNode(ushort const *)
0x180008dbc  mov     ebx, eax
0x180008dbe  jmp     short loc_180008E0E
0x180008dc0  mov     [rsp+28h+arg_8], 0
0x180008dc9  mov     rax, [rcx]
0x180008dcc  lea     rdx, [rsp+28h+arg_8]
0x180008dd1  mov     rax, [rax+0C0h]
0x180008dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ddd  mov     ebx, eax
0x180008ddf  test    eax, eax
0x180008de1  js      short loc_180008E03
0x180008de3  mov     rcx, [rsp+28h+arg_8]
0x180008de8  mov     rax, [rcx]
0x180008deb  mov     r8, rdi
0x180008dee  lea     rdx, _GUID_38e2c24d_88c2_4bc5_a7d8_fb0211146dc8
0x180008df5  mov     rax, [rax]
0x180008df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dfd  mov     ebx, eax
0x180008dff  test    eax, eax
0x180008e01  jns     short loc_180008E1C
0x180008e03  lea     rcx, [rsp+28h+arg_8]
0x180008e08  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008e0d  nop
0x180008e0e  lea     rcx, [rsp+28h+arg_10]
0x180008e13  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008e18  mov     eax, ebx
0x180008e1a  jmp     short loc_180008E3C
0x180008e1c  lea     rcx, [rsp+28h+arg_8]
0x180008e21  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008e26  nop
0x180008e27  lea     rcx, [rsp+28h+arg_10]
0x180008e2c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008e31  mov     rdx, rsi
0x180008e34  mov     rcx, rdi
0x180008e37  call    ?CopyTo@?$CComPtrBase@UIXPathNavigator@@@ATL@@QEAAJPEAPEAUIXPathNavigator@@@Z; ATL::CComPtrBase<IXPathNavigator>::CopyTo(IXPathNavigator * *)
0x180008e3c  mov     rbx, [rsp+28h+arg_0]
0x180008e41  mov     rsi, [rsp+28h+arg_18]
0x180008e46  add     rsp, 20h
0x180008e4a  pop     rdi
0x180008e4b  retn
```
