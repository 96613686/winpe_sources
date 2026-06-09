# AnimationHelpers::LoadThemeTransform(int,int,TA_TRANSFORM *,ulong,TA_TIMINGFUNCTION *,ulong)

- ea: `0x180005128`
- end: `0x18000528f`
- name: `?LoadThemeTransform@AnimationHelpers@@YAJHHPEAUTA_TRANSFORM@@KPEAUTA_TIMINGFUNCTION@@K@Z`
- size: `359`
- prototype: `int(AnimationHelpers *__hidden this, int, int, struct TA_TRANSFORM *, unsigned int, struct TA_TIMINGFUNCTION *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005298`

## callees

- `0x180005128`
- `0x1800386bc`
- `0x180040270`

## import_xrefs

- `UxTheme!GetThemeTimingFunction` at `0x180005210`
- `UxTheme!GetThemeTimingFunction` at `0x180005210`
- `UxTheme!CloseThemeData` at `0x18000523b`
- `UxTheme!CloseThemeData` at `0x18000526c`
- `UxTheme!CloseThemeData` at `0x18000527a`
- `UxTheme!CloseThemeData` at `0x18000523b`
- `UxTheme!CloseThemeData` at `0x18000526c`
- `UxTheme!CloseThemeData` at `0x18000527a`
- `UxTheme!OpenThemeData` at `0x18000514a`
- `UxTheme!OpenThemeData` at `0x180005161`
- `UxTheme!OpenThemeData` at `0x18000514a`
- `UxTheme!OpenThemeData` at `0x180005161`
- `UxTheme!GetThemeAnimationTransform` at `0x1800051ae`
- `UxTheme!GetThemeAnimationTransform` at `0x1800051ae`

## pseudocode

```c
__int64 __fastcall AnimationHelpers::LoadThemeTransform(
        AnimationHelpers *this,
        unsigned int a2,
        __int64 a3,
        struct TA_TRANSFORM *a4,
        __int64 a5,
        struct TA_TIMINGFUNCTION *a6)
{
  unsigned int v7; // r15d
  HTHEME v9; // rdi
  HTHEME v10; // rax
  void *v11; // rbx
  int ThemeAnimationTransform; // eax
  unsigned int v13; // esi
  int ThemeTimingFunction; // eax
  int v16; // [rsp+20h] [rbp-68h]
  HTHEME v17; // [rsp+40h] [rbp-48h] BYREF
  HTHEME v18[8]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7 = (unsigned int)this;
  v9 = OpenThemeData(0, L"Animations");
  v18[0] = v9;
  v10 = OpenThemeData(0, L"TimingFunction");
  v17 = v10;
  v11 = v10;
  if ( v9 && v10 )
  {
    LODWORD(a6) = 0;
    ThemeAnimationTransform = GetThemeAnimationTransform(v9, v7, a2);
    v13 = ThemeAnimationTransform;
    if ( ThemeAnimationTransform < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
        (const char *)(unsigned int)ThemeAnimationTransform,
        a3);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v18);
      return v13;
    }
    ThemeTimingFunction = GetThemeTimingFunction(v11, *(unsigned int *)(a3 + 4), a5, 20);
    v13 = ThemeTimingFunction;
    if ( ThemeTimingFunction < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
        (const char *)(unsigned int)ThemeTimingFunction,
        (int)&a6);
    CloseThemeData(v11);
LABEL_11:
    CloseThemeData(v9);
    return v13;
  }
  v13 = -2147467260;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15,
    (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
    (const char *)0x80004004LL,
    v16);
  if ( v11 )
    CloseThemeData(v11);
  if ( v9 )
    goto LABEL_11;
  return v13;
}

```

## disassembly

