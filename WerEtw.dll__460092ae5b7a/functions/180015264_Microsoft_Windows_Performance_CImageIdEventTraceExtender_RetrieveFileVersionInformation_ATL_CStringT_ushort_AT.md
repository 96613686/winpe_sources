# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,XPerfCore::CFileMapping *)

- ea: `0x180015264`
- end: `0x1800155d8`
- name: `?RetrieveFileVersionInformation@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAVCFileMapping@XPerfCore@@@Z`
- size: `884`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *, struct XPerfCore::CFileMapping *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f3cc`

## callees

- `0x180001870`
- `0x180001894`
- `0x1800045d4`
- `0x180004670`
- `0x180004694`
- `0x18001154c`
- `0x180011630`
- `0x180012308`
- `0x180012418`
- `0x180012c18`
- `0x180015264`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001538a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001538a`

## string_xrefs

- `0x18001545c`: `CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        struct XPerfCore::CFileMapping *a4)
{
  void *v8; // rcx
  int VersionInfo; // edi
  unsigned __int64 v10; // r8
  __int64 result; // rax
  __int64 v12; // rdi
  __int64 v13; // r8
  unsigned __int64 v14; // r8
  __int64 v15; // r8
  void *v16; // rsi
  int Error; // ebx
  unsigned __int64 v18; // r8
  __int64 v19; // r8
  unsigned __int64 v20; // r8
  __int64 v21; // r8
  unsigned __int64 v22; // r8
  __int64 v23; // r8
  bool IsLibraryAvailable; // al
  int v25; // eax
  __int64 *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 *v30; // rbx
  unsigned int puLen[2]; // [rsp+30h] [rbp-288h] BYREF
  void *Block; // [rsp+38h] [rbp-280h] BYREF
  unsigned __int16 v33; // [rsp+40h] [rbp-278h]
  LPVOID lpBuffer[2]; // [rsp+48h] [rbp-270h] BYREF
  ATL::CAtlException *v35; // [rsp+58h] [rbp-260h] BYREF
  unsigned __int16 v36[264]; // [rsp+60h] [rbp-258h] BYREF

  lpBuffer[1] = (LPVOID)a1;
  operator delete(0);
  v8 = 0;
  Block = 0;
  if ( !a4 )
  {
    VersionInfo = -2147467261;
LABEL_5:
    operator delete(v8);
    return (unsigned int)VersionInfo;
  }
  VersionInfo = XPerfCore::CFileVersionInfo::GetVersionInfo((XPerfCore::CFileVersionInfo *)&Block, a3, a4);
  if ( VersionInfo < 0 )
  {
    v8 = Block;
    goto LABEL_5;
  }
  XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&Block, v36, v10, L"FileDescription");
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( v36[v13] );
  ATL::CSimpleStringT<unsigned short,0>::Append(a2, v36, v13);
  ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
  XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&Block, v36, v14, L"FileVersion");
  v15 = -1;
  do
    ++v15;
  while ( v36[v15] );
  ATL::CSimpleStringT<unsigned short,0>::Append(a2, v36, v15);
  ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
  lpBuffer[0] = 0;
  v16 = Block;
  if ( !Block )
  {
    Error = -2147418113;
LABEL_14:
    operator delete(v16);
    return (unsigned int)Error;
  }
  puLen[0] = 0;
  if ( !VerQueryValueW(Block, L"\\", lpBuffer, puLen) )
  {
    lpBuffer[0] = 0;
    Error = ATL::AtlHresultFromLastError();
    if ( Error < 0 )
      goto LABEL_14;
    goto LABEL_16;
  }
  if ( puLen[0] < 0xC )
  {
LABEL_16:
    operator delete(v16);
    return 2147549183LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    a2,
    L"%u.%u.%u.%u",
    *((unsigned __int16 *)lpBuffer[0] + 5),
    *((unsigned __int16 *)lpBuffer[0] + 4),
    *((unsigned __int16 *)lpBuffer[0] + 7),
    *((unsigned __int16 *)lpBuffer[0] + 6));
  ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    a2,
    L"%u",
    v33);
  ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
  XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&Block, v36, v18, L"ProductName");
  v19 = -1;
  do
    ++v19;
  while ( v36[v19] );
  ATL::CSimpleStringT<unsigned short,0>::Append(a2, v36, v19);
  ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
  XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&Block, v36, v20, L"CompanyName");
  v21 = -1;
  do
    ++v21;
  while ( v36[v21] );
  ATL::CSimpleStringT<unsigned short,0>::Append(a2, v36, v21);
  ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
  XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&Block, v36, v22, L"ProductVersion");
  v23 = -1;
  do
    ++v23;
  while ( v36[v23] );
  ATL::CSimpleStringT<unsigned short,0>::Append(a2, v36, v23);
  ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
  *(_QWORD *)puLen = 0;
  IsLibraryAvailable = Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 296));
  try
  {
    try
    {
      if ( IsLibraryAvailable )
        v25 = (*(__int64 (__fastcall **)(const unsigned __int16 *, __int64, unsigned int *))(a1 + 312))(a3, 1, puLen);
      else
        v25 = ATL::AtlHresultFromWin32(0x7Fu);
      if ( v25 >= 0 )
      {
        v26 = *(__int64 **)puLen;
      }
      else
      {
        v26 = 0;
        *(_QWORD *)puLen = 0;
      }
      if ( v26 )
      {
        v27 = *v26;
        if ( *v26 )
        {
          v28 = -1;
          do
            ++v28;
          while ( *(_WORD *)(v27 + 2 * v28) );
          ATL::CSimpleStringT<unsigned short,0>::Append(a2, v27, v28);
        }
      }
      ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
      if ( *(_QWORD *)puLen )
      {
        v29 = *(_QWORD *)(*(_QWORD *)puLen + 8LL);
        if ( v29 )
        {
          do
            ++v12;
          while ( *(_WORD *)(v29 + 2 * v12) );
          ATL::CSimpleStringT<unsigned short,0>::Append(a2, v29, (unsigned int)v12);
        }
      }
      ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
      v30 = *(__int64 **)puLen;
      if ( *(_QWORD *)puLen )
      {
        if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 296)) )
          (*(void (__fastcall **)(__int64 *))(a1 + 320))(v30);
        *(_QWORD *)puLen = 0;
      }
    }
    catch ( ... )
    {
      throw;
    }
    operator delete(Block);
    result = 0;
  }
  catch ( ATL::CAtlException *v35 )
  {
    return *(unsigned int *)v35;
  }
  try
  {
    if ( IsLibraryAvailable )
      v25 = (*(__int64 (__fastcall **)(const unsigned __int16 *, __int64, unsigned int *))(a1 + 312))(a3, 1, puLen);
    else
      v25 = ATL::AtlHresultFromWin32(0x7Fu);
    if ( v25 >= 0 )
    {
      v26 = *(__int64 **)puLen;
    }
    else
    {
      v26 = 0;
      *(_QWORD *)puLen = 0;
    }
    if ( v26 )
    {
      v27 = *v26;
      if ( *v26 )
      {
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)(v27 + 2 * v28) );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v27, v28);
      }
    }
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    if ( *(_QWORD *)puLen )
    {
      v29 = *(_QWORD *)(*(_QWORD *)puLen + 8LL);
      if ( v29 )
      {
        do
          ++v12;
        while ( *(_WORD *)(v29 + 2 * v12) );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v29, (unsigned int)v12);
      }
    }
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    v30 = *(__int64 **)puLen;
    if ( *(_QWORD *)puLen )
    {
      if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 296)) )
        (*(void (__fastcall **)(__int64 *))(a1 + 320))(v30);
      *(_QWORD *)puLen = 0;
    }
  }
  catch ( ... )
  {
    throw;
  }
}

```

