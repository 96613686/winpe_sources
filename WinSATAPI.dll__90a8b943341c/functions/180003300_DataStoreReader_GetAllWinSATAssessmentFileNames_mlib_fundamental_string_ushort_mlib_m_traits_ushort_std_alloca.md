# DataStoreReader::GetAllWinSATAssessmentFileNames(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>> &,DataStoreID,AssessmentTimeTaken)

- ea: `0x180003300`
- end: `0x1800035c6`
- name: `?GetAllWinSATAssessmentFileNames@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@W4DataStoreID@@W4AssessmentTimeTaken@@@Z`
- size: `710`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180001980`
- `0x18001f530`

## callees

- `0x180003300`
- `0x180004048`
- `0x1800043f0`
- `0x180004990`
- `0x180008490`
- `0x18000d07c`
- `0x180011e70`
- `0x180011ee0`
- `0x180011fc0`
- `0x180012bf3`
- `0x18002c3e4`
- `0x18002fb50`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003544`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003553`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003544`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003553`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000343b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800034e0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003509`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000343b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800034e0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003509`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003401`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003449`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003401`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000342a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000342a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003519`
- `KERNEL32!GetCurrentDirectoryW` at `0x18000341a`
- `KERNEL32!GetCurrentDirectoryW` at `0x18000341a`

## string_xrefs

- `0x18000338d`: `.WinSAT.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DataStoreReader::GetAllWinSATAssessmentFileNames(__int64 a1, _QWORD *a2)
{
  void *v4; // rax
  __int64 v5; // rcx
  const wchar_t *i; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rsi
  WCHAR *v9; // rdx
  WCHAR *v10; // rdi
  WCHAR *v11; // rax
  DWORD LastError; // esi
  signed int v13; // eax
  unsigned int v14; // edi
  void *v16; // rcx
  char pExceptionObject; // [rsp+30h] [rbp-2B8h] BYREF
  _QWORD v19[3]; // [rsp+38h] [rbp-2B0h] BYREF
  void **v20; // [rsp+50h] [rbp-298h] BYREF
  __int16 v21; // [rsp+58h] [rbp-290h]
  __int64 v22; // [rsp+260h] [rbp-88h]
  __int64 v23; // [rsp+268h] [rbp-80h]
  __int64 v24; // [rsp+270h] [rbp-78h]
  __int64 v25; // [rsp+278h] [rbp-70h]
  __int64 v26; // [rsp+280h] [rbp-68h]
  void **v27; // [rsp+288h] [rbp-60h]
  __int128 v28; // [rsp+290h] [rbp-58h]
  __int128 v29; // [rsp+2A0h] [rbp-48h]
  _QWORD *v30; // [rsp+2B0h] [rbp-38h]

  v19[1] = -2;
  v4 = operator new(0x28u);
  if ( !v4 )
    std::_Xbad_alloc();
  v19[0] = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             v4,
             260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
    v19,
    L"*%s.Assessment (%s)",
    L"Formal",
    L"*");
  v5 = 0x10000;
  for ( i = L".WinSAT.xml"; ; ++i )
  {
    if ( !v5 )
      throw (mlib::CStringTooBig *)&pExceptionObject;
    if ( !*i )
      break;
    --v5;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::munge(
    v19,
    0,
    *(_QWORD *)v19[0],
    L".WinSAT.xml",
    i - L".WinSAT.xml");
  v7 = (_QWORD *)v19[0];
  v8 = *(_QWORD *)(v19[0] + 24LL);
  v9 = *(WCHAR **)(*(_QWORD *)a1 + 24LL);
  v10 = 0;
  if ( !v9 || !*v9 )
  {
    v11 = (WCHAR *)operator new[](0x208u);
    v10 = v11;
    if ( !v11 )
    {
      SetLastError(8u);
      goto LABEL_18;
    }
    if ( !GetCurrentDirectoryW(0x104u, v11) )
    {
      LastError = GetLastError();
      operator delete[](v10);
      SetLastError(LastError);
      goto LABEL_17;
    }
    v9 = v10;
  }
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = -1;
  v26 = 0;
  v27 = &mlib::FSpecList<unsigned short>::`vftable';
  v28 = 0;
  v29 = 0;
  v21 = 0;
  v20 = &mlib::FileFinder<unsigned short>::`vftable';
  v30 = a2;
  LastError = mlib::TraverseDirT<unsigned short>::traverse_dir(&v20, v9, v8);
  if ( v10 )
    operator delete[](v10);
  v20 = &mlib::TraverseDirT<unsigned short>::`vftable';
  v27 = &mlib::FSpecList<unsigned short>::`vftable';
  operator delete[](*((void **)&v29 + 1));
LABEL_17:
  if ( !LastError )
  {
    std::_Sort<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> *,__int64,bool (*)(mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const &,mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const &)>(
      *a2,
      a2[1],
      (__int64)(a2[1] - *a2) >> 3);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v19);
    return 0;
  }
