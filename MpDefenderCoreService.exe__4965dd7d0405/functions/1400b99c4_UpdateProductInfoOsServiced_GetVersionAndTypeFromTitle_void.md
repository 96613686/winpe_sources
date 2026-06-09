# UpdateProductInfoOsServiced::GetVersionAndTypeFromTitle(void)

- ea: `0x1400b99c4`
- end: `0x1400b9d7d`
- name: `?GetVersionAndTypeFromTitle@UpdateProductInfoOsServiced@@QEAAXXZ`
- size: `953`
- prototype: `void __fastcall(UpdateProductInfoOsServiced *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400bab40`

## callees

- `0x140020e70`
- `0x14003a5c0`
- `0x14007d1e0`
- `0x14007e088`
- `0x140084850`
- `0x140084a18`
- `0x140084a8c`
- `0x140084b28`
- `0x140085d38`
- `0x14008d1fc`
- `0x1400b850c`
- `0x1400b99c4`
- `0x1400baf48`
- `0x1400bb460`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1400b9bc8`
- `KERNEL32!WideCharToMultiByte` at `0x1400b9c23`
- `KERNEL32!WideCharToMultiByte` at `0x1400b9bc8`
- `KERNEL32!WideCharToMultiByte` at `0x1400b9c23`
- `KERNEL32!GetLastError` at `0x1400b9cb8`
- `KERNEL32!GetLastError` at `0x1400b9cb8`

## string_xrefs

- `0x1400b9a6f`: `Security Intelligence Update`
- `0x1400b9a83`: `Definition Update`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UpdateProductInfoOsServiced::GetVersionAndTypeFromTitle(__m128i *this)
{
  __m128i *v2; // rdi
  size_t v3; // rsi
  __int64 *v4; // r9
  __int64 v5; // rax
  unsigned __int64 v6; // r12
  unsigned __int64 v7; // rdx
  __int64 *v8; // rax
  char *v9; // rbx
  __int64 trivial_2; // rax
  __int64 v11; // rax
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r8
  const WCHAR *v15; // r8
  int v16; // eax
  int cbMultiByte; // ebx
  const WCHAR *v18; // r8
  LPCWCH *v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 *v22; // [rsp+40h] [rbp-39h]
  __m128i v23; // [rsp+48h] [rbp-31h] BYREF
  __m128i si128; // [rsp+58h] [rbp-21h]
  LPSTR lpMultiByteStr[2]; // [rsp+68h] [rbp-11h] BYREF
  __int64 v26; // [rsp+78h] [rbp-1h]
  LPCWCH lpWideCharStr[2]; // [rsp+80h] [rbp+7h] BYREF
  __int128 v28; // [rsp+90h] [rbp+17h]

  v2 = this + 3;
  if ( !this[4].m128i_i64[0] )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, &WPP_78dcd942f53334a8c0f25b7dfbe81ade_Traceguids);
    return;
  }
  v3 = -1;
  if ( std::wstring::find(&this[3], L"antimalware platform") == -1
    && std::wstring::find(v2, L"Antimalware platform") == -1 )
  {
    if ( std::wstring::find(v2, L"Security Intelligence Update") == -1
      && std::wstring::find(v2, L"Definition Update") == -1 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v4 = (__int64 *)v2;
        if ( v2[1].m128i_i64[1] > 7uLL )
          v4 = (__int64 *)v2->m128i_i64[0];
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, &WPP_78dcd942f53334a8c0f25b7dfbe81ade_Traceguids, v4);
      }
      this->m128i_i32[3] = 0;
    }
    else
    {
      this->m128i_i32[3] = 1;
    }
  }
  else
  {
    this->m128i_i32[3] = 2;
  }
  v5 = std::wstring::find(v2, L"(Version ");
  if ( v5 == -1 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      return;
    if ( v2[1].m128i_i64[1] > 7uLL )
      v2 = (__m128i *)v2->m128i_i64[0];
    v21 = 18;
LABEL_56:
    WPP_SF_S(*(_QWORD *)(v20 + 16), v21, &WPP_78dcd942f53334a8c0f25b7dfbe81ade_Traceguids, v2);
    return;
  }
  v6 = v5 + 9;
  v7 = v2[1].m128i_u64[0];
  v8 = (__int64 *)v2;
  v22 = (__int64 *)v2;
  if ( v2[1].m128i_i64[1] > 7uLL )
  {
    v8 = (__int64 *)v2->m128i_i64[0];
    v22 = (__int64 *)v2->m128i_i64[0];
  }
  if ( v6 >= v7
    || (_mm_lfence(),
        v9 = (char *)v8 + 2 * v7,
        trivial_2 = _std_find_trivial_2((char *)v8 + 2 * v6, v9, 41),
        (char *)trivial_2 == v9)
    || (v11 = (trivial_2 - (__int64)v22) >> 1, v11 == -1) )
  {
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      return;
    if ( v2[1].m128i_i64[1] > 7uLL )
      v2 = (__m128i *)v2->m128i_i64[0];
    v21 = 17;
    goto LABEL_56;
  }
  *(_OWORD *)lpWideCharStr = 0;
  v28 = 0;
  v12 = v2[1].m128i_u64[0];
  if ( v12 < v6 )
    std::_String_val<std::_Simple_types<char>>::_Xran();
  _mm_lfence();
  v13 = v11 - v6;
  v14 = v12 - v6;
  if ( v14 >= v13 )
    v14 = v13;
  if ( v2[1].m128i_i64[1] > 7uLL )
    v2 = (__m128i *)v2->m128i_i64[0];
  std::wstring::_Construct<1,wchar_t const *>(lpWideCharStr, (char *)v2 + 2 * v6, v14);
  v15 = (const WCHAR *)lpWideCharStr;
  if ( *((_QWORD *)&v28 + 1) > 7u )
    v15 = lpWideCharStr[0];
  v16 = WideCharToMultiByte(0xFDE9u, 0, v15, -1, 0, 0, 0, 0);
  cbMultiByte = v16;
  if ( v16 > 0 )
  {
    _mm_lfence();
    *(_OWORD *)lpMultiByteStr = 0;
    v26 = 0;
    std::vector<char>::vector<char>(lpMultiByteStr, v16);
    v18 = (const WCHAR *)lpWideCharStr;
    if ( *((_QWORD *)&v28 + 1) > 7u )
      v18 = lpWideCharStr[0];
    if ( WideCharToMultiByte(0xFDE9u, 0, v18, -1, lpMultiByteStr[0], cbMultiByte, 0, 0) )
    {
      v23 = 0;
      si128 = 0;
      do
        ++v3;
      while ( lpMultiByteStr[0][v3] );
      std::string::_Construct<1,char const *>(&v23, lpMultiByteStr[0], v3);
      if ( &this[1] != &v23 )
      {
        _mm_lfence();
        std::string::_Tidy_deallocate(&this[1]);
        this[1] = v23;
        this[2] = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v23.m128i_i8[0] = 0;
      }
      std::string::_Tidy_deallocate(&v23);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v19 = lpWideCharStr;
      if ( *((_QWORD *)&v28 + 1) > 7u )
        v19 = (LPCWCH *)lpWideCharStr[0];
      GetLastError();
      WPP_SF_dS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (__int64)v19);
    }
    std::vector<unsigned char>::_Tidy(lpMultiByteStr);
  }
  std::wstring::_Tidy_deallocate(lpWideCharStr);
}

```

