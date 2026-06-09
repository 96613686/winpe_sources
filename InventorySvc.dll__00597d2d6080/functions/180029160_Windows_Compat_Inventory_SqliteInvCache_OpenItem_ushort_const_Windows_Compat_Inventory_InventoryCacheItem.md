# Windows::Compat::Inventory::SqliteInvCache::OpenItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x180029160`
- end: `0x18002942c`
- name: `?OpenItem@SqliteInvCache@Inventory@Compat@Windows@@UEBAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `716`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180002bf0`
- `0x180002c40`
- `0x180006a04`
- `0x1800074f0`
- `0x1800152d0`
- `0x1800201a4`
- `0x180022d98`
- `0x180029160`
- `0x180036be4`
- `0x1800817cc`
- `0x1800a1980`
- `0x1800a22c0`
- `0x1800a4690`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029274`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029274`

## string_xrefs

- `0x18002930d`: `CreateWriteStatement failed [%#x]`
- `0x1800292b9`: `Windows::Compat::Inventory::SqliteInvCache::OpenItem`
- `0x18002931a`: `Windows::Compat::Inventory::SqliteInvCache::OpenItem`
- `0x1800293ca`: `Windows::Compat::Inventory::SqliteInvCache::OpenItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::OpenItem(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        struct Windows::Compat::Inventory::InventoryCacheItem **a3)
{
  int v3; // edi
  __int64 v5; // r12
  _QWORD *v6; // rdx
  int v7; // eax
  int v8; // ebx
  __int64 v9; // r15
  signed int v10; // r14d
  const char *v11; // rax
  int v12; // eax
  int i; // esi
  __int64 v14; // rax
  int v15; // eax
  struct Windows::Compat::Inventory::InventoryCacheItem *v16; // rsi
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v20; // [rsp+20h] [rbp-60h]
  __int64 v21; // [rsp+28h] [rbp-58h]
  __int64 v22; // [rsp+30h] [rbp-50h] BYREF
  __int64 v23; // [rsp+38h] [rbp-48h]
  const char *v24; // [rsp+40h] [rbp-40h]
  __int64 v25; // [rsp+48h] [rbp-38h] BYREF
  struct Windows::Compat::Inventory::InventoryCacheItem **v26; // [rsp+50h] [rbp-30h]
  __int128 v27; // [rsp+58h] [rbp-28h] BYREF
  __int64 v28; // [rsp+68h] [rbp-18h]
  __int64 v29; // [rsp+70h] [rbp-10h]

  v26 = a3;
  v3 = (int)a2;
  v5 = 0;
  v22 = 0;
  v25 = 0;
  v6 = (_QWORD *)((char *)this + 176);
  if ( *((_QWORD *)this + 25) > 7u )
    v6 = (_QWORD *)*v6;
  v7 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v6, -1, 128, (__int64)&v25, 0);
  v8 = v7;
  v9 = v25;
  if ( v7 )
  {
    if ( v7 > 0 )
      v10 = (unsigned __int16)v7 | 0x80070000;
    else
      v10 = v7;
    v23 = 629;
    v11 = "sqlite3_prepare_v2 failed: [%d] %hs";
    goto LABEL_24;
  }
  if ( v25 )
  {
    LOBYTE(v21) = 2;
    v12 = bindText(v25, 1, v3, -2, 0, v21);
    v8 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v10 = (unsigned __int16)v12 | 0x80070000;
      else
        v10 = v12;
      v23 = 644;
      v11 = "sqlite3_bind_text16 failed: [%d] %hs";
      goto LABEL_24;
    }
    for ( i = 0; i < 100; ++i )
    {
      v8 = sqlite3_step(v9);
      if ( (unsigned int)(v8 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v8 == 101 )
    {
      v10 = -2147024894;
    }
    else
    {
      if ( v8 != 100 )
      {
        if ( v8 > 0 )
          v10 = (unsigned __int16)v8 | 0x80070000;
        else
          v10 = v8;
        v23 = 658;
        v11 = "sqlite3_step failed: [%d] %hs";
LABEL_24:
        v24 = v11;
        v14 = sqlite3_errmsg(*((_QWORD *)this + 1));
        LODWORD(v20) = v8;
        AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::OpenItem", v23, v24, v20, v14);
        if ( v10 >= 0 )
          goto LABEL_31;
        goto LABEL_30;
      }
      v15 = Windows::Compat::Inventory::SqliteInvCache::CreateWriteStatement(this, &v22);
      v10 = v15;
      if ( v15 >= 0 )
      {
        v16 = (struct Windows::Compat::Inventory::InventoryCacheItem *)operator new(0x58u);
        v23 = (__int64)v16;
        v17 = v9;
        v9 = 0;
        v25 = 0;
        v18 = v22;
        v5 = 0;
        v22 = 0;
        v27 = 0;
        v28 = 0;
        v29 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v27);
        Windows::Compat::Inventory::SqliteInvCacheItem::SqliteInvCacheItem(
          (__int64)v16,
          (__int64)&v27,
          (__int64)this + 136,
          v18,
          v17);
        std::wstring::~wstring(&v27);
        *(_QWORD *)v16 = &Windows::Compat::Inventory::SqliteInvCacheItem::`vftable';
        *v26 = v16;
        goto LABEL_31;
      }
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::OpenItem",
        665,
        "CreateWriteStatement failed [%#x]",
        v15);
      v5 = v22;
    }
  }
  else
  {
    v10 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::OpenItem",
      635,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
  }
