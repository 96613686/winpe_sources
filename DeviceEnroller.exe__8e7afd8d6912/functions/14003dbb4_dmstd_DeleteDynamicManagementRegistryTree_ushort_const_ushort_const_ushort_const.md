# dmstd::DeleteDynamicManagementRegistryTree(ushort const *,ushort const *,ushort const *)

- ea: `0x14003dbb4`
- end: `0x14003e270`
- name: `?DeleteDynamicManagementRegistryTree@dmstd@@YAJPEBG00@Z`
- size: `1724`
- prototype: `__int64 __fastcall(dmstd *this, unsigned __int16 *, LPCWSTR lpSubKey, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400406d0`
- `0x140040b10`
- `0x140044360`

## callees

- `0x1400042f0`
- `0x1400095b4`
- `0x14001e784`
- `0x14001ed14`
- `0x14003d044`
- `0x14003d0d0`
- `0x14003d2f4`
- `0x14003d944`
- `0x14003dbb4`
- `0x14003eac4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e128`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003e13b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003e13b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003e08d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003e167`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003e08d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003e167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e0b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e0fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e133`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e186`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e223`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e0b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e0fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e133`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e186`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e223`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14003e0dc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14003e0dc`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14003e1cc`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14003e1cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall dmstd::DeleteDynamicManagementRegistryTree(
        dmstd *this,
        unsigned __int16 *a2,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a4)
{
  __int64 v7; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned __int64 v14; // r8
  __m128i *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  __m128i *v18; // rdx
  __m128i *v19; // rdx
  const WCHAR *v20; // rdx
  LSTATUS v21; // eax
  signed int v22; // ebx
  LSTATUS v23; // eax
  HKEY v24; // rsi
  DWORD LastError; // ebx
  LSTATUS v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rax
  LSTATUS v29; // eax
  unsigned int v30; // ebx
  int phkResult; // [rsp+20h] [rbp-148h]
  HKEY hKey; // [rsp+30h] [rbp-138h] BYREF
  __int128 v33; // [rsp+38h] [rbp-130h] BYREF
  __int64 v34; // [rsp+48h] [rbp-120h]
  __int128 v35; // [rsp+50h] [rbp-118h] BYREF
  __m128i si128; // [rsp+60h] [rbp-108h]
  LPCWSTR lpSubKeya[2]; // [rsp+70h] [rbp-F8h] BYREF
  __int128 v38; // [rsp+80h] [rbp-E8h]
  __int128 v39; // [rsp+90h] [rbp-D8h] BYREF
  __int128 v40; // [rsp+A0h] [rbp-C8h]
  __int128 v41; // [rsp+B0h] [rbp-B8h] BYREF
  __int128 v42; // [rsp+C0h] [rbp-A8h]
  _OWORD v43[2]; // [rsp+D0h] [rbp-98h] BYREF
  _OWORD Src[2]; // [rsp+F0h] [rbp-78h] BYREF
  _OWORD v45[2]; // [rsp+110h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  if ( !this )
  {
    v7 = 124;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\helpers.cpp",
      (const char *)0x80070057LL,
      phkResult);
    return 2147942487LL;
  }
  if ( !lpSubKey )
  {
    v7 = 125;
    goto LABEL_3;
  }
  v33 = 0;
  v34 = 0;
  memset(Src, 0, sizeof(Src));
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( qword_14007E6B8[v10] );
  std::wstring::_Construct<1,unsigned short const *>((char **)Src, qword_14007E6B8, v10);
  v11 = std::wstring::append(Src, (void *)L"\\");
  v41 = 0;
  v42 = 0;
  v41 = *(_OWORD *)v11;
  v42 = *(_OWORD *)(v11 + 16);
  *(_QWORD *)(v11 + 16) = 0;
  *(_QWORD *)(v11 + 24) = 7;
  *(_WORD *)v11 = 0;
  v12 = std::wstring::append(&v41, this);
  v39 = 0;
  v40 = 0;
  v39 = *(_OWORD *)v12;
  v40 = *(_OWORD *)(v12 + 16);
  *(_QWORD *)(v12 + 16) = 0;
  *(_QWORD *)(v12 + 24) = 7;
  *(_WORD *)v12 = 0;
  v13 = std::wstring::append(&v39, (void *)L"\\");
  *(_OWORD *)lpSubKeya = 0;
  v38 = 0;
  *(_OWORD *)lpSubKeya = *(_OWORD *)v13;
  v38 = *(_OWORD *)(v13 + 16);
  *(_QWORD *)(v13 + 16) = 0;
  *(_QWORD *)(v13 + 24) = 7;
  *(_WORD *)v13 = 0;
  std::wstring::~wstring((char **)&v39);
  std::wstring::~wstring((char **)&v41);
  std::wstring::~wstring((char **)Src);
  v35 = 0;
  si128 = 0;
  v14 = -1;
  do
    ++v14;
  while ( *((_WORD *)this + v14) );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v35, this, v14);
  v15 = (__m128i *)*((_QWORD *)&v33 + 1);
  if ( *((_QWORD *)&v33 + 1) == v34 )
  {
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v33, *((_QWORD *)&v33 + 1), &v35);
  }
  else
  {
    **((_OWORD **)&v33 + 1) = v35;
    v15[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v35) = 0;
    *((_QWORD *)&v33 + 1) += 32LL;
  }
  std::wstring::~wstring((char **)&v35);
  if ( a2 )
  {
    memset(v45, 0, sizeof(v45));
    std::wstring::_Construct<1,unsigned short const *>((char **)v45, L"User", 4u);
    v16 = std::wstring::append(v45, (void *)L"\\");
    v35 = 0;
    si128 = 0;
    v35 = *(_OWORD *)v16;
    si128 = *(__m128i *)(v16 + 16);
    *(_QWORD *)(v16 + 16) = 0;
    *(_QWORD *)(v16 + 24) = 7;
    *(_WORD *)v16 = 0;
    v17 = std::wstring::append(&v35, a2);
    v43[0] = *(_OWORD *)v17;
    v43[1] = *(_OWORD *)(v17 + 16);
    *(_QWORD *)(v17 + 16) = 0;
    *(_QWORD *)(v17 + 24) = 7;
    *(_WORD *)v17 = 0;
    std::wstring::append(lpSubKeya);
    std::wstring::~wstring((char **)v43);
    std::wstring::~wstring((char **)&v35);
    std::wstring::~wstring((char **)v45);
    v35 = 0;
    si128 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v35, L"User", 4u);
    v18 = (__m128i *)*((_QWORD *)&v33 + 1);
    if ( *((_QWORD *)&v33 + 1) == v34 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v33, *((_QWORD *)&v33 + 1), &v35);
    }
    else
    {
      **((_OWORD **)&v33 + 1) = v35;
      v18[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v35) = 0;
      *((_QWORD *)&v33 + 1) += 32LL;
    }
    std::wstring::~wstring((char **)&v35);
    v35 = 0;
    si128 = 0;
    do
      ++v9;
    while ( a2[v9] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v35, a2, v9);
    v19 = (__m128i *)*((_QWORD *)&v33 + 1);
    if ( *((_QWORD *)&v33 + 1) == v34 )
      goto LABEL_23;
LABEL_22:
    **((_OWORD **)&v33 + 1) = v35;
    v19[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v35) = 0;
    *((_QWORD *)&v33 + 1) += 32LL;
    goto LABEL_24;
  }
  std::wstring::append(lpSubKeya, (void *)L"Device");
  v35 = 0;
  si128 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v35, L"Device", 6u);
  v19 = (__m128i *)*((_QWORD *)&v33 + 1);
  if ( *((_QWORD *)&v33 + 1) != v34 )
    goto LABEL_22;
LABEL_23:
  std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v33, v19, &v35);
LABEL_24:
  std::wstring::~wstring((char **)&v35);
  hKey = 0;
  v20 = (const WCHAR *)lpSubKeya;
  if ( *((_QWORD *)&v38 + 1) > 7u )
    v20 = lpSubKeya[0];
  v21 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v20, 0, 0x10009u, &hKey);
  v22 = v21;
  if ( v21 > 0 )
    v22 = (unsigned __int16)v21 | 0x80070000;
  if ( v22 < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
LABEL_45:
    std::wstring::~wstring((char **)lpSubKeya);
    std::vector<std::wstring>::_Tidy(&v33);
    return (unsigned int)v22;
  }
  v23 = RegDeleteTreeW(hKey, lpSubKey);
  v22 = v23;
  if ( v23 > 0 )
    v22 = (unsigned __int16)v23 | 0x80070000;
  if ( v22 < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_45;
  }
  v24 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v24);
    SetLastError(LastError);
  }
  hKey = 0;
  v26 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, qword_14007E6B8, 0, 0x20019u, &hKey);
  v22 = v26;
  if ( v26 > 0 )
    v22 = (unsigned __int16)v26 | 0x80070000;
  if ( v22 < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_45;
  }
  do
  {
    v28 = lambda_0efc253941f2ee789cd73d41de8d0770_::operator()(v27, v43, &v33);
    if ( *(_QWORD *)(v28 + 24) > 7u )
      v28 = *(_QWORD *)v28;
    v29 = RegDeleteKeyW(hKey, (LPCWSTR)v28);
    v30 = v29;
    if ( v29 > 0 )
      v30 = (unsigned __int16)v29 | 0x80070000;
    std::wstring::~wstring((char **)v43);
    std::wstring::~wstring((char **)(*((_QWORD *)&v33 + 1) - 32LL));
    *((_QWORD *)&v33 + 1) -= 32LL;
  }
  while ( (_QWORD)v33 != *((_QWORD *)&v33 + 1) && (!v30 || v30 == -2147024894) );
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring((char **)lpSubKeya);
  std::vector<std::wstring>::_Tidy(&v33);
  return 0;
}

```