## disassembly

```asm
0x1400b99c4  mov     [rsp-8+arg_8], rbx
0x1400b99c9  mov     [rsp-8+arg_10], rsi
0x1400b99ce  push    rbp
0x1400b99cf  push    rdi
0x1400b99d0  push    r12
0x1400b99d2  push    r13
0x1400b99d4  push    r14
0x1400b99d6  lea     rbp, [rsp-37h]
0x1400b99db  sub     rsp, 0B0h
0x1400b99e2  mov     rax, cs:__security_cookie
0x1400b99e9  xor     rax, rsp
0x1400b99ec  mov     [rbp+57h+var_30], rax
0x1400b99f0  mov     r13, rcx
0x1400b99f3  xor     ebx, ebx
0x1400b99f5  lea     rdi, [rcx+30h]
0x1400b99f9  cmp     [rdi+10h], rbx
0x1400b99fd  jnz     short loc_1400B9A38
0x1400b99ff  lea     r14, WPP_GLOBAL_Control
0x1400b9a06  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b9a0d  cmp     rcx, r14
0x1400b9a10  jz      loc_1400B9D4F
0x1400b9a16  test    byte ptr [rcx+1Ch], 1
0x1400b9a1a  jz      loc_1400B9D4F
0x1400b9a20  lea     edx, [rbx+0Eh]
0x1400b9a23  lea     r8, WPP_78dcd942f53334a8c0f25b7dfbe81ade_Traceguids
0x1400b9a2a  mov     rcx, [rcx+10h]
0x1400b9a2e  call    WPP_SF_
0x1400b9a33  jmp     loc_1400B9D4F
0x1400b9a38  lea     rdx, aAntimalwarePla; "antimalware platform"
0x1400b9a3f  mov     rcx, rdi
0x1400b9a42  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find(wchar_t const * const,unsigned __int64)
0x1400b9a47  lea     r14, WPP_GLOBAL_Control
0x1400b9a4e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400b9a52  cmp     rax, rsi
0x1400b9a55  jnz     loc_1400B9ADB
0x1400b9a5b  lea     rdx, aAntimalwarePla_0; "Antimalware platform"
0x1400b9a62  mov     rcx, rdi
0x1400b9a65  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find(wchar_t const * const,unsigned __int64)
0x1400b9a6a  cmp     rax, rsi
0x1400b9a6d  jnz     short loc_1400B9ADB
0x1400b9a6f  lea     rdx, aSecurityIntell; "Security Intelligence Update"
0x1400b9a76  mov     rcx, rdi
0x1400b9a79  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find(wchar_t const * const,unsigned __int64)
0x1400b9a7e  cmp     rax, rsi
0x1400b9a81  jnz     short loc_1400B9AD1
0x1400b9a83  lea     rdx, aDefinitionUpda; "Definition Update"
0x1400b9a8a  mov     rcx, rdi
0x1400b9a8d  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find(wchar_t const * const,unsigned __int64)
0x1400b9a92  cmp     rax, rsi
0x1400b9a95  jnz     short loc_1400B9AD1
0x1400b9a97  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b9a9e  cmp     rcx, r14
0x1400b9aa1  jz      short loc_1400B9ACB
0x1400b9aa3  test    byte ptr [rcx+1Ch], 1
0x1400b9aa7  jz      short loc_1400B9ACB
0x1400b9aa9  mov     r9, rdi
0x1400b9aac  cmp     qword ptr [rdi+18h], 7
0x1400b9ab1  jbe     short loc_1400B9AB6
0x1400b9ab3  mov     r9, [rdi]
0x1400b9ab6  mov     edx, 0Fh
0x1400b9abb  lea     r8, WPP_78dcd942f53334a8c0f25b7dfbe81ade_Traceguids
0x1400b9ac2  mov     rcx, [rcx+10h]
0x1400b9ac6  call    WPP_SF_S
0x1400b9acb  mov     [r13+0Ch], ebx
0x1400b9acf  jmp     short loc_1400B9AE3
0x1400b9ad1  mov     dword ptr [r13+0Ch], 1
0x1400b9ad9  jmp     short loc_1400B9AE3
0x1400b9adb  mov     dword ptr [r13+0Ch], 2
0x1400b9ae3  lea     rdx, aVersion_1; "(Version "
0x1400b9aea  mov     rcx, rdi
0x1400b9aed  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find(wchar_t const * const,unsigned __int64)
0x1400b9af2  cmp     rax, rsi
0x1400b9af5  jz      loc_1400B9D1B
0x1400b9afb  lea     r12, [rax+9]
0x1400b9aff  mov     rdx, [rdi+10h]
0x1400b9b03  mov     rax, rdi
0x1400b9b06  mov     [rbp+57h+var_90], rax
0x1400b9b0a  cmp     qword ptr [rdi+18h], 7
0x1400b9b0f  jbe     short loc_1400B9B18
0x1400b9b11  mov     rax, [rdi]
0x1400b9b14  mov     [rbp+57h+var_90], rax
0x1400b9b18  cmp     r12, rdx
0x1400b9b1b  jnb     loc_1400B9CF8
0x1400b9b21  lea     rcx, [rax+r12*2]
0x1400b9b25  lfence
0x1400b9b28  lea     rbx, [rax+rdx*2]
0x1400b9b2c  mov     r8d, 29h ; ')'
0x1400b9b32  mov     rdx, rbx
0x1400b9b35  call    __std_find_trivial_2
0x1400b9b3a  cmp     rax, rbx
0x1400b9b3d  jz      loc_1400B9CF8
0x1400b9b43  sub     rax, [rbp+57h+var_90]
0x1400b9b47  sar     rax, 1
0x1400b9b4a  cmp     rax, rsi
0x1400b9b4d  jz      loc_1400B9CF8
0x1400b9b53  xorps   xmm0, xmm0
0x1400b9b56  movups  xmmword ptr [rbp+57h+lpWideCharStr], xmm0
0x1400b9b5a  xorps   xmm1, xmm1
0x1400b9b5d  movdqu  [rbp+57h+var_40], xmm1
0x1400b9b62  mov     r8, [rdi+10h]
0x1400b9b66  cmp     r8, r12
0x1400b9b69  jb      loc_1400B9D77
0x1400b9b6f  lfence
0x1400b9b72  sub     rax, r12
0x1400b9b75  sub     r8, r12
0x1400b9b78  cmp     r8, rax
0x1400b9b7b  cmovnb  r8, rax
0x1400b9b7f  cmp     qword ptr [rdi+18h], 7
0x1400b9b84  jbe     short loc_1400B9B89
0x1400b9b86  mov     rdi, [rdi]
0x1400b9b89  lea     rdx, [rdi+r12*2]
0x1400b9b8d  lea     rcx, [rbp+57h+lpWideCharStr]
0x1400b9b91  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400b9b96  nop
0x1400b9b97  lea     r8, [rbp+57h+lpWideCharStr]
0x1400b9b9b  cmp     qword ptr [rbp+57h+var_40+8], 7
0x1400b9ba0  cmova   r8, [rbp+57h+lpWideCharStr]; lpWideCharStr
0x1400b9ba5  xor     edi, edi
0x1400b9ba7  mov     [rsp+0D0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1400b9bac  mov     [rsp+0D0h+lpDefaultChar], rdi; lpDefaultChar
0x1400b9bb1  mov     [rsp+0D0h+cbMultiByte], edi; cbMultiByte
0x1400b9bb5  mov     [rsp+0D0h+lpMultiByteStr], rdi; lpMultiByteStr
0x1400b9bba  mov     r9d, esi; cchWideChar
0x1400b9bbd  xor     edx, edx; dwFlags
0x1400b9bbf  mov     r12d, 0FDE9h
0x1400b9bc5  mov     ecx, r12d; CodePage
0x1400b9bc8  call    cs:__imp_WideCharToMultiByte
0x1400b9bce  movsxd  rbx, eax
0x1400b9bd1  test    eax, eax
0x1400b9bd3  jle     loc_1400B9CED
0x1400b9bd9  lfence
0x1400b9bdc  xorps   xmm0, xmm0
0x1400b9bdf  xor     eax, eax
0x1400b9be1  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1400b9be5  mov     [rbp+57h+var_58], rax
0x1400b9be9  mov     rdx, rbx
0x1400b9bec  lea     rcx, [rbp+57h+var_68]
0x1400b9bf0  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x1400b9bf5  nop
0x1400b9bf6  mov     rax, [rbp+57h+var_68]
0x1400b9bfa  lea     r8, [rbp+57h+lpWideCharStr]
0x1400b9bfe  cmp     qword ptr [rbp+57h+var_40+8], 7
0x1400b9c03  cmova   r8, [rbp+57h+lpWideCharStr]; lpWideCharStr
0x1400b9c08  mov     [rsp+0D0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1400b9c0d  mov     [rsp+0D0h+lpDefaultChar], rdi; lpDefaultChar
0x1400b9c12  mov     [rsp+0D0h+cbMultiByte], ebx; cbMultiByte
0x1400b9c16  mov     [rsp+0D0h+lpMultiByteStr], rax; lpMultiByteStr
0x1400b9c1b  mov     r9d, esi; cchWideChar
0x1400b9c1e  xor     edx, edx; dwFlags
0x1400b9c20  mov     ecx, r12d; CodePage
0x1400b9c23  call    cs:__imp_WideCharToMultiByte
0x1400b9c29  test    eax, eax
0x1400b9c2b  jz      short loc_1400B9C98
0x1400b9c2d  xorps   xmm0, xmm0
0x1400b9c30  movups  [rbp+57h+var_88], xmm0
0x1400b9c34  xorps   xmm1, xmm1
0x1400b9c37  movdqu  [rbp+57h+var_78], xmm1
0x1400b9c3c  mov     rdx, [rbp+57h+var_68]
0x1400b9c40  inc     rsi
0x1400b9c43  cmp     [rdx+rsi], dil
0x1400b9c47  jnz     short loc_1400B9C40
0x1400b9c49  mov     r8, rsi
0x1400b9c4c  lea     rcx, [rbp+57h+var_88]
0x1400b9c50  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400b9c55  lea     rbx, [r13+10h]
0x1400b9c59  lea     rax, [rbp+57h+var_88]
0x1400b9c5d  cmp     rbx, rax
0x1400b9c60  jz      short loc_1400B9C8D
0x1400b9c62  lfence
0x1400b9c65  mov     rcx, rbx
0x1400b9c68  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400b9c6d  movups  xmm0, [rbp+57h+var_88]
0x1400b9c71  movups  xmmword ptr [rbx], xmm0
0x1400b9c74  movups  xmm1, [rbp+57h+var_78]
0x1400b9c78  movups  xmmword ptr [rbx+10h], xmm1
0x1400b9c7c  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1400b9c84  movdqu  [rbp+57h+var_78], xmm0
0x1400b9c89  mov     byte ptr [rbp+57h+var_88], dil
0x1400b9c8d  lea     rcx, [rbp+57h+var_88]
0x1400b9c91  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400b9c96  jmp     short loc_1400B9CE3
0x1400b9c98  mov     rax, cs:WPP_GLOBAL_Control
0x1400b9c9f  cmp     rax, r14
0x1400b9ca2  jz      short loc_1400B9CE3
0x1400b9ca4  test    byte ptr [rax+1Ch], 1
0x1400b9ca8  jz      short loc_1400B9CE3
0x1400b9caa  lea     rbx, [rbp+57h+lpWideCharStr]
0x1400b9cae  cmp     qword ptr [rbp+57h+var_40+8], 7
0x1400b9cb3  cmova   rbx, [rbp+57h+lpWideCharStr]
0x1400b9cb8  call    cs:__imp_GetLastError
0x1400b9cbe  mov     edx, 10h
0x1400b9cc3  mov     [rsp+0D0h+lpMultiByteStr], rbx; __int64
0x1400b9cc8  mov     r9d, eax
0x1400b9ccb  lea     r8, WPP_78dcd942f53334a8c0f25b7dfbe81ade_Traceguids
0x1400b9cd2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b9cd9  mov     rcx, [rcx+10h]; LoggerHandle
0x1400b9cdd  call    WPP_SF_dS
0x1400b9ce2  nop
0x1400b9ce3  lea     rcx, [rbp+57h+var_68]
0x1400b9ce7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400b9cec  nop
0x1400b9ced  lea     rcx, [rbp+57h+lpWideCharStr]
0x1400b9cf1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400b9cf6  jmp     short loc_1400B9D4F
0x1400b9cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b9cff  cmp     rcx, r14
0x1400b9d02  jz      short loc_1400B9D4F
0x1400b9d04  test    byte ptr [rcx+1Ch], 2
0x1400b9d08  jz      short loc_1400B9D4F
0x1400b9d0a  cmp     qword ptr [rdi+18h], 7
0x1400b9d0f  jbe     short loc_1400B9D14
0x1400b9d11  mov     rdi, [rdi]
0x1400b9d14  mov     edx, 11h
0x1400b9d19  jmp     short loc_1400B9D3C
0x1400b9d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b9d22  cmp     rcx, r14
0x1400b9d25  jz      short loc_1400B9D4F
0x1400b9d27  test    byte ptr [rcx+1Ch], 2
0x1400b9d2b  jz      short loc_1400B9D4F
0x1400b9d2d  cmp     qword ptr [rdi+18h], 7
0x1400b9d32  jbe     short loc_1400B9D37
0x1400b9d34  mov     rdi, [rdi]
0x1400b9d37  mov     edx, 12h
0x1400b9d3c  mov     r9, rdi
0x1400b9d3f  lea     r8, WPP_78dcd942f53334a8c0f25b7dfbe81ade_Traceguids
0x1400b9d46  mov     rcx, [rcx+10h]
0x1400b9d4a  call    WPP_SF_S
0x1400b9d4f  mov     rcx, [rbp+57h+var_30]
0x1400b9d53  xor     rcx, rsp; StackCookie
0x1400b9d56  call    __security_check_cookie
0x1400b9d5b  lea     r11, [rsp+0D0h+var_20]
0x1400b9d63  mov     rbx, [r11+38h]
0x1400b9d67  mov     rsi, [r11+40h]
0x1400b9d6b  mov     rsp, r11
0x1400b9d6e  pop     r14
0x1400b9d70  pop     r13
0x1400b9d72  pop     r12
0x1400b9d74  pop     rdi
0x1400b9d75  pop     rbp
0x1400b9d76  retn
0x1400b9d77  call    ?_Xran@?$_String_val@U?$_Simple_types@D@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<char>>::_Xran(void)
```