```asm
0x180005128  push    rbx
0x18000512a  push    rbp
0x18000512b  push    rsi
0x18000512c  push    rdi
0x18000512d  push    r14
0x18000512f  push    r15
0x180005131  sub     rsp, 58h
0x180005135  mov     r14d, edx
0x180005138  mov     r15d, ecx
0x18000513b  lea     rdx, pszClassList; "Animations"
0x180005142  xor     ecx, ecx; hwnd
0x180005144  mov     esi, r9d
0x180005147  mov     rbp, r8
0x18000514a  call    cs:__imp_OpenThemeData
0x180005150  lea     rdx, aTimingfunction; "TimingFunction"
0x180005157  xor     ecx, ecx; hwnd
0x180005159  mov     rdi, rax
0x18000515c  mov     [rsp+88h+var_40], rax
0x180005161  call    cs:__imp_OpenThemeData
0x180005167  mov     [rsp+88h+var_48], rax
0x18000516c  mov     rbx, rax
0x18000516f  test    rdi, rdi
0x180005172  jz      loc_180005243
0x180005178  test    rax, rax
0x18000517b  jz      loc_180005243
0x180005181  lea     rax, [rsp+88h+arg_28]
0x180005189  mov     dword ptr [rsp+88h+arg_28], 0
0x180005194  mov     [rsp+88h+var_58], rax
0x180005199  xor     r9d, r9d
0x18000519c  mov     [rsp+88h+var_60], esi
0x1800051a0  mov     r8d, r14d
0x1800051a3  mov     edx, r15d
0x1800051a6  mov     qword ptr [rsp+88h+var_68], rbp; int
0x1800051ab  mov     rcx, rdi
0x1800051ae  call    cs:__imp_GetThemeAnimationTransform
0x1800051b4  mov     esi, eax
0x1800051b6  test    eax, eax
0x1800051b8  jns     short loc_1800051EF
0x1800051ba  mov     rcx, [rsp+88h]; this
0x1800051c2  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x1800051c9  mov     r9d, eax; char *
0x1800051cc  mov     edx, 20h ; ' '; void *
0x1800051d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051d6  lea     rcx, [rsp+88h+var_48]
0x1800051db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?CloseThemeData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800051e0  lea     rcx, [rsp+88h+var_40]
0x1800051e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?CloseThemeData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800051ea  jmp     loc_180005280
0x1800051ef  mov     r8, [rsp+88h+arg_20]
0x1800051f7  lea     rax, [rsp+88h+arg_28]
0x1800051ff  mov     edx, [rbp+4]
0x180005202  mov     r9d, 14h
0x180005208  mov     rcx, rbx
0x18000520b  mov     qword ptr [rsp+88h+var_68], rax; int
0x180005210  call    cs:__imp_GetThemeTimingFunction
0x180005216  mov     esi, eax
0x180005218  test    eax, eax
0x18000521a  jns     short loc_180005238
0x18000521c  mov     rcx, [rsp+88h]; this
0x180005224  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x18000522b  mov     r9d, eax; char *
0x18000522e  mov     edx, 24h ; '$'; void *
0x180005233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005238  mov     rcx, rbx; hTheme
0x18000523b  call    cs:__imp_CloseThemeData
0x180005241  jmp     short loc_180005277
0x180005243  mov     rcx, [rsp+88h]; this
0x18000524b  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x180005252  mov     esi, 80004004h
0x180005257  mov     edx, 15h; void *
0x18000525c  mov     r9d, esi; char *
0x18000525f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005264  test    rbx, rbx
0x180005267  jz      short loc_180005272
0x180005269  mov     rcx, rbx; hTheme
0x18000526c  call    cs:__imp_CloseThemeData
0x180005272  test    rdi, rdi
0x180005275  jz      short loc_180005280
0x180005277  mov     rcx, rdi; hTheme
0x18000527a  call    cs:__imp_CloseThemeData
0x180005280  mov     eax, esi
0x180005282  add     rsp, 58h
0x180005286  pop     r15
0x180005288  pop     r14
0x18000528a  pop     rdi
0x18000528b  pop     rsi
0x18000528c  pop     rbp
0x18000528d  pop     rbx
0x18000528e  retn
```
