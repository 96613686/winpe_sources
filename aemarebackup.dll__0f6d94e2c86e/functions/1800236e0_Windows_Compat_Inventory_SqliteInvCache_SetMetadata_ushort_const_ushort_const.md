# Windows::Compat::Inventory::SqliteInvCache::SetMetadata(ushort const *,ushort const *)

- ea: `0x1800236e0`
- end: `0x180023bbd`
- name: `?SetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEBG0@Z`
- size: `1245`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004ea0`
- `0x18001209c`
- `0x1800134b8`
- `0x1800236e0`
- `0x1800276cc`
- `0x180027d3c`
- `0x18004c020`
- `0x180059d64`
- `0x1800a494c`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023af6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023af6`

## string_xrefs

- `0x18002375b`: `DELETE FROM `
- `0x180023920`: `REPLACE INTO `
- `0x180023829`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x1800238b5`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x1800238e6`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x1800239ee`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x180023a73`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x180023b3f`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x180023b67`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`

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
  __int64 v9; // rax
  __int128 *v10; // rdx
  int v11; // eax
  int v12; // edi
  unsigned int v13; // ebx
  const char *v14; // rax
  __int64 v15; // rsi
  int v16; // eax
  int v17; // r14d
  const char *v18; // rax
  __int64 v19; // rax
  __int128 *v20; // rdx
  int v21; // eax
  int v22; // edi
  const char *v23; // rax
  int v24; // eax
  int v25; // r14d
  const char *v26; // rax
  __int64 v27; // r8
  int v28; // eax
  int i; // r12d
  int v30; // r14d
  const char *v31; // rax
  __int64 v33; // [rsp+40h] [rbp-29h] BYREF
  __int128 v34; // [rsp+48h] [rbp-21h] BYREF
  __int128 v35; // [rsp+58h] [rbp-11h]
  char *Src[4]; // [rsp+68h] [rbp-1h] BYREF

  v3 = (int)a3;
  v4 = (int)a2;
  v33 = 0;
  v6 = (_QWORD *)((char *)this + 104);
  v7 = *((_QWORD *)this + 15);
  v8 = 0x7FFFFFFFFFFFFFFELL - v7;
  if ( a3 )
  {
    if ( v8 < 0xD )
      std::_Xlen_string();
    if ( v6[3] > 7u )
      v6 = (_QWORD *)*v6;
    std::wstring::wstring(Src, v7, a3, L"REPLACE INTO ", 13, v6, v7);
    v19 = std::wstring::append(Src, L" (Name, Value) VALUES (?, ?);");
    v34 = 0;
    v35 = 0;
    v34 = *(_OWORD *)v19;
    v35 = *(_OWORD *)(v19 + 16);
    *(_QWORD *)(v19 + 16) = 0;
    *(_QWORD *)(v19 + 24) = 7;
    *(_WORD *)v19 = 0;
    std::wstring::~wstring(Src);
    v33 = 0;
    v20 = &v34;
    if ( *((_QWORD *)&v35 + 1) > 7u )
      LODWORD(v20) = v34;
    v21 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v20, -1, 128, (__int64)&v33, 0);
    v22 = v21;
    if ( v21 )
    {
      if ( v21 > 0 )
        v13 = (unsigned __int16)v21 | 0x80070000;
      else
        v13 = v21;
      v23 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1270,
        "sqlite3_prepare_v2 failed: [%d] %hs",
        v22,
        v23);
      goto LABEL_12;
    }
    v15 = v33;
    if ( v33 )
    {
      v24 = bindText(v33, 1, v4, -2, 0, 2);
      v25 = v24;
      if ( v24 )
      {
        if ( v24 > 0 )
          v13 = (unsigned __int16)v24 | 0x80070000;
        else
          v13 = v24;
        v26 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
        v27 = 1284;
      }
      else
      {
        v28 = bindText(v15, 2, v3, -2, 0, 2);
        v25 = v28;
        if ( !v28 )
          goto LABEL_43;
        if ( v28 > 0 )
          v13 = (unsigned __int16)v28 | 0x80070000;
        else
          v13 = v28;
        v26 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
        v27 = 1292;
      }
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        v27,
        "sqlite3_bind_text16 failed: [%d] %hs",
        v25,
        v26);
    }
    else
    {
      v13 = -2147467259;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1276,
        "sqlite3_prepare_v2 returned a null statement [%#x]",
        -2147467259);
    }
LABEL_52:
    std::wstring::~wstring((char **)&v34);
    goto LABEL_53;
  }
  if ( v8 < 0xC )
    std::_Xlen_string();
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  std::wstring::wstring(Src, v7, 0, L"DELETE FROM ", 12, v6, v7);
  v9 = std::wstring::append(Src, L" WHERE Name = ?;");
  v34 = 0;
  v35 = 0;
  v34 = *(_OWORD *)v9;
  v35 = *(_OWORD *)(v9 + 16);
  *(_QWORD *)(v9 + 16) = 0;
  *(_QWORD *)(v9 + 24) = 7;
  *(_WORD *)v9 = 0;
  std::wstring::~wstring(Src);
  v33 = 0;
  v10 = &v34;
  if ( *((_QWORD *)&v35 + 1) > 7u )
    LODWORD(v10) = v34;
  v11 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v10, -1, 128, (__int64)&v33, 0);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v13 = (unsigned __int16)v11 | 0x80070000;
    else
      v13 = v11;
    v14 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1245,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v12,
      v14);
LABEL_12:
    std::wstring::~wstring((char **)&v34);
    v15 = v33;
    goto LABEL_53;
  }
  v15 = v33;
  if ( !v33 )
  {
    v13 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1251,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
    goto LABEL_52;
  }
  v16 = bindText(v33, 1, v4, -2, 0, 2);
  v17 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v13 = (unsigned __int16)v16 | 0x80070000;
    else
      v13 = v16;
    v18 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1259,
      "sqlite3_bind_text16 failed: [%d] %hs",
      v17,
      v18);
    goto LABEL_52;
  }
LABEL_43:
  std::wstring::~wstring((char **)&v34);
  v13 = 0;
  for ( i = 0; i < 100; ++i )
  {
    v30 = sqlite3_step(v15);
    if ( (unsigned int)(v30 - 5) > 1 )
      break;
    Sleep(5u);
  }
  if ( v30 != 101 )
  {
    if ( v30 > 0 )
      v13 = (unsigned __int16)v30 | 0x80070000;
    else
      v13 = v30;
    v31 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1301,
      "sqlite3_step failed: [%d] %hs",
      v30,
      v31);
  }
LABEL_53:
  if ( v15 )
    sqlite3_finalize(v15);
  return v13;
}

```

