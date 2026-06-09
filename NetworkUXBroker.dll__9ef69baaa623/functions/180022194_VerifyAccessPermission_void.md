# VerifyAccessPermission(void)

- ea: `0x180022194`
- end: `0x180022490`
- name: `?VerifyAccessPermission@@YAJXZ`
- size: `764`
- prototype: `__int64 __fastcall(CallerIdentity *, __int64, bool *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001b5c0`

## callees

- `0x180002a28`
- `0x1800033d6`
- `0x18000e768`
- `0x180011c34`
- `0x18001916c`
- `0x18001ab7c`
- `0x18001d88c`
- `0x180021d6c`
- `0x180022194`
- `0x180022498`
- `0x18003ae70`
- `0x18003af3c`
- `0x18003b27c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022271`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022271`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002225f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002225f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022237`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022237`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022221`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022221`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800223f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800223f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002227b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002227b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800222d1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800222d1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800221fe`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800221fe`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002245a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002245a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002238d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002238d`

## string_xrefs

- `0x1800222df`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180022302`: `onecoreuap\net\ux\uxmanager\lib\accesscheck.cpp`
- `0x180022347`: `onecoreuap\net\ux\uxmanager\lib\accesscheck.cpp`
- `0x18002239b`: `onecoreuap\net\ux\uxmanager\lib\accesscheck.cpp`
- `0x18002241f`: `onecoreuap\net\ux\uxmanager\lib\accesscheck.cpp`
- `0x180022470`: `onecoreuap\net\ux\uxmanager\lib\accesscheck.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VerifyAccessPermission(CallerIdentity *a1, __int64 a2, bool *a3)
{
  unsigned __int16 **v3; // rdx
  const unsigned __int16 *v4; // rdx
  signed int CallingProcessAppId; // ebx
  HRESULT v6; // eax
  unsigned int v7; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v11; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rcx
  const char *v15; // r9
  int v16; // eax
  int token_information; // eax
  void *v18; // rbx
  const char *v19; // r9
  unsigned int v20; // edi
  unsigned int i; // edi
  int ReturnLength; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPVOID pv; // [rsp+50h] [rbp+20h] BYREF
  DWORD v26; // [rsp+58h] [rbp+28h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  LOBYTE(pv) = 0;
  if ( CallerIdentity::CheckCallerCapability(a1, (const unsigned __int16 *)&pv, a3) < 0 || !(_BYTE)pv )
  {
    pv = 0;
    CoTaskMemFree_0(0);
    CallingProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&pv, v3);
    if ( CallingProcessAppId >= 0 )
      CallingProcessAppId = !CallerIdentity::IsShellExperienceAppId((LPCWCH)pv, v4) ? 0x80070005 : 0;
    CoTaskMemFree_0(pv);
    if ( CallingProcessAppId < 0 )
    {
      v6 = CoImpersonateClient();
      v7 = v6;
      if ( v6 >= 0 )
      {
        TokenHandle = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &TokenHandle,
          0);
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
          goto LABEL_16;
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 == -2147023888 )
        {
          CurrentProcess = GetCurrentProcess();
          if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
            goto LABEL_16;
          v11 = GetLastError();
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
        }
        if ( (v7 & 0x80000000) != 0 )
        {
          v12 = v7;
          v13 = 52;
LABEL_21:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v13,
            (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\accesscheck.cpp",
            (const char *)v12,
            ReturnLength);
LABEL_42:
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          CoRevertToSelf();
          return v7;
        }
LABEL_16:
        LODWORD(pv) = 0;
        v26 = 0;
        v14 = -6;
        if ( TokenHandle )
          v14 = (__int64)TokenHandle;
        if ( GetTokenInformation((HANDLE)v14, TokenIsAppContainer, &pv, 4u, &v26) )
        {
          if ( (_DWORD)pv )
          {
            StringSid = 0;
            pv = 0;
            token_information = wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(&pv, TokenHandle);
            v7 = token_information;
            if ( token_information >= 0 )
            {
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &StringSid,
                0);
              v18 = pv;
              if ( ConvertSidToStringSidW(*(PSID *)pv, &StringSid) )
              {
                for ( i = 0; i < 0x15; ++i )
                {
                  if ( CompareStringOrdinal(StringSid, -1, off_18004C5B0[i], -1, 1) == 2 )
                  {
                    if ( v18 )
                      operator delete(v18);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&StringSid);
                    goto LABEL_23;
                  }
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x4C,
                  (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\accesscheck.cpp",
                  (const char *)0x80070005LL,
                  ReturnLength);
                if ( v18 )
                  operator delete(v18);
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&StringSid);
                v7 = -2147024891;
              }
              else
              {
                v20 = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x42,
                        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\accesscheck.cpp",
                        v19);
                if ( v18 )
                  operator delete(v18);
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&StringSid);
                v7 = v20;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x41,
                (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\accesscheck.cpp",
                (const char *)(unsigned int)token_information,
                ReturnLength);
              if ( pv )
                operator delete(pv);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&StringSid);
            }
            goto LABEL_42;
          }
        }
        else
        {
          v16 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x298,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v15);
          v7 = v16;
          if ( v16 < 0 )
          {
            v12 = (unsigned int)v16;
            v13 = 56;
            goto LABEL_21;
          }
        }
