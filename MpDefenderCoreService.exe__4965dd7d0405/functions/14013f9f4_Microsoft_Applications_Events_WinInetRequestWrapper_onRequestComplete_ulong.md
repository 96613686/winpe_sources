# Microsoft::Applications::Events::WinInetRequestWrapper::onRequestComplete(ulong)

- ea: `0x14013f9f4`
- end: `0x14013feb4`
- name: `?onRequestComplete@WinInetRequestWrapper@Events@Applications@Microsoft@@QEAAXK@Z`
- size: `1216`
- prototype: `void __fastcall(Microsoft::Applications::Events::WinInetRequestWrapper *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14013feb4`
- `0x1401406a0`

## callees

- `0x14003a0f4`
- `0x14003a5c0`
- `0x14003c364`
- `0x14003c594`
- `0x14007e088`
- `0x140084a18`
- `0x1400854b4`
- `0x1400ea848`
- `0x1400ee5e0`
- `0x1400ff188`
- `0x14011b830`
- `0x14013401c`
- `0x14013f684`
- `0x14013f9f4`
- `0x140166250`
- `0x140166990`

## import_xrefs

- `WININET!InternetReadFile` at `0x14013fa84`
- `WININET!InternetReadFile` at `0x14013fa84`
- `WININET!InternetSetStatusCallbackW` at `0x14013fe3f`
- `WININET!InternetSetStatusCallbackW` at `0x14013fe3f`
- `WININET!HttpQueryInfoA` at `0x14013fb71`
- `WININET!HttpQueryInfoA` at `0x14013fbca`
- `WININET!HttpQueryInfoA` at `0x14013fc2e`
- `WININET!HttpQueryInfoA` at `0x14013fb71`
- `WININET!HttpQueryInfoA` at `0x14013fbca`
- `WININET!HttpQueryInfoA` at `0x14013fc2e`
- `KERNEL32!GetLastError` at `0x14013fa9e`
- `KERNEL32!GetLastError` at `0x14013fb84`
- `KERNEL32!GetLastError` at `0x14013fbd4`
- `KERNEL32!GetLastError` at `0x14013fa9e`
- `KERNEL32!GetLastError` at `0x14013fb84`
- `KERNEL32!GetLastError` at `0x14013fbd4`

## string_xrefs

