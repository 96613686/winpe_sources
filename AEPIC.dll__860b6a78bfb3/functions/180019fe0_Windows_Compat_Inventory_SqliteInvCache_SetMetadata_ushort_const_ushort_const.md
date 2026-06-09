# Windows::Compat::Inventory::SqliteInvCache::SetMetadata(ushort const *,ushort const *)

- ea: `0x180019fe0`
- end: `0x18001a39a`
- name: `?SetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEBG0@Z`
- size: `954`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180005890`
- `0x18000eb38`
- `0x18000ec14`
- `0x1800103b0`
- `0x180019fe0`
- `0x18001c5f0`
- `0x18001c73c`
- `0x1800295dc`
- `0x18003fd34`
- `0x1800870b4`
- `0x1800a5e60`

## string_xrefs

- `0x18001a026`: `DELETE FROM `
- `0x18001a16f`: `REPLACE INTO `
- `0x18001a0b9`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18001a0fa`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18001a20a`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18001a242`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18001a35a`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::SetMetadata(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v4; // esi
  char *v6; // r8
  __int64 v7; // rax
  _QWORD *v8; // rdx
  int v9; // eax
  int v10; // ebx
  unsigned int v11; // edi
  Windows::Compat::Inventory *v12; // rbx
  int v13; // eax
  int v14; // esi
  __int64 v15; // rax
  _QWORD *v16; // rdx
  int v17; // eax
  int v18; // ebx
  int v19; // eax
  int v20; // esi
  int v21; // eax
  int v22; // esi
  struct sqlite3_stmt *v23; // rdx
  int v24; // r8d
  int v25; // eax
  int v26; // ebx
  const char *v27; // rax
  __int64 v29; // [rsp+20h] [rbp-60h]
  __int64 v30; // [rsp+20h] [rbp-60h]
  __int64 v31; // [rsp+20h] [rbp-60h]
  __int64 v32; // [rsp+20h] [rbp-60h]
  __int64 v33; // [rsp+20h] [rbp-60h]
  __int64 v34; // [rsp+28h] [rbp-58h]
  __int64 v35; // [rsp+28h] [rbp-58h]
  __int64 v36; // [rsp+28h] [rbp-58h]
  __int64 v37; // [rsp+28h] [rbp-58h]
  __int64 v38; // [rsp+28h] [rbp-58h]
  Windows::Compat::Inventory *v39; // [rsp+30h] [rbp-50h] BYREF
  _DWORD v40[6]; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int64 v41; // [rsp+50h] [rbp-30h]
  _BYTE v42[32]; // [rsp+58h] [rbp-28h] BYREF

  v4 = (int)a2;
  v39 = 0;
  v6 = (char *)this + 104;
  if ( a3 )
  {
    v15 = std::operator+<unsigned short>(v42, L"REPLACE INTO ", v6);
    std::operator+<unsigned short>(v40, v15, L" (Name, Value) VALUES (?, ?);");
    std::wstring::_Tidy_deallocate(v42);
    v39 = 0;
    v16 = v40;
    if ( v41 > 7 )
      LODWORD(v16) = v40[0];
    v17 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v16, -1, 128, (__int64)&v39, 0);
    v18 = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        v11 = (unsigned __int16)v17 | 0x80070000;
      else
        v11 = v17;
      v36 = sqlite3_errmsg(*((_QWORD *)this + 1));
      LODWORD(v31) = v18;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1270,
        "sqlite3_prepare_v2 failed: [%d] %hs",
        v31,
        v36);
      goto LABEL_9;
    }
    v12 = v39;
    if ( !v39 )
    {
      v11 = -2147467259;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1276,
        "sqlite3_prepare_v2 returned a null statement [%#x]",
        -2147467259);
      goto LABEL_9;
    }
    v19 = bindText((_DWORD)v39, 1, v4, -2, 0, 2);
    v20 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v11 = (unsigned __int16)v19 | 0x80070000;
      else
        v11 = v19;
      v37 = sqlite3_errmsg(*((_QWORD *)this + 1));
      LODWORD(v32) = v20;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1284,
        "sqlite3_bind_text16 failed: [%d] %hs",
        v32,
        v37);
      goto LABEL_9;
    }
    v21 = bindText((_DWORD)v12, 2, (_DWORD)a3, -2, 0, 2);
    v22 = v21;
    if ( v21 )
    {
      if ( v21 > 0 )
        v11 = (unsigned __int16)v21 | 0x80070000;
      else
        v11 = v21;
      v38 = sqlite3_errmsg(*((_QWORD *)this + 1));
      LODWORD(v33) = v22;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1292,
        "sqlite3_bind_text16 failed: [%d] %hs",
        v33,
        v38);
      goto LABEL_9;
    }
  }
  else
  {
    v7 = std::operator+<unsigned short>(v42, L"DELETE FROM ", v6);
    std::operator+<unsigned short>(v40, v7, L" WHERE Name = ?;");
    std::wstring::_Tidy_deallocate(v42);
    v39 = 0;
    v8 = v40;
    if ( v41 > 7 )
      LODWORD(v8) = v40[0];
    v9 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v8, -1, 128, (__int64)&v39, 0);
    v10 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v11 = (unsigned __int16)v9 | 0x80070000;
      else
        v11 = v9;
      v34 = sqlite3_errmsg(*((_QWORD *)this + 1));
      LODWORD(v29) = v10;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1245,
        "sqlite3_prepare_v2 failed: [%d] %hs",
        v29,
        v34);
      goto LABEL_9;
    }
    v12 = v39;
    if ( !v39 )
    {
      v11 = -2147467259;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1251,
        "sqlite3_prepare_v2 returned a null statement [%#x]",
        -2147467259);
LABEL_9:
      std::wstring::_Tidy_deallocate(v40);
      goto LABEL_42;
    }
    v13 = bindText((_DWORD)v39, 1, v4, -2, 0, 2);
    v14 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v11 = (unsigned __int16)v13 | 0x80070000;
      else
        v11 = v13;
      v35 = sqlite3_errmsg(*((_QWORD *)this + 1));
      LODWORD(v30) = v14;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1259,
        "sqlite3_bind_text16 failed: [%d] %hs",
        v30,
        v35);
      goto LABEL_9;
    }
  }
  std::wstring::_Tidy_deallocate(v40);
  v11 = 0;
  v25 = Windows::Compat::Inventory::sqlite3_step_with_retry(v12, v23, v24);
  v26 = v25;
  if ( v25 != 101 )
  {
    if ( v25 > 0 )
      v11 = (unsigned __int16)v25 | 0x80070000;
    else
      v11 = v25;
    v27 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1301,
      "sqlite3_step failed: [%d] %hs",
      v26,
      v27);
  }
LABEL_42:
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (*)(sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (*)(sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(&v39);
  return v11;
}

```

