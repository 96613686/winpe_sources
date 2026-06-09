# Windows::Compat::Inventory::SqliteInvCache::SetMetadata(ushort const *,ushort const *)

- ea: `0x18002b590`
- end: `0x18002ba11`
- name: `?SetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEBG0@Z`
- size: `1153`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
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
- `0x18002b590`
- `0x180036be4`
- `0x1800817cc`
- `0x1800a1980`
- `0x1800a22c0`
- `0x1800a4690`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b94a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b94a`

## string_xrefs

- `0x18002b60b`: `DELETE FROM `
- `0x18002b7a2`: `REPLACE INTO `
- `0x18002b6ab`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18002b737`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18002b768`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18002b842`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18002b8c7`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18002b993`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18002b9bb`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::SetMetadata(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v3; // r12d
  int v4; // r14d
  _QWORD *v6; // rax
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  _QWORD *v9; // rdx
  int v10; // eax
  int v11; // edi
  unsigned int v12; // ebx
  const char *v13; // rax
  __int64 v14; // rsi
  int v15; // eax
  int v16; // r14d
  const char *v17; // rax
  _QWORD *v18; // rdx
  int v19; // eax
  int v20; // edi
  const char *v21; // rax
  int v22; // eax
  int v23; // r14d
  const char *v24; // rax
  __int64 v25; // r8
  int v26; // eax
  int i; // r12d
  int v28; // r14d
  const char *v29; // rax
  __int64 v31; // [rsp+40h] [rbp-29h] BYREF
  _DWORD v32[6]; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v33; // [rsp+60h] [rbp-9h]
  _BYTE v34[32]; // [rsp+68h] [rbp-1h] BYREF

  v3 = (int)a3;
  v4 = (int)a2;
  v31 = 0;
  v6 = (_QWORD *)((char *)this + 104);
  v7 = *((_QWORD *)this + 15);
  v8 = 0x7FFFFFFFFFFFFFFELL - v7;
  if ( a3 )
  {
    if ( v8 < 0xD )
      std::_Xlen_string();
    if ( v6[3] > 7u )
      v6 = (_QWORD *)*v6;
    std::wstring::wstring(v34, v7, a3, L"REPLACE INTO ", 13, v6, v7);
    std::operator+<unsigned short>(v32, v34, L" (Name, Value) VALUES (?, ?);");
    std::wstring::~wstring(v34);
    v31 = 0;
    v18 = v32;
    if ( v33 > 7 )
      LODWORD(v18) = v32[0];
    v19 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v18, -1, 128, (__int64)&v31, 0);
    v20 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v12 = (unsigned __int16)v19 | 0x80070000;
      else
        v12 = v19;
      v21 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1270,
        "sqlite3_prepare_v2 failed: [%d] %hs",
        v20,
        v21);
      goto LABEL_12;
    }
    v14 = v31;
    if ( v31 )
    {
      v22 = bindText(v31, 1, v4, -2, 0, 2);
      v23 = v22;
      if ( v22 )
      {
        if ( v22 > 0 )
          v12 = (unsigned __int16)v22 | 0x80070000;
        else
          v12 = v22;
        v24 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
        v25 = 1284;
      }
      else
      {
        v26 = bindText(v14, 2, v3, -2, 0, 2);
        v23 = v26;
        if ( !v26 )
          goto LABEL_43;
        if ( v26 > 0 )
          v12 = (unsigned __int16)v26 | 0x80070000;
        else
          v12 = v26;
        v24 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
        v25 = 1292;
      }
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        v25,
        "sqlite3_bind_text16 failed: [%d] %hs",
        v23,
        v24);
    }
    else
    {
      v12 = -2147467259;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1276,
        "sqlite3_prepare_v2 returned a null statement [%#x]",
        -2147467259);
    }
LABEL_52:
    std::wstring::~wstring(v32);
    goto LABEL_53;
  }
  if ( v8 < 0xC )
    std::_Xlen_string();
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  std::wstring::wstring(v34, v7, 0, L"DELETE FROM ", 12, v6, v7);
  std::operator+<unsigned short>(v32, v34, L" WHERE Name = ?;");
  std::wstring::~wstring(v34);
  v31 = 0;
  v9 = v32;
  if ( v33 > 7 )
    LODWORD(v9) = v32[0];
  v10 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v9, -1, 128, (__int64)&v31, 0);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v12 = (unsigned __int16)v10 | 0x80070000;
    else
      v12 = v10;
    v13 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1245,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v11,
      v13);
LABEL_12:
    std::wstring::~wstring(v32);
    v14 = v31;
    goto LABEL_53;
  }
  v14 = v31;
  if ( !v31 )
  {
    v12 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1251,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
    goto LABEL_52;
  }
  v15 = bindText(v31, 1, v4, -2, 0, 2);
  v16 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v12 = (unsigned __int16)v15 | 0x80070000;
    else
      v12 = v15;
    v17 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1259,
      "sqlite3_bind_text16 failed: [%d] %hs",
      v16,
      v17);
    goto LABEL_52;
  }
LABEL_43:
  std::wstring::~wstring(v32);
  v12 = 0;
  for ( i = 0; i < 100; ++i )
  {
    v28 = sqlite3_step(v14);
    if ( (unsigned int)(v28 - 5) > 1 )
      break;
    Sleep(5u);
  }
  if ( v28 != 101 )
  {
    if ( v28 > 0 )
      v12 = (unsigned __int16)v28 | 0x80070000;
    else
      v12 = v28;
    v29 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1301,
      "sqlite3_step failed: [%d] %hs",
      v28,
      v29);
  }
LABEL_53:
  if ( v14 )
    sqlite3_finalize(v14);
  return v12;
}

```