## disassembly

```asm
0x1800236e0  push    rbp
0x1800236e2  push    rbx
0x1800236e3  push    rsi
0x1800236e4  push    rdi
0x1800236e5  push    r12
0x1800236e7  push    r14
0x1800236e9  push    r15
0x1800236eb  lea     rbp, [rsp-27h]
0x1800236f0  sub     rsp, 90h
0x1800236f7  mov     rax, cs:__security_cookie
0x1800236fe  xor     rax, rsp
0x180023701  mov     [rbp+57h+var_38], rax
0x180023705  mov     r12, r8
0x180023708  mov     r14, rdx
0x18002370b  mov     r15, rcx
0x18002370e  mov     [rbp+57h+var_80], 0
0x180023716  lea     rax, [rcx+68h]
0x18002371a  mov     rdx, [rax+10h]
0x18002371e  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180023728  sub     rcx, rdx
0x18002372b  test    r8, r8
0x18002372e  jnz     loc_1800238F9
0x180023734  cmp     rcx, 0Ch
0x180023738  jb      loc_180023BB7
0x18002373e  cmp     qword ptr [rax+18h], 7
0x180023743  jbe     short loc_180023748
0x180023745  mov     rax, [rax]
0x180023748  mov     [rsp+0C0h+var_90], rdx
0x18002374d  mov     [rsp+0C0h+var_98], rax
0x180023752  mov     [rsp+0C0h+var_A0], 0Ch
0x18002375b  lea     r9, aDeleteFrom; "DELETE FROM "
0x180023762  lea     rcx, [rbp+57h+Src]
0x180023766  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002376b  nop
0x18002376c  lea     rdx, aWhereName; " WHERE Name = ?;"
0x180023773  lea     rcx, [rbp+57h+Src]; Src
0x180023777  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002377c  xorps   xmm0, xmm0
0x18002377f  movups  [rbp+57h+var_78], xmm0
0x180023783  xorps   xmm1, xmm1
0x180023786  movdqu  [rbp+57h+var_68], xmm1
0x18002378b  movups  xmm0, xmmword ptr [rax]
0x18002378e  movups  [rbp+57h+var_78], xmm0
0x180023792  movups  xmm1, xmmword ptr [rax+10h]
0x180023796  movups  [rbp+57h+var_68], xmm1
0x18002379a  mov     qword ptr [rax+10h], 0
0x1800237a2  mov     qword ptr [rax+18h], 7
0x1800237aa  xor     ecx, ecx
0x1800237ac  mov     [rax], cx
0x1800237af  lea     rcx, [rbp+57h+Src]
0x1800237b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800237b8  mov     [rbp+57h+var_80], 0
0x1800237c0  lea     rdx, [rbp+57h+var_78]
0x1800237c4  cmp     qword ptr [rbp+57h+var_68+8], 7
0x1800237c9  cmova   rdx, qword ptr [rbp+57h+var_78]
0x1800237ce  mov     [rsp+0C0h+var_98], 0
0x1800237d7  lea     rax, [rbp+57h+var_80]
0x1800237db  mov     [rsp+0C0h+var_A0], rax
0x1800237e0  mov     r9d, 80h
0x1800237e6  or      r8d, 0FFFFFFFFh
0x1800237ea  mov     rcx, [r15+8]
0x1800237ee  call    sqlite3Prepare16
0x1800237f3  mov     edi, eax
0x1800237f5  test    eax, eax
0x1800237f7  jz      short loc_18002384D
0x1800237f9  test    eax, eax
0x1800237fb  jg      short loc_180023801
0x1800237fd  mov     ebx, eax
0x1800237ff  jmp     short loc_18002380A
0x180023801  movzx   ebx, di
0x180023804  or      ebx, 80070000h
0x18002380a  mov     rcx, [r15+8]
0x18002380e  call    sqlite3_errmsg
0x180023813  mov     [rsp+0C0h+var_98], rax
0x180023818  mov     dword ptr [rsp+0C0h+var_A0], edi
0x18002381c  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x180023823  mov     r8d, 4DDh
0x180023829  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x180023830  mov     ecx, 1
0x180023835  call    AslLogCallPrintf
0x18002383a  nop
0x18002383b  lea     rcx, [rbp+57h+var_78]
0x18002383f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023844  mov     rsi, [rbp+57h+var_80]
0x180023848  jmp     loc_180023B83
0x18002384d  mov     rsi, [rbp+57h+var_80]
0x180023851  test    rsi, rsi
0x180023854  jz      short loc_1800238CE
0x180023856  mov     byte ptr [rsp+0C0h+var_98], 2
0x18002385b  mov     [rsp+0C0h+var_A0], 0
0x180023864  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18002386b  mov     r8, r14
0x18002386e  lea     edi, [r9+3]
0x180023872  mov     edx, edi
0x180023874  mov     rcx, rsi
0x180023877  call    bindText
0x18002387c  mov     r14d, eax
0x18002387f  test    eax, eax
0x180023881  jz      short loc_1800238C9
0x180023883  test    eax, eax
0x180023885  jg      short loc_18002388B
0x180023887  mov     ebx, eax
0x180023889  jmp     short loc_180023895
0x18002388b  movzx   ebx, r14w
0x18002388f  or      ebx, 80070000h
0x180023895  mov     rcx, [r15+8]
0x180023899  call    sqlite3_errmsg
0x18002389e  mov     [rsp+0C0h+var_98], rax
0x1800238a3  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x1800238a8  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x1800238af  mov     r8d, 4EBh
0x1800238b5  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800238bc  mov     ecx, edi
0x1800238be  call    AslLogCallPrintf
0x1800238c3  nop
0x1800238c4  jmp     loc_180023B79
0x1800238c9  jmp     loc_180023AD1
0x1800238ce  mov     eax, 80004005h
0x1800238d3  mov     ebx, eax
0x1800238d5  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800238d9  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x1800238e0  mov     r8d, 4E3h
0x1800238e6  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800238ed  mov     ecx, 1
0x1800238f2  call    AslLogCallPrintf
0x1800238f7  jmp     short loc_1800238C4
0x1800238f9  cmp     rcx, 0Dh
0x1800238fd  jb      loc_180023BB1
0x180023903  cmp     qword ptr [rax+18h], 7
0x180023908  jbe     short loc_18002390D
0x18002390a  mov     rax, [rax]
0x18002390d  mov     [rsp+0C0h+var_90], rdx
0x180023912  mov     [rsp+0C0h+var_98], rax
0x180023917  mov     [rsp+0C0h+var_A0], 0Dh
0x180023920  lea     r9, aReplaceInto; "REPLACE INTO "
0x180023927  lea     rcx, [rbp+57h+Src]
0x18002392b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180023930  nop
0x180023931  lea     rdx, aNameValueValue; " (Name, Value) VALUES (?, ?);"
0x180023938  lea     rcx, [rbp+57h+Src]; Src
0x18002393c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180023941  xorps   xmm0, xmm0
0x180023944  movups  [rbp+57h+var_78], xmm0
0x180023948  xorps   xmm1, xmm1
0x18002394b  movdqu  [rbp+57h+var_68], xmm1
0x180023950  movups  xmm0, xmmword ptr [rax]
0x180023953  movups  [rbp+57h+var_78], xmm0
0x180023957  movups  xmm1, xmmword ptr [rax+10h]
0x18002395b  movups  [rbp+57h+var_68], xmm1
0x18002395f  mov     qword ptr [rax+10h], 0
0x180023967  mov     qword ptr [rax+18h], 7
0x18002396f  xor     ecx, ecx
0x180023971  mov     [rax], cx
0x180023974  lea     rcx, [rbp+57h+Src]
0x180023978  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002397d  mov     [rbp+57h+var_80], 0
0x180023985  lea     rdx, [rbp+57h+var_78]
0x180023989  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18002398e  cmova   rdx, qword ptr [rbp+57h+var_78]
0x180023993  mov     [rsp+0C0h+var_98], 0
0x18002399c  lea     rax, [rbp+57h+var_80]
0x1800239a0  mov     [rsp+0C0h+var_A0], rax
0x1800239a5  mov     r9d, 80h
0x1800239ab  or      r8d, 0FFFFFFFFh
0x1800239af  mov     rcx, [r15+8]
0x1800239b3  call    sqlite3Prepare16
0x1800239b8  mov     edi, eax
0x1800239ba  test    eax, eax
0x1800239bc  jz      short loc_180023A05
0x1800239be  test    eax, eax
0x1800239c0  jg      short loc_1800239C6
0x1800239c2  mov     ebx, eax
0x1800239c4  jmp     short loc_1800239CF
0x1800239c6  movzx   ebx, di
0x1800239c9  or      ebx, 80070000h
0x1800239cf  mov     rcx, [r15+8]
0x1800239d3  call    sqlite3_errmsg
0x1800239d8  mov     [rsp+0C0h+var_98], rax
0x1800239dd  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1800239e1  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x1800239e8  mov     r8d, 4F6h
0x1800239ee  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800239f5  mov     ecx, 1
0x1800239fa  call    AslLogCallPrintf
0x1800239ff  nop
0x180023a00  jmp     loc_18002383B
0x180023a05  mov     rsi, [rbp+57h+var_80]
0x180023a09  test    rsi, rsi
0x180023a0c  jz      loc_180023B4F
0x180023a12  mov     byte ptr [rsp+0C0h+var_98], 2
0x180023a17  mov     [rsp+0C0h+var_A0], 0
0x180023a20  mov     rbx, 0FFFFFFFFFFFFFFFEh
0x180023a27  mov     r9, rbx
0x180023a2a  mov     r8, r14
0x180023a2d  lea     edi, [rbx+3]
0x180023a30  mov     edx, edi
0x180023a32  mov     rcx, rsi
0x180023a35  call    bindText
0x180023a3a  mov     r14d, eax
0x180023a3d  test    eax, eax
0x180023a3f  jz      short loc_180023A86
0x180023a41  test    eax, eax
0x180023a43  jg      short loc_180023A49
0x180023a45  mov     ebx, eax
0x180023a47  jmp     short loc_180023A53
0x180023a49  movzx   ebx, r14w
0x180023a4d  or      ebx, 80070000h
0x180023a53  mov     rcx, [r15+8]
0x180023a57  call    sqlite3_errmsg
0x180023a5c  mov     r8d, 504h
0x180023a62  mov     [rsp+0C0h+var_98], rax
0x180023a67  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180023a6e  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x180023a73  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x180023a7a  mov     ecx, edi
0x180023a7c  call    AslLogCallPrintf
0x180023a81  jmp     loc_180023B79
0x180023a86  mov     byte ptr [rsp+0C0h+var_98], 2
0x180023a8b  mov     [rsp+0C0h+var_A0], 0
0x180023a94  mov     r9, rbx
0x180023a97  mov     r8, r12
0x180023a9a  mov     edx, 2
0x180023a9f  mov     rcx, rsi
0x180023aa2  call    bindText
0x180023aa7  mov     r14d, eax
0x180023aaa  test    eax, eax
0x180023aac  jz      short loc_180023AD1
0x180023aae  test    eax, eax
0x180023ab0  jg      short loc_180023AB6
0x180023ab2  mov     ebx, eax
0x180023ab4  jmp     short loc_180023AC0
0x180023ab6  movzx   ebx, r14w
0x180023aba  or      ebx, 80070000h
0x180023ac0  mov     rcx, [r15+8]
0x180023ac4  call    sqlite3_errmsg
0x180023ac9  mov     r8d, 50Ch
0x180023acf  jmp     short loc_180023A62
0x180023ad1  lea     rcx, [rbp+57h+var_78]
0x180023ad5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023ada  xor     ebx, ebx
0x180023adc  xor     r12d, r12d
0x180023adf  mov     rcx, rsi
0x180023ae2  call    sqlite3_step
0x180023ae7  mov     r14d, eax
0x180023aea  lea     ecx, [rax-5]
0x180023aed  cmp     ecx, edi
0x180023aef  ja      short loc_180023B05
0x180023af1  mov     ecx, 5; dwMilliseconds
0x180023af6  call    cs:__imp_Sleep
0x180023afc  add     r12d, edi
0x180023aff  cmp     r12d, 64h ; 'd'
0x180023b03  jl      short loc_180023ADF
0x180023b05  cmp     r14d, 65h ; 'e'
0x180023b09  jz      short loc_180023B83
0x180023b0b  test    r14d, r14d
0x180023b0e  jg      short loc_180023B15
0x180023b10  mov     ebx, r14d
0x180023b13  jmp     short loc_180023B1F
0x180023b15  movzx   ebx, r14w
0x180023b19  or      ebx, 80070000h
0x180023b1f  mov     rcx, [r15+8]
0x180023b23  call    sqlite3_errmsg
0x180023b28  mov     [rsp+0C0h+var_98], rax
0x180023b2d  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x180023b32  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180023b39  mov     r8d, 515h
0x180023b3f  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x180023b46  mov     ecx, edi
0x180023b48  call    AslLogCallPrintf
0x180023b4d  jmp     short loc_180023B83
0x180023b4f  mov     eax, 80004005h
0x180023b54  mov     ebx, eax
0x180023b56  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180023b5a  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x180023b61  mov     r8d, 4FCh
0x180023b67  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x180023b6e  mov     ecx, 1
0x180023b73  call    AslLogCallPrintf
0x180023b78  nop
0x180023b79  lea     rcx, [rbp+57h+var_78]
0x180023b7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023b82  nop
0x180023b83  test    rsi, rsi
0x180023b86  jz      short loc_180023B91
0x180023b88  mov     rcx, rsi
0x180023b8b  call    sqlite3_finalize
0x180023b90  nop
0x180023b91  mov     eax, ebx
0x180023b93  mov     rcx, [rbp+57h+var_38]
0x180023b97  xor     rcx, rsp; StackCookie
0x180023b9a  call    __security_check_cookie
0x180023b9f  add     rsp, 90h
0x180023ba6  pop     r15
0x180023ba8  pop     r14
0x180023baa  pop     r12
0x180023bac  pop     rdi
0x180023bad  pop     rsi
0x180023bae  pop     rbx
0x180023baf  pop     rbp
0x180023bb0  retn
  ... truncated ...
```
