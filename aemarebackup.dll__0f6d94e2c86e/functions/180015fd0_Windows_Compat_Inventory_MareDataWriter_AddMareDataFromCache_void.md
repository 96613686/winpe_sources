# Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache(void)

- ea: `0x180015fd0`
- end: `0x18001640d`
- name: `?AddMareDataFromCache@MareDataWriter@Inventory@Compat@Windows@@AEAAJXZ`
- size: `1085`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::MareDataWriter *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1800172a0`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x180006cec`
- `0x18000f174`
- `0x18000fb60`
- `0x1800105bc`
- `0x180010f58`
- `0x1800134b8`
- `0x18001459c`
- `0x180015fd0`
- `0x18001b554`
- `0x18001bb7c`
- `0x18001d840`
- `0x18001efb4`
- `0x18002d73c`
- `0x18002e958`
- `0x180030934`
- `0x180030a04`
- `0x18004c020`
- `0x1800e683c`

## string_xrefs

- `0x1800160bb`: `Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache`
- `0x180016109`: `Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache`
- `0x1800160fc`: `%ls has %d items in cache`
- `0x180016149`: `TelCacheProvider::GetNextItem failed [%#x]`
- `0x1800163bb`: `TelCacheProvider::GetNextItem failed [%#x]`
- `0x1800160e0`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x1800160aa`: `TelCacheProvider::Initialize failed [%#x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache(
        Windows::Compat::Inventory::MareDataWriter *this)
{
  wchar_t *v2; // rax
  int ItemCount; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  int i; // eax
  __int64 *v9; // rsi
  __int64 v10; // r8
  __int64 v11; // rbx
  Windows::Compat::Inventory::MareApplication *v12; // rcx
  __int64 *v13; // rsi
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v17; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[16]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h]
  Windows::Compat::Inventory::MareApplication *v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+78h] [rbp-88h] BYREF
  __int128 v25; // [rsp+88h] [rbp-78h] BYREF
  __int64 v26; // [rsp+98h] [rbp-68h]
  __int64 v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[80]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v30; // [rsp+108h] [rbp+8h]
  __int16 v31; // [rsp+110h] [rbp+10h]
  __int64 v32; // [rsp+118h] [rbp+18h]
  __int128 v33; // [rsp+120h] [rbp+20h]
  __int64 v34; // [rsp+130h] [rbp+30h]
  int v35; // [rsp+138h] [rbp+38h]
  char v36; // [rsp+13Ch] [rbp+3Ch]
  void **v37; // [rsp+140h] [rbp+40h] BYREF
  char v38; // [rsp+148h] [rbp+48h]
  unsigned __int16 v39[260]; // [rsp+14Ah] [rbp+4Ah] BYREF
  wchar_t v40[45]; // [rsp+352h] [rbp+252h] BYREF
  wchar_t String2[46]; // [rsp+3ACh] [rbp+2ACh] BYREF
  int v42; // [rsp+408h] [rbp+308h]
  __int64 v43; // [rsp+410h] [rbp+310h]
  unsigned __int16 v44[260]; // [rsp+418h] [rbp+318h] BYREF
  unsigned __int16 v45[264]; // [rsp+620h] [rbp+520h] BYREF

  v37 = &Windows::Compat::Inventory::MareBackupItem::`vftable';
  v42 = 0;
  v43 = 0;
  memset_0(v29, 0, 0x4Eu);
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v30 = 0;
  v28 = 0;
  v2 = (wchar_t *)operator new(0x6E8u);
  v19 = v2;
  *(_QWORD *)v2 = &Windows::Compat::Inventory::MareBackupItem::`vftable';
  *((_DWORD *)v2 + 178) = 0;
  *((_QWORD *)v2 + 90) = 0;
  ItemCount = TelCacheProvider::Initialize(&v28, L"Mare", v2, 0, 3, 3, 100);
  v4 = ItemCount;
  if ( ItemCount < 0 )
  {
    v5 = "TelCacheProvider::Initialize failed [%#x]";
    v6 = 266;
LABEL_3:
    LODWORD(v17) = ItemCount;
LABEL_35:
    AslLogCallPrintf(1, "Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache", v6, v5, v17);
    goto LABEL_36;
  }
  v18 = 0;
  ItemCount = TelCacheProvider::GetItemCount((TelCacheProvider *)&v28, &v18);
  v4 = ItemCount;
  if ( ItemCount < 0 )
  {
    v5 = "TelCacheProvider::GetItemCount failed [%#x]";
    v6 = 274;
    goto LABEL_3;
  }
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache",
    279,
    "%ls has %d items in cache",
    L"Mare",
    v18);
  for ( i = TelCacheProvider::GetFirstItem((TelCacheProvider *)&v28, (struct IAmiInventoryItem *)&v37);
        ;
        i = TelCacheProvider::GetNextItem((TelCacheProvider *)&v28, (struct IAmiInventoryItem *)&v37) )
  {
    v4 = i;
    if ( i == -2147024637 )
      break;
    if ( !v18-- )
      break;
    if ( i >= 0 )
    {
      if ( v38 )
      {
        v19 = String2;
        if ( !wcscmp_0(L"0000f519feec486de87ed73cb92d3cac802400000000", String2) )
        {
          AslLogCallPrintf(
            3,
            "Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache",
            297,
            "%ls is a system file. Skipping",
            v39);
        }
        else
        {
          v9 = (__int64 *)((char *)this + 288);
          v25 = 0;
          v26 = 0;
          v27 = 0;
          v10 = -1;
          do
            ++v10;
          while ( String2[v10] );
          std::wstring::_Construct<1,unsigned short const *>(&v25, String2);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
            (char *)this + 288,
            v21,
            &v25);
          v11 = v22;
          if ( *(_BYTE *)(v22 + 25) || (unsigned __int8)std::operator<<unsigned short>(&v25, v22 + 32) )
            v11 = *v9;
          std::wstring::~wstring(&v25);
          if ( v11 == *v9 )
          {
            AslLogCallPrintf(
              3,
              "Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache",
              310,
              "Adding MARE orphan file %ls to %ls",
              v39,
              String2);
            v23 = (Windows::Compat::Inventory::MareApplication *)operator new(0x110u);
            v20 = Windows::Compat::Inventory::MareApplication::MareApplication(v23, String2, v39);
            std::_Tree<std::_Tmap_traits<std::wstring const,Windows::Compat::Inventory::MareApplication *,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Windows::Compat::Inventory::MareApplication *>>,0>>::emplace<unsigned short const * &,Windows::Compat::Inventory::MareApplication *>(
              (char *)this + 288,
              &v24,
              &v19,
              &v20);
            v12 = *(Windows::Compat::Inventory::MareApplication **)(v24 + 64);
          }
          else
          {
            AslLogCallPrintf(
              3,
              "Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache",
              304,
              "Adding MARE file %ls to %ls",
              v39,
              String2);
            v12 = *(Windows::Compat::Inventory::MareApplication **)(v11 + 64);
          }
          Windows::Compat::Inventory::MareApplication::AddMatchingFile(
            v12,
            (struct Windows::Compat::Inventory::MareBackupItem *)&v37);
        }
      }
      else
      {
        v13 = (__int64 *)((char *)this + 288);
        v25 = 0;
        v26 = 0;
        v27 = 0;
        v14 = -1;
        do
          ++v14;
        while ( v40[v14] );
        std::wstring::_Construct<1,unsigned short const *>(&v25, v40);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
          (char *)this + 288,
          v21,
          &v25);
        v15 = v22;
        if ( *(_BYTE *)(v22 + 25) || (unsigned __int8)std::operator<<unsigned short>(&v25, v22 + 32) )
          v15 = *v13;
        std::wstring::~wstring(&v25);
        if ( v15 != *v13 )
        {
          AslLogCallPrintf(
            3,
            "Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache",
            321,
            "Adding MARE data to %ls",
            v40);
          *(_DWORD *)(*(_QWORD *)(v15 + 64) + 136LL) |= v42;
          Windows::Compat::Inventory::MareApplication::SetRestoreDetails(
            *(Windows::Compat::Inventory::MareApplication **)(v15 + 64),
            v44);
          Windows::Compat::Inventory::MareApplication::SetSdbGuids(
            *(Windows::Compat::Inventory::MareApplication **)(v15 + 64),
            v45);
        }
      }
    }
    else
    {
      LODWORD(v17) = i;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache",
        287,
        "TelCacheProvider::GetNextItem failed [%#x]",
        v17);
    }
  }
  if ( (_WORD)i != 259 )
  {
    LODWORD(v17) = i;
    v5 = "TelCacheProvider::GetNextItem failed [%#x]";
    v6 = 338;
    goto LABEL_35;
  }
  v4 = 0;
