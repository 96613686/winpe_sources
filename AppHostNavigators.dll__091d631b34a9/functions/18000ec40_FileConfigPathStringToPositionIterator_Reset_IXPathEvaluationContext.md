# FileConfigPathStringToPositionIterator::Reset(IXPathEvaluationContext *)

- ea: `0x18000ec40`
- end: `0x18000ee56`
- name: `?Reset@FileConfigPathStringToPositionIterator@@UEAAJPEAUIXPathEvaluationContext@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(FileConfigPathStringToPositionIterator *__hidden this, struct IXPathEvaluationContext *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180004840`
- `0x180005390`
- `0x18000ec40`
- `0x18000ee94`
- `0x18000eef0`
- `0x18000fe00`
- `0x180012ea8`
- `0x180014010`

## string_xrefs

- `0x18000eca2`: `get-raw-config`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FileConfigPathStringToPositionIterator::Reset(
        FileConfigPathStringToPositionIterator *this,
        struct IXPathEvaluationContext *a2)
{
  int v4; // ebx
  __int64 v5; // rbx
  __int64 v6; // rcx
  int v7; // edi
  struct IXPathNavigator *v8; // rdx
  AppHostConfigPathNavigator *v9; // rbx
  struct IXPathNavigator *v11; // [rsp+20h] [rbp-20h] BYREF
  __int64 (__fastcall ***v12)(_QWORD, GUID *, struct IXPathNavigator **); // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 *v13; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+38h] [rbp-8h] BYREF
  __int64 v15; // [rsp+60h] [rbp+20h] BYREF
  __int64 v16; // [rsp+70h] [rbp+30h] BYREF
  AppHostConfigPathNavigator *v17; // [rsp+78h] [rbp+38h] BYREF

  v13 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, struct IXPathEvaluationContext *, unsigned __int16 **))(**((_QWORD **)this + 4)
                                                                                                + 48LL))(
         *((_QWORD *)this + 4),
         a2,
         &v13);
  if ( v4 >= 0 )
  {
    v14 = 0;
    v4 = AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastContextNodeAsDerivedType(
           a2,
           &v14);
    if ( v4 < 0 )
    {
LABEL_19:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
      goto LABEL_20;
    }
    v5 = v14;
    if ( !v14 )
    {
      v4 = AppHostNavigatorException::SetFunctionInvalidContextNodeException(L"get-raw-config");
      goto LABEL_19;
    }
    v15 = 0;
    v6 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 40) + 160LL) + 16LL);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 48LL))(v6, &v15);
    if ( v7 < 0 )
    {
LABEL_6:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
      v4 = v7;
      goto LABEL_19;
    }
    v16 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64 *))(*(_QWORD *)v15 + 24LL))(v15, v13, &v16);
    if ( v7 < 0 )
    {
LABEL_8:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
      goto LABEL_6;
    }
    v8 = 0;
    v11 = 0;
    if ( v16 )
    {
      v17 = 0;
      v4 = AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::Clone(
             v5,
             &v17);
      if ( v4 < 0 )
      {
LABEL_11:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
        goto LABEL_19;
      }
      v9 = v17;
      v7 = AppHostConfigPathNavigator::MoveToPath(v17, v13);
      if ( v7 < 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
        goto LABEL_8;
      }
      v12 = 0;
      v4 = (*(__int64 (__fastcall **)(AppHostConfigPathNavigator *, __int64 (__fastcall ****)(_QWORD, GUID *, struct IXPathNavigator **)))(*(_QWORD *)v9 + 184LL))(
             v9,
             &v12);
      if ( v4 < 0 || (v4 = (**v12)(v12, &GUID_38e2c24d_88c2_4bc5_a7d8_fb0211146dc8, &v11), v4 < 0) )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
        goto LABEL_11;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
      v8 = v11;
    }
    SingletonIteratorBase::ResetWithContextNode(this, v8);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
    v4 = 0;
    goto LABEL_19;
  }
