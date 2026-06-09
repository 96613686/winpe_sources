# SdbReadApphelpDetailsData

- ea: `0x180044b60`
- end: `0x180044fb6`
- name: `SdbReadApphelpDetailsData`
- size: `1110`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting`

## callees

- `0x18000b360`
- `0x18000ecc0`
- `0x18000f114`
- `0x18000f150`
- `0x1800164a0`
- `0x180022b10`
- `0x180044500`
- `0x180044b60`
- `0x18004513c`
- `0x18004525c`
- `0x180045adc`
- `0x180049af0`
- `0x180049ba0`
- `0x18004b060`
- `0x180059270`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044f56`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044f56`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180044c1d`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180044c1d`

## string_xrefs

- `0x180044bca`: `SdbReadApphelpDetailsData`
- `0x180044d21`: `SdbReadApphelpDetailsData`
- `0x180044db5`: `SdbReadApphelpDetailsData`
- `0x180044f7e`: `SdbReadApphelpDetailsData`
- `0x180044d68`: `Failed to open the apphelp resource dll`
- `0x180044da8`: `Failed to create a temporary string table`

## pseudocode

```c
__int64 __fastcall SdbReadApphelpDetailsData(__int64 a1, __int64 a2)
{
  unsigned int v4; // r15d
  unsigned int FirstDWORDIndexedTag; // edi
  int UserDefaultUILanguage; // r14d
  unsigned int v7; // ebp
  unsigned int FirstTag; // eax
  unsigned int v9; // eax
  int DWORDTag; // eax
  unsigned int v11; // eax
  unsigned int v12; // ebp
  unsigned int v13; // eax
  unsigned int v14; // eax
  HMODULE v15; // rbp
  int v16; // r14d
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  const char *v29; // r9
  __int64 v30; // r8
  __int64 v32; // [rsp+20h] [rbp-88h]
  _OWORD v33[2]; // [rsp+30h] [rbp-78h] BYREF
  __int64 v34; // [rsp+50h] [rbp-58h]
  __int128 v35; // [rsp+60h] [rbp-48h] BYREF

  v34 = 0;
  v4 = 0;
  memset(v33, 0, sizeof(v33));
  v35 = 0;
  if ( (unsigned int)SdbGetIndex(a1, 28685, 16405, 0) )
  {
    FirstDWORDIndexedTag = SdbFindFirstDWORDIndexedTag(a1, 28685, 16405, *(_DWORD *)(a2 + 8), (__int64)v33);
    if ( FirstDWORDIndexedTag )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      v7 = 0;
      while ( 1 )
      {
        FirstTag = SdbFindFirstTag(a1, FirstDWORDIndexedTag, 16405);
        if ( !FirstTag )
          break;
        if ( (unsigned int)SdbReadDWORDTag(a1, FirstTag, 0) != *(_DWORD *)(a2 + 8) )
        {
          v29 = "No entry with the same HTMLHELPID for 0x%x";
          v30 = 666;
          goto LABEL_53;
        }
        v9 = SdbFindFirstTag(a1, FirstDWORDIndexedTag, 16401);
        if ( !v9 )
          goto LABEL_17;
        DWORDTag = SdbReadDWORDTag(a1, v9, 0);
        if ( DWORDTag == 1033 )
        {
          v7 = FirstDWORDIndexedTag;
        }
        else if ( DWORDTag == UserDefaultUILanguage || !DWORDTag )
        {
          goto LABEL_17;
        }
        FirstDWORDIndexedTag = SdbFindNextDWORDIndexedTag(a1, v33);
        if ( !FirstDWORDIndexedTag )
        {
          if ( !v7 )
          {
            LODWORD(v32) = *(_DWORD *)(a2 + 8);
            AslLogCallPrintf(1, "SdbReadApphelpDetailsData", 706, "No entry for HTMLHELPID 0x%x", v32);
            return v4;
          }
          FirstDWORDIndexedTag = v7;
LABEL_17:
          v11 = SdbFindFirstTag(a1, FirstDWORDIndexedTag, 28686);
          v12 = v11;
          if ( v11 )
          {
            v13 = SdbFindFirstTag(a1, v11, 24601);
            if ( v13 )
              *(_QWORD *)(a2 + 32) = SdbGetStringTagPtr(a1, v13);
            v14 = SdbFindFirstTag(a1, v12, 24602);
            if ( v14 )
              *(_QWORD *)(a2 + 40) = SdbGetStringTagPtr(a1, v14);
          }
          if ( !(unsigned int)SdbGetDatabaseID(a1, &v35) )
            AslLogCallPrintf(1, "SdbReadApphelpDetailsData", 729, "Failed to retrieve the DB GUID");
          if ( (unsigned int)SdbIsStandardDatabase(&v35) )
          {
            *(_QWORD *)(a2 + 64) = 0;
            *(_QWORD *)(a2 + 56) = 0;
            *(_QWORD *)(a2 + 48) = 0;
            v15 = SdbOpenApphelpResourceFile(0);
            if ( !v15 )
            {
              AslLogCallPrintf(1, "SdbReadApphelpDetailsData", 746, "Failed to open the apphelp resource dll");
              return v4;
            }
            if ( !*(_QWORD *)(a1 + 2640) && !(unsigned int)SdbpAddStringTableToPDB(a1) )
            {
              AslLogCallPrintf(1, "SdbReadApphelpDetailsData", 756, "Failed to create a temporary string table");
LABEL_50:
              FreeLibrary(v15);
              return v4;
            }
            v16 = 0;
            v17 = SdbFindFirstTag(a1, FirstDWORDIndexedTag, 16420);
            if ( v17 )
            {
              v18 = SdbReadDWORDTag(a1, v17, 0);
              if ( v18 )
                *(_QWORD *)(a2 + 48) = SdbpAddResourceStringToTable(*(_QWORD *)(a1 + 2640), v15, v18);
            }
            v19 = SdbFindFirstTag(a1, FirstDWORDIndexedTag, 16421);
            if ( v19 )
            {
              v20 = SdbReadDWORDTag(a1, v19, 0);
              if ( v20 )
                *(_QWORD *)(a2 + 56) = SdbpAddResourceStringToTable(*(_QWORD *)(a1 + 2640), v15, v20);
            }
            v21 = SdbFindFirstTag(a1, FirstDWORDIndexedTag, 16425);
            if ( v21 )
            {
              v22 = SdbReadDWORDTag(a1, v21, 0);
              if ( v22 )
                v16 = SdbpAddResourceStringToTable(*(_QWORD *)(a1 + 2640), v15, v22);
            }
            v23 = SdbFindFirstTag(a1, FirstDWORDIndexedTag, 16422);
            if ( v23 )
            {
              v24 = SdbReadDWORDTag(a1, v23, 0);
              if ( v24 )
              {
                v25 = SdbpAddResourceStringToTable(*(_QWORD *)(a1 + 2640), v15, v24);
                *(_QWORD *)(a2 + 64) = SdbpExpandSummaryMsg(
                                         v25,
                                         *(_QWORD *)(a2 + 48),
                                         *(_QWORD *)(a2 + 56),
                                         v16,
                                         *(_QWORD *)(a1 + 2640));
              }
            }
          }
          else
          {
            v15 = 0;
            v26 = SdbFindFirstTag(a1, FirstDWORDIndexedTag, 24600);
            if ( v26 )
              *(_QWORD *)(a2 + 64) = SdbGetStringTagPtr(a1, v26);
            v27 = SdbFindFirstTag(a1, FirstDWORDIndexedTag, 24604);
            if ( v27 )
              *(_QWORD *)(a2 + 56) = SdbGetStringTagPtr(a1, v27);
            v28 = SdbFindFirstTag(a1, FirstDWORDIndexedTag, 24603);
            if ( v28 )
              *(_QWORD *)(a2 + 48) = SdbGetStringTagPtr(a1, v28);
          }
          v4 = 1;
          if ( !v15 )
            return v4;
          goto LABEL_50;
        }
      }
      v29 = "Failed to get HTMLHELPID for entry 0x%x";
      v30 = 659;
LABEL_53:
      LODWORD(v32) = FirstDWORDIndexedTag;
      AslLogCallPrintf(1, "SdbReadApphelpDetailsData", v30, v29, v32);
    }
    else
    {
      LODWORD(v32) = *(_DWORD *)(a2 + 8);
      AslLogCallPrintf(
        1,
        "SdbReadApphelpDetailsData",
        634,
        "Failed to find HTMLHELPID 0x%x in the details database",
        v32);
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbReadApphelpDetailsData", 623, "HTMLHELPID index in details database is not available");
  }
  return v4;
}

