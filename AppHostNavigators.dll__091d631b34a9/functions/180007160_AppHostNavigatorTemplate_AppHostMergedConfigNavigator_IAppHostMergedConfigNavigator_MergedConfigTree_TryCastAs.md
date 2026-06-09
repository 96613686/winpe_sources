# AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostMergedConfigNavigator * *)

- ea: `0x180007160`
- end: `0x1800071e5`
- name: `?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostMergedConfigNavigator@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006bd0`
- `0x180006f70`
- `0x18000e368`

## callees

- `0x1800021a4`
- `0x180007160`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::TryCastAsDerivedType(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  if ( !a1 )
    return 0;
  v6 = 0;
  v4 = (**a1)(a1, &GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8, &v6);
  if ( v4 < 0 )
  {
    if ( v4 == -2147467262 )
      v4 = 0;
  }
  else
  {
    v5 = v6;
    v6 = 0;
    *a2 = (v5 - 8) & -(__int64)(v5 != 0);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007160  mov     [rsp+arg_8], rbx
0x180007165  push    rdi
0x180007166  sub     rsp, 20h
0x18000716a  mov     rdi, rdx
0x18000716d  mov     qword ptr [rdx], 0
0x180007174  test    rcx, rcx
0x180007177  jnz     short loc_18000717D
0x180007179  xor     eax, eax
0x18000717b  jmp     short loc_1800071DA
0x18000717d  mov     [rsp+28h+arg_0], 0
0x180007186  mov     rax, [rcx]
0x180007189  lea     r8, [rsp+28h+arg_0]
0x18000718e  lea     rdx, _GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8
0x180007195  mov     rax, [rax]
0x180007198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000719d  mov     ebx, eax
0x18000719f  test    eax, eax
0x1800071a1  js      short loc_1800071C3
0x1800071a3  mov     rcx, [rsp+28h+arg_0]
0x1800071a8  mov     [rsp+28h+arg_0], 0
0x1800071b1  lea     rdx, [rcx-8]
0x1800071b5  neg     rcx
0x1800071b8  sbb     rcx, rcx
0x1800071bb  and     rcx, rdx
0x1800071be  mov     [rdi], rcx
0x1800071c1  jmp     short loc_1800071CE
0x1800071c3  xor     eax, eax
0x1800071c5  cmp     ebx, 80004002h
0x1800071cb  cmovz   ebx, eax
0x1800071ce  lea     rcx, [rsp+28h+arg_0]
0x1800071d3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800071d8  mov     eax, ebx
0x1800071da  mov     rbx, [rsp+28h+arg_8]
0x1800071df  add     rsp, 20h
0x1800071e3  pop     rdi
0x1800071e4  retn
```
