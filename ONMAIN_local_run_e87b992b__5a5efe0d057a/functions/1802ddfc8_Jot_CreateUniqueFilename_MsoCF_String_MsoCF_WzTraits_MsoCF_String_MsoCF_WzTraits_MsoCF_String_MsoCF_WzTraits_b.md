# Jot::CreateUniqueFilename(MsoCF::String<MsoCF::WzTraits>,MsoCF::String<MsoCF::WzTraits>,MsoCF::String<MsoCF::WzTraits>,bool,bool,bool,bool)

- ea: `0x1802ddfc8`
- end: `0x1802de718`
- name: `?CreateUniqueFilename@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$String@UWzTraits@MsoCF@@@MsoCF@@00_N111@Z`
- size: `1872`
- prototype: `_QWORD *__fastcall(_QWORD *, void *, const wchar_t *, __int64, wchar_t *, char, char, char)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, loader_planting`

## callers

- `0x1802ddbc0`

## callees

- `0x18005b344`
- `0x18005b408`
- `0x18005cab0`
- `0x180094064`
- `0x18009424c`
- `0x1800943d4`
- `0x180145f40`
- `0x1801c1cbc`
- `0x18024cb70`
- `0x180258a54`
- `0x180273ea4`
- `0x1802b0bc4`
- `0x1802ddfc8`
- `0x1802de718`
- `0x1802e2190`
- `0x1802e2251`
- `0x1802e5170`
- `0x1803046d0`
- `0x1806728c0`
- `0x1806a8c10`
- `0x1806a8c38`
- `0x180700e54`
- `0x180a716e0`

## import_xrefs

- `KERNEL32!FindClose` at `0x1802de616`
- `KERNEL32!FindClose` at `0x1802de6c2`
- `KERNEL32!FindClose` at `0x1802de616`
- `KERNEL32!FindClose` at `0x1802de6c2`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x1802de2ea`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x1802de361`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x1802de2ea`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x1802de361`
- `Mso20Win32Client!__imp_?MsoWzFileNameInPath@@YAPEB_WPEB_W@Z` at `0x1802de282`
- `Mso20Win32Client!__imp_?MsoWzFileNameInPath@@YAPEB_WPEB_W@Z` at `0x1802de282`
- `Mso20Win32Client!__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z` at `0x1802de5b4`
- `Mso20Win32Client!__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z` at `0x1802de5b4`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x1802de07f`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x1802de4d4`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x1802de5cd`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x1802de07f`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x1802de4d4`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x1802de5cd`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802de30b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802de642`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802de656`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802de6ee`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802de702`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802de30b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802de642`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802de656`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802de6ee`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802de702`
- `Mso20Win32Client!__imp_MsoPwchStrStrFast` at `0x1802de16d`
- `Mso20Win32Client!__imp_MsoPwchStrStrFast` at `0x1802de16d`
- `Mso20Win32Client!__imp_MsoParseUIntWz` at `0x1802de3b4`
- `Mso20Win32Client!__imp_MsoParseUIntWz` at `0x1802de3b4`

## pseudocode

