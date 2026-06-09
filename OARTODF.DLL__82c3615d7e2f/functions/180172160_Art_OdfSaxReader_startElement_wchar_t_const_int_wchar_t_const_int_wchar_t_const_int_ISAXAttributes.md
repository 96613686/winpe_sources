# Art::OdfSaxReader::startElement(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ISAXAttributes *)

- ea: `0x180172160`
- end: `0x1801725a9`
- name: `?startElement@OdfSaxReader@Art@@UEAAJPEB_WH0H0HPEAUISAXAttributes@@@Z`
- size: `1097`
- prototype: `__int64 __fastcall(Art::OdfSaxReader *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int, struct ISAXAttributes *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callees

- `0x1800047e8`
- `0x180004950`
- `0x180004e20`
- `0x180004fb0`
- `0x180005394`
- `0x18000aa44`
- `0x180171790`
- `0x180172160`
- `0x1801a80e0`

## import_xrefs

- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x1801722af`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x1801722af`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801721da`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801723b0`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x180172440`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801721da`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801723b0`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x180172440`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801721eb`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801723c1`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x180172451`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801721eb`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801723c1`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x180172451`
- `mso40uiWin32Client!__imp_??0CXmlName@Ofc@@QEAA@PEB_WH0H0H@Z` at `0x1801721cd`
- `mso40uiWin32Client!__imp_??0CXmlName@Ofc@@QEAA@PEB_WH0H0H@Z` at `0x1801721cd`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x180172211`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801723e6`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801724aa`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x180172211`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801723e6`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801724aa`
- `mso40uiWin32Client!__imp_?startElement@CSAXReader@Ofc@@MEAAJPEB_WH0H0HPEAUISAXAttributes@@@Z` at `0x180172511`
- `mso40uiWin32Client!__imp_?startElement@CSAXReader@Ofc@@MEAAJPEB_WH0H0HPEAUISAXAttributes@@@Z` at `0x18017258a`
- `mso40uiWin32Client!__imp_?startElement@CSAXReader@Ofc@@MEAAJPEB_WH0H0HPEAUISAXAttributes@@@Z` at `0x180172511`
- `mso40uiWin32Client!__imp_?startElement@CSAXReader@Ofc@@MEAAJPEB_WH0H0HPEAUISAXAttributes@@@Z` at `0x18017258a`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x18017225b`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x180172294`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x18017225b`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x180172294`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18017251c`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18017251c`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180172527`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180172527`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Art::OdfSaxReader::startElement(
        struct Ofc::CProxyPtrImpl **this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        const wchar_t *a6,
        int a7,
        struct ISAXAttributes *a8)
{
  char v10; // r12
  unsigned int v11; // r13d
  void *Checked; // rax
  int v13; // ebx
  Art::FeatureGates *v14; // rcx
  char v15; // al
  char v16; // al
  Ofc::CListImpl *v17; // rsi
  struct Ofc::CProxyPtrImpl *v18; // rcx
  __int64 v19; // rcx
  __int64 *v20; // rbx
  __int64 v21; // rbx
  __int64 result; // rax
  int v23; // r15d
  __int64 v24; // rax
  int v25; // eax
  void *const *ItemAddr; // rax
  void *v27; // rax
  _WORD *v28; // r15
  unsigned int v29; // edx
  bool v30; // al
  _QWORD *v31; // r9
  _QWORD *v32; // rax
  _QWORD *v33; // rax
  void *v34; // r10
  unsigned int v35; // r12d
  int v36; // r15d
  unsigned int v37; // r8d
  struct Ofc::CProxyPtrImpl *v38; // rax
  void *v39; // rbx
  int v40; // [rsp+30h] [rbp-A8h]
  _DWORD *v41; // [rsp+50h] [rbp-88h] BYREF
  int v42; // [rsp+58h] [rbp-80h]
  __int64 v43; // [rsp+60h] [rbp-78h]
  int v44; // [rsp+68h] [rbp-70h]
  int v45; // [rsp+6Ch] [rbp-6Ch]
  _BYTE v46[32]; // [rsp+70h] [rbp-68h] BYREF
  int v47; // [rsp+90h] [rbp-48h]
  struct Ofc::CProxyPtrImpl *v48; // [rsp+E0h] [rbp+8h] BYREF
  const wchar_t *v49; // [rsp+E8h] [rbp+10h]
  unsigned int v50; // [rsp+F0h] [rbp+18h]

  v50 = a3;
  v49 = a2;
  try
  {
    v10 = 0;
    if ( *((_BYTE *)this + 272) || !*((_QWORD *)this[29] + 2) )
    {
      Ofc::CSAXReader::startElement((Ofc::CSAXReader *)this, a2, a3, a4, a5, a6, a7, a8);
      return 0;
    }
    v11 = a5;
    Ofc::CXmlName::CXmlName((Ofc::CXmlName *)v46, a2, a3, a4, a5, a6, a7);
    v48 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(this[28]);
    Checked = Ofc::CProxyPtrImpl::GetChecked(v48);
    v13 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)Checked + 424LL))(Checked);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v48);
    if ( v13 && v47 != 307 && v47 != 318
      || v47 == 321
      && (!a4
        ? (v15 = sub_18000AA44(0, v11, (unsigned int)L"p", 1, 0))
        : (v15 = (unsigned int)MsoFRgwchEqual(a4, v11, L"p", 1, 4) != 0),
          v15
       || (!a4
         ? (v16 = sub_18000AA44(0, v11, (unsigned int)L"list", 4, 0))
         : (v16 = (unsigned int)MsoFRgwchEqual(a4, v11, L"list", 4, 4) != 0),
           v16))
      || Art::FeatureGates::FUsingODF_1_4(v14) && v47 == 320 )
    {
      v17 = (Ofc::CListImpl *)(this + 26);
      v18 = this[26];
      if ( v18 )
        v19 = *((_QWORD *)v18 + 1);
      else
        v19 = 0;
      if ( v19 )
        v20 = (__int64 *)(v19 + 8 * ((unsigned int)(*(_DWORD *)(v19 + 16) - 1) + 3LL));
      else
        v20 = 0;
      if ( v20 )
        v21 = *v20;
      else
        v21 = 0;
      if ( !v21 )
        return 0;
      if ( !*(_BYTE *)(v21 + 8) )
      {
        v23 = 0;
        Ofc::CListIterImpl::CListIterImpl((Ofc::CListIterImpl *)&v41, (const struct Ofc::CListImpl *)(this + 26));
        v45 = v41[3];
        if ( *(_QWORD *)v41 )
          v24 = *(_QWORD *)(*(_QWORD *)v41 + 8LL);
        else
          v24 = 0;
        v43 = v24;
        if ( v24 )
          v25 = *(_DWORD *)(v24 + 16);
        else
          v25 = 0;
        v44 = v25;
        if ( v25 )
          v44 = v25 - 1;
        Ofc::CListIterImpl::UpdateCurrItem((Ofc::CListIterImpl *)&v41);
        while ( 1 )
        {
          ItemAddr = Ofc::CListIterImpl::PrevItemAddr((Ofc::CListIterImpl *)&v41);
          if ( !ItemAddr )
            break;
          if ( *((_BYTE *)*ItemAddr + 9) )
          {
            if ( (unsigned int)++v23 > 1 )
              goto LABEL_56;
          }
        }
        if ( !*(_BYTE *)(v21 + 10) )
        {
          v10 = 1;
          v48 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(this[28]);
          v27 = Ofc::CProxyPtrImpl::GetChecked(v48);
          (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 184LL))(v27);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v48);
        }
        v28 = *(_WORD **)v21;
        if ( !**(_WORD **)v21 )
        {
          v29 = *((_DWORD *)this + 54);
          if ( v29 >= 2 )
          {
            v41 = 0;
            v42 = 0;
            v43 = 0;
            v30 = Ofc::CListImpl::FGetItemPos((Ofc::CListImpl *)(this + 26), v29 - 2, (struct Ofc::CListPos *)&v41);
            v32 = (_QWORD *)(v43 & -(__int64)v30);
            if ( v32 )
              v33 = (_QWORD *)*v32;
            else
              v33 = v31;
            v28 = (_WORD *)*v33;
          }
        }
        v48 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(this[29]);
        v34 = Ofc::CProxyPtrImpl::GetChecked(v48);
        LOBYTE(v40) = v10;
        v35 = v50;
        v36 = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD, const wchar_t *, unsigned int, struct ISAXAttributes *, int, _WORD *))(*(_QWORD *)v34 + 368LL))(
                v34,
                v49,
                v50,
                a4,
                v11,
                a8,
                v40,
                v28);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v48);
        if ( v36 >= 0 )
        {
          if ( !*(_BYTE *)(v21 + 10) )
            *(_BYTE *)(v21 + 10) = 1;
          return (unsigned int)v36;
        }
        goto LABEL_57;
      }
    }
    else
    {
      v17 = (Ofc::CListImpl *)(this + 26);
    }
LABEL_56:
    v35 = v50;
LABEL_57:
    Ofc::CSAXReader::startElement((Ofc::CSAXReader *)this, v49, v35, a4, v11, a6, a7, a8);
    v38 = (struct Ofc::CProxyPtrImpl *)Mso::Memory::AllocateEx((Mso::Memory *)0x10, 0, v37);
    if ( !v38 )
      ThrowOOM();
    v48 = v38;
    v39 = (void *)Art::XmlParentForAppContent::XmlParentForAppContent(v38, a8, (const struct Ofc::CXmlName *)v46);
    *Ofc::CListImpl::NewTail(v17) = v39;
    return 0;
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180172160  mov     [rsp+arg_10], r8d
0x180172165  mov     [rsp+arg_8], rdx
0x18017216a  push    rbx
0x18017216b  push    rsi
0x18017216c  push    rdi
0x18017216d  push    r12
0x18017216f  push    r13
0x180172171  push    r14
0x180172173  push    r15
0x180172175  sub     rsp, 0A0h
0x18017217c  mov     r14, r9
0x18017217f  mov     rdi, rcx
0x180172182  xor     r12d, r12d
0x180172185  cmp     [rcx+110h], r12b
0x18017218c  jnz     loc_18017255A
0x180172192  mov     rax, [rcx+0E8h]
0x180172199  cmp     [rax+10h], r12
0x18017219d  jz      loc_18017255A
0x1801721a3  mov     eax, [rsp+0D8h+arg_30]
0x1801721aa  mov     [rsp+0D8h+var_A8], eax
0x1801721ae  mov     rax, [rsp+0D8h+arg_28]
0x1801721b6  mov     [rsp+0D8h+var_B0], rax
0x1801721bb  mov     r13d, [rsp+0D8h+arg_20]
0x1801721c3  mov     [rsp+0D8h+var_B8], r13d
0x1801721c8  lea     rcx, [rsp+0D8h+var_68]
0x1801721cd  call    cs:__imp_??0CXmlName@Ofc@@QEAA@PEB_WH0H0H@Z; Ofc::CXmlName::CXmlName(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)
0x1801721d3  mov     rcx, [rdi+0E0h]
0x1801721da  call    cs:__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1801721e0  mov     [rsp+0D8h+arg_0], rax
0x1801721e8  mov     rcx, rax
0x1801721eb  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1801721f1  mov     rdx, rax
0x1801721f4  mov     rcx, [rax]
0x1801721f7  mov     rax, [rcx+1A8h]
0x1801721fe  mov     rcx, rdx
0x180172201  call    cs:__guard_dispatch_icall_fptr
0x180172207  mov     ebx, eax
0x180172209  lea     rcx, [rsp+0D8h+arg_0]
0x180172211  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180172217  mov     eax, [rsp+0D8h+var_48]
0x18017221e  test    ebx, ebx
0x180172220  jz      short loc_180172234
0x180172222  cmp     eax, 133h
0x180172227  jz      short loc_180172234
0x180172229  cmp     eax, 13Eh
0x18017222e  jnz     loc_1801722CE
0x180172234  cmp     eax, 141h
0x180172239  jnz     short loc_1801722AF
0x18017223b  mov     r9d, 1
0x180172241  lea     r8, aP; "p"
0x180172248  mov     edx, r13d
0x18017224b  mov     rcx, r14
0x18017224e  test    r14, r14
0x180172251  jz      short loc_180172268
0x180172253  lea     ebx, [r9+3]
0x180172257  mov     [rsp+0D8h+var_B8], ebx
0x18017225b  call    cs:__imp_MsoFRgwchEqual
0x180172261  test    eax, eax
0x180172263  setnz   al
0x180172266  jmp     short loc_180172277
0x180172268  mov     byte ptr [rsp+0D8h+var_B8], r12b
0x18017226d  call    sub_18000AA44
0x180172272  mov     ebx, 4
0x180172277  test    al, al
0x180172279  jnz     short loc_1801722CE
0x18017227b  mov     r9d, ebx
0x18017227e  lea     r8, aList; "list"
0x180172285  mov     edx, r13d
0x180172288  mov     rcx, r14
0x18017228b  test    r14, r14
0x18017228e  jz      short loc_1801722A1
0x180172290  mov     [rsp+0D8h+var_B8], ebx
0x180172294  call    cs:__imp_MsoFRgwchEqual
0x18017229a  test    eax, eax
0x18017229c  setnz   al
0x18017229f  jmp     short loc_1801722AB
0x1801722a1  mov     byte ptr [rsp+0D8h+var_B8], r12b
0x1801722a6  call    sub_18000AA44
0x1801722ab  test    al, al
0x1801722ad  jnz     short loc_1801722CE
0x1801722af  call    cs:__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FUsingODF_1_4(void)
0x1801722b5  test    al, al
0x1801722b7  jz      loc_1801724C7
0x1801722bd  cmp     [rsp+0D8h+var_48], 140h
0x1801722c8  jnz     loc_1801724C7
0x1801722ce  lea     rsi, [rdi+0D0h]
0x1801722d5  mov     rcx, [rsi]
0x1801722d8  test    rcx, rcx
0x1801722db  jz      short loc_1801722E3
0x1801722dd  mov     rcx, [rcx+8]
0x1801722e1  jmp     short loc_1801722E6
0x1801722e3  mov     rcx, r12
0x1801722e6  test    rcx, rcx
0x1801722e9  jz      short loc_1801722FA
0x1801722eb  mov     ebx, [rcx+10h]
0x1801722ee  dec     ebx
0x1801722f0  add     rbx, 3
0x1801722f4  lea     rbx, [rcx+rbx*8]
0x1801722f8  jmp     short loc_1801722FD
0x1801722fa  mov     rbx, r12
0x1801722fd  test    rbx, rbx
0x180172300  jz      short loc_180172307
0x180172302  mov     rbx, [rbx]
0x180172305  jmp     short loc_18017230A
0x180172307  mov     rbx, r12
0x18017230a  test    rbx, rbx
0x18017230d  jnz     short loc_180172316
0x18017230f  xor     eax, eax
0x180172311  jmp     loc_180172596
0x180172316  cmp     [rbx+8], r12b
0x18017231a  jnz     loc_1801724CE
0x180172320  mov     r15d, r12d
0x180172323  mov     rdx, rsi; struct Ofc::CListImpl *
0x180172326  lea     rcx, [rsp+0D8h+var_88]; this
0x18017232b  call    ??0CListIterImpl@Ofc@@IEAA@AEBVCListImpl@1@@Z; Ofc::CListIterImpl::CListIterImpl(Ofc::CListImpl const &)
0x180172330  mov     rcx, [rsp+0D8h+var_88]
0x180172335  mov     eax, [rcx+0Ch]
0x180172338  mov     [rsp+0D8h+var_6C], eax
0x18017233c  mov     rax, [rcx]
0x18017233f  test    rax, rax
0x180172342  jz      short loc_18017234A
0x180172344  mov     rax, [rax+8]
0x180172348  jmp     short loc_18017234D
0x18017234a  mov     rax, r12
0x18017234d  mov     [rsp+0D8h+var_78], rax
0x180172352  test    rax, rax
0x180172355  jz      short loc_18017235C
0x180172357  mov     eax, [rax+10h]
0x18017235a  jmp     short loc_18017235F
0x18017235c  mov     eax, r12d
0x18017235f  mov     [rsp+0D8h+var_70], eax
0x180172363  test    eax, eax
0x180172365  jz      short loc_18017236D
0x180172367  dec     eax
0x180172369  mov     [rsp+0D8h+var_70], eax
0x18017236d  lea     rcx, [rsp+0D8h+var_88]; this
0x180172372  call    ?UpdateCurrItem@CListIterImpl@Ofc@@AEBAXXZ; Ofc::CListIterImpl::UpdateCurrItem(void)
0x180172377  lea     rcx, [rsp+0D8h+var_88]; this
0x18017237c  call    ?PrevItemAddr@CListIterImpl@Ofc@@IEAAPEBQEAXXZ; Ofc::CListIterImpl::PrevItemAddr(void)
0x180172381  test    rax, rax
0x180172384  jz      short loc_18017239D
0x180172386  mov     rax, [rax]
0x180172389  cmp     [rax+9], r12b
0x18017238d  jz      short loc_180172377
0x18017238f  inc     r15d
0x180172392  cmp     r15d, 1
0x180172396  jbe     short loc_180172377
0x180172398  jmp     loc_1801724CE
0x18017239d  xor     r9d, r9d
0x1801723a0  cmp     [rbx+0Ah], r9b
0x1801723a4  jnz     short loc_1801723EF
0x1801723a6  mov     r12b, 1
0x1801723a9  mov     rcx, [rdi+0E0h]
0x1801723b0  call    cs:__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1801723b6  mov     [rsp+0D8h+arg_0], rax
0x1801723be  mov     rcx, rax
0x1801723c1  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1801723c7  mov     rdx, rax
0x1801723ca  mov     rcx, [rax]
0x1801723cd  mov     rax, [rcx+0B8h]
0x1801723d4  mov     rcx, rdx
0x1801723d7  call    cs:__guard_dispatch_icall_fptr
0x1801723dd  nop
0x1801723de  lea     rcx, [rsp+0D8h+arg_0]
0x1801723e6  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1801723ec  xor     r9d, r9d
0x1801723ef  mov     r15, [rbx]
0x1801723f2  cmp     [r15], r9w
0x1801723f6  jnz     short loc_180172439
0x1801723f8  mov     edx, [rdi+0D8h]
0x1801723fe  cmp     edx, 2
0x180172401  jb      short loc_180172439
0x180172403  mov     [rsp+0D8h+var_88], r9
0x180172408  mov     [rsp+0D8h+var_80], r9d
0x18017240d  mov     [rsp+0D8h+var_78], r9
0x180172412  add     edx, 0FFFFFFFEh; unsigned int
0x180172415  lea     r8, [rsp+0D8h+var_88]; struct Ofc::CListPos *
0x18017241a  mov     rcx, rsi; this
0x18017241d  call    ?FGetItemPos@CListImpl@Ofc@@IEBA_NKAEAUCListPos@2@@Z; Ofc::CListImpl::FGetItemPos(ulong,Ofc::CListPos &)
0x180172422  neg     al
0x180172424  sbb     rax, rax
0x180172427  and     rax, [rsp+0D8h+var_78]
0x18017242c  jz      short loc_180172433
0x18017242e  mov     rax, [rax]
0x180172431  jmp     short loc_180172436
0x180172433  mov     rax, r9
0x180172436  mov     r15, [rax]
0x180172439  mov     rcx, [rdi+0E8h]
0x180172440  call    cs:__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180172446  mov     [rsp+0D8h+arg_0], rax
0x18017244e  mov     rcx, rax
0x180172451  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180172457  mov     r10, rax
0x18017245a  mov     rcx, [rax]
0x18017245d  mov     rax, [rcx+170h]
0x180172464  mov     [rsp+0D8h+var_A0], r15
0x180172469  mov     byte ptr [rsp+0D8h+var_A8], r12b
0x18017246e  mov     rcx, [rsp+0D8h+arg_38]
0x180172476  mov     [rsp+0D8h+var_B0], rcx
0x18017247b  mov     [rsp+0D8h+var_B8], r13d
0x180172480  mov     r9, r14
0x180172483  mov     r12d, [rsp+0D8h+arg_10]
0x18017248b  mov     r8d, r12d
0x18017248e  mov     rdx, [rsp+0D8h+arg_8]
0x180172496  mov     rcx, r10
0x180172499  call    cs:__guard_dispatch_icall_fptr
0x18017249f  mov     r15d, eax
0x1801724a2  lea     rcx, [rsp+0D8h+arg_0]
0x1801724aa  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1801724b0  test    r15d, r15d
0x1801724b3  js      short loc_1801724D6
0x1801724b5  cmp     byte ptr [rbx+0Ah], 0
0x1801724b9  jnz     short loc_1801724BF
0x1801724bb  mov     byte ptr [rbx+0Ah], 1
0x1801724bf  mov     eax, r15d
0x1801724c2  jmp     loc_180172596
0x1801724c7  lea     rsi, [rdi+0D0h]
0x1801724ce  mov     r12d, [rsp+0D8h+arg_10]
0x1801724d6  mov     rax, [rsp+0D8h+arg_38]
0x1801724de  mov     [rsp+0D8h+var_A0], rax
0x1801724e3  mov     eax, [rsp+0D8h+arg_30]
0x1801724ea  mov     [rsp+0D8h+var_A8], eax
0x1801724ee  mov     rax, [rsp+0D8h+arg_28]
0x1801724f6  mov     [rsp+0D8h+var_B0], rax
0x1801724fb  mov     [rsp+0D8h+var_B8], r13d
0x180172500  mov     r9, r14
0x180172503  mov     r8d, r12d
0x180172506  mov     rdx, [rsp+0D8h+arg_8]
0x18017250e  mov     rcx, rdi
0x180172511  call    cs:__imp_?startElement@CSAXReader@Ofc@@MEAAJPEB_WH0H0HPEAUISAXAttributes@@@Z; Ofc::CSAXReader::startElement(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ISAXAttributes *)
0x180172517  xor     edx, edx
0x180172519  lea     ecx, [rdx+10h]
0x18017251c  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180172522  test    rax, rax
0x180172525  jnz     short loc_18017252D
0x180172527  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x18017252d  mov     [rsp+0D8h+arg_0], rax
0x180172535  lea     r8, [rsp+0D8h+var_68]; struct Ofc::CXmlName *
0x18017253a  mov     rdx, [rsp+0D8h+arg_38]; struct ISAXAttributes *
0x180172542  mov     rcx, rax; this
0x180172545  call    ??0XmlParentForAppContent@Art@@QEAA@PEAUISAXAttributes@@AEBUCXmlName@Ofc@@@Z; Art::XmlParentForAppContent::XmlParentForAppContent(ISAXAttributes *,Ofc::CXmlName const &)
0x18017254a  mov     rbx, rax
0x18017254d  mov     rcx, rsi; this
0x180172550  call    ?NewTail@CListImpl@Ofc@@IEAAPEAPEAXXZ; Ofc::CListImpl::NewTail(void)
0x180172555  mov     [rax], rbx
0x180172558  jmp     short loc_180172590
0x18017255a  mov     rax, [rsp+0D8h+arg_38]
0x180172562  mov     [rsp+0D8h+var_A0], rax
0x180172567  mov     eax, [rsp+0D8h+arg_30]
0x18017256e  mov     [rsp+0D8h+var_A8], eax
0x180172572  mov     rax, [rsp+0D8h+arg_28]
0x18017257a  mov     [rsp+0D8h+var_B0], rax
0x18017257f  mov     eax, [rsp+0D8h+arg_20]
0x180172586  mov     [rsp+0D8h+var_B8], eax
0x18017258a  call    cs:__imp_?startElement@CSAXReader@Ofc@@MEAAJPEB_WH0H0HPEAUISAXAttributes@@@Z; Ofc::CSAXReader::startElement(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ISAXAttributes *)
0x180172590  xor     eax, eax
0x180172592  jmp     short loc_180172596
0x180172594  xor     eax, eax
0x180172596  add     rsp, 0A0h
0x18017259d  pop     r15
0x18017259f  pop     r14
0x1801725a1  pop     r13
0x1801725a3  pop     r12
0x1801725a5  pop     rdi
0x1801725a6  pop     rsi
0x1801725a7  pop     rbx
0x1801725a8  retn
```