- `0x14013fae3`: `InternetReadFile() failed: %d`
- `0x14013faba`: `InternetReadFile() failed: ERROR_IO_PENDING. Waiting for INTERNET_STATUS_REQUEST_COMPLETE to be called again`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::Applications::Events::WinInetRequestWrapper::onRequestComplete(
        Microsoft::Applications::Events::WinInetRequestWrapper *this,
        unsigned int a2)
{
  unsigned int v2; // edi
  char *v4; // r15
  DWORD *v5; // r14
  char *v6; // rbx
  __int64 i; // rdx
  BOOL File; // eax
  DWORD LastError; // eax
  void *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r15
  __int64 v13; // rbx
  LPVOID *v14; // r14
  DWORD v15; // eax
  const char *v16; // rdi
  DWORD v17; // eax
  __int64 v18; // rax
  char *v19; // rax
  char *v20; // r14
  const char *j; // rdi
  char *v22; // rax
  char *v23; // r14
  __int64 v24; // rcx
  unsigned int v25; // edi
  unsigned int v26; // edi
  unsigned int v27; // edi
  unsigned int v28; // edi
  bool v29; // zf
  unsigned int v30; // edi
  bool v31; // zf
  unsigned int v32; // edi
  unsigned int v33; // edi
  unsigned int v34; // edi
  unsigned int v35; // edi
  unsigned int v36; // edi
  unsigned int v37; // edi
  unsigned int v38; // edi
  unsigned int v39; // edi
  unsigned int v40; // edi
  unsigned int v41; // edi
  unsigned int v42; // edi
  unsigned int v43; // edi
  DWORD dwBufferLength; // [rsp+38h] [rbp-31h] BYREF
  int Buffer; // [rsp+3Ch] [rbp-2Dh] BYREF
  __int128 v46; // [rsp+40h] [rbp-29h] BYREF
  __int64 v47; // [rsp+50h] [rbp-19h]
  __int64 v48; // [rsp+58h] [rbp-11h]
  __int128 v49; // [rsp+60h] [rbp-9h] BYREF
  __int64 v50; // [rsp+70h] [rbp+7h]
  __int64 v51; // [rsp+78h] [rbp+Fh]

  v2 = a2;
  if ( !a2 )
  {
    v4 = (char *)this + 1104;
    v5 = (DWORD *)((char *)this + 1096);
    v6 = (char *)this + 72;
    for ( i = *((_QWORD *)this + 139); ; i = *((_QWORD *)this + 139) )
    {
      std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
        v4,
        i,
        v6,
        (char *)this + *v5 - (_QWORD)v6 + 72);
      if ( *((_BYTE *)this + 1128) )
      {
        if ( !*v5 )
          break;
      }
      File = InternetReadFile(*((HINTERNET *)this + 7), v6, 0x400u, v5);
      *((_BYTE *)this + 1128) = 1;
      if ( !File )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError == 997 )
        {
          if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
            Microsoft::Applications::Events::PlatformAbstraction::detail::log(
              4,
              "MATSDK",
              "InternetReadFile() failed: ERROR_IO_PENDING. Waiting for INTERNET_STATUS_REQUEST_COMPLETE to be called again");
          return;
        }
        if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 2 )
          Microsoft::Applications::Events::PlatformAbstraction::detail::log(
            2,
            "MATSDK",
            "InternetReadFile() failed: %d",
            LastError);
        break;
      }
    }
  }
  v10 = operator new(0x78u);
  memset(v10, 0, 0x78u);
  v11 = Microsoft::Applications::Events::SimpleHttpResponse::SimpleHttpResponse(v10, (char *)this + 8);
  v12 = v11;
  v13 = v11;
  if ( !v2 )
  {
    v14 = (LPVOID *)((char *)this + 1104);
    std::vector<unsigned char>::operator=(v11 + 96, (char *)this + 1104);
    *(_DWORD *)(v13 + 40) = 0;
    Buffer = 0;
    dwBufferLength = 4;
    if ( !HttpQueryInfoA(*((HINTERNET *)this + 7), 0x20000013u, &Buffer, &dwBufferLength, 0)
      && Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 2 )
    {
      v15 = GetLastError();
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        2,
        "MATSDK",
        "HttpQueryInfo(STATUS_CODE) failed: %d",
        v15);
    }
    *(_DWORD *)(v12 + 44) = Buffer;
    v16 = (char *)this + 72;
    dwBufferLength = 1023;
    if ( !HttpQueryInfoA(*((HINTERNET *)this + 7), 0x16u, (char *)this + 72, &dwBufferLength, 0) )
    {
      v17 = GetLastError();
      if ( v17 != 122 )
      {
        if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 2 )
          Microsoft::Applications::Events::PlatformAbstraction::detail::log(
            2,
            "MATSDK",
            "HttpQueryInfo(RAW_HEADERS) failed: %d",
            v17);
LABEL_20:
        v18 = 0;
        dwBufferLength = 0;
LABEL_25:
        v16[v18] = 0;
        if ( *v16 )
        {
          do
          {
            v19 = strchr(v16, 58);
            v20 = v19;
            if ( !v19 )
              break;
            v46 = 0;
            v47 = 0;
            v48 = 0;
            if ( v16 == v19 )
            {
              v47 = 0;
              v48 = 15;
              LOBYTE(v46) = 0;
            }
            else
            {
              std::string::_Construct<1,char const *>(&v46, v16, v19 - v16);
            }
            for ( j = v20 + 1; *j == 32; ++j )
              ;
            v22 = strstr(j, "\r\n");
            v23 = v22;
            if ( !v22 )
            {
              std::string::_Tidy_deallocate(&v46);
              break;
            }
            v49 = 0;
            v50 = 0;
            v51 = 0;
            if ( j == v22 )
            {
              v50 = 0;
              v51 = 15;
              LOBYTE(v49) = 0;
            }
            else
            {
              std::string::_Construct<1,char const *>(&v49, j, v22 - j);
            }
            Microsoft::Applications::Events::HttpHeaders::add(v12 + 48, &v46, &v49);
            v16 = v23 + 2;
            std::string::_Tidy_deallocate(&v49);
            std::string::_Tidy_deallocate(&v46);
          }
          while ( v23[2] );
        }
        v24 = *((_QWORD *)this + 5);
        if ( v24 )
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v24 + 16LL))(v24, 7, *((_QWORD *)this + 7));
        goto LABEL_74;
      }
      std::vector<unsigned char>::resize((char *)this + 1104, dwBufferLength + 1);
      v16 = (const char *)*v14;
      if ( !HttpQueryInfoA(*((HINTERNET *)this + 7), 0x16u, *v14, &dwBufferLength, 0) )
      {
        if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 2 )
          Microsoft::Applications::Events::PlatformAbstraction::detail::log(
            2,
            "MATSDK",
            "HttpQueryInfo(RAW_HEADERS) failed twice: %d",
            122);
        goto LABEL_20;
      }
    }
    v18 = dwBufferLength;
    goto LABEL_25;
  }
  if ( v2 > 0x2F0A )
  {
    if ( v2 > 0x2F78 )
    {
      v40 = v2 - 12156;
      if ( !v40 )
        goto LABEL_73;
      v41 = v40 - 4;
      if ( !v41 )
        goto LABEL_73;
      v42 = v41 - 9;
      if ( !v42 )
        goto LABEL_73;
      v43 = v42 - 1;
      if ( !v43 )
        goto LABEL_73;
      v31 = v43 == 5;
    }
    else
    {
      if ( v2 == 12152 )
        goto LABEL_73;
      v35 = v2 - 12043;
      if ( !v35 )
        goto LABEL_73;
      v36 = v35 - 1;
      if ( !v36 )
        goto LABEL_73;
      v37 = v36 - 1;
      if ( !v37 )
        goto LABEL_73;
      v38 = v37 - 7;
      if ( !v38 )
        goto LABEL_73;
      v39 = v38 - 3;
      if ( !v39 )
        goto LABEL_73;
      v31 = v39 == 96;
    }
LABEL_71:
    if ( !v31 )
    {
      *(_DWORD *)(v11 + 40) = 2;
      goto LABEL_74;
    }
LABEL_73:
    *(_DWORD *)(v11 + 40) = 3;
    goto LABEL_74;
  }
  if ( v2 == 12042 )
    goto LABEL_73;
  if ( v2 > 0x2EFE )
  {
    v32 = v2 - 12031;
    if ( !v32 )
      goto LABEL_73;
    v33 = v32 - 6;
    if ( !v33 )
      goto LABEL_73;
    v34 = v33 - 1;
    if ( !v34 )
      goto LABEL_73;
    v30 = v34 - 1;
    v29 = v30 == 0;
    goto LABEL_51;
  }
  if ( v2 == 12030 )
    goto LABEL_73;
  v25 = v2 - 12002;
  if ( !v25 )
    goto LABEL_73;
  v26 = v25 - 1;
  if ( !v26 )
    goto LABEL_73;
  v27 = v26 - 4;
  if ( !v27 )
    goto LABEL_73;
  v28 = v27 - 10;
  if ( v28 )
  {
    v30 = v28 - 11;
    v29 = v30 == 0;
LABEL_51:
    if ( v29 )
      goto LABEL_73;
    v31 = v30 == 1;
    goto LABEL_71;
  }
  *(_DWORD *)(v11 + 40) = 1;
