# Container::Manager::Image::_anonymous_namespace_::GetHivePath

- ea: `0x1800288cc`
- end: `0x180028af6`
- name: `Container::Manager::Image::_anonymous_namespace_::GetHivePath`
- size: `554`
- prototype: `__int64 __fastcall(__int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180029070`

## callees

- `0x180002534`
- `0x1800045e4`
- `0x180007b4c`
- `0x180009e10`
- `0x18000af30`
- `0x18000bb98`
- `0x1800288cc`

## string_xrefs

- `0x180028954`: `Windows\System32\Config`
- `0x180028a34`: `SECURITY`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::GetHivePath(__int64 *a1, int a2, __int64 a3)
{
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rdx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  unsigned int v11; // ebx
  const wchar_t *v13; // [rsp+20h] [rbp-30h]
  void *v14[2]; // [rsp+30h] [rbp-20h] BYREF
  _WORD v15[8]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v5 = a1[1] - *a1;
  v6 = *a1;
  v14[0] = v15;
  v14[1] = v15;
  v15[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v14,
                           v6,
                           v5 >> 1) )
  {
    v7 = 196;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v13);
    if ( v14[0] != v15 )
      operator delete(v14[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( a2 == 1 )
  {
    v13 = L"Users\\Default\\ntuser.dat";
    if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v14) )
    {
      v7 = 201;
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  v13 = L"Windows\\System32\\Config";
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v14) )
  {
    v7 = 205;
    goto LABEL_23;
  }
  v8 = a2 - 2;
  if ( !v8 )
  {
    v13 = L"SAM";
    if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v14) )
    {
      v7 = 211;
      goto LABEL_23;
    }
LABEL_26:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      a3,
      v14);
    if ( v14[0] != v15 )
      operator delete(v14[0], (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v13 = L"SECURITY";
    if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v14) )
    {
      v7 = 217;
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v13 = L"SOFTWARE";
    if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v14) )
    {
      v7 = 223;
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  if ( v10 == 1 )
  {
    v13 = L"SYSTEM";
    if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v14) )
    {
      v7 = 229;
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  v11 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xED,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)0x32,
          (unsigned int)L"Windows\\System32\\Config");
  if ( v14[0] != v15 )
    operator delete(v14[0], (const struct std::nothrow_t *)&std::nothrow);
  return v11;
}

