# Windows::Compat::Inventory::SqliteInvCache::RemoveItem(ushort const *)

- ea: `0x1800297b0`
- end: `0x180029a3d`
- name: `?RemoveItem@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEBG@Z`
- size: `653`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002bf0`
- `0x1800074f0`
- `0x1800109dc`
- `0x1800152d0`
- `0x18001f4a4`
- `0x18001fd88`
- `0x1800297b0`
- `0x180036be4`
- `0x1800817cc`
- `0x1800a1980`
- `0x1800a22c0`
- `0x1800a4690`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029993`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029993`

## string_xrefs

- `0x1800298fa`: `Windows::Compat::Inventory::SqliteInvCache::RemoveItem`
- `0x1800299e6`: `Windows::Compat::Inventory::SqliteInvCache::RemoveItem`
- `0x180029818`: `DELETE FROM `

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::RemoveItem(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  int v3; // ebx
  _QWORD *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  _QWORD *v9; // rdx
  int v10; // eax
  int v11; // edi
  unsigned int v12; // ebx
  int v13; // eax
  int v14; // esi
  __int64 v15; // rax
  const char *v16; // r9
  __int64 v17; // r8
  int i; // r15d
  __int64 v20; // [rsp+20h] [rbp-79h]
  __int64 v21; // [rsp+20h] [rbp-79h]
  __int64 v22; // [rsp+28h] [rbp-71h]
  __int64 v23; // [rsp+28h] [rbp-71h]
  __int64 v24; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v25[4]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v26[32]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v27[32]; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v28[32]; // [rsp+A8h] [rbp+Fh] BYREF

  v3 = (int)a2;
  v5 = (_QWORD *)((char *)this + 72);
  v6 = *((_QWORD *)this + 11);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v6) < 0xC )
    std::_Xlen_string();
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::wstring(v26, v5, a3, L"DELETE FROM ", 12, v5, v6);
  v7 = std::operator+<unsigned short>(v28, v26, L" WHERE ");
  v8 = std::operator+<unsigned short>(v27, v7, L"ItemKey");
  std::operator+<unsigned short>(v25, v8, L" = ?;");
  std::wstring::~wstring(v27);
  std::wstring::~wstring(v28);
  std::wstring::~wstring(v26);
  v24 = 0;
  v9 = v25;
  if ( v25[3] > 7u )
    LODWORD(v9) = v25[0];
  v10 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v9, -1, 128, (__int64)&v24, 0);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v12 = (unsigned __int16)v10 | 0x80070000;
    else
      v12 = v10;
    v23 = sqlite3_errmsg(*((_QWORD *)this + 1));
    LODWORD(v20) = v11;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::RemoveItem",
      719,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v20,
      v23);
  }
  else if ( v24 )
  {
    LOBYTE(v22) = 2;
    v13 = bindText(v24, 1, v3, -2, 0, v22);
    v14 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v12 = (unsigned __int16)v13 | 0x80070000;
      else
        v12 = v13;
      v15 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v16 = "sqlite3_bind_text16 failed: [%d] %hs";
      v17 = 733;
    }
    else
    {
      v12 = 0;
      for ( i = 0; i < 100; ++i )
      {
        v14 = sqlite3_step(v24);
        if ( (unsigned int)(v14 - 5) > 1 )
          break;
        Sleep(5u);
      }
      if ( v14 == 101 )
        goto LABEL_28;
      if ( v14 > 0 )
        v12 = (unsigned __int16)v14 | 0x80070000;
      else
        v12 = v14;
      v15 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v16 = "sqlite3_step failed: [%d] %hs";
      v17 = 740;
    }
    LODWORD(v21) = v14;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::RemoveItem", v17, v16, v21, v15);
  }
  else
  {
    v12 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::RemoveItem",
      725,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
  }
LABEL_28:
  if ( v24 )
    sqlite3_finalize(v24);
  std::wstring::~wstring(v25);
  return v12;
}

```

## disassembly