LABEL_74:
  if ( !*((_BYTE *)this + 1129) )
  {
    InternetSetStatusCallbackW(*((HINTERNET *)this + 7), 0);
    *((_BYTE *)this + 1129) = 1;
    v13 = 0;
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5), v12);
    Microsoft::Applications::Events::HttpClient_WinInet::erase(*(_QWORD *)this, (char *)this + 8);
  }
  if ( v13 )
    (**(void (__fastcall ***)(__int64, __int64))v13)(v13, 1);
}

```

## disassembly

```asm
0x14013f9f4  mov     [rsp-8+arg_10], rbx
0x14013f9f9  push    rbp
0x14013f9fa  push    rsi
0x14013f9fb  push    rdi
0x14013f9fc  push    r12
0x14013f9fe  push    r13
0x14013fa00  push    r14
0x14013fa02  push    r15
0x14013fa04  lea     rbp, [rsp-27h]
0x14013fa09  sub     rsp, 90h
0x14013fa10  mov     rax, cs:__security_cookie
0x14013fa17  xor     rax, rsp
0x14013fa1a  mov     [rbp+57h+var_40], rax
0x14013fa1e  mov     edi, edx
0x14013fa20  mov     rsi, rcx
0x14013fa23  mov     r13d, 2
0x14013fa29  xor     r12d, r12d
0x14013fa2c  test    edx, edx
0x14013fa2e  jnz     loc_14013FAF9
0x14013fa34  lea     r15, [rcx+450h]
0x14013fa3b  lea     r14, [rcx+448h]
0x14013fa42  lea     rbx, [rcx+48h]
0x14013fa46  mov     rdx, [r15+8]
0x14013fa4a  mov     r9d, [r14]
0x14013fa4d  sub     r9, rbx
0x14013fa50  add     r9, 48h ; 'H'
0x14013fa54  add     r9, rsi
0x14013fa57  mov     r8, rbx
0x14013fa5a  mov     rcx, r15
0x14013fa5d  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x14013fa62  cmp     [rsi+468h], r12b
0x14013fa69  jz      short loc_14013FA74
0x14013fa6b  cmp     [r14], r12d
0x14013fa6e  jz      loc_14013FAF9
0x14013fa74  mov     r9, r14; lpdwNumberOfBytesRead
0x14013fa77  mov     r8d, 400h; dwNumberOfBytesToRead
0x14013fa7d  mov     rdx, rbx; lpBuffer
0x14013fa80  mov     rcx, [rsi+38h]; hFile
0x14013fa84  call    cs:__imp_InternetReadFile
0x14013fa8a  mov     byte ptr [rsi+468h], 1
0x14013fa91  test    eax, eax
0x14013fa93  jz      short loc_14013FA9E
0x14013fa95  mov     rdx, [rsi+458h]
0x14013fa9c  jmp     short loc_14013FA4A
0x14013fa9e  call    cs:__imp_GetLastError
0x14013faa4  mov     edi, eax
0x14013faa6  cmp     eax, 3E5h
0x14013faab  jnz     short loc_14013FAD7
0x14013faad  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 4; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14013fab4  jl      loc_14013FE8D
0x14013faba  lea     r8, aInternetreadfi_0; "InternetReadFile() failed: ERROR_IO_PEN"...
0x14013fac1  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x14013fac8  mov     ecx, 4
0x14013facd  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14013fad2  jmp     loc_14013FE8D
0x14013fad7  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, r13d; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14013fade  jl      short loc_14013FAF9
0x14013fae0  mov     r9d, eax
0x14013fae3  lea     r8, aInternetreadfi; "InternetReadFile() failed: %d"
0x14013faea  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x14013faf1  mov     ecx, r13d
0x14013faf4  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14013faf9  mov     r14d, 78h ; 'x'
0x14013faff  mov     ecx, r14d; Size
0x14013fb02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14013fb07  mov     rbx, rax
0x14013fb0a  mov     [rbp+57h+var_90], rax
0x14013fb0e  mov     r8d, r14d; Size
0x14013fb11  xor     edx, edx; Val
0x14013fb13  mov     rcx, rax; void *
0x14013fb16  call    memset
0x14013fb1b  lea     rdx, [rsi+8]
0x14013fb1f  mov     rcx, rbx
0x14013fb22  call    ??0SimpleHttpResponse@Events@Applications@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Applications::Events::SimpleHttpResponse::SimpleHttpResponse(std::string const &)
0x14013fb27  mov     r15, rax
0x14013fb2a  mov     rbx, rax
0x14013fb2d  mov     [rbp+57h+var_90], rax
0x14013fb31  test    edi, edi
0x14013fb33  jnz     loc_14013FD72
0x14013fb39  lea     r14, [rsi+450h]
0x14013fb40  lea     rcx, [rax+60h]
0x14013fb44  mov     rdx, r14
0x14013fb47  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x14013fb4c  mov     [rbx+28h], r12d
0x14013fb50  mov     [rbp+57h+Buffer], r12d
0x14013fb54  mov     [rbp+57h+dwBufferLength], 4
0x14013fb5b  mov     [rsp+0C0h+lpdwIndex], r12; lpdwIndex
0x14013fb60  lea     r9, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x14013fb64  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x14013fb68  mov     edx, 20000013h; dwInfoLevel
0x14013fb6d  mov     rcx, [rsi+38h]; hRequest
0x14013fb71  call    cs:__imp_HttpQueryInfoA
0x14013fb77  test    eax, eax
0x14013fb79  jnz     short loc_14013FBA3
0x14013fb7b  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, r13d; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14013fb82  jl      short loc_14013FBA3
0x14013fb84  call    cs:__imp_GetLastError
0x14013fb8a  mov     r9d, eax
0x14013fb8d  lea     r8, aHttpqueryinfoS; "HttpQueryInfo(STATUS_CODE) failed: %d"
0x14013fb94  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x14013fb9b  mov     ecx, r13d
0x14013fb9e  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14013fba3  mov     eax, [rbp+57h+Buffer]
0x14013fba6  mov     [r15+2Ch], eax
0x14013fbaa  lea     rdi, [rsi+48h]
0x14013fbae  mov     [rbp+57h+dwBufferLength], 3FFh
0x14013fbb5  mov     [rsp+0C0h+lpdwIndex], r12; lpdwIndex
0x14013fbba  lea     r9, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x14013fbbe  mov     r8, rdi; lpBuffer
0x14013fbc1  mov     edx, 16h; dwInfoLevel
0x14013fbc6  mov     rcx, [rsi+38h]; hRequest
0x14013fbca  call    cs:__imp_HttpQueryInfoA
0x14013fbd0  test    eax, eax
0x14013fbd2  jnz     short loc_14013FC4E
0x14013fbd4  call    cs:__imp_GetLastError
0x14013fbda  cmp     eax, 7Ah ; 'z'
0x14013fbdd  jz      short loc_14013FC09
0x14013fbdf  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, r13d; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14013fbe6  jl      short loc_14013FC01
0x14013fbe8  mov     r9d, eax
0x14013fbeb  lea     r8, aHttpqueryinfoR; "HttpQueryInfo(RAW_HEADERS) failed: %d"
0x14013fbf2  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x14013fbf9  mov     ecx, r13d
0x14013fbfc  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14013fc01  mov     eax, r12d
0x14013fc04  mov     [rbp+57h+dwBufferLength], eax
0x14013fc07  jmp     short loc_14013FC51
0x14013fc09  mov     edx, [rbp+57h+dwBufferLength]
0x14013fc0c  inc     edx
0x14013fc0e  mov     rcx, r14
0x14013fc11  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x14013fc16  mov     rdi, [r14]
0x14013fc19  mov     [rsp+0C0h+lpdwIndex], r12; lpdwIndex
0x14013fc1e  lea     r9, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x14013fc22  mov     r8, rdi; lpBuffer
0x14013fc25  mov     edx, 16h; dwInfoLevel
0x14013fc2a  mov     rcx, [rsi+38h]; hRequest
0x14013fc2e  call    cs:__imp_HttpQueryInfoA
0x14013fc34  test    eax, eax
0x14013fc36  jnz     short loc_14013FC4E
0x14013fc38  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, r13d; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14013fc3f  jl      short loc_14013FC01
0x14013fc41  lea     r9d, [rax+7Ah]
0x14013fc45  lea     r8, aHttpqueryinfoR_0; "HttpQueryInfo(RAW_HEADERS) failed twice"...
0x14013fc4c  jmp     short loc_14013FBF2
0x14013fc4e  mov     eax, [rbp+57h+dwBufferLength]
0x14013fc51  mov     [rax+rdi], r12b
0x14013fc55  cmp     [rdi], r12b
0x14013fc58  jz      loc_14013FD48
0x14013fc5e  mov     r13d, 0Fh
0x14013fc64  mov     edx, 3Ah ; ':'; Val
0x14013fc69  mov     rcx, rdi; Str
0x14013fc6c  call    strchr
0x14013fc71  mov     r14, rax
0x14013fc74  test    rax, rax
0x14013fc77  jz      loc_14013FD48
0x14013fc7d  xorps   xmm0, xmm0
0x14013fc80  movups  [rbp+57h+var_80], xmm0
0x14013fc84  mov     [rbp+57h+var_70], r12
0x14013fc88  mov     [rbp+57h+var_68], r12
0x14013fc8c  cmp     rdi, rax
0x14013fc8f  jnz     short loc_14013FC9F
0x14013fc91  mov     [rbp+57h+var_70], r12
0x14013fc95  mov     [rbp+57h+var_68], r13
0x14013fc99  mov     byte ptr [rbp+57h+var_80], r12b
0x14013fc9d  jmp     short loc_14013FCB2
0x14013fc9f  mov     r8, r14
0x14013fca2  sub     r8, rdi
0x14013fca5  mov     rdx, rdi
0x14013fca8  lea     rcx, [rbp+57h+var_80]
0x14013fcac  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14013fcb1  nop
0x14013fcb2  lea     rdi, [r14+1]
0x14013fcb6  jmp     short loc_14013FCBB
0x14013fcb8  inc     rdi
0x14013fcbb  cmp     byte ptr [rdi], 20h ; ' '
0x14013fcbe  jz      short loc_14013FCB8
0x14013fcc0  lea     rdx, asc_1401A2CE4; "\r\n"
0x14013fcc7  mov     rcx, rdi; Str
0x14013fcca  call    strstr
0x14013fccf  mov     r14, rax
0x14013fcd2  test    rax, rax
0x14013fcd5  jz      short loc_14013FD3F
0x14013fcd7  xorps   xmm0, xmm0
0x14013fcda  movups  [rbp+57h+var_60], xmm0
0x14013fcde  mov     [rbp+57h+var_50], r12
0x14013fce2  mov     [rbp+57h+var_48], r12
0x14013fce6  cmp     rdi, rax
0x14013fce9  jnz     short loc_14013FCF9
0x14013fceb  mov     [rbp+57h+var_50], r12
0x14013fcef  mov     [rbp+57h+var_48], r13
0x14013fcf3  mov     byte ptr [rbp+57h+var_60], r12b
0x14013fcf7  jmp     short loc_14013FD0C
0x14013fcf9  mov     r8, r14
0x14013fcfc  sub     r8, rdi
0x14013fcff  mov     rdx, rdi
0x14013fd02  lea     rcx, [rbp+57h+var_60]
0x14013fd06  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14013fd0b  nop
0x14013fd0c  lea     rcx, [r15+30h]
0x14013fd10  lea     r8, [rbp+57h+var_60]
0x14013fd14  lea     rdx, [rbp+57h+var_80]
0x14013fd18  call    ?add@HttpHeaders@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Applications::Events::HttpHeaders::add(std::string const &,std::string const &)
0x14013fd1d  lea     rdi, [r14+2]
0x14013fd21  lea     rcx, [rbp+57h+var_60]
0x14013fd25  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14013fd2a  nop
0x14013fd2b  lea     rcx, [rbp+57h+var_80]
0x14013fd2f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14013fd34  cmp     [rdi], r12b
0x14013fd37  jnz     loc_14013FC64
0x14013fd3d  jmp     short loc_14013FD48
0x14013fd3f  lea     rcx, [rbp+57h+var_80]
0x14013fd43  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14013fd48  mov     rcx, [rsi+28h]
0x14013fd4c  test    rcx, rcx
0x14013fd4f  jz      loc_14013FE30
0x14013fd55  mov     rax, [rcx]
0x14013fd58  xor     r9d, r9d
0x14013fd5b  mov     r8, [rsi+38h]
0x14013fd5f  lea     edx, [r9+7]
0x14013fd63  mov     rax, [rax+10h]
0x14013fd67  call    cs:__guard_dispatch_icall_fptr
0x14013fd6d  jmp     loc_14013FE30
0x14013fd72  mov     eax, 2F0Ah
0x14013fd77  cmp     edi, eax
0x14013fd79  ja      short loc_14013FDDA
0x14013fd7b  jz      loc_14013FE28
0x14013fd81  mov     eax, 2EFEh
0x14013fd86  cmp     edi, eax
0x14013fd88  ja      short loc_14013FDC3
0x14013fd8a  jz      loc_14013FE28
0x14013fd90  sub     edi, 2EE2h
0x14013fd96  jz      loc_14013FE28
0x14013fd9c  sub     edi, 1
0x14013fd9f  jz      loc_14013FE28
0x14013fda5  sub     edi, 4
0x14013fda8  jz      short loc_14013FE28
0x14013fdaa  sub     edi, 0Ah
0x14013fdad  jz      short loc_14013FDB9
0x14013fdaf  sub     edi, 0Bh
0x14013fdb2  jz      short loc_14013FE28
0x14013fdb4  cmp     edi, 1
0x14013fdb7  jmp     short loc_14013FE20
0x14013fdb9  mov     dword ptr [r15+28h], 1
0x14013fdc1  jmp     short loc_14013FE30
0x14013fdc3  sub     edi, 2EFFh
0x14013fdc9  jz      short loc_14013FE28
0x14013fdcb  sub     edi, 6
0x14013fdce  jz      short loc_14013FE28
0x14013fdd0  sub     edi, 1
0x14013fdd3  jz      short loc_14013FE28
0x14013fdd5  sub     edi, 1
0x14013fdd8  jmp     short loc_14013FDB2
0x14013fdda  mov     eax, 2F78h
0x14013fddf  cmp     edi, eax
0x14013fde1  ja      short loc_14013FE06
0x14013fde3  jz      short loc_14013FE28
0x14013fde5  sub     edi, 2F0Bh
0x14013fdeb  jz      short loc_14013FE28
0x14013fded  sub     edi, 1
0x14013fdf0  jz      short loc_14013FE28
0x14013fdf2  sub     edi, 1
0x14013fdf5  jz      short loc_14013FE28
0x14013fdf7  sub     edi, 7
0x14013fdfa  jz      short loc_14013FE28
0x14013fdfc  sub     edi, 3
0x14013fdff  jz      short loc_14013FE28
0x14013fe01  cmp     edi, 60h ; '`'
0x14013fe04  jmp     short loc_14013FE20
0x14013fe06  sub     edi, 2F7Ch
0x14013fe0c  jz      short loc_14013FE28
0x14013fe0e  sub     edi, 4
0x14013fe11  jz      short loc_14013FE28
0x14013fe13  sub     edi, 9
0x14013fe16  jz      short loc_14013FE28
0x14013fe18  sub     edi, 1
0x14013fe1b  jz      short loc_14013FE28
0x14013fe1d  cmp     edi, 5
0x14013fe20  jz      short loc_14013FE28
0x14013fe22  mov     [r15+28h], r13d
0x14013fe26  jmp     short loc_14013FE30
0x14013fe28  mov     dword ptr [r15+28h], 3
0x14013fe30  cmp     [rsi+469h], r12b
0x14013fe37  jnz     short loc_14013FE74
0x14013fe39  xor     edx, edx; lpfnInternetCallback
0x14013fe3b  mov     rcx, [rsi+38h]; hInternet
0x14013fe3f  call    cs:__imp_InternetSetStatusCallbackW
0x14013fe45  mov     byte ptr [rsi+469h], 1
0x14013fe4c  mov     rcx, [rsi+28h]
0x14013fe50  mov     rbx, r12
0x14013fe53  mov     [rbp+57h+var_90], rbx
0x14013fe57  mov     rax, [rcx]
0x14013fe5a  mov     rdx, r15
0x14013fe5d  mov     rax, [rax+8]
0x14013fe61  call    cs:__guard_dispatch_icall_fptr
0x14013fe67  lea     rdx, [rsi+8]
0x14013fe6b  mov     rcx, [rsi]
0x14013fe6e  call    ?erase@HttpClient_WinInet@Events@Applications@Microsoft@@IEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Applications::Events::HttpClient_WinInet::erase(std::string const &)
0x14013fe73  nop
  ... truncated ...
```
