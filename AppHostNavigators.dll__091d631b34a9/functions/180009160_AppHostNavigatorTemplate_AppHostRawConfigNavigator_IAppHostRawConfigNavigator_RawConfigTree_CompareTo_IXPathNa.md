# AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::CompareTo(IXPathNavigator *,long *)

- ea: `0x180009160`
- end: `0x180009299`
- name: `?CompareTo@?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@UEAAJPEAUIXPathNavigator@@PEAJ@Z`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800039ec`
- `0x180009160`
- `0x180009650`
- `0x180009e3c`
- `0x18000fbe8`
- `0x180011064`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::CompareTo(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  int v5; // ebx
  __int64 result; // rax
  __int64 v7; // rbx
  unsigned int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // r15
  const WCHAR *v11; // r12
  const WCHAR *v12; // rdx
  struct NavigationNodeBase *v13; // r8
  struct NavigationNodeBase *v14; // rcx
  unsigned int v15; // [rsp+20h] [rbp-48h] BYREF
  __int64 v16; // [rsp+78h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  try
  {
    v16 = 0;
    v5 = AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::TryCastAsDerivedType(
           a2,
           &v16);
    if ( v5 < 0 )
    {
      InvasivePtr<AppHostConfigPathNavigator>::Reset(&v16);
      return (unsigned int)v5;
    }
    v7 = v16;
    if ( !v16 )
    {
      v8 = AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException();
      InvasivePtr<AppHostConfigPathNavigator>::Reset(&v16);
      return v8;
    }
    *a3 = 0;
    v9 = *(_QWORD *)(v7 + 40);
    v10 = *(_QWORD *)(a1 + 40);
    if ( v10 != v9 )
    {
      v11 = &qword_1800181B0;
      v12 = &qword_1800181B0;
      if ( *(_QWORD *)(v9 + 136) )
        v12 = *(const WCHAR **)(v9 + 136);
      if ( (unsigned int)WideCharStringTemplate<String>::CompareTo((const WCHAR **)(v10 + 136), v12) )
      {
        if ( *(_QWORD *)(v9 + 144) )
          v11 = *(const WCHAR **)(v9 + 144);
        if ( (unsigned int)WideCharStringTemplate<String>::CompareTo((const WCHAR **)(v10 + 144), v11) )
        {
          *a3 = 1;
          InvasivePtr<AppHostConfigPathNavigator>::Reset(&v16);
          return 0;
        }
      }
      *a3 = 0;
    }
    v13 = *(struct NavigationNodeBase **)(v7 + 48);
    v14 = *(struct NavigationNodeBase **)(a1 + 48);
    if ( v14 != v13 )
      *a3 = NavigationNodeBase::ComparePositions(v14, *(_DWORD *)(a1 + 32), v13, *(_DWORD *)(v7 + 32));
    InvasivePtr<AppHostConfigPathNavigator>::Reset(&v16);
    result = 0;
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
0x180009160  push    rbx
0x180009162  push    rsi
0x180009163  push    rdi
0x180009164  push    r12
0x180009166  push    r14
0x180009168  push    r15
0x18000916a  sub     rsp, 38h
0x18000916e  mov     rdi, r8
0x180009171  mov     rax, rdx
0x180009174  mov     rsi, rcx
0x180009177  test    rdx, rdx
0x18000917a  jz      loc_180009285
0x180009180  test    r8, r8
0x180009183  jz      loc_180009285
0x180009189  mov     [rsp+68h+arg_8], 0
0x180009192  lea     rdx, [rsp+68h+arg_8]
0x180009197  mov     rcx, rax
0x18000919a  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostRawConfigNavigator@@@Z; AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostRawConfigNavigator * *)
0x18000919f  mov     ebx, eax
0x1800091a1  test    eax, eax
0x1800091a3  jns     short loc_1800091B6
0x1800091a5  lea     rcx, [rsp+68h+arg_8]
0x1800091aa  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800091af  mov     eax, ebx
0x1800091b1  jmp     loc_18000928A
0x1800091b6  mov     rbx, [rsp+68h+arg_8]
0x1800091bb  test    rbx, rbx
0x1800091be  jnz     short loc_1800091D8
0x1800091c0  call    ?SetCannotComparePositionOfDifferentTypesException@AppHostNavigatorException@@SAJXZ; AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException(void)
0x1800091c5  mov     ebx, eax
0x1800091c7  lea     rcx, [rsp+68h+arg_8]
0x1800091cc  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x1800091d1  mov     eax, ebx
0x1800091d3  jmp     loc_18000928A
0x1800091d8  mov     dword ptr [rdi], 0
0x1800091de  mov     r14, [rbx+28h]
0x1800091e2  mov     r15, [rsi+28h]
0x1800091e6  cmp     r15, r14
0x1800091e9  jz      short loc_18000924E
0x1800091eb  mov     rax, [r14+88h]
0x1800091f2  lea     r12, qword_1800181B0
0x1800091f9  mov     rdx, r12
0x1800091fc  test    rax, rax
0x1800091ff  cmovnz  rdx, rax
0x180009203  lea     rcx, [r15+88h]
0x18000920a  call    ?CompareTo@?$WideCharStringTemplate@VString@@@@QEBAJPEBG_N@Z; WideCharStringTemplate<String>::CompareTo(ushort const *,bool)
0x18000920f  test    eax, eax
0x180009211  jz      short loc_180009248
0x180009213  mov     rax, [r14+90h]
0x18000921a  test    rax, rax
0x18000921d  cmovnz  r12, rax
0x180009221  lea     rcx, [r15+90h]
0x180009228  mov     rdx, r12
0x18000922b  call    ?CompareTo@?$WideCharStringTemplate@VString@@@@QEBAJPEBG_N@Z; WideCharStringTemplate<String>::CompareTo(ushort const *,bool)
0x180009230  test    eax, eax
0x180009232  jz      short loc_180009248
0x180009234  mov     dword ptr [rdi], 1
0x18000923a  lea     rcx, [rsp+68h+arg_8]
0x18000923f  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180009244  xor     eax, eax
0x180009246  jmp     short loc_18000928A
0x180009248  mov     dword ptr [rdi], 0
0x18000924e  mov     r8, [rbx+30h]; struct NavigationNodeBase *
0x180009252  mov     rcx, [rsi+30h]; struct NavigationNodeBase *
0x180009256  cmp     rcx, r8
0x180009259  jz      short loc_180009269
0x18000925b  mov     r9d, [rbx+20h]; unsigned int
0x18000925f  mov     edx, [rsi+20h]; unsigned int
0x180009262  call    ?ComparePositions@NavigationNodeBase@@SAJPEAV1@K0K@Z; NavigationNodeBase::ComparePositions(NavigationNodeBase *,ulong,NavigationNodeBase *,ulong)
0x180009267  mov     [rdi], eax
0x180009269  lea     rcx, [rsp+68h+arg_8]
0x18000926e  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x180009273  nop
0x180009274  xor     eax, eax
0x180009276  jmp     short loc_18000928A
0x180009278  mov     eax, [rsp+68h+var_48]
0x18000927c  jmp     short loc_180009283
0x18000927e  mov     eax, 8000FFFFh
0x180009283  jmp     short loc_18000928A
0x180009285  mov     eax, 80070057h
0x18000928a  add     rsp, 38h
0x18000928e  pop     r15
0x180009290  pop     r14
0x180009292  pop     r12
0x180009294  pop     rdi
0x180009295  pop     rsi
0x180009296  pop     rbx
0x180009297  retn
```
