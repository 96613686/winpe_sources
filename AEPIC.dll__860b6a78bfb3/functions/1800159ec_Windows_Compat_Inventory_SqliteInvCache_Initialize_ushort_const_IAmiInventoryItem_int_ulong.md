# Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)

- ea: `0x1800159ec`
- end: `0x180015ce9`
- name: `?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z`
- size: `765`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, struct IAmiInventoryItem *, int, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180015cf0`

## callees

- `0x180005890`
- `0x18000ed74`
- `0x18000edf0`
- `0x18000ee58`
- `0x18000f228`
- `0x180011c64`
- `0x180011d38`
- `0x1800124d0`
- `0x1800159ec`
- `0x180016ff8`
- `0x18001c5ac`
- `0x18001c5f0`
- `0x18001c78c`
- `0x1800295dc`
- `0x18006e9a4`
- `0x1800a5e60`
- `0x1800eb010`

## string_xrefs

- `0x180015a34`: `TemplateItem cannot be null [%#x]`
- `0x180015a75`: `TemplateItem must have a property schema defined [%#x]`
- `0x180015a9c`: `OpenDb failed [%#x]`
- `0x180015c21`: `CreateReadItemQuery failed [%#x]`
- `0x180015c42`: `CreateWriteItemQuery failed [%#x]`
- `0x180015b1e`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x180015c4d`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x180015c71`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x180015cb2`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x180015c04`: `CreateTable failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::Initialize(
        struct sqlite3 **this,
        const unsigned __int16 *a2,
        struct IAmiInventoryItem *a3,
        int a4)
{
  int Table; // eax
  unsigned int v9; // ebx
  __int64 v10; // r8
  const char *v11; // r9
  __int64 *v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rbx
  Windows::Compat::Inventory::SqliteInvCache *v15; // rax
  __int64 v16; // r8
  void *v17; // rax
  __int64 v18; // rax
  int v19; // edi
  const char *v20; // rax
  _OWORD v22[2]; // [rsp+38h] [rbp-39h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-19h] BYREF

  if ( a3 )
  {
    v12 = (__int64 *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _OWORD *))(*(_QWORD *)a3 + 64LL))(a3, v22);
    v13 = *v12;
    v14 = v12[1];
    std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(v22);
    if ( v13 == v14 )
    {
      Table = -2147024809;
      v9 = -2147024809;
      v10 = 558;
      v11 = "TemplateItem must have a property schema defined [%#x]";
    }
    else
    {
      Table = Windows::Compat::Inventory::SqliteInvCache::OpenDb(a2, this + 1, a4);
      v9 = Table;
      if ( Table >= 0 )
      {
        *((_BYTE *)this + 168) = a4 != 0;
        v15 = (Windows::Compat::Inventory::SqliteInvCache *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _OWORD *))(*(_QWORD *)a3 + 64LL))(
                                                              a3,
                                                              v22);
        if ( this + 17 != (struct sqlite3 **)v15 )
          std::vector<IAmiInventoryItem::_CacheItemProperty>::_Assign_counted_range<IAmiInventoryItem::_CacheItemProperty *>(
            this + 17,
            *(_QWORD *)v15,
            (__int64)(*((_QWORD *)v15 + 1) - *(_QWORD *)v15) >> 4);
        std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(v22);
        v16 = -1;
        do
          ++v16;
        while ( a2[v16] );
        std::wstring::_Assign<unsigned short>(this + 9, a2);
        if ( !this[11] )
        {
          AslLogCallPrintf(
            1,
            "Windows::Compat::Inventory::SqliteInvCache::Initialize",
            575,
            "Table name conversion failed");
          return v9;
        }
        v17 = (void *)std::to_wstring(v23, 0);
        v18 = std::wstring::_Insert<unsigned short>(v17);
        v22[0] = *(_OWORD *)v18;
        v22[1] = *(_OWORD *)(v18 + 16);
        *(_QWORD *)(v18 + 16) = 0;
        *(_QWORD *)(v18 + 24) = 7;
        *(_WORD *)v18 = 0;
        std::wstring::_Append<unsigned short>(this + 9);
        std::wstring::_Tidy_deallocate(v22);
        std::wstring::_Tidy_deallocate(v23);
        std::wstring::_Assign<unsigned short>(this + 13, L"Metadata_");
        std::to_wstring(v23, 0);
        std::wstring::_Append<unsigned short>(this + 13);
        std::wstring::_Tidy_deallocate(v23);
        Table = Windows::Compat::Inventory::SqliteInvCache::CreateTable((Windows::Compat::Inventory::SqliteInvCache *)this);
        v9 = Table;
        if ( Table >= 0 )
        {
          Table = Windows::Compat::Inventory::SqliteInvCache::CreateReadItemQuery((Windows::Compat::Inventory::SqliteInvCache *)this);
          v9 = Table;
          if ( Table >= 0 )
          {
            Table = Windows::Compat::Inventory::SqliteInvCache::CreateWriteItemQuery((Windows::Compat::Inventory::SqliteInvCache *)this);
            v9 = Table;
            if ( Table >= 0 )
              return v9;
            v10 = 600;
            v11 = "CreateWriteItemQuery failed [%#x]";
          }
          else
          {
            v10 = 593;
            v11 = "CreateReadItemQuery failed [%#x]";
          }
        }
        else
        {
          v10 = 586;
          v11 = "CreateTable failed [%#x]";
        }
      }
      else
      {
        v10 = 565;
        v11 = "OpenDb failed [%#x]";
      }
    }
  }
  else
  {
    Table = -2147024809;
    v9 = -2147024809;
    v10 = 551;
    v11 = "TemplateItem cannot be null [%#x]";
  }
  AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::Initialize", v10, v11, Table);
  if ( this[1] )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::SqliteInvCache::Initialize",
      607,
      "closing database due to failure");
    v19 = sqlite3Close(this[1], 0);
    if ( v19 )
    {
      v20 = (const char *)sqlite3_errmsg(this[1]);
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::Initialize",
        611,
        "sqlite3_close failed: [%d] %hs",
        v19,
        v20);
    }
    this[1] = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x1800159ec  push    rbp
0x1800159ee  push    rbx
0x1800159ef  push    rsi
0x1800159f0  push    rdi
0x1800159f1  push    r12
0x1800159f3  push    r13
0x1800159f5  push    r14
0x1800159f7  push    r15
0x1800159f9  lea     rbp, [rsp-17h]
0x1800159fe  sub     rsp, 88h
0x180015a05  mov     rax, cs:__security_cookie
0x180015a0c  xor     rax, rsp
0x180015a0f  mov     [rbp+4Fh+var_48], rax
0x180015a13  mov     r12d, r9d
0x180015a16  mov     r14, r8
0x180015a19  mov     r15, rdx
0x180015a1c  mov     rsi, rcx
0x180015a1f  xor     r13d, r13d
0x180015a22  test    r8, r8
0x180015a25  jnz     short loc_180015A40
0x180015a27  mov     eax, 80070057h
0x180015a2c  mov     ebx, eax
0x180015a2e  mov     r8d, 227h
0x180015a34  lea     r9, aTemplateitemCa; "TemplateItem cannot be null [%#x]"
0x180015a3b  jmp     loc_180015C49
0x180015a40  mov     rax, [r8]
0x180015a43  lea     rdx, [rbp+4Fh+var_88]
0x180015a47  mov     rcx, r14
0x180015a4a  mov     rax, [rax+40h]
0x180015a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a53  mov     rdi, [rax]
0x180015a56  mov     rbx, [rax+8]
0x180015a5a  lea     rcx, [rbp+4Fh+var_88]
0x180015a5e  call    ?_Tidy@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAXXZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(void)
0x180015a63  cmp     rdi, rbx
0x180015a66  jnz     short loc_180015A81
0x180015a68  mov     eax, 80070057h
0x180015a6d  mov     ebx, eax
0x180015a6f  mov     r8d, 22Eh
0x180015a75  lea     r9, aTemplateitemMu; "TemplateItem must have a property schem"...
0x180015a7c  jmp     loc_180015C49
0x180015a81  lea     rdx, [rsi+8]; struct sqlite3 **
0x180015a85  mov     r8d, r12d; int
0x180015a88  mov     rcx, r15; unsigned __int16 *
0x180015a8b  call    ?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z; Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)
0x180015a90  mov     ebx, eax
0x180015a92  test    eax, eax
0x180015a94  jns     short loc_180015AA8
0x180015a96  mov     r8d, 235h
0x180015a9c  lea     r9, aOpendbFailedX; "OpenDb failed [%#x]"
0x180015aa3  jmp     loc_180015C49
0x180015aa8  test    r12d, r12d
0x180015aab  setnz   al
0x180015aae  mov     [rsi+0A8h], al
0x180015ab4  mov     rax, [r14]
0x180015ab7  lea     rdx, [rbp+4Fh+var_88]
0x180015abb  mov     rcx, r14
0x180015abe  mov     rax, [rax+40h]
0x180015ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ac7  nop
0x180015ac8  lea     rcx, [rsi+88h]
0x180015acf  cmp     rcx, rax
0x180015ad2  jz      short loc_180015AE8
0x180015ad4  mov     r8, [rax+8]
0x180015ad8  sub     r8, [rax]
0x180015adb  sar     r8, 4
0x180015adf  mov     rdx, [rax]
0x180015ae2  call    ??$_Assign_counted_range@PEAU_CacheItemProperty@IAmiInventoryItem@@@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAXPEAU_CacheItemProperty@IAmiInventoryItem@@_K@Z; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Assign_counted_range<IAmiInventoryItem::_CacheItemProperty *>(IAmiInventoryItem::_CacheItemProperty *,unsigned __int64)
0x180015ae7  nop
0x180015ae8  lea     rcx, [rbp+4Fh+var_88]
0x180015aec  call    ?_Tidy@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAXXZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(void)
0x180015af1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015af5  inc     r8
0x180015af8  cmp     [r15+r8*2], r13w
0x180015afd  jnz     short loc_180015AF5
0x180015aff  mov     rdx, r15
0x180015b02  lea     rcx, [rsi+48h]
0x180015b06  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180015b0b  cmp     [rsi+58h], r13
0x180015b0f  jnz     short loc_180015B34
0x180015b11  lea     r9, aTableNameConve; "Table name conversion failed"
0x180015b18  mov     r8d, 23Fh
0x180015b1e  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::SqliteInvCa"...
0x180015b25  mov     ecx, 1
0x180015b2a  call    AslLogCallPrintf
0x180015b2f  jmp     loc_180015CC7
0x180015b34  xor     edx, edx
0x180015b36  lea     rcx, [rbp+4Fh+var_68]
0x180015b3a  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x180015b3f  nop
0x180015b40  mov     r9d, 1
0x180015b46  mov     rcx, rax; Src
0x180015b49  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x180015b4e  movups  xmm0, xmmword ptr [rax]
0x180015b51  movups  [rbp+4Fh+var_88], xmm0
0x180015b55  movups  xmm1, xmmword ptr [rax+10h]
0x180015b59  movups  [rbp+4Fh+var_78], xmm1
0x180015b5d  mov     [rax+10h], r13
0x180015b61  mov     qword ptr [rax+18h], 7
0x180015b69  mov     [rax], r13w
0x180015b6d  movq    r8, xmm1
0x180015b72  lea     rdx, [rbp+4Fh+var_88]
0x180015b76  movq    r9, xmm0
0x180015b7b  psrldq  xmm1, 8
0x180015b80  movq    rax, xmm1
0x180015b85  cmp     rax, 7
0x180015b89  cmova   rdx, r9
0x180015b8d  lea     rcx, [rsi+48h]; Src
0x180015b91  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180015b96  nop
0x180015b97  lea     rcx, [rbp+4Fh+var_88]
0x180015b9b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015ba0  nop
0x180015ba1  lea     rcx, [rbp+4Fh+var_68]
0x180015ba5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015baa  mov     r8d, 9
0x180015bb0  lea     rdx, aMetadata; "Metadata_"
0x180015bb7  lea     rcx, [rsi+68h]
0x180015bbb  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180015bc0  xor     edx, edx
0x180015bc2  lea     rcx, [rbp+4Fh+var_68]
0x180015bc6  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x180015bcb  nop
0x180015bcc  mov     r8, [rax+10h]
0x180015bd0  cmp     qword ptr [rax+18h], 7
0x180015bd5  jbe     short loc_180015BDA
0x180015bd7  mov     rax, [rax]
0x180015bda  mov     rdx, rax
0x180015bdd  lea     rcx, [rsi+68h]; Src
0x180015be1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180015be6  nop
0x180015be7  lea     rcx, [rbp+4Fh+var_68]
0x180015beb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015bf0  mov     rcx, rsi; this
0x180015bf3  call    ?CreateTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateTable(void)
0x180015bf8  mov     ebx, eax
0x180015bfa  test    eax, eax
0x180015bfc  jns     short loc_180015C0D
0x180015bfe  mov     r8d, 24Ah
0x180015c04  lea     r9, aCreatetableFai; "CreateTable failed [%#x]"
0x180015c0b  jmp     short loc_180015C49
0x180015c0d  mov     rcx, rsi; this
0x180015c10  call    ?CreateReadItemQuery@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateReadItemQuery(void)
0x180015c15  mov     ebx, eax
0x180015c17  test    eax, eax
0x180015c19  jns     short loc_180015C2A
0x180015c1b  mov     r8d, 251h
0x180015c21  lea     r9, aCreatereaditem; "CreateReadItemQuery failed [%#x]"
0x180015c28  jmp     short loc_180015C49
0x180015c2a  mov     rcx, rsi; this
0x180015c2d  call    ?CreateWriteItemQuery@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateWriteItemQuery(void)
0x180015c32  mov     ebx, eax
0x180015c34  test    eax, eax
0x180015c36  jns     loc_180015CC7
0x180015c3c  mov     r8d, 258h
0x180015c42  lea     r9, aCreatewriteite; "CreateWriteItemQuery failed [%#x]"
0x180015c49  mov     [rsp+0C0h+var_A0], eax
0x180015c4d  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::SqliteInvCa"...
0x180015c54  mov     ecx, 1
0x180015c59  call    AslLogCallPrintf
0x180015c5e  cmp     [rsi+8], r13
0x180015c62  jz      short loc_180015CC7
0x180015c64  lea     r9, aClosingDatabas; "closing database due to failure"
0x180015c6b  mov     r8d, 25Fh
0x180015c71  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::SqliteInvCa"...
0x180015c78  mov     ecx, 3
0x180015c7d  call    AslLogCallPrintf
0x180015c82  xor     edx, edx
0x180015c84  mov     rcx, [rsi+8]
0x180015c88  call    sqlite3Close
0x180015c8d  mov     edi, eax
0x180015c8f  test    eax, eax
0x180015c91  jz      short loc_180015CC3
0x180015c93  mov     rcx, [rsi+8]
0x180015c97  call    sqlite3_errmsg
0x180015c9c  mov     [rsp+0C0h+var_98], rax
0x180015ca1  mov     [rsp+0C0h+var_A0], edi
0x180015ca5  lea     r9, aSqlite3CloseFa; "sqlite3_close failed: [%d] %hs"
0x180015cac  mov     r8d, 263h
0x180015cb2  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::SqliteInvCa"...
0x180015cb9  mov     ecx, 1
0x180015cbe  call    AslLogCallPrintf
0x180015cc3  mov     [rsi+8], r13
0x180015cc7  mov     eax, ebx
0x180015cc9  mov     rcx, [rbp+4Fh+var_48]
0x180015ccd  xor     rcx, rsp; StackCookie
0x180015cd0  call    __security_check_cookie
0x180015cd5  add     rsp, 88h
0x180015cdc  pop     r15
0x180015cde  pop     r14
0x180015ce0  pop     r13
0x180015ce2  pop     r12
0x180015ce4  pop     rdi
0x180015ce5  pop     rsi
0x180015ce6  pop     rbx
0x180015ce7  pop     rbp
0x180015ce8  retn
```
