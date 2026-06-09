# AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::CompareTo(IXPathNavigator *,long *)

- ea: `0x180004980`
- end: `0x180004a45`
- name: `?CompareTo@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@UEAAJPEAUIXPathNavigator@@PEAJ@Z`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800039ec`
- `0x180004980`
- `0x180005920`
- `0x18000fbe8`
- `0x180011064`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::CompareTo(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        _DWORD *a3)
{
  HINSTANCE v5; // rcx
  int v6; // edi
  __int64 result; // rax
  __int64 v8; // r9
  unsigned int v9; // ebx
  struct NavigationNodeBase *v10; // r8
  struct NavigationNodeBase *v11; // rcx
  unsigned int v12; // [rsp+20h] [rbp-18h] BYREF
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  try
  {
    v13 = 0;
    v6 = AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastAsDerivedType(
           a2,
           &v13);
    if ( v6 >= 0 )
    {
      v8 = v13;
      if ( v13 )
      {
        *a3 = 0;
        v10 = *(struct NavigationNodeBase **)(v8 + 48);
        v11 = *(struct NavigationNodeBase **)(a1 + 48);
        if ( v11 != v10 )
          *a3 = NavigationNodeBase::ComparePositions(v11, *(_DWORD *)(a1 + 32), v10, *(_DWORD *)(v8 + 32));
        InvasivePtr<AppHostConfigPathNavigator>::Reset(&v13);
        result = 0;
      }
      else
      {
        v9 = AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException(v5);
        InvasivePtr<AppHostConfigPathNavigator>::Reset(&v13);
        result = v9;
      }
    }
    else
    {
      InvasivePtr<AppHostConfigPathNavigator>::Reset(&v13);
      result = (unsigned int)v6;
    }
  }
  catch ( long v12 )
  {
    return v12;
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
0x180004980  mov     r11, rsp
0x180004983  mov     [r11+8], rbx
0x180004987  mov     [r11+18h], rsi
0x18000498b  push    rdi
0x18000498c  sub     rsp, 30h
0x180004990  mov     rbx, r8
0x180004993  mov     rax, rdx
0x180004996  mov     rsi, rcx
0x180004999  test    rdx, rdx
0x18000499c  jz      loc_180004A2F
0x1800049a2  test    rbx, rbx
0x1800049a5  jz      loc_180004A2F
0x1800049ab  mov     qword ptr [r11+10h], 0
0x1800049b3  lea     rdx, [r11+10h]
0x1800049b7  mov     rcx, rax
0x1800049ba  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostConfigPathNavigator * *)
0x1800049bf  mov     edi, eax
0x1800049c1  test    eax, eax
0x1800049c3  jns     short loc_1800049D3
0x1800049c5  lea     rcx, [rsp+38h+arg_8]
0x1800049ca  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800049cf  mov     eax, edi
0x1800049d1  jmp     short loc_180004A34
0x1800049d3  mov     r9, [rsp+38h+arg_8]
0x1800049d8  test    r9, r9
0x1800049db  jnz     short loc_1800049F2
0x1800049dd  call    ?SetCannotComparePositionOfDifferentTypesException@AppHostNavigatorException@@SAJXZ; AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException(void)
0x1800049e2  mov     ebx, eax
0x1800049e4  lea     rcx, [rsp+38h+arg_8]
0x1800049e9  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800049ee  mov     eax, ebx
0x1800049f0  jmp     short loc_180004A34
0x1800049f2  mov     dword ptr [rbx], 0
0x1800049f8  mov     r8, [r9+30h]; struct NavigationNodeBase *
0x1800049fc  mov     rcx, [rsi+30h]; struct NavigationNodeBase *
0x180004a00  cmp     rcx, r8
0x180004a03  jz      short loc_180004A13
0x180004a05  mov     r9d, [r9+20h]; unsigned int
0x180004a09  mov     edx, [rsi+20h]; unsigned int
0x180004a0c  call    ?ComparePositions@NavigationNodeBase@@SAJPEAV1@K0K@Z; NavigationNodeBase::ComparePositions(NavigationNodeBase *,ulong,NavigationNodeBase *,ulong)
0x180004a11  mov     [rbx], eax
0x180004a13  lea     rcx, [rsp+38h+arg_8]
0x180004a18  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180004a1d  nop
0x180004a1e  xor     eax, eax
0x180004a20  jmp     short loc_180004A34
0x180004a22  mov     eax, [rsp+38h+var_18]
0x180004a26  jmp     short loc_180004A2D
0x180004a28  mov     eax, 8000FFFFh
0x180004a2d  jmp     short loc_180004A34
0x180004a2f  mov     eax, 80070057h
0x180004a34  mov     rbx, [rsp+38h+arg_0]
0x180004a39  mov     rsi, [rsp+38h+arg_10]
0x180004a3e  add     rsp, 30h
0x180004a42  pop     rdi
0x180004a43  retn
```
