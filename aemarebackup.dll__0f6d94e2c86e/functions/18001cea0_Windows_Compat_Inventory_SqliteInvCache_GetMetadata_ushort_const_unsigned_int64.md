# Windows::Compat::Inventory::SqliteInvCache::GetMetadata(ushort const *,unsigned __int64 &)

- ea: `0x18001cea0`
- end: `0x18001d1c5`
- name: `?GetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEBAJPEBGAEA_K@Z`
- size: `805`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180004ea0`
- `0x18000fb60`
- `0x18001209c`
- `0x1800134b8`
- `0x18001cea0`
- `0x1800276cc`
- `0x180027d3c`
- `0x18004c020`
- `0x180059d64`
- `0x1800a494c`
- `0x1800c2b60`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x18001d119`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x18001d119`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d0ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d0ef`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18001d12c`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18001d12c`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001d13f`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001d13f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d070`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d070`

## string_xrefs

- `0x18001cfe2`: `Windows::Compat::Inventory::SqliteInvCache::GetMetadata`
- `0x18001d16d`: `Windows::Compat::Inventory::SqliteInvCache::GetMetadata`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::GetMetadata(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        unsigned __int64 *a3)
{
  int v4; // ebx
  _QWORD *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int128 *v9; // rdx
  unsigned __int64 v10; // r12
  int v11; // eax
  int v12; // edi
  __int64 v13; // r14
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // esi
  __int64 v17; // rax
  const char *v18; // r9
  __int64 v19; // r8
  int i; // ebx
  _WORD *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  _DWORD *v25; // rax
  _DWORD *v26; // rdi
  const wchar_t *v27; // rbx
  unsigned __int64 v28; // rax
  __int64 v30; // [rsp+20h] [rbp-79h]
  __int64 v31; // [rsp+20h] [rbp-79h]
  __int64 v32; // [rsp+28h] [rbp-71h]
  __int64 v33; // [rsp+28h] [rbp-71h]
  __int64 v34; // [rsp+40h] [rbp-59h] BYREF
  wchar_t *EndPtr; // [rsp+48h] [rbp-51h] BYREF
  __int128 v36; // [rsp+50h] [rbp-49h] BYREF
  __int128 v37; // [rsp+60h] [rbp-39h]
  wchar_t *String[2]; // [rsp+70h] [rbp-29h] BYREF
  __int128 v39; // [rsp+80h] [rbp-19h]
  char *Src[4]; // [rsp+90h] [rbp-9h] BYREF

  v4 = (int)a2;
  v6 = (_QWORD *)((char *)this + 104);
  v7 = *((_QWORD *)this + 15);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v7) < 0x12 )
    std::_Xlen_string();
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  std::wstring::wstring(Src, v6, a3, L"SELECT Value FROM ", 18, v6, v7);
  v8 = std::wstring::append(Src, L" WHERE Name = ?;");
  v36 = 0;
  v37 = 0;
  v36 = *(_OWORD *)v8;
  v37 = *(_OWORD *)(v8 + 16);
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  *(_WORD *)v8 = 0;
  std::wstring::~wstring(Src);
  *a3 = 0;
  v34 = 0;
  v9 = &v36;
  if ( *((_QWORD *)&v37 + 1) > 7u )
    LODWORD(v9) = v36;
  v10 = -1;
  v11 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v9, -1, 128, (__int64)&v34, 0);
  v12 = v11;
  v13 = v34;
  if ( v11 )
  {
    if ( v11 > 0 )
      v14 = (unsigned __int16)v11 | 0x80070000;
    else
      v14 = v11;
    v33 = sqlite3_errmsg(*((_QWORD *)this + 1));
    LODWORD(v30) = v12;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::GetMetadata",
      1046,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v30,
      v33);
    goto LABEL_39;
  }
  if ( v34 )
  {
    LOBYTE(v32) = 2;
    v15 = bindText(v34, 1, v4, -2, 0, v32);
    v16 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v14 = (unsigned __int16)v15 | 0x80070000;
      else
        v14 = v15;
      v17 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v18 = "sqlite3_bind_text16 failed: [%d] %hs";
      v19 = 1060;
LABEL_18:
      LODWORD(v31) = v16;
      AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::GetMetadata", v19, v18, v31, v17);
      goto LABEL_39;
    }
    for ( i = 0; i < 100; ++i )
    {
      v16 = sqlite3_step(v13);
      if ( (unsigned int)(v16 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v16 == 101 )
    {
      v14 = -2147024894;
    }
    else
    {
      if ( v16 != 100 )
      {
        if ( v16 > 0 )
          v14 = (unsigned __int16)v16 | 0x80070000;
        else
          v14 = v16;
        v17 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v18 = "sqlite3_step failed: [%d] %hs";
        v19 = 1072;
        goto LABEL_18;
      }
      v21 = (_WORD *)sqlite3_column_text16(v13, 0);
      *(_OWORD *)String = 0;
      v39 = 0;
      do
        ++v10;
      while ( v21[v10] );
      std::wstring::_Construct<1,unsigned short const *>((char **)String, v21, v10);
      v25 = (_DWORD *)_o__errno(v23, v22, v24);
      v26 = v25;
      v27 = (const wchar_t *)String;
      if ( *((_QWORD *)&v39 + 1) > 7u )
        v27 = String[0];
      EndPtr = 0;
      *v25 = 0;
      v28 = wcstoull(v27, &EndPtr, 10);
      if ( v27 == EndPtr )
      {
        std::_Xinvalid_argument("invalid stoull argument");
        __debugbreak();
      }
      if ( *v26 == 34 )
      {
        std::_Xout_of_range("stoull argument out of range");
        __debugbreak();
      }
      v14 = 0;
      *a3 = v28;
      std::wstring::~wstring((char **)String);
    }
  }
  else
  {
    v14 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::GetMetadata",
      1052,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
  }
LABEL_39:
  if ( v13 )
    sqlite3_finalize(v13);
  std::wstring::~wstring((char **)&v36);
  return v14;
}

```

