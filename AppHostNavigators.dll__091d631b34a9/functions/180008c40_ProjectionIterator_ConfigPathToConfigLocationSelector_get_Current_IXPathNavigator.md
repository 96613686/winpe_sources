# ProjectionIterator<ConfigPathToConfigLocationSelector>::get_Current(IXPathNavigator * *)

- ea: `0x180008c40`
- end: `0x180008d3c`
- name: `?get_Current@?$ProjectionIterator@VConfigPathToConfigLocationSelector@@@@UEAAJPEAPEAUIXPathNavigator@@@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180007b04`
- `0x180008838`
- `0x180008c40`
- `0x18000fcd0`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProjectionIterator<ConfigPathToConfigLocationSelector>::get_Current(__int64 a1, __int64 a2)
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
      v5 = AppHostNavigatorException::SetFunctionEvaluationFailedDueToInvalidSourceNode(L"get-locations");
      goto LABEL_11;
    }
    v6 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v7 + 184LL))(
           v7,
           &v6);
    if ( v5 < 0 || (v5 = (**v6)(v6, &GUID_38e2c24d_88c2_4bc5_a7d8_fb0211146dc8, v4), v5 < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
      goto LABEL_11;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  }
  return ATL::CComPtrBase<IXPathNavigator>::CopyTo(v4, a2);
}

```

## disassembly

```asm
0x180008c40  mov     [rsp+arg_0], rbx
0x180008c45  mov     [rsp+arg_18], rsi
0x180008c4a  push    rdi
0x180008c4b  sub     rsp, 20h
0x180008c4f  mov     rsi, rdx
0x180008c52  test    rdx, rdx
0x180008c55  jnz     short loc_180008C61
0x180008c57  mov     eax, 80070057h
0x180008c5c  jmp     loc_180008D2C
0x180008c61  lea     rdi, [rcx+20h]
0x180008c65  cmp     qword ptr [rdi], 0
0x180008c69  jnz     loc_180008D21
0x180008c6f  cmp     byte ptr [rcx+10h], 0
0x180008c73  jz      loc_180008D21
0x180008c79  mov     [rsp+28h+arg_10], 0
0x180008c82  lea     rdx, [rsp+28h+arg_10]
0x180008c87  mov     rcx, [rcx+18h]
0x180008c8b  call    ?TryCastPositionAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathNodeIterator@@PEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastPositionAsDerivedType(IXPathNodeIterator *,AppHostConfigPathNavigator * *)
0x180008c90  mov     ebx, eax
0x180008c92  test    eax, eax
0x180008c94  js      short loc_180008CFE
0x180008c96  mov     rcx, [rsp+28h+arg_10]
0x180008c9b  test    rcx, rcx
0x180008c9e  jnz     short loc_180008CB0
0x180008ca0  lea     rcx, aGetLocations; "get-locations"
0x180008ca7  call    ?SetFunctionEvaluationFailedDueToInvalidSourceNode@AppHostNavigatorException@@SAJPEBG@Z; AppHostNavigatorException::SetFunctionEvaluationFailedDueToInvalidSourceNode(ushort const *)
0x180008cac  mov     ebx, eax
0x180008cae  jmp     short loc_180008CFE
0x180008cb0  mov     [rsp+28h+arg_8], 0
0x180008cb9  mov     rax, [rcx]
0x180008cbc  lea     rdx, [rsp+28h+arg_8]
0x180008cc1  mov     rax, [rax+0B8h]
0x180008cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ccd  mov     ebx, eax
0x180008ccf  test    eax, eax
0x180008cd1  js      short loc_180008CF3
0x180008cd3  mov     rcx, [rsp+28h+arg_8]
0x180008cd8  mov     rax, [rcx]
0x180008cdb  mov     r8, rdi
0x180008cde  lea     rdx, _GUID_38e2c24d_88c2_4bc5_a7d8_fb0211146dc8
0x180008ce5  mov     rax, [rax]
0x180008ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ced  mov     ebx, eax
0x180008cef  test    eax, eax
0x180008cf1  jns     short loc_180008D0C
0x180008cf3  lea     rcx, [rsp+28h+arg_8]
0x180008cf8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008cfd  nop
0x180008cfe  lea     rcx, [rsp+28h+arg_10]
0x180008d03  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008d08  mov     eax, ebx
0x180008d0a  jmp     short loc_180008D2C
0x180008d0c  lea     rcx, [rsp+28h+arg_8]
0x180008d11  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008d16  nop
0x180008d17  lea     rcx, [rsp+28h+arg_10]
0x180008d1c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008d21  mov     rdx, rsi
0x180008d24  mov     rcx, rdi
0x180008d27  call    ?CopyTo@?$CComPtrBase@UIXPathNavigator@@@ATL@@QEAAJPEAPEAUIXPathNavigator@@@Z; ATL::CComPtrBase<IXPathNavigator>::CopyTo(IXPathNavigator * *)
0x180008d2c  mov     rbx, [rsp+28h+arg_0]
0x180008d31  mov     rsi, [rsp+28h+arg_18]
0x180008d36  add     rsp, 20h
0x180008d3a  pop     rdi
0x180008d3b  retn
```