```asm
0x1800297b0  mov     [rsp-8+arg_10], rbx
0x1800297b5  push    rbp
0x1800297b6  push    rsi
0x1800297b7  push    rdi
0x1800297b8  push    r13
0x1800297ba  push    r15
0x1800297bc  lea     rbp, [rsp-37h]
0x1800297c1  sub     rsp, 0D0h
0x1800297c8  mov     rax, cs:__security_cookie
0x1800297cf  xor     rax, rsp
0x1800297d2  mov     [rbp+57h+var_28], rax
0x1800297d6  mov     rbx, rdx
0x1800297d9  mov     r13, rcx
0x1800297dc  lea     rdx, [rcx+48h]
0x1800297e0  mov     rcx, [rdx+10h]
0x1800297e4  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800297ee  sub     rax, rcx
0x1800297f1  cmp     rax, 0Ch
0x1800297f5  jb      loc_180029A37
0x1800297fb  cmp     qword ptr [rdx+18h], 7
0x180029800  jbe     short loc_180029805
0x180029802  mov     rdx, [rdx]
0x180029805  mov     [rsp+0F0h+var_C0], rcx
0x18002980a  mov     [rsp+0F0h+var_C8], rdx
0x18002980f  mov     [rsp+0F0h+var_D0], 0Ch
0x180029818  lea     r9, aDeleteFrom; "DELETE FROM "
0x18002981f  lea     rcx, [rbp+57h+var_88]
0x180029823  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180029828  nop
0x180029829  lea     r8, aWhere; " WHERE "
0x180029830  lea     rdx, [rbp+57h+var_88]
0x180029834  lea     rcx, [rbp+57h+var_48]
0x180029838  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002983d  nop
0x18002983e  lea     r8, aItemkey; "ItemKey"
0x180029845  mov     rdx, rax
0x180029848  lea     rcx, [rbp+57h+var_68]
0x18002984c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180029851  nop
0x180029852  lea     r8, asc_1800DC410; " = ?;"
0x180029859  mov     rdx, rax
0x18002985c  lea     rcx, [rbp+57h+var_A8]
0x180029860  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180029865  nop
0x180029866  lea     rcx, [rbp+57h+var_68]; void *
0x18002986a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002986f  nop
0x180029870  lea     rcx, [rbp+57h+var_48]; void *
0x180029874  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029879  nop
0x18002987a  lea     rcx, [rbp+57h+var_88]; void *
0x18002987e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029883  nop
0x180029884  mov     [rbp+57h+var_B0], 0
0x18002988c  lea     rdx, [rbp+57h+var_A8]
0x180029890  cmp     [rbp+57h+var_90], 7
0x180029895  cmova   rdx, [rbp+57h+var_A8]
0x18002989a  mov     [rsp+0F0h+var_C8], 0
0x1800298a3  lea     rax, [rbp+57h+var_B0]
0x1800298a7  mov     [rsp+0F0h+var_D0], rax
0x1800298ac  mov     r9d, 80h
0x1800298b2  or      r8d, 0FFFFFFFFh
0x1800298b6  mov     rcx, [r13+8]
0x1800298ba  call    sqlite3Prepare16
0x1800298bf  mov     edi, eax
0x1800298c1  test    eax, eax
0x1800298c3  jz      short loc_18002990B
0x1800298c5  test    eax, eax
0x1800298c7  jg      short loc_1800298CD
0x1800298c9  mov     ebx, eax
0x1800298cb  jmp     short loc_1800298D6
0x1800298cd  movzx   ebx, di
0x1800298d0  or      ebx, 80070000h
0x1800298d6  mov     rcx, [r13+8]
0x1800298da  call    sqlite3_errmsg
0x1800298df  mov     [rsp+0F0h+var_C8], rax
0x1800298e4  mov     dword ptr [rsp+0F0h+var_D0], edi
0x1800298e8  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x1800298ef  mov     r8d, 2CFh
0x1800298f5  mov     ecx, 1
0x1800298fa  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Inventory::SqliteInvCa"...
0x180029901  call    AslLogCallPrintf
0x180029906  jmp     loc_1800299F8
0x18002990b  cmp     [rbp+57h+var_B0], 0
0x180029910  jz      loc_1800299D0
0x180029916  mov     byte ptr [rsp+0F0h+var_C8], 2
0x18002991b  mov     [rsp+0F0h+var_D0], 0
0x180029924  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18002992b  mov     r8, rbx
0x18002992e  lea     edi, [r9+3]
0x180029932  mov     edx, edi
0x180029934  mov     rcx, [rbp+57h+var_B0]
0x180029938  call    bindText
0x18002993d  mov     esi, eax
0x18002993f  test    eax, eax
0x180029941  jz      short loc_180029977
0x180029943  test    eax, eax
0x180029945  jg      short loc_18002994B
0x180029947  mov     ebx, eax
0x180029949  jmp     short loc_180029954
0x18002994b  movzx   ebx, si
0x18002994e  or      ebx, 80070000h
0x180029954  mov     rcx, [r13+8]
0x180029958  call    sqlite3_errmsg
0x18002995d  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180029964  mov     r8d, 2DDh
0x18002996a  mov     [rsp+0F0h+var_C8], rax
0x18002996f  mov     dword ptr [rsp+0F0h+var_D0], esi
0x180029973  mov     ecx, edi
0x180029975  jmp     short loc_1800298FA
0x180029977  xor     ebx, ebx
0x180029979  xor     r15d, r15d
0x18002997c  mov     rcx, [rbp+57h+var_B0]
0x180029980  call    sqlite3_step
0x180029985  mov     esi, eax
0x180029987  lea     ecx, [rax-5]
0x18002998a  cmp     ecx, edi
0x18002998c  ja      short loc_1800299A2
0x18002998e  mov     ecx, 5; dwMilliseconds
0x180029993  call    cs:__imp_Sleep
0x180029999  add     r15d, edi
0x18002999c  cmp     r15d, 64h ; 'd'
0x1800299a0  jl      short loc_18002997C
0x1800299a2  cmp     esi, 65h ; 'e'
0x1800299a5  jz      short loc_1800299F8
0x1800299a7  test    esi, esi
0x1800299a9  jg      short loc_1800299AF
0x1800299ab  mov     ebx, esi
0x1800299ad  jmp     short loc_1800299B8
0x1800299af  movzx   ebx, si
0x1800299b2  or      ebx, 80070000h
0x1800299b8  mov     rcx, [r13+8]
0x1800299bc  call    sqlite3_errmsg
0x1800299c1  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x1800299c8  mov     r8d, 2E4h
0x1800299ce  jmp     short loc_18002996A
0x1800299d0  mov     ebx, 80004005h
0x1800299d5  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x1800299d9  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x1800299e0  mov     r8d, 2D5h
0x1800299e6  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800299ed  mov     ecx, 1
0x1800299f2  call    AslLogCallPrintf
0x1800299f7  nop
0x1800299f8  cmp     [rbp+57h+var_B0], 0
0x1800299fd  jz      short loc_180029A09
0x1800299ff  mov     rcx, [rbp+57h+var_B0]
0x180029a03  call    sqlite3_finalize
0x180029a08  nop
0x180029a09  lea     rcx, [rbp+57h+var_A8]; void *
0x180029a0d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029a12  mov     eax, ebx
0x180029a14  mov     rcx, [rbp+57h+var_28]
0x180029a18  xor     rcx, rsp; StackCookie
0x180029a1b  call    __security_check_cookie
0x180029a20  mov     rbx, [rsp+0F0h+arg_10]
0x180029a28  add     rsp, 0D0h
0x180029a2f  pop     r15
0x180029a31  pop     r13
0x180029a33  pop     rdi
0x180029a34  pop     rsi
0x180029a35  pop     rbp
0x180029a36  retn
0x180029a37  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
