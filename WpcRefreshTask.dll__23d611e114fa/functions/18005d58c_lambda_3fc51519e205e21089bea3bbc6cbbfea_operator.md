# _lambda_3fc51519e205e21089bea3bbc6cbbfea_::operator()

- ea: `0x18005d58c`
- end: `0x18005da11`
- name: `_lambda_3fc51519e205e21089bea3bbc6cbbfea_::operator()`
- size: `1157`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x18005f6b0`

## callees

- `0x1800060a0`
- `0x1800060fc`
- `0x180006ed4`
- `0x180006ee0`
- `0x180007e28`
- `0x180008d50`
- `0x180008e04`
- `0x18000995c`
- `0x180009a18`
- `0x180009a80`
- `0x180009de0`
- `0x18000ecc0`
- `0x1800349ac`
- `0x1800354b8`
- `0x180035e0c`
- `0x18005d58c`
- `0x18005df78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d70e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d88c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d8f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d70e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d88c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d8f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d955`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005d5ea`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005d700`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005d77a`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005d5ea`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005d700`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005d77a`
- `WINHTTP!WinHttpReadData` at `0x18005d637`
- `WINHTTP!WinHttpReadData` at `0x18005d637`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_3fc51519e205e21089bea3bbc6cbbfea_::operator()(__int64 a1, void *a2)
{
  __int64 v4; // rdx
  DWORD v5; // ecx
  char *v6; // r14
  char *v7; // rbx
  char v8; // r9
  unsigned __int64 v9; // rcx
  __int128 *p_Src; // rax
  __int128 *v11; // r8
  signed int v12; // eax
  unsigned int v13; // ebx
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // rbx
  void *v16; // r13
  _QWORD *v17; // r12
  _QWORD *v18; // rsi
  _QWORD *v19; // r14
  char *v20; // r15
  char *v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  signed int v26; // eax
  unsigned int v27; // ebx
  signed int v28; // eax
  unsigned int v29; // ebx
  signed int LastError; // eax
  unsigned int v31; // ebx
  DWORD dwNumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpdwBufferLength; // [rsp+34h] [rbp-CCh] BYREF
  DWORD dwBufferLength; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-C0h] BYREF
  void *v36; // [rsp+68h] [rbp-98h]
  _BYTE v37[16]; // [rsp+70h] [rbp-90h] BYREF
  __int128 Src; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v39; // [rsp+90h] [rbp-70h]
  unsigned __int64 v40; // [rsp+98h] [rbp-68h]
  __int128 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-50h]
  __int64 v43; // [rsp+B8h] [rbp-48h]
  _BYTE Buffer[2048]; // [rsp+D0h] [rbp-30h] BYREF

  dwBufferLength = 4;
  if ( !WinHttpQueryHeaders(a2, 0x20000013u, 0, *(LPVOID *)a1, &dwBufferLength, 0) )
  {
    LastError = GetLastError();
    v31 = LastError;
    if ( LastError > 0 )
      v31 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v31);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&v41, v31);
    throw (ErrorCodeException *)&v41;
  }
  dwNumberOfBytesRead = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  Src = 0;
  v39 = 0;
  v40 = 15;
  LOBYTE(Src) = 0;
  do
  {
    if ( !WinHttpReadData(a2, Buffer, 0x800u, &dwNumberOfBytesRead) )
    {
      v28 = GetLastError();
      v29 = v28;
      if ( v28 > 0 )
        v29 = (unsigned __int16)v28 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v29);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v29);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v5 = dwNumberOfBytesRead;
    v6 = &Buffer[dwNumberOfBytesRead];
    v7 = Buffer;
    if ( Buffer != v6 )
    {
      do
      {
        v8 = *v7;
        v9 = v39;
        if ( v39 >= v40 )
        {
          std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(&Src);
        }
        else
        {
          ++v39;
          p_Src = &Src;
          if ( v40 > 0xF )
            p_Src = (__int128 *)Src;
          *((_BYTE *)p_Src + v9) = v8;
          *((_BYTE *)p_Src + v9 + 1) = 0;
        }
        ++v7;
      }
      while ( v7 != v6 );
      v5 = dwNumberOfBytesRead;
    }
  }
  while ( v5 == 2048 );
  v11 = &Src;
  if ( v40 > 0xF )
    v11 = (__int128 *)Src;
  StringAlgo::ToUnicode(&v41, v4, v11);
  std::wstring::operator=(*(_QWORD *)a1 + 8LL, &v41);
  std::wstring::~wstring(&v41);
  if ( *(_BYTE *)(a1 + 8) )
  {
    lpdwBufferLength = 0;
    if ( !WinHttpQueryHeaders(a2, 0x16u, 0, 0, &lpdwBufferLength, 0) )
    {
      v12 = GetLastError();
      v13 = v12;
      if ( v12 != 122 && v12 )
      {
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v13);
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v13);
        throw (ErrorCodeException *)pExceptionObject;
      }
      v14 = (unsigned __int64)lpdwBufferLength >> 1;
      v15 = saturated_mul(v14, 2u);
      v16 = operator new[](v15);
      memset_0(v16, 0, v15);
      v36 = v16;
      if ( !WinHttpQueryHeaders(a2, 0x15u, 0, v16, &lpdwBufferLength, 0) )
      {
        v26 = GetLastError();
        v27 = v26;
        if ( v26 > 0 )
          v27 = (unsigned __int16)v26 | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v27);
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v27);
        throw (ErrorCodeException *)pExceptionObject;
      }
      v41 = 0;
      v42 = 0;
      v43 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v41, v16, v14);
      v17 = (_QWORD *)ParseHeaders(v37, &v41);
      v18 = (_QWORD *)(*(_QWORD *)a1 + 40LL);
      if ( v18 != v17 )
      {
        v19 = (_QWORD *)*v18;
        v20 = *(char **)(*v18 + 8LL);
        while ( !v20[25] )
        {
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            v18,
            v18,
            *((_QWORD *)v20 + 2));
          v21 = v20;
          v20 = *(char **)v20;
          std::wstring::~wstring(v21 + 64);
          std::wstring::~wstring(v21 + 32);
          operator delete(v21, 0x60u);
        }
        v19[1] = v19;
        *v19 = v19;
        v19[2] = v19;
        v18[1] = 0;
        v22 = *v18;
        *v18 = *v17;
        *v17 = v22;
        v23 = v18[1];
        v18[1] = v17[1];
        v17[1] = v23;
      }
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v37);
      std::wstring::~wstring(&v41);
      operator delete(v16, v24);
    }
  }
  return std::string::~string(&Src);
}

```