LABEL_23:
        v7 = 0;
        goto LABEL_42;
      }
      if ( v6 != -2147417833 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x55,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\accesscheck.cpp",
          (const char *)(unsigned int)v6,
          ReturnLength);
        return v7;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180022194  push    rbp
0x180022196  push    rbx
0x180022197  push    rdi
0x180022198  mov     rbp, rsp
0x18002219b  sub     rsp, 30h
0x18002219f  lea     rdx, [rbp+pv]; unsigned __int16 *
0x1800221a3  mov     byte ptr [rbp+pv], 0
0x1800221a7  call    ?CheckCallerCapability@CallerIdentity@@YAJPEBGPEA_N@Z; CallerIdentity::CheckCallerCapability(ushort const *,bool *)
0x1800221ac  test    eax, eax
0x1800221ae  js      short loc_1800221BA
0x1800221b0  cmp     byte ptr [rbp+pv], 0
0x1800221b4  jnz     loc_180022486
0x1800221ba  xor     ecx, ecx; pv
0x1800221bc  mov     [rbp+pv], 0
0x1800221c4  call    CoTaskMemFree_0
0x1800221c9  lea     rcx, [rbp+pv]; this
0x1800221cd  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x1800221d2  mov     ebx, eax
0x1800221d4  test    eax, eax
0x1800221d6  js      short loc_1800221ED
0x1800221d8  mov     rcx, [rbp+pv]; lpString2
0x1800221dc  call    ?IsShellExperienceAppId@CallerIdentity@@YA_NPEBG@Z; CallerIdentity::IsShellExperienceAppId(ushort const *)
0x1800221e1  neg     al
0x1800221e3  sbb     ebx, ebx
0x1800221e5  not     ebx
0x1800221e7  and     ebx, 80070005h
0x1800221ed  mov     rcx, [rbp+pv]; pv
0x1800221f1  call    CoTaskMemFree_0
0x1800221f6  test    ebx, ebx
0x1800221f8  jns     loc_180022486
0x1800221fe  call    cs:__imp_CoImpersonateClient
0x180022204  mov     ebx, eax
0x180022206  test    eax, eax
0x180022208  js      loc_180022464
0x18002220e  xor     edx, edx
0x180022210  mov     [rbp+TokenHandle], 0
0x180022218  lea     rcx, [rbp+TokenHandle]
0x18002221c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180022221  call    cs:__imp_GetCurrentThread
0x180022227  mov     edx, 8; DesiredAccess
0x18002222c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180022230  mov     rcx, rax; ThreadHandle
0x180022233  lea     r8d, [rdx-7]; OpenAsSelf
0x180022237  call    cs:__imp_OpenThreadToken
0x18002223d  test    eax, eax
0x18002223f  jnz     short loc_18002229A
0x180022241  call    cs:__imp_GetLastError
0x180022247  mov     ebx, eax
0x180022249  mov     edi, 80070000h
0x18002224e  test    eax, eax
0x180022250  jle     short loc_180022257
0x180022252  movzx   ebx, ax
0x180022255  or      ebx, edi
0x180022257  cmp     ebx, 800703F0h
0x18002225d  jnz     short loc_18002228C
0x18002225f  call    cs:__imp_GetCurrentProcess
0x180022265  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180022269  mov     edx, 8; DesiredAccess
0x18002226e  mov     rcx, rax; ProcessHandle
0x180022271  call    cs:__imp_OpenProcessToken
0x180022277  test    eax, eax
0x180022279  jnz     short loc_18002229A
0x18002227b  call    cs:__imp_GetLastError
0x180022281  mov     ebx, eax
0x180022283  test    eax, eax
0x180022285  jle     short loc_18002228C
0x180022287  movzx   ebx, ax
0x18002228a  or      ebx, edi
0x18002228c  test    ebx, ebx
0x18002228e  jns     short loc_18002229A
0x180022290  mov     r9d, ebx
0x180022293  mov     edx, 34h ; '4'
0x180022298  jmp     short loc_1800222FE
0x18002229a  mov     rax, [rbp+TokenHandle]
0x18002229e  lea     r8, [rbp+pv]; TokenInformation
0x1800222a2  test    rax, rax
0x1800222a5  mov     dword ptr [rbp+pv], 0
0x1800222ac  mov     r9d, 4; TokenInformationLength
0x1800222b2  mov     [rbp+arg_8], 0
0x1800222b9  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x1800222c0  cmovnz  rcx, rax; TokenHandle
0x1800222c4  lea     rax, [rbp+arg_8]
0x1800222c8  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x1800222cd  lea     edx, [r9+19h]; TokenInformationClass
0x1800222d1  call    cs:__imp_GetTokenInformation
0x1800222d7  test    eax, eax
0x1800222d9  jnz     short loc_180022313
0x1800222db  mov     rcx, [rbp+18h]; this
0x1800222df  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800222e6  mov     edx, 298h; void *
0x1800222eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800222f0  mov     ebx, eax
0x1800222f2  test    eax, eax
0x1800222f4  jns     short loc_180022319
0x1800222f6  mov     r9d, eax; char *
0x1800222f9  mov     edx, 38h ; '8'; void *
0x1800222fe  mov     rcx, [rbp+18h]; this
0x180022302  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\uxmanager\\lib\\ac"...
0x180022309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002230e  jmp     loc_180022451
0x180022313  cmp     dword ptr [rbp+pv], 0
0x180022317  jnz     short loc_180022320
0x180022319  xor     ebx, ebx
0x18002231b  jmp     loc_180022451
0x180022320  mov     rdx, [rbp+TokenHandle]
0x180022324  lea     rcx, [rbp+pv]
0x180022328  mov     [rbp+StringSid], 0
0x180022330  mov     [rbp+pv], 0
0x180022338  call    ??$get_token_information_nothrow@U_TOKEN_APPCONTAINER_INFORMATION@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_APPCONTAINER_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(wistd::unique_ptr<_TOKEN_APPCONTAINER_INFORMATION,wil::details::token_info_deleter> &,void *)
0x18002233d  mov     ebx, eax
0x18002233f  test    eax, eax
0x180022341  jns     short loc_180022377
0x180022343  mov     rcx, [rbp+18h]; this
0x180022347  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\uxmanager\\lib\\ac"...
0x18002234e  mov     r9d, eax; char *
0x180022351  mov     edx, 41h ; 'A'; void *
0x180022356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002235b  mov     rcx, [rbp+pv]; Block
0x18002235f  test    rcx, rcx
0x180022362  jz      short loc_180022369
0x180022364  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022369  lea     rcx, [rbp+StringSid]
0x18002236d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022372  jmp     loc_180022451
0x180022377  xor     edx, edx
0x180022379  lea     rcx, [rbp+StringSid]
0x18002237d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180022382  mov     rbx, [rbp+pv]
0x180022386  lea     rdx, [rbp+StringSid]; StringSid
0x18002238a  mov     rcx, [rbx]; Sid
0x18002238d  call    cs:__imp_ConvertSidToStringSidW
0x180022393  test    eax, eax
0x180022395  jnz     short loc_1800223C9
0x180022397  mov     rcx, [rbp+18h]; this
0x18002239b  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\uxmanager\\lib\\ac"...
0x1800223a2  lea     edx, [rax+42h]; void *
0x1800223a5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800223aa  mov     edi, eax
0x1800223ac  test    rbx, rbx
0x1800223af  jz      short loc_1800223B9
0x1800223b1  mov     rcx, rbx; Block
0x1800223b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800223b9  lea     rcx, [rbp+StringSid]
0x1800223bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800223c2  mov     ebx, edi
0x1800223c4  jmp     loc_180022451
0x1800223c9  xor     edi, edi
0x1800223cb  cmp     edi, 15h
0x1800223ce  jnb     short loc_18002241B
0x1800223d0  mov     rcx, [rbp+StringSid]; lpString1
0x1800223d4  lea     rax, off_18004C5B0; "S-1-15-2-155514346-2573954481-755741238"...
0x1800223db  or      r9d, 0FFFFFFFFh; cchCount2
0x1800223df  movsxd  r8, edi
0x1800223e2  or      edx, r9d; cchCount1
0x1800223e5  mov     [rsp+30h+ReturnLength], 1; bIgnoreCase
0x1800223ed  mov     r8, [rax+r8*8]; lpString2
0x1800223f1  call    cs:__imp_CompareStringOrdinal
0x1800223f7  cmp     eax, 2
0x1800223fa  jz      short loc_180022400
0x1800223fc  inc     edi
0x1800223fe  jmp     short loc_1800223CB
0x180022400  test    rbx, rbx
0x180022403  jz      short loc_18002240D
0x180022405  mov     rcx, rbx; Block
0x180022408  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002240d  lea     rcx, [rbp+StringSid]
0x180022411  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022416  jmp     loc_180022319
0x18002241b  mov     rcx, [rbp+18h]; this
0x18002241f  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\uxmanager\\lib\\ac"...
0x180022426  mov     r9d, 80070005h; char *
0x18002242c  mov     edx, 4Ch ; 'L'; void *
0x180022431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022436  test    rbx, rbx
0x180022439  jz      short loc_180022443
0x18002243b  mov     rcx, rbx; Block
0x18002243e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022443  lea     rcx, [rbp+StringSid]
0x180022447  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002244c  mov     ebx, 80070005h
0x180022451  lea     rcx, [rbp+TokenHandle]
0x180022455  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002245a  call    cs:__imp_CoRevertToSelf
0x180022460  mov     eax, ebx
0x180022462  jmp     short loc_180022488
0x180022464  cmp     ebx, 80010117h
0x18002246a  jz      short loc_180022486
0x18002246c  mov     rcx, [rbp+18h]; this
0x180022470  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\uxmanager\\lib\\ac"...
0x180022477  mov     r9d, ebx; char *
0x18002247a  mov     edx, 55h ; 'U'; void *
0x18002247f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022484  jmp     short loc_180022460
0x180022486  xor     eax, eax
0x180022488  add     rsp, 30h
0x18002248c  pop     rdi
0x18002248d  pop     rbx
0x18002248e  pop     rbp
0x18002248f  retn
```
