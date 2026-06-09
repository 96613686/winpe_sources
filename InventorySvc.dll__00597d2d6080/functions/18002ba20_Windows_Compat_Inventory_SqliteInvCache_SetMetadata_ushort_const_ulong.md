# Windows::Compat::Inventory::SqliteInvCache::SetMetadata(ushort const *,ulong)

- ea: `0x18002ba20`
- end: `0x18002bcd7`
- name: `?SetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEBGK@Z`
- size: `695`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180002bf0`
- `0x1800074f0`
- `0x1800109dc`
- `0x1800152d0`
- `0x18001f4a4`
- `0x18001fd88`
- `0x18002ba20`
- `0x18002e128`
- `0x180036be4`
- `0x1800817cc`
- `0x1800a1980`
- `0x1800a22c0`
- `0x1800a4690`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002bc32`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002bc32`

## string_xrefs

- `0x18002ba8a`: `REPLACE INTO `
- `0x18002bb34`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18002bc88`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`

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
  _QWORD *v8; // rdx
  int v9; // eax
  int v10; // edi
  __int64 v11; // r14
  unsigned int v12; // ebx
  int v13; // eax
  int v14; // esi
  __int64 v15; // rax
  __int64 v16; // r8
  const char *v17; // r9
  _QWORD *v18; // rax
  int i; // r15d
  __int64 v21; // [rsp+20h] [rbp-49h]
  __int64 v22; // [rsp+20h] [rbp-49h]
  __int64 v23; // [rsp+28h] [rbp-41h]
  __int64 v24; // [rsp+28h] [rbp-41h]
  __int64 v25; // [rsp+28h] [rbp-41h]
  __int64 v26; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v27[4]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v28[32]; // [rsp+68h] [rbp-1h] BYREF

  v3 = a3;
  v4 = (int)a2;
  v6 = (_QWORD *)((char *)this + 104);
  v7 = *((_QWORD *)this + 15);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v7) < 0xD )
    std::_Xlen_string();
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  std::wstring::wstring(v28, v6, a3, L"REPLACE INTO ", 13, v6, v7);
  std::operator+<unsigned short>(v27, v28, L" (Name, Value) VALUES (?, ?);");
  std::wstring::~wstring(v28);
  v26 = 0;
  v8 = v27;
  if ( v27[3] > 7u )
    LODWORD(v8) = v27[0];
  v9 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v8, -1, 128, (__int64)&v26, 0);
  v10 = v9;
  v11 = v26;
  if ( v9 )
  {
    if ( v9 > 0 )
      v12 = (unsigned __int16)v9 | 0x80070000;
    else
      v12 = v9;
    v24 = sqlite3_errmsg(*((_QWORD *)this + 1));
    LODWORD(v21) = v10;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1148,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v21,
      v24);
    goto LABEL_36;
  }
  if ( v26 )
  {
    LOBYTE(v23) = 2;
    v13 = bindText(v26, 1, v4, -2, 0, v23);
    v14 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v12 = (unsigned __int16)v13 | 0x80070000;
      else
        v12 = v13;
      v15 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v16 = 1162;
    }
    else
    {
      v18 = (_QWORD *)std::to_wstring(v28, v3);
      if ( v18[3] > 7u )
        v18 = (_QWORD *)*v18;
      LOBYTE(v25) = 2;
      v14 = bindText(v11, 2, (_DWORD)v18, -2, -1, v25);
      std::wstring::~wstring(v28);
      if ( !v14 )
      {
        v12 = 0;
        for ( i = 0; i < 100; ++i )
        {
          v14 = sqlite3_step(v11);
          if ( (unsigned int)(v14 - 5) > 1 )
            break;
          Sleep(5u);
        }
        if ( v14 == 101 )
          goto LABEL_36;
        if ( v14 > 0 )
          v12 = (unsigned __int16)v14 | 0x80070000;
        else
          v12 = v14;
        v15 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v17 = "sqlite3_step failed: [%d] %hs";
        v16 = 1177;
        goto LABEL_19;
      }
      if ( v14 > 0 )
        v12 = (unsigned __int16)v14 | 0x80070000;
      else
        v12 = v14;
      v15 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v16 = 1170;
    }
    v17 = "sqlite3_bind_text16 failed: [%d] %hs";
LABEL_19:
    LODWORD(v22) = v14;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::SetMetadata", v16, v17, v22, v15);
    goto LABEL_36;
  }
  v12 = -2147467259;
  AslLogCallPrintf(
    1,
    "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
    1154,
    "sqlite3_prepare_v2 returned a null statement [%#x]",
    -2147467259);
LABEL_36:
  if ( v11 )
    sqlite3_finalize(v11);
  std::wstring::~wstring(v27);
  return v12;
}

```

