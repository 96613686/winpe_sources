# Windows::Compat::Inventory::SqliteInvCache::DropTable(void)

- ea: `0x180018fd8`
- end: `0x18001934e`
- name: `?DropTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ`
- size: `886`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800171f0`

## callees

- `0x180004ea0`
- `0x18001209c`
- `0x1800134b8`
- `0x1800149a8`
- `0x180018fd8`
- `0x1800276cc`
- `0x180027d3c`
- `0x180027dbc`
- `0x18004c020`
- `0x1800a494c`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019241`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001922e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001922e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001913f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800192b7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001913f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800192b7`

## string_xrefs

- `0x180019104`: `Windows::Compat::Inventory::SqliteInvCache::DropTable`
- `0x180019172`: `Windows::Compat::Inventory::SqliteInvCache::DropTable`
- `0x1800192ea`: `Windows::Compat::Inventory::SqliteInvCache::DropTable`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::DropTable(
        Windows::Compat::Inventory::SqliteInvCache *this,
        __int64 a2,
        __int64 a3)
{
  int v4; // r12d
  _QWORD *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int128 *v8; // rdx
  signed int v9; // edi
  const char *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // ebx
  const char *v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rax
  DWORD LastError; // ebx
  __int128 *v18; // rdx
  int v19; // ebx
  __int64 v20; // r12
  __int64 v21; // rax
  const char *v22; // r9
  __int64 v23; // r8
  int i; // r15d
  __int64 v26; // [rsp+20h] [rbp-69h]
  __int64 v27; // [rsp+40h] [rbp-49h] BYREF
  __int128 v28; // [rsp+48h] [rbp-41h] BYREF
  __int128 v29; // [rsp+58h] [rbp-31h]
  _OWORD Src[2]; // [rsp+68h] [rbp-21h] BYREF
  char *v31[4]; // [rsp+88h] [rbp-1h] BYREF

  v4 = 0;
  v5 = (_QWORD *)((char *)this + 72);
  v6 = *((_QWORD *)this + 11);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v6) < 0x15 )
    std::_Xlen_string();
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::wstring(Src, v5, a3, L"DROP TABLE IF EXISTS ", 21, v5, v6);
  v7 = std::wstring::append(Src, L";");
  v28 = 0;
  v29 = 0;
  v28 = *(_OWORD *)v7;
  v29 = *(_OWORD *)(v7 + 16);
  *(_QWORD *)(v7 + 16) = 0;
  *(_QWORD *)(v7 + 24) = 7;
  *(_WORD *)v7 = 0;
  std::wstring::~wstring((char **)Src);
  std::list<std::wstring>::clear((char *)this + 24);
  std::list<std::wstring>::clear((char *)this + 48);
  v27 = 0;
  v8 = &v28;
  if ( *((_QWORD *)&v29 + 1) > 7u )
    LODWORD(v8) = v28;
  v9 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v8, -1, 128, (__int64)&v27, 0);
  if ( v9 )
  {
    v10 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::DropTable",
      1544,
      "sqlite3_exec failed: [%d] %hs",
      v9,
      v10);
    if ( v9 <= 0 )
      goto LABEL_17;
    v9 = (unsigned __int16)v9;
    goto LABEL_9;
  }
  v9 = 0;
  do
  {
    v13 = sqlite3_step(v27);
    if ( (unsigned int)(v13 - 5) > 1 )
      break;
    Sleep(5u);
    ++v4;
  }
  while ( v4 < 100 );
  if ( v13 != 101 )
  {
    v14 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::DropTable",
      1552,
      "sqlite3_step failed: [%d] %hs",
      v13,
      v14);
    if ( v13 > 0 )
    {
      v9 = (unsigned __int16)v13;
LABEL_9:
      v9 |= 0x80070000;
      goto LABEL_17;
    }
    v9 = v13;
  }
LABEL_17:
  v15 = (_QWORD *)((char *)this + 104);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *((_QWORD *)this + 15)) < 0x15 )
    std::_Xlen_string();
  if ( *((_QWORD *)this + 16) > 7u )
    v15 = (_QWORD *)*v15;
  std::wstring::wstring(v31, v11, v12, L"DROP TABLE IF EXISTS ", 21, v15, *((_QWORD *)this + 15));
  v16 = std::wstring::append(v31, L";");
  Src[0] = *(_OWORD *)v16;
  Src[1] = *(_OWORD *)(v16 + 16);
  *(_QWORD *)(v16 + 16) = 0;
  *(_QWORD *)(v16 + 24) = 7;
  *(_WORD *)v16 = 0;
  std::wstring::operator=(&v28, Src);
  std::wstring::~wstring((char **)Src);
  std::wstring::~wstring(v31);
  if ( v27 )
  {
    LastError = GetLastError();
    sqlite3_finalize(v27);
    SetLastError(LastError);
  }
  v27 = 0;
  v18 = &v28;
  if ( *((_QWORD *)&v29 + 1) > 7u )
    LODWORD(v18) = v28;
  v19 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v18, -1, 128, (__int64)&v27, 0);
  v20 = v27;
  if ( v19 )
  {
    v21 = sqlite3_errmsg(*((_QWORD *)this + 1));
    v22 = "sqlite3_exec failed: [%d] %hs";
    v23 = 1562;
  }
  else
  {
    for ( i = 0; i < 100; ++i )
    {
      v19 = sqlite3_step(v20);
      if ( (unsigned int)(v19 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v19 == 101 )
      goto LABEL_34;
    v21 = sqlite3_errmsg(*((_QWORD *)this + 1));
    v22 = "sqlite3_step failed: [%d] %hs";
    v23 = 1570;
  }
  LODWORD(v26) = v19;
  AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::DropTable", v23, v22, v26, v21);
  if ( v19 > 0 )
    v9 = (unsigned __int16)v19 | 0x80070000;
  else
    v9 = v19;
LABEL_34:
  if ( v20 )
    sqlite3_finalize(v20);
  std::wstring::~wstring((char **)&v28);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180018fd8  push    rbp
0x180018fda  push    rbx
0x180018fdb  push    rdi
0x180018fdc  push    r12
0x180018fde  push    r14
0x180018fe0  push    r15
0x180018fe2  lea     rbp, [rsp-2Fh]
0x180018fe7  sub     rsp, 0B8h
0x180018fee  mov     rax, cs:__security_cookie
0x180018ff5  xor     rax, rsp
0x180018ff8  mov     [rbp+57h+var_38], rax
0x180018ffc  mov     r14, rcx
0x180018fff  xor     r12d, r12d
0x180019002  lea     rdx, [rcx+48h]
0x180019006  mov     rcx, [rdx+10h]
0x18001900a  mov     r15, 7FFFFFFFFFFFFFFEh
0x180019014  mov     rax, r15
0x180019017  sub     rax, rcx
0x18001901a  cmp     rax, 15h
0x18001901e  jb      loc_180019348
0x180019024  cmp     qword ptr [rdx+18h], 7
0x180019029  jbe     short loc_18001902E
0x18001902b  mov     rdx, [rdx]
0x18001902e  mov     [rsp+0E0h+var_B0], rcx
0x180019033  mov     [rsp+0E0h+var_B8], rdx
0x180019038  mov     [rsp+0E0h+var_C0], 15h
0x180019041  lea     r9, aDropTableIfExi; "DROP TABLE IF EXISTS "
0x180019048  lea     rcx, [rbp+57h+Src]
0x18001904c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180019051  nop
0x180019052  lea     rdx, asc_1800F5790; ";"
0x180019059  lea     rcx, [rbp+57h+Src]; Src
0x18001905d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180019062  xorps   xmm0, xmm0
0x180019065  movups  [rbp+57h+var_98], xmm0
0x180019069  xorps   xmm1, xmm1
0x18001906c  movdqu  [rbp+57h+var_88], xmm1
0x180019071  movups  xmm0, xmmword ptr [rax]
0x180019074  movups  [rbp+57h+var_98], xmm0
0x180019078  movups  xmm1, xmmword ptr [rax+10h]
0x18001907c  movups  [rbp+57h+var_88], xmm1
0x180019080  mov     [rax+10h], r12
0x180019084  mov     qword ptr [rax+18h], 7
0x18001908c  mov     [rax], r12w
0x180019090  lea     rcx, [rbp+57h+Src]
0x180019094  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019099  nop
0x18001909a  lea     rcx, [r14+18h]
0x18001909e  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x1800190a3  lea     rcx, [r14+30h]
0x1800190a7  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x1800190ac  mov     [rbp+57h+var_A0], r12
0x1800190b0  lea     rdx, [rbp+57h+var_98]
0x1800190b4  cmp     qword ptr [rbp+57h+var_88+8], 7
0x1800190b9  cmova   rdx, qword ptr [rbp+57h+var_98]
0x1800190be  mov     [rsp+0E0h+var_B8], r12
0x1800190c3  lea     rax, [rbp+57h+var_A0]
0x1800190c7  mov     [rsp+0E0h+var_C0], rax
0x1800190cc  mov     r9d, 80h
0x1800190d2  or      r8d, 0FFFFFFFFh
0x1800190d6  mov     rcx, [r14+8]
0x1800190da  call    sqlite3Prepare16
0x1800190df  mov     edi, eax
0x1800190e1  test    eax, eax
0x1800190e3  jz      short loc_180019124
0x1800190e5  mov     rcx, [r14+8]
0x1800190e9  call    sqlite3_errmsg
0x1800190ee  mov     [rsp+0E0h+var_B8], rax
0x1800190f3  mov     dword ptr [rsp+0E0h+var_C0], edi
0x1800190f7  lea     r9, aSqlite3ExecFai; "sqlite3_exec failed: [%d] %hs"
0x1800190fe  mov     r8d, 608h
0x180019104  lea     rdx, aWindowsCompatI_0; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001910b  mov     ecx, 1
0x180019110  call    AslLogCallPrintf
0x180019115  test    edi, edi
0x180019117  jle     short loc_180019196
0x180019119  movzx   edi, di
0x18001911c  or      edi, 80070000h
0x180019122  jmp     short loc_180019196
0x180019124  mov     edi, r12d
0x180019127  mov     rcx, [rbp+57h+var_A0]
0x18001912b  call    sqlite3_step
0x180019130  mov     ebx, eax
0x180019132  lea     ecx, [rax-5]
0x180019135  cmp     ecx, 1
0x180019138  ja      short loc_18001914E
0x18001913a  mov     ecx, 5; dwMilliseconds
0x18001913f  call    cs:__imp_Sleep
0x180019145  inc     r12d
0x180019148  cmp     r12d, 64h ; 'd'
0x18001914c  jl      short loc_180019127
0x18001914e  cmp     ebx, 65h ; 'e'
0x180019151  jz      short loc_180019193
0x180019153  mov     rcx, [r14+8]
0x180019157  call    sqlite3_errmsg
0x18001915c  mov     [rsp+0E0h+var_B8], rax
0x180019161  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180019165  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18001916c  mov     r8d, 610h
0x180019172  lea     rdx, aWindowsCompatI_0; "Windows::Compat::Inventory::SqliteInvCa"...
0x180019179  mov     ecx, 1
0x18001917e  call    AslLogCallPrintf
0x180019183  xor     r12d, r12d
0x180019186  test    ebx, ebx
0x180019188  jg      short loc_18001918E
0x18001918a  mov     edi, ebx
0x18001918c  jmp     short loc_180019196
0x18001918e  movzx   edi, bx
0x180019191  jmp     short loc_18001911C
0x180019193  xor     r12d, r12d
0x180019196  lea     rax, [r14+68h]
0x18001919a  mov     rcx, [rax+10h]
0x18001919e  sub     r15, rcx
0x1800191a1  cmp     r15, 15h
0x1800191a5  jb      loc_180019342
0x1800191ab  cmp     qword ptr [rax+18h], 7
0x1800191b0  jbe     short loc_1800191B5
0x1800191b2  mov     rax, [rax]
0x1800191b5  mov     [rsp+0E0h+var_B0], rcx
0x1800191ba  mov     [rsp+0E0h+var_B8], rax
0x1800191bf  mov     [rsp+0E0h+var_C0], 15h
0x1800191c8  lea     r9, aDropTableIfExi; "DROP TABLE IF EXISTS "
0x1800191cf  lea     rcx, [rbp+57h+var_58]
0x1800191d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800191d8  nop
0x1800191d9  lea     rdx, asc_1800F5790; ";"
0x1800191e0  lea     rcx, [rbp+57h+var_58]; Src
0x1800191e4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800191e9  movups  xmm0, xmmword ptr [rax]
0x1800191ec  movups  [rbp+57h+Src], xmm0
0x1800191f0  movups  xmm1, xmmword ptr [rax+10h]
0x1800191f4  movups  [rbp+57h+var_68], xmm1
0x1800191f8  mov     [rax+10h], r12
0x1800191fc  mov     qword ptr [rax+18h], 7
0x180019204  mov     [rax], r12w
0x180019208  lea     rdx, [rbp+57h+Src]
0x18001920c  lea     rcx, [rbp+57h+var_98]
0x180019210  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180019215  lea     rcx, [rbp+57h+Src]
0x180019219  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001921e  nop
0x18001921f  lea     rcx, [rbp+57h+var_58]
0x180019223  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019228  cmp     [rbp+57h+var_A0], r12
0x18001922c  jz      short loc_180019248
0x18001922e  call    cs:__imp_GetLastError
0x180019234  mov     ebx, eax
0x180019236  mov     rcx, [rbp+57h+var_A0]
0x18001923a  call    sqlite3_finalize
0x18001923f  mov     ecx, ebx; dwErrCode
0x180019241  call    cs:__imp_SetLastError
0x180019247  nop
0x180019248  mov     [rbp+57h+var_A0], r12
0x18001924c  lea     rdx, [rbp+57h+var_98]
0x180019250  cmp     qword ptr [rbp+57h+var_88+8], 7
0x180019255  cmova   rdx, qword ptr [rbp+57h+var_98]
0x18001925a  mov     [rsp+0E0h+var_B8], r12
0x18001925f  lea     rax, [rbp+57h+var_A0]
0x180019263  mov     [rsp+0E0h+var_C0], rax
0x180019268  mov     r9d, 80h
0x18001926e  or      r8d, 0FFFFFFFFh
0x180019272  mov     rcx, [r14+8]
0x180019276  call    sqlite3Prepare16
0x18001927b  mov     ebx, eax
0x18001927d  mov     r12, [rbp+57h+var_A0]
0x180019281  test    eax, eax
0x180019283  jz      short loc_18001929D
0x180019285  mov     rcx, [r14+8]
0x180019289  call    sqlite3_errmsg
0x18001928e  lea     r9, aSqlite3ExecFai; "sqlite3_exec failed: [%d] %hs"
0x180019295  mov     r8d, 61Ah
0x18001929b  jmp     short loc_1800192E1
0x18001929d  xor     r15d, r15d
0x1800192a0  mov     rcx, r12
0x1800192a3  call    sqlite3_step
0x1800192a8  mov     ebx, eax
0x1800192aa  lea     ecx, [rax-5]
0x1800192ad  cmp     ecx, 1
0x1800192b0  ja      short loc_1800192C6
0x1800192b2  mov     ecx, 5; dwMilliseconds
0x1800192b7  call    cs:__imp_Sleep
0x1800192bd  inc     r15d
0x1800192c0  cmp     r15d, 64h ; 'd'
0x1800192c4  jl      short loc_1800192A0
0x1800192c6  cmp     ebx, 65h ; 'e'
0x1800192c9  jz      short loc_18001930C
0x1800192cb  mov     rcx, [r14+8]
0x1800192cf  call    sqlite3_errmsg
0x1800192d4  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x1800192db  mov     r8d, 622h
0x1800192e1  mov     [rsp+0E0h+var_B8], rax
0x1800192e6  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800192ea  lea     rdx, aWindowsCompatI_0; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800192f1  mov     ecx, 1
0x1800192f6  call    AslLogCallPrintf
0x1800192fb  test    ebx, ebx
0x1800192fd  jg      short loc_180019303
0x1800192ff  mov     edi, ebx
0x180019301  jmp     short loc_18001930C
0x180019303  movzx   edi, bx
0x180019306  or      edi, 80070000h
0x18001930c  test    r12, r12
0x18001930f  jz      short loc_18001931A
0x180019311  mov     rcx, r12
0x180019314  call    sqlite3_finalize
0x180019319  nop
0x18001931a  lea     rcx, [rbp+57h+var_98]
0x18001931e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019323  mov     eax, edi
0x180019325  mov     rcx, [rbp+57h+var_38]
0x180019329  xor     rcx, rsp; StackCookie
0x18001932c  call    __security_check_cookie
0x180019331  add     rsp, 0B8h
0x180019338  pop     r15
0x18001933a  pop     r14
0x18001933c  pop     r12
0x18001933e  pop     rdi
0x18001933f  pop     rbx
0x180019340  pop     rbp
0x180019341  retn
0x180019342  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180019348  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