```

## disassembly

```asm
0x1800288cc  mov     [rsp-8+arg_0], rbx
0x1800288d1  mov     [rsp-8+arg_8], rdi
0x1800288d6  push    rbp
0x1800288d7  mov     rbp, rsp
0x1800288da  sub     rsp, 50h
0x1800288de  mov     rdi, r8
0x1800288e1  lea     rax, [rbp+var_10]
0x1800288e5  mov     r8, [rcx+8]
0x1800288e9  mov     ebx, edx
0x1800288eb  sub     r8, [rcx]
0x1800288ee  mov     rdx, [rcx]
0x1800288f1  lea     rcx, [rbp+var_20]
0x1800288f5  mov     [rbp+var_20], rax
0x1800288f9  lea     rax, [rbp+var_10]
0x1800288fd  mov     [rbp+var_18], rax
0x180028901  xor     eax, eax
0x180028903  sar     r8, 1
0x180028906  mov     [rbp+var_10], ax
0x18002890a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18002890f  test    al, al
0x180028911  jnz     short loc_18002891D
0x180028913  mov     edx, 0C4h
0x180028918  jmp     loc_180028A88
0x18002891d  lea     rdx, [rbp+var_30]
0x180028921  lea     rcx, [rbp+var_20]; this
0x180028925  cmp     ebx, 1
0x180028928  jnz     short loc_180028954
0x18002892a  lea     rax, aUsersDefaultNt; "Users\\Default\\ntuser.dat"
0x180028931  mov     [rbp+var_28], 18h
0x180028939  mov     [rbp+var_30], rax
0x18002893d  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180028942  test    al, al
0x180028944  jnz     loc_180028ABE
0x18002894a  mov     edx, 0C9h
0x18002894f  jmp     loc_180028A88
0x180028954  lea     rax, aWindowsSystem3_0; "Windows\\System32\\Config"
0x18002895b  mov     [rbp+var_28], 17h
0x180028963  mov     [rbp+var_30], rax
0x180028967  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18002896c  test    al, al
0x18002896e  jnz     short loc_18002897A
0x180028970  mov     edx, 0CDh
0x180028975  jmp     loc_180028A88
0x18002897a  sub     ebx, 2
0x18002897d  jz      loc_180028A5F
0x180028983  sub     ebx, 1
0x180028986  jz      loc_180028A34
0x18002898c  sub     ebx, 1
0x18002898f  jz      short loc_180028A05
0x180028991  cmp     ebx, 1
0x180028994  jz      short loc_1800289D3
0x180028996  mov     rcx, [rbp+8]; this
0x18002899a  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1800289a1  mov     r9d, 32h ; '2'; char *
0x1800289a7  mov     edx, 0EDh; void *
0x1800289ac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800289b1  mov     rcx, [rbp+var_20]; void *
0x1800289b5  mov     ebx, eax
0x1800289b7  lea     rax, [rbp+var_10]
0x1800289bb  cmp     rcx, rax
0x1800289be  jz      short loc_1800289CC
0x1800289c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800289c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800289cc  mov     eax, ebx
0x1800289ce  jmp     loc_180028AE5
0x1800289d3  lea     rax, aSystem; "SYSTEM"
0x1800289da  mov     [rbp+var_28], 6
0x1800289e2  lea     rdx, [rbp+var_30]
0x1800289e6  mov     [rbp+var_30], rax
0x1800289ea  lea     rcx, [rbp+var_20]; this
0x1800289ee  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800289f3  test    al, al
0x1800289f5  jnz     loc_180028ABE
0x1800289fb  mov     edx, 0E5h
0x180028a00  jmp     loc_180028A88
0x180028a05  lea     rax, aSoftware; "SOFTWARE"
0x180028a0c  mov     [rbp+var_28], 8
0x180028a14  lea     rdx, [rbp+var_30]
0x180028a18  mov     [rbp+var_30], rax
0x180028a1c  lea     rcx, [rbp+var_20]; this
0x180028a20  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180028a25  test    al, al
0x180028a27  jnz     loc_180028ABE
0x180028a2d  mov     edx, 0DFh
0x180028a32  jmp     short loc_180028A88
0x180028a34  lea     rax, aSecurity; "SECURITY"
0x180028a3b  mov     [rbp+var_28], 8
0x180028a43  lea     rdx, [rbp+var_30]
0x180028a47  mov     [rbp+var_30], rax
0x180028a4b  lea     rcx, [rbp+var_20]; this
0x180028a4f  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180028a54  test    al, al
0x180028a56  jnz     short loc_180028ABE
0x180028a58  mov     edx, 0D9h
0x180028a5d  jmp     short loc_180028A88
0x180028a5f  lea     rax, aSam; "SAM"
0x180028a66  mov     [rbp+var_28], 3
0x180028a6e  lea     rdx, [rbp+var_30]
0x180028a72  mov     [rbp+var_30], rax
0x180028a76  lea     rcx, [rbp+var_20]; this
0x180028a7a  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180028a7f  test    al, al
0x180028a81  jnz     short loc_180028ABE
0x180028a83  mov     edx, 0D3h; void *
0x180028a88  mov     rcx, [rbp+8]; this
0x180028a8c  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028a93  mov     r9d, 8007000Eh; char *
0x180028a99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a9e  mov     rcx, [rbp+var_20]; void *
0x180028aa2  lea     rax, [rbp+var_10]
0x180028aa6  cmp     rcx, rax
0x180028aa9  jz      short loc_180028AB7
0x180028aab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028ab2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028ab7  mov     eax, 8007000Eh
0x180028abc  jmp     short loc_180028AE5
0x180028abe  lea     rdx, [rbp+var_20]
0x180028ac2  mov     rcx, rdi
0x180028ac5  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180028aca  mov     rcx, [rbp+var_20]; void *
0x180028ace  lea     rax, [rbp+var_10]
0x180028ad2  cmp     rcx, rax
0x180028ad5  jz      short loc_180028AE3
0x180028ad7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028ade  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028ae3  xor     eax, eax
0x180028ae5  mov     rbx, [rsp+50h+arg_0]
0x180028aea  mov     rdi, [rsp+50h+arg_8]
0x180028aef  add     rsp, 50h
0x180028af3  pop     rbp
0x180028af4  retn
```
