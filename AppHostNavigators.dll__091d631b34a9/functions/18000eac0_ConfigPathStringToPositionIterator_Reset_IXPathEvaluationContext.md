# ConfigPathStringToPositionIterator::Reset(IXPathEvaluationContext *)

- ea: `0x18000eac0`
- end: `0x18000eb9d`
- name: `?Reset@ConfigPathStringToPositionIterator@@UEAAJPEAUIXPathEvaluationContext@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(ConfigPathStringToPositionIterator *__hidden this, struct IXPathEvaluationContext *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180004840`
- `0x180005390`
- `0x18000eac0`
- `0x18000ee94`
- `0x18000eef0`
- `0x18000fe00`
- `0x180012ea8`
- `0x180014010`

## string_xrefs

- `0x18000eb1e`: `get-config`

## pseudocode

```c
__int64 __fastcall ConfigPathStringToPositionIterator::Reset(
        ConfigPathStringToPositionIterator *this,
        struct IXPathEvaluationContext *a2)
{
  int v4; // ebx
  struct IXPathNavigator *v6; // [rsp+40h] [rbp+20h] BYREF
  unsigned __int16 *v7; // [rsp+50h] [rbp+30h] BYREF
  __int64 v8; // [rsp+58h] [rbp+38h] BYREF

  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, struct IXPathEvaluationContext *, unsigned __int16 **))(**((_QWORD **)this + 4)
                                                                                                + 48LL))(
         *((_QWORD *)this + 4),
         a2,
         &v7);
  if ( v4 >= 0 )
  {
    v8 = 0;
    v4 = AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastContextNodeAsDerivedType(
           a2,
           &v8);
    if ( v4 >= 0 )
    {
      if ( v8 )
      {
        v6 = 0;
        v4 = AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::Clone(
               v8,
               &v6);
        if ( v4 < 0 || (v4 = AppHostConfigPathNavigator::MoveToPath(v6, v7), v4 < 0) )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
        }
        else
        {
          SingletonIteratorBase::ResetWithContextNode(this, v6);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
          v4 = 0;
        }
      }
      else
      {
        v4 = AppHostNavigatorException::SetFunctionInvalidContextNodeException(L"get-config");
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  }
  ScopedBSTR::Reset((ScopedBSTR *)&v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000eac0  mov     [rsp-18h+arg_8], rbx
0x18000eac5  push    rbp
0x18000eac6  push    rsi
0x18000eac7  push    rdi
0x18000eac8  mov     rbp, rsp
0x18000eacb  sub     rsp, 20h
0x18000eacf  mov     rdi, rdx
0x18000ead2  mov     rsi, rcx
0x18000ead5  mov     [rbp+arg_10], 0
0x18000eadd  mov     rcx, [rcx+20h]
0x18000eae1  mov     rax, [rcx]
0x18000eae4  lea     r8, [rbp+arg_10]
0x18000eae8  mov     rax, [rax+30h]
0x18000eaec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaf1  mov     ebx, eax
0x18000eaf3  test    eax, eax
0x18000eaf5  js      loc_18000EB85
0x18000eafb  mov     [rbp+arg_18], 0
0x18000eb03  lea     rdx, [rbp+arg_18]
0x18000eb07  mov     rcx, rdi
0x18000eb0a  call    ?TryCastContextNodeAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathEvaluationContext@@PEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastContextNodeAsDerivedType(IXPathEvaluationContext *,AppHostConfigPathNavigator * *)
0x18000eb0f  mov     ebx, eax
0x18000eb11  test    eax, eax
0x18000eb13  js      short loc_18000EB7B
0x18000eb15  mov     rcx, [rbp+arg_18]
0x18000eb19  test    rcx, rcx
0x18000eb1c  jnz     short loc_18000EB2E
0x18000eb1e  lea     rcx, aGetConfig; "get-config"
0x18000eb25  call    ?SetFunctionInvalidContextNodeException@AppHostNavigatorException@@SAJPEBG@Z; AppHostNavigatorException::SetFunctionInvalidContextNodeException(ushort const *)
0x18000eb2a  mov     ebx, eax
0x18000eb2c  jmp     short loc_18000EB7B
0x18000eb2e  mov     [rbp+arg_0], 0
0x18000eb36  lea     rdx, [rbp+arg_0]
0x18000eb3a  call    ?Clone@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@QEAAJPEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::Clone(AppHostConfigPathNavigator * *)
0x18000eb3f  mov     ebx, eax
0x18000eb41  test    eax, eax
0x18000eb43  jns     short loc_18000EB50
0x18000eb45  lea     rcx, [rbp+arg_0]
0x18000eb49  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000eb4e  jmp     short loc_18000EB7B
0x18000eb50  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x18000eb54  mov     rcx, [rbp+arg_0]; this
0x18000eb58  call    ?MoveToPath@AppHostConfigPathNavigator@@QEAAJPEBG@Z; AppHostConfigPathNavigator::MoveToPath(ushort const *)
0x18000eb5d  mov     ebx, eax
0x18000eb5f  test    eax, eax
0x18000eb61  js      short loc_18000EB45
0x18000eb63  mov     rdx, [rbp+arg_0]; struct IXPathNavigator *
0x18000eb67  mov     rcx, rsi; this
0x18000eb6a  call    ?ResetWithContextNode@SingletonIteratorBase@@IEAAJPEAUIXPathNavigator@@@Z; SingletonIteratorBase::ResetWithContextNode(IXPathNavigator *)
0x18000eb6f  nop
0x18000eb70  lea     rcx, [rbp+arg_0]
0x18000eb74  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000eb79  xor     ebx, ebx
0x18000eb7b  lea     rcx, [rbp+arg_18]
0x18000eb7f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000eb84  nop
0x18000eb85  lea     rcx, [rbp+arg_10]; this
0x18000eb89  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000eb8e  mov     eax, ebx
0x18000eb90  mov     rbx, [rsp+20h+arg_8]
0x18000eb95  add     rsp, 20h
0x18000eb99  pop     rdi
0x18000eb9a  pop     rsi
0x18000eb9b  pop     rbp
0x18000eb9c  retn
```
