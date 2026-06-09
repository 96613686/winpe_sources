# Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)

- ea: `0x1800643a4`
- end: `0x18006467f`
- name: `?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z`
- size: `731`
- prototype: `__int64 __fastcall(struct sqlite3 **this, const unsigned __int16 *, struct IAmiInventoryItem *, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18002debc`

## callees

- `0x180018a60`
- `0x1800197d4`
- `0x180044c88`
- `0x180045480`
- `0x180052eb8`
- `0x180057460`
- `0x180059920`
- `0x18005cd98`
- `0x18005d2a4`
- `0x18005f674`
- `0x18005f750`
- `0x18005fd00`
- `0x1800643a4`
- `0x180065240`
- `0x180067e58`
- `0x1800a3f24`
- `0x180130010`

## string_xrefs

- `0x1800643ef`: `TemplateItem cannot be null [%#x]`
- `0x180064432`: `TemplateItem must have a property schema defined [%#x]`
- `0x180064459`: `OpenDb failed [%#x]`
- `0x1800645b8`: `CreateReadItemQuery failed [%#x]`
- `0x1800645d9`: `CreateWriteItemQuery failed [%#x]`
- `0x1800644de`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x1800645e4`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x180064608`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x180064649`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x18006459b`: `CreateTable failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::Initialize(
        struct sqlite3 **this,
        const unsigned __int16 *a2,
        struct IAmiInventoryItem *a3,
        int a4)
{
  int Table; // ebx
  int v9; // r8d
  const char *v10; // r9
  __int64 *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rbx
  Windows::Compat::Inventory::SqliteInvCache *v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rdx
  _BYTE v19[32]; // [rsp+38h] [rbp-80h] BYREF
  _BYTE v20[32]; // [rsp+58h] [rbp-60h] BYREF

  if ( a3 )
  {
    v11 = (__int64 *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _BYTE *))(*(_QWORD *)a3 + 64LL))(a3, v19);
    v12 = *v11;
    v13 = v11[1];
    std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(v19);
    if ( v12 == v13 )
    {
      Table = -2147024809;
      v9 = 558;
      v10 = "TemplateItem must have a property schema defined [%#x]";
    }
    else
    {
      Table = Windows::Compat::Inventory::SqliteInvCache::OpenDb(a2, this + 1, a4);
      if ( Table >= 0 )
      {
        *((_BYTE *)this + 168) = a4 != 0;
        v14 = (Windows::Compat::Inventory::SqliteInvCache *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _BYTE *))(*(_QWORD *)a3 + 64LL))(
                                                              a3,
                                                              v19);
        if ( this + 17 != (struct sqlite3 **)v14 )
          std::vector<IAmiInventoryItem::_CacheItemProperty>::_Assign_counted_range<IAmiInventoryItem::_CacheItemProperty *>(
            this + 17,
            *(_QWORD *)v14,
            (__int64)(*((_QWORD *)v14 + 1) - *(_QWORD *)v14) >> 4);
        std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(v19);
        v15 = -1;
        do
          ++v15;
        while ( a2[v15] );
        std::wstring::_Assign<unsigned short>(this + 9, a2);
        if ( !this[11] )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::Initialize",
            575,
            (unsigned int)"Table name conversion failed");
          return (unsigned int)Table;
        }
        v16 = std::to_wstring(v20, 0);
        std::operator+<unsigned short>(v19, v17, v16);
        std::wstring::_Append<unsigned short>(this + 9);
        std::wstring::~wstring(v19);
        std::wstring::~wstring(v20);
        std::wstring::_Assign<unsigned short>(this + 13, L"Metadata_");
        std::to_wstring(v20, 0);
        std::wstring::_Append<unsigned short>(this + 13);
        std::wstring::~wstring(v20);
        Table = Windows::Compat::Inventory::SqliteInvCache::CreateTable((Windows::Compat::Inventory::SqliteInvCache *)this);
        if ( Table >= 0 )
        {
          Table = Windows::Compat::Inventory::SqliteInvCache::CreateReadItemQuery((Windows::Compat::Inventory::SqliteInvCache *)this);
          if ( Table >= 0 )
          {
            Table = Windows::Compat::Inventory::SqliteInvCache::CreateWriteItemQuery((Windows::Compat::Inventory::SqliteInvCache *)this);
            if ( Table >= 0 )
              return (unsigned int)Table;
            v9 = 600;
            v10 = "CreateWriteItemQuery failed [%#x]";
          }
          else
          {
            v9 = 593;
            v10 = "CreateReadItemQuery failed [%#x]";
          }
        }
        else
        {
          v9 = 586;
          v10 = "CreateTable failed [%#x]";
        }
      }
      else
      {
        v9 = 565;
        v10 = "OpenDb failed [%#x]";
      }
    }
  }
  else
  {
    Table = -2147024809;
    v9 = 551;
    v10 = "TemplateItem cannot be null [%#x]";
  }
  AslLogCallPrintf(1, (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::Initialize", v9, (_DWORD)v10);
  if ( this[1] )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::Initialize",
      607,
      (unsigned int)"closing database due to failure");
    if ( (unsigned int)sqlite3Close(this[1], 0) )
    {
      sqlite3_errmsg(this[1]);
      AslLogCallPrintf(
        1,
        (unsigned int)"Windows::Compat::Inventory::SqliteInvCache::Initialize",
        611,
        (unsigned int)"sqlite3_close failed: [%d] %hs");
    }
    this[1] = 0;
  }
  return (unsigned int)Table;
}

```

