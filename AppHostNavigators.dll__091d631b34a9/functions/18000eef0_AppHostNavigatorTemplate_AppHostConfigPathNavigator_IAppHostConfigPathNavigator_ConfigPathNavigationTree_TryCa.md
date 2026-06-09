# AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastContextNodeAsDerivedType(IXPathEvaluationContext *,AppHostConfigPathNavigator * *)

- ea: `0x18000eef0`
- end: `0x18000ef43`
- name: `?TryCastContextNodeAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathEvaluationContext@@PEAPEAVAppHostConfigPathNavigator@@@Z`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eac0`
- `0x18000ec40`

## callees

- `0x1800021a4`
- `0x180005920`
- `0x18000eef0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastContextNodeAsDerivedType(
        __int64 a1,
        __int64 *a2)
{
  int v3; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a1 + 24LL))(
         a1,
         &v5);
  if ( v3 >= 0 )
    v3 = AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastAsDerivedType(
           v5,
           a2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000eef0  mov     [rsp+arg_8], rbx
0x18000eef5  push    rdi
0x18000eef6  sub     rsp, 20h
0x18000eefa  mov     rdi, rdx
0x18000eefd  mov     [rsp+28h+arg_0], 0
0x18000ef06  mov     rax, [rcx]
0x18000ef09  lea     rdx, [rsp+28h+arg_0]
0x18000ef0e  mov     rax, [rax+18h]
0x18000ef12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef17  mov     ebx, eax
0x18000ef19  test    eax, eax
0x18000ef1b  js      short loc_18000EF2C
0x18000ef1d  mov     rdx, rdi
0x18000ef20  mov     rcx, [rsp+28h+arg_0]
0x18000ef25  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostConfigPathNavigator * *)
0x18000ef2a  mov     ebx, eax
0x18000ef2c  lea     rcx, [rsp+28h+arg_0]
0x18000ef31  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ef36  mov     eax, ebx
0x18000ef38  mov     rbx, [rsp+28h+arg_8]
0x18000ef3d  add     rsp, 20h
0x18000ef41  pop     rdi
0x18000ef42  retn
```
