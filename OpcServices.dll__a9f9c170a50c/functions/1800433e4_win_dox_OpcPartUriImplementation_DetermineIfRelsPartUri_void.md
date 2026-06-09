# win_dox::OpcPartUriImplementation::DetermineIfRelsPartUri(void)

- ea: `0x1800433e4`
- end: `0x180043661`
- name: `?DetermineIfRelsPartUri@OpcPartUriImplementation@win_dox@@AEAAXXZ`
- size: `637`
- prototype: `void __fastcall(win_dox::OpcPartUriImplementation *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180043308`
- `0x180043364`

## callees

- `0x18000d4d8`
- `0x1800198bc`
- `0x18001aaa0`
- `0x1800425d8`
- `0x1800433e4`
- `0x180043668`
- `0x180043820`
- `0x1800517a0`
- `0x18005c630`
- `0x180079ca0`
- `0x180080258`
- `0x1800cce54`
- `0x1800cd38c`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180043498`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180043498`

## string_xrefs

- `0x18004356a`: `::CompareString returned invalid return value`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall win_dox::OpcPartUriImplementation::DetermineIfRelsPartUri(win_dox::OpcPartUriImplementation *this)
{
  __int64 v2; // rbx
  const WCHAR *p_lpString1; // rcx
  bool v4; // di
  int v5; // eax
  win_musl::detail *v6; // rcx
  int v7; // eax
  const struct win_dox::OpcPartUri *PackageRelationshipUri; // rax
  int v9; // ebx
  const wchar_t *v10; // rcx
  unsigned int LastErrorAsFailHR; // [rsp+28h] [rbp-D8h]
  __int64 v12; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[8]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v15; // [rsp+68h] [rbp-98h] BYREF
  __int64 v16; // [rsp+78h] [rbp-88h]
  unsigned __int64 v17; // [rsp+80h] [rbp-80h]
  _BYTE v18[8]; // [rsp+88h] [rbp-78h] BYREF
  LPCWCH lpString1; // [rsp+90h] [rbp-70h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v21; // [rsp+A8h] [rbp-58h]
  _BYTE v22[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *Block; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v24; // [rsp+D0h] [rbp-30h]
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-20h] BYREF

  v13[1] = -2;
  v12 = 0;
  v2 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 8LL))(*(_QWORD *)this);
  v12 = v2;
  v13[2] = &v12;
  win_dox::to_interface<IByteReceiver>::resolve(v13, &v12);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  win_dox::Uri::GetExtension(v13, v18);
  if ( !v20 )
    goto LABEL_9;
  p_lpString1 = (const WCHAR *)&lpString1;
  if ( v21 >= 8 )
    p_lpString1 = lpString1;
  v4 = 1;
  v5 = CompareStringOrdinal(p_lpString1, -1, L".rels", -1, 1) - 1;
  if ( !v5 )
    goto LABEL_9;
  v7 = v5 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
    {
      LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v6);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x5B4u,
        LastErrorAsFailHR,
        (struct win_musl::TStringEllipseBase *)L"::CompareString returned invalid return value");
      throw (SplException::THResultException *)pExceptionObject;
    }
LABEL_9:
    v4 = 0;
    goto LABEL_10;
  }
  PackageRelationshipUri = (const struct win_dox::OpcPartUri *)GetPackageRelationshipUri(v14);
  v9 = win_dox::OpcPartUriImplementation::ComparePartUri(this, PackageRelationshipUri);
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v14);
  if ( v9 )
  {
    win_dox::Uri::GetPath(v13, v22);
    FindLastSegment(v14, v22);
    if ( v16 )
    {
      v10 = (const wchar_t *)&v15;
      if ( v17 >= 8 )
        v10 = v15;
      v4 = Compare(v10, L"_rels") == 0;
    }
    if ( v17 >= 8 )
      operator delete(v15);
    v17 = 7;
    v16 = 0;
    LOWORD(v15) = 0;
    if ( v24 >= 8 )
      operator delete(Block);
  }
