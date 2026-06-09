# Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace(wchar_t const *)

- ea: `0x180296ad0`
- end: `0x1802971e3`
- name: `?SnapMiniTrace@UtcApiManager@Diagnostics@Microsoft@@UEAAJPEB_W@Z`
- size: `1811`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcApiManager *this, const wchar_t *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180020150`
- `0x18002110c`
- `0x18002afd8`
- `0x18002b770`
- `0x18002b9c0`
- `0x18002df00`
- `0x180064e8c`
- `0x180087174`
- `0x18008abf4`
- `0x18009b658`
- `0x18009c194`
- `0x18009c8c0`
- `0x1800c53b4`
- `0x1800dce08`
- `0x180102bbc`
- `0x180142fcc`
- `0x1801bbc78`
- `0x1801d5a9c`
- `0x18020aac0`
- `0x180287298`
- `0x180296ad0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180296ca8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180296ca8`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180296c13`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180296c13`
- `RPCRT4!RpcRevertToSelf` at `0x180296bb7`
- `RPCRT4!RpcRevertToSelf` at `0x180296c67`
- `RPCRT4!RpcRevertToSelf` at `0x180296d34`
- `RPCRT4!RpcRevertToSelf` at `0x180296e20`
- `RPCRT4!RpcRevertToSelf` at `0x180296efd`
- `RPCRT4!RpcRevertToSelf` at `0x180296f93`
- `RPCRT4!RpcRevertToSelf` at `0x180297081`
- `RPCRT4!RpcRevertToSelf` at `0x1802970d2`
- `RPCRT4!RpcRevertToSelf` at `0x180296bb7`
- `RPCRT4!RpcRevertToSelf` at `0x180296c67`
- `RPCRT4!RpcRevertToSelf` at `0x180296d34`
- `RPCRT4!RpcRevertToSelf` at `0x180296e20`
- `RPCRT4!RpcRevertToSelf` at `0x180296efd`
- `RPCRT4!RpcRevertToSelf` at `0x180296f93`
- `RPCRT4!RpcRevertToSelf` at `0x180297081`
- `RPCRT4!RpcRevertToSelf` at `0x1802970d2`

## string_xrefs

- `0x180296b13`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180296b8b`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180296c2d`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180296cfa`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180296dcf`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180296eac`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180296f42`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180297030`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x18029711a`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x180297134`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x18029714e`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x180297168`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x180297182`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x18029719c`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x1802971b6`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x1802971d0`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace(
        Microsoft::Diagnostics::UtcApiManager *this,
        const wchar_t *a2)
{
  _QWORD *v4; // rcx
  const char *v5; // r9
  WCHAR *v6; // rcx
  const char *v7; // r9
  const WCHAR *v8; // rcx
  const char *v9; // r9
  int v10; // r8d
  int v11; // r9d
  PWSTR *v12; // rax
  unsigned int v13; // ebx
  const char *v14; // r9
  struct Microsoft::Diagnostics::TraceManager *TraceManager; // rdi
  __int64 v16; // r8
  int v17; // eax
  unsigned int v18; // ebx
  const char *v19; // r9
  int appended; // eax
  __int64 v21; // r8
  unsigned int v22; // ebx
  const char *v23; // r9
  __int128 v24; // xmm6
  int v25; // edx
  int v26; // eax
  unsigned int v27; // ebx
  const char *v28; // r9
  const char *v29; // r9
  unsigned int v30; // [rsp+20h] [rbp-E8h]
  int v31; // [rsp+20h] [rbp-E8h]
  char v32; // [rsp+41h] [rbp-C7h]
  PWSTR *v33; // [rsp+48h] [rbp-C0h] BYREF
  char v34; // [rsp+50h] [rbp-B8h]
  __int128 v35; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v36[4]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v37; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v38[16]; // [rsp+90h] [rbp-78h] BYREF
  PWSTR pszPathOut[3]; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v40; // [rsp+B8h] [rbp-50h]
  _QWORD v41[2]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v42; // [rsp+D0h] [rbp-38h]
  unsigned __int64 v43; // [rsp+D8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( a2 )
  {
    Microsoft::Diagnostics::UtcApiManager::ImpersonateRpcCaller(this);
    std::wstring::wstring(v41, a2);
    v4 = v41;
    if ( v43 > 7 )
      v4 = (_QWORD *)v41[0];
    if ( std::_Traits_find_ch<std::char_traits<wchar_t>>(v4, v42, 0, 47) == -1 )
    {
      std::wstring::wstring(pszPathOut, v42, 0);
      v6 = (WCHAR *)pszPathOut;
      if ( v40 > 7 )
        v6 = pszPathOut[0];
      if ( PathCchCanonicalizeEx(v6, (size_t)pszPathOut[2] + 1, a2, 1u) >= 0 )
      {
        Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)pszPathOut);
        v8 = (const WCHAR *)pszPathOut;
        if ( v40 > 7 )
          v8 = pszPathOut[0];
        if ( GetFileAttributesW(v8) == -1 )
        {
          if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x2000) )
          {
            v12 = pszPathOut;
            if ( v40 > 7 )
              v12 = (PWSTR *)pszPathOut[0];
            *(_QWORD *)v36 = v12;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
              (unsigned int)&dword_1804543B0,
              (unsigned int)byte_1803ED059,
              v10,
              v11,
              (__int64)v36);
          }
          v33 = pszPathOut;
          v34 = 1;
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_1804631A0, 0, 0) )
          {
            TraceManager = Microsoft::Diagnostics::LifetimeManager::GetTraceManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
            *(_QWORD *)&v37 = *((_QWORD *)TraceManager + 4);
            *((_QWORD *)&v37 + 1) = (char *)TraceManager + 272;
            v35 = *(_OWORD *)&off_18036C4E8;
            *(_OWORD *)v36 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPathOut, v38, v16);
            v17 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v36, 0, &v35);
            v18 = v17;
            if ( v17 >= 0 )
            {
              v35 = *(_OWORD *)&Microsoft::Diagnostics::TraceSlot::k_traceSlotOutputNames;
              appended = Microsoft::Diagnostics::Utils::String::AppendPath(pszPathOut, &v35);
              v22 = appended;
              if ( appended >= 0 )
              {
                *(_QWORD *)&v35 = 0;
                BYTE8(v35) = 0;
                v24 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPathOut, v38, v21);
                *(_QWORD *)v36 = Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash((Microsoft::Diagnostics::TraceSlotSafeWrapper *)&v37);
                v37 = v24;
                LOBYTE(v25) = 2;
                v26 = Microsoft::Diagnostics::TraceManager::SnapSlotTrace(
                        (_DWORD)TraceManager,
                        v25,
                        (unsigned int)&GUID_NULL,
                        (unsigned int)&GUID_NULL,
                        (__int64)v36,
                        (__int64)&v37,
                        0,
                        (__int64)&v35);
                v27 = v26;
                if ( v26 >= 0 )
                {
                  v34 = 0;
                  Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace_::_3_::_lambda_1_::operator()(&v33);
                  std::wstring::_Tidy_deallocate(pszPathOut);
                  std::wstring::_Tidy_deallocate(v41);
                  if ( v32 && RpcRevertToSelf() )
                    wil::details::in1diag3::_FailFast_Unexpected(
                      retaddr,
                      (void *)0x21E,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
                      v29);
                  return 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x6A,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                    (const char *)(unsigned int)v26,
                    v31);
                  v34 = 0;
                  Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace_::_3_::_lambda_1_::operator()(&v33);
                  std::wstring::_Tidy_deallocate(pszPathOut);
                  std::wstring::_Tidy_deallocate(v41);
                  if ( v32 && RpcRevertToSelf() )
                    wil::details::in1diag3::_FailFast_Unexpected(
                      retaddr,
                      (void *)0x21E,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
                      v28);
                  return v27;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x62,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                  (const char *)(unsigned int)appended,
                  v30);
                v34 = 0;
                Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace_::_3_::_lambda_1_::operator()(&v33);
                std::wstring::_Tidy_deallocate(pszPathOut);
                std::wstring::_Tidy_deallocate(v41);
                if ( v32 && RpcRevertToSelf() )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    (void *)0x21E,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
                    v23);
                return v22;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x61,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                (const char *)(unsigned int)v17,
                v30);
              v34 = 0;
              Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace_::_3_::_lambda_1_::operator()(&v33);
              std::wstring::_Tidy_deallocate(pszPathOut);
              std::wstring::_Tidy_deallocate(v41);
              if ( v32 && RpcRevertToSelf() )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x21E,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
                  v19);
              return v18;
            }
          }
          else
          {
            v13 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x5B,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                    (const char *)0x15,
                    v30);
            v34 = 0;
            Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace_::_3_::_lambda_1_::operator()(&v33);
            std::wstring::_Tidy_deallocate(pszPathOut);
            std::wstring::_Tidy_deallocate(v41);
            if ( v32 && RpcRevertToSelf() )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x21E,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
                v14);
            return v13;
          }
        }
        else
        {
          if ( (unsigned int)dword_1804543B0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x2000) )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_1804543B0,
              byte_1803ED011);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x44,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            (const char *)0x80070057LL,
            v30);
          std::wstring::_Tidy_deallocate(pszPathOut);
          std::wstring::_Tidy_deallocate(v41);
          if ( v32 && RpcRevertToSelf() )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x21E,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
              v9);
          return 2147942487LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)0x80070057LL,
          v30);
        std::wstring::_Tidy_deallocate(pszPathOut);
        std::wstring::_Tidy_deallocate(v41);
        if ( v32 && RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x21E,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
            v7);
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)0x80070057LL,
        v30);
      std::wstring::_Tidy_deallocate(v41);
      if ( v32 )
      {
        if ( RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x21E,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
            v5);
      }
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v30);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180296ad0  mov     rax, rsp
0x180296ad3  mov     [rax+8], rbx
0x180296ad7  mov     [rax+18h], rsi
0x180296adb  push    rdi
0x180296adc  sub     rsp, 100h
0x180296ae3  movaps  xmmword ptr [rax-18h], xmm6
0x180296ae7  mov     rax, cs:__security_cookie
0x180296aee  xor     rax, rsp
0x180296af1  mov     [rsp+108h+var_28], rax
0x180296af9  mov     rbx, rdx
0x180296afc  xor     esi, esi
0x180296afe  test    rdx, rdx
0x180296b01  jnz     short loc_180296B29
0x180296b03  mov     rcx, [rsp+108h]; this
0x180296b0b  mov     ebx, 80070057h
0x180296b10  mov     r9d, ebx; char *
0x180296b13  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180296b1a  lea     edx, [rsi+22h]; void *
0x180296b1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180296b22  mov     eax, ebx
0x180296b24  jmp     loc_1802970E8
0x180296b29  lea     rdx, [rsp+108h+var_C8]
0x180296b2e  call    ?ImpersonateRpcCaller@UtcApiManager@Diagnostics@Microsoft@@AEAA@XZ; Microsoft::Diagnostics::UtcApiManager::ImpersonateRpcCaller(void)
0x180296b33  nop
0x180296b34  mov     rdx, rbx
0x180296b37  lea     rcx, [rsp+108h+var_48]
0x180296b3f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180296b44  nop
0x180296b45  lea     rcx, [rsp+108h+var_48]
0x180296b4d  cmp     [rsp+108h+var_30], 7
0x180296b56  cmova   rcx, [rsp+108h+var_48]
0x180296b5f  mov     r9d, 2Fh ; '/'
0x180296b65  xor     r8d, r8d
0x180296b68  mov     rdx, [rsp+108h+var_38]
0x180296b70  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x180296b75  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180296b79  jz      short loc_180296BCC
0x180296b7b  mov     rcx, [rsp+108h]; this
0x180296b83  mov     ebx, 80070057h
0x180296b88  mov     r9d, ebx; char *
0x180296b8b  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180296b92  mov     edx, 2Eh ; '.'; void *
0x180296b97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180296b9c  nop
0x180296b9d  lea     rcx, [rsp+108h+var_48]
0x180296ba5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296baa  nop
0x180296bab  cmp     [rsp+108h+var_C8+1], sil
0x180296bb0  jz      short loc_180296BC5
0x180296bb2  mov     [rsp+108h+var_C8+1], sil
0x180296bb7  call    cs:__imp_RpcRevertToSelf
0x180296bbd  test    eax, eax
0x180296bbf  jnz     loc_180297112
0x180296bc5  mov     eax, ebx
0x180296bc7  jmp     loc_1802970E8
0x180296bcc  xor     r8d, r8d
0x180296bcf  mov     rdx, [rsp+108h+var_38]
0x180296bd7  lea     rcx, [rsp+108h+pszPathOut]
0x180296bdf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x180296be4  nop
0x180296be5  mov     rdx, [rsp+108h+var_58]
0x180296bed  lea     rcx, [rsp+108h+pszPathOut]
0x180296bf5  cmp     [rsp+108h+var_50], 7
0x180296bfe  cmova   rcx, [rsp+108h+pszPathOut]; pszPathOut
0x180296c07  inc     rdx; cchPathOut
0x180296c0a  mov     r9d, 1; dwFlags
0x180296c10  mov     r8, rbx; pszPathIn
0x180296c13  call    cs:__imp_PathCchCanonicalizeEx
0x180296c19  test    eax, eax
0x180296c1b  jns     short loc_180296C7C
0x180296c1d  mov     rcx, [rsp+108h]; this
0x180296c25  mov     ebx, 80070057h
0x180296c2a  mov     r9d, ebx; char *
0x180296c2d  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180296c34  mov     edx, 35h ; '5'; void *
0x180296c39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180296c3e  nop
0x180296c3f  lea     rcx, [rsp+108h+pszPathOut]
0x180296c47  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296c4c  nop
0x180296c4d  lea     rcx, [rsp+108h+var_48]
0x180296c55  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296c5a  nop
0x180296c5b  cmp     [rsp+108h+var_C8+1], sil
0x180296c60  jz      short loc_180296C75
0x180296c62  mov     [rsp+108h+var_C8+1], sil
0x180296c67  call    cs:__imp_RpcRevertToSelf
0x180296c6d  test    eax, eax
0x180296c6f  jnz     loc_18029712C
0x180296c75  mov     eax, ebx
0x180296c77  jmp     loc_1802970E8
0x180296c7c  xor     r8d, r8d
0x180296c7f  mov     dl, 1
0x180296c81  lea     rcx, [rsp+108h+pszPathOut]; lpSrc
0x180296c89  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180296c8e  lea     rcx, [rsp+108h+pszPathOut]
0x180296c96  cmp     [rsp+108h+var_50], 7
0x180296c9f  cmova   rcx, [rsp+108h+pszPathOut]; lpFileName
0x180296ca8  call    cs:__imp_GetFileAttributesW
0x180296cae  cmp     eax, 0FFFFFFFFh
0x180296cb1  mov     eax, cs:dword_1804543B0
0x180296cb7  jz      loc_180296D49
0x180296cbd  cmp     eax, 3
0x180296cc0  jbe     short loc_180296CEA
0x180296cc2  mov     edx, 2000h
0x180296cc7  lea     rcx, dword_1804543B0
0x180296cce  call    _tlgKeywordOn
0x180296cd3  test    al, al
0x180296cd5  jz      short loc_180296CEA
0x180296cd7  lea     rdx, byte_1803ED011
0x180296cde  lea     rcx, dword_1804543B0
0x180296ce5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180296cea  mov     rcx, [rsp+108h]; this
0x180296cf2  mov     ebx, 80070057h
0x180296cf7  mov     r9d, ebx; char *
0x180296cfa  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180296d01  mov     edx, 44h ; 'D'; void *
0x180296d06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180296d0b  nop
0x180296d0c  lea     rcx, [rsp+108h+pszPathOut]
0x180296d14  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296d19  nop
0x180296d1a  lea     rcx, [rsp+108h+var_48]
0x180296d22  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296d27  nop
0x180296d28  cmp     [rsp+108h+var_C8+1], sil
0x180296d2d  jz      short loc_180296D42
0x180296d2f  mov     [rsp+108h+var_C8+1], sil
0x180296d34  call    cs:__imp_RpcRevertToSelf
0x180296d3a  test    eax, eax
0x180296d3c  jnz     loc_180297146
0x180296d42  mov     eax, ebx
0x180296d44  jmp     loc_1802970E8
0x180296d49  cmp     eax, 4
0x180296d4c  jbe     short loc_180296D9F
0x180296d4e  mov     edx, 2000h
0x180296d53  lea     rcx, dword_1804543B0
0x180296d5a  call    _tlgKeywordOn
0x180296d5f  test    al, al
0x180296d61  jz      short loc_180296D9F
0x180296d63  lea     rax, [rsp+108h+pszPathOut]
0x180296d6b  cmp     [rsp+108h+var_50], 7
0x180296d74  cmova   rax, [rsp+108h+pszPathOut]
0x180296d7d  mov     qword ptr [rsp+108h+var_98], rax
0x180296d82  lea     rax, [rsp+108h+var_98]
0x180296d87  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180296d8c  lea     rdx, byte_1803ED059
0x180296d93  lea     rcx, dword_1804543B0
0x180296d9a  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180296d9f  lea     rax, [rsp+108h+pszPathOut]
0x180296da7  mov     [rsp+108h+var_C0], rax
0x180296dac  mov     [rsp+108h+var_B8], 1
0x180296db1  mov     rcx, rsi
0x180296db4  xor     eax, eax
0x180296db6  lock cmpxchg qword ptr cs:xmmword_1804631A0, rcx
0x180296dbf  jnz     short loc_180296E35
0x180296dc1  mov     rcx, [rsp+108h]; this
0x180296dc9  mov     r9d, 15h; char *
0x180296dcf  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180296dd6  lea     edx, [r9+46h]; void *
0x180296dda  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180296ddf  mov     ebx, eax
0x180296de1  cmp     [rsp+108h+var_B8], sil
0x180296de6  jz      short loc_180296DF8
0x180296de8  mov     [rsp+108h+var_B8], sil
0x180296ded  lea     rcx, [rsp+108h+var_C0]
0x180296df2  call    _Microsoft__Diagnostics__UtcApiManager__SnapMiniTrace____3____lambda_1___operator__
0x180296df7  nop
0x180296df8  lea     rcx, [rsp+108h+pszPathOut]
0x180296e00  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296e05  nop
0x180296e06  lea     rcx, [rsp+108h+var_48]
0x180296e0e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296e13  nop
0x180296e14  cmp     [rsp+108h+var_C8+1], sil
0x180296e19  jz      short loc_180296E2E
0x180296e1b  mov     [rsp+108h+var_C8+1], sil
0x180296e20  call    cs:__imp_RpcRevertToSelf
0x180296e26  test    eax, eax
0x180296e28  jnz     loc_180297160
0x180296e2e  mov     eax, ebx
0x180296e30  jmp     loc_1802970E8
0x180296e35  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180296e3c  call    ?GetTraceManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTraceManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTraceManager(void)
0x180296e41  mov     rdi, rax
0x180296e44  mov     rcx, [rax+20h]
0x180296e48  mov     qword ptr [rsp+108h+var_88], rcx
0x180296e50  lea     rcx, [rax+110h]
0x180296e57  mov     qword ptr [rsp+108h+var_88+8], rcx
0x180296e5f  movups  xmm0, xmmword ptr cs:off_18036C4E8; "O:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;S-1"...
0x180296e66  movdqu  [rsp+108h+var_A8], xmm0
0x180296e6c  lea     rdx, [rsp+108h+var_78]
0x180296e74  lea     rcx, [rsp+108h+pszPathOut]
0x180296e7c  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180296e81  movups  xmm0, xmmword ptr [rax]
0x180296e84  movdqu  xmmword ptr [rsp+108h+var_98], xmm0
0x180296e8a  lea     r8, [rsp+108h+var_A8]
0x180296e8f  xor     edx, edx
0x180296e91  lea     rcx, [rsp+108h+var_98]
0x180296e96  call    ?ExpandAndCreateDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N0@Z; Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(std::wstring_view,bool,std::wstring_view)
0x180296e9b  mov     ebx, eax
0x180296e9d  test    eax, eax
0x180296e9f  jns     short loc_180296F12
0x180296ea1  mov     rcx, [rsp+108h]; this
0x180296ea9  mov     r9d, eax; char *
0x180296eac  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180296eb3  mov     edx, 61h ; 'a'; void *
0x180296eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180296ebd  nop
0x180296ebe  cmp     [rsp+108h+var_B8], sil
0x180296ec3  jz      short loc_180296ED5
0x180296ec5  mov     [rsp+108h+var_B8], sil
0x180296eca  lea     rcx, [rsp+108h+var_C0]
0x180296ecf  call    _Microsoft__Diagnostics__UtcApiManager__SnapMiniTrace____3____lambda_1___operator__
0x180296ed4  nop
0x180296ed5  lea     rcx, [rsp+108h+pszPathOut]
0x180296edd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296ee2  nop
0x180296ee3  lea     rcx, [rsp+108h+var_48]
0x180296eeb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296ef0  nop
0x180296ef1  cmp     [rsp+108h+var_C8+1], sil
0x180296ef6  jz      short loc_180296F0B
0x180296ef8  mov     [rsp+108h+var_C8+1], sil
0x180296efd  call    cs:__imp_RpcRevertToSelf
0x180296f03  test    eax, eax
0x180296f05  jnz     loc_18029717A
0x180296f0b  mov     eax, ebx
0x180296f0d  jmp     loc_1802970E8
0x180296f12  movaps  xmm0, xmmword ptr cs:?k_traceSlotOutputNames@TraceSlot@Diagnostics@Microsoft@@2QBV?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const near * const Microsoft::Diagnostics::TraceSlot::k_traceSlotOutputNames
0x180296f19  movdqu  [rsp+108h+var_A8], xmm0
0x180296f1f  lea     rdx, [rsp+108h+var_A8]
0x180296f24  lea     rcx, [rsp+108h+pszPathOut]
0x180296f2c  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x180296f31  mov     ebx, eax
0x180296f33  test    eax, eax
0x180296f35  jns     short loc_180296FA8
0x180296f37  mov     rcx, [rsp+108h]; this
0x180296f3f  mov     r9d, eax; char *
0x180296f42  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180296f49  mov     edx, 62h ; 'b'; void *
0x180296f4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180296f53  nop
0x180296f54  cmp     [rsp+108h+var_B8], sil
0x180296f59  jz      short loc_180296F6B
0x180296f5b  mov     [rsp+108h+var_B8], sil
0x180296f60  lea     rcx, [rsp+108h+var_C0]
0x180296f65  call    _Microsoft__Diagnostics__UtcApiManager__SnapMiniTrace____3____lambda_1___operator__
0x180296f6a  nop
0x180296f6b  lea     rcx, [rsp+108h+pszPathOut]
0x180296f73  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296f78  nop
0x180296f79  lea     rcx, [rsp+108h+var_48]
0x180296f81  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296f86  nop
0x180296f87  cmp     [rsp+108h+var_C8+1], sil
0x180296f8c  jz      short loc_180296FA1
0x180296f8e  mov     [rsp+108h+var_C8+1], sil
0x180296f93  call    cs:__imp_RpcRevertToSelf
0x180296f99  test    eax, eax
0x180296f9b  jnz     loc_180297194
0x180296fa1  mov     eax, ebx
0x180296fa3  jmp     loc_1802970E8
0x180296fa8  mov     qword ptr [rsp+108h+var_A8], rsi
0x180296fad  mov     byte ptr [rsp+108h+var_A8+8], sil
0x180296fb2  lea     rdx, [rsp+108h+var_78]
0x180296fba  lea     rcx, [rsp+108h+pszPathOut]
0x180296fc2  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180296fc7  movups  xmm6, xmmword ptr [rax]
0x180296fca  lea     rcx, [rsp+108h+var_88]; this
0x180296fd2  call    ?GetOwnerTraceProfileHash@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA_KXZ; Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash(void)
0x180296fd7  mov     qword ptr [rsp+108h+var_98], rax
0x180296fdc  movdqu  [rsp+108h+var_88], xmm6
0x180296fe5  lea     rax, [rsp+108h+var_A8]
0x180296fea  mov     [rsp+108h+var_D0], rax
0x180296fef  mov     [rsp+108h+var_D8], rsi
0x180296ff4  lea     rax, [rsp+108h+var_88]
0x180296ffc  mov     [rsp+108h+var_E0], rax
0x180297001  lea     rax, [rsp+108h+var_98]
0x180297006  mov     qword ptr [rsp+108h+var_E8], rax; int
0x18029700b  lea     r8, GUID_NULL
0x180297012  mov     r9, r8
0x180297015  mov     dl, 2
0x180297017  mov     rcx, rdi
0x18029701a  call    ?SnapSlotTrace@TraceManager@Diagnostics@Microsoft@@QEAAJVTraceSlotType@23@AEBU_GUID@@1AEB_KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_KAEBUSnapTraceMetadata@23@@Z; Microsoft::Diagnostics::TraceManager::SnapSlotTrace(Microsoft::Diagnostics::TraceSlotType,_GUID const &,_GUID const &,unsigned __int64 const &,std::wstring_view,unsigned __int64,Microsoft::Diagnostics::SnapTraceMetadata const &)
0x18029701f  mov     ebx, eax
0x180297021  test    eax, eax
0x180297023  jns     short loc_180297093
0x180297025  mov     rcx, [rsp+108h]; this
0x18029702d  mov     r9d, eax; char *
0x180297030  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180297037  mov     edx, 6Ah ; 'j'; void *
0x18029703c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180297041  nop
0x180297042  cmp     [rsp+108h+var_B8], sil
0x180297047  jz      short loc_180297059
0x180297049  mov     [rsp+108h+var_B8], sil
0x18029704e  lea     rcx, [rsp+108h+var_C0]
0x180297053  call    _Microsoft__Diagnostics__UtcApiManager__SnapMiniTrace____3____lambda_1___operator__
0x180297058  nop
  ... truncated ...
```
