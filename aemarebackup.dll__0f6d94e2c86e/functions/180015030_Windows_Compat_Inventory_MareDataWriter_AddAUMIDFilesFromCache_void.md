# Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache(void)

- ea: `0x180015030`
- end: `0x180015839`
- name: `?AddAUMIDFilesFromCache@MareDataWriter@Inventory@Compat@Windows@@AEAAJXZ`
- size: `2057`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::MareDataWriter *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800172a0`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x180006cec`
- `0x18000f174`
- `0x18000fb60`
- `0x18000fc14`
- `0x1800105bc`
- `0x180010f58`
- `0x180011fcc`
- `0x18001338c`
- `0x1800134b8`
- `0x18001459c`
- `0x180014a48`
- `0x180015030`
- `0x18001767c`
- `0x18001b554`
- `0x18001b710`
- `0x18001bb7c`
- `0x18001d840`
- `0x18001efb4`
- `0x1800277cc`
- `0x18002d73c`
- `0x18002e66c`
- `0x18002e7ac`
- `0x18002e824`
- `0x18003580c`
- `0x180035b98`
- `0x180036834`
- `0x180042980`
- `0x180044a98`
- `0x180044b1c`
- `0x18004c020`
- `0x1800e683c`

## string_xrefs

- `0x1800151b0`: `%ls has %d items in cache`
- `0x18001520f`: `TelCacheProvider::GetNextItem failed [%#x]`
- `0x1800157db`: `TelCacheProvider::GetNextItem failed [%#x]`
- `0x18001515f`: `Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache`
- `0x1800151bd`: `Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache`
- `0x180015275`: `empty linkPath [%#x]`
- `0x18001529f`: `empty targetPath [%#x]`
- `0x180015325`: `ComputeFileCacheKey failed [%#x]`
- `0x180015393`: `File "%ls" not in cache`
- `0x1800153ab`: `TelCacheProvider::GetItem failed [%#x]`
- `0x180015184`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x18001514e`: `TelCacheProvider::Initialize failed [%#x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache(
        Windows::Compat::Inventory::MareDataWriter *this)
{
  unsigned int v2; // r15d
  _QWORD *v3; // rax
  AmiShortcutItem *v4; // rax
  const wchar_t *v5; // rdi
  __int64 *v6; // rdx
  int ItemCount; // eax
  int FirstItem; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  unsigned int v12; // edx
  const char *v13; // r9
  __int64 v14; // r8
  const wchar_t *v15; // rax
  const unsigned __int16 *v16; // r8
  int v17; // eax
  int Item; // eax
  unsigned __int16 **v19; // rax
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rbx
  const wchar_t *v24; // rcx
  const wchar_t *v25; // rcx
  unsigned __int16 **v26; // rcx
  __int64 v27; // rbx
  const wchar_t *v28; // rcx
  const wchar_t *v29; // rdx
  const wchar_t *v30; // rcx
  const wchar_t *v31; // rax
  wchar_t **v32; // rsi
  __int64 *v33; // r14
  __int64 v34; // r8
  __int64 v35; // rbx
  Windows::Compat::Inventory::MareApplication *v36; // rax
  const unsigned __int16 *v37; // r8
  Windows::Compat::Inventory::MareApplication *v38; // r14
  File *v39; // rsi
  unsigned __int16 **v40; // rdx
  __int64 v41; // r8
  int v42; // r15d
  struct File *v43; // rax
  const unsigned __int16 *v44; // rdx
  const unsigned __int16 *v45; // r8
  const unsigned __int16 *v46; // rdx
  const wchar_t *v47; // rax
  __int64 v49; // [rsp+20h] [rbp-E0h]
  unsigned int v50; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v51; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t **v52; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v53[4]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v55[16]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v56; // [rsp+98h] [rbp-68h]
  _BYTE v57[16]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v58[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v60; // [rsp+C8h] [rbp-38h]
  wchar_t *String1[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v62; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v63; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v64[3]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v65; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v66[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v67; // [rsp+120h] [rbp+20h]
  unsigned __int64 v68; // [rsp+128h] [rbp+28h]
  wchar_t *v69[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v70; // [rsp+140h] [rbp+40h]
  unsigned __int64 v71; // [rsp+148h] [rbp+48h]
  __int128 v72; // [rsp+150h] [rbp+50h] BYREF
  __int64 v73; // [rsp+160h] [rbp+60h]
  __int64 v74; // [rsp+168h] [rbp+68h]
  __int64 v75; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v76[80]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v77; // [rsp+1C8h] [rbp+C8h]
  __int16 v78; // [rsp+1D0h] [rbp+D0h]
  __int64 v79; // [rsp+1D8h] [rbp+D8h]
  __int128 v80; // [rsp+1E0h] [rbp+E0h]
  __int64 v81; // [rsp+1F0h] [rbp+F0h]
  int v82; // [rsp+1F8h] [rbp+F8h]
  char v83; // [rsp+1FCh] [rbp+FCh]
  _BYTE v84[8]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v85[64]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v86[32]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v87[32]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v88[40]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v89[8]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v90[80]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v91[728]; // [rsp+308h] [rbp+208h] BYREF
  unsigned __int16 v92[48]; // [rsp+5E0h] [rbp+4E0h] BYREF

  v2 = 0;
  LODWORD(v51) = 0;
  AmiShortcutItem::AmiShortcutItem((AmiShortcutItem *)v84);
  memset_0(v76, 0, 0x4Eu);
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v77 = 0;
  v75 = 0;
  v53[1] = 0;
  v3 = operator new(0x40u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  v53[0] = v3;
  v52 = (wchar_t **)operator new(0xA8u);
  v4 = AmiShortcutItem::AmiShortcutItem((AmiShortcutItem *)v52);
  v5 = (const wchar_t *)&AmiShortcutItem::ShortcutCacheProviderName;
  v6 = &AmiShortcutItem::ShortcutCacheProviderName;
  if ( (unsigned __int64)qword_18011BC28 > 7 )
    v6 = (__int64 *)AmiShortcutItem::ShortcutCacheProviderName;
  ItemCount = TelCacheProvider::Initialize(&v75, v6, v4, 0, 3, 3, 100);
  FirstItem = ItemCount;
  if ( ItemCount < 0 )
  {
    v9 = "TelCacheProvider::Initialize failed [%#x]";
    v10 = 357;
LABEL_5:
    LODWORD(v49) = ItemCount;
LABEL_104:
    AslLogCallPrintf(1, "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache", v10, v9, v49);
    goto LABEL_105;
  }
  v50 = 0;
  ItemCount = TelCacheProvider::GetItemCount((TelCacheProvider *)&v75, &v50);
  FirstItem = ItemCount;
  if ( ItemCount < 0 )
  {
    v9 = "TelCacheProvider::GetItemCount failed [%#x]";
    v10 = 365;
    goto LABEL_5;
  }
  if ( (unsigned __int64)qword_18011BC28 > 7 )
    v5 = (const wchar_t *)AmiShortcutItem::ShortcutCacheProviderName;
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache",
    370,
    "%ls has %d items in cache",
    v5,
    v50);
  FirstItem = TelCacheProvider::GetFirstItem((TelCacheProvider *)&v75, (struct IAmiInventoryItem *)v84);
  if ( FirstItem != -2147024637 )
  {
    while ( 1 )
    {
      if ( !v50-- )
        goto LABEL_101;
      if ( FirstItem >= 0 )
        break;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache",
        378,
        "TelCacheProvider::GetNextItem failed [%#x]",
        FirstItem);
LABEL_100:
      FirstItem = TelCacheProvider::GetNextItem((TelCacheProvider *)&v75, (struct IAmiInventoryItem *)v84);
      if ( FirstItem == -2147024637 )
        goto LABEL_101;
    }
    std::wstring::wstring(v66, v87);
    std::wstring::wstring(v58, v86);
    std::wstring::wstring(String1, v88);
    std::wstring::wstring(v64, v85);
    if ( v64[2] )
    {
      if ( v59 )
      {
        if ( v67 )
        {
          *(_OWORD *)v69 = 0;
          v70 = 0;
          v71 = 7;
          LOWORD(v69[0]) = 0;
          v16 = (const unsigned __int16 *)v58;
          if ( v60 > 7 )
            v16 = v58[0];
          v17 = ComputeFileCacheKey(v92, v12, v16);
          if ( v17 >= 0 )
          {
            File::File((File *)v89);
            File::SetItemKey((File *)v90, v92);
            Item = TelCacheProvider::GetItem(this, (struct IAmiInventoryItem *)v90, 0);
            if ( Item < 0 )
            {
              if ( (_WORD)Item == 2 )
              {
                v19 = v58;
                if ( v60 > 7 )
                  v19 = (unsigned __int16 **)v58[0];
                AslLogCallPrintf(
                  3,
                  "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache",
                  421,
                  "File \"%ls\" not in cache",
                  v19);
              }
              else
              {
                LODWORD(v49) = Item;
                AslLogCallPrintf(
                  1,
                  "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache",
                  425,
                  "TelCacheProvider::GetItem failed [%#x]",
                  v49);
              }
            }
            std::wstring::operator=(v69, v91);
            File::~File((File *)v89);
          }
          else
          {
            AslLogCallPrintf(
              1,
              "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache",
              410,
              "ComputeFileCacheKey failed [%#x]",
              v17);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CompatMareBackupAumidFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_CompatMareBackupAumidFix>::GetImpl'::`2'::impl) )
          {
            if ( v62 )
            {
              v20 = (const wchar_t *)String1;
              if ( v63 > 7 )
                v20 = String1[0];
              if ( wcscmp_0(v20, L"0000f519feec486de87ed73cb92d3cac802400000000") )
                goto LABEL_49;
            }
            std::wstring::operator=(String1, v69);
            if ( v62 )
            {
              v21 = (const wchar_t *)String1;
              if ( v63 > 7 )
                v21 = String1[0];
              if ( wcscmp_0(v21, L"0000f519feec486de87ed73cb92d3cac802400000000") )
                goto LABEL_60;
            }
            v22 = 441;
          }
          else
          {
            v23 = v62;
            if ( v62 )
            {
              v24 = (const wchar_t *)String1;
              if ( v63 > 7 )
                v24 = String1[0];
              if ( wcscmp_0(v24, L"0000f519feec486de87ed73cb92d3cac802400000000") && v23 == 45 )
              {
LABEL_49:
                v25 = (const wchar_t *)v69;
                if ( v71 > 7 )
                  v25 = v69[0];
                if ( !wcscmp_0(v25, L"0000f519feec486de87ed73cb92d3cac802400000000") )
                {
                  v59 = 0;
                  v26 = v58;
                  if ( v60 > 7 )
                    v26 = (unsigned __int16 **)v58[0];
                  *(_WORD *)v26 = 0;
                }
LABEL_60:
                v29 = (const wchar_t *)String1;
                if ( v63 > 7 )
                  v29 = String1[0];
                v30 = (const wchar_t *)v64;
                if ( v65 > 7 )
                  v30 = v64[0];
                v31 = (const wchar_t *)v66;
                if ( v68 > 7 )
                  v31 = v66[0];
                AslLogCallPrintf(
                  3,
                  "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache",
                  477,
                  "Adding %ls %ls to \"%ls\"",
                  v31,
                  v30,
                  v29);
                v32 = String1;
                if ( v63 > 7 )
                  v32 = (wchar_t **)String1[0];
                v52 = v32;
                v33 = (__int64 *)((char *)this + 288);
                v72 = 0;
                v73 = 0;
                v74 = 0;
                v34 = -1;
                do
                  ++v34;
                while ( *((_WORD *)v32 + v34) );
                std::wstring::_Construct<1,unsigned short const *>(&v72, v32);
                std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
                  (char *)this + 288,
                  v55,
                  &v72);
                v35 = v56;
                if ( *(_BYTE *)(v56 + 25) || (unsigned __int8)std::operator<<unsigned short>(&v72, v56 + 32) )
                  v35 = *v33;
                std::wstring::~wstring(&v72);
                if ( v35 == *v33 )
                {
                  if ( !v59 )
                  {
                    AslLogCallPrintf(
                      1,
                      "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache",
                      499,
                      "Found a non-orphan ProgramId without an app %ls [%#x]",
                      (const wchar_t *)v32,
                      -2147418113);
LABEL_92:
                    if ( v67 )
                      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring const &>(
                        v53,
                        v57,
                        v66);
                    std::wstring::~wstring(v69);
                    std::wstring::~wstring(v64);
                    std::wstring::~wstring(String1);
                    std::wstring::~wstring(v58);
                    std::wstring::~wstring(v66);
                    goto LABEL_100;
                  }
                  v36 = (Windows::Compat::Inventory::MareApplication *)operator new(0x110u);
                  v53[2] = v36;
                  v37 = (const unsigned __int16 *)v58;
                  if ( v60 > 7 )
                    v37 = v58[0];
                  v51 = Windows::Compat::Inventory::MareApplication::MareApplication(
                          v36,
                          (const unsigned __int16 *)v32,
                          v37);
                  std::_Tree<std::_Tmap_traits<std::wstring const,Windows::Compat::Inventory::MareApplication *,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Windows::Compat::Inventory::MareApplication *>>,0>>::emplace<unsigned short const * &,Windows::Compat::Inventory::MareApplication *>(
                    (char *)this + 288,
                    &v54,
                    &v52,
                    &v51);
                  v35 = v54;
                  v38 = *(Windows::Compat::Inventory::MareApplication **)(v54 + 64);
                  v39 = (File *)operator new(0x330u);
                  v53[3] = v39;
                  v40 = v58;
                  if ( v60 > 7 )
                    v40 = (unsigned __int16 **)v58[0];
                  v72 = 0;
                  v73 = 0;
                  v74 = 0;
                  v41 = -1;
                  do
                    ++v41;
                  while ( *((_WORD *)v40 + v41) );
                  std::wstring::_Construct<1,unsigned short const *>(&v72, v40);
                  v42 = v2 | 1;
                  LODWORD(v51) = v42;
                  v43 = (struct File *)File::File(v39);
                  Windows::Compat::Inventory::MareApplication::AddFile(v38, v43);
                  v2 = v42 & 0xFFFFFFFE;
                  std::wstring::~wstring(&v72);
                }
                else if ( v59 )
                {
                  v44 = (const unsigned __int16 *)v58;
                  if ( v60 > 7 )
                    v44 = v58[0];
                  Windows::Compat::Inventory::MareApplication::AddFile(
                    *(Windows::Compat::Inventory::MareApplication **)(v35 + 64),
                    v44);
                }
                v45 = (const unsigned __int16 *)v64;
                if ( v65 > 7 )
                  v45 = v64[0];
                v46 = (const unsigned __int16 *)v66;
                if ( v68 > 7 )
                  v46 = v66[0];
                Windows::Compat::Inventory::MareApplication::AddAumid(
                  *(Windows::Compat::Inventory::MareApplication **)(v35 + 64),
                  v46,
                  v45);
                goto LABEL_92;
              }
            }
            std::wstring::operator=(String1, v69);
            v27 = v62;
            if ( v62 )
            {
              v28 = (const wchar_t *)String1;
              if ( v63 > 7 )
                v28 = String1[0];
              if ( wcscmp_0(v28, L"0000f519feec486de87ed73cb92d3cac802400000000") && v27 == 45 )
                goto LABEL_60;
            }
            v22 = 463;
          }
          v47 = (const wchar_t *)v64;
          if ( v65 > 7 )
            v47 = v64[0];
          AslLogCallPrintf(
            3,
            "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache",
            v22,
            "No known, non-system programId for \"%ls\"",
            v47);
          std::wstring::~wstring(v69);
        }
        else
        {
          v15 = (const wchar_t *)v64;
          if ( v65 > 7 )
            v15 = v64[0];
          AslLogCallPrintf(
            1,
            "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache",
            400,
            "empty aumid for shortcut %ls [%#x]",
            v15,
            -2147418113);
        }
        goto LABEL_99;
      }
      v13 = "empty targetPath [%#x]";
      v14 = 394;
    }
    else
    {
      v13 = "empty linkPath [%#x]";
      v14 = 389;
    }
    LODWORD(v49) = -2147418113;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache", v14, v13, v49);
LABEL_99:
    std::wstring::~wstring(v64);
    std::wstring::~wstring(String1);
    std::wstring::~wstring(v58);
    std::wstring::~wstring(v66);
    goto LABEL_100;
  }
LABEL_101:
  if ( (_WORD)FirstItem != 259 )
  {
    LODWORD(v49) = FirstItem;
    v9 = "TelCacheProvider::GetNextItem failed [%#x]";
    v10 = 518;
    goto LABEL_104;
  }
  FirstItem = 0;
LABEL_105:
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v53);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v75);
  AmiShortcutItem::~AmiShortcutItem((AmiShortcutItem *)v84);
  return (unsigned int)FirstItem;
}

