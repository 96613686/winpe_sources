# Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,bool,void *)

- ea: `0x14001071c`
- end: `0x140010c36`
- name: `?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z`
- size: `1306`
- prototype: `int __fastcall(_QWORD *lpSrc)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000fccc`

## callees

- `0x140008660`
- `0x1400092f0`
- `0x14000a840`
- `0x14000df0c`
- `0x14000eb3c`
- `0x14000f194`
- `0x14000fad4`
- `0x14001071c`
- `0x1400116a0`
- `0x1400116c0`
- `0x1400116f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400107bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400109dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400107bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400109dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140010792`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140010792`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400107a8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400107a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010be4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010be4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140010a8e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140010b38`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140010a8e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140010b38`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x1400108da`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x1400108da`

## pseudocode

```c
int __fastcall Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(_QWORD *lpSrc)
{
  int v2; // eax
  HANDLE CurrentThread; // rax
  __int64 v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // r8
  WCHAR *v8; // rdi
  __int64 i; // rcx
  __int64 v10; // rsi
  unsigned __int64 v11; // rcx
  LPWSTR *v12; // rcx
  unsigned __int64 v13; // rdx
  LPWSTR *v14; // r9
  _WORD *v15; // rdi
  unsigned __int64 j; // rcx
  WCHAR *v17; // r8
  const WCHAR *v18; // rdx
  LPWSTR *v19; // rcx
  _WORD *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // edx
  __int64 v23; // rdi
  unsigned __int64 v24; // r8
  LPWSTR *v25; // rcx
  __int64 v26; // rdx
  LPWSTR *v27; // r9
  _WORD *v28; // rdi
  __int64 k; // rcx
  __int64 v30; // rax
  _QWORD *v31; // rsi
  unsigned int v32; // r8d
  const char *v33; // r9
  char *v34; // rdi
  __int64 trivial_2; // rax
  __int64 v36; // rcx
  WCHAR *v37; // r8
  WCHAR *v38; // rdi
  __int64 m; // rcx
  WCHAR *v40; // rdx
  const WCHAR *v41; // rcx
  DWORD v42; // eax
  unsigned int v43; // r8d
  const char *v44; // r9
  unsigned __int64 v45; // rdx
  LPWSTR *v46; // rcx
  unsigned __int64 v47; // r8
  LPWSTR *v48; // r9
  _WORD *v49; // rdi
  unsigned __int64 n; // rcx
  WCHAR *v51; // rdx
  const WCHAR *v52; // rcx
  unsigned int v53; // r8d
  const char *v54; // r9
  __int64 v55; // rax
  LPWSTR *v56; // rcx
  LPWSTR *v57; // r9
  _WORD *v58; // rdi
  unsigned __int64 ii; // rcx
  int result; // eax
  HANDLE TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  __int128 v62; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR lpDest[2]; // [rsp+50h] [rbp-30h] BYREF
  DWORD dwSize[2]; // [rsp+60h] [rbp-20h]
  unsigned __int64 v65; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v62 = *(_OWORD *)&off_1400193D8;
  *(_OWORD *)lpDest = *(_OWORD *)&off_1400193E8;
  v2 = Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(lpSrc, (__int64)lpDest, (char **)&v62);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x343,
      (__int64)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
      (const char *)(unsigned int)v2);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) && GetLastError() != 1008 )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x359, v5, v6);
  if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( GetLastError() != 1008 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x384, v32, v33);
  }
  else
  {
    *(_OWORD *)lpDest = 0;
    *(_QWORD *)dwSize = 0;
    v65 = 0;
    *(_QWORD *)&v62 = 263;
    v7 = (WCHAR *)std::wstring::_Allocate_for_capacity<0>(v4, &v62);
    lpDest[0] = v7;
    *(_QWORD *)dwSize = 260;
    v65 = v62;
    v8 = v7;
    for ( i = 260; i; --i )
      *v8++ = 0;
    v7[260] = 0;
    LODWORD(v10) = 260;
    while ( 1 )
    {
      v17 = (WCHAR *)lpDest;
      if ( v65 > 7 )
        v17 = lpDest[0];
      v18 = lpSrc[3] <= 7u ? (const WCHAR *)lpSrc : (const WCHAR *)*lpSrc;
      if ( ExpandEnvironmentStringsForUserW(TokenHandle, v18, v17, dwSize[0]) )
        break;
      if ( (unsigned int)v10 >= 0x410 )
        goto LABEL_33;
      v10 = (unsigned int)(2 * v10);
      v11 = *(_QWORD *)dwSize;
      if ( (unsigned __int64)(unsigned int)v10 > *(_QWORD *)dwSize )
      {
        v13 = (unsigned int)v10 - *(_QWORD *)dwSize;
        if ( v13 > v65 - *(_QWORD *)dwSize )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__K_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0_W_Z__K_W_Z(lpDest);
        }
        else
        {
          *(_QWORD *)dwSize = (unsigned int)v10;
          v14 = lpDest;
          if ( v65 > 7 )
            v14 = (LPWSTR *)lpDest[0];
          v15 = (_WORD *)v14 + v11;
          if ( v13 )
          {
            for ( j = (unsigned int)v10 - v11; j; --j )
              *v15++ = 0;
          }
          *((_WORD *)v14 + v10) = 0;
        }
      }
      else
      {
        *(_QWORD *)dwSize = (unsigned int)v10;
        v12 = lpDest;
        if ( v65 > 7 )
          v12 = (LPWSTR *)lpDest[0];
        *((_WORD *)v12 + v10) = 0;
      }
    }
    if ( v65 <= 7 )
    {
      v19 = lpDest;
    }
    else
    {
      v19 = (LPWSTR *)lpDest[0];
      if ( !lpDest[0] )
      {
LABEL_33:
        if ( lpSrc[3] <= 7u )
          v20 = lpSrc;
        else
          v20 = (_WORD *)*lpSrc;
        lpSrc[2] = 0;
        *v20 = 0;
        goto LABEL_111;
      }
    }
    if ( (unsigned int)v10 > 0x7FFFFFFF )
      goto LABEL_33;
    v21 = (unsigned int)v10;
    if ( (_DWORD)v10 )
    {
      while ( *(_WORD *)v19 )
      {
        v19 = (LPWSTR *)((char *)v19 + 2);
        if ( !--v21 )
          goto LABEL_42;
      }
      v22 = v10 - v21;
    }
    else
    {
LABEL_42:
      v22 = 0;
    }
    if ( !v21 )
      goto LABEL_33;
    v23 = v22;
    v24 = *(_QWORD *)dwSize;
    if ( (unsigned __int64)v22 > *(_QWORD *)dwSize )
    {
      v26 = v22 - *(_QWORD *)dwSize;
      if ( v23 - *(_QWORD *)dwSize > v65 - *(_QWORD *)dwSize )
      {
        ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__K_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0_W_Z__K_W_Z(lpDest);
      }
      else
      {
        *(_QWORD *)dwSize = v23;
        v27 = lpDest;
        if ( v65 > 7 )
          v27 = (LPWSTR *)lpDest[0];
        v28 = (_WORD *)v27 + v24;
        if ( v26 )
        {
          for ( k = v26; k; --k )
            *v28++ = 0;
        }
        *((_WORD *)v27 + v26 + v24) = 0;
      }
    }
    else
    {
      *(_QWORD *)dwSize = v22;
      v25 = lpDest;
      if ( v65 > 7 )
        v25 = (LPWSTR *)lpDest[0];
      *((_WORD *)v25 + v22) = 0;
    }
    std::wstring::operator=(lpSrc, lpDest);
    std::wstring::~wstring((char **)lpDest);
  }
  v30 = lpSrc[2];
  if ( lpSrc[3] <= 7u )
    v31 = lpSrc;
  else
    v31 = (_QWORD *)*lpSrc;
  if ( v30 )
  {
    v34 = (char *)v31 + 2 * v30;
    trivial_2 = _std_find_trivial_2(v31, v34, 37);
    if ( (char *)trivial_2 != v34 && (trivial_2 - (__int64)v31) >> 1 != -1 )
    {
      *(_OWORD *)lpDest = 0;
      *(_QWORD *)dwSize = 0;
      v65 = 0;
      *(_QWORD *)&v62 = 263;
      v37 = (WCHAR *)std::wstring::_Allocate_for_capacity<0>(v36, &v62);
      lpDest[0] = v37;
      *(_QWORD *)dwSize = 260;
      v65 = v62;
      v38 = v37;
      for ( m = 260; m; --m )
        *v38++ = 0;
      v37[260] = 0;
      v40 = (WCHAR *)lpDest;
      if ( v65 > 7 )
        v40 = lpDest[0];
      if ( lpSrc[3] <= 7u )
        v41 = (const WCHAR *)lpSrc;
      else
        v41 = (const WCHAR *)*lpSrc;
      v42 = ExpandEnvironmentStringsW(v41, v40, dwSize[0]);
      if ( !v42 )
        wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x390, v43, v44);
      v45 = *(_QWORD *)dwSize;
      if ( (unsigned __int64)v42 >= *(_QWORD *)dwSize )
      {
        if ( (unsigned __int64)v42 > *(_QWORD *)dwSize )
        {
          v47 = v42 - *(_QWORD *)dwSize;
          if ( v47 > v65 - *(_QWORD *)dwSize )
          {
            ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__K_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0_W_Z__K_W_Z(lpDest);
          }
          else
          {
            *(_QWORD *)dwSize = v42;
            v48 = lpDest;
            if ( v65 > 7 )
              v48 = (LPWSTR *)lpDest[0];
            v49 = (_WORD *)v48 + v45;
            if ( v47 )
            {
              for ( n = v47; n; --n )
                *v49++ = 0;
            }
            *((_WORD *)v48 + v47 + v45) = 0;
          }
        }
        else
        {
          *(_QWORD *)dwSize = v42;
          v46 = lpDest;
          if ( v65 > 7 )
            v46 = (LPWSTR *)lpDest[0];
          *((_WORD *)v46 + v42) = 0;
        }
        v51 = (WCHAR *)lpDest;
        if ( v65 > 7 )
          v51 = lpDest[0];
        if ( lpSrc[3] <= 7u )
          v52 = (const WCHAR *)lpSrc;
        else
          v52 = (const WCHAR *)*lpSrc;
        v42 = ExpandEnvironmentStringsW(v52, v51, dwSize[0]);
        if ( !v42 )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x397, v53, v54);
        v45 = *(_QWORD *)dwSize;
      }
      v55 = v42 - 1;
      if ( (unsigned int)v55 > v45 )
      {
        if ( (unsigned int)v55 - v45 > v65 - v45 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__K_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0_W_Z__K_W_Z(lpDest);
        }
        else
        {
          *(_QWORD *)dwSize = (unsigned int)v55;
          v57 = lpDest;
          if ( v65 > 7 )
            v57 = (LPWSTR *)lpDest[0];
          v58 = (_WORD *)v57 + v45;
          if ( (unsigned int)v55 != v45 )
          {
            for ( ii = (unsigned int)v55 - v45; ii; --ii )
              *v58++ = 0;
          }
          *((_WORD *)v57 + (unsigned int)v55) = 0;
        }
      }
      else
      {
        *(_QWORD *)dwSize = (unsigned int)v55;
        v56 = lpDest;
        if ( v65 > 7 )
          v56 = (LPWSTR *)lpDest[0];
        *((_WORD *)v56 + v55) = 0;
      }
      std::wstring::operator=(lpSrc, lpDest);
