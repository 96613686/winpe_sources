# AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::CompareTo(IXPathNavigator *,long *)

- ea: `0x180002700`
- end: `0x180002803`
- name: `?CompareTo@?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@UEAAJPEAUIXPathNavigator@@PEAJ@Z`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002700`
- `0x1800039ec`
- `0x180003a48`
- `0x180009e3c`
- `0x18000fbe8`
- `0x180011064`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::CompareTo(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  int v5; // ebx
  __int64 result; // rax
  __int64 v7; // rbx
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rcx
  const WCHAR *v11; // rdx
  int v12; // eax
  struct NavigationNodeBase *v13; // r8
  struct NavigationNodeBase *v14; // rcx
  unsigned int v15; // [rsp+20h] [rbp-18h] BYREF
  __int64 v16; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  try
  {
    v16 = 0;
    v5 = AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::TryCastAsDerivedType(
           a2,
           &v16);
    if ( v5 >= 0 )
    {
      v7 = v16;
      if ( v16 )
      {
        *a3 = 0;
        v9 = *(_QWORD *)(v7 + 40);
        v10 = *(_QWORD *)(a1 + 40);
        if ( v10 == v9 )
          goto LABEL_13;
        v11 = &qword_1800181B0;
        if ( *(_QWORD *)(v9 + 40) )
          v11 = *(const WCHAR **)(v9 + 40);
        v12 = WideCharStringTemplate<String>::CompareTo((const WCHAR **)(v10 + 40), v11);
        *a3 = v12;
        if ( !v12 )
        {
LABEL_13:
          v13 = *(struct NavigationNodeBase **)(v7 + 48);
          v14 = *(struct NavigationNodeBase **)(a1 + 48);
          if ( v14 != v13 )
            *a3 = NavigationNodeBase::ComparePositions(v14, *(_DWORD *)(a1 + 32), v13, *(_DWORD *)(v7 + 32));
        }
        InvasivePtr<AppHostConfigPathNavigator>::Reset(&v16);
        result = 0;
      }
      else
      {
        v8 = AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException();
        InvasivePtr<AppHostConfigPathNavigator>::Reset(&v16);
        result = v8;
      }
    }
    else
    {
      InvasivePtr<AppHostConfigPathNavigator>::Reset(&v16);
      result = (unsigned int)v5;
    }
  }
  catch ( long v15 )
  {
    return v15;
  }
  catch ( ... )
  {
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x180002700  mov     r11, rsp
0x180002703  mov     [r11+8], rbx
0x180002707  mov     [r11+18h], rsi
0x18000270b  push    rdi
0x18000270c  sub     rsp, 30h
0x180002710  mov     rdi, r8
0x180002713  mov     rax, rdx
0x180002716  mov     rsi, rcx
0x180002719  test    rdx, rdx
0x18000271c  jz      loc_1800027ED
0x180002722  test    r8, r8
0x180002725  jz      loc_1800027ED
0x18000272b  mov     qword ptr [r11+10h], 0
0x180002733  lea     rdx, [r11+10h]
0x180002737  mov     rcx, rax
0x18000273a  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostConfigLocationsNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostConfigLocationsNavigator * *)
0x18000273f  mov     ebx, eax
0x180002741  test    eax, eax
0x180002743  jns     short loc_180002756
0x180002745  lea     rcx, [rsp+38h+arg_8]
0x18000274a  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000274f  mov     eax, ebx
0x180002751  jmp     loc_1800027F2
0x180002756  mov     rbx, [rsp+38h+arg_8]
0x18000275b  test    rbx, rbx
0x18000275e  jnz     short loc_180002775
0x180002760  call    ?SetCannotComparePositionOfDifferentTypesException@AppHostNavigatorException@@SAJXZ; AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException(void)
0x180002765  mov     ebx, eax
0x180002767  lea     rcx, [rsp+38h+arg_8]
0x18000276c  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180002771  mov     eax, ebx
0x180002773  jmp     short loc_1800027F2
0x180002775  mov     dword ptr [rdi], 0
0x18000277b  mov     rax, [rbx+28h]
0x18000277f  mov     rcx, [rsi+28h]
0x180002783  cmp     rcx, rax
0x180002786  jz      short loc_1800027B6
0x180002788  lea     rdx, qword_1800181B0
0x18000278f  cmp     qword ptr [rax+28h], 0
0x180002794  cmovnz  rdx, [rax+28h]
0x180002799  add     rcx, 28h ; '('
0x18000279d  call    ?CompareTo@?$WideCharStringTemplate@VString@@@@QEBAJPEBG_N@Z; WideCharStringTemplate<String>::CompareTo(ushort const *,bool)
0x1800027a2  mov     [rdi], eax
0x1800027a4  test    eax, eax
0x1800027a6  jz      short loc_1800027B6
0x1800027a8  lea     rcx, [rsp+38h+arg_8]
0x1800027ad  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800027b2  xor     eax, eax
0x1800027b4  jmp     short loc_1800027F2
0x1800027b6  mov     r8, [rbx+30h]; struct NavigationNodeBase *
0x1800027ba  mov     rcx, [rsi+30h]; struct NavigationNodeBase *
0x1800027be  cmp     rcx, r8
0x1800027c1  jz      short loc_1800027D1
0x1800027c3  mov     r9d, [rbx+20h]; unsigned int
0x1800027c7  mov     edx, [rsi+20h]; unsigned int
0x1800027ca  call    ?ComparePositions@NavigationNodeBase@@SAJPEAV1@K0K@Z; NavigationNodeBase::ComparePositions(NavigationNodeBase *,ulong,NavigationNodeBase *,ulong)
0x1800027cf  mov     [rdi], eax
0x1800027d1  lea     rcx, [rsp+38h+arg_8]
0x1800027d6  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800027db  nop
0x1800027dc  xor     eax, eax
0x1800027de  jmp     short loc_1800027F2
0x1800027e0  mov     eax, [rsp+38h+var_18]
0x1800027e4  jmp     short loc_1800027EB
0x1800027e6  mov     eax, 8000FFFFh
0x1800027eb  jmp     short loc_1800027F2
0x1800027ed  mov     eax, 80070057h
0x1800027f2  mov     rbx, [rsp+38h+arg_0]
0x1800027f7  mov     rsi, [rsp+38h+arg_10]
0x1800027fc  add     rsp, 30h
0x180002800  pop     rdi
0x180002801  retn
```