```

## disassembly

```asm
0x180015030  push    rbp
0x180015032  push    rbx
0x180015033  push    rsi
0x180015034  push    rdi
0x180015035  push    r12
0x180015037  push    r13
0x180015039  push    r14
0x18001503b  push    r15
0x18001503d  lea     rbp, [rsp-558h]
0x180015045  sub     rsp, 658h
0x18001504c  mov     rax, cs:__security_cookie
0x180015053  xor     rax, rsp
0x180015056  mov     [rbp+590h+var_50], rax
0x18001505d  mov     r13, rcx
0x180015060  xor     r12d, r12d
0x180015063  mov     r15d, r12d
0x180015066  mov     dword ptr [rsp+690h+var_648], r12d
0x18001506b  lea     rcx, [rbp+590h+var_490]; this
0x180015072  call    ??0AmiShortcutItem@@QEAA@XZ; AmiShortcutItem::AmiShortcutItem(void)
0x180015077  nop
0x180015078  xor     edx, edx; Val
0x18001507a  lea     r8d, [r12+4Eh]; Size
0x18001507f  lea     rcx, [rbp+590h+var_518]; void *
0x180015083  call    memset_0
0x180015088  mov     [rbp+590h+var_4C0], r12w
0x180015090  mov     [rbp+590h+var_4B8], r12
0x180015097  xorps   xmm0, xmm0
0x18001509a  movdqa  [rbp+590h+var_4B0], xmm0
0x1800150a2  mov     [rbp+590h+var_4A0], r12
0x1800150a9  mov     [rbp+590h+var_498], r12d
0x1800150b0  mov     [rbp+590h+var_494], r12b
0x1800150b7  mov     [rbp+590h+var_4C8], r12
0x1800150be  mov     [rbp+590h+var_520], r12
0x1800150c2  mov     [rsp+690h+var_638], r12
0x1800150c7  mov     [rsp+690h+var_630], r12
0x1800150cc  lea     ecx, [r12+40h]; Size
0x1800150d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800150d6  mov     [rax], rax
0x1800150d9  mov     [rax+8], rax
0x1800150dd  mov     [rax+10h], rax
0x1800150e1  lea     esi, [r12+1]
0x1800150e6  mov     word ptr [rax+18h], 101h
0x1800150ec  mov     [rsp+690h+var_638], rax
0x1800150f1  mov     ecx, 0A8h; Size
0x1800150f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800150fb  mov     [rsp+690h+var_640], rax
0x180015100  mov     rcx, rax; this
0x180015103  call    ??0AmiShortcutItem@@QEAA@XZ; AmiShortcutItem::AmiShortcutItem(void)
0x180015108  lea     rdi, ?ShortcutCacheProviderName@AmiShortcutItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiShortcutItem::ShortcutCacheProviderName
0x18001510f  mov     rdx, rdi
0x180015112  cmp     cs:qword_18011BC28, 7
0x18001511a  cmova   rdx, cs:?ShortcutCacheProviderName@AmiShortcutItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiShortcutItem::ShortcutCacheProviderName
0x180015122  mov     dword ptr [rsp+690h+var_660], 64h ; 'd'
0x18001512a  lea     r14d, [r12+3]
0x18001512f  mov     dword ptr [rsp+690h+var_668], r14d
0x180015134  mov     dword ptr [rsp+690h+var_670], r14d
0x180015139  xor     r9d, r9d
0x18001513c  mov     r8, rax
0x18001513f  lea     rcx, [rbp+590h+var_520]
0x180015143  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180015148  mov     ebx, eax
0x18001514a  test    eax, eax
0x18001514c  jns     short loc_18001516B
0x18001514e  lea     r9, aTelcacheprovid_16; "TelCacheProvider::Initialize failed [%#"...
0x180015155  mov     r8d, 165h
0x18001515b  mov     dword ptr [rsp+690h+var_670], eax
0x18001515f  lea     rdx, aWindowsCompatI_43; "Windows::Compat::Inventory::MareDataWri"...
0x180015166  jmp     loc_1800157EB
0x18001516b  mov     [rsp+690h+var_650], r12d
0x180015170  lea     rdx, [rsp+690h+var_650]; unsigned int *
0x180015175  lea     rcx, [rbp+590h+var_520]; this
0x180015179  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x18001517e  mov     ebx, eax
0x180015180  test    eax, eax
0x180015182  jns     short loc_180015193
0x180015184  lea     r9, aTelcacheprovid_5; "TelCacheProvider::GetItemCount failed ["...
0x18001518b  mov     r8d, 16Dh
0x180015191  jmp     short loc_18001515B
0x180015193  mov     eax, [rsp+690h+var_650]
0x180015197  cmp     cs:qword_18011BC28, 7
0x18001519f  cmova   rdi, cs:?ShortcutCacheProviderName@AmiShortcutItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiShortcutItem::ShortcutCacheProviderName
0x1800151a7  mov     dword ptr [rsp+690h+var_668], eax
0x1800151ab  mov     [rsp+690h+var_670], rdi
0x1800151b0  lea     r9, aLsHasDItemsInC; "%ls has %d items in cache"
0x1800151b7  mov     r8d, 172h
0x1800151bd  lea     rdi, aWindowsCompatI_43; "Windows::Compat::Inventory::MareDataWri"...
0x1800151c4  mov     rdx, rdi
0x1800151c7  mov     ecx, r14d
0x1800151ca  call    AslLogCallPrintf
0x1800151cf  lea     rdx, [rbp+590h+var_490]; struct IAmiInventoryItem *
0x1800151d6  lea     rcx, [rbp+590h+var_520]; this
0x1800151da  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x1800151df  mov     ebx, eax
0x1800151e1  cmp     eax, 80070103h
0x1800151e6  jz      loc_1800157CB
0x1800151ec  lea     r14, a0000f519feec48; "0000f519feec486de87ed73cb92d3cac8024000"...
0x1800151f3  mov     eax, [rsp+690h+var_650]
0x1800151f7  mov     ecx, eax
0x1800151f9  dec     eax
0x1800151fb  mov     [rsp+690h+var_650], eax
0x1800151ff  test    ecx, ecx
0x180015201  jz      loc_1800157CB
0x180015207  test    ebx, ebx
0x180015209  jns     short loc_18001522B
0x18001520b  mov     dword ptr [rsp+690h+var_670], ebx
0x18001520f  lea     r9, aTelcacheprovid_11; "TelCacheProvider::GetNextItem failed [%"...
0x180015216  mov     r8d, 17Ah
0x18001521c  mov     rdx, rdi
0x18001521f  mov     ecx, esi
0x180015221  call    AslLogCallPrintf
0x180015226  jmp     loc_1800157AE
0x18001522b  lea     rdx, [rbp+590h+var_428]
0x180015232  lea     rcx, [rbp+590h+var_580]
0x180015236  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001523b  nop
0x18001523c  lea     rdx, [rbp+590h+var_448]
0x180015243  lea     rcx, [rbp+590h+var_5E0]
0x180015247  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001524c  nop
0x18001524d  lea     rdx, [rbp+590h+var_408]
0x180015254  lea     rcx, [rbp+590h+String1]
0x180015258  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001525d  nop
0x18001525e  lea     rdx, [rbp+590h+var_488]
0x180015265  lea     rcx, [rbp+590h+var_5A0]
0x180015269  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001526e  nop
0x18001526f  cmp     [rbp+590h+var_590], r12
0x180015273  jnz     short loc_180015299
0x180015275  lea     r9, aEmptyLinkpathX; "empty linkPath [%#x]"
0x18001527c  mov     r8d, 185h
0x180015282  mov     dword ptr [rsp+690h+var_670], 8000FFFFh
0x18001528a  mov     rdx, rdi
0x18001528d  mov     ecx, esi
0x18001528f  call    AslLogCallPrintf
0x180015294  jmp     loc_180015787
0x180015299  cmp     [rbp+590h+var_5D0], r12
0x18001529d  jnz     short loc_1800152AE
0x18001529f  lea     r9, aEmptyTargetpat; "empty targetPath [%#x]"
0x1800152a6  mov     r8d, 18Ah
0x1800152ac  jmp     short loc_180015282
0x1800152ae  cmp     [rbp+590h+var_570], r12
0x1800152b2  jnz     short loc_1800152EB
0x1800152b4  lea     rax, [rbp+590h+var_5A0]
0x1800152b8  cmp     [rbp+590h+var_588], 7
0x1800152bd  cmova   rax, [rbp+590h+var_5A0]
0x1800152c2  mov     dword ptr [rsp+690h+var_668], 8000FFFFh
0x1800152ca  mov     [rsp+690h+var_670], rax
0x1800152cf  lea     r9, aEmptyAumidForS; "empty aumid for shortcut %ls [%#x]"
0x1800152d6  mov     r8d, 190h
0x1800152dc  mov     rdx, rdi
0x1800152df  mov     ecx, esi
0x1800152e1  call    AslLogCallPrintf
0x1800152e6  jmp     loc_180015787
0x1800152eb  xorps   xmm0, xmm0
0x1800152ee  movups  xmmword ptr [rbp+590h+var_560], xmm0
0x1800152f2  mov     [rbp+590h+var_550], r12
0x1800152f6  mov     [rbp+590h+var_548], 7
0x1800152fe  mov     word ptr [rbp+590h+var_560], r12w
0x180015303  lea     r8, [rbp+590h+var_5E0]
0x180015307  cmp     [rbp+590h+var_5C8], 7
0x18001530c  cmova   r8, [rbp+590h+var_5E0]; unsigned __int16 *
0x180015311  lea     rcx, [rbp+590h+var_B0]; unsigned __int16 *
0x180015318  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x18001531d  test    eax, eax
0x18001531f  jns     short loc_180015341
0x180015321  mov     dword ptr [rsp+690h+var_670], eax
0x180015325  lea     r9, aComputefilecac; "ComputeFileCacheKey failed [%#x]"
0x18001532c  mov     r8d, 19Ah
0x180015332  mov     rdx, rdi
0x180015335  mov     ecx, esi
0x180015337  call    AslLogCallPrintf
0x18001533c  jmp     loc_1800153DC
0x180015341  lea     rcx, [rbp+590h+var_3E0]; this
0x180015348  call    ??0File@@QEAA@XZ; File::File(void)
0x18001534d  nop
0x18001534e  lea     rdx, [rbp+590h+var_B0]; unsigned __int16 *
0x180015355  lea     rcx, [rbp+590h+var_3D8]; this
0x18001535c  call    ?SetItemKey@File@@UEAAKPEBG@Z; File::SetItemKey(ushort const *)
0x180015361  xor     r8d, r8d; bool
0x180015364  lea     rdx, [rbp+590h+var_3D8]; struct IAmiInventoryItem *
0x18001536b  mov     rcx, r13; this
0x18001536e  call    ?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z; TelCacheProvider::GetItem(IAmiInventoryItem *,bool)
0x180015373  test    eax, eax
0x180015375  jns     short loc_1800153BF
0x180015377  mov     rdx, rdi
0x18001537a  cmp     ax, 2
0x18001537e  jnz     short loc_1800153A7
0x180015380  lea     rax, [rbp+590h+var_5E0]
0x180015384  cmp     [rbp+590h+var_5C8], 7
0x180015389  cmova   rax, [rbp+590h+var_5E0]
0x18001538e  mov     [rsp+690h+var_670], rax
0x180015393  lea     r9, aFileLsNotInCac; "File \"%ls\" not in cache"
0x18001539a  mov     r8d, 1A5h
0x1800153a0  mov     ecx, 3
0x1800153a5  jmp     short loc_1800153BA
0x1800153a7  mov     dword ptr [rsp+690h+var_670], eax
0x1800153ab  lea     r9, aTelcacheprovid_29; "TelCacheProvider::GetItem failed [%#x]"
0x1800153b2  mov     r8d, 1A9h
0x1800153b8  mov     ecx, esi
0x1800153ba  call    AslLogCallPrintf
0x1800153bf  lea     rdx, [rbp+590h+var_388]
0x1800153c6  lea     rcx, [rbp+590h+var_560]
0x1800153ca  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800153cf  nop
0x1800153d0  lea     rcx, [rbp+590h+var_3E0]; this
0x1800153d7  call    ??1File@@UEAA@XZ; File::~File(void)
0x1800153dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_CompatMareBackupAumidFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_CompatMareBackupAumidFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CompatMareBackupAumidFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_CompatMareBackupAumidFix>::GetImpl(void)'::`2'::impl
0x1800153e3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_CompatMareBackupAumidFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CompatMareBackupAumidFix>::__private_IsEnabled(void)
0x1800153e8  test    al, al
0x1800153ea  jz      short loc_180015448
0x1800153ec  cmp     [rbp+590h+var_5B0], r12
0x1800153f0  jz      short loc_18001540C
0x1800153f2  lea     rcx, [rbp+590h+String1]
0x1800153f6  cmp     [rbp+590h+var_5A8], 7
0x1800153fb  cmova   rcx, [rbp+590h+String1]; String1
0x180015400  mov     rdx, r14; String2
0x180015403  call    wcscmp_0
0x180015408  test    eax, eax
0x18001540a  jnz     short loc_180015471
0x18001540c  lea     rdx, [rbp+590h+var_560]
0x180015410  lea     rcx, [rbp+590h+String1]
0x180015414  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180015419  cmp     [rbp+590h+var_5B0], r12
0x18001541d  jz      short loc_18001543D
0x18001541f  lea     rcx, [rbp+590h+String1]
0x180015423  cmp     [rbp+590h+var_5A8], 7
0x180015428  cmova   rcx, [rbp+590h+String1]; String1
0x18001542d  mov     rdx, r14; String2
0x180015430  call    wcscmp_0
0x180015435  test    eax, eax
0x180015437  jnz     loc_1800154E5
0x18001543d  mov     r8d, 1B9h
0x180015443  jmp     loc_180015755
0x180015448  mov     rbx, [rbp+590h+var_5B0]
0x18001544c  test    rbx, rbx
0x18001544f  jz      short loc_1800154A3
0x180015451  lea     rcx, [rbp+590h+String1]
0x180015455  cmp     [rbp+590h+var_5A8], 7
0x18001545a  cmova   rcx, [rbp+590h+String1]; String1
0x18001545f  mov     rdx, r14; String2
0x180015462  call    wcscmp_0
0x180015467  test    eax, eax
0x180015469  jz      short loc_1800154A3
0x18001546b  cmp     rbx, 2Dh ; '-'
0x18001546f  jnz     short loc_1800154A3
0x180015471  lea     rcx, [rbp+590h+var_560]
0x180015475  cmp     [rbp+590h+var_548], 7
0x18001547a  cmova   rcx, [rbp+590h+var_560]; String1
0x18001547f  mov     rdx, r14; String2
0x180015482  call    wcscmp_0
0x180015487  test    eax, eax
0x180015489  jnz     short loc_1800154E5
0x18001548b  mov     [rbp+590h+var_5D0], r12
0x18001548f  lea     rcx, [rbp+590h+var_5E0]
0x180015493  cmp     [rbp+590h+var_5C8], 7
0x180015498  cmova   rcx, [rbp+590h+var_5E0]
0x18001549d  mov     [rcx], r12w
0x1800154a1  jmp     short loc_1800154E5
0x1800154a3  lea     rdx, [rbp+590h+var_560]
0x1800154a7  lea     rcx, [rbp+590h+String1]
0x1800154ab  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800154b0  mov     rbx, [rbp+590h+var_5B0]
0x1800154b4  test    rbx, rbx
0x1800154b7  jz      loc_18001574F
0x1800154bd  lea     rcx, [rbp+590h+String1]
0x1800154c1  cmp     [rbp+590h+var_5A8], 7
0x1800154c6  cmova   rcx, [rbp+590h+String1]; String1
0x1800154cb  mov     rdx, r14; String2
0x1800154ce  call    wcscmp_0
0x1800154d3  test    eax, eax
0x1800154d5  jz      loc_18001574F
0x1800154db  cmp     rbx, 2Dh ; '-'
0x1800154df  jnz     loc_18001574F
0x1800154e5  lea     rdx, [rbp+590h+String1]
0x1800154e9  cmp     [rbp+590h+var_5A8], 7
0x1800154ee  cmova   rdx, [rbp+590h+String1]
0x1800154f3  lea     rcx, [rbp+590h+var_5A0]
0x1800154f7  cmp     [rbp+590h+var_588], 7
0x1800154fc  cmova   rcx, [rbp+590h+var_5A0]
0x180015501  lea     rax, [rbp+590h+var_580]
0x180015505  cmp     [rbp+590h+var_568], 7
0x18001550a  cmova   rax, [rbp+590h+var_580]
0x18001550f  mov     [rsp+690h+var_660], rdx
0x180015514  mov     [rsp+690h+var_668], rcx
0x180015519  mov     [rsp+690h+var_670], rax
0x18001551e  lea     r9, aAddingLsLsToLs; "Adding %ls %ls to \"%ls\""
0x180015525  mov     r8d, 1DDh
0x18001552b  mov     rdx, rdi
0x18001552e  mov     ecx, 3
0x180015533  call    AslLogCallPrintf
0x180015538  lea     rsi, [rbp+590h+String1]
0x18001553c  cmp     [rbp+590h+var_5A8], 7
0x180015541  cmova   rsi, [rbp+590h+String1]
0x180015546  mov     [rsp+690h+var_640], rsi
0x18001554b  lea     r14, [r13+120h]
0x180015552  xorps   xmm0, xmm0
0x180015555  movups  [rbp+590h+var_540], xmm0
0x180015559  mov     [rbp+590h+var_530], r12
0x18001555d  mov     [rbp+590h+var_528], r12
  ... truncated ...
```