LABEL_10:
  *((_DWORD *)this + 14) = v4;
  if ( v21 >= 8 )
    operator delete((void *)lpString1);
  v21 = 7;
  v20 = 0;
  LOWORD(lpString1) = 0;
  if ( v13[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
}

```

## disassembly

```asm
0x1800433e4  push    rbp
0x1800433e6  push    rbx
0x1800433e7  push    rsi
0x1800433e8  push    rdi
0x1800433e9  lea     rbp, [rsp-98h]
0x1800433f1  sub     rsp, 198h
0x1800433f8  mov     [rsp+1B0h+var_160], 0FFFFFFFFFFFFFFFEh
0x180043401  mov     rax, cs:__security_cookie
0x180043408  xor     rax, rsp
0x18004340b  mov     [rbp+0B0h+var_30], rax
0x180043412  mov     rsi, rcx
0x180043415  xor     ecx, ecx
0x180043417  mov     [rsp+1B0h+var_170], rcx
0x18004341c  mov     rbx, [rsi]
0x18004341f  test    rbx, rbx
0x180043422  jnz     loc_180043521
0x180043428  mov     [rsp+1B0h+var_170], rbx
0x18004342d  test    rcx, rcx
0x180043430  jnz     loc_18004353A
0x180043436  lea     rax, [rsp+1B0h+var_170]
0x18004343b  mov     [rsp+1B0h+var_158], rax
0x180043440  lea     rdx, [rsp+1B0h+var_170]
0x180043445  lea     rcx, [rsp+1B0h+var_168]
0x18004344a  call    ?resolve@?$to_interface@UIByteReceiver@@@win_dox@@SA?AV?$scope@PEAUIByteReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBV34@@Z; win_dox::to_interface<IByteReceiver>::resolve(win_scope::scope<IByteReceiver *,win_scope::const_policies<win_scope::com_policies>> const &)
0x18004344f  nop
0x180043450  mov     rcx, [rsp+1B0h+var_170]
0x180043455  test    rcx, rcx
0x180043458  jnz     loc_180043507
0x18004345e  lea     rdx, [rbp+0B0h+var_128]
0x180043462  lea     rcx, [rsp+1B0h+var_168]
0x180043467  call    ?GetExtension@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetExtension(void)
0x18004346c  nop
0x18004346d  cmp     [rbp+0B0h+var_110], 0
0x180043472  jz      short loc_1800434A6
0x180043474  lea     rcx, [rbp+0B0h+lpString1]
0x180043478  cmp     [rbp+0B0h+var_108], 8
0x18004347d  cmovnb  rcx, [rbp+0B0h+lpString1]; lpString1
0x180043482  mov     edi, 1
0x180043487  mov     [rsp+1B0h+bIgnoreCase], edi; bIgnoreCase
0x18004348b  or      edx, 0FFFFFFFFh; cchCount1
0x18004348e  mov     r9d, edx; cchCount2
0x180043491  lea     r8, ?g_relationshipsExtension@win_musl@@3QB_WB; ".rels"
0x180043498  call    cs:__imp_CompareStringOrdinal
0x18004349e  sub     eax, edi
0x1800434a0  jnz     loc_180043559
0x1800434a6  xor     dil, dil
0x1800434a9  xor     eax, eax
0x1800434ab  test    dil, dil
0x1800434ae  setnz   al
0x1800434b1  mov     [rsi+38h], eax
0x1800434b4  cmp     [rbp+0B0h+var_108], 8
0x1800434b9  jnb     loc_18004354B
0x1800434bf  mov     [rbp+0B0h+var_108], 7
0x1800434c7  mov     [rbp+0B0h+var_110], 0
0x1800434cf  xor     eax, eax
0x1800434d1  mov     word ptr [rbp+0B0h+lpString1], ax
0x1800434d5  mov     rcx, [rsp+1B0h+var_168]
0x1800434da  test    rcx, rcx
0x1800434dd  jz      short loc_1800434EC
0x1800434df  mov     rax, [rcx]
0x1800434e2  mov     rax, [rax+10h]
0x1800434e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434eb  nop
0x1800434ec  mov     rcx, [rbp+0B0h+var_30]
0x1800434f3  xor     rcx, rsp; StackCookie
0x1800434f6  call    __security_check_cookie
0x1800434fb  add     rsp, 198h
0x180043502  pop     rdi
0x180043503  pop     rsi
0x180043504  pop     rbx
0x180043505  pop     rbp
0x180043506  retn
0x180043507  mov     rax, [rcx]
0x18004350a  mov     rax, [rax+10h]
0x18004350e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043513  mov     [rsp+1B0h+var_170], 0
0x18004351c  jmp     loc_18004345E
0x180043521  mov     rax, [rbx]
0x180043524  mov     rcx, rbx
0x180043527  mov     rax, [rax+8]
0x18004352b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043530  mov     rcx, [rsp+1B0h+var_170]
0x180043535  jmp     loc_180043428
0x18004353a  mov     rax, [rcx]
0x18004353d  mov     rax, [rax+10h]
0x180043541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043546  jmp     loc_180043436
0x18004354b  mov     rcx, [rbp+0B0h+lpString1]; Block
0x18004354f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180043554  jmp     loc_1800434BF
0x180043559  sub     eax, edi
0x18004355b  jz      short loc_1800435AA
0x18004355d  cmp     eax, edi
0x18004355f  jz      loc_1800434A6
0x180043565  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18004356a  lea     rcx, aComparestringR; "::CompareString returned invalid return"...
0x180043571  mov     [rsp+1B0h+var_180], rcx; struct win_musl::TStringEllipseBase *
0x180043576  mov     [rsp+1B0h+var_188], eax; unsigned int
0x18004357a  mov     [rsp+1B0h+bIgnoreCase], 5B4h; unsigned int
0x180043582  lea     r9, word_18013A0B6
0x180043589  lea     r8, aNoFilename; "(no filename)"
0x180043590  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x180043594  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180043599  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800435a0  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1800435a4  call    _CxxThrowException_0
0x1800435aa  lea     rcx, [rsp+1B0h+var_150]
0x1800435af  call    ?GetPackageRelationshipUri@@YA?AVOpcPartUri@win_dox@@XZ; GetPackageRelationshipUri(void)
0x1800435b4  nop
0x1800435b5  mov     rdx, rax; struct win_dox::OpcPartUri *
0x1800435b8  mov     rcx, rsi; this
0x1800435bb  call    ?ComparePartUri@OpcPartUriImplementation@win_dox@@QEBAHAEBVOpcPartUri@2@@Z; win_dox::OpcPartUriImplementation::ComparePartUri(win_dox::OpcPartUri const &)
0x1800435c0  mov     ebx, eax
0x1800435c2  lea     rcx, [rsp+1B0h+var_150]; this
0x1800435c7  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x1800435cc  test    ebx, ebx
0x1800435ce  jz      loc_1800434A9
0x1800435d4  lea     rdx, [rbp+0B0h+var_100]
0x1800435d8  lea     rcx, [rsp+1B0h+var_168]
0x1800435dd  call    ?GetPath@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetPath(void)
0x1800435e2  nop
0x1800435e3  lea     rdx, [rbp+0B0h+var_100]
0x1800435e7  lea     rcx, [rsp+1B0h+var_150]
0x1800435ec  call    ?FindLastSegment@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV12@@Z; FindLastSegment(std::wstring const &)
0x1800435f1  nop
0x1800435f2  cmp     [rsp+1B0h+var_138], 0
0x1800435f8  jz      short loc_18004361C
0x1800435fa  lea     rcx, [rsp+1B0h+var_148]
0x1800435ff  cmp     [rbp+0B0h+var_130], 8
0x180043604  cmovnb  rcx, [rsp+1B0h+var_148]; wchar_t *
0x18004360a  lea     rdx, ?g_relationshipsSegment@win_musl@@3QB_WB; "_rels"
0x180043611  call    ?Compare@@YAHPEB_W0@Z; Compare(wchar_t const *,wchar_t const *)
0x180043616  test    eax, eax
0x180043618  setz    dil
0x18004361c  cmp     [rbp+0B0h+var_130], 8
0x180043621  jnb     short loc_180043654
0x180043623  mov     [rbp+0B0h+var_130], 7
0x18004362b  mov     [rsp+1B0h+var_138], 0
0x180043634  xor     eax, eax
0x180043636  mov     word ptr [rsp+1B0h+var_148], ax
0x18004363b  cmp     [rbp+0B0h+var_E0], 8
0x180043640  jb      loc_1800434A9
0x180043646  mov     rcx, [rbp+0B0h+Block]; Block
0x18004364a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004364f  jmp     loc_1800434A9
0x180043654  mov     rcx, [rsp+1B0h+var_148]; Block
0x180043659  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004365e  jmp     short loc_180043623
```
