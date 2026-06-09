# AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::IsNodeType(ushort *,int *)

- ea: `0x180006ec0`
- end: `0x180006f64`
- name: `?IsNodeType@?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@UEAAJPEAGPEAH@Z`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180006ec0`
- `0x18000bf9c`
- `0x180010624`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::IsNodeType(
        __int64 a1,
        const WCHAR *a2,
        _DWORD *a3)
{
  __int64 v6; // rax
  bool IsEnumValue; // al
  __int64 AppHostNodeType; // rax
  bool v10; // al
  unsigned int v11; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v12[32]; // [rsp+28h] [rbp-20h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  try
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 40) + 8LL))(*(_QWORD *)(a1 + 40), v12);
    IsEnumValue = Helpers::IsEnumValue(*(LPCWCH *)(v6 + 8), a2);
  }
  catch ( long v11 )
  {
    return v11;
  }
  catch ( ... )
  {
    return 2147549183LL;
  }
  *a3 = IsEnumValue;
  if ( IsEnumValue )
    return 0;
  AppHostNodeType = ConfigNavigationNode::QueryAppHostNodeType(*(_QWORD *)(a1 + 40), v12);
  v10 = Helpers::IsEnumValue(*(LPCWCH *)(AppHostNodeType + 8), a2);
  *a3 = v10;
  if ( !v10 )
    *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x180006ec0  mov     [rsp+arg_0], rbx
0x180006ec5  mov     [rsp+arg_8], rsi
0x180006eca  push    rdi
0x180006ecb  sub     rsp, 40h
0x180006ecf  mov     rbx, r8
0x180006ed2  mov     rdi, rdx
0x180006ed5  mov     rsi, rcx
0x180006ed8  test    rdx, rdx
0x180006edb  jz      short loc_180006F4E
0x180006edd  test    rbx, rbx
0x180006ee0  jz      short loc_180006F4E
0x180006ee2  mov     rcx, [rcx+28h]
0x180006ee6  mov     rax, [rcx]
0x180006ee9  lea     rdx, [rsp+48h+var_20]
0x180006eee  mov     rax, [rax+8]
0x180006ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ef7  mov     rdx, rdi; lpString1
0x180006efa  mov     rcx, [rax+8]; lpString2
0x180006efe  call    ?IsEnumValue@Helpers@@SA_NPEBG0@Z; Helpers::IsEnumValue(ushort const *,ushort const *)
0x180006f03  movzx   eax, al
0x180006f06  mov     [rbx], eax
0x180006f08  test    eax, eax
0x180006f0a  jz      short loc_180006F10
0x180006f0c  xor     eax, eax
0x180006f0e  jmp     short loc_180006F53
0x180006f10  lea     rdx, [rsp+48h+var_20]
0x180006f15  mov     rcx, [rsi+28h]
0x180006f19  call    ?QueryAppHostNodeType@ConfigNavigationNode@@QEAA?AV?$NamedEnum@W4ConfigNodeType@@@@XZ; ConfigNavigationNode::QueryAppHostNodeType(void)
0x180006f1e  mov     rdx, rdi; lpString1
0x180006f21  mov     rcx, [rax+8]; lpString2
0x180006f25  call    ?IsEnumValue@Helpers@@SA_NPEBG0@Z; Helpers::IsEnumValue(ushort const *,ushort const *)
0x180006f2a  movzx   eax, al
0x180006f2d  mov     [rbx], eax
0x180006f2f  test    eax, eax
0x180006f31  jz      short loc_180006F37
0x180006f33  xor     eax, eax
0x180006f35  jmp     short loc_180006F53
0x180006f37  mov     dword ptr [rbx], 0
0x180006f3d  xor     eax, eax
0x180006f3f  jmp     short loc_180006F53
0x180006f41  mov     eax, [rsp+48h+var_28]
0x180006f45  jmp     short loc_180006F4C
0x180006f47  mov     eax, 8000FFFFh
0x180006f4c  jmp     short loc_180006F53
0x180006f4e  mov     eax, 80070057h
0x180006f53  mov     rbx, [rsp+48h+arg_0]
0x180006f58  mov     rsi, [rsp+48h+arg_8]
0x180006f5d  add     rsp, 40h
0x180006f61  pop     rdi
0x180006f62  retn
```
