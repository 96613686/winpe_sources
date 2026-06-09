# Windows::Compat::Inventory::SqliteInvCache::SetMetadata(ushort const *,ulong)

- ea: `0x180023bd0`
- end: `0x180023eb4`
- name: `?SetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEBGK@Z`
- size: `740`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180004ea0`
- `0x18001209c`
- `0x1800134b8`
- `0x180023bd0`
- `0x1800276cc`
- `0x180027d3c`
- `0x18002aa18`
- `0x18004c020`
- `0x180059d64`
- `0x1800a494c`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023e0f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023e0f`

## string_xrefs

- `0x180023c3f`: `REPLACE INTO `
- `0x180023d12`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x180023e65`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::SetMetadata(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  unsigned int v3; // ebx
  int v4; // esi
  _QWORD *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int128 *v9; // rdx
  int v10; // eax
  int v11; // edi
  __int64 v12; // r14
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // esi
  __int64 v16; // rax
  __int64 v17; // r8
  const char *v18; // r9
  _QWORD *v19; // rax
  int i; // r12d
  __int64 v22; // [rsp+20h] [rbp-49h]
  __int64 v23; // [rsp+20h] [rbp-49h]
  __int64 v24; // [rsp+28h] [rbp-41h]
  __int64 v25; // [rsp+28h] [rbp-41h]
  __int64 v26; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+40h] [rbp-29h] BYREF
  __int128 v28; // [rsp+48h] [rbp-21h] BYREF
  __int128 v29; // [rsp+58h] [rbp-11h]
  char *Src[4]; // [rsp+68h] [rbp-1h] BYREF

  v3 = a3;
  v4 = (int)a2;
  v6 = (_QWORD *)((char *)this + 104);
  v7 = *((_QWORD *)this + 15);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v7) < 0xD )
    std::_Xlen_string();
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  std::wstring::wstring(Src, v6, a3, L"REPLACE INTO ", 13, v6, v7);
  v8 = std::wstring::append(Src, L" (Name, Value) VALUES (?, ?);");
  v28 = 0;
  v29 = 0;
  v28 = *(_OWORD *)v8;
  v29 = *(_OWORD *)(v8 + 16);
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  *(_WORD *)v8 = 0;
  std::wstring::~wstring(Src);
  v27 = 0;
  v9 = &v28;
  if ( *((_QWORD *)&v29 + 1) > 7u )
    LODWORD(v9) = v28;
  v10 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v9, -1, 128, (__int64)&v27, 0);
  v11 = v10;
  v12 = v27;
  if ( v10 )
  {
    if ( v10 > 0 )
      v13 = (unsigned __int16)v10 | 0x80070000;
    else
      v13 = v10;
    v25 = sqlite3_errmsg(*((_QWORD *)this + 1));
    LODWORD(v22) = v11;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1148,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v22,
      v25);
    goto LABEL_36;
  }
  if ( v27 )
  {
    LOBYTE(v24) = 2;
    v14 = bindText(v27, 1, v4, -2, 0, v24);
    v15 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v13 = (unsigned __int16)v14 | 0x80070000;
      else
        v13 = v14;
      v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v17 = 1162;
    }
    else
    {
      v19 = (_QWORD *)std::to_wstring(Src, v3);
      if ( v19[3] > 7u )
        v19 = (_QWORD *)*v19;
      LOBYTE(v26) = 2;
      v15 = bindText(v12, 2, (_DWORD)v19, -2, -1, v26);
      std::wstring::~wstring(Src);
      if ( !v15 )
      {
        v13 = 0;
        for ( i = 0; i < 100; ++i )
        {
          v15 = sqlite3_step(v12);
          if ( (unsigned int)(v15 - 5) > 1 )
            break;
          Sleep(5u);
        }
        if ( v15 == 101 )
          goto LABEL_36;
        if ( v15 > 0 )
          v13 = (unsigned __int16)v15 | 0x80070000;
        else
          v13 = v15;
        v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v18 = "sqlite3_step failed: [%d] %hs";
        v17 = 1177;
        goto LABEL_19;
      }
      if ( v15 > 0 )
        v13 = (unsigned __int16)v15 | 0x80070000;
      else
        v13 = v15;
      v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v17 = 1170;
    }
    v18 = "sqlite3_bind_text16 failed: [%d] %hs";
LABEL_19:
    LODWORD(v23) = v15;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::SetMetadata", v17, v18, v23, v16);
    goto LABEL_36;
  }
  v13 = -2147467259;
  AslLogCallPrintf(
    1,
    "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
    1154,
    "sqlite3_prepare_v2 returned a null statement [%#x]",
    -2147467259);
LABEL_36:
  if ( v12 )
    sqlite3_finalize(v12);
  std::wstring::~wstring((char **)&v28);
  return v13;
}

```