LABEL_111:
      std::wstring::~wstring((char **)lpDest);
    }
  }
  result = (_DWORD)TokenHandle - 1;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return CloseHandle(TokenHandle);
  return result;
}

```

## disassembly

```asm
0x14001071c  mov     [rsp-28h+arg_8], rbx
0x140010721  mov     [rsp-28h+arg_10], rsi
0x140010726  push    rbp
0x140010727  push    rdi
0x140010728  push    r12
0x14001072a  push    r14
0x14001072c  push    r15
0x14001072e  mov     rbp, rsp
0x140010731  sub     rsp, 80h
0x140010738  mov     rax, cs:__security_cookie
0x14001073f  xor     rax, rsp
0x140010742  mov     [rbp+var_10], rax
0x140010746  mov     rbx, rcx
0x140010749  movups  xmm0, xmmword ptr cs:off_1400193D8; "%DiagtrackStorageRoot%"
0x140010750  movdqu  [rbp+var_40], xmm0
0x140010755  movups  xmm1, xmmword ptr cs:off_1400193E8; "%ProgramData%\\Microsoft\\Diagnosis"
0x14001075c  movdqu  xmmword ptr [rbp+lpDest], xmm1
0x140010761  lea     r8, [rbp+var_40]
0x140010765  lea     rdx, [rbp+lpDest]
0x140010769  call    ??$ReplaceAllImpl@_W@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1_N@Z; Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(std::wstring &,std::wstring_view,std::wstring_view,bool)
0x14001076e  mov     rcx, [rbp+28h]; this
0x140010772  xor     r14d, r14d
0x140010775  test    eax, eax
0x140010777  jns     short loc_14001078E
0x140010779  mov     r9d, eax; char *
0x14001077c  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x140010783  mov     edx, 343h; void *
0x140010788  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001078d  nop
0x14001078e  mov     [rbp+TokenHandle], r14
0x140010792  call    cs:__imp_GetCurrentThread
0x140010798  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14001079c  mov     edx, 0Eh; DesiredAccess
0x1400107a1  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1400107a5  mov     rcx, rax; ThreadHandle
0x1400107a8  call    cs:__imp_OpenThreadToken
0x1400107ae  mov     esi, 3F0h
0x1400107b3  test    eax, eax
0x1400107b5  jnz     short loc_1400107D2
0x1400107b7  mov     rdi, [rbp+28h]
0x1400107bb  call    cs:__imp_GetLastError
0x1400107c1  cmp     eax, esi
0x1400107c3  jz      short loc_1400107D2
0x1400107c5  mov     edx, 359h; void *
0x1400107ca  mov     rcx, rdi; this
0x1400107cd  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1400107d2  mov     rax, [rbp+TokenHandle]
0x1400107d6  dec     rax
0x1400107d9  mov     r12d, 104h
0x1400107df  mov     r15d, 7
0x1400107e5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400107e9  ja      loc_1400109D9
0x1400107ef  xorps   xmm0, xmm0
0x1400107f2  movups  xmmword ptr [rbp+lpDest], xmm0
0x1400107f6  mov     qword ptr [rbp+dwSize], r14
0x1400107fa  mov     [rbp+var_18], r14
0x1400107fe  mov     qword ptr [rbp+var_40], 107h
0x140010806  lea     rdx, [rbp+var_40]
0x14001080a  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x14001080f  mov     r8, rax
0x140010812  mov     [rbp+lpDest], rax
0x140010816  mov     qword ptr [rbp+dwSize], r12
0x14001081a  mov     rcx, qword ptr [rbp+var_40]
0x14001081e  mov     [rbp+var_18], rcx
0x140010822  movzx   eax, r14w
0x140010826  mov     rdi, r8
0x140010829  mov     ecx, r12d
0x14001082c  rep stosw
0x14001082f  mov     [r8+208h], r14w
0x140010837  mov     esi, r12d
0x14001083a  jmp     short loc_1400108B7
0x14001083c  cmp     esi, 410h
0x140010842  jnb     loc_1400108FD
0x140010848  add     esi, esi
0x14001084a  mov     rcx, qword ptr [rbp+dwSize]
0x14001084e  mov     r8d, esi
0x140010851  cmp     r8, rcx
0x140010854  ja      short loc_14001086E
0x140010856  mov     qword ptr [rbp+dwSize], r8
0x14001085a  lea     rcx, [rbp+lpDest]
0x14001085e  cmp     [rbp+var_18], r15
0x140010862  cmova   rcx, [rbp+lpDest]
0x140010867  mov     [rcx+rsi*2], r14w
0x14001086c  jmp     short loc_1400108B7
0x14001086e  mov     rdx, r8
0x140010871  sub     rdx, rcx
0x140010874  mov     rax, [rbp+var_18]
0x140010878  sub     rax, rcx
0x14001087b  cmp     rdx, rax
0x14001087e  ja      short loc_1400108AB
0x140010880  mov     qword ptr [rbp+dwSize], r8
0x140010884  lea     r9, [rbp+lpDest]
0x140010888  cmp     [rbp+var_18], r15
0x14001088c  cmova   r9, [rbp+lpDest]
0x140010891  lea     rdi, [r9+rcx*2]
0x140010895  test    rdx, rdx
0x140010898  jz      short loc_1400108A4
0x14001089a  movzx   eax, r14w
0x14001089e  mov     rcx, rdx
0x1400108a1  rep stosw
0x1400108a4  mov     [r9+rsi*2], r14w
0x1400108a9  jmp     short loc_1400108B7
0x1400108ab  mov     r9, rdx
0x1400108ae  lea     rcx, [rbp+lpDest]; Src
0x1400108b2  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x1400108b7  lea     r8, [rbp+lpDest]
0x1400108bb  cmp     [rbp+var_18], r15
0x1400108bf  cmova   r8, [rbp+lpDest]; lpDest
0x1400108c4  cmp     [rbx+18h], r15
0x1400108c8  jbe     short loc_1400108CF
0x1400108ca  mov     rdx, [rbx]
0x1400108cd  jmp     short loc_1400108D2
0x1400108cf  mov     rdx, rbx; lpSrc
0x1400108d2  mov     r9d, [rbp+dwSize]; dwSize
0x1400108d6  mov     rcx, [rbp+TokenHandle]; hToken
0x1400108da  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x1400108e0  test    eax, eax
0x1400108e2  jz      loc_14001083C
0x1400108e8  mov     r11, [rbp+lpDest]
0x1400108ec  mov     r10, [rbp+var_18]
0x1400108f0  cmp     r10, r15
0x1400108f3  jbe     short loc_140010918
0x1400108f5  mov     rcx, r11
0x1400108f8  test    r11, r11
0x1400108fb  jnz     short loc_14001091C
0x1400108fd  cmp     [rbx+18h], r15
0x140010901  jbe     short loc_140010908
0x140010903  mov     rcx, [rbx]
0x140010906  jmp     short loc_14001090B
0x140010908  mov     rcx, rbx
0x14001090b  mov     [rbx+10h], r14
0x14001090f  mov     [rcx], r14w
0x140010913  jmp     loc_140010BCC
0x140010918  lea     rcx, [rbp+lpDest]
0x14001091c  cmp     esi, 7FFFFFFFh
0x140010922  ja      short loc_1400108FD
0x140010924  mov     eax, esi
0x140010926  mov     edx, esi
0x140010928  test    esi, esi
0x14001092a  jz      short loc_14001093C
0x14001092c  cmp     [rcx], r14w
0x140010930  jz      short loc_140010965
0x140010932  add     rcx, 2
0x140010936  sub     rax, 1
0x14001093a  jnz     short loc_14001092C
0x14001093c  mov     rdx, r14
0x14001093f  test    rax, rax
0x140010942  jz      short loc_1400108FD
0x140010944  mov     edi, edx
0x140010946  mov     r8, qword ptr [rbp+dwSize]
0x14001094a  cmp     rdi, r8
0x14001094d  ja      short loc_14001096A
0x14001094f  mov     qword ptr [rbp+dwSize], rdi
0x140010953  lea     rcx, [rbp+lpDest]
0x140010957  cmp     r10, r15
0x14001095a  cmova   rcx, r11
0x14001095e  mov     [rcx+rdi*2], r14w
0x140010963  jmp     short loc_1400109B4
0x140010965  sub     rdx, rax
0x140010968  jmp     short loc_14001093F
0x14001096a  mov     rdx, rdi
0x14001096d  sub     rdx, r8
0x140010970  mov     rax, r10
0x140010973  sub     rax, r8
0x140010976  cmp     rdx, rax
0x140010979  ja      short loc_1400109A8
0x14001097b  mov     qword ptr [rbp+dwSize], rdi
0x14001097f  lea     r9, [rbp+lpDest]
0x140010983  cmp     r10, r15
0x140010986  cmova   r9, r11
0x14001098a  lea     rdi, [r9+r8*2]
0x14001098e  test    rdx, rdx
0x140010991  jz      short loc_14001099D
0x140010993  movzx   eax, r14w
0x140010997  mov     rcx, rdx
0x14001099a  rep stosw
0x14001099d  lea     rcx, [rdx+r8]
0x1400109a1  mov     [r9+rcx*2], r14w
0x1400109a6  jmp     short loc_1400109B4
0x1400109a8  mov     r9, rdx
0x1400109ab  lea     rcx, [rbp+lpDest]; Src
0x1400109af  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x1400109b4  lea     rdx, [rbp+lpDest]
0x1400109b8  mov     rcx, rbx
0x1400109bb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400109c0  nop
0x1400109c1  lea     rcx, [rbp+lpDest]; void *
0x1400109c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400109ca  mov     rax, [rbx+10h]
0x1400109ce  cmp     [rbx+18h], r15
0x1400109d2  jbe     short loc_1400109ED
0x1400109d4  mov     rsi, [rbx]
0x1400109d7  jmp     short loc_1400109F0
0x1400109d9  mov     rdi, [rbp+28h]
0x1400109dd  call    cs:__imp_GetLastError
0x1400109e3  cmp     eax, esi
0x1400109e5  jnz     loc_140010C1D
0x1400109eb  jmp     short loc_1400109CA
0x1400109ed  mov     rsi, rbx
0x1400109f0  test    rax, rax
0x1400109f3  jz      loc_140010BD6
0x1400109f9  lea     rdi, [rsi+rax*2]
0x1400109fd  mov     r8d, 25h ; '%'
0x140010a03  mov     rdx, rdi
0x140010a06  mov     rcx, rsi
0x140010a09  call    __std_find_trivial_2
0x140010a0e  cmp     rax, rdi
0x140010a11  jz      loc_140010BD6
0x140010a17  sub     rax, rsi
0x140010a1a  sar     rax, 1
0x140010a1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140010a21  jz      loc_140010BD6
0x140010a27  xorps   xmm0, xmm0
0x140010a2a  movups  xmmword ptr [rbp+lpDest], xmm0
0x140010a2e  mov     qword ptr [rbp+dwSize], r14
0x140010a32  mov     [rbp+var_18], r14
0x140010a36  mov     qword ptr [rbp+var_40], 107h
0x140010a3e  lea     rdx, [rbp+var_40]
0x140010a42  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x140010a47  mov     r8, rax
0x140010a4a  mov     [rbp+lpDest], rax
0x140010a4e  mov     qword ptr [rbp+dwSize], r12
0x140010a52  mov     rcx, qword ptr [rbp+var_40]
0x140010a56  mov     [rbp+var_18], rcx
0x140010a5a  movzx   eax, r14w
0x140010a5e  mov     rdi, r8
0x140010a61  mov     rcx, r12
0x140010a64  rep stosw
0x140010a67  mov     [r8+208h], r14w
0x140010a6f  lea     rdx, [rbp+lpDest]
0x140010a73  cmp     [rbp+var_18], r15
0x140010a77  cmova   rdx, [rbp+lpDest]; lpDst
0x140010a7c  cmp     [rbx+18h], r15
0x140010a80  jbe     short loc_140010A87
0x140010a82  mov     rcx, [rbx]
0x140010a85  jmp     short loc_140010A8A
0x140010a87  mov     rcx, rbx; lpSrc
0x140010a8a  mov     r8d, [rbp+dwSize]; nSize
0x140010a8e  call    cs:__imp_ExpandEnvironmentStringsW
0x140010a94  mov     rcx, [rbp+28h]; this
0x140010a98  test    eax, eax
0x140010a9a  jz      loc_140010C2B
0x140010aa0  mov     rdx, qword ptr [rbp+dwSize]
0x140010aa4  mov     edi, eax
0x140010aa6  cmp     rdi, rdx
0x140010aa9  jb      loc_140010B4E
0x140010aaf  ja      short loc_140010AC9
0x140010ab1  mov     qword ptr [rbp+dwSize], rdi
0x140010ab5  lea     rcx, [rbp+lpDest]
0x140010ab9  cmp     [rbp+var_18], r15
0x140010abd  cmova   rcx, [rbp+lpDest]
0x140010ac2  mov     [rcx+rdi*2], r14w
0x140010ac7  jmp     short loc_140010B19
0x140010ac9  mov     r8, rdi
0x140010acc  sub     r8, rdx
0x140010acf  mov     rax, [rbp+var_18]
0x140010ad3  sub     rax, rdx
0x140010ad6  cmp     r8, rax
0x140010ad9  ja      short loc_140010B0A
0x140010adb  mov     qword ptr [rbp+dwSize], rdi
0x140010adf  lea     r9, [rbp+lpDest]
0x140010ae3  cmp     [rbp+var_18], r15
0x140010ae7  cmova   r9, [rbp+lpDest]
0x140010aec  lea     rdi, [r9+rdx*2]
0x140010af0  test    r8, r8
0x140010af3  jz      short loc_140010AFF
0x140010af5  movzx   eax, r14w
0x140010af9  mov     rcx, r8
0x140010afc  rep stosw
0x140010aff  lea     rcx, [r8+rdx]
0x140010b03  mov     [r9+rcx*2], r14w
0x140010b08  jmp     short loc_140010B19
0x140010b0a  mov     r9, r8
0x140010b0d  mov     rdx, r8
0x140010b10  lea     rcx, [rbp+lpDest]; Src
0x140010b14  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x140010b19  lea     rdx, [rbp+lpDest]
0x140010b1d  cmp     [rbp+var_18], r15
0x140010b21  cmova   rdx, [rbp+lpDest]; lpDst
0x140010b26  cmp     [rbx+18h], r15
0x140010b2a  jbe     short loc_140010B31
0x140010b2c  mov     rcx, [rbx]
0x140010b2f  jmp     short loc_140010B34
0x140010b31  mov     rcx, rbx; lpSrc
0x140010b34  mov     r8d, [rbp+dwSize]; nSize
0x140010b38  call    cs:__imp_ExpandEnvironmentStringsW
0x140010b3e  mov     rcx, [rbp+28h]; this
0x140010b42  test    eax, eax
0x140010b44  jz      loc_140010C12
0x140010b4a  mov     rdx, qword ptr [rbp+dwSize]
0x140010b4e  dec     eax
0x140010b50  mov     edi, eax
0x140010b52  cmp     rdi, rdx
0x140010b55  ja      short loc_140010B6F
0x140010b57  mov     qword ptr [rbp+dwSize], rdi
0x140010b5b  lea     rcx, [rbp+lpDest]
0x140010b5f  cmp     [rbp+var_18], r15
0x140010b63  cmova   rcx, [rbp+lpDest]
0x140010b68  mov     [rcx+rax*2], r14w
0x140010b6d  jmp     short loc_140010BBF
  ... truncated ...
```