## disassembly

```asm
0x18005d58c  mov     [rsp-8+arg_10], rbx
0x18005d591  push    rbp
0x18005d592  push    rsi
0x18005d593  push    rdi
0x18005d594  push    r12
0x18005d596  push    r13
0x18005d598  push    r14
0x18005d59a  push    r15
0x18005d59c  lea     rbp, [rsp-7E0h]
0x18005d5a4  sub     rsp, 8E0h
0x18005d5ab  mov     rax, cs:__security_cookie
0x18005d5b2  xor     rax, rsp
0x18005d5b5  mov     [rbp+810h+var_40], rax
0x18005d5bc  mov     rdi, rdx
0x18005d5bf  mov     rsi, rcx
0x18005d5c2  xor     r15d, r15d
0x18005d5c5  mov     [rsp+910h+dwBufferLength], 4
0x18005d5cd  mov     [rsp+910h+lpdwIndex], r15; lpdwIndex
0x18005d5d2  lea     rax, [rsp+910h+dwBufferLength]
0x18005d5d7  mov     [rsp+910h+lpdwBufferLength], rax; lpdwBufferLength
0x18005d5dc  mov     r9, [rcx]; lpBuffer
0x18005d5df  xor     r8d, r8d; pwszName
0x18005d5e2  mov     edx, 20000013h; dwInfoLevel
0x18005d5e7  mov     rcx, rdi; hRequest
0x18005d5ea  call    cs:__imp_WinHttpQueryHeaders
0x18005d5f0  test    eax, eax
0x18005d5f2  jz      loc_18005D955
0x18005d5f8  mov     [rsp+910h+dwNumberOfBytesRead], r15d
0x18005d5fd  mov     r12d, 800h
0x18005d603  mov     r8d, r12d; Size
0x18005d606  xor     edx, edx; Val
0x18005d608  lea     rcx, [rbp+810h+Buffer]; void *
0x18005d60c  call    memset_0
0x18005d611  xorps   xmm0, xmm0
0x18005d614  movups  [rbp+810h+Src], xmm0
0x18005d618  mov     [rbp+810h+var_880], r15
0x18005d61c  mov     [rbp+810h+var_878], 0Fh
0x18005d624  mov     byte ptr [rbp+810h+Src], r15b
0x18005d628  lea     r9, [rsp+910h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18005d62d  mov     r8d, r12d; dwNumberOfBytesToRead
0x18005d630  lea     rdx, [rbp+810h+Buffer]; lpBuffer
0x18005d634  mov     rcx, rdi; hRequest
0x18005d637  call    cs:__imp_WinHttpReadData
0x18005d63d  test    eax, eax
0x18005d63f  jz      loc_18005D8F1
0x18005d645  mov     ecx, [rsp+910h+dwNumberOfBytesRead]
0x18005d649  lea     r14, [rbp+810h+Buffer]
0x18005d64d  add     r14, rcx
0x18005d650  lea     rbx, [rbp+810h+Buffer]
0x18005d654  lea     rax, [rbp+810h+Buffer]
0x18005d658  cmp     rax, r14
0x18005d65b  jz      short loc_18005D6A0
0x18005d65d  mov     r9b, [rbx]
0x18005d660  mov     rcx, [rbp+810h+var_880]
0x18005d664  cmp     rcx, [rbp+810h+var_878]
0x18005d668  jnb     short loc_18005D68B
0x18005d66a  lea     rax, [rcx+1]
0x18005d66e  mov     [rbp+810h+var_880], rax
0x18005d672  lea     rax, [rbp+810h+Src]
0x18005d676  cmp     [rbp+810h+var_878], 0Fh
0x18005d67b  cmova   rax, qword ptr [rbp+810h+Src]
0x18005d680  mov     [rax+rcx], r9b
0x18005d684  mov     [rax+rcx+1], r15b
0x18005d689  jmp     short loc_18005D694
0x18005d68b  lea     rcx, [rbp+810h+Src]; Src
0x18005d68f  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18005d694  inc     rbx
0x18005d697  cmp     rbx, r14
0x18005d69a  jnz     short loc_18005D65D
0x18005d69c  mov     ecx, [rsp+910h+dwNumberOfBytesRead]
0x18005d6a0  cmp     ecx, r12d
0x18005d6a3  jz      short loc_18005D628
0x18005d6a5  lea     r8, [rbp+810h+Src]
0x18005d6a9  cmp     [rbp+810h+var_878], 0Fh
0x18005d6ae  cmova   r8, qword ptr [rbp+810h+Src]
0x18005d6b3  lea     rcx, [rbp+810h+var_870]
0x18005d6b7  call    ?ToUnicode@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HPEBDH@Z; StringAlgo::ToUnicode(int,char const *,int)
0x18005d6bc  mov     rcx, [rsi]
0x18005d6bf  add     rcx, 8
0x18005d6c3  lea     rdx, [rbp+810h+var_870]
0x18005d6c7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005d6cc  lea     rcx, [rbp+810h+var_870]
0x18005d6d0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d6d5  cmp     [rsi+8], r15b
0x18005d6d9  jz      loc_18005D859
0x18005d6df  mov     [rsp+910h+var_8DC], r15d
0x18005d6e4  mov     [rsp+910h+lpdwIndex], r15; lpdwIndex
0x18005d6e9  lea     rax, [rsp+910h+var_8DC]
0x18005d6ee  mov     [rsp+910h+lpdwBufferLength], rax; lpdwBufferLength
0x18005d6f3  xor     r9d, r9d; lpBuffer
0x18005d6f6  xor     r8d, r8d; pwszName
0x18005d6f9  lea     edx, [r9+16h]; dwInfoLevel
0x18005d6fd  mov     rcx, rdi; hRequest
0x18005d700  call    cs:__imp_WinHttpQueryHeaders
0x18005d706  test    eax, eax
0x18005d708  jnz     loc_18005D859
0x18005d70e  call    cs:__imp_GetLastError
0x18005d714  mov     ebx, eax
0x18005d716  cmp     eax, 7Ah ; 'z'
0x18005d719  jz      short loc_18005D723
0x18005d71b  test    eax, eax
0x18005d71d  jnz     loc_18005D9B7
0x18005d723  mov     r14d, [rsp+910h+var_8DC]
0x18005d728  shr     r14, 1
0x18005d72b  mov     eax, 2
0x18005d730  mul     r14
0x18005d733  mov     rbx, rax
0x18005d736  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005d73d  cmovb   rbx, rax
0x18005d741  mov     rcx, rbx; unsigned __int64
0x18005d744  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005d749  mov     r13, rax
0x18005d74c  mov     r8, rbx; Size
0x18005d74f  xor     edx, edx; Val
0x18005d751  mov     rcx, rax; void *
0x18005d754  call    memset_0
0x18005d759  mov     [rsp+910h+var_8A8], r13
0x18005d75e  mov     [rsp+910h+lpdwIndex], r15; lpdwIndex
0x18005d763  lea     rax, [rsp+910h+var_8DC]
0x18005d768  mov     [rsp+910h+lpdwBufferLength], rax; lpdwBufferLength
0x18005d76d  mov     r9, r13; lpBuffer
0x18005d770  xor     r8d, r8d; pwszName
0x18005d773  lea     edx, [r8+15h]; dwInfoLevel
0x18005d777  mov     rcx, rdi; hRequest
0x18005d77a  call    cs:__imp_WinHttpQueryHeaders
0x18005d780  test    eax, eax
0x18005d782  jz      loc_18005D88C
0x18005d788  xorps   xmm0, xmm0
0x18005d78b  movups  [rbp+810h+var_870], xmm0
0x18005d78f  mov     [rbp+810h+var_860], r15
0x18005d793  mov     [rbp+810h+var_858], r15
0x18005d797  mov     r8, r14
0x18005d79a  mov     rdx, r13
0x18005d79d  lea     rcx, [rbp+810h+var_870]
0x18005d7a1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005d7a6  nop
0x18005d7a7  lea     rdx, [rbp+810h+var_870]
0x18005d7ab  lea     rcx, [rsp+910h+var_8A0]
0x18005d7b0  call    ?ParseHeaders@@YA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; ParseHeaders(std::wstring const &)
0x18005d7b5  mov     r12, rax
0x18005d7b8  mov     rsi, [rsi]
0x18005d7bb  add     rsi, 28h ; '('
0x18005d7bf  cmp     rsi, rax
0x18005d7c2  jz      short loc_18005D83B
0x18005d7c4  mov     r14, [rsi]
0x18005d7c7  mov     r15, [r14+8]
0x18005d7cb  jmp     short loc_18005D801
0x18005d7cd  mov     r8, [r15+10h]
0x18005d7d1  mov     rdx, rsi
0x18005d7d4  mov     rcx, rsi
0x18005d7d7  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x18005d7dc  mov     rdi, r15
0x18005d7df  mov     r15, [r15]
0x18005d7e2  lea     rcx, [rdi+40h]
0x18005d7e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d7eb  lea     rcx, [rdi+20h]
0x18005d7ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d7f4  mov     edx, 60h ; '`'; unsigned __int64
0x18005d7f9  mov     rcx, rdi; void *
0x18005d7fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005d801  cmp     byte ptr [r15+19h], 0
0x18005d806  jz      short loc_18005D7CD
0x18005d808  mov     [r14+8], r14
0x18005d80c  mov     [r14], r14
0x18005d80f  mov     [r14+10h], r14
0x18005d813  mov     qword ptr [rsi+8], 0
0x18005d81b  mov     rcx, [rsi]
0x18005d81e  mov     rax, [r12]
0x18005d822  mov     [rsi], rax
0x18005d825  mov     [r12], rcx
0x18005d829  mov     rcx, [rsi+8]
0x18005d82d  mov     rax, [r12+8]
0x18005d832  mov     [rsi+8], rax
0x18005d836  mov     [r12+8], rcx
0x18005d83b  lea     rcx, [rsp+910h+var_8A0]
0x18005d840  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18005d845  nop
0x18005d846  lea     rcx, [rbp+810h+var_870]
0x18005d84a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d84f  nop
0x18005d850  mov     rcx, r13; void *
0x18005d853  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005d858  nop
0x18005d859  lea     rcx, [rbp+810h+Src]
0x18005d85d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18005d862  mov     rcx, [rbp+810h+var_40]
0x18005d869  xor     rcx, rsp; StackCookie
0x18005d86c  call    __security_check_cookie
0x18005d871  mov     rbx, [rsp+910h+arg_10]
0x18005d879  add     rsp, 8E0h
0x18005d880  pop     r15
0x18005d882  pop     r14
0x18005d884  pop     r13
0x18005d886  pop     r12
0x18005d888  pop     rdi
0x18005d889  pop     rsi
0x18005d88a  pop     rbp
0x18005d88b  retn
0x18005d88c  call    cs:__imp_GetLastError
0x18005d892  nop
0x18005d893  mov     ebx, eax
0x18005d895  test    eax, eax
0x18005d897  jle     short loc_18005D8A2
0x18005d899  movzx   ebx, ax
0x18005d89c  or      ebx, 80070000h
0x18005d8a2  lea     rax, WPP_GLOBAL_Control
0x18005d8a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d8b0  cmp     rcx, rax
0x18005d8b3  jz      short loc_18005D8D3
0x18005d8b5  test    byte ptr [rcx+1Ch], 1
0x18005d8b9  jz      short loc_18005D8D3
0x18005d8bb  mov     edx, 14h
0x18005d8c0  mov     r9d, ebx
0x18005d8c3  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x18005d8ca  mov     rcx, [rcx+10h]
0x18005d8ce  call    WPP_SF_d
0x18005d8d3  mov     edx, ebx; int
0x18005d8d5  lea     rcx, [rsp+910h+pExceptionObject]; this
0x18005d8da  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18005d8df  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18005d8e6  lea     rcx, [rsp+910h+pExceptionObject]; pExceptionObject
0x18005d8eb  call    _CxxThrowException_0
0x18005d8f1  call    cs:__imp_GetLastError
0x18005d8f7  mov     ebx, eax
0x18005d8f9  test    eax, eax
0x18005d8fb  jle     short loc_18005D906
0x18005d8fd  movzx   ebx, ax
0x18005d900  or      ebx, 80070000h
0x18005d906  lea     rax, WPP_GLOBAL_Control
0x18005d90d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d914  cmp     rcx, rax
0x18005d917  jz      short loc_18005D937
0x18005d919  test    byte ptr [rcx+1Ch], 1
0x18005d91d  jz      short loc_18005D937
0x18005d91f  mov     edx, 12h
0x18005d924  mov     r9d, ebx
0x18005d927  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x18005d92e  mov     rcx, [rcx+10h]
0x18005d932  call    WPP_SF_d
0x18005d937  mov     edx, ebx; int
0x18005d939  lea     rcx, [rsp+910h+pExceptionObject]; this
0x18005d93e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18005d943  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18005d94a  lea     rcx, [rsp+910h+pExceptionObject]; pExceptionObject
0x18005d94f  call    _CxxThrowException_0
0x18005d955  call    cs:__imp_GetLastError
0x18005d95b  mov     ebx, eax
0x18005d95d  test    eax, eax
0x18005d95f  jle     short loc_18005D96A
0x18005d961  movzx   ebx, ax
0x18005d964  or      ebx, 80070000h
0x18005d96a  lea     rax, WPP_GLOBAL_Control
0x18005d971  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d978  cmp     rcx, rax
0x18005d97b  jz      short loc_18005D99B
0x18005d97d  test    byte ptr [rcx+1Ch], 1
0x18005d981  jz      short loc_18005D99B
0x18005d983  mov     edx, 11h
0x18005d988  mov     r9d, ebx
0x18005d98b  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x18005d992  mov     rcx, [rcx+10h]
0x18005d996  call    WPP_SF_d
0x18005d99b  mov     edx, ebx; int
0x18005d99d  lea     rcx, [rbp+810h+var_870]; this
0x18005d9a1  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18005d9a6  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18005d9ad  lea     rcx, [rbp+810h+var_870]; pExceptionObject
0x18005d9b1  call    _CxxThrowException_0
0x18005d9b7  jle     short loc_18005D9C2
0x18005d9b9  movzx   ebx, ax
0x18005d9bc  or      ebx, 80070000h
0x18005d9c2  lea     rax, WPP_GLOBAL_Control
0x18005d9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d9d0  cmp     rcx, rax
0x18005d9d3  jz      short loc_18005D9F3
0x18005d9d5  test    byte ptr [rcx+1Ch], 1
0x18005d9d9  jz      short loc_18005D9F3
0x18005d9db  mov     edx, 13h
0x18005d9e0  mov     r9d, ebx
0x18005d9e3  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x18005d9ea  mov     rcx, [rcx+10h]
0x18005d9ee  call    WPP_SF_d
0x18005d9f3  mov     edx, ebx; int
0x18005d9f5  lea     rcx, [rsp+910h+pExceptionObject]; this
0x18005d9fa  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18005d9ff  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18005da06  lea     rcx, [rsp+910h+pExceptionObject]; pExceptionObject
0x18005da0b  call    _CxxThrowException_0
```