## disassembly

```asm
0x14003dbb4  mov     [rsp+arg_18], rbx
0x14003dbb9  push    rsi
0x14003dbba  push    rdi
0x14003dbbb  push    r13
0x14003dbbd  push    r14
0x14003dbbf  push    r15
0x14003dbc1  sub     rsp, 140h
0x14003dbc8  mov     rax, cs:__security_cookie
0x14003dbcf  xor     rax, rsp
0x14003dbd2  mov     [rsp+168h+var_38], rax
0x14003dbda  mov     r14, r8
0x14003dbdd  mov     rsi, rdx
0x14003dbe0  mov     rdi, rcx
0x14003dbe3  xor     r15d, r15d
0x14003dbe6  test    rcx, rcx
0x14003dbe9  jnz     short loc_14003DC11
0x14003dbeb  lea     edx, [rcx+7Ch]; void *
0x14003dbee  mov     ebx, 80070057h
0x14003dbf3  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14003dbfa  mov     r9d, ebx; char *
0x14003dbfd  mov     rcx, [rsp+168h]; this
0x14003dc05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003dc0a  mov     eax, ebx
0x14003dc0c  jmp     loc_14003E247
0x14003dc11  test    r14, r14
0x14003dc14  jnz     short loc_14003DC1C
0x14003dc16  lea     edx, [r14+7Dh]
0x14003dc1a  jmp     short loc_14003DBEE
0x14003dc1c  xorps   xmm0, xmm0
0x14003dc1f  movdqu  [rsp+168h+var_130], xmm0
0x14003dc25  mov     [rsp+168h+var_120], r15
0x14003dc2a  mov     rdx, cs:qword_14007E6B8
0x14003dc31  movups  [rsp+168h+Src], xmm0
0x14003dc39  xorps   xmm1, xmm1
0x14003dc3c  movdqu  [rsp+168h+var_68], xmm1
0x14003dc45  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003dc49  mov     r8, rbx
0x14003dc4c  inc     r8
0x14003dc4f  cmp     [rdx+r8*2], r15w
0x14003dc54  jnz     short loc_14003DC4C
0x14003dc56  lea     rcx, [rsp+168h+Src]
0x14003dc5e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003dc63  nop
0x14003dc64  lea     rdx, asc_140061150; "\\"
0x14003dc6b  lea     rcx, [rsp+168h+Src]; Src
0x14003dc73  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003dc78  xorps   xmm0, xmm0
0x14003dc7b  movups  [rsp+168h+var_B8], xmm0
0x14003dc83  xorps   xmm1, xmm1
0x14003dc86  movdqu  [rsp+168h+var_A8], xmm1
0x14003dc8f  movups  xmm0, xmmword ptr [rax]
0x14003dc92  movups  [rsp+168h+var_B8], xmm0
0x14003dc9a  movups  xmm1, xmmword ptr [rax+10h]
0x14003dc9e  movups  [rsp+168h+var_A8], xmm1
0x14003dca6  mov     [rax+10h], r15
0x14003dcaa  mov     r13d, 7
0x14003dcb0  mov     [rax+18h], r13
0x14003dcb4  mov     [rax], r15w
0x14003dcb8  mov     rdx, rdi; void *
0x14003dcbb  lea     rcx, [rsp+168h+var_B8]; Src
0x14003dcc3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003dcc8  xorps   xmm0, xmm0
0x14003dccb  movups  [rsp+168h+var_D8], xmm0
0x14003dcd3  xorps   xmm1, xmm1
0x14003dcd6  movdqu  [rsp+168h+var_C8], xmm1
0x14003dcdf  movups  xmm0, xmmword ptr [rax]
0x14003dce2  movups  [rsp+168h+var_D8], xmm0
0x14003dcea  movups  xmm1, xmmword ptr [rax+10h]
0x14003dcee  movups  [rsp+168h+var_C8], xmm1
0x14003dcf6  mov     [rax+10h], r15
0x14003dcfa  mov     [rax+18h], r13
0x14003dcfe  mov     [rax], r15w
0x14003dd02  lea     rdx, asc_140061150; "\\"
0x14003dd09  lea     rcx, [rsp+168h+var_D8]; Src
0x14003dd11  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003dd16  xorps   xmm0, xmm0
0x14003dd19  movups  xmmword ptr [rsp+168h+lpSubKey], xmm0
0x14003dd1e  xorps   xmm1, xmm1
0x14003dd21  movdqu  [rsp+168h+var_E8], xmm1
0x14003dd2a  movups  xmm0, xmmword ptr [rax]
0x14003dd2d  movups  xmmword ptr [rsp+168h+lpSubKey], xmm0
0x14003dd32  movups  xmm1, xmmword ptr [rax+10h]
0x14003dd36  movups  [rsp+168h+var_E8], xmm1
0x14003dd3e  mov     [rax+10h], r15
0x14003dd42  mov     [rax+18h], r13
0x14003dd46  mov     [rax], r15w
0x14003dd4a  lea     rcx, [rsp+168h+var_D8]
0x14003dd52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003dd57  nop
0x14003dd58  lea     rcx, [rsp+168h+var_B8]
0x14003dd60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003dd65  nop
0x14003dd66  lea     rcx, [rsp+168h+Src]
0x14003dd6e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003dd73  xorps   xmm0, xmm0
0x14003dd76  movups  [rsp+168h+var_118], xmm0
0x14003dd7b  xorps   xmm1, xmm1
0x14003dd7e  movdqu  [rsp+168h+var_108], xmm1
0x14003dd84  mov     r8, rbx
0x14003dd87  inc     r8
0x14003dd8a  cmp     [rdi+r8*2], r15w
0x14003dd8f  jnz     short loc_14003DD87
0x14003dd91  mov     rdx, rdi
0x14003dd94  lea     rcx, [rsp+168h+var_118]
0x14003dd99  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003dd9e  nop
0x14003dd9f  mov     rdx, qword ptr [rsp+168h+var_130+8]
0x14003dda4  cmp     rdx, [rsp+168h+var_120]
0x14003dda9  jz      short loc_14003DDD8
0x14003ddab  movups  xmm0, [rsp+168h+var_118]
0x14003ddb0  movups  xmmword ptr [rdx], xmm0
0x14003ddb3  movups  xmm1, [rsp+168h+var_108]
0x14003ddb8  movups  xmmword ptr [rdx+10h], xmm1
0x14003ddbc  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14003ddc4  movdqu  [rsp+168h+var_108], xmm0
0x14003ddca  mov     word ptr [rsp+168h+var_118], r15w
0x14003ddd0  add     qword ptr [rsp+168h+var_130+8], 20h ; ' '
0x14003ddd6  jmp     short loc_14003DDE8
0x14003ddd8  lea     r8, [rsp+168h+var_118]
0x14003dddd  lea     rcx, [rsp+168h+var_130]
0x14003dde2  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x14003dde7  nop
0x14003dde8  lea     rcx, [rsp+168h+var_118]
0x14003dded  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003ddf2  test    rsi, rsi
0x14003ddf5  jz      loc_14003DFCD
0x14003ddfb  xorps   xmm0, xmm0
0x14003ddfe  movups  [rsp+168h+var_58], xmm0
0x14003de06  xorps   xmm1, xmm1
0x14003de09  movdqu  [rsp+168h+var_48], xmm1
0x14003de12  mov     edi, 4
0x14003de17  mov     r8d, edi
0x14003de1a  lea     rdx, aUser; "User"
0x14003de21  lea     rcx, [rsp+168h+var_58]
0x14003de29  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003de2e  nop
0x14003de2f  lea     rdx, asc_140061150; "\\"
0x14003de36  lea     rcx, [rsp+168h+var_58]; Src
0x14003de3e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003de43  xorps   xmm0, xmm0
0x14003de46  movups  [rsp+168h+var_118], xmm0
0x14003de4b  xorps   xmm1, xmm1
0x14003de4e  movdqu  [rsp+168h+var_108], xmm1
0x14003de54  movups  xmm0, xmmword ptr [rax]
0x14003de57  movups  [rsp+168h+var_118], xmm0
0x14003de5c  movups  xmm1, xmmword ptr [rax+10h]
0x14003de60  movups  [rsp+168h+var_108], xmm1
0x14003de65  mov     [rax+10h], r15
0x14003de69  mov     [rax+18h], r13
0x14003de6d  mov     [rax], r15w
0x14003de71  mov     rdx, rsi; void *
0x14003de74  lea     rcx, [rsp+168h+var_118]; Src
0x14003de79  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003de7e  movups  xmm0, xmmword ptr [rax]
0x14003de81  movups  [rsp+168h+var_98], xmm0
0x14003de89  movups  xmm1, xmmword ptr [rax+10h]
0x14003de8d  movups  [rsp+168h+var_88], xmm1
0x14003de95  mov     [rax+10h], r15
0x14003de99  mov     [rax+18h], r13
0x14003de9d  mov     [rax], r15w
0x14003dea1  lea     rdx, [rsp+168h+var_98]
0x14003dea9  lea     rcx, [rsp+168h+lpSubKey]; Src
0x14003deae  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x14003deb3  nop
0x14003deb4  lea     rcx, [rsp+168h+var_98]
0x14003debc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003dec1  nop
0x14003dec2  lea     rcx, [rsp+168h+var_118]
0x14003dec7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003decc  nop
0x14003decd  lea     rcx, [rsp+168h+var_58]
0x14003ded5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003deda  xorps   xmm0, xmm0
0x14003dedd  movups  [rsp+168h+var_118], xmm0
0x14003dee2  xorps   xmm1, xmm1
0x14003dee5  movdqu  [rsp+168h+var_108], xmm1
0x14003deeb  mov     r8d, edi
0x14003deee  lea     rdx, aUser; "User"
0x14003def5  lea     rcx, [rsp+168h+var_118]
0x14003defa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003deff  nop
0x14003df00  mov     rdx, qword ptr [rsp+168h+var_130+8]
0x14003df05  cmp     rdx, [rsp+168h+var_120]
0x14003df0a  jz      short loc_14003DF39
0x14003df0c  movups  xmm0, [rsp+168h+var_118]
0x14003df11  movups  xmmword ptr [rdx], xmm0
0x14003df14  movups  xmm1, [rsp+168h+var_108]
0x14003df19  movups  xmmword ptr [rdx+10h], xmm1
0x14003df1d  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14003df25  movdqu  [rsp+168h+var_108], xmm0
0x14003df2b  mov     word ptr [rsp+168h+var_118], r15w
0x14003df31  add     qword ptr [rsp+168h+var_130+8], 20h ; ' '
0x14003df37  jmp     short loc_14003DF49
0x14003df39  lea     r8, [rsp+168h+var_118]
0x14003df3e  lea     rcx, [rsp+168h+var_130]
0x14003df43  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x14003df48  nop
0x14003df49  lea     rcx, [rsp+168h+var_118]
0x14003df4e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003df53  xorps   xmm0, xmm0
0x14003df56  movups  [rsp+168h+var_118], xmm0
0x14003df5b  xorps   xmm1, xmm1
0x14003df5e  movdqu  [rsp+168h+var_108], xmm1
0x14003df64  inc     rbx
0x14003df67  cmp     [rsi+rbx*2], r15w
0x14003df6c  jnz     short loc_14003DF64
0x14003df6e  mov     r8, rbx
0x14003df71  mov     rdx, rsi
0x14003df74  lea     rcx, [rsp+168h+var_118]
0x14003df79  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003df7e  nop
0x14003df7f  mov     rdx, qword ptr [rsp+168h+var_130+8]
0x14003df84  cmp     rdx, [rsp+168h+var_120]
0x14003df89  jz      short loc_14003DFB8
0x14003df8b  movups  xmm0, [rsp+168h+var_118]
0x14003df90  movups  xmmword ptr [rdx], xmm0
0x14003df93  movups  xmm1, [rsp+168h+var_108]
0x14003df98  movups  xmmword ptr [rdx+10h], xmm1
0x14003df9c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14003dfa4  movdqu  [rsp+168h+var_108], xmm0
0x14003dfaa  mov     word ptr [rsp+168h+var_118], r15w
0x14003dfb0  add     qword ptr [rsp+168h+var_130+8], 20h ; ' '
0x14003dfb6  jmp     short loc_14003DFC8
0x14003dfb8  lea     r8, [rsp+168h+var_118]
0x14003dfbd  lea     rcx, [rsp+168h+var_130]
0x14003dfc2  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x14003dfc7  nop
0x14003dfc8  jmp     loc_14003E050
0x14003dfcd  lea     rdx, aDevice; "Device"
0x14003dfd4  lea     rcx, [rsp+168h+lpSubKey]; Src
0x14003dfd9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003dfde  xorps   xmm0, xmm0
0x14003dfe1  movups  [rsp+168h+var_118], xmm0
0x14003dfe6  xorps   xmm1, xmm1
0x14003dfe9  movdqu  [rsp+168h+var_108], xmm1
0x14003dfef  mov     r8d, 6
0x14003dff5  lea     rdx, aDevice; "Device"
0x14003dffc  lea     rcx, [rsp+168h+var_118]
0x14003e001  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003e006  nop
0x14003e007  mov     rdx, qword ptr [rsp+168h+var_130+8]
0x14003e00c  cmp     rdx, [rsp+168h+var_120]
0x14003e011  jz      short loc_14003E040
0x14003e013  movups  xmm0, [rsp+168h+var_118]
0x14003e018  movups  xmmword ptr [rdx], xmm0
0x14003e01b  movups  xmm1, [rsp+168h+var_108]
0x14003e020  movups  xmmword ptr [rdx+10h], xmm1
0x14003e024  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14003e02c  movdqu  [rsp+168h+var_108], xmm0
0x14003e032  mov     word ptr [rsp+168h+var_118], r15w
0x14003e038  add     qword ptr [rsp+168h+var_130+8], 20h ; ' '
0x14003e03e  jmp     short loc_14003E050
0x14003e040  lea     r8, [rsp+168h+var_118]
0x14003e045  lea     rcx, [rsp+168h+var_130]
0x14003e04a  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x14003e04f  nop
0x14003e050  lea     rcx, [rsp+168h+var_118]
0x14003e055  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e05a  nop
0x14003e05b  mov     [rsp+168h+hKey], r15
0x14003e060  lea     rdx, [rsp+168h+lpSubKey]
0x14003e065  cmp     qword ptr [rsp+168h+var_E8+8], r13
0x14003e06d  cmova   rdx, [rsp+168h+lpSubKey]; lpSubKey
0x14003e073  lea     rax, [rsp+168h+hKey]
0x14003e078  mov     qword ptr [rsp+168h+phkResult], rax; phkResult
0x14003e07d  mov     r9d, 10009h; samDesired
0x14003e083  xor     r8d, r8d; ulOptions
0x14003e086  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003e08d  call    cs:__imp_RegOpenKeyExW
0x14003e093  mov     ebx, eax
0x14003e095  mov     edi, 80070000h
0x14003e09a  test    eax, eax
0x14003e09c  jle     short loc_14003E0A3
0x14003e09e  movzx   ebx, ax
0x14003e0a1  or      ebx, edi
0x14003e0a3  test    ebx, ebx
0x14003e0a5  jns     short loc_14003E0D4
0x14003e0a7  mov     rcx, [rsp+168h+hKey]; hKey
0x14003e0ac  test    rcx, rcx
0x14003e0af  jz      short loc_14003E0B8
0x14003e0b1  call    cs:__imp_RegCloseKey
0x14003e0b7  nop
0x14003e0b8  lea     rcx, [rsp+168h+lpSubKey]
0x14003e0bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e0c2  nop
0x14003e0c3  lea     rcx, [rsp+168h+var_130]
0x14003e0c8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x14003e0cd  mov     eax, ebx
0x14003e0cf  jmp     loc_14003E247
0x14003e0d4  mov     rdx, r14; lpSubKey
0x14003e0d7  mov     rcx, [rsp+168h+hKey]; hKey
0x14003e0dc  call    cs:__imp_RegDeleteTreeW
0x14003e0e2  mov     ebx, eax
0x14003e0e4  test    eax, eax
0x14003e0e6  jle     short loc_14003E0ED
0x14003e0e8  movzx   ebx, ax
0x14003e0eb  or      ebx, edi
0x14003e0ed  test    ebx, ebx
0x14003e0ef  jns     short loc_14003E11E
0x14003e0f1  mov     rcx, [rsp+168h+hKey]; hKey
  ... truncated ...
```