## disassembly

```asm
0x180015264  push    rbx
0x180015266  push    rsi
0x180015267  push    rdi
0x180015268  push    r12
0x18001526a  push    r14
0x18001526c  push    r15
0x18001526e  sub     rsp, 288h
0x180015275  mov     rax, cs:__security_cookie
0x18001527c  xor     rax, rsp
0x18001527f  mov     [rsp+2B8h+var_48], rax
0x180015287  mov     rdi, r9
0x18001528a  mov     r15, r8
0x18001528d  mov     rbx, rdx
0x180015290  mov     r14, rcx
0x180015293  mov     [rsp+2B8h+var_268], rcx
0x180015298  xor     ecx, ecx; Block
0x18001529a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001529f  xor     r12d, r12d
0x1800152a2  mov     ecx, r12d
0x1800152a5  mov     [rsp+2B8h+Block], rcx
0x1800152aa  test    rdi, rdi
0x1800152ad  jnz     short loc_1800152B6
0x1800152af  mov     edi, 80004003h
0x1800152b4  jmp     short loc_1800152D1
0x1800152b6  mov     r8, rdi; struct XPerfCore::CFileMapping *
0x1800152b9  mov     rdx, r15; unsigned __int16 *
0x1800152bc  lea     rcx, [rsp+2B8h+Block]; this
0x1800152c1  call    ?GetVersionInfo@CFileVersionInfo@XPerfCore@@QEAAJPEBGPEAVCFileMapping@2@@Z; XPerfCore::CFileVersionInfo::GetVersionInfo(ushort const *,XPerfCore::CFileMapping *)
0x1800152c6  mov     edi, eax
0x1800152c8  test    eax, eax
0x1800152ca  jns     short loc_1800152DD
0x1800152cc  mov     rcx, [rsp+2B8h+Block]; Block
0x1800152d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800152d6  mov     eax, edi
0x1800152d8  jmp     loc_1800155B6
0x1800152dd  lea     r9, aFiledescriptio; "FileDescription"
0x1800152e4  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x1800152e9  lea     rcx, [rsp+2B8h+Block]; this
0x1800152ee  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x1800152f3  lea     rax, [rsp+2B8h+var_258]
0x1800152f8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800152fc  mov     r8, rdi
0x1800152ff  inc     r8
0x180015302  cmp     [rax+r8*2], r12w
0x180015307  jnz     short loc_1800152FF
0x180015309  lea     rdx, [rsp+2B8h+var_258]
0x18001530e  mov     rcx, rbx
0x180015311  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180015316  mov     rcx, rbx
0x180015319  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001531e  lea     r9, aFileversion; "FileVersion"
0x180015325  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x18001532a  lea     rcx, [rsp+2B8h+Block]; this
0x18001532f  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180015334  lea     rax, [rsp+2B8h+var_258]
0x180015339  mov     r8, rdi
0x18001533c  inc     r8
0x18001533f  cmp     [rax+r8*2], r12w
0x180015344  jnz     short loc_18001533C
0x180015346  lea     rdx, [rsp+2B8h+var_258]
0x18001534b  mov     rcx, rbx
0x18001534e  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180015353  mov     rcx, rbx
0x180015356  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001535b  mov     [rsp+2B8h+lpBuffer], r12
0x180015360  mov     rsi, [rsp+2B8h+Block]
0x180015365  test    rsi, rsi
0x180015368  jnz     short loc_180015371
0x18001536a  mov     ebx, 8000FFFFh
0x18001536f  jmp     short loc_1800153A4
0x180015371  mov     [rsp+2B8h+puLen], r12d
0x180015376  lea     r9, [rsp+2B8h+puLen]; puLen
0x18001537b  lea     r8, [rsp+2B8h+lpBuffer]; lplpBuffer
0x180015380  lea     rdx, asc_18002D2B0; "\\"
0x180015387  mov     rcx, rsi; pBlock
0x18001538a  call    cs:__imp_VerQueryValueW
0x180015390  test    eax, eax
0x180015392  jnz     short loc_1800153B3
0x180015394  mov     [rsp+2B8h+lpBuffer], r12
0x180015399  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001539e  mov     ebx, eax
0x1800153a0  test    eax, eax
0x1800153a2  jns     short loc_1800153BA
0x1800153a4  mov     rcx, rsi; Block
0x1800153a7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800153ac  mov     eax, ebx
0x1800153ae  jmp     loc_1800155B6
0x1800153b3  cmp     [rsp+2B8h+puLen], 0Ch
0x1800153b8  jnb     short loc_1800153CC
0x1800153ba  mov     rcx, rsi; Block
0x1800153bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800153c2  mov     eax, 8000FFFFh
0x1800153c7  jmp     loc_1800155B6
0x1800153cc  mov     rdx, [rsp+2B8h+lpBuffer]
0x1800153d1  movzx   eax, word ptr [rdx+0Ch]
0x1800153d5  movzx   ecx, word ptr [rdx+0Eh]
0x1800153d9  movzx   r9d, word ptr [rdx+8]
0x1800153de  movzx   r8d, word ptr [rdx+0Ah]
0x1800153e3  mov     [rsp+2B8h+var_290], eax
0x1800153e7  mov     [rsp+2B8h+var_298], ecx
0x1800153eb  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x1800153f2  mov     rcx, rbx
0x1800153f5  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800153fa  mov     rcx, rbx
0x1800153fd  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180015402  movzx   r8d, [rsp+2B8h+var_278]
0x180015408  lea     rdx, aU; "%u"
0x18001540f  mov     rcx, rbx
0x180015412  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180015417  mov     rcx, rbx
0x18001541a  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001541f  lea     r9, aProductname; "ProductName"
0x180015426  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x18001542b  lea     rcx, [rsp+2B8h+Block]; this
0x180015430  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180015435  lea     rax, [rsp+2B8h+var_258]
0x18001543a  mov     r8, rdi
0x18001543d  inc     r8
0x180015440  cmp     [rax+r8*2], r12w
0x180015445  jnz     short loc_18001543D
0x180015447  lea     rdx, [rsp+2B8h+var_258]
0x18001544c  mov     rcx, rbx
0x18001544f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180015454  mov     rcx, rbx
0x180015457  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001545c  lea     r9, aCompanyname; "CompanyName"
0x180015463  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x180015468  lea     rcx, [rsp+2B8h+Block]; this
0x18001546d  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180015472  lea     rax, [rsp+2B8h+var_258]
0x180015477  mov     r8, rdi
0x18001547a  inc     r8
0x18001547d  cmp     [rax+r8*2], r12w
0x180015482  jnz     short loc_18001547A
0x180015484  lea     rdx, [rsp+2B8h+var_258]
0x180015489  mov     rcx, rbx
0x18001548c  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180015491  mov     rcx, rbx
0x180015494  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180015499  lea     r9, aProductversion; "ProductVersion"
0x1800154a0  lea     rdx, [rsp+2B8h+var_258]; unsigned __int16 *
0x1800154a5  lea     rcx, [rsp+2B8h+Block]; this
0x1800154aa  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x1800154af  lea     rax, [rsp+2B8h+var_258]
0x1800154b4  mov     r8, rdi
0x1800154b7  inc     r8
0x1800154ba  cmp     [rax+r8*2], r12w
0x1800154bf  jnz     short loc_1800154B7
0x1800154c1  lea     rdx, [rsp+2B8h+var_258]
0x1800154c6  mov     rcx, rbx
0x1800154c9  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800154ce  mov     rcx, rbx
0x1800154d1  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800154d6  mov     qword ptr [rsp+2B8h+puLen], r12
0x1800154db  lea     rsi, [r14+128h]
0x1800154e2  mov     rcx, rsi; this
0x1800154e5  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x1800154ea  test    al, al
0x1800154ec  jz      short loc_180015506
0x1800154ee  lea     r8, [rsp+2B8h+puLen]
0x1800154f3  mov     edx, 1
0x1800154f8  mov     rcx, r15
0x1800154fb  mov     rax, [rsi+10h]
0x1800154ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015504  jmp     short loc_180015510
0x180015506  mov     ecx, 7Fh; unsigned int
0x18001550b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180015510  test    eax, eax
0x180015512  jns     short loc_18001551E
0x180015514  mov     rax, r12
0x180015517  mov     qword ptr [rsp+2B8h+puLen], rax
0x18001551c  jmp     short loc_180015523
0x18001551e  mov     rax, qword ptr [rsp+2B8h+puLen]
0x180015523  test    rax, rax
0x180015526  jz      short loc_180015545
0x180015528  mov     rdx, [rax]
0x18001552b  test    rdx, rdx
0x18001552e  jz      short loc_180015545
0x180015530  mov     r8, rdi
0x180015533  inc     r8
0x180015536  cmp     [rdx+r8*2], r12w
0x18001553b  jnz     short loc_180015533
0x18001553d  mov     rcx, rbx
0x180015540  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180015545  mov     rcx, rbx
0x180015548  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001554d  mov     rdx, qword ptr [rsp+2B8h+puLen]
0x180015552  test    rdx, rdx
0x180015555  jz      short loc_180015575
0x180015557  mov     rdx, [rdx+8]
0x18001555b  test    rdx, rdx
0x18001555e  jz      short loc_180015575
0x180015560  inc     rdi
0x180015563  cmp     [rdx+rdi*2], r12w
0x180015568  jnz     short loc_180015560
0x18001556a  mov     r8d, edi
0x18001556d  mov     rcx, rbx
0x180015570  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180015575  mov     rcx, rbx
0x180015578  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001557d  mov     rbx, qword ptr [rsp+2B8h+puLen]
0x180015582  test    rbx, rbx
0x180015585  jz      short loc_1800155A4
0x180015587  mov     rcx, rsi; this
0x18001558a  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x18001558f  test    al, al
0x180015591  jz      short loc_18001559F
0x180015593  mov     rcx, rbx
0x180015596  mov     rax, [rsi+18h]
0x18001559a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001559f  mov     qword ptr [rsp+2B8h+puLen], r12
0x1800155a4  mov     rcx, [rsp+2B8h+Block]; Block
0x1800155a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800155ae  xor     eax, eax
0x1800155b0  jmp     short loc_1800155B6
0x1800155b2  mov     eax, [rsp+2B8h+puLen]
0x1800155b6  mov     rcx, [rsp+2B8h+var_48]
0x1800155be  xor     rcx, rsp; StackCookie
0x1800155c1  call    __security_check_cookie
0x1800155c6  add     rsp, 288h
0x1800155cd  pop     r15
0x1800155cf  pop     r14
0x1800155d1  pop     r12
0x1800155d3  pop     rdi
0x1800155d4  pop     rsi
0x1800155d5  pop     rbx
0x1800155d6  retn
```
