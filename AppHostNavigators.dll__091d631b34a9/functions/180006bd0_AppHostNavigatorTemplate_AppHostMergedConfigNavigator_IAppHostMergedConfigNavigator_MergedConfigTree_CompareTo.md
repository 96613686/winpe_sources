# AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::CompareTo(IXPathNavigator *,long *)

- ea: `0x180006bd0`
- end: `0x180006ced`
- name: `?CompareTo@?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@UEAAJPEAUIXPathNavigator@@PEAJ@Z`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800039ec`
- `0x180006bd0`
- `0x180007160`
- `0x18000fbe8`
- `0x180011064`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180006c85`
- `KERNEL32!CompareStringOrdinal` at `0x180006c85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::CompareTo(
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
  const WCHAR *v11; // rax
  const WCHAR *v12; // r8
  int v13; // eax
  struct NavigationNodeBase *v14; // r8
  struct NavigationNodeBase *v15; // rcx
  unsigned int v16; // [rsp+30h] [rbp-18h] BYREF
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  try
  {
    v17 = 0;
    v5 = AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::TryCastAsDerivedType(
           a2,
           &v17);
    if ( v5 >= 0 )
    {
      v7 = v17;
      if ( v17 )
      {
        *a3 = 0;
        v9 = *(_QWORD *)(v7 + 40);
        v10 = *(_QWORD *)(a1 + 40);
        if ( v10 == v9 )
          goto LABEL_13;
        v11 = *(const WCHAR **)(v9 + 136);
        v12 = &qword_1800181B0;
        if ( v11 )
          v12 = v11;
        v13 = CompareStringOrdinal(*(LPCWCH *)(v10 + 136), -1, v12, -1, 1);
        *a3 = v13 - 2;
        if ( v13 == 2 )
        {
LABEL_13:
          v14 = *(struct NavigationNodeBase **)(v7 + 48);
          v15 = *(struct NavigationNodeBase **)(a1 + 48);
          if ( v15 != v14 )
            *a3 = NavigationNodeBase::ComparePositions(v15, *(_DWORD *)(a1 + 32), v14, *(_DWORD *)(v7 + 32));
        }
        InvasivePtr<AppHostConfigPathNavigator>::Reset(&v17);
        result = 0;
      }
      else
      {
        v8 = AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException();
        InvasivePtr<AppHostConfigPathNavigator>::Reset(&v17);
        result = v8;
      }
    }
    else
    {
      InvasivePtr<AppHostConfigPathNavigator>::Reset(&v17);
      result = (unsigned int)v5;
    }
  }
  catch ( long v16 )
  {
    return v16;
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
0x180006bd0  mov     r11, rsp
0x180006bd3  mov     [r11+8], rbx
0x180006bd7  mov     [r11+18h], rsi
0x180006bdb  push    rdi
0x180006bdc  sub     rsp, 40h
0x180006be0  mov     rdi, r8
0x180006be3  mov     rax, rdx
0x180006be6  mov     rsi, rcx
0x180006be9  test    rdx, rdx
0x180006bec  jz      loc_180006CD7
0x180006bf2  test    r8, r8
0x180006bf5  jz      loc_180006CD7
0x180006bfb  mov     qword ptr [r11+10h], 0
0x180006c03  lea     rdx, [r11+10h]
0x180006c07  mov     rcx, rax
0x180006c0a  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostMergedConfigNavigator@@@Z; AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostMergedConfigNavigator * *)
0x180006c0f  mov     ebx, eax
0x180006c11  test    eax, eax
0x180006c13  jns     short loc_180006C26
0x180006c15  lea     rcx, [rsp+48h+arg_8]
0x180006c1a  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180006c1f  mov     eax, ebx
0x180006c21  jmp     loc_180006CDC
0x180006c26  mov     rbx, [rsp+48h+arg_8]
0x180006c2b  test    rbx, rbx
0x180006c2e  jnz     short loc_180006C48
0x180006c30  call    ?SetCannotComparePositionOfDifferentTypesException@AppHostNavigatorException@@SAJXZ; AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException(void)
0x180006c35  mov     ebx, eax
0x180006c37  lea     rcx, [rsp+48h+arg_8]
0x180006c3c  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180006c41  mov     eax, ebx
0x180006c43  jmp     loc_180006CDC
0x180006c48  mov     dword ptr [rdi], 0
0x180006c4e  mov     rax, [rbx+28h]
0x180006c52  mov     rcx, [rsi+28h]
0x180006c56  cmp     rcx, rax
0x180006c59  jz      short loc_180006CA0
0x180006c5b  mov     rax, [rax+88h]
0x180006c62  lea     r8, qword_1800181B0
0x180006c69  test    rax, rax
0x180006c6c  cmovnz  r8, rax; lpString2
0x180006c70  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x180006c78  or      edx, 0FFFFFFFFh; cchCount1
0x180006c7b  mov     r9d, edx; cchCount2
0x180006c7e  mov     rcx, [rcx+88h]; lpString1
0x180006c85  call    cs:__imp_CompareStringOrdinal
0x180006c8b  add     eax, 0FFFFFFFEh
0x180006c8e  mov     [rdi], eax
0x180006c90  jz      short loc_180006CA0
0x180006c92  lea     rcx, [rsp+48h+arg_8]
0x180006c97  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180006c9c  xor     eax, eax
0x180006c9e  jmp     short loc_180006CDC
0x180006ca0  mov     r8, [rbx+30h]; struct NavigationNodeBase *
0x180006ca4  mov     rcx, [rsi+30h]; struct NavigationNodeBase *
0x180006ca8  cmp     rcx, r8
0x180006cab  jz      short loc_180006CBB
0x180006cad  mov     r9d, [rbx+20h]; unsigned int
0x180006cb1  mov     edx, [rsi+20h]; unsigned int
0x180006cb4  call    ?ComparePositions@NavigationNodeBase@@SAJPEAV1@K0K@Z; NavigationNodeBase::ComparePositions(NavigationNodeBase *,ulong,NavigationNodeBase *,ulong)
0x180006cb9  mov     [rdi], eax
0x180006cbb  lea     rcx, [rsp+48h+arg_8]
0x180006cc0  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180006cc5  nop
0x180006cc6  xor     eax, eax
0x180006cc8  jmp     short loc_180006CDC
0x180006cca  mov     eax, [rsp+48h+var_18]
0x180006cce  jmp     short loc_180006CD5
0x180006cd0  mov     eax, 8000FFFFh
0x180006cd5  jmp     short loc_180006CDC
0x180006cd7  mov     eax, 80070057h
0x180006cdc  mov     rbx, [rsp+48h+arg_0]
0x180006ce1  mov     rsi, [rsp+48h+arg_10]
0x180006ce6  add     rsp, 40h
0x180006cea  pop     rdi
0x180006ceb  retn
```
