# Windows::Compat::Inventory::SqliteInvCache::GetItemList(std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,unsigned __int64)

- ea: `0x18001bc40`
- end: `0x18001bff5`
- name: `?GetItemList@SqliteInvCache@Inventory@Compat@Windows@@QEBAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_K@Z`
- size: `949`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18001b490`
- `0x180020790`

## callees

- `0x180004ea0`
- `0x180006cec`
- `0x18000fb60`
- `0x1800134b8`
- `0x18001bc40`
- `0x180027cb0`
- `0x180027d3c`
- `0x18004c020`
- `0x1800a494c`
- `0x1800c18e0`
- `0x1800c2b60`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bc85`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bc85`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001bf52`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001bf52`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001beae`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001beae`

## string_xrefs

- `0x18001be36`: `Windows::Compat::Inventory::SqliteInvCache::GetItemList`
- `0x18001bfa3`: `Windows::Compat::Inventory::SqliteInvCache::GetItemList`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::GetItemList(
        __int64 a1,
        __int64 *a2,
        struct _FILETIME a3)
{
  struct _FILETIME v3; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int128 *v10; // rdx
  int v11; // eax
  int v12; // edi
  struct _FILETIME v13; // rsi
  unsigned int v14; // ebx
  __int64 v15; // rax
  const char *v16; // r9
  __int64 v17; // r8
  int v18; // eax
  int i; // ebx
  _WORD *v20; // rdi
  __int64 v21; // r13
  void *v22; // rbx
  unsigned __int64 v23; // r8
  _QWORD *v24; // rax
  __int64 v26; // [rsp+20h] [rbp-99h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-89h] BYREF
  __int128 v28; // [rsp+38h] [rbp-81h] BYREF
  __int128 v29; // [rsp+48h] [rbp-71h]
  __int128 v30; // [rsp+58h] [rbp-61h] BYREF
  __int128 v31; // [rsp+68h] [rbp-51h]
  __int128 Src; // [rsp+78h] [rbp-41h] BYREF
  __int128 v33; // [rsp+88h] [rbp-31h]
  __int128 v34; // [rsp+98h] [rbp-21h] BYREF
  __int128 v35; // [rsp+A8h] [rbp-11h]
  __int128 v36; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v37; // [rsp+C8h] [rbp+Fh]
  __int64 v38; // [rsp+D0h] [rbp+17h]

  v3 = a3;
  if ( !*(_QWORD *)&a3 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v3 = SystemTimeAsFileTime;
  }
  v36 = 0;
  v37 = 0;
  v38 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v36, L"SELECT ", 7u);
  v6 = std::wstring::append(&v36, L"ItemKey");
  v34 = 0;
  v35 = 0u;
  v34 = *(_OWORD *)v6;
  v35 = *(_OWORD *)(v6 + 16);
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 7;
  *(_WORD *)v6 = 0;
  v7 = std::wstring::append(&v34, L" FROM ");
  Src = 0;
  v33 = 0u;
  Src = *(_OWORD *)v7;
  v33 = *(_OWORD *)(v7 + 16);
  *(_QWORD *)(v7 + 16) = 0;
  *(_QWORD *)(v7 + 24) = 7;
  *(_WORD *)v7 = 0;
  v8 = std::wstring::append(&Src);
  v28 = 0;
  v29 = 0u;
  v28 = *(_OWORD *)v8;
  v29 = *(_OWORD *)(v8 + 16);
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  *(_WORD *)v8 = 0;
  v9 = std::wstring::append(&v28, L" WHERE LastModified <= ?;");
  v30 = 0;
  v31 = 0u;
  v30 = *(_OWORD *)v9;
  v31 = *(_OWORD *)(v9 + 16);
  *(_QWORD *)(v9 + 16) = 0;
  *(_QWORD *)(v9 + 24) = 7;
  *(_WORD *)v9 = 0;
  std::wstring::~wstring((char **)&v28);
  std::wstring::~wstring((char **)&Src);
  std::wstring::~wstring((char **)&v34);
  std::wstring::~wstring((char **)&v36);
  SystemTimeAsFileTime = 0;
  v10 = &v30;
  if ( *((_QWORD *)&v31 + 1) > 7u )
    LODWORD(v10) = v30;
  v11 = sqlite3Prepare16(*(_QWORD *)(a1 + 8), (_DWORD)v10, -1, 128, (__int64)&SystemTimeAsFileTime, 0);
  v12 = v11;
  v13 = SystemTimeAsFileTime;
  if ( v11 )
  {
    if ( v11 > 0 )
      v14 = (unsigned __int16)v11 | 0x80070000;
    else
      v14 = v11;
    v15 = sqlite3_errmsg(*(_QWORD *)(a1 + 8));
    v16 = "sqlite3_prepare_v2 failed: [%d] %hs";
    v17 = 884;
LABEL_10:
    LODWORD(v26) = v12;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::GetItemList", v17, v16, v26, v15);
    goto LABEL_33;
  }
  if ( SystemTimeAsFileTime )
  {
    v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))sqlite3_bind_int64)(SystemTimeAsFileTime, 1, v3);
    v12 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v14 = (unsigned __int16)v18 | 0x80070000;
      else
        v14 = v18;
      v15 = sqlite3_errmsg(*(_QWORD *)(a1 + 8));
      v16 = "sqlite3_bind_int64 failed: [%d] %hs";
      v17 = 897;
      goto LABEL_10;
    }
    while ( 1 )
    {
      for ( i = 0; i < 100; ++i )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD))sqlite3_step)(v13);
        if ( (unsigned int)(v12 - 5) > 1 )
          break;
        Sleep(5u);
      }
      if ( v12 != 100 )
        break;
      v20 = (_WORD *)((__int64 (__fastcall *)(_QWORD, _QWORD))sqlite3_column_text16)(v13, 0);
      if ( v20 )
      {
        if ( a2[1] == 0x555555555555555LL )
          std::_Xlength_error("list too long");
        v21 = *a2;
        v28 = (unsigned __int64)a2;
        v22 = operator new(0x30u);
        *((_QWORD *)&v28 + 1) = v22;
        *((_OWORD *)v22 + 1) = 0;
        *((_QWORD *)v22 + 4) = 0;
        *((_QWORD *)v22 + 5) = 0;
        v23 = -1;
        do
          ++v23;
        while ( v20[v23] );
        std::wstring::_Construct<1,unsigned short const *>((char **)v22 + 2, v20, v23);
        ++a2[1];
        v24 = *(_QWORD **)(v21 + 8);
        *(_QWORD *)v22 = v21;
        *((_QWORD *)v22 + 1) = v24;
        *((_QWORD *)&v28 + 1) = 0;
        *(_QWORD *)(v21 + 8) = v22;
        *v24 = v22;
      }
    }
    v14 = 0;
    if ( v12 != 101 )
    {
      if ( v12 > 0 )
        v14 = (unsigned __int16)v12 | 0x80070000;
      else
        v14 = v12;
      v15 = sqlite3_errmsg(*(_QWORD *)(a1 + 8));
      v16 = "sqlite3_step failed: [%d] %hs";
      v17 = 911;
      goto LABEL_10;
    }
  }
  else
  {
    v14 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::GetItemList",
      890,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
  }
LABEL_33:
  if ( v13 )
    ((void (__fastcall *)(_QWORD))sqlite3_finalize)(v13);
  std::wstring::~wstring((char **)&v30);
  return v14;
}

```