LABEL_18:
  v13 = GetLastError();
  v14 = v13;
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  if ( v7[2]-- == 1 )
  {
    v16 = (void *)v7[3];
    if ( v16 )
      operator delete(v16);
    operator delete(v7);
  }
  return v14;
}

```

## disassembly

```asm
0x180003300  mov     rax, rsp
0x180003303  push    rdi
0x180003304  push    r14
0x180003306  push    r15
0x180003308  sub     rsp, 2D0h
0x18000330f  mov     [rsp+2E8h+var_2A8], 0FFFFFFFFFFFFFFFEh
0x180003318  mov     [rax+10h], rbx
0x18000331c  mov     [rax+18h], rbp
0x180003320  mov     [rax+20h], rsi
0x180003324  mov     rax, cs:__security_cookie
0x18000332b  xor     rax, rsp
0x18000332e  mov     [rsp+2E8h+var_28], rax
0x180003336  mov     r14, rdx
0x180003339  mov     rdi, rcx
0x18000333c  mov     ecx, 28h ; '('; Size
0x180003341  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003346  test    rax, rax
0x180003349  jnz     short loc_180003351
0x18000334b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180003351  mov     [rsp+2E8h+var_2B0], rax
0x180003356  mov     edx, 104h
0x18000335b  mov     rcx, rax
0x18000335e  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x180003363  nop
0x180003364  mov     [rsp+2E8h+var_2B0], rax
0x180003369  lea     r9, asc_180037888; "*"
0x180003370  lea     r8, aFormal; "Formal"
0x180003377  lea     rdx, aSAssessmentS; "*%s.Assessment (%s)"
0x18000337e  lea     rcx, [rsp+2E8h+var_2B0]
0x180003383  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x180003388  mov     ecx, 10000h
0x18000338d  lea     r9, aWinsatXml; ".WinSAT.xml"
0x180003394  mov     rax, r9
0x180003397  test    rcx, rcx
0x18000339a  jz      loc_1800035B4
0x1800033a0  cmp     word ptr [rax], 0
0x1800033a4  jz      short loc_1800033AF
0x1800033a6  add     rax, 2
0x1800033aa  dec     rcx
0x1800033ad  jmp     short loc_180003397
0x1800033af  sub     rax, r9
0x1800033b2  sar     rax, 1
0x1800033b5  mov     rcx, [rsp+2E8h+var_2B0]
0x1800033ba  mov     [rsp+2E8h+var_2C8], rax
0x1800033bf  mov     r8, [rcx]
0x1800033c2  xor     edx, edx
0x1800033c4  lea     rcx, [rsp+2E8h+var_2B0]
0x1800033c9  call    ?munge@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAX_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::munge(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x1800033ce  mov     rbx, [rsp+2E8h+var_2B0]
0x1800033d3  mov     rsi, [rbx+18h]
0x1800033d7  mov     rax, [rdi]
0x1800033da  mov     rdx, [rax+18h]
0x1800033de  xor     ebp, ebp
0x1800033e0  mov     edi, ebp
0x1800033e2  test    rdx, rdx
0x1800033e5  jz      short loc_1800033EC
0x1800033e7  cmp     [rdx], di
0x1800033ea  jnz     short loc_18000345D
0x1800033ec  mov     ecx, 208h; unsigned __int64
0x1800033f1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800033f6  mov     rdi, rax
0x1800033f9  test    rax, rax
0x1800033fc  jnz     short loc_180003412
0x1800033fe  lea     ecx, [rax+8]; dwErrCode
0x180003401  call    cs:__imp_SetLastError
0x180003408  nop     dword ptr [rax+rax+00h]
0x18000340d  jmp     loc_180003519
0x180003412  mov     rdx, rdi; lpBuffer
0x180003415  mov     ecx, 104h; nBufferLength
0x18000341a  call    cs:__imp_GetCurrentDirectoryW
0x180003421  nop     dword ptr [rax+rax+00h]
0x180003426  test    eax, eax
0x180003428  jnz     short loc_18000345A
0x18000342a  call    cs:__imp_GetLastError
0x180003431  nop     dword ptr [rax+rax+00h]
0x180003436  mov     esi, eax
0x180003438  mov     rcx, rdi
0x18000343b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003442  nop     dword ptr [rax+rax+00h]
0x180003447  mov     ecx, esi; dwErrCode
0x180003449  call    cs:__imp_SetLastError
0x180003450  nop     dword ptr [rax+rax+00h]
0x180003455  jmp     loc_180003515
0x18000345a  mov     rdx, rdi
0x18000345d  mov     [rsp+2E8h+var_88], rbp
0x180003465  mov     [rsp+2E8h+var_80], rbp
0x18000346d  mov     [rsp+2E8h+var_78], rbp
0x180003475  mov     [rsp+2E8h+var_70], 0FFFFFFFFFFFFFFFFh
0x180003481  mov     [rsp+2E8h+var_68], rbp
0x180003489  lea     r15, ??_7?$FSpecList@G@mlib@@6B@; const mlib::FSpecList<ushort>::`vftable'
0x180003490  mov     [rsp+2E8h+var_60], r15
0x180003498  xorps   xmm0, xmm0
0x18000349b  movdqa  [rsp+2E8h+var_58], xmm0
0x1800034a4  xorps   xmm1, xmm1
0x1800034a7  movdqa  [rsp+2E8h+var_48], xmm1
0x1800034b0  mov     [rsp+2E8h+var_290], bp
0x1800034b5  lea     rax, ??_7?$FileFinder@G@mlib@@6B@; const mlib::FileFinder<ushort>::`vftable'
0x1800034bc  mov     [rsp+2E8h+var_298], rax
0x1800034c1  mov     [rsp+2E8h+var_38], r14
0x1800034c9  mov     r8, rsi
0x1800034cc  lea     rcx, [rsp+2E8h+var_298]
0x1800034d1  call    ?traverse_dir@?$TraverseDirT@G@mlib@@QEAAKPEBG0_K_N@Z; mlib::TraverseDirT<ushort>::traverse_dir(ushort const *,ushort const *,unsigned __int64,bool)
0x1800034d6  mov     esi, eax
0x1800034d8  test    rdi, rdi
0x1800034db  jz      short loc_1800034ED
0x1800034dd  mov     rcx, rdi
0x1800034e0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800034e7  nop     dword ptr [rax+rax+00h]
0x1800034ec  nop
0x1800034ed  lea     rax, ??_7?$TraverseDirT@G@mlib@@6B@; const mlib::TraverseDirT<ushort>::`vftable'
0x1800034f4  mov     [rsp+2E8h+var_298], rax
0x1800034f9  mov     [rsp+2E8h+var_60], r15
0x180003501  mov     rcx, qword ptr [rsp+2E8h+var_48+8]
0x180003509  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003510  nop     dword ptr [rax+rax+00h]
0x180003515  test    esi, esi
0x180003517  jz      short loc_18000358F
0x180003519  call    cs:__imp_GetLastError
0x180003520  nop     dword ptr [rax+rax+00h]
0x180003525  mov     edi, eax
0x180003527  test    eax, eax
0x180003529  jle     short loc_180003534
0x18000352b  movzx   edi, ax
0x18000352e  or      edi, 80070000h
0x180003534  sub     qword ptr [rbx+10h], 1
0x180003539  jnz     short loc_18000355F
0x18000353b  mov     rcx, [rbx+18h]
0x18000353f  test    rcx, rcx
0x180003542  jz      short loc_180003550
0x180003544  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000354b  nop     dword ptr [rax+rax+00h]
0x180003550  mov     rcx, rbx
0x180003553  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000355a  nop     dword ptr [rax+rax+00h]
0x18000355f  mov     eax, edi
0x180003561  mov     rcx, [rsp+2E8h+var_28]
0x180003569  xor     rcx, rsp; StackCookie
0x18000356c  call    __security_check_cookie
0x180003571  lea     r11, [rsp+2E8h+var_18]
0x180003579  mov     rbx, [r11+28h]
0x18000357d  mov     rbp, [r11+30h]
0x180003581  mov     rsi, [r11+38h]
0x180003585  mov     rsp, r11
0x180003588  pop     r15
0x18000358a  pop     r14
0x18000358c  pop     rdi
0x18000358d  retn
0x18000358f  mov     rcx, [r14]
0x180003592  mov     rdx, [r14+8]
0x180003596  mov     r8, rdx
0x180003599  sub     r8, rcx
0x18000359c  sar     r8, 3
0x1800035a0  call    ??$_Sort@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@_JP6A_NAEBV12@0@Z@std@@YAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0_JP6A_NAEBV12@2@Z@Z; std::_Sort<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,__int64,bool (*)(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,__int64,bool (*)(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &))
0x1800035a5  nop
0x1800035a6  lea     rcx, [rsp+2E8h+var_2B0]
0x1800035ab  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800035b0  xor     eax, eax
0x1800035b2  jmp     short loc_180003561
0x1800035b4  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x1800035bb  lea     rcx, [rsp+2E8h+pExceptionObject]; pExceptionObject
0x1800035c0  call    _CxxThrowException_0
```
