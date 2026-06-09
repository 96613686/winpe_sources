# AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastPositionAsDerivedType(IXPathNodeIterator *,AppHostConfigPathNavigator * *)

- ea: `0x180008838`
- end: `0x18000888b`
- name: `?TryCastPositionAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathNodeIterator@@PEAPEAVAppHostConfigPathNavigator@@@Z`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008c40`
- `0x180008d50`

## callees

- `0x1800021a4`
- `0x180005920`
- `0x180008838`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastPositionAsDerivedType(
        __int64 a1,
        __int64 *a2)
{
  int v3; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a1 + 32LL))(
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
0x180008838  mov     [rsp+arg_8], rbx
0x18000883d  push    rdi
0x18000883e  sub     rsp, 20h
0x180008842  mov     rdi, rdx
0x180008845  mov     [rsp+28h+arg_0], 0
0x18000884e  mov     rax, [rcx]
0x180008851  lea     rdx, [rsp+28h+arg_0]
0x180008856  mov     rax, [rax+20h]
0x18000885a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885f  mov     ebx, eax
0x180008861  test    eax, eax
0x180008863  js      short loc_180008874
0x180008865  mov     rdx, rdi
0x180008868  mov     rcx, [rsp+28h+arg_0]
0x18000886d  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostConfigPathNavigator * *)
0x180008872  mov     ebx, eax
0x180008874  lea     rcx, [rsp+28h+arg_0]
0x180008879  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000887e  mov     eax, ebx
0x180008880  mov     rbx, [rsp+28h+arg_8]
0x180008885  add     rsp, 20h
0x180008889  pop     rdi
0x18000888a  retn
```