LABEL_30:
  *v26 = 0;
LABEL_31:
  if ( v5 )
    sqlite3_finalize(v5);
  if ( v9 )
    sqlite3_finalize(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180029160  mov     [rsp-38h+arg_18], rbx
0x180029165  push    rbp
0x180029166  push    rsi
0x180029167  push    rdi
0x180029168  push    r12
0x18002916a  push    r13
0x18002916c  push    r14
0x18002916e  push    r15
0x180029170  mov     rbp, rsp
0x180029173  sub     rsp, 80h
0x18002917a  mov     rax, cs:__security_cookie
0x180029181  xor     rax, rsp
0x180029184  mov     [rbp+var_8], rax
0x180029188  mov     [rbp+var_30], r8
0x18002918c  mov     rdi, rdx
0x18002918f  mov     r13, rcx
0x180029192  xor     r14d, r14d
0x180029195  mov     r12d, r14d
0x180029198  mov     [rbp+var_50], r14
0x18002919c  mov     [rbp+var_38], r14
0x1800291a0  lea     rdx, [rcx+0B0h]
0x1800291a7  cmp     qword ptr [rdx+18h], 7
0x1800291ac  jbe     short loc_1800291B1
0x1800291ae  mov     rdx, [rdx]
0x1800291b1  mov     [rsp+80h+var_58], r14
0x1800291b6  lea     rax, [rbp+var_38]
0x1800291ba  mov     [rsp+80h+var_60], rax
0x1800291bf  mov     r9d, 80h
0x1800291c5  or      r8d, 0FFFFFFFFh
0x1800291c9  mov     rcx, [rcx+8]
0x1800291cd  call    sqlite3Prepare16
0x1800291d2  mov     ebx, eax
0x1800291d4  mov     r15, [rbp+var_38]
0x1800291d8  test    eax, eax
0x1800291da  jz      short loc_180029207
0x1800291dc  jg      short loc_1800291E3
0x1800291de  mov     r14d, eax
0x1800291e1  jmp     short loc_1800291EE
0x1800291e3  movzx   r14d, ax
0x1800291e7  or      r14d, 80070000h
0x1800291ee  mov     edi, 1
0x1800291f3  mov     [rbp+var_48], 275h
0x1800291fb  lea     rax, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x180029202  jmp     loc_1800292B9
0x180029207  test    r15, r15
0x18002920a  jz      loc_1800293B2
0x180029210  mov     byte ptr [rsp+80h+var_58], 2
0x180029215  mov     [rsp+80h+var_60], r14
0x18002921a  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180029221  mov     r8, rdi
0x180029224  lea     edi, [r9+3]
0x180029228  mov     edx, edi
0x18002922a  mov     rcx, r15
0x18002922d  call    bindText
0x180029232  mov     ebx, eax
0x180029234  test    eax, eax
0x180029236  jz      short loc_18002925B
0x180029238  jg      short loc_18002923F
0x18002923a  mov     r14d, eax
0x18002923d  jmp     short loc_18002924A
0x18002923f  movzx   r14d, ax
0x180029243  or      r14d, 80070000h
0x18002924a  mov     [rbp+var_48], 284h
0x180029252  lea     rax, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180029259  jmp     short loc_1800292B9
0x18002925b  mov     esi, r14d
0x18002925e  mov     rcx, r15
0x180029261  call    sqlite3_step
0x180029266  mov     ebx, eax
0x180029268  add     eax, 0FFFFFFFBh
0x18002926b  cmp     eax, edi
0x18002926d  ja      short loc_180029281
0x18002926f  mov     ecx, 5; dwMilliseconds
0x180029274  call    cs:__imp_Sleep
0x18002927a  add     esi, edi
0x18002927c  cmp     esi, 64h ; 'd'
0x18002927f  jl      short loc_18002925E
0x180029281  cmp     ebx, 65h ; 'e'
0x180029284  jnz     short loc_180029291
0x180029286  mov     r14d, 80070002h
0x18002928c  jmp     loc_1800293DB
0x180029291  cmp     ebx, 64h ; 'd'
0x180029294  jz      short loc_1800292F6
0x180029296  test    ebx, ebx
0x180029298  jg      short loc_18002929F
0x18002929a  mov     r14d, ebx
0x18002929d  jmp     short loc_1800292AA
0x18002929f  movzx   r14d, bx
0x1800292a3  or      r14d, 80070000h
0x1800292aa  mov     [rbp+var_48], 292h
0x1800292b2  lea     rax, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x1800292b9  lea     rsi, aWindowsCompatI_37; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800292c0  mov     [rbp+var_40], rax
0x1800292c4  mov     rcx, [r13+8]
0x1800292c8  call    sqlite3_errmsg
0x1800292cd  mov     [rsp+80h+var_58], rax
0x1800292d2  mov     dword ptr [rsp+80h+var_60], ebx
0x1800292d6  mov     r9, [rbp+var_40]
0x1800292da  mov     r8, [rbp+var_48]
0x1800292de  mov     rdx, rsi
0x1800292e1  mov     ecx, edi
0x1800292e3  call    AslLogCallPrintf
0x1800292e8  test    r14d, r14d
0x1800292eb  jns     loc_1800293E6
0x1800292f1  jmp     loc_1800293DB
0x1800292f6  lea     rdx, [rbp+var_50]
0x1800292fa  mov     rcx, r13
0x1800292fd  call    ?CreateWriteStatement@SqliteInvCache@Inventory@Compat@Windows@@AEBAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@P6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Compat::Inventory::SqliteInvCache::CreateWriteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (*)(sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>> &)
0x180029302  mov     r14d, eax
0x180029305  test    eax, eax
0x180029307  jns     short loc_180029331
0x180029309  mov     dword ptr [rsp+80h+var_60], eax
0x18002930d  lea     r9, aCreatewritesta; "CreateWriteStatement failed [%#x]"
0x180029314  mov     r8d, 299h
0x18002931a  lea     rdx, aWindowsCompatI_37; "Windows::Compat::Inventory::SqliteInvCa"...
0x180029321  mov     ecx, edi
0x180029323  call    AslLogCallPrintf
0x180029328  mov     r12, [rbp+var_50]
0x18002932c  jmp     loc_1800293DB
0x180029331  mov     ecx, 58h ; 'X'; Size
0x180029336  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002933b  mov     rsi, rax
0x18002933e  mov     [rbp+var_48], rax
0x180029342  mov     rdi, r15
0x180029345  xor     r15d, r15d
0x180029348  mov     [rbp+var_38], r15
0x18002934c  mov     rbx, [rbp+var_50]
0x180029350  xor     r12d, r12d
0x180029353  mov     [rbp+var_50], r12
0x180029357  xorps   xmm0, xmm0
0x18002935a  movups  [rbp+var_28], xmm0
0x18002935e  mov     [rbp+var_18], r12
0x180029362  mov     [rbp+var_10], r12
0x180029366  xor     r8d, r8d
0x180029369  lea     rdx, cchOriginalDestLength
0x180029370  lea     rcx, [rbp+var_28]
0x180029374  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180029379  nop
0x18002937a  lea     r8, [r13+88h]
0x180029381  mov     [rsp+80h+var_60], rdi
0x180029386  mov     r9, rbx
0x180029389  lea     rdx, [rbp+var_28]
0x18002938d  mov     rcx, rsi
0x180029390  call    ??0SqliteInvCacheItem@Inventory@Compat@Windows@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@5@PEAUsqlite3_stmt@@2@Z; Windows::Compat::Inventory::SqliteInvCacheItem::SqliteInvCacheItem(std::wstring const &,std::vector<IAmiInventoryItem::_CacheItemProperty> const &,sqlite3_stmt *,sqlite3_stmt *)
0x180029395  nop
0x180029396  lea     rcx, [rbp+var_28]; void *
0x18002939a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002939f  lea     rax, ??_7SqliteInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::SqliteInvCacheItem::`vftable'
0x1800293a6  mov     [rsi], rax
0x1800293a9  mov     rax, [rbp+var_30]
0x1800293ad  mov     [rax], rsi
0x1800293b0  jmp     short loc_1800293E6
0x1800293b2  mov     r14d, 80004005h
0x1800293b8  mov     dword ptr [rsp+80h+var_60], r14d
0x1800293bd  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x1800293c4  mov     r8d, 27Bh
0x1800293ca  lea     rdx, aWindowsCompatI_37; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800293d1  mov     ecx, 1
0x1800293d6  call    AslLogCallPrintf
0x1800293db  mov     rax, [rbp+var_30]
0x1800293df  mov     qword ptr [rax], 0
0x1800293e6  test    r12, r12
0x1800293e9  jz      short loc_1800293F4
0x1800293eb  mov     rcx, r12
0x1800293ee  call    sqlite3_finalize
0x1800293f3  nop
0x1800293f4  test    r15, r15
0x1800293f7  jz      short loc_180029402
0x1800293f9  mov     rcx, r15
0x1800293fc  call    sqlite3_finalize
0x180029401  nop
0x180029402  mov     eax, r14d
0x180029405  mov     rcx, [rbp+var_8]
0x180029409  xor     rcx, rsp; StackCookie
0x18002940c  call    __security_check_cookie
0x180029411  mov     rbx, [rsp+80h+arg_18]
0x180029419  add     rsp, 80h
0x180029420  pop     r15
0x180029422  pop     r14
0x180029424  pop     r13
0x180029426  pop     r12
0x180029428  pop     rdi
0x180029429  pop     rsi
0x18002942a  pop     rbp
0x18002942b  retn
```