```c
_QWORD *__fastcall Jot::CreateUniqueFilename(
        _QWORD *a1,
        void *a2,
        const wchar_t *a3,
        __int64 a4,
        wchar_t *a5,
        char a6,
        char a7,
        char a8)
{
  _QWORD *v11; // r14
  wchar_t *v12; // rax
  const wchar_t *v13; // rdx
  bool v14; // r9
  Jot *v15; // rcx
  unsigned int FileOrDirectory; // eax
  unsigned int v17; // r9d
  __int64 v18; // rdx
  __int64 v19; // rdi
  __int64 v20; // rcx
  unsigned int v21; // r13d
  __m128i si128; // xmm6
  int *v23; // rdx
  char *v24; // rcx
  const wchar_t *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r9
  Mso::Memory *v28; // rdx
  Mso::Memory *v29; // rcx
  _BYTE *v30; // r15
  _BYTE *v31; // rdi
  struct _GUID *p_Src_8; // rcx
  unsigned int v33; // eax
  __int64 v34; // rax
  const wchar_t *v35; // rdx
  bool v36; // r9
  Jot *v37; // rcx
  _QWORD *v38; // rax
  wchar_t *v39; // rax
  const wchar_t *v40; // rcx
  const wchar_t *v41; // rdx
  bool v42; // r9
  Jot *v43; // rcx
  unsigned int v44; // eax
  unsigned int v45; // r9d
  _QWORD *v46; // rax
  wchar_t *v47; // rbx
  __int64 v48; // rax
  const wchar_t *v49; // rdx
  bool v50; // r9
  Jot *v51; // rcx
  unsigned int v52; // eax
  unsigned int v53; // r9d
  void *v54; // rdx
  void *v56; // rdx
  char v57; // [rsp+28h] [rbp-E0h]
  int v58; // [rsp+30h] [rbp-D8h]
  __int64 v59; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE hFindFile; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v61; // [rsp+58h] [rbp-B0h]
  _QWORD *Src; // [rsp+60h] [rbp-A8h]
  struct _GUID Src_8; // [rsp+68h] [rbp-A0h] BYREF
  __m128i v64; // [rsp+78h] [rbp-90h]
  char v65[16]; // [rsp+88h] [rbp-80h] BYREF
  __m128i v66; // [rsp+98h] [rbp-70h]
  int v67[4]; // [rsp+A8h] [rbp-60h] BYREF
  __m128i v68; // [rsp+B8h] [rbp-50h]
  _OWORD v69[2]; // [rsp+C8h] [rbp-40h] BYREF
  int v70[2]; // [rsp+E8h] [rbp-20h] BYREF
  char *v71; // [rsp+F0h] [rbp-18h]
  int v72; // [rsp+F8h] [rbp-10h]
  char v73; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v74[32]; // [rsp+138h] [rbp+30h] BYREF
  void **v75; // [rsp+158h] [rbp+50h] BYREF
  Mso::Memory *v76; // [rsp+160h] [rbp+58h]
  int v77; // [rsp+168h] [rbp+60h]
  __int64 v78; // [rsp+170h] [rbp+68h]
  _BYTE v79[272]; // [rsp+178h] [rbp+70h] BYREF
  void **v80; // [rsp+288h] [rbp+180h] BYREF
  Mso::Memory *v81; // [rsp+290h] [rbp+188h]
  int v82; // [rsp+298h] [rbp+190h]
  __int64 v83; // [rsp+2A0h] [rbp+198h]
  _BYTE v84[272]; // [rsp+2A8h] [rbp+1A0h] BYREF
  void **v85; // [rsp+3B8h] [rbp+2B0h] BYREF
  Mso::Memory *v86; // [rsp+3C0h] [rbp+2B8h]
  int v87; // [rsp+3C8h] [rbp+2C0h]
  __int64 v88; // [rsp+3D0h] [rbp+2C8h]
  _BYTE v89[272]; // [rsp+3D8h] [rbp+2D0h] BYREF
  int v90[148]; // [rsp+4E8h] [rbp+3E0h] BYREF

  v11 = a1;
  Src = a1;
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 7;
  *(_WORD *)a1 = 0;
  LODWORD(v61) = 1;
  if ( a3 )
  {
    std::wstring::assign(a1, a2);
    hFindFile = v11;
    if ( v11[2] < 0x105u )
      std::wstring::resize(v11, 261);
    v12 = (wchar_t *)std::wstring::operator[](v11, 0);
    MsoAppendToPath(a3, v12, 260);
    Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(&hFindFile);
    v15 = (Jot *)v11;
    if ( v11[3] > 7u )
      v15 = (Jot *)*v11;
    LOBYTE(v13) = (_BYTE)a5;
    FileOrDirectory = Jot::CreateFileOrDirectory(v15, v13, a6 != 1, v14);
    if ( !FileOrDirectory )
      return v11;
    if ( FileOrDirectory != 183 && FileOrDirectory != 80 )
    {
      if ( v11[3] > 7u )
        v11 = (_QWORD *)*v11;
      Jot::ThrowWin32WithFilenameTag((Jot *)FileOrDirectory, (unsigned int)v11, (const wchar_t *)0x10CF220, v17);
    }
    if ( a7 )
      return v11;
  }
  if ( !a4 )
    goto LABEL_77;
  v78 = 260;
  v75 = &off_181533690;
  v76 = (Mso::Memory *)v79;
  v77 = 260;
  MsoCF::Strings::SetWtzEmpty(&v75);
  v83 = 260;
  v80 = &off_181533690;
  v81 = (Mso::Memory *)v84;
  v82 = 260;
  MsoCF::Strings::SetWtzEmpty(&v80);
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)(a4 + 2 * v18) );
  v19 = MsoPwchStrStrFast(a4, v18, L"|0", 1);
  MsoCF::Strings::SetWtzFromArrayOfCharacters(&v75, a4, (v19 - a4) >> 1);
  v20 = -1;
  do
    ++v20;
  while ( *(_WORD *)(a4 + 2 * v20) );
  MsoCF::Strings::SetWtzFromArrayOfCharacters(&v80, v19 + 4, (a4 + 2LL * (int)v20 - (v19 + 4)) >> 1);
  v21 = 0;
  *(_OWORD *)v67 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v68 = si128;
  LOWORD(v67[0]) = 0;
  v59 = a4;
  MsoCF::StringFromPatternWithConverter<wchar_t const *,wchar_t [2]>(&Src_8);
  LODWORD(v61) = 3;
  std::wstring::operator=(v67, &Src_8);
  std::wstring::~wstring(&Src_8);
  *(_OWORD *)v65 = 0;
  v66 = si128;
  *(_WORD *)v65 = 0;
  hFindFile = (HANDLE)-1LL;
  memset_0(v90, 0, sizeof(v90));
  while ( 1 )
  {
    v23 = v67;
    if ( v68.m128i_i64[1] > 7uLL )
      LODWORD(v23) = v67[0];
    if ( !(unsigned __int8)Jot::FFindFiles((int)a2, (int)v23, (int)&hFindFile, (int)v90, v65, v58, 0) )
      break;
    v24 = v65;
    if ( v66.m128i_i64[1] > 7uLL )
      v24 = *(char **)v65;
    v25 = MsoWzFileNameInPath((const wchar_t *)v24);
    v88 = 260;
    v85 = &off_181533690;
    v86 = (Mso::Memory *)v89;
    v87 = 260;
    MsoCF::Strings::CopyWzToWtz(v25, &v85);
    v26 = *(unsigned __int16 *)v76;
    v27 = *(unsigned __int16 *)v86;
    if ( (unsigned int)v27 >= (unsigned int)v26 )
      v27 = *(unsigned __int16 *)v76;
    if ( !(unsigned int)MsoFRgwchEqual((char *)v76 + 2, v26, (char *)v86 + 2, v27, 1) )
      goto LABEL_27;
    v28 = v86;
    v30 = (char *)v86 + 2 * *(unsigned __int16 *)v76 + 2;
    v31 = (char *)v86 + 2 * (*(unsigned __int16 *)v86 - (unsigned __int64)*(unsigned __int16 *)v81) + 2;
    if ( v31 < v30 )
    {
LABEL_39:
      if ( v28 != (Mso::Memory *)v89 )
      {
        v29 = v28;
LABEL_28:
        Mso::Memory::Free(v29, v28);
      }
    }
    else
    {
      if ( !(unsigned int)MsoFRgwchEqual((char *)v81 + 2, *(unsigned __int16 *)v81, v31, *(unsigned __int16 *)v81, 1) )
      {
        v28 = v86;
        goto LABEL_39;
      }
      Src_8 = 0;
      v64 = si128;
      LOWORD(Src_8.Data1) = 0;
      std::wstring::assign(&Src_8, v30);
      LODWORD(v59) = 0;
      p_Src_8 = &Src_8;
      if ( v64.m128i_i64[1] > 7uLL )
        p_Src_8 = *(struct _GUID **)&Src_8.Data1;
      if ( (unsigned int)MsoParseUIntWz(p_Src_8, &v59) )
      {
        v33 = v59;
        if ( v21 > (unsigned int)v59 )
          v33 = v21;
        v21 = v33;
      }
      std::wstring::~wstring(&Src_8);
LABEL_27:
      v29 = v86;
      if ( v86 != (Mso::Memory *)v89 )
        goto LABEL_28;
    }
  }
  Src_8 = 0;
  v64 = si128;
  LOWORD(Src_8.Data1) = 0;
  *(_QWORD *)v70 = &off_1815167C8;
  v71 = &v73;
  v72 = 50;
  MsoCF::Strings::SetWzFromNumber((int)v70, v57);
  v59 = a4;
  v34 = MsoCF::StringFromPattern<wchar_t const *,MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFixedBuffer<wchar_t,25>>>(
          v69,
          &v59,
          v70);
  std::wstring::operator=(&Src_8, v34);
  std::wstring::~wstring(v69);
  v37 = (Jot *)&Src_8;
  if ( v64.m128i_i64[1] > 7uLL )
    v37 = *(Jot **)&Src_8.Data1;
  LOBYTE(v35) = (_BYTE)a5;
  Jot::ThrowOnInvalidFilename(v37, v35, 0, v36);
  std::wstring::assign(v11, a2);
  v38 = (_QWORD *)Jot::basic_strbuffer<std::wstring>::basic_strbuffer<std::wstring>(&v59, v11, 260);
  v39 = (wchar_t *)std::wstring::operator[](*v38, 0);
  v40 = (const wchar_t *)&Src_8;
  if ( v64.m128i_i64[1] > 7uLL )
    v40 = *(const wchar_t **)&Src_8.Data1;
  MsoAppendToPath(v40, v39, 260);
  Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(&v59);
  v43 = (Jot *)v11;
  if ( v11[3] > 7u )
    v43 = (Jot *)*v11;
  LOBYTE(v41) = (_BYTE)a5;
  v44 = Jot::CreateFileOrDirectory(v43, v41, a6 != 1, v42);
  if ( !v44 )
  {
    std::wstring::~wstring(&Src_8);
    goto LABEL_61;
  }
  if ( v44 != 183 && v44 != 80 )
  {
    if ( v11[3] > 7u )
      v11 = (_QWORD *)*v11;
    Jot::ThrowWin32WithFilenameTag((Jot *)v44, (unsigned int)v11, (const wchar_t *)0x10CF221, v45);
  }
  std::wstring::~wstring(&Src_8);
  if ( !a7 )
  {
    if ( a8 )
    {
      std::wstring::assign(v11, a2);
      v46 = (_QWORD *)Jot::basic_strbuffer<std::wstring>::basic_strbuffer<std::wstring>(&v59, v11, 260);
      v47 = (wchar_t *)std::wstring::operator[](*v46, 0);
      v69[0] = *CreateGuid_ElseCrash(&Src_8);
      v48 = OGuid::ToString(v74, v69, 0);
      if ( *(_QWORD *)(v48 + 24) > 7u )
        v48 = *(_QWORD *)v48;
      MsoAppendToPath((const wchar_t *)v48, v47, 260);
      std::wstring::~wstring(v74);
      Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(&v59);
      v51 = (Jot *)v11;
      if ( v11[3] > 7u )
        v51 = (Jot *)*v11;
      LOBYTE(v49) = (_BYTE)a5;
      v52 = Jot::CreateFileOrDirectory(v51, v49, a6 != 1, v50);
      if ( v52 )
      {
        if ( v11[3] > 7u )
          v11 = (_QWORD *)*v11;
        Jot::ThrowWin32WithFilenameTag((Jot *)v52, (unsigned int)v11, (const wchar_t *)0x10CF223, v53);
      }
      goto LABEL_61;
    }
    if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      FindClose(hFindFile);
    std::wstring::~wstring(v65);
    std::wstring::~wstring(v67);
    if ( v81 != (Mso::Memory *)v84 )
      Mso::Memory::Free(v81, v56);
    if ( v76 != (Mso::Memory *)v79 )
      Mso::Memory::Free(v76, v56);
LABEL_77:
    MsoCF::ThrowWin32Tag((MsoCF *)2, 0x114578Fu, (unsigned int)a3);
  }
LABEL_61:
  if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    FindClose(hFindFile);
  std::wstring::~wstring(v65);
  std::wstring::~wstring(v67);
  if ( v81 != (Mso::Memory *)v84 )
    Mso::Memory::Free(v81, v54);
  if ( v76 != (Mso::Memory *)v79 )
    Mso::Memory::Free(v76, v54);
  return v11;
}

```