## disassembly

```asm
0x18002ba20  push    rbp
0x18002ba22  push    rbx
0x18002ba23  push    rsi
0x18002ba24  push    rdi
0x18002ba25  push    r13
0x18002ba27  push    r14
0x18002ba29  push    r15
0x18002ba2b  lea     rbp, [rsp-27h]
0x18002ba30  sub     rsp, 90h
0x18002ba37  mov     rax, cs:__security_cookie
0x18002ba3e  xor     rax, rsp
0x18002ba41  mov     [rbp+57h+var_38], rax
0x18002ba45  mov     ebx, r8d
0x18002ba48  mov     rsi, rdx
0x18002ba4b  mov     r13, rcx
0x18002ba4e  lea     rdx, [rcx+68h]
0x18002ba52  mov     rcx, [rdx+10h]
0x18002ba56  mov     rax, 7FFFFFFFFFFFFFFEh
0x18002ba60  sub     rax, rcx
0x18002ba63  cmp     rax, 0Dh
0x18002ba67  jb      loc_18002BCD1
0x18002ba6d  cmp     qword ptr [rdx+18h], 7
0x18002ba72  jbe     short loc_18002BA77
0x18002ba74  mov     rdx, [rdx]
0x18002ba77  mov     [rsp+0C0h+var_90], rcx
0x18002ba7c  mov     [rsp+0C0h+var_98], rdx
0x18002ba81  mov     [rsp+0C0h+var_A0], 0Dh
0x18002ba8a  lea     r9, aReplaceInto; "REPLACE INTO "
0x18002ba91  lea     rcx, [rbp+57h+var_58]
0x18002ba95  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002ba9a  nop
0x18002ba9b  lea     r8, aNameValueValue; " (Name, Value) VALUES (?, ?);"
0x18002baa2  lea     rdx, [rbp+57h+var_58]
0x18002baa6  lea     rcx, [rbp+57h+var_78]
0x18002baaa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002baaf  nop
0x18002bab0  lea     rcx, [rbp+57h+var_58]; void *
0x18002bab4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bab9  nop
0x18002baba  mov     [rbp+57h+var_80], 0
0x18002bac2  lea     rdx, [rbp+57h+var_78]
0x18002bac6  cmp     [rbp+57h+var_60], 7
0x18002bacb  cmova   rdx, [rbp+57h+var_78]
0x18002bad0  mov     [rsp+0C0h+var_98], 0
0x18002bad9  lea     rax, [rbp+57h+var_80]
0x18002badd  mov     [rsp+0C0h+var_A0], rax
0x18002bae2  mov     r9d, 80h
0x18002bae8  or      r8d, 0FFFFFFFFh
0x18002baec  mov     rcx, [r13+8]
0x18002baf0  call    sqlite3Prepare16
0x18002baf5  mov     edi, eax
0x18002baf7  mov     r14, [rbp+57h+var_80]
0x18002bafb  test    eax, eax
0x18002bafd  jz      short loc_18002BB45
0x18002baff  test    eax, eax
0x18002bb01  jg      short loc_18002BB07
0x18002bb03  mov     ebx, eax
0x18002bb05  jmp     short loc_18002BB10
0x18002bb07  movzx   ebx, di
0x18002bb0a  or      ebx, 80070000h
0x18002bb10  mov     rcx, [r13+8]
0x18002bb14  call    sqlite3_errmsg
0x18002bb19  mov     [rsp+0C0h+var_98], rax
0x18002bb1e  mov     dword ptr [rsp+0C0h+var_A0], edi
0x18002bb22  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18002bb29  mov     r8d, 47Ch
0x18002bb2f  mov     ecx, 1
0x18002bb34  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002bb3b  call    AslLogCallPrintf
0x18002bb40  jmp     loc_18002BC9A
0x18002bb45  test    r14, r14
0x18002bb48  jz      loc_18002BC72
0x18002bb4e  mov     byte ptr [rsp+0C0h+var_98], 2
0x18002bb53  mov     [rsp+0C0h+var_A0], 0
0x18002bb5c  mov     r15, 0FFFFFFFFFFFFFFFEh
0x18002bb63  mov     r9, r15
0x18002bb66  mov     r8, rsi
0x18002bb69  lea     edi, [r15+3]
0x18002bb6d  mov     edx, edi
0x18002bb6f  mov     rcx, r14
0x18002bb72  call    bindText
0x18002bb77  mov     esi, eax
0x18002bb79  test    eax, eax
0x18002bb7b  jz      short loc_18002BBB1
0x18002bb7d  test    eax, eax
0x18002bb7f  jg      short loc_18002BB85
0x18002bb81  mov     ebx, eax
0x18002bb83  jmp     short loc_18002BB8E
0x18002bb85  movzx   ebx, si
0x18002bb88  or      ebx, 80070000h
0x18002bb8e  mov     rcx, [r13+8]
0x18002bb92  call    sqlite3_errmsg
0x18002bb97  mov     r8d, 48Ah
0x18002bb9d  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18002bba4  mov     [rsp+0C0h+var_98], rax
0x18002bba9  mov     dword ptr [rsp+0C0h+var_A0], esi
0x18002bbad  mov     ecx, edi
0x18002bbaf  jmp     short loc_18002BB34
0x18002bbb1  mov     edx, ebx
0x18002bbb3  lea     rcx, [rbp+57h+var_58]
0x18002bbb7  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18002bbbc  nop
0x18002bbbd  cmp     qword ptr [rax+18h], 7
0x18002bbc2  jbe     short loc_18002BBC7
0x18002bbc4  mov     rax, [rax]
0x18002bbc7  mov     byte ptr [rsp+0C0h+var_98], 2
0x18002bbcc  mov     [rsp+0C0h+var_A0], 0FFFFFFFFFFFFFFFFh
0x18002bbd5  mov     r9, r15
0x18002bbd8  mov     r8, rax
0x18002bbdb  mov     edx, 2
0x18002bbe0  mov     rcx, r14
0x18002bbe3  call    bindText
0x18002bbe8  mov     esi, eax
0x18002bbea  lea     rcx, [rbp+57h+var_58]; void *
0x18002bbee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bbf3  test    esi, esi
0x18002bbf5  jz      short loc_18002BC17
0x18002bbf7  jg      short loc_18002BBFD
0x18002bbf9  mov     ebx, esi
0x18002bbfb  jmp     short loc_18002BC06
0x18002bbfd  movzx   ebx, si
0x18002bc00  or      ebx, 80070000h
0x18002bc06  mov     rcx, [r13+8]
0x18002bc0a  call    sqlite3_errmsg
0x18002bc0f  mov     r8d, 492h
0x18002bc15  jmp     short loc_18002BB9D
0x18002bc17  xor     ebx, ebx
0x18002bc19  xor     r15d, r15d
0x18002bc1c  mov     rcx, r14
0x18002bc1f  call    sqlite3_step
0x18002bc24  mov     esi, eax
0x18002bc26  lea     ecx, [rax-5]
0x18002bc29  cmp     ecx, edi
0x18002bc2b  ja      short loc_18002BC41
0x18002bc2d  mov     ecx, 5; dwMilliseconds
0x18002bc32  call    cs:__imp_Sleep
0x18002bc38  add     r15d, edi
0x18002bc3b  cmp     r15d, 64h ; 'd'
0x18002bc3f  jl      short loc_18002BC1C
0x18002bc41  cmp     esi, 65h ; 'e'
0x18002bc44  jz      short loc_18002BC9A
0x18002bc46  test    esi, esi
0x18002bc48  jg      short loc_18002BC4E
0x18002bc4a  mov     ebx, esi
0x18002bc4c  jmp     short loc_18002BC57
0x18002bc4e  movzx   ebx, si
0x18002bc51  or      ebx, 80070000h
0x18002bc57  mov     rcx, [r13+8]
0x18002bc5b  call    sqlite3_errmsg
0x18002bc60  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18002bc67  mov     r8d, 499h
0x18002bc6d  jmp     loc_18002BBA4
0x18002bc72  mov     ebx, 80004005h
0x18002bc77  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18002bc7b  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18002bc82  mov     r8d, 482h
0x18002bc88  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002bc8f  mov     ecx, 1
0x18002bc94  call    AslLogCallPrintf
0x18002bc99  nop
0x18002bc9a  test    r14, r14
0x18002bc9d  jz      short loc_18002BCA8
0x18002bc9f  mov     rcx, r14
0x18002bca2  call    sqlite3_finalize
0x18002bca7  nop
0x18002bca8  lea     rcx, [rbp+57h+var_78]; void *
0x18002bcac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bcb1  mov     eax, ebx
0x18002bcb3  mov     rcx, [rbp+57h+var_38]
0x18002bcb7  xor     rcx, rsp; StackCookie
0x18002bcba  call    __security_check_cookie
0x18002bcbf  add     rsp, 90h
0x18002bcc6  pop     r15
0x18002bcc8  pop     r14
0x18002bcca  pop     r13
0x18002bccc  pop     rdi
0x18002bccd  pop     rsi
0x18002bcce  pop     rbx
0x18002bccf  pop     rbp
0x18002bcd0  retn
0x18002bcd1  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