## disassembly

```asm
0x18001cea0  mov     [rsp-8+arg_18], rbx
0x18001cea5  push    rbp
0x18001cea6  push    rsi
0x18001cea7  push    rdi
0x18001cea8  push    r12
0x18001ceaa  push    r13
0x18001ceac  push    r14
0x18001ceae  push    r15
0x18001ceb0  lea     rbp, [rsp-27h]
0x18001ceb5  sub     rsp, 0C0h
0x18001cebc  mov     rax, cs:__security_cookie
0x18001cec3  xor     rax, rsp
0x18001cec6  mov     [rbp+57h+var_40], rax
0x18001ceca  mov     r13, r8
0x18001cecd  mov     rbx, rdx
0x18001ced0  mov     r15, rcx
0x18001ced3  xor     esi, esi
0x18001ced5  lea     rdx, [rcx+68h]
0x18001ced9  mov     rcx, [rdx+10h]
0x18001cedd  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001cee7  sub     rax, rcx
0x18001ceea  cmp     rax, 12h
0x18001ceee  jb      loc_18001D1BF
0x18001cef4  cmp     qword ptr [rdx+18h], 7
0x18001cef9  jbe     short loc_18001CEFE
0x18001cefb  mov     rdx, [rdx]
0x18001cefe  mov     [rsp+0F0h+var_C0], rcx
0x18001cf03  mov     [rsp+0F0h+var_C8], rdx
0x18001cf08  mov     [rsp+0F0h+var_D0], 12h
0x18001cf11  lea     r9, aSelectValueFro; "SELECT Value FROM "
0x18001cf18  lea     rcx, [rbp+57h+Src]
0x18001cf1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001cf21  nop
0x18001cf22  lea     rdx, aWhereName; " WHERE Name = ?;"
0x18001cf29  lea     rcx, [rbp+57h+Src]; Src
0x18001cf2d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001cf32  xorps   xmm0, xmm0
0x18001cf35  movups  [rbp+57h+var_A0], xmm0
0x18001cf39  xorps   xmm1, xmm1
0x18001cf3c  movdqu  [rbp+57h+var_90], xmm1
0x18001cf41  movups  xmm0, xmmword ptr [rax]
0x18001cf44  movups  [rbp+57h+var_A0], xmm0
0x18001cf48  movups  xmm1, xmmword ptr [rax+10h]
0x18001cf4c  movups  [rbp+57h+var_90], xmm1
0x18001cf50  mov     [rax+10h], rsi
0x18001cf54  mov     qword ptr [rax+18h], 7
0x18001cf5c  mov     [rax], si
0x18001cf5f  lea     rcx, [rbp+57h+Src]
0x18001cf63  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cf68  nop
0x18001cf69  mov     [r13+0], rsi
0x18001cf6d  mov     [rbp+57h+var_B0], rsi
0x18001cf71  lea     rdx, [rbp+57h+var_A0]
0x18001cf75  cmp     qword ptr [rbp+57h+var_90+8], 7
0x18001cf7a  cmova   rdx, qword ptr [rbp+57h+var_A0]
0x18001cf7f  mov     [rsp+0F0h+var_C8], rsi
0x18001cf84  lea     rax, [rbp+57h+var_B0]
0x18001cf88  mov     [rsp+0F0h+var_D0], rax
0x18001cf8d  mov     r9d, 80h
0x18001cf93  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001cf97  mov     r8d, r12d
0x18001cf9a  mov     rcx, [r15+8]
0x18001cf9e  call    sqlite3Prepare16
0x18001cfa3  mov     edi, eax
0x18001cfa5  mov     r14, [rbp+57h+var_B0]
0x18001cfa9  test    eax, eax
0x18001cfab  jz      short loc_18001CFF3
0x18001cfad  test    eax, eax
0x18001cfaf  jg      short loc_18001CFB5
0x18001cfb1  mov     ebx, eax
0x18001cfb3  jmp     short loc_18001CFBE
0x18001cfb5  movzx   ebx, di
0x18001cfb8  or      ebx, 80070000h
0x18001cfbe  mov     rcx, [r15+8]
0x18001cfc2  call    sqlite3_errmsg
0x18001cfc7  mov     [rsp+0F0h+var_C8], rax
0x18001cfcc  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18001cfd0  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18001cfd7  mov     r8d, 416h
0x18001cfdd  mov     ecx, 1
0x18001cfe2  lea     rdx, aWindowsCompatI_44; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001cfe9  call    AslLogCallPrintf
0x18001cfee  jmp     loc_18001D17F
0x18001cff3  test    r14, r14
0x18001cff6  jz      loc_18001D157
0x18001cffc  mov     byte ptr [rsp+0F0h+var_C8], 2
0x18001d001  mov     [rsp+0F0h+var_D0], rsi
0x18001d006  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18001d00d  mov     r8, rbx
0x18001d010  lea     edi, [r9+3]
0x18001d014  mov     edx, edi
0x18001d016  mov     rcx, r14
0x18001d019  call    bindText
0x18001d01e  mov     esi, eax
0x18001d020  test    eax, eax
0x18001d022  jz      short loc_18001D058
0x18001d024  test    eax, eax
0x18001d026  jg      short loc_18001D02C
0x18001d028  mov     ebx, eax
0x18001d02a  jmp     short loc_18001D035
0x18001d02c  movzx   ebx, si
0x18001d02f  or      ebx, 80070000h
0x18001d035  mov     rcx, [r15+8]
0x18001d039  call    sqlite3_errmsg
0x18001d03e  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18001d045  mov     r8d, 424h
0x18001d04b  mov     [rsp+0F0h+var_C8], rax
0x18001d050  mov     dword ptr [rsp+0F0h+var_D0], esi
0x18001d054  mov     ecx, edi
0x18001d056  jmp     short loc_18001CFE2
0x18001d058  xor     ebx, ebx
0x18001d05a  mov     rcx, r14
0x18001d05d  call    sqlite3_step
0x18001d062  mov     esi, eax
0x18001d064  lea     ecx, [rax-5]
0x18001d067  cmp     ecx, edi
0x18001d069  ja      short loc_18001D07D
0x18001d06b  mov     ecx, 5; dwMilliseconds
0x18001d070  call    cs:__imp_Sleep
0x18001d076  add     ebx, edi
0x18001d078  cmp     ebx, 64h ; 'd'
0x18001d07b  jl      short loc_18001D05A
0x18001d07d  cmp     esi, 65h ; 'e'
0x18001d080  jnz     short loc_18001D08C
0x18001d082  mov     ebx, 80070002h
0x18001d087  jmp     loc_18001D17F
0x18001d08c  cmp     esi, 64h ; 'd'
0x18001d08f  jz      short loc_18001D0BA
0x18001d091  test    esi, esi
0x18001d093  jg      short loc_18001D099
0x18001d095  mov     ebx, esi
0x18001d097  jmp     short loc_18001D0A2
0x18001d099  movzx   ebx, si
0x18001d09c  or      ebx, 80070000h
0x18001d0a2  mov     rcx, [r15+8]
0x18001d0a6  call    sqlite3_errmsg
0x18001d0ab  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18001d0b2  mov     r8d, 430h
0x18001d0b8  jmp     short loc_18001D04B
0x18001d0ba  xor     edx, edx
0x18001d0bc  mov     rcx, r14
0x18001d0bf  call    sqlite3_column_text16
0x18001d0c4  xorps   xmm0, xmm0
0x18001d0c7  movups  xmmword ptr [rbp+57h+String], xmm0
0x18001d0cb  xorps   xmm1, xmm1
0x18001d0ce  movdqu  [rbp+57h+var_70], xmm1
0x18001d0d3  xor     esi, esi
0x18001d0d5  inc     r12
0x18001d0d8  cmp     [rax+r12*2], si
0x18001d0dd  jnz     short loc_18001D0D5
0x18001d0df  mov     r8, r12
0x18001d0e2  mov     rdx, rax
0x18001d0e5  lea     rcx, [rbp+57h+String]
0x18001d0e9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d0ee  nop
0x18001d0ef  call    cs:__imp__o__errno
0x18001d0f5  mov     rdi, rax
0x18001d0f8  lea     rbx, [rbp+57h+String]
0x18001d0fc  cmp     qword ptr [rbp+57h+var_70+8], 7
0x18001d101  cmova   rbx, [rbp+57h+String]
0x18001d106  mov     [rbp+57h+EndPtr], rsi
0x18001d10a  mov     [rax], esi
0x18001d10c  mov     r8d, 0Ah; Radix
0x18001d112  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x18001d116  mov     rcx, rbx; String
0x18001d119  call    cs:__imp_wcstoull
0x18001d11f  cmp     rbx, [rbp+57h+EndPtr]
0x18001d123  jnz     short loc_18001D133
0x18001d125  lea     rcx, aInvalidStoullA; "invalid stoull argument"
0x18001d12c  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x18001d132  int     3; Trap to Debugger
0x18001d133  cmp     dword ptr [rdi], 22h ; '"'
0x18001d136  jnz     short loc_18001D146
0x18001d138  lea     rcx, aStoullArgument; "stoull argument out of range"
0x18001d13f  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18001d145  int     3; Trap to Debugger
0x18001d146  mov     ebx, esi
0x18001d148  mov     [r13+0], rax
0x18001d14c  lea     rcx, [rbp+57h+String]
0x18001d150  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d155  jmp     short loc_18001D17F
0x18001d157  mov     ebx, 80004005h
0x18001d15c  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18001d160  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18001d167  mov     r8d, 41Ch
0x18001d16d  lea     rdx, aWindowsCompatI_44; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001d174  mov     ecx, 1
0x18001d179  call    AslLogCallPrintf
0x18001d17e  nop
0x18001d17f  test    r14, r14
0x18001d182  jz      short loc_18001D18D
0x18001d184  mov     rcx, r14
0x18001d187  call    sqlite3_finalize
0x18001d18c  nop
0x18001d18d  lea     rcx, [rbp+57h+var_A0]
0x18001d191  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d196  mov     eax, ebx
0x18001d198  mov     rcx, [rbp+57h+var_40]
0x18001d19c  xor     rcx, rsp; StackCookie
0x18001d19f  call    __security_check_cookie
0x18001d1a4  mov     rbx, [rsp+0F0h+arg_18]
0x18001d1ac  add     rsp, 0C0h
0x18001d1b3  pop     r15
0x18001d1b5  pop     r14
0x18001d1b7  pop     r13
0x18001d1b9  pop     r12
0x18001d1bb  pop     rdi
0x18001d1bc  pop     rsi
0x18001d1bd  pop     rbp
0x18001d1be  retn
0x18001d1bf  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