## disassembly

```asm
0x1800643a4  push    rbx
0x1800643a6  push    rbp
0x1800643a7  push    rsi
0x1800643a8  push    rdi
0x1800643a9  push    r12
0x1800643ab  push    r14
0x1800643ad  push    r15
0x1800643af  sub     rsp, 80h
0x1800643b6  mov     [rsp+0B8h+var_88], 0FFFFFFFFFFFFFFFEh
0x1800643bf  mov     rax, cs:__security_cookie
0x1800643c6  xor     rax, rsp
0x1800643c9  mov     [rsp+0B8h+var_40], rax
0x1800643ce  mov     r15d, r9d
0x1800643d1  mov     r14, r8
0x1800643d4  mov     rbp, rdx
0x1800643d7  mov     rsi, rcx
0x1800643da  xor     r12d, r12d
0x1800643dd  test    r8, r8
0x1800643e0  jnz     short loc_1800643FB
0x1800643e2  mov     eax, 80070057h
0x1800643e7  mov     ebx, eax
0x1800643e9  mov     r8d, 227h
0x1800643ef  lea     r9, aTemplateitemCa; "TemplateItem cannot be null [%#x]"
0x1800643f6  jmp     loc_1800645E0
0x1800643fb  mov     rax, [r8]
0x1800643fe  lea     rdx, [rsp+0B8h+var_80]
0x180064403  mov     rcx, r14
0x180064406  mov     rax, [rax+40h]
0x18006440a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006440f  mov     rdi, [rax]
0x180064412  mov     rbx, [rax+8]
0x180064416  lea     rcx, [rsp+0B8h+var_80]
0x18006441b  call    ?_Tidy@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAXXZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(void)
0x180064420  cmp     rdi, rbx
0x180064423  jnz     short loc_18006443E
0x180064425  mov     eax, 80070057h
0x18006442a  mov     ebx, eax
0x18006442c  mov     r8d, 22Eh
0x180064432  lea     r9, aTemplateitemMu; "TemplateItem must have a property schem"...
0x180064439  jmp     loc_1800645E0
0x18006443e  lea     rdx, [rsi+8]; struct sqlite3 **
0x180064442  mov     r8d, r15d; int
0x180064445  mov     rcx, rbp; unsigned __int16 *
0x180064448  call    ?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z; Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)
0x18006444d  mov     ebx, eax
0x18006444f  test    eax, eax
0x180064451  jns     short loc_180064465
0x180064453  mov     r8d, 235h
0x180064459  lea     r9, aOpendbFailedX; "OpenDb failed [%#x]"
0x180064460  jmp     loc_1800645E0
0x180064465  test    r15d, r15d
0x180064468  setnz   al
0x18006446b  mov     [rsi+0A8h], al
0x180064471  mov     rax, [r14]
0x180064474  lea     rdx, [rsp+0B8h+var_80]
0x180064479  mov     rcx, r14
0x18006447c  mov     rax, [rax+40h]
0x180064480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064485  nop
0x180064486  lea     rcx, [rsi+88h]
0x18006448d  cmp     rcx, rax
0x180064490  jz      short loc_1800644A6
0x180064492  mov     r8, [rax+8]
0x180064496  sub     r8, [rax]
0x180064499  sar     r8, 4
0x18006449d  mov     rdx, [rax]
0x1800644a0  call    ??$_Assign_counted_range@PEAU_CacheItemProperty@IAmiInventoryItem@@@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAXPEAU_CacheItemProperty@IAmiInventoryItem@@_K@Z; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Assign_counted_range<IAmiInventoryItem::_CacheItemProperty *>(IAmiInventoryItem::_CacheItemProperty *,unsigned __int64)
0x1800644a5  nop
0x1800644a6  lea     rcx, [rsp+0B8h+var_80]
0x1800644ab  call    ?_Tidy@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAXXZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(void)
0x1800644b0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800644b4  inc     r8
0x1800644b7  cmp     [rbp+r8*2+0], r12w
0x1800644bd  jnz     short loc_1800644B4
0x1800644bf  mov     rdx, rbp
0x1800644c2  lea     rcx, [rsi+48h]
0x1800644c6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800644cb  cmp     [rsi+58h], r12
0x1800644cf  jnz     short loc_1800644F4
0x1800644d1  lea     r9, aTableNameConve; "Table name conversion failed"
0x1800644d8  mov     r8d, 23Fh
0x1800644de  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800644e5  mov     ecx, 1
0x1800644ea  call    AslLogCallPrintf
0x1800644ef  jmp     loc_18006465E
0x1800644f4  xor     edx, edx
0x1800644f6  lea     rcx, [rsp+0B8h+var_60]
0x1800644fb  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x180064500  nop
0x180064501  mov     r8, rax
0x180064504  lea     rcx, [rsp+0B8h+var_80]
0x180064509  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18006450e  nop
0x18006450f  mov     r8, [rax+10h]
0x180064513  cmp     qword ptr [rax+18h], 7
0x180064518  jbe     short loc_18006451D
0x18006451a  mov     rax, [rax]
0x18006451d  mov     rdx, rax
0x180064520  lea     rcx, [rsi+48h]; Src
0x180064524  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180064529  nop
0x18006452a  lea     rcx, [rsp+0B8h+var_80]
0x18006452f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180064534  nop
0x180064535  lea     rcx, [rsp+0B8h+var_60]
0x18006453a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006453f  mov     r8d, 9
0x180064545  lea     rdx, aMetadata; "Metadata_"
0x18006454c  lea     rcx, [rsi+68h]
0x180064550  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180064555  xor     edx, edx
0x180064557  lea     rcx, [rsp+0B8h+var_60]
0x18006455c  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x180064561  nop
0x180064562  mov     r8, [rax+10h]
0x180064566  cmp     qword ptr [rax+18h], 7
0x18006456b  jbe     short loc_180064570
0x18006456d  mov     rax, [rax]
0x180064570  mov     rdx, rax
0x180064573  lea     rcx, [rsi+68h]; Src
0x180064577  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18006457c  nop
0x18006457d  lea     rcx, [rsp+0B8h+var_60]
0x180064582  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180064587  mov     rcx, rsi; this
0x18006458a  call    ?CreateTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateTable(void)
0x18006458f  mov     ebx, eax
0x180064591  test    eax, eax
0x180064593  jns     short loc_1800645A4
0x180064595  mov     r8d, 24Ah
0x18006459b  lea     r9, aCreatetableFai; "CreateTable failed [%#x]"
0x1800645a2  jmp     short loc_1800645E0
0x1800645a4  mov     rcx, rsi; this
0x1800645a7  call    ?CreateReadItemQuery@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateReadItemQuery(void)
0x1800645ac  mov     ebx, eax
0x1800645ae  test    eax, eax
0x1800645b0  jns     short loc_1800645C1
0x1800645b2  mov     r8d, 251h
0x1800645b8  lea     r9, aCreatereaditem; "CreateReadItemQuery failed [%#x]"
0x1800645bf  jmp     short loc_1800645E0
0x1800645c1  mov     rcx, rsi; this
0x1800645c4  call    ?CreateWriteItemQuery@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateWriteItemQuery(void)
0x1800645c9  mov     ebx, eax
0x1800645cb  test    eax, eax
0x1800645cd  jns     loc_18006465E
0x1800645d3  mov     r8d, 258h
0x1800645d9  lea     r9, aCreatewriteite; "CreateWriteItemQuery failed [%#x]"
0x1800645e0  mov     [rsp+0B8h+var_98], eax
0x1800645e4  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800645eb  mov     ecx, 1
0x1800645f0  call    AslLogCallPrintf
0x1800645f5  cmp     [rsi+8], r12
0x1800645f9  jz      short loc_18006465E
0x1800645fb  lea     r9, aClosingDatabas; "closing database due to failure"
0x180064602  mov     r8d, 25Fh
0x180064608  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::SqliteInvCa"...
0x18006460f  mov     ecx, 3
0x180064614  call    AslLogCallPrintf
0x180064619  xor     edx, edx
0x18006461b  mov     rcx, [rsi+8]
0x18006461f  call    sqlite3Close
0x180064624  mov     edi, eax
0x180064626  test    eax, eax
0x180064628  jz      short loc_18006465A
0x18006462a  mov     rcx, [rsi+8]
0x18006462e  call    sqlite3_errmsg
0x180064633  mov     [rsp+0B8h+var_90], rax
0x180064638  mov     [rsp+0B8h+var_98], edi
0x18006463c  lea     r9, aSqlite3CloseFa; "sqlite3_close failed: [%d] %hs"
0x180064643  mov     r8d, 263h
0x180064649  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::SqliteInvCa"...
0x180064650  mov     ecx, 1
0x180064655  call    AslLogCallPrintf
0x18006465a  mov     [rsi+8], r12
0x18006465e  mov     eax, ebx
0x180064660  mov     rcx, [rsp+0B8h+var_40]
0x180064665  xor     rcx, rsp; StackCookie
0x180064668  call    __security_check_cookie
0x18006466d  add     rsp, 80h
0x180064674  pop     r15
0x180064676  pop     r14
0x180064678  pop     r12
0x18006467a  pop     rdi
0x18006467b  pop     rsi
0x18006467c  pop     rbp
0x18006467d  pop     rbx
0x18006467e  retn
```