## disassembly

```asm
0x180019fe0  mov     [rsp-28h+arg_18], rbx
0x180019fe5  push    rbp
0x180019fe6  push    rsi
0x180019fe7  push    rdi
0x180019fe8  push    r14
0x180019fea  push    r15
0x180019fec  mov     rbp, rsp
0x180019fef  sub     rsp, 80h
0x180019ff6  mov     rax, cs:__security_cookie
0x180019ffd  xor     rax, rsp
0x18001a000  mov     [rbp+var_8], rax
0x18001a004  mov     r15, r8
0x18001a007  mov     rsi, rdx
0x18001a00a  mov     r14, rcx
0x18001a00d  mov     [rbp+var_50], 0
0x18001a015  lea     r8, [rcx+68h]
0x18001a019  lea     rcx, [rbp+var_28]
0x18001a01d  test    r15, r15
0x18001a020  jnz     loc_18001A16F
0x18001a026  lea     rdx, aDeleteFrom; "DELETE FROM "
0x18001a02d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18001a032  nop
0x18001a033  lea     r8, aWhereName; " WHERE Name = ?;"
0x18001a03a  mov     rdx, rax
0x18001a03d  lea     rcx, [rbp+var_48]
0x18001a041  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18001a046  nop
0x18001a047  lea     rcx, [rbp+var_28]
0x18001a04b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a050  mov     [rbp+var_50], r15
0x18001a054  lea     rdx, [rbp+var_48]
0x18001a058  cmp     [rbp+var_30], 7
0x18001a05d  cmova   rdx, qword ptr [rbp+var_48]
0x18001a062  mov     [rsp+80h+var_58], r15
0x18001a067  lea     rax, [rbp+var_50]
0x18001a06b  mov     [rsp+80h+var_60], rax
0x18001a070  mov     r9d, 80h
0x18001a076  or      r8d, 0FFFFFFFFh
0x18001a07a  mov     rcx, [r14+8]
0x18001a07e  call    sqlite3Prepare16
0x18001a083  mov     ebx, eax
0x18001a085  test    eax, eax
0x18001a087  jz      short loc_18001A0D9
0x18001a089  test    eax, eax
0x18001a08b  jg      short loc_18001A091
0x18001a08d  mov     edi, eax
0x18001a08f  jmp     short loc_18001A09A
0x18001a091  movzx   edi, bx
0x18001a094  or      edi, 80070000h
0x18001a09a  mov     rcx, [r14+8]
0x18001a09e  call    sqlite3_errmsg
0x18001a0a3  mov     [rsp+80h+var_58], rax
0x18001a0a8  mov     dword ptr [rsp+80h+var_60], ebx
0x18001a0ac  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18001a0b3  mov     r8d, 4DDh
0x18001a0b9  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001a0c0  mov     ecx, 1
0x18001a0c5  call    AslLogCallPrintf
0x18001a0ca  nop
0x18001a0cb  lea     rcx, [rbp+var_48]
0x18001a0cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a0d4  jmp     loc_18001A36C
0x18001a0d9  mov     rbx, [rbp+var_50]
0x18001a0dd  test    rbx, rbx
0x18001a0e0  jnz     short loc_18001A10B
0x18001a0e2  mov     eax, 80004005h
0x18001a0e7  mov     edi, eax
0x18001a0e9  mov     dword ptr [rsp+80h+var_60], eax
0x18001a0ed  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18001a0f4  mov     r8d, 4E3h
0x18001a0fa  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001a101  lea     ecx, [rbx+1]
0x18001a104  call    AslLogCallPrintf
0x18001a109  jmp     short loc_18001A0CB
0x18001a10b  mov     byte ptr [rsp+80h+var_58], 2
0x18001a110  mov     [rsp+80h+var_60], 0
0x18001a119  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18001a120  mov     r8, rsi
0x18001a123  lea     edx, [r9+3]
0x18001a127  mov     rcx, rbx
0x18001a12a  call    bindText
0x18001a12f  mov     esi, eax
0x18001a131  test    eax, eax
0x18001a133  jz      short loc_18001A16A
0x18001a135  test    eax, eax
0x18001a137  jg      short loc_18001A13D
0x18001a139  mov     edi, eax
0x18001a13b  jmp     short loc_18001A146
0x18001a13d  movzx   edi, si
0x18001a140  or      edi, 80070000h
0x18001a146  mov     rcx, [r14+8]
0x18001a14a  call    sqlite3_errmsg
0x18001a14f  mov     [rsp+80h+var_58], rax
0x18001a154  mov     dword ptr [rsp+80h+var_60], esi
0x18001a158  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18001a15f  mov     r8d, 4EBh
0x18001a165  jmp     loc_18001A0B9
0x18001a16a  jmp     loc_18001A310
0x18001a16f  lea     rdx, aReplaceInto; "REPLACE INTO "
0x18001a176  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18001a17b  nop
0x18001a17c  lea     r8, aNameValueValue; " (Name, Value) VALUES (?, ?);"
0x18001a183  mov     rdx, rax
0x18001a186  lea     rcx, [rbp+var_48]
0x18001a18a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18001a18f  nop
0x18001a190  lea     rcx, [rbp+var_28]
0x18001a194  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a199  mov     [rbp+var_50], 0
0x18001a1a1  lea     rdx, [rbp+var_48]
0x18001a1a5  cmp     [rbp+var_30], 7
0x18001a1aa  cmova   rdx, qword ptr [rbp+var_48]
0x18001a1af  mov     [rsp+80h+var_58], 0
0x18001a1b8  lea     rax, [rbp+var_50]
0x18001a1bc  mov     [rsp+80h+var_60], rax
0x18001a1c1  mov     r9d, 80h
0x18001a1c7  or      r8d, 0FFFFFFFFh
0x18001a1cb  mov     rcx, [r14+8]
0x18001a1cf  call    sqlite3Prepare16
0x18001a1d4  mov     ebx, eax
0x18001a1d6  test    eax, eax
0x18001a1d8  jz      short loc_18001A221
0x18001a1da  test    eax, eax
0x18001a1dc  jg      short loc_18001A1E2
0x18001a1de  mov     edi, eax
0x18001a1e0  jmp     short loc_18001A1EB
0x18001a1e2  movzx   edi, bx
0x18001a1e5  or      edi, 80070000h
0x18001a1eb  mov     rcx, [r14+8]
0x18001a1ef  call    sqlite3_errmsg
0x18001a1f4  mov     [rsp+80h+var_58], rax
0x18001a1f9  mov     dword ptr [rsp+80h+var_60], ebx
0x18001a1fd  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18001a204  mov     r8d, 4F6h
0x18001a20a  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001a211  mov     ecx, 1
0x18001a216  call    AslLogCallPrintf
0x18001a21b  nop
0x18001a21c  jmp     loc_18001A0CB
0x18001a221  mov     rbx, [rbp+var_50]
0x18001a225  test    rbx, rbx
0x18001a228  jnz     short loc_18001A253
0x18001a22a  mov     eax, 80004005h
0x18001a22f  mov     edi, eax
0x18001a231  mov     dword ptr [rsp+80h+var_60], eax
0x18001a235  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18001a23c  mov     r8d, 4FCh
0x18001a242  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001a249  lea     ecx, [rbx+1]
0x18001a24c  call    AslLogCallPrintf
0x18001a251  jmp     short loc_18001A21C
0x18001a253  mov     byte ptr [rsp+80h+var_58], 2
0x18001a258  mov     [rsp+80h+var_60], 0
0x18001a261  mov     rdi, 0FFFFFFFFFFFFFFFEh
0x18001a268  mov     r9, rdi
0x18001a26b  mov     r8, rsi
0x18001a26e  lea     edx, [rdi+3]
0x18001a271  mov     rcx, rbx
0x18001a274  call    bindText
0x18001a279  mov     esi, eax
0x18001a27b  test    eax, eax
0x18001a27d  jz      short loc_18001A2B4
0x18001a27f  test    eax, eax
0x18001a281  jg      short loc_18001A287
0x18001a283  mov     edi, eax
0x18001a285  jmp     short loc_18001A290
0x18001a287  movzx   edi, si
0x18001a28a  or      edi, 80070000h
0x18001a290  mov     rcx, [r14+8]
0x18001a294  call    sqlite3_errmsg
0x18001a299  mov     [rsp+80h+var_58], rax
0x18001a29e  mov     dword ptr [rsp+80h+var_60], esi
0x18001a2a2  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18001a2a9  mov     r8d, 504h
0x18001a2af  jmp     loc_18001A20A
0x18001a2b4  mov     byte ptr [rsp+80h+var_58], 2
0x18001a2b9  mov     [rsp+80h+var_60], 0
0x18001a2c2  mov     r9, rdi
0x18001a2c5  mov     r8, r15
0x18001a2c8  mov     edx, 2
0x18001a2cd  mov     rcx, rbx
0x18001a2d0  call    bindText
0x18001a2d5  mov     esi, eax
0x18001a2d7  test    eax, eax
0x18001a2d9  jz      short loc_18001A310
0x18001a2db  test    eax, eax
0x18001a2dd  jg      short loc_18001A2E3
0x18001a2df  mov     edi, eax
0x18001a2e1  jmp     short loc_18001A2EC
0x18001a2e3  movzx   edi, si
0x18001a2e6  or      edi, 80070000h
0x18001a2ec  mov     rcx, [r14+8]
0x18001a2f0  call    sqlite3_errmsg
0x18001a2f5  mov     [rsp+80h+var_58], rax
0x18001a2fa  mov     dword ptr [rsp+80h+var_60], esi
0x18001a2fe  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18001a305  mov     r8d, 50Ch
0x18001a30b  jmp     loc_18001A20A
0x18001a310  lea     rcx, [rbp+var_48]
0x18001a314  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a319  xor     edi, edi
0x18001a31b  mov     rcx, rbx; this
0x18001a31e  call    ?sqlite3_step_with_retry@Inventory@Compat@Windows@@YAHPEAUsqlite3_stmt@@H@Z; Windows::Compat::Inventory::sqlite3_step_with_retry(sqlite3_stmt *,int)
0x18001a323  mov     ebx, eax
0x18001a325  cmp     eax, 65h ; 'e'
0x18001a328  jz      short loc_18001A36C
0x18001a32a  test    eax, eax
0x18001a32c  jg      short loc_18001A332
0x18001a32e  mov     edi, eax
0x18001a330  jmp     short loc_18001A33B
0x18001a332  movzx   edi, bx
0x18001a335  or      edi, 80070000h
0x18001a33b  mov     rcx, [r14+8]
0x18001a33f  call    sqlite3_errmsg
0x18001a344  mov     [rsp+80h+var_58], rax
0x18001a349  mov     dword ptr [rsp+80h+var_60], ebx
0x18001a34d  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18001a354  mov     r8d, 515h
0x18001a35a  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001a361  mov     ecx, 1
0x18001a366  call    AslLogCallPrintf
0x18001a36b  nop
0x18001a36c  lea     rcx, [rbp+var_50]
0x18001a370  call    ??1?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@P6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (*)(sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (*)(sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(void)
0x18001a375  mov     eax, edi
0x18001a377  mov     rcx, [rbp+var_8]
0x18001a37b  xor     rcx, rsp; StackCookie
0x18001a37e  call    __security_check_cookie
0x18001a383  mov     rbx, [rsp+80h+arg_18]
0x18001a38b  add     rsp, 80h
0x18001a392  pop     r15
0x18001a394  pop     r14
0x18001a396  pop     rdi
0x18001a397  pop     rsi
0x18001a398  pop     rbp
0x18001a399  retn
```