LABEL_36:
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v28);
  return v4;
}

```

## disassembly

```asm
0x180015fd0  mov     [rsp-8+arg_8], rbx
0x180015fd5  mov     [rsp-8+arg_10], rsi
0x180015fda  push    rbp
0x180015fdb  push    rdi
0x180015fdc  push    r12
0x180015fde  push    r14
0x180015fe0  push    r15
0x180015fe2  lea     rbp, [rsp-740h]
0x180015fea  sub     rsp, 840h
0x180015ff1  mov     rax, cs:__security_cookie
0x180015ff8  xor     rax, rsp
0x180015ffb  mov     [rbp+760h+var_30], rax
0x180016002  mov     r14, rcx
0x180016005  lea     rbx, ??_7MareBackupItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::MareBackupItem::`vftable'
0x18001600c  mov     [rbp+760h+var_720], rbx
0x180016010  xor     r15d, r15d
0x180016013  mov     [rbp+760h+var_458], r15d
0x18001601a  mov     [rbp+760h+var_450], r15
0x180016021  xor     edx, edx; Val
0x180016023  lea     r8d, [r15+4Eh]; Size
0x180016027  lea     rcx, [rbp+760h+var_7A8]; void *
0x18001602b  call    memset_0
0x180016030  mov     [rbp+760h+var_750], r15w
0x180016035  mov     [rbp+760h+var_748], r15
0x180016039  xorps   xmm0, xmm0
0x18001603c  movdqa  [rbp+760h+var_740], xmm0
0x180016041  mov     [rbp+760h+var_730], r15
0x180016045  mov     [rbp+760h+var_728], r15d
0x180016049  mov     [rbp+760h+var_724], r15b
0x18001604d  mov     [rbp+760h+var_758], r15
0x180016051  mov     [rbp+760h+var_7B0], r15
0x180016055  mov     ecx, 6E8h; Size
0x18001605a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001605f  mov     [rsp+860h+var_818], rax
0x180016064  mov     [rax], rbx
0x180016067  mov     [rax+2C8h], r15d
0x18001606e  mov     [rax+2D0h], r15
0x180016075  mov     [rsp+860h+var_830], 64h ; 'd'
0x18001607d  lea     r12d, [r15+3]
0x180016081  mov     dword ptr [rsp+860h+var_838], r12d
0x180016086  mov     dword ptr [rsp+860h+var_840], r12d
0x18001608b  xor     r9d, r9d
0x18001608e  mov     r8, rax
0x180016091  lea     rdi, aMare; "Mare"
0x180016098  mov     rdx, rdi
0x18001609b  lea     rcx, [rbp+760h+var_7B0]
0x18001609f  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x1800160a4  mov     ebx, eax
0x1800160a6  test    eax, eax
0x1800160a8  jns     short loc_1800160C7
0x1800160aa  lea     r9, aTelcacheprovid_16; "TelCacheProvider::Initialize failed [%#"...
0x1800160b1  mov     r8d, 10Ah
0x1800160b7  mov     dword ptr [rsp+860h+var_840], eax
0x1800160bb  lea     rdx, aWindowsCompatI_1; "Windows::Compat::Inventory::MareDataWri"...
0x1800160c2  jmp     loc_1800163CB
0x1800160c7  mov     [rsp+860h+var_820], r15d
0x1800160cc  lea     rdx, [rsp+860h+var_820]; unsigned int *
0x1800160d1  lea     rcx, [rbp+760h+var_7B0]; this
0x1800160d5  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x1800160da  mov     ebx, eax
0x1800160dc  test    eax, eax
0x1800160de  jns     short loc_1800160EF
0x1800160e0  lea     r9, aTelcacheprovid_5; "TelCacheProvider::GetItemCount failed ["...
0x1800160e7  mov     r8d, 112h
0x1800160ed  jmp     short loc_1800160B7
0x1800160ef  mov     eax, [rsp+860h+var_820]
0x1800160f3  mov     dword ptr [rsp+860h+var_838], eax
0x1800160f7  mov     [rsp+860h+var_840], rdi
0x1800160fc  lea     r9, aLsHasDItemsInC; "%ls has %d items in cache"
0x180016103  mov     r8d, 117h
0x180016109  lea     rdi, aWindowsCompatI_1; "Windows::Compat::Inventory::MareDataWri"...
0x180016110  mov     rdx, rdi
0x180016113  mov     ecx, r12d
0x180016116  call    AslLogCallPrintf
0x18001611b  lea     rdx, [rbp+760h+var_720]; struct IAmiInventoryItem *
0x18001611f  lea     rcx, [rbp+760h+var_7B0]; this
0x180016123  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x180016128  jmp     loc_18001639E
0x18001612d  mov     eax, [rsp+860h+var_820]
0x180016131  mov     ecx, eax
0x180016133  dec     eax
0x180016135  mov     [rsp+860h+var_820], eax
0x180016139  test    ecx, ecx
0x18001613b  jz      loc_1800163AB
0x180016141  test    ebx, ebx
0x180016143  jns     short loc_18001615D
0x180016145  mov     dword ptr [rsp+860h+var_840], ebx
0x180016149  lea     r9, aTelcacheprovid_11; "TelCacheProvider::GetNextItem failed [%"...
0x180016150  mov     r8d, 11Fh
0x180016156  mov     ecx, 1
0x18001615b  jmp     short loc_1800161A3
0x18001615d  cmp     [rbp+760h+var_718], r15b
0x180016161  jz      loc_1800162C4
0x180016167  lea     rax, [rbp+760h+String2]
0x18001616e  mov     [rsp+860h+var_818], rax
0x180016173  lea     rdx, [rbp+760h+String2]; String2
0x18001617a  lea     rcx, a0000f519feec48; "0000f519feec486de87ed73cb92d3cac8024000"...
0x180016181  call    wcscmp_0
0x180016186  test    eax, eax
0x180016188  jnz     short loc_1800161B0
0x18001618a  lea     rax, [rbp+760h+var_716]
0x18001618e  mov     [rsp+860h+var_840], rax
0x180016193  lea     r9, aLsIsASystemFil; "%ls is a system file. Skipping"
0x18001619a  mov     r8d, 129h
0x1800161a0  mov     ecx, r12d
0x1800161a3  mov     rdx, rdi
0x1800161a6  call    AslLogCallPrintf
0x1800161ab  jmp     loc_180016391
0x1800161b0  lea     rsi, [r14+120h]
0x1800161b7  xorps   xmm0, xmm0
0x1800161ba  movups  [rbp+760h+var_7D8], xmm0
0x1800161be  mov     [rbp+760h+var_7C8], r15
0x1800161c2  mov     [rbp+760h+var_7C0], r15
0x1800161c6  lea     rax, [rbp+760h+String2]
0x1800161cd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800161d1  inc     r8
0x1800161d4  cmp     [rax+r8*2], r15w
0x1800161d9  jnz     short loc_1800161D1
0x1800161db  lea     rdx, [rbp+760h+String2]
0x1800161e2  lea     rcx, [rbp+760h+var_7D8]
0x1800161e6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800161eb  lea     r8, [rbp+760h+var_7D8]
0x1800161ef  lea     rdx, [rsp+860h+var_808]
0x1800161f4  mov     rcx, rsi
0x1800161f7  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800161fc  mov     rbx, [rsp+860h+var_7F8]
0x180016201  cmp     [rbx+19h], r15b
0x180016205  jnz     short loc_180016218
0x180016207  lea     rdx, [rbx+20h]
0x18001620b  lea     rcx, [rbp+760h+var_7D8]
0x18001620f  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180016214  test    al, al
0x180016216  jz      short loc_18001621B
0x180016218  mov     rbx, [rsi]
0x18001621b  lea     rcx, [rbp+760h+var_7D8]
0x18001621f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016224  lea     rax, [rbp+760h+String2]
0x18001622b  mov     rdx, rdi
0x18001622e  mov     ecx, r12d
0x180016231  mov     [rsp+860h+var_838], rax
0x180016236  lea     rax, [rbp+760h+var_716]
0x18001623a  mov     [rsp+860h+var_840], rax
0x18001623f  cmp     rbx, [rsi]
0x180016242  jnz     short loc_1800162A0
0x180016244  lea     r9, aAddingMareOrph; "Adding MARE orphan file %ls to %ls"
0x18001624b  mov     r8d, 136h
0x180016251  call    AslLogCallPrintf
0x180016256  mov     ecx, 110h; Size
0x18001625b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016260  mov     [rsp+860h+var_7F0], rax
0x180016265  lea     r8, [rbp+760h+var_716]; unsigned __int16 *
0x180016269  lea     rdx, [rbp+760h+String2]; unsigned __int16 *
0x180016270  mov     rcx, rax; this
0x180016273  call    ??0MareApplication@Inventory@Compat@Windows@@QEAA@PEBG0@Z; Windows::Compat::Inventory::MareApplication::MareApplication(ushort const *,ushort const *)
0x180016278  nop
0x180016279  mov     [rsp+860h+var_810], rax
0x18001627e  lea     r9, [rsp+860h+var_810]
0x180016283  lea     r8, [rsp+860h+var_818]
0x180016288  lea     rdx, [rsp+860h+var_7E8]
0x18001628d  mov     rcx, rsi
0x180016290  call    ??$emplace@AEAPEBGPEAVMareApplication@Inventory@Compat@Windows@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVMareApplication@Inventory@Compat@Windows@@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVMareApplication@Inventory@Compat@Windows@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVMareApplication@Inventory@Compat@Windows@@@std@@@std@@@std@@@std@@_N@1@AEAPEBG$$QEAPEAVMareApplication@Inventory@Compat@Windows@@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,Windows::Compat::Inventory::MareApplication *,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Windows::Compat::Inventory::MareApplication *>>,0>>::emplace<ushort const * &,Windows::Compat::Inventory::MareApplication *>(ushort const * &,Windows::Compat::Inventory::MareApplication * &&)
0x180016295  mov     rax, [rsp+860h+var_7E8]
0x18001629a  mov     rcx, [rax+40h]
0x18001629e  jmp     short loc_1800162B6
0x1800162a0  lea     r9, aAddingMareFile; "Adding MARE file %ls to %ls"
0x1800162a7  mov     r8d, 130h
0x1800162ad  call    AslLogCallPrintf
0x1800162b2  mov     rcx, [rbx+40h]; this
0x1800162b6  lea     rdx, [rbp+760h+var_720]; struct Windows::Compat::Inventory::MareBackupItem *
0x1800162ba  call    ?AddMatchingFile@MareApplication@Inventory@Compat@Windows@@QEAAXAEAVMareBackupItem@234@@Z; Windows::Compat::Inventory::MareApplication::AddMatchingFile(Windows::Compat::Inventory::MareBackupItem &)
0x1800162bf  jmp     loc_180016391
0x1800162c4  lea     rsi, [r14+120h]
0x1800162cb  xorps   xmm0, xmm0
0x1800162ce  movups  [rbp+760h+var_7D8], xmm0
0x1800162d2  mov     [rbp+760h+var_7C8], r15
0x1800162d6  mov     [rbp+760h+var_7C0], r15
0x1800162da  lea     rax, [rbp+760h+var_50E]
0x1800162e1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800162e5  inc     r8
0x1800162e8  cmp     [rax+r8*2], r15w
0x1800162ed  jnz     short loc_1800162E5
0x1800162ef  lea     rdx, [rbp+760h+var_50E]
0x1800162f6  lea     rcx, [rbp+760h+var_7D8]
0x1800162fa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800162ff  lea     r8, [rbp+760h+var_7D8]
0x180016303  lea     rdx, [rsp+860h+var_808]
0x180016308  mov     rcx, rsi
0x18001630b  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180016310  mov     rbx, [rsp+860h+var_7F8]
0x180016315  cmp     [rbx+19h], r15b
0x180016319  jnz     short loc_18001632C
0x18001631b  lea     rdx, [rbx+20h]
0x18001631f  lea     rcx, [rbp+760h+var_7D8]
0x180016323  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180016328  test    al, al
0x18001632a  jz      short loc_18001632F
0x18001632c  mov     rbx, [rsi]
0x18001632f  lea     rcx, [rbp+760h+var_7D8]
0x180016333  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016338  cmp     rbx, [rsi]
0x18001633b  jz      short loc_180016391
0x18001633d  lea     rax, [rbp+760h+var_50E]
0x180016344  mov     [rsp+860h+var_840], rax
0x180016349  lea     r9, aAddingMareData; "Adding MARE data to %ls"
0x180016350  mov     r8d, 141h
0x180016356  mov     rdx, rdi
0x180016359  mov     ecx, r12d
0x18001635c  call    AslLogCallPrintf
0x180016361  mov     rcx, [rbx+40h]
0x180016365  mov     eax, [rbp+760h+var_458]
0x18001636b  or      [rcx+88h], eax
0x180016371  lea     rdx, [rbp+760h+var_448]; unsigned __int16 *
0x180016378  mov     rcx, [rbx+40h]; this
0x18001637c  call    ?SetRestoreDetails@MareApplication@Inventory@Compat@Windows@@QEAAXPEBG@Z; Windows::Compat::Inventory::MareApplication::SetRestoreDetails(ushort const *)
0x180016381  lea     rdx, [rbp+760h+var_240]; unsigned __int16 *
0x180016388  mov     rcx, [rbx+40h]; this
0x18001638c  call    ?SetSdbGuids@MareApplication@Inventory@Compat@Windows@@QEAAXPEBG@Z; Windows::Compat::Inventory::MareApplication::SetSdbGuids(ushort const *)
0x180016391  lea     rdx, [rbp+760h+var_720]; struct IAmiInventoryItem *
0x180016395  lea     rcx, [rbp+760h+var_7B0]; this
0x180016399  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x18001639e  cmp     eax, 80070103h
0x1800163a3  mov     ebx, eax
0x1800163a5  jnz     loc_18001612D
0x1800163ab  cmp     bx, 103h
0x1800163b0  jnz     short loc_1800163B7
0x1800163b2  mov     ebx, r15d
0x1800163b5  jmp     short loc_1800163D6
0x1800163b7  mov     dword ptr [rsp+860h+var_840], ebx
0x1800163bb  lea     r9, aTelcacheprovid_11; "TelCacheProvider::GetNextItem failed [%"...
0x1800163c2  mov     r8d, 152h
0x1800163c8  mov     rdx, rdi
0x1800163cb  mov     ecx, 1
0x1800163d0  call    AslLogCallPrintf
0x1800163d5  nop
0x1800163d6  lea     rcx, [rbp+760h+var_7B0]; this
0x1800163da  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x1800163df  nop
0x1800163e0  mov     eax, ebx
0x1800163e2  mov     rcx, [rbp+760h+var_30]
0x1800163e9  xor     rcx, rsp; StackCookie
0x1800163ec  call    __security_check_cookie
0x1800163f1  lea     r11, [rsp+860h+var_20]
0x1800163f9  mov     rbx, [r11+38h]
0x1800163fd  mov     rsi, [r11+40h]
0x180016401  mov     rsp, r11
0x180016404  pop     r15
0x180016406  pop     r14
0x180016408  pop     r12
0x18001640a  pop     rdi
0x18001640b  pop     rbp
0x18001640c  retn
```