## disassembly

```asm
0x180023bd0  push    rbp
0x180023bd2  push    rbx
0x180023bd3  push    rsi
0x180023bd4  push    rdi
0x180023bd5  push    r12
0x180023bd7  push    r14
0x180023bd9  push    r15
0x180023bdb  lea     rbp, [rsp-27h]
0x180023be0  sub     rsp, 90h
0x180023be7  mov     rax, cs:__security_cookie
0x180023bee  xor     rax, rsp
0x180023bf1  mov     [rbp+57h+var_38], rax
0x180023bf5  mov     ebx, r8d
0x180023bf8  mov     rsi, rdx
0x180023bfb  mov     r15, rcx
0x180023bfe  lea     rdx, [rcx+68h]
0x180023c02  mov     rcx, [rdx+10h]
0x180023c06  mov     rax, 7FFFFFFFFFFFFFFEh
0x180023c10  sub     rax, rcx
0x180023c13  cmp     rax, 0Dh
0x180023c17  jb      loc_180023EAE
0x180023c1d  mov     r12d, 7
0x180023c23  cmp     [rdx+18h], r12
0x180023c27  jbe     short loc_180023C2C
0x180023c29  mov     rdx, [rdx]
0x180023c2c  mov     [rsp+0C0h+var_90], rcx
0x180023c31  mov     [rsp+0C0h+var_98], rdx
0x180023c36  mov     [rsp+0C0h+var_A0], 0Dh
0x180023c3f  lea     r9, aReplaceInto; "REPLACE INTO "
0x180023c46  lea     rcx, [rbp+57h+Src]
0x180023c4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180023c4f  nop
0x180023c50  lea     rdx, aNameValueValue; " (Name, Value) VALUES (?, ?);"
0x180023c57  lea     rcx, [rbp+57h+Src]; Src
0x180023c5b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180023c60  xorps   xmm0, xmm0
0x180023c63  movups  [rbp+57h+var_78], xmm0
0x180023c67  xorps   xmm1, xmm1
0x180023c6a  movdqu  [rbp+57h+var_68], xmm1
0x180023c6f  movups  xmm0, xmmword ptr [rax]
0x180023c72  movups  [rbp+57h+var_78], xmm0
0x180023c76  movups  xmm1, xmmword ptr [rax+10h]
0x180023c7a  movups  [rbp+57h+var_68], xmm1
0x180023c7e  mov     qword ptr [rax+10h], 0
0x180023c86  mov     [rax+18h], r12
0x180023c8a  xor     ecx, ecx
0x180023c8c  mov     [rax], cx
0x180023c8f  lea     rcx, [rbp+57h+Src]
0x180023c93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023c98  nop
0x180023c99  mov     [rbp+57h+var_80], 0
0x180023ca1  lea     rdx, [rbp+57h+var_78]
0x180023ca5  cmp     qword ptr [rbp+57h+var_68+8], r12
0x180023ca9  cmova   rdx, qword ptr [rbp+57h+var_78]
0x180023cae  mov     [rsp+0C0h+var_98], 0
0x180023cb7  lea     rax, [rbp+57h+var_80]
0x180023cbb  mov     [rsp+0C0h+var_A0], rax
0x180023cc0  mov     r9d, 80h
0x180023cc6  or      r8d, 0FFFFFFFFh
0x180023cca  mov     rcx, [r15+8]
0x180023cce  call    sqlite3Prepare16
0x180023cd3  mov     edi, eax
0x180023cd5  mov     r14, [rbp+57h+var_80]
0x180023cd9  test    eax, eax
0x180023cdb  jz      short loc_180023D23
0x180023cdd  test    eax, eax
0x180023cdf  jg      short loc_180023CE5
0x180023ce1  mov     ebx, eax
0x180023ce3  jmp     short loc_180023CEE
0x180023ce5  movzx   ebx, di
0x180023ce8  or      ebx, 80070000h
0x180023cee  mov     rcx, [r15+8]
0x180023cf2  call    sqlite3_errmsg
0x180023cf7  mov     [rsp+0C0h+var_98], rax
0x180023cfc  mov     dword ptr [rsp+0C0h+var_A0], edi
0x180023d00  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x180023d07  mov     r8d, 47Ch
0x180023d0d  mov     ecx, 1
0x180023d12  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x180023d19  call    AslLogCallPrintf
0x180023d1e  jmp     loc_180023E77
0x180023d23  test    r14, r14
0x180023d26  jz      loc_180023E4F
0x180023d2c  mov     byte ptr [rsp+0C0h+var_98], 2
0x180023d31  mov     [rsp+0C0h+var_A0], 0
0x180023d3a  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180023d41  mov     r8, rsi
0x180023d44  lea     edi, [r9+3]
0x180023d48  mov     edx, edi
0x180023d4a  mov     rcx, r14
0x180023d4d  call    bindText
0x180023d52  mov     esi, eax
0x180023d54  test    eax, eax
0x180023d56  jz      short loc_180023D8C
0x180023d58  test    eax, eax
0x180023d5a  jg      short loc_180023D60
0x180023d5c  mov     ebx, eax
0x180023d5e  jmp     short loc_180023D69
0x180023d60  movzx   ebx, si
0x180023d63  or      ebx, 80070000h
0x180023d69  mov     rcx, [r15+8]
0x180023d6d  call    sqlite3_errmsg
0x180023d72  mov     r8d, 48Ah
0x180023d78  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180023d7f  mov     [rsp+0C0h+var_98], rax
0x180023d84  mov     dword ptr [rsp+0C0h+var_A0], esi
0x180023d88  mov     ecx, edi
0x180023d8a  jmp     short loc_180023D12
0x180023d8c  mov     edx, ebx
0x180023d8e  lea     rcx, [rbp+57h+Src]
0x180023d92  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x180023d97  nop
0x180023d98  cmp     [rax+18h], r12
0x180023d9c  jbe     short loc_180023DA1
0x180023d9e  mov     rax, [rax]
0x180023da1  mov     byte ptr [rsp+0C0h+var_98], 2
0x180023da6  mov     [rsp+0C0h+var_A0], 0FFFFFFFFFFFFFFFFh
0x180023daf  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180023db6  mov     r8, rax
0x180023db9  lea     edx, [r9+4]
0x180023dbd  mov     rcx, r14
0x180023dc0  call    bindText
0x180023dc5  mov     esi, eax
0x180023dc7  lea     rcx, [rbp+57h+Src]
0x180023dcb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023dd0  test    esi, esi
0x180023dd2  jz      short loc_180023DF4
0x180023dd4  jg      short loc_180023DDA
0x180023dd6  mov     ebx, esi
0x180023dd8  jmp     short loc_180023DE3
0x180023dda  movzx   ebx, si
0x180023ddd  or      ebx, 80070000h
0x180023de3  mov     rcx, [r15+8]
0x180023de7  call    sqlite3_errmsg
0x180023dec  mov     r8d, 492h
0x180023df2  jmp     short loc_180023D78
0x180023df4  xor     ebx, ebx
0x180023df6  xor     r12d, r12d
0x180023df9  mov     rcx, r14
0x180023dfc  call    sqlite3_step
0x180023e01  mov     esi, eax
0x180023e03  lea     ecx, [rax-5]
0x180023e06  cmp     ecx, edi
0x180023e08  ja      short loc_180023E1E
0x180023e0a  mov     ecx, 5; dwMilliseconds
0x180023e0f  call    cs:__imp_Sleep
0x180023e15  add     r12d, edi
0x180023e18  cmp     r12d, 64h ; 'd'
0x180023e1c  jl      short loc_180023DF9
0x180023e1e  cmp     esi, 65h ; 'e'
0x180023e21  jz      short loc_180023E77
0x180023e23  test    esi, esi
0x180023e25  jg      short loc_180023E2B
0x180023e27  mov     ebx, esi
0x180023e29  jmp     short loc_180023E34
0x180023e2b  movzx   ebx, si
0x180023e2e  or      ebx, 80070000h
0x180023e34  mov     rcx, [r15+8]
0x180023e38  call    sqlite3_errmsg
0x180023e3d  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180023e44  mov     r8d, 499h
0x180023e4a  jmp     loc_180023D7F
0x180023e4f  mov     ebx, 80004005h
0x180023e54  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180023e58  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x180023e5f  mov     r8d, 482h
0x180023e65  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x180023e6c  mov     ecx, 1
0x180023e71  call    AslLogCallPrintf
0x180023e76  nop
0x180023e77  test    r14, r14
0x180023e7a  jz      short loc_180023E85
0x180023e7c  mov     rcx, r14
0x180023e7f  call    sqlite3_finalize
0x180023e84  nop
0x180023e85  lea     rcx, [rbp+57h+var_78]
0x180023e89  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023e8e  mov     eax, ebx
0x180023e90  mov     rcx, [rbp+57h+var_38]
0x180023e94  xor     rcx, rsp; StackCookie
0x180023e97  call    __security_check_cookie
0x180023e9c  add     rsp, 90h
0x180023ea3  pop     r15
0x180023ea5  pop     r14
0x180023ea7  pop     r12
0x180023ea9  pop     rdi
0x180023eaa  pop     rsi
0x180023eab  pop     rbx
0x180023eac  pop     rbp
0x180023ead  retn
0x180023eae  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