## disassembly

```asm
0x18001bc40  mov     [rsp-8+arg_18], rbx
0x18001bc45  push    rbp
0x18001bc46  push    rsi
0x18001bc47  push    rdi
0x18001bc48  push    r12
0x18001bc4a  push    r13
0x18001bc4c  push    r14
0x18001bc4e  push    r15
0x18001bc50  lea     rbp, [rsp-27h]
0x18001bc55  sub     rsp, 0E0h
0x18001bc5c  mov     rax, cs:__security_cookie
0x18001bc63  xor     rax, rsp
0x18001bc66  mov     [rbp+57h+var_38], rax
0x18001bc6a  mov     rbx, r8
0x18001bc6d  mov     r14, rdx
0x18001bc70  mov     r15, rcx
0x18001bc73  xor     r12d, r12d
0x18001bc76  test    r8, r8
0x18001bc79  jnz     short loc_18001BC90
0x18001bc7b  mov     qword ptr [rsp+110h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18001bc80  lea     rcx, [rsp+110h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001bc85  call    cs:__imp_GetSystemTimeAsFileTime
0x18001bc8b  mov     rbx, qword ptr [rsp+110h+SystemTimeAsFileTime.dwLowDateTime]
0x18001bc90  xorps   xmm0, xmm0
0x18001bc93  movups  [rbp+57h+var_58], xmm0
0x18001bc97  mov     [rbp+57h+var_48], r12
0x18001bc9b  mov     [rbp+57h+var_40], r12
0x18001bc9f  mov     edi, 7
0x18001bca4  mov     r8d, edi
0x18001bca7  lea     rdx, aSelect; "SELECT "
0x18001bcae  lea     rcx, [rbp+57h+var_58]
0x18001bcb2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bcb7  nop
0x18001bcb8  lea     rdx, aItemkey; "ItemKey"
0x18001bcbf  lea     rcx, [rbp+57h+var_58]; Src
0x18001bcc3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001bcc8  xorps   xmm0, xmm0
0x18001bccb  movups  [rbp+57h+var_78], xmm0
0x18001bccf  mov     qword ptr [rbp+57h+var_68], r12
0x18001bcd3  mov     qword ptr [rbp+57h+var_68+8], r12
0x18001bcd7  movups  xmm0, xmmword ptr [rax]
0x18001bcda  movups  [rbp+57h+var_78], xmm0
0x18001bcde  movups  xmm1, xmmword ptr [rax+10h]
0x18001bce2  movups  [rbp+57h+var_68], xmm1
0x18001bce6  mov     [rax+10h], r12
0x18001bcea  mov     [rax+18h], rdi
0x18001bcee  mov     [rax], r12w
0x18001bcf2  lea     rdx, aFrom_0; " FROM "
0x18001bcf9  lea     rcx, [rbp+57h+var_78]; Src
0x18001bcfd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001bd02  xorps   xmm0, xmm0
0x18001bd05  movups  [rbp+57h+Src], xmm0
0x18001bd09  mov     qword ptr [rbp+57h+var_88], r12
0x18001bd0d  mov     qword ptr [rbp+57h+var_88+8], r12
0x18001bd11  movups  xmm0, xmmword ptr [rax]
0x18001bd14  movups  [rbp+57h+Src], xmm0
0x18001bd18  movups  xmm1, xmmword ptr [rax+10h]
0x18001bd1c  movups  [rbp+57h+var_88], xmm1
0x18001bd20  mov     [rax+10h], r12
0x18001bd24  mov     [rax+18h], rdi
0x18001bd28  mov     [rax], r12w
0x18001bd2c  lea     rdx, [r15+48h]
0x18001bd30  lea     rcx, [rbp+57h+Src]; Src
0x18001bd34  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001bd39  xorps   xmm0, xmm0
0x18001bd3c  movups  [rsp+110h+var_D8], xmm0
0x18001bd41  mov     qword ptr [rbp+57h+var_C8], r12
0x18001bd45  mov     qword ptr [rbp+57h+var_C8+8], r12
0x18001bd49  movups  xmm0, xmmword ptr [rax]
0x18001bd4c  movups  [rsp+110h+var_D8], xmm0
0x18001bd51  movups  xmm1, xmmword ptr [rax+10h]
0x18001bd55  movups  [rbp+57h+var_C8], xmm1
0x18001bd59  mov     [rax+10h], r12
0x18001bd5d  mov     [rax+18h], rdi
0x18001bd61  mov     [rax], r12w
0x18001bd65  lea     rdx, aWhereLastmodif; " WHERE LastModified <= ?;"
0x18001bd6c  lea     rcx, [rsp+110h+var_D8]; Src
0x18001bd71  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001bd76  xorps   xmm0, xmm0
0x18001bd79  movups  [rbp+57h+var_B8], xmm0
0x18001bd7d  mov     qword ptr [rbp+57h+var_A8], r12
0x18001bd81  mov     qword ptr [rbp+57h+var_A8+8], r12
0x18001bd85  movups  xmm0, xmmword ptr [rax]
0x18001bd88  movups  [rbp+57h+var_B8], xmm0
0x18001bd8c  movups  xmm1, xmmword ptr [rax+10h]
0x18001bd90  movups  [rbp+57h+var_A8], xmm1
0x18001bd94  mov     [rax+10h], r12
0x18001bd98  mov     [rax+18h], rdi
0x18001bd9c  mov     [rax], r12w
0x18001bda0  lea     rcx, [rsp+110h+var_D8]
0x18001bda5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bdaa  nop
0x18001bdab  lea     rcx, [rbp+57h+Src]
0x18001bdaf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bdb4  nop
0x18001bdb5  lea     rcx, [rbp+57h+var_78]
0x18001bdb9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bdbe  nop
0x18001bdbf  lea     rcx, [rbp+57h+var_58]
0x18001bdc3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bdc8  nop
0x18001bdc9  mov     qword ptr [rsp+110h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18001bdce  lea     rdx, [rbp+57h+var_B8]
0x18001bdd2  cmp     qword ptr [rbp+57h+var_A8+8], rdi
0x18001bdd6  cmova   rdx, qword ptr [rbp+57h+var_B8]
0x18001bddb  mov     [rsp+110h+var_E8], r12
0x18001bde0  lea     rax, [rsp+110h+SystemTimeAsFileTime]
0x18001bde5  mov     [rsp+110h+var_F0], rax
0x18001bdea  lea     r9d, [rdi+79h]
0x18001bdee  or      r8d, 0FFFFFFFFh
0x18001bdf2  mov     rcx, [r15+8]
0x18001bdf6  call    sqlite3Prepare16
0x18001bdfb  mov     edi, eax
0x18001bdfd  mov     rsi, qword ptr [rsp+110h+SystemTimeAsFileTime.dwLowDateTime]
0x18001be02  test    eax, eax
0x18001be04  jz      short loc_18001BE4C
0x18001be06  test    eax, eax
0x18001be08  jg      short loc_18001BE0E
0x18001be0a  mov     ebx, eax
0x18001be0c  jmp     short loc_18001BE17
0x18001be0e  movzx   ebx, di
0x18001be11  or      ebx, 80070000h
0x18001be17  mov     rcx, [r15+8]
0x18001be1b  call    sqlite3_errmsg
0x18001be20  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18001be27  mov     r8d, 374h
0x18001be2d  mov     [rsp+110h+var_E8], rax
0x18001be32  mov     dword ptr [rsp+110h+var_F0], edi
0x18001be36  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001be3d  mov     ecx, 1
0x18001be42  call    AslLogCallPrintf
0x18001be47  jmp     loc_18001BFB5
0x18001be4c  test    rsi, rsi
0x18001be4f  jz      loc_18001BF8D
0x18001be55  mov     r8, rbx
0x18001be58  mov     edx, 1
0x18001be5d  mov     rcx, rsi
0x18001be60  call    sqlite3_bind_int64
0x18001be65  mov     edi, eax
0x18001be67  test    eax, eax
0x18001be69  jz      short loc_18001BE94
0x18001be6b  test    eax, eax
0x18001be6d  jg      short loc_18001BE73
0x18001be6f  mov     ebx, eax
0x18001be71  jmp     short loc_18001BE7C
0x18001be73  movzx   ebx, di
0x18001be76  or      ebx, 80070000h
0x18001be7c  mov     rcx, [r15+8]
0x18001be80  call    sqlite3_errmsg
0x18001be85  lea     r9, aSqlite3BindInt; "sqlite3_bind_int64 failed: [%d] %hs"
0x18001be8c  mov     r8d, 381h
0x18001be92  jmp     short loc_18001BE2D
0x18001be94  mov     ebx, r12d
0x18001be97  mov     rcx, rsi
0x18001be9a  call    sqlite3_step
0x18001be9f  mov     edi, eax
0x18001bea1  lea     ecx, [rax-5]
0x18001bea4  cmp     ecx, 1
0x18001bea7  ja      short loc_18001BEBB
0x18001bea9  mov     ecx, 5; dwMilliseconds
0x18001beae  call    cs:__imp_Sleep
0x18001beb4  inc     ebx
0x18001beb6  cmp     ebx, 64h ; 'd'
0x18001beb9  jl      short loc_18001BE97
0x18001bebb  cmp     edi, 64h ; 'd'
0x18001bebe  jnz     loc_18001BF59
0x18001bec4  xor     edx, edx
0x18001bec6  mov     rcx, rsi
0x18001bec9  call    sqlite3_column_text16
0x18001bece  mov     rdi, rax
0x18001bed1  test    rax, rax
0x18001bed4  jz      short loc_18001BE94
0x18001bed6  mov     rax, 555555555555555h
0x18001bee0  cmp     [r14+8], rax
0x18001bee4  jz      short loc_18001BF4B
0x18001bee6  mov     r13, [r14]
0x18001bee9  mov     qword ptr [rsp+110h+var_D8], r14
0x18001beee  mov     qword ptr [rbp+57h+var_D8+8], r12
0x18001bef2  mov     ecx, 30h ; '0'; Size
0x18001bef7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001befc  mov     rbx, rax
0x18001beff  mov     qword ptr [rbp+57h+var_D8+8], rax
0x18001bf03  lea     rcx, [rax+10h]
0x18001bf07  xorps   xmm0, xmm0
0x18001bf0a  movups  xmmword ptr [rcx], xmm0
0x18001bf0d  mov     [rcx+10h], r12
0x18001bf11  mov     [rcx+18h], r12
0x18001bf15  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001bf19  inc     r8
0x18001bf1c  cmp     [rdi+r8*2], r12w
0x18001bf21  jnz     short loc_18001BF19
0x18001bf23  mov     rdx, rdi
0x18001bf26  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bf2b  nop
0x18001bf2c  inc     qword ptr [r14+8]
0x18001bf30  mov     rax, [r13+8]
0x18001bf34  mov     [rbx], r13
0x18001bf37  mov     [rbx+8], rax
0x18001bf3b  mov     qword ptr [rbp+57h+var_D8+8], r12
0x18001bf3f  mov     [r13+8], rbx
0x18001bf43  mov     [rax], rbx
0x18001bf46  jmp     loc_18001BE94
0x18001bf4b  lea     rcx, aListTooLong; "list too long"
0x18001bf52  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001bf59  mov     ebx, r12d
0x18001bf5c  cmp     edi, 65h ; 'e'
0x18001bf5f  jz      short loc_18001BFB5
0x18001bf61  test    edi, edi
0x18001bf63  jg      short loc_18001BF69
0x18001bf65  mov     ebx, edi
0x18001bf67  jmp     short loc_18001BF72
0x18001bf69  movzx   ebx, di
0x18001bf6c  or      ebx, 80070000h
0x18001bf72  mov     rcx, [r15+8]
0x18001bf76  call    sqlite3_errmsg
0x18001bf7b  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18001bf82  mov     r8d, 38Fh
0x18001bf88  jmp     loc_18001BE2D
0x18001bf8d  mov     ebx, 80004005h
0x18001bf92  mov     dword ptr [rsp+110h+var_F0], ebx
0x18001bf96  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18001bf9d  mov     r8d, 37Ah
0x18001bfa3  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001bfaa  mov     ecx, 1
0x18001bfaf  call    AslLogCallPrintf
0x18001bfb4  nop
0x18001bfb5  test    rsi, rsi
0x18001bfb8  jz      short loc_18001BFC3
0x18001bfba  mov     rcx, rsi
0x18001bfbd  call    sqlite3_finalize
0x18001bfc2  nop
0x18001bfc3  lea     rcx, [rbp+57h+var_B8]
0x18001bfc7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bfcc  mov     eax, ebx
0x18001bfce  mov     rcx, [rbp+57h+var_38]
0x18001bfd2  xor     rcx, rsp; StackCookie
0x18001bfd5  call    __security_check_cookie
0x18001bfda  mov     rbx, [rsp+110h+arg_18]
0x18001bfe2  add     rsp, 0E0h
0x18001bfe9  pop     r15
0x18001bfeb  pop     r14
0x18001bfed  pop     r13
0x18001bfef  pop     r12
0x18001bff1  pop     rdi
0x18001bff2  pop     rsi
0x18001bff3  pop     rbp
0x18001bff4  retn
```
