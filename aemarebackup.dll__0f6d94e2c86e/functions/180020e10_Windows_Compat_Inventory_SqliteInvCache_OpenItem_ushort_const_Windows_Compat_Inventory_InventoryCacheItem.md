# Windows::Compat::Inventory::SqliteInvCache::OpenItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x180020e10`
- end: `0x1800210dc`
- name: `?OpenItem@SqliteInvCache@Inventory@Compat@Windows@@UEBAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `716`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180004ea0`
- `0x180006cec`
- `0x18000fb60`
- `0x180012ad8`
- `0x1800134b8`
- `0x180018eb0`
- `0x180020e10`
- `0x18004c020`
- `0x180059d64`
- `0x1800a494c`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020f24`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020f24`

## string_xrefs

- `0x180020fbd`: `CreateWriteStatement failed [%#x]`
- `0x180020f69`: `Windows::Compat::Inventory::SqliteInvCache::OpenItem`
- `0x180020fca`: `Windows::Compat::Inventory::SqliteInvCache::OpenItem`
- `0x18002107a`: `Windows::Compat::Inventory::SqliteInvCache::OpenItem`

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
        std::wstring::_Construct<1,unsigned short const *>((char **)&v27, &dword_1800F6C3C, 0);
        Windows::Compat::Inventory::SqliteInvCacheItem::SqliteInvCacheItem(
          (__int64)v16,
          (__int64)&v27,
          (__int64)this + 136,
          v18,
          v17);
        std::wstring::~wstring((char **)&v27);
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
0x180020e10  mov     [rsp-38h+arg_18], rbx
0x180020e15  push    rbp
0x180020e16  push    rsi
0x180020e17  push    rdi
0x180020e18  push    r12
0x180020e1a  push    r13
0x180020e1c  push    r14
0x180020e1e  push    r15
0x180020e20  mov     rbp, rsp
0x180020e23  sub     rsp, 80h
0x180020e2a  mov     rax, cs:__security_cookie
0x180020e31  xor     rax, rsp
0x180020e34  mov     [rbp+var_8], rax
0x180020e38  mov     [rbp+var_30], r8
0x180020e3c  mov     rdi, rdx
0x180020e3f  mov     r13, rcx
0x180020e42  xor     r14d, r14d
0x180020e45  mov     r12d, r14d
0x180020e48  mov     [rbp+var_50], r14
0x180020e4c  mov     [rbp+var_38], r14
0x180020e50  lea     rdx, [rcx+0B0h]
0x180020e57  cmp     qword ptr [rdx+18h], 7
0x180020e5c  jbe     short loc_180020E61
0x180020e5e  mov     rdx, [rdx]
0x180020e61  mov     [rsp+80h+var_58], r14
0x180020e66  lea     rax, [rbp+var_38]
0x180020e6a  mov     [rsp+80h+var_60], rax
0x180020e6f  mov     r9d, 80h
0x180020e75  or      r8d, 0FFFFFFFFh
0x180020e79  mov     rcx, [rcx+8]
0x180020e7d  call    sqlite3Prepare16
0x180020e82  mov     ebx, eax
0x180020e84  mov     r15, [rbp+var_38]
0x180020e88  test    eax, eax
0x180020e8a  jz      short loc_180020EB7
0x180020e8c  jg      short loc_180020E93
0x180020e8e  mov     r14d, eax
0x180020e91  jmp     short loc_180020E9E
0x180020e93  movzx   r14d, ax
0x180020e97  or      r14d, 80070000h
0x180020e9e  mov     edi, 1
0x180020ea3  mov     [rbp+var_48], 275h
0x180020eab  lea     rax, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x180020eb2  jmp     loc_180020F69
0x180020eb7  test    r15, r15
0x180020eba  jz      loc_180021062
0x180020ec0  mov     byte ptr [rsp+80h+var_58], 2
0x180020ec5  mov     [rsp+80h+var_60], r14
0x180020eca  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180020ed1  mov     r8, rdi
0x180020ed4  lea     edi, [r9+3]
0x180020ed8  mov     edx, edi
0x180020eda  mov     rcx, r15
0x180020edd  call    bindText
0x180020ee2  mov     ebx, eax
0x180020ee4  test    eax, eax
0x180020ee6  jz      short loc_180020F0B
0x180020ee8  jg      short loc_180020EEF
0x180020eea  mov     r14d, eax
0x180020eed  jmp     short loc_180020EFA
0x180020eef  movzx   r14d, ax
0x180020ef3  or      r14d, 80070000h
0x180020efa  mov     [rbp+var_48], 284h
0x180020f02  lea     rax, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180020f09  jmp     short loc_180020F69
0x180020f0b  mov     esi, r14d
0x180020f0e  mov     rcx, r15
0x180020f11  call    sqlite3_step
0x180020f16  mov     ebx, eax
0x180020f18  add     eax, 0FFFFFFFBh
0x180020f1b  cmp     eax, edi
0x180020f1d  ja      short loc_180020F31
0x180020f1f  mov     ecx, 5; dwMilliseconds
0x180020f24  call    cs:__imp_Sleep
0x180020f2a  add     esi, edi
0x180020f2c  cmp     esi, 64h ; 'd'
0x180020f2f  jl      short loc_180020F0E
0x180020f31  cmp     ebx, 65h ; 'e'
0x180020f34  jnz     short loc_180020F41
0x180020f36  mov     r14d, 80070002h
0x180020f3c  jmp     loc_18002108B
0x180020f41  cmp     ebx, 64h ; 'd'
0x180020f44  jz      short loc_180020FA6
0x180020f46  test    ebx, ebx
0x180020f48  jg      short loc_180020F4F
0x180020f4a  mov     r14d, ebx
0x180020f4d  jmp     short loc_180020F5A
0x180020f4f  movzx   r14d, bx
0x180020f53  or      r14d, 80070000h
0x180020f5a  mov     [rbp+var_48], 292h
0x180020f62  lea     rax, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180020f69  lea     rsi, aWindowsCompatI_17; "Windows::Compat::Inventory::SqliteInvCa"...
0x180020f70  mov     [rbp+var_40], rax
0x180020f74  mov     rcx, [r13+8]
0x180020f78  call    sqlite3_errmsg
0x180020f7d  mov     [rsp+80h+var_58], rax
0x180020f82  mov     dword ptr [rsp+80h+var_60], ebx
0x180020f86  mov     r9, [rbp+var_40]
0x180020f8a  mov     r8, [rbp+var_48]
0x180020f8e  mov     rdx, rsi
0x180020f91  mov     ecx, edi
0x180020f93  call    AslLogCallPrintf
0x180020f98  test    r14d, r14d
0x180020f9b  jns     loc_180021096
0x180020fa1  jmp     loc_18002108B
0x180020fa6  lea     rdx, [rbp+var_50]
0x180020faa  mov     rcx, r13
0x180020fad  call    ?CreateWriteStatement@SqliteInvCache@Inventory@Compat@Windows@@AEBAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@P6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Compat::Inventory::SqliteInvCache::CreateWriteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (*)(sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>> &)
0x180020fb2  mov     r14d, eax
0x180020fb5  test    eax, eax
0x180020fb7  jns     short loc_180020FE1
0x180020fb9  mov     dword ptr [rsp+80h+var_60], eax
0x180020fbd  lea     r9, aCreatewritesta; "CreateWriteStatement failed [%#x]"
0x180020fc4  mov     r8d, 299h
0x180020fca  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::SqliteInvCa"...
0x180020fd1  mov     ecx, edi
0x180020fd3  call    AslLogCallPrintf
0x180020fd8  mov     r12, [rbp+var_50]
0x180020fdc  jmp     loc_18002108B
0x180020fe1  mov     ecx, 58h ; 'X'; Size
0x180020fe6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020feb  mov     rsi, rax
0x180020fee  mov     [rbp+var_48], rax
0x180020ff2  mov     rdi, r15
0x180020ff5  xor     r15d, r15d
0x180020ff8  mov     [rbp+var_38], r15
0x180020ffc  mov     rbx, [rbp+var_50]
0x180021000  xor     r12d, r12d
0x180021003  mov     [rbp+var_50], r12
0x180021007  xorps   xmm0, xmm0
0x18002100a  movups  [rbp+var_28], xmm0
0x18002100e  mov     [rbp+var_18], r12
0x180021012  mov     [rbp+var_10], r12
0x180021016  xor     r8d, r8d
0x180021019  lea     rdx, dword_1800F6C3C
0x180021020  lea     rcx, [rbp+var_28]
0x180021024  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021029  nop
0x18002102a  lea     r8, [r13+88h]
0x180021031  mov     [rsp+80h+var_60], rdi
0x180021036  mov     r9, rbx
0x180021039  lea     rdx, [rbp+var_28]
0x18002103d  mov     rcx, rsi
0x180021040  call    ??0SqliteInvCacheItem@Inventory@Compat@Windows@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@5@PEAUsqlite3_stmt@@2@Z; Windows::Compat::Inventory::SqliteInvCacheItem::SqliteInvCacheItem(std::wstring const &,std::vector<IAmiInventoryItem::_CacheItemProperty> const &,sqlite3_stmt *,sqlite3_stmt *)
0x180021045  nop
0x180021046  lea     rcx, [rbp+var_28]
0x18002104a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002104f  lea     rax, ??_7SqliteInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::SqliteInvCacheItem::`vftable'
0x180021056  mov     [rsi], rax
0x180021059  mov     rax, [rbp+var_30]
0x18002105d  mov     [rax], rsi
0x180021060  jmp     short loc_180021096
0x180021062  mov     r14d, 80004005h
0x180021068  mov     dword ptr [rsp+80h+var_60], r14d
0x18002106d  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x180021074  mov     r8d, 27Bh
0x18002107a  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::SqliteInvCa"...
0x180021081  mov     ecx, 1
0x180021086  call    AslLogCallPrintf
0x18002108b  mov     rax, [rbp+var_30]
0x18002108f  mov     qword ptr [rax], 0
0x180021096  test    r12, r12
0x180021099  jz      short loc_1800210A4
0x18002109b  mov     rcx, r12
0x18002109e  call    sqlite3_finalize
0x1800210a3  nop
0x1800210a4  test    r15, r15
0x1800210a7  jz      short loc_1800210B2
0x1800210a9  mov     rcx, r15
0x1800210ac  call    sqlite3_finalize
0x1800210b1  nop
0x1800210b2  mov     eax, r14d
0x1800210b5  mov     rcx, [rbp+var_8]
0x1800210b9  xor     rcx, rsp; StackCookie
0x1800210bc  call    __security_check_cookie
0x1800210c1  mov     rbx, [rsp+80h+arg_18]
0x1800210c9  add     rsp, 80h
0x1800210d0  pop     r15
0x1800210d2  pop     r14
0x1800210d4  pop     r13
0x1800210d6  pop     r12
0x1800210d8  pop     rdi
0x1800210d9  pop     rsi
0x1800210da  pop     rbp
0x1800210db  retn
```