## disassembly

```asm
0x18002b590  push    rbp
0x18002b592  push    rbx
0x18002b593  push    rsi
0x18002b594  push    rdi
0x18002b595  push    r12
0x18002b597  push    r14
0x18002b599  push    r15
0x18002b59b  lea     rbp, [rsp-27h]
0x18002b5a0  sub     rsp, 90h
0x18002b5a7  mov     rax, cs:__security_cookie
0x18002b5ae  xor     rax, rsp
0x18002b5b1  mov     [rbp+57h+var_38], rax
0x18002b5b5  mov     r12, r8
0x18002b5b8  mov     r14, rdx
0x18002b5bb  mov     r15, rcx
0x18002b5be  mov     [rbp+57h+var_80], 0
0x18002b5c6  lea     rax, [rcx+68h]
0x18002b5ca  mov     rdx, [rax+10h]
0x18002b5ce  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18002b5d8  sub     rcx, rdx
0x18002b5db  test    r8, r8
0x18002b5de  jnz     loc_18002B77B
0x18002b5e4  cmp     rcx, 0Ch
0x18002b5e8  jb      loc_18002BA0B
0x18002b5ee  cmp     qword ptr [rax+18h], 7
0x18002b5f3  jbe     short loc_18002B5F8
0x18002b5f5  mov     rax, [rax]
0x18002b5f8  mov     [rsp+0C0h+var_90], rdx
0x18002b5fd  mov     [rsp+0C0h+var_98], rax
0x18002b602  mov     [rsp+0C0h+var_A0], 0Ch
0x18002b60b  lea     r9, aDeleteFrom; "DELETE FROM "
0x18002b612  lea     rcx, [rbp+57h+var_58]
0x18002b616  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002b61b  nop
0x18002b61c  lea     r8, aWhereName; " WHERE Name = ?;"
0x18002b623  lea     rdx, [rbp+57h+var_58]
0x18002b627  lea     rcx, [rbp+57h+var_78]
0x18002b62b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002b630  nop
0x18002b631  lea     rcx, [rbp+57h+var_58]; void *
0x18002b635  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b63a  mov     [rbp+57h+var_80], 0
0x18002b642  lea     rdx, [rbp+57h+var_78]
0x18002b646  cmp     [rbp+57h+var_60], 7
0x18002b64b  cmova   rdx, qword ptr [rbp+57h+var_78]
0x18002b650  mov     [rsp+0C0h+var_98], 0
0x18002b659  lea     rax, [rbp+57h+var_80]
0x18002b65d  mov     [rsp+0C0h+var_A0], rax
0x18002b662  mov     r9d, 80h
0x18002b668  or      r8d, 0FFFFFFFFh
0x18002b66c  mov     rcx, [r15+8]
0x18002b670  call    sqlite3Prepare16
0x18002b675  mov     edi, eax
0x18002b677  test    eax, eax
0x18002b679  jz      short loc_18002B6CF
0x18002b67b  test    eax, eax
0x18002b67d  jg      short loc_18002B683
0x18002b67f  mov     ebx, eax
0x18002b681  jmp     short loc_18002B68C
0x18002b683  movzx   ebx, di
0x18002b686  or      ebx, 80070000h
0x18002b68c  mov     rcx, [r15+8]
0x18002b690  call    sqlite3_errmsg
0x18002b695  mov     [rsp+0C0h+var_98], rax
0x18002b69a  mov     dword ptr [rsp+0C0h+var_A0], edi
0x18002b69e  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18002b6a5  mov     r8d, 4DDh
0x18002b6ab  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002b6b2  mov     ecx, 1
0x18002b6b7  call    AslLogCallPrintf
0x18002b6bc  nop
0x18002b6bd  lea     rcx, [rbp+57h+var_78]; void *
0x18002b6c1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b6c6  mov     rsi, [rbp+57h+var_80]
0x18002b6ca  jmp     loc_18002B9D7
0x18002b6cf  mov     rsi, [rbp+57h+var_80]
0x18002b6d3  test    rsi, rsi
0x18002b6d6  jz      short loc_18002B750
0x18002b6d8  mov     byte ptr [rsp+0C0h+var_98], 2
0x18002b6dd  mov     [rsp+0C0h+var_A0], 0
0x18002b6e6  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18002b6ed  mov     r8, r14
0x18002b6f0  lea     edi, [r9+3]
0x18002b6f4  mov     edx, edi
0x18002b6f6  mov     rcx, rsi
0x18002b6f9  call    bindText
0x18002b6fe  mov     r14d, eax
0x18002b701  test    eax, eax
0x18002b703  jz      short loc_18002B74B
0x18002b705  test    eax, eax
0x18002b707  jg      short loc_18002B70D
0x18002b709  mov     ebx, eax
0x18002b70b  jmp     short loc_18002B717
0x18002b70d  movzx   ebx, r14w
0x18002b711  or      ebx, 80070000h
0x18002b717  mov     rcx, [r15+8]
0x18002b71b  call    sqlite3_errmsg
0x18002b720  mov     [rsp+0C0h+var_98], rax
0x18002b725  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x18002b72a  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18002b731  mov     r8d, 4EBh
0x18002b737  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002b73e  mov     ecx, edi
0x18002b740  call    AslLogCallPrintf
0x18002b745  nop
0x18002b746  jmp     loc_18002B9CD
0x18002b74b  jmp     loc_18002B925
0x18002b750  mov     eax, 80004005h
0x18002b755  mov     ebx, eax
0x18002b757  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18002b75b  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18002b762  mov     r8d, 4E3h
0x18002b768  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002b76f  mov     ecx, 1
0x18002b774  call    AslLogCallPrintf
0x18002b779  jmp     short loc_18002B746
0x18002b77b  cmp     rcx, 0Dh
0x18002b77f  jb      loc_18002BA05
0x18002b785  cmp     qword ptr [rax+18h], 7
0x18002b78a  jbe     short loc_18002B78F
0x18002b78c  mov     rax, [rax]
0x18002b78f  mov     [rsp+0C0h+var_90], rdx
0x18002b794  mov     [rsp+0C0h+var_98], rax
0x18002b799  mov     [rsp+0C0h+var_A0], 0Dh
0x18002b7a2  lea     r9, aReplaceInto; "REPLACE INTO "
0x18002b7a9  lea     rcx, [rbp+57h+var_58]
0x18002b7ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002b7b2  nop
0x18002b7b3  lea     r8, aNameValueValue; " (Name, Value) VALUES (?, ?);"
0x18002b7ba  lea     rdx, [rbp+57h+var_58]
0x18002b7be  lea     rcx, [rbp+57h+var_78]
0x18002b7c2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002b7c7  nop
0x18002b7c8  lea     rcx, [rbp+57h+var_58]; void *
0x18002b7cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b7d1  mov     [rbp+57h+var_80], 0
0x18002b7d9  lea     rdx, [rbp+57h+var_78]
0x18002b7dd  cmp     [rbp+57h+var_60], 7
0x18002b7e2  cmova   rdx, qword ptr [rbp+57h+var_78]
0x18002b7e7  mov     [rsp+0C0h+var_98], 0
0x18002b7f0  lea     rax, [rbp+57h+var_80]
0x18002b7f4  mov     [rsp+0C0h+var_A0], rax
0x18002b7f9  mov     r9d, 80h
0x18002b7ff  or      r8d, 0FFFFFFFFh
0x18002b803  mov     rcx, [r15+8]
0x18002b807  call    sqlite3Prepare16
0x18002b80c  mov     edi, eax
0x18002b80e  test    eax, eax
0x18002b810  jz      short loc_18002B859
0x18002b812  test    eax, eax
0x18002b814  jg      short loc_18002B81A
0x18002b816  mov     ebx, eax
0x18002b818  jmp     short loc_18002B823
0x18002b81a  movzx   ebx, di
0x18002b81d  or      ebx, 80070000h
0x18002b823  mov     rcx, [r15+8]
0x18002b827  call    sqlite3_errmsg
0x18002b82c  mov     [rsp+0C0h+var_98], rax
0x18002b831  mov     dword ptr [rsp+0C0h+var_A0], edi
0x18002b835  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18002b83c  mov     r8d, 4F6h
0x18002b842  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002b849  mov     ecx, 1
0x18002b84e  call    AslLogCallPrintf
0x18002b853  nop
0x18002b854  jmp     loc_18002B6BD
0x18002b859  mov     rsi, [rbp+57h+var_80]
0x18002b85d  test    rsi, rsi
0x18002b860  jz      loc_18002B9A3
0x18002b866  mov     byte ptr [rsp+0C0h+var_98], 2
0x18002b86b  mov     [rsp+0C0h+var_A0], 0
0x18002b874  mov     rbx, 0FFFFFFFFFFFFFFFEh
0x18002b87b  mov     r9, rbx
0x18002b87e  mov     r8, r14
0x18002b881  lea     edi, [rbx+3]
0x18002b884  mov     edx, edi
0x18002b886  mov     rcx, rsi
0x18002b889  call    bindText
0x18002b88e  mov     r14d, eax
0x18002b891  test    eax, eax
0x18002b893  jz      short loc_18002B8DA
0x18002b895  test    eax, eax
0x18002b897  jg      short loc_18002B89D
0x18002b899  mov     ebx, eax
0x18002b89b  jmp     short loc_18002B8A7
0x18002b89d  movzx   ebx, r14w
0x18002b8a1  or      ebx, 80070000h
0x18002b8a7  mov     rcx, [r15+8]
0x18002b8ab  call    sqlite3_errmsg
0x18002b8b0  mov     r8d, 504h
0x18002b8b6  mov     [rsp+0C0h+var_98], rax
0x18002b8bb  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18002b8c2  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x18002b8c7  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002b8ce  mov     ecx, edi
0x18002b8d0  call    AslLogCallPrintf
0x18002b8d5  jmp     loc_18002B9CD
0x18002b8da  mov     byte ptr [rsp+0C0h+var_98], 2
0x18002b8df  mov     [rsp+0C0h+var_A0], 0
0x18002b8e8  mov     r9, rbx
0x18002b8eb  mov     r8, r12
0x18002b8ee  mov     edx, 2
0x18002b8f3  mov     rcx, rsi
0x18002b8f6  call    bindText
0x18002b8fb  mov     r14d, eax
0x18002b8fe  test    eax, eax
0x18002b900  jz      short loc_18002B925
0x18002b902  test    eax, eax
0x18002b904  jg      short loc_18002B90A
0x18002b906  mov     ebx, eax
0x18002b908  jmp     short loc_18002B914
0x18002b90a  movzx   ebx, r14w
0x18002b90e  or      ebx, 80070000h
0x18002b914  mov     rcx, [r15+8]
0x18002b918  call    sqlite3_errmsg
0x18002b91d  mov     r8d, 50Ch
0x18002b923  jmp     short loc_18002B8B6
0x18002b925  lea     rcx, [rbp+57h+var_78]; void *
0x18002b929  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b92e  xor     ebx, ebx
0x18002b930  xor     r12d, r12d
0x18002b933  mov     rcx, rsi
0x18002b936  call    sqlite3_step
0x18002b93b  mov     r14d, eax
0x18002b93e  lea     ecx, [rax-5]
0x18002b941  cmp     ecx, edi
0x18002b943  ja      short loc_18002B959
0x18002b945  mov     ecx, 5; dwMilliseconds
0x18002b94a  call    cs:__imp_Sleep
0x18002b950  add     r12d, edi
0x18002b953  cmp     r12d, 64h ; 'd'
0x18002b957  jl      short loc_18002B933
0x18002b959  cmp     r14d, 65h ; 'e'
0x18002b95d  jz      short loc_18002B9D7
0x18002b95f  test    r14d, r14d
0x18002b962  jg      short loc_18002B969
0x18002b964  mov     ebx, r14d
0x18002b967  jmp     short loc_18002B973
0x18002b969  movzx   ebx, r14w
0x18002b96d  or      ebx, 80070000h
0x18002b973  mov     rcx, [r15+8]
0x18002b977  call    sqlite3_errmsg
0x18002b97c  mov     [rsp+0C0h+var_98], rax
0x18002b981  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x18002b986  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18002b98d  mov     r8d, 515h
0x18002b993  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002b99a  mov     ecx, edi
0x18002b99c  call    AslLogCallPrintf
0x18002b9a1  jmp     short loc_18002B9D7
0x18002b9a3  mov     eax, 80004005h
0x18002b9a8  mov     ebx, eax
0x18002b9aa  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18002b9ae  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18002b9b5  mov     r8d, 4FCh
0x18002b9bb  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002b9c2  mov     ecx, 1
0x18002b9c7  call    AslLogCallPrintf
0x18002b9cc  nop
0x18002b9cd  lea     rcx, [rbp+57h+var_78]; void *
0x18002b9d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b9d6  nop
0x18002b9d7  test    rsi, rsi
0x18002b9da  jz      short loc_18002B9E5
0x18002b9dc  mov     rcx, rsi
0x18002b9df  call    sqlite3_finalize
0x18002b9e4  nop
0x18002b9e5  mov     eax, ebx
0x18002b9e7  mov     rcx, [rbp+57h+var_38]
0x18002b9eb  xor     rcx, rsp; StackCookie
0x18002b9ee  call    __security_check_cookie
0x18002b9f3  add     rsp, 90h
0x18002b9fa  pop     r15
0x18002b9fc  pop     r14
0x18002b9fe  pop     r12
0x18002ba00  pop     rdi
0x18002ba01  pop     rsi
0x18002ba02  pop     rbx
0x18002ba03  pop     rbp
0x18002ba04  retn
0x18002ba05  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18002ba0b  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