```

## disassembly

```asm
0x180044b60  mov     [rsp+arg_10], rbx
0x180044b65  push    rbp
0x180044b66  push    rsi
0x180044b67  push    rdi
0x180044b68  push    r14
0x180044b6a  push    r15
0x180044b6c  sub     rsp, 80h
0x180044b73  mov     rax, cs:__security_cookie
0x180044b7a  xor     rax, rsp
0x180044b7d  mov     [rsp+0A8h+var_38], rax
0x180044b82  xorps   xmm0, xmm0
0x180044b85  mov     rsi, rdx
0x180044b88  xor     eax, eax
0x180044b8a  mov     edi, 700Dh
0x180044b8f  mov     edx, edi
0x180044b91  mov     [rsp+0A8h+var_58], rax
0x180044b96  mov     r8d, 4015h
0x180044b9c  xor     r9d, r9d
0x180044b9f  mov     rbx, rcx
0x180044ba2  xor     r15d, r15d
0x180044ba5  movups  [rsp+0A8h+var_78], xmm0
0x180044baa  movups  [rsp+0A8h+var_68], xmm0
0x180044baf  movups  [rsp+0A8h+var_48], xmm0
0x180044bb4  call    SdbGetIndex
0x180044bb9  test    eax, eax
0x180044bbb  jnz     short loc_180044BE0
0x180044bbd  lea     r9, aHtmlhelpidInde; "HTMLHELPID index in details database is"...
0x180044bc4  mov     r8d, 26Fh
0x180044bca  lea     rdx, aSdbreadapphelp_1; "SdbReadApphelpDetailsData"
0x180044bd1  mov     ecx, 1
0x180044bd6  call    AslLogCallPrintf
0x180044bdb  jmp     loc_180044F8F
0x180044be0  mov     r9d, [rsi+8]
0x180044be4  lea     rax, [rsp+0A8h+var_78]
0x180044be9  mov     r8d, 4015h
0x180044bef  mov     [rsp+0A8h+var_88], rax
0x180044bf4  mov     edx, edi
0x180044bf6  mov     rcx, rbx
0x180044bf9  call    SdbFindFirstDWORDIndexedTag
0x180044bfe  mov     edi, eax
0x180044c00  test    eax, eax
0x180044c02  jnz     short loc_180044C1D
0x180044c04  mov     eax, [rsi+8]
0x180044c07  lea     r9, aFailedToFindHt; "Failed to find HTMLHELPID 0x%x in the d"...
0x180044c0e  mov     dword ptr [rsp+0A8h+var_88], eax
0x180044c12  mov     r8d, 27Ah
0x180044c18  jmp     loc_180044F7E
0x180044c1d  call    cs:__imp_GetUserDefaultUILanguage
0x180044c23  movzx   r14d, ax
0x180044c27  xor     ebp, ebp
0x180044c29  mov     r8d, 4015h
0x180044c2f  mov     edx, edi
0x180044c31  mov     rcx, rbx
0x180044c34  call    SdbFindFirstTag
0x180044c39  test    eax, eax
0x180044c3b  jz      loc_180044F6D
0x180044c41  xor     r8d, r8d
0x180044c44  mov     edx, eax
0x180044c46  mov     rcx, rbx
0x180044c49  call    SdbReadDWORDTag
0x180044c4e  cmp     eax, [rsi+8]
0x180044c51  jnz     loc_180044F5E
0x180044c57  mov     r8d, 4011h
0x180044c5d  mov     edx, edi
0x180044c5f  mov     rcx, rbx
0x180044c62  call    SdbFindFirstTag
0x180044c67  test    eax, eax
0x180044c69  jz      short loc_180044CA9
0x180044c6b  xor     r8d, r8d
0x180044c6e  mov     edx, eax
0x180044c70  mov     rcx, rbx
0x180044c73  call    SdbReadDWORDTag
0x180044c78  cmp     eax, 409h
0x180044c7d  jnz     short loc_180044C83
0x180044c7f  mov     ebp, edi
0x180044c81  jmp     short loc_180044C8C
0x180044c83  cmp     eax, r14d
0x180044c86  jz      short loc_180044CA9
0x180044c88  test    eax, eax
0x180044c8a  jz      short loc_180044CA9
0x180044c8c  lea     rdx, [rsp+0A8h+var_78]
0x180044c91  mov     rcx, rbx
0x180044c94  call    SdbFindNextDWORDIndexedTag
0x180044c99  mov     edi, eax
0x180044c9b  test    eax, eax
0x180044c9d  jnz     short loc_180044C29
0x180044c9f  test    ebp, ebp
0x180044ca1  jz      loc_180044D7A
0x180044ca7  mov     edi, ebp
0x180044ca9  mov     r8d, 700Eh
0x180044caf  mov     edx, edi
0x180044cb1  mov     rcx, rbx
0x180044cb4  call    SdbFindFirstTag
0x180044cb9  mov     ebp, eax
0x180044cbb  test    eax, eax
0x180044cbd  jz      short loc_180044D03
0x180044cbf  mov     r8d, 6019h
0x180044cc5  mov     edx, eax
0x180044cc7  mov     rcx, rbx
0x180044cca  call    SdbFindFirstTag
0x180044ccf  test    eax, eax
0x180044cd1  jz      short loc_180044CE1
0x180044cd3  mov     edx, eax
0x180044cd5  mov     rcx, rbx
0x180044cd8  call    SdbGetStringTagPtr
0x180044cdd  mov     [rsi+20h], rax
0x180044ce1  mov     r8d, 601Ah
0x180044ce7  mov     edx, ebp
0x180044ce9  mov     rcx, rbx
0x180044cec  call    SdbFindFirstTag
0x180044cf1  test    eax, eax
0x180044cf3  jz      short loc_180044D03
0x180044cf5  mov     edx, eax
0x180044cf7  mov     rcx, rbx
0x180044cfa  call    SdbGetStringTagPtr
0x180044cff  mov     [rsi+28h], rax
0x180044d03  lea     rdx, [rsp+0A8h+var_48]
0x180044d08  mov     rcx, rbx
0x180044d0b  call    SdbGetDatabaseID
0x180044d10  test    eax, eax
0x180044d12  jnz     short loc_180044D30
0x180044d14  lea     r9, aFailedToRetrie_6; "Failed to retrieve the DB GUID"
0x180044d1b  mov     r8d, 2D9h
0x180044d21  lea     rdx, aSdbreadapphelp_1; "SdbReadApphelpDetailsData"
0x180044d28  lea     ecx, [rax+1]
0x180044d2b  call    AslLogCallPrintf
0x180044d30  movaps  xmm0, [rsp+0A8h+var_48]
0x180044d35  lea     rcx, [rsp+0A8h+var_48]
0x180044d3a  movdqa  [rsp+0A8h+var_48], xmm0
0x180044d40  call    SdbIsStandardDatabase
0x180044d45  test    eax, eax
0x180044d47  jz      loc_180044EE0
0x180044d4d  xor     ecx, ecx; lpLibFileName
0x180044d4f  mov     [rsi+40h], r15
0x180044d53  mov     [rsi+38h], r15
0x180044d57  mov     [rsi+30h], r15
0x180044d5b  call    SdbOpenApphelpResourceFile
0x180044d60  mov     rbp, rax
0x180044d63  test    rax, rax
0x180044d66  jnz     short loc_180044D93
0x180044d68  lea     r9, aFailedToOpenTh; "Failed to open the apphelp resource dll"
0x180044d6f  mov     r8d, 2EAh
0x180044d75  jmp     loc_180044BCA
0x180044d7a  mov     eax, [rsi+8]
0x180044d7d  lea     r9, aNoEntryForHtml; "No entry for HTMLHELPID 0x%x"
0x180044d84  mov     dword ptr [rsp+0A8h+var_88], eax
0x180044d88  mov     r8d, 2C2h
0x180044d8e  jmp     loc_180044F7E
0x180044d93  cmp     [rbx+0A50h], r15
0x180044d9a  jnz     short loc_180044DC9
0x180044d9c  mov     rcx, rbx
0x180044d9f  call    SdbpAddStringTableToPDB
0x180044da4  test    eax, eax
0x180044da6  jnz     short loc_180044DC9
0x180044da8  lea     r9, aFailedToCreate_23; "Failed to create a temporary string tab"...
0x180044daf  mov     r8d, 2F4h
0x180044db5  lea     rdx, aSdbreadapphelp_1; "SdbReadApphelpDetailsData"
0x180044dbc  lea     ecx, [rax+1]
0x180044dbf  call    AslLogCallPrintf
0x180044dc4  jmp     loc_180044F53
0x180044dc9  mov     r8d, 4024h
0x180044dcf  mov     edx, edi
0x180044dd1  mov     rcx, rbx
0x180044dd4  xor     r14d, r14d
0x180044dd7  call    SdbFindFirstTag
0x180044ddc  test    eax, eax
0x180044dde  jz      short loc_180044E07
0x180044de0  xor     r8d, r8d
0x180044de3  mov     edx, eax
0x180044de5  mov     rcx, rbx
0x180044de8  call    SdbReadDWORDTag
0x180044ded  test    eax, eax
0x180044def  jz      short loc_180044E07
0x180044df1  mov     rcx, [rbx+0A50h]
0x180044df8  mov     r8d, eax
0x180044dfb  mov     rdx, rbp
0x180044dfe  call    SdbpAddResourceStringToTable
0x180044e03  mov     [rsi+30h], rax
0x180044e07  mov     r8d, 4025h
0x180044e0d  mov     edx, edi
0x180044e0f  mov     rcx, rbx
0x180044e12  call    SdbFindFirstTag
0x180044e17  test    eax, eax
0x180044e19  jz      short loc_180044E42
0x180044e1b  xor     r8d, r8d
0x180044e1e  mov     edx, eax
0x180044e20  mov     rcx, rbx
0x180044e23  call    SdbReadDWORDTag
0x180044e28  test    eax, eax
0x180044e2a  jz      short loc_180044E42
0x180044e2c  mov     rcx, [rbx+0A50h]
0x180044e33  mov     r8d, eax
0x180044e36  mov     rdx, rbp
0x180044e39  call    SdbpAddResourceStringToTable
0x180044e3e  mov     [rsi+38h], rax
0x180044e42  mov     r8d, 4029h
0x180044e48  mov     edx, edi
0x180044e4a  mov     rcx, rbx
0x180044e4d  call    SdbFindFirstTag
0x180044e52  test    eax, eax
0x180044e54  jz      short loc_180044E7C
0x180044e56  xor     r8d, r8d
0x180044e59  mov     edx, eax
0x180044e5b  mov     rcx, rbx
0x180044e5e  call    SdbReadDWORDTag
0x180044e63  test    eax, eax
0x180044e65  jz      short loc_180044E7C
0x180044e67  mov     rcx, [rbx+0A50h]
0x180044e6e  mov     r8d, eax
0x180044e71  mov     rdx, rbp
0x180044e74  call    SdbpAddResourceStringToTable
0x180044e79  mov     r14, rax
0x180044e7c  mov     r8d, 4026h
0x180044e82  mov     edx, edi
0x180044e84  mov     rcx, rbx
0x180044e87  call    SdbFindFirstTag
0x180044e8c  test    eax, eax
0x180044e8e  jz      loc_180044F48
0x180044e94  xor     r8d, r8d
0x180044e97  mov     edx, eax
0x180044e99  mov     rcx, rbx
0x180044e9c  call    SdbReadDWORDTag
0x180044ea1  test    eax, eax
0x180044ea3  jz      loc_180044F48
0x180044ea9  mov     rcx, [rbx+0A50h]
0x180044eb0  mov     r8d, eax
0x180044eb3  mov     rdx, rbp
0x180044eb6  call    SdbpAddResourceStringToTable
0x180044ebb  mov     rcx, [rbx+0A50h]
0x180044ec2  mov     r9, r14
0x180044ec5  mov     r8, [rsi+38h]
0x180044ec9  mov     rdx, [rsi+30h]
0x180044ecd  mov     [rsp+0A8h+var_88], rcx
0x180044ed2  mov     rcx, rax
0x180044ed5  call    SdbpExpandSummaryMsg
0x180044eda  mov     [rsi+40h], rax
0x180044ede  jmp     short loc_180044F48
0x180044ee0  mov     r8d, 6018h
0x180044ee6  mov     edx, edi
0x180044ee8  mov     rcx, rbx
0x180044eeb  xor     ebp, ebp
0x180044eed  call    SdbFindFirstTag
0x180044ef2  test    eax, eax
0x180044ef4  jz      short loc_180044F04
0x180044ef6  mov     edx, eax
0x180044ef8  mov     rcx, rbx
0x180044efb  call    SdbGetStringTagPtr
0x180044f00  mov     [rsi+40h], rax
0x180044f04  mov     r8d, 601Ch
0x180044f0a  mov     edx, edi
0x180044f0c  mov     rcx, rbx
0x180044f0f  call    SdbFindFirstTag
0x180044f14  test    eax, eax
0x180044f16  jz      short loc_180044F26
0x180044f18  mov     edx, eax
0x180044f1a  mov     rcx, rbx
0x180044f1d  call    SdbGetStringTagPtr
0x180044f22  mov     [rsi+38h], rax
0x180044f26  mov     r8d, 601Bh
0x180044f2c  mov     edx, edi
0x180044f2e  mov     rcx, rbx
0x180044f31  call    SdbFindFirstTag
0x180044f36  test    eax, eax
0x180044f38  jz      short loc_180044F48
0x180044f3a  mov     edx, eax
0x180044f3c  mov     rcx, rbx
0x180044f3f  call    SdbGetStringTagPtr
0x180044f44  mov     [rsi+30h], rax
0x180044f48  mov     r15d, 1
0x180044f4e  test    rbp, rbp
0x180044f51  jz      short loc_180044F8F
0x180044f53  mov     rcx, rbp; hLibModule
0x180044f56  call    cs:__imp_FreeLibrary
0x180044f5c  jmp     short loc_180044F8F
0x180044f5e  lea     r9, aNoEntryWithThe; "No entry with the same HTMLHELPID for 0"...
0x180044f65  mov     r8d, 29Ah
0x180044f6b  jmp     short loc_180044F7A
0x180044f6d  lea     r9, aFailedToGetHtm; "Failed to get HTMLHELPID for entry 0x%x"
0x180044f74  mov     r8d, 293h
0x180044f7a  mov     dword ptr [rsp+0A8h+var_88], edi
0x180044f7e  lea     rdx, aSdbreadapphelp_1; "SdbReadApphelpDetailsData"
0x180044f85  mov     ecx, 1
0x180044f8a  call    AslLogCallPrintf
0x180044f8f  mov     eax, r15d
0x180044f92  mov     rcx, [rsp+0A8h+var_38]
0x180044f97  xor     rcx, rsp; StackCookie
0x180044f9a  call    __security_check_cookie
0x180044f9f  mov     rbx, [rsp+0A8h+arg_10]
0x180044fa7  add     rsp, 80h
0x180044fae  pop     r15
0x180044fb0  pop     r14
0x180044fb2  pop     rdi
0x180044fb3  pop     rsi
0x180044fb4  pop     rbp
0x180044fb5  retn
```