## disassembly

```asm
0x1802ddfc8  mov     rax, rsp
0x1802ddfcb  mov     [rax+10h], rbx
0x1802ddfcf  mov     [rax+18h], rsi
0x1802ddfd3  mov     [rax+20h], rdi
0x1802ddfd7  push    rbp
0x1802ddfd8  push    r12
0x1802ddfda  push    r13
0x1802ddfdc  push    r14
0x1802ddfde  push    r15
0x1802ddfe0  lea     rbp, [rax-678h]
0x1802ddfe7  sub     rsp, 750h
0x1802ddfee  movaps  xmmword ptr [rax-38h], xmm6
0x1802ddff2  mov     rax, cs:__security_cookie
0x1802ddff9  xor     rax, rsp
0x1802ddffc  mov     [rbp+670h+var_40], rax
0x1802de003  mov     rbx, r9
0x1802de006  mov     rdi, r8
0x1802de009  mov     rsi, rdx
0x1802de00c  mov     r14, rcx
0x1802de00f  mov     qword ptr [rsp+770h+Src.Data1], rcx
0x1802de014  mov     eax, 1
0x1802de019  mov     dword ptr [rsp+770h+var_720], eax
0x1802de01d  xorps   xmm0, xmm0
0x1802de020  movups  xmmword ptr [rcx], xmm0
0x1802de023  xor     r15d, r15d
0x1802de026  mov     [rcx+10h], r15
0x1802de02a  mov     qword ptr [rcx+18h], 7
0x1802de032  mov     [rcx], r15w
0x1802de036  mov     dword ptr [rsp+770h+var_720], eax
0x1802de03a  mov     r13d, 104h
0x1802de040  mov     r12b, byte ptr [rbp+670h+arg_20]
0x1802de047  test    r8, r8
0x1802de04a  jz      loc_1802DE0EB
0x1802de050  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1802de055  mov     [rsp+770h+hFindFile], r14
0x1802de05a  lea     edx, [r13+1]
0x1802de05e  cmp     [r14+10h], rdx
0x1802de062  jnb     short loc_1802DE06C
0x1802de064  mov     rcx, r14
0x1802de067  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1802de06c  xor     edx, edx
0x1802de06e  mov     rcx, r14
0x1802de071  call    ??A?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEA_W_K@Z; std::wstring::operator[](unsigned __int64)
0x1802de076  mov     r8d, r13d
0x1802de079  mov     rdx, rax
0x1802de07c  mov     rcx, rdi
0x1802de07f  call    cs:__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z; MsoAppendToPath(wchar_t const *,wchar_t *,int)
0x1802de085  lea     rcx, [rsp+770h+hFindFile]
0x1802de08a  call    ??1?$basic_strbuffer@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Jot@@QEAA@XZ; Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(void)
0x1802de08f  mov     r8b, [rbp+670h+arg_28]
0x1802de096  xor     r8b, 1; bool
0x1802de09a  mov     rcx, r14
0x1802de09d  cmp     qword ptr [r14+18h], 7
0x1802de0a2  jbe     short loc_1802DE0A7
0x1802de0a4  mov     rcx, [r14]; this
0x1802de0a7  mov     dl, r12b; wchar_t *
0x1802de0aa  call    ?CreateFileOrDirectory@Jot@@YAKPEB_W_N1@Z; Jot::CreateFileOrDirectory(wchar_t const *,bool,bool)
0x1802de0af  test    eax, eax
0x1802de0b1  jz      loc_1802DE65D
0x1802de0b7  cmp     eax, 0B7h
0x1802de0bc  jz      short loc_1802DE0DE
0x1802de0be  cmp     eax, 50h ; 'P'
0x1802de0c1  jz      short loc_1802DE0DE
0x1802de0c3  cmp     qword ptr [r14+18h], 7
0x1802de0c8  jbe     short loc_1802DE0CD
0x1802de0ca  mov     r14, [r14]
0x1802de0cd  mov     r8d, 10CF220h; wchar_t *
0x1802de0d3  mov     rdx, r14; unsigned int
0x1802de0d6  mov     ecx, eax; this
0x1802de0d8  call    ?ThrowWin32WithFilenameTag@Jot@@YAXKPEB_WK@Z; Jot::ThrowWin32WithFilenameTag(ulong,wchar_t const *,ulong)
0x1802de0de  cmp     [rbp+670h+arg_30], r15b
0x1802de0e5  jnz     loc_1802DE65D
0x1802de0eb  test    rbx, rbx
0x1802de0ee  jz      loc_1802DE708
0x1802de0f4  mov     [rbp+670h+var_608], r13
0x1802de0f8  lea     rdi, off_181533690
0x1802de0ff  mov     [rbp+670h+var_620], rdi
0x1802de103  lea     rax, [rbp+670h+var_600]
0x1802de107  mov     [rbp+670h+var_618], rax
0x1802de10b  mov     [rbp+670h+var_610], r13d
0x1802de10f  lea     rcx, [rbp+670h+var_620]
0x1802de113  call    ?SetWtzEmpty@Strings@MsoCF@@YAXAEAV?$CWtzInBuffer_Template@V?$CBuffer@_W@MsoCF@@@2@H@Z; MsoCF::Strings::SetWtzEmpty(MsoCF::CWtzInBuffer_Template<MsoCF::CBuffer<wchar_t>> &,int)
0x1802de118  nop
0x1802de119  mov     [rbp+670h+var_4D8], 104h
0x1802de124  mov     [rbp+670h+var_4F0], rdi
0x1802de12b  lea     rax, [rbp+670h+var_4D0]
0x1802de132  mov     [rbp+670h+var_4E8], rax
0x1802de139  mov     [rbp+670h+var_4E0], r13d
0x1802de140  lea     rcx, [rbp+670h+var_4F0]
0x1802de147  call    ?SetWtzEmpty@Strings@MsoCF@@YAXAEAV?$CWtzInBuffer_Template@V?$CBuffer@_W@MsoCF@@@2@H@Z; MsoCF::Strings::SetWtzEmpty(MsoCF::CWtzInBuffer_Template<MsoCF::CBuffer<wchar_t>> &,int)
0x1802de14c  or      r13, 0FFFFFFFFFFFFFFFFh
0x1802de150  mov     rdx, r13
0x1802de153  inc     rdx
0x1802de156  cmp     [rbx+rdx*2], r15w
0x1802de15b  jnz     short loc_1802DE153
0x1802de15d  mov     r9d, 1
0x1802de163  lea     r8, a0_19; "|0"
0x1802de16a  mov     rcx, rbx
0x1802de16d  call    cs:__imp_MsoPwchStrStrFast
0x1802de173  mov     rdi, rax
0x1802de176  mov     r8, rax
0x1802de179  sub     r8, rbx
0x1802de17c  sar     r8, 1
0x1802de17f  mov     rdx, rbx
0x1802de182  lea     rcx, [rbp+670h+var_620]
0x1802de186  call    ?SetWtzFromArrayOfCharacters@Strings@MsoCF@@YAXAEAV?$CWtzInBuffer_Template@V?$CBuffer@_W@MsoCF@@@2@PEB_WH@Z; MsoCF::Strings::SetWtzFromArrayOfCharacters(MsoCF::CWtzInBuffer_Template<MsoCF::CBuffer<wchar_t>> &,wchar_t const *,int)
0x1802de18b  mov     rcx, r13
0x1802de18e  inc     rcx
0x1802de191  cmp     [rbx+rcx*2], r15w
0x1802de196  jnz     short loc_1802DE18E
0x1802de198  lea     rdx, [rdi+4]
0x1802de19c  movsxd  r8, ecx
0x1802de19f  add     r8, r8
0x1802de1a2  sub     r8, rdx
0x1802de1a5  add     r8, rbx
0x1802de1a8  sar     r8, 1
0x1802de1ab  lea     rcx, [rbp+670h+var_4F0]
0x1802de1b2  call    ?SetWtzFromArrayOfCharacters@Strings@MsoCF@@YAXAEAV?$CWtzInBuffer_Template@V?$CBuffer@_W@MsoCF@@@2@PEB_WH@Z; MsoCF::Strings::SetWtzFromArrayOfCharacters(MsoCF::CWtzInBuffer_Template<MsoCF::CBuffer<wchar_t>> &,wchar_t const *,int)
0x1802de1b7  mov     r13d, r15d
0x1802de1ba  xorps   xmm0, xmm0
0x1802de1bd  movups  xmmword ptr [rbp+670h+var_6D0], xmm0
0x1802de1c1  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1802de1c9  movdqu  [rbp+670h+var_6C0], xmm6
0x1802de1ce  mov     word ptr [rbp+670h+var_6D0], r15w
0x1802de1d3  mov     [rsp+770h+var_730], rbx
0x1802de1d8  lea     rdx, [rsp+770h+var_730]
0x1802de1dd  lea     rcx, [rsp+770h+Src.Data4]; Src
0x1802de1e2  call    ??$StringFromPatternWithConverter@PEB_W$$BY01_W@MsoCF@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBQEB_WAEAY01$$CB_W@Z; MsoCF::StringFromPatternWithConverter<wchar_t const *,wchar_t [2]>(wchar_t const * const &,wchar_t const (&)[2])
0x1802de1e7  mov     dword ptr [rsp+770h+var_720], 3
0x1802de1ef  lea     rdx, [rsp+770h+Src.Data4]
0x1802de1f4  lea     rcx, [rbp+670h+var_6D0]
0x1802de1f8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1802de1fd  lea     rcx, [rsp+770h+Src.Data4]; void *
0x1802de202  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802de207  xorps   xmm0, xmm0
0x1802de20a  movups  xmmword ptr [rbp+670h+var_6F0], xmm0
0x1802de20e  movdqu  [rbp+670h+var_6E0], xmm6
0x1802de213  mov     word ptr [rbp+670h+var_6F0], r15w
0x1802de218  mov     [rsp+770h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x1802de221  xor     edx, edx; Val
0x1802de223  mov     r8d, 250h; Size
0x1802de229  lea     rcx, [rbp+670h+var_290]; void *
0x1802de230  call    memset_0
0x1802de235  lea     r12, off_181533690
0x1802de23c  lea     rdx, [rbp+670h+var_6D0]
0x1802de240  cmp     qword ptr [rbp+670h+var_6C0+8], 7
0x1802de245  cmova   rdx, qword ptr [rbp+670h+var_6D0]; int
0x1802de24a  mov     [rsp+770h+var_740], r15b; char
0x1802de24f  lea     rax, [rbp+670h+var_6F0]
0x1802de253  mov     [rsp+770h+var_750], rax; char
0x1802de258  lea     r9, [rbp+670h+var_290]; int
0x1802de25f  lea     r8, [rsp+770h+hFindFile]; int
0x1802de264  mov     rcx, rsi; int
0x1802de267  call    ?FFindFiles@Jot@@YA_NPEB_W0AEAVCFindHandleOwner@Ofc@@PEAU_WIN32_FIND_DATAW@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N4@Z; Jot::FFindFiles(wchar_t const *,wchar_t const *,Ofc::CFindHandleOwner &,_WIN32_FIND_DATAW *,std::wstring &,bool,bool)
0x1802de26c  test    al, al
0x1802de26e  jz      loc_1802DE400
0x1802de274  lea     rcx, [rbp+670h+var_6F0]
0x1802de278  cmp     qword ptr [rbp+670h+var_6E0+8], 7
0x1802de27d  cmova   rcx, qword ptr [rbp+670h+var_6F0]
0x1802de282  call    cs:__imp_?MsoWzFileNameInPath@@YAPEB_WPEB_W@Z; MsoWzFileNameInPath(wchar_t const *)
0x1802de288  mov     [rbp+670h+var_3A8], 104h
0x1802de293  mov     [rbp+670h+var_3C0], r12
0x1802de29a  lea     rcx, [rbp+670h+var_3A0]
0x1802de2a1  mov     [rbp+670h+var_3B8], rcx
0x1802de2a8  mov     [rbp+670h+var_3B0], 104h
0x1802de2b2  lea     rdx, [rbp+670h+var_3C0]
0x1802de2b9  mov     rcx, rax
0x1802de2bc  call    ?CopyWzToWtz@Strings@MsoCF@@YAXPEB_WAEAV?$CWtzInBuffer_Template@V?$CBuffer@_W@MsoCF@@@2@@Z; MsoCF::Strings::CopyWzToWtz(wchar_t const *,MsoCF::CWtzInBuffer_Template<MsoCF::CBuffer<wchar_t>> &)
0x1802de2c1  mov     rcx, [rbp+670h+var_618]
0x1802de2c5  movzx   edx, word ptr [rcx]
0x1802de2c8  mov     r8, [rbp+670h+var_3B8]
0x1802de2cf  movzx   r9d, word ptr [r8]
0x1802de2d3  cmp     r9d, edx
0x1802de2d6  cmovnb  r9d, edx
0x1802de2da  add     r8, 2
0x1802de2de  add     rcx, 2
0x1802de2e2  mov     dword ptr [rsp+770h+var_750], 1
0x1802de2ea  call    cs:__imp_MsoFRgwchEqual
0x1802de2f0  test    eax, eax
0x1802de2f2  jnz     short loc_1802DE316
0x1802de2f4  lea     rax, [rbp+670h+var_3A0]
0x1802de2fb  mov     rcx, [rbp+670h+var_3B8]
0x1802de302  cmp     rcx, rax
0x1802de305  jz      loc_1802DE23C
0x1802de30b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1802de311  jmp     loc_1802DE23C
0x1802de316  mov     rax, [rbp+670h+var_618]
0x1802de31a  movzx   ecx, word ptr [rax]
0x1802de31d  mov     rdx, [rbp+670h+var_3B8]
0x1802de324  inc     rcx
0x1802de327  lea     r15, [rdx+rcx*2]
0x1802de32b  mov     rcx, [rbp+670h+var_4E8]
0x1802de332  movzx   r8d, word ptr [rcx]
0x1802de336  movzx   edi, word ptr [rdx]
0x1802de339  sub     rdi, r8
0x1802de33c  inc     rdi
0x1802de33f  lea     rdi, [rdx+rdi*2]
0x1802de343  cmp     rdi, r15
0x1802de346  jb      loc_1802DE3E2
0x1802de34c  mov     edx, r8d
0x1802de34f  add     rcx, 2
0x1802de353  mov     dword ptr [rsp+770h+var_750], 1
0x1802de35b  mov     r9d, r8d
0x1802de35e  mov     r8, rdi
0x1802de361  call    cs:__imp_MsoFRgwchEqual
0x1802de367  xor     ecx, ecx
0x1802de369  test    eax, eax
0x1802de36b  jz      short loc_1802DE3DB
0x1802de36d  xorps   xmm0, xmm0
0x1802de370  movups  xmmword ptr [rsp+770h+Src.Data4], xmm0
0x1802de375  movdqu  [rsp+770h+var_708+8], xmm6
0x1802de37b  mov     word ptr [rsp+770h+Src.Data4], cx
0x1802de380  sub     rdi, r15
0x1802de383  sar     rdi, 1
0x1802de386  mov     r8, rdi
0x1802de389  mov     rdx, r15; Src
0x1802de38c  lea     rcx, [rsp+770h+Src.Data4]; void *
0x1802de391  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x1802de396  xor     r15d, r15d
0x1802de399  mov     dword ptr [rsp+770h+var_730], r15d
0x1802de39e  lea     rcx, [rsp+770h+Src.Data4]
0x1802de3a3  cmp     [rsp+770h+var_6F8], 7
0x1802de3a9  cmova   rcx, qword ptr [rsp+770h+Src.Data4]
0x1802de3af  lea     rdx, [rsp+770h+var_730]
0x1802de3b4  call    cs:__imp_MsoParseUIntWz
0x1802de3ba  test    eax, eax
0x1802de3bc  jz      short loc_1802DE3CC
0x1802de3be  mov     eax, dword ptr [rsp+770h+var_730]
0x1802de3c2  cmp     r13d, eax
0x1802de3c5  cmova   eax, r13d
0x1802de3c9  mov     r13d, eax
0x1802de3cc  lea     rcx, [rsp+770h+Src.Data4]; void *
0x1802de3d1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802de3d6  jmp     loc_1802DE2F4
0x1802de3db  mov     rdx, [rbp+670h+var_3B8]
0x1802de3e2  lea     rax, [rbp+670h+var_3A0]
0x1802de3e9  cmp     rdx, rax
0x1802de3ec  mov     r15d, 0
0x1802de3f2  jz      loc_1802DE23C
0x1802de3f8  mov     rcx, rdx
0x1802de3fb  jmp     loc_1802DE30B
0x1802de400  xorps   xmm0, xmm0
0x1802de403  movups  xmmword ptr [rsp+770h+Src.Data4], xmm0
0x1802de408  movdqu  [rsp+770h+var_708+8], xmm6
0x1802de40e  mov     word ptr [rsp+770h+Src.Data4], r15w
0x1802de414  lea     rax, off_1815167C8
0x1802de41b  mov     qword ptr [rbp+670h+var_690], rax
0x1802de41f  lea     rax, [rbp+670h+var_678]
0x1802de423  mov     [rbp+670h+var_688], rax
0x1802de427  mov     [rbp+670h+var_680], 32h ; '2'
0x1802de42e  lea     edx, [r13+1]
0x1802de432  xor     r9d, r9d
0x1802de435  lea     r8d, [r9+0Ah]
0x1802de439  lea     rcx, [rbp+670h+var_690]; int
0x1802de43d  call    ?SetWzFromNumber@Strings@MsoCF@@YAXAEAV?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CBuffer@_W@2@@2@IHHPEAH@Z; MsoCF::Strings::SetWzFromNumber(MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CBuffer<wchar_t>> &,uint,int,int,int *)
0x1802de442  mov     [rsp+770h+var_730], rbx
0x1802de447  lea     r8, [rbp+670h+var_690]
0x1802de44b  lea     rdx, [rsp+770h+var_730]
0x1802de450  lea     rcx, [rbp+670h+var_6B0]
0x1802de454  call    ??$StringFromPattern@PEB_WV?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFixedBuffer@_W$0BJ@@2@@MsoCF@@@MsoCF@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBQEB_WAEBV?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFixedBuffer@_W$0BJ@@2@@0@@Z; MsoCF::StringFromPattern<wchar_t const *,MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFixedBuffer<wchar_t,25>>>(wchar_t const * const &,MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFixedBuffer<wchar_t,25>> const &)
0x1802de459  mov     rdx, rax
0x1802de45c  lea     rcx, [rsp+770h+Src.Data4]
0x1802de461  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1802de466  lea     rcx, [rbp+670h+var_6B0]; void *
0x1802de46a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802de46f  lea     rcx, [rsp+770h+Src.Data4]
0x1802de474  cmp     [rsp+770h+var_6F8], 7
0x1802de47a  cmova   rcx, qword ptr [rsp+770h+Src.Data4]; this
0x1802de480  xor     r8d, r8d; bool
0x1802de483  mov     r12b, byte ptr [rbp+670h+arg_20]
0x1802de48a  mov     dl, r12b; wchar_t *
0x1802de48d  call    ?ThrowOnInvalidFilename@Jot@@YAXPEB_W_N1@Z; Jot::ThrowOnInvalidFilename(wchar_t const *,bool,bool)
0x1802de492  mov     rdx, rsi; Src
0x1802de495  mov     rcx, r14; void *
0x1802de498  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1802de49d  mov     r8d, 104h
0x1802de4a3  mov     rdx, r14
0x1802de4a6  lea     rcx, [rsp+770h+var_730]
0x1802de4ab  call    ??0?$basic_strbuffer@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Jot@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; Jot::basic_strbuffer<std::wstring>::basic_strbuffer<std::wstring>(std::wstring &,unsigned __int64)
0x1802de4b0  xor     edx, edx
0x1802de4b2  mov     rcx, [rax]
0x1802de4b5  call    ??A?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEA_W_K@Z; std::wstring::operator[](unsigned __int64)
0x1802de4ba  lea     rcx, [rsp+770h+Src.Data4]
0x1802de4bf  cmp     [rsp+770h+var_6F8], 7
0x1802de4c5  cmova   rcx, qword ptr [rsp+770h+Src.Data4]
0x1802de4cb  mov     r8d, 104h
0x1802de4d1  mov     rdx, rax
0x1802de4d4  call    cs:__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z; MsoAppendToPath(wchar_t const *,wchar_t *,int)
0x1802de4da  lea     rcx, [rsp+770h+var_730]
0x1802de4df  call    ??1?$basic_strbuffer@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Jot@@QEAA@XZ; Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(void)
0x1802de4e4  mov     dil, [rbp+670h+arg_28]
0x1802de4eb  xor     dil, 1
0x1802de4ef  mov     rcx, r14
0x1802de4f2  cmp     qword ptr [r14+18h], 7
0x1802de4f7  jbe     short loc_1802DE4FC
0x1802de4f9  mov     rcx, [r14]; this
0x1802de4fc  mov     r8b, dil; bool
0x1802de4ff  mov     dl, r12b; wchar_t *
0x1802de502  call    ?CreateFileOrDirectory@Jot@@YAKPEB_W_N1@Z; Jot::CreateFileOrDirectory(wchar_t const *,bool,bool)
0x1802de507  test    eax, eax
  ... truncated ...
```