LABEL_20:
  ScopedBSTR::Reset((ScopedBSTR *)&v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ec40  mov     [rsp-18h+arg_8], rbx
0x18000ec45  push    rbp
0x18000ec46  push    rsi
0x18000ec47  push    rdi
0x18000ec48  mov     rbp, rsp
0x18000ec4b  sub     rsp, 40h
0x18000ec4f  mov     rdi, rdx
0x18000ec52  mov     rsi, rcx
0x18000ec55  mov     [rbp+var_10], 0
0x18000ec5d  mov     rcx, [rcx+20h]
0x18000ec61  mov     rax, [rcx]
0x18000ec64  lea     r8, [rbp+var_10]
0x18000ec68  mov     rax, [rax+30h]
0x18000ec6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec71  mov     ebx, eax
0x18000ec73  test    eax, eax
0x18000ec75  js      loc_18000EE3E
0x18000ec7b  mov     [rbp+var_8], 0
0x18000ec83  lea     rdx, [rbp+var_8]
0x18000ec87  mov     rcx, rdi
0x18000ec8a  call    ?TryCastContextNodeAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathEvaluationContext@@PEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastContextNodeAsDerivedType(IXPathEvaluationContext *,AppHostConfigPathNavigator * *)
0x18000ec8f  mov     ebx, eax
0x18000ec91  test    eax, eax
0x18000ec93  js      loc_18000EE34
0x18000ec99  mov     rbx, [rbp+var_8]
0x18000ec9d  test    rbx, rbx
0x18000eca0  jnz     short loc_18000ECB5
0x18000eca2  lea     rcx, aGetRawConfig; "get-raw-config"
0x18000eca9  call    ?SetFunctionInvalidContextNodeException@AppHostNavigatorException@@SAJPEBG@Z; AppHostNavigatorException::SetFunctionInvalidContextNodeException(ushort const *)
0x18000ecae  mov     ebx, eax
0x18000ecb0  jmp     loc_18000EE34
0x18000ecb5  mov     [rbp+arg_0], 0
0x18000ecbd  mov     rax, [rbx+28h]
0x18000ecc1  mov     rcx, [rax+0A0h]
0x18000ecc8  mov     rcx, [rcx+10h]
0x18000eccc  mov     rax, [rcx]
0x18000eccf  lea     rdx, [rbp+arg_0]
0x18000ecd3  mov     rax, [rax+30h]
0x18000ecd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecdc  mov     edi, eax
0x18000ecde  test    eax, eax
0x18000ece0  jns     short loc_18000ECF2
0x18000ece2  lea     rcx, [rbp+arg_0]
0x18000ece6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000eceb  mov     ebx, edi
0x18000eced  jmp     loc_18000EE34
0x18000ecf2  mov     [rbp+arg_10], 0
0x18000ecfa  mov     rcx, [rbp+arg_0]
0x18000ecfe  mov     rax, [rcx]
0x18000ed01  lea     r8, [rbp+arg_10]
0x18000ed05  mov     rdx, [rbp+var_10]
0x18000ed09  mov     rax, [rax+18h]
0x18000ed0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed12  mov     edi, eax
0x18000ed14  test    eax, eax
0x18000ed16  jns     short loc_18000ED23
0x18000ed18  lea     rcx, [rbp+arg_10]
0x18000ed1c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ed21  jmp     short loc_18000ECE2
0x18000ed23  xor     edx, edx
0x18000ed25  mov     [rbp+var_20], rdx
0x18000ed29  cmp     [rbp+arg_10], rdx
0x18000ed2d  jz      loc_18000EE0C
0x18000ed33  mov     [rbp+arg_18], rdx
0x18000ed37  lea     rdx, [rbp+arg_18]
0x18000ed3b  mov     rcx, rbx
0x18000ed3e  call    ?Clone@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@QEAAJPEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::Clone(AppHostConfigPathNavigator * *)
0x18000ed43  mov     ebx, eax
0x18000ed45  test    eax, eax
0x18000ed47  jns     short loc_18000ED75
0x18000ed49  lea     rcx, [rbp+arg_18]
0x18000ed4d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ed52  nop
0x18000ed53  lea     rcx, [rbp+var_20]
0x18000ed57  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ed5c  nop
0x18000ed5d  lea     rcx, [rbp+arg_10]
0x18000ed61  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ed66  nop
0x18000ed67  lea     rcx, [rbp+arg_0]
0x18000ed6b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ed70  jmp     loc_18000EE34
0x18000ed75  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18000ed79  mov     rbx, [rbp+arg_18]
0x18000ed7d  mov     rcx, rbx; this
0x18000ed80  call    ?MoveToPath@AppHostConfigPathNavigator@@QEAAJPEBG@Z; AppHostConfigPathNavigator::MoveToPath(ushort const *)
0x18000ed85  mov     edi, eax
0x18000ed87  test    eax, eax
0x18000ed89  jns     short loc_18000EDA3
0x18000ed8b  lea     rcx, [rbp+arg_18]
0x18000ed8f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ed94  nop
0x18000ed95  lea     rcx, [rbp+var_20]
0x18000ed99  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ed9e  jmp     loc_18000ED18
0x18000eda3  mov     [rbp+var_18], 0
0x18000edab  mov     rax, [rbx]
0x18000edae  lea     rdx, [rbp+var_18]
0x18000edb2  mov     rcx, rbx
0x18000edb5  mov     rax, [rax+0B8h]
0x18000edbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edc1  mov     ebx, eax
0x18000edc3  test    eax, eax
0x18000edc5  jns     short loc_18000EDD5
0x18000edc7  lea     rcx, [rbp+var_18]
0x18000edcb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000edd0  jmp     loc_18000ED49
0x18000edd5  mov     rcx, [rbp+var_18]
0x18000edd9  mov     rax, [rcx]
0x18000eddc  lea     r8, [rbp+var_20]
0x18000ede0  lea     rdx, _GUID_38e2c24d_88c2_4bc5_a7d8_fb0211146dc8
0x18000ede7  mov     rax, [rax]
0x18000edea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edef  mov     ebx, eax
0x18000edf1  lea     rcx, [rbp+var_18]
0x18000edf5  test    eax, eax
0x18000edf7  js      short loc_18000EDCB
0x18000edf9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000edfe  nop
0x18000edff  lea     rcx, [rbp+arg_18]
0x18000ee03  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ee08  mov     rdx, [rbp+var_20]; struct IXPathNavigator *
0x18000ee0c  mov     rcx, rsi; this
0x18000ee0f  call    ?ResetWithContextNode@SingletonIteratorBase@@IEAAJPEAUIXPathNavigator@@@Z; SingletonIteratorBase::ResetWithContextNode(IXPathNavigator *)
0x18000ee14  nop
0x18000ee15  lea     rcx, [rbp+var_20]
0x18000ee19  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ee1e  nop
0x18000ee1f  lea     rcx, [rbp+arg_10]
0x18000ee23  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ee28  nop
0x18000ee29  lea     rcx, [rbp+arg_0]
0x18000ee2d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ee32  xor     ebx, ebx
0x18000ee34  lea     rcx, [rbp+var_8]
0x18000ee38  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ee3d  nop
0x18000ee3e  lea     rcx, [rbp+var_10]; this
0x18000ee42  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000ee47  mov     eax, ebx
0x18000ee49  mov     rbx, [rsp+40h+arg_8]
0x18000ee4e  add     rsp, 40h
0x18000ee52  pop     rdi
0x18000ee53  pop     rsi
0x18000ee54  pop     rbp
0x18000ee55  retn
```
