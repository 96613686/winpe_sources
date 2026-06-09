# Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateGlobalPrompt(Windows::Internal::CapabilityAccess::Private::GlobalPrompt,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue &)

- ea: `0x18006c2bc`
- end: `0x18006c6ee`
- name: `?CreateGlobalPrompt@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAAJW4GlobalPrompt@2345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111AEAW4CapabilityConsentValue@2345@@Z`
- size: `1074`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, Windows::Internal::CapabilityAccess::Private *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800679b8`
- `0x18006cbe4`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x180017bc4`
- `0x18001c3b4`
- `0x1800210d4`
- `0x1800257a4`
- `0x180028188`
- `0x180029408`
- `0x18003fd60`
- `0x18004f644`
- `0x180065408`
- `0x18006c2bc`
- `0x180070824`
- `0x180071bd8`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x18006c36a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x18006c36a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006c39f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006c39f`

## string_xrefs

- `0x18006c37f`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c3b4`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c6db`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateGlobalPrompt(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        Windows::Internal::CapabilityAccess::Private *a7)
{
  __int64 v11; // r13
  __int64 v12; // rax
  int v13; // eax
  const char *v14; // r9
  int v15; // eax
  unsigned int v16; // ebx
  const enum Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue *v17; // rdx
  const unsigned __int16 *v18; // rax
  const enum Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue *v19; // rdx
  const unsigned __int16 *v20; // rax
  int v21; // esi
  int v22; // r12d
  int v23; // edi
  int v24; // eax
  __int64 v25; // rbx
  const enum Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue *v26; // rdx
  __int64 v27; // rax
  int v28; // ecx
  int v29; // r8d
  __int64 v30; // r9
  __int64 v31; // r10
  int v32; // r11d
  __int64 v34; // r14
  char v35; // r13
  const unsigned __int16 *v36; // rax
  const enum Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue *v37; // rdx
  const unsigned __int16 *v38; // rax
  __int64 v39; // r12
  int v40; // ebx
  int v41; // r15d
  int v42; // esi
  int v43; // edi
  wil *v44; // rcx
  int v45; // eax
  wil *v46; // rcx
  __int64 v47; // rsi
  __int64 v48; // rdi
  __int64 v49; // rbx
  wil *v50; // rcx
  const enum Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue *v51; // rdx
  unsigned int v52; // eax
  __int64 v53; // r8
  int v54; // r9d
  char v55; // r10
  wil *v56; // rcx
  __int64 v57; // [rsp+0h] [rbp-248h] BYREF
  __int64 v58; // [rsp+20h] [rbp-228h]
  bool v59; // [rsp+70h] [rbp-1D8h]
  unsigned int v60; // [rsp+74h] [rbp-1D4h]
  __int64 v61; // [rsp+78h] [rbp-1D0h] BYREF
  __int64 v62; // [rsp+80h] [rbp-1C8h] BYREF
  __int64 v63; // [rsp+88h] [rbp-1C0h]
  __int64 v64; // [rsp+90h] [rbp-1B8h]
  __int64 v65; // [rsp+98h] [rbp-1B0h]
  Windows::Internal::CapabilityAccess::Private *v66; // [rsp+A0h] [rbp-1A8h]
  __int64 v67; // [rsp+A8h] [rbp-1A0h]
  __int64 v68; // [rsp+B0h] [rbp-198h]
  __int64 v69; // [rsp+B8h] [rbp-190h]
  __int64 v70; // [rsp+C0h] [rbp-188h]
  __int64 v71; // [rsp+C8h] [rbp-180h]
  __int64 v72; // [rsp+D0h] [rbp-178h]
  _BYTE *v73; // [rsp+D8h] [rbp-170h]
  _BYTE *v74; // [rsp+E0h] [rbp-168h]
  _BYTE *v75; // [rsp+E8h] [rbp-160h]
  _BYTE *v76; // [rsp+F0h] [rbp-158h]
  _BYTE *v77; // [rsp+F8h] [rbp-150h]
  _BYTE *v78; // [rsp+100h] [rbp-148h]
  _BYTE v79[32]; // [rsp+108h] [rbp-140h] BYREF
  _BYTE v80[32]; // [rsp+128h] [rbp-120h] BYREF
  _BYTE v81[32]; // [rsp+148h] [rbp-100h] BYREF
  _BYTE v82[32]; // [rsp+168h] [rbp-E0h] BYREF
  _BYTE v83[32]; // [rsp+188h] [rbp-C0h] BYREF
  _BYTE v84[32]; // [rsp+1A8h] [rbp-A0h] BYREF
  _OWORD v85[2]; // [rsp+1C8h] [rbp-80h] BYREF
  _BYTE v86[32]; // [rsp+1E8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v63 = a4;
  v64 = a1;
  v65 = a4;
  v70 = a5;
  v72 = a5;
  v69 = a6;
  v71 = a6;
  v66 = a7;
  v62 = 0;
  v11 = a1 + 392;
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 392);
  v13 = UMgrQueryUserContextFromSid(v12, &v62);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xEC3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
      (const char *)(unsigned int)v13,
      v58);
    v15 = UMgrQueryUserContext(*(_QWORD *)(a1 + 448), &v62);
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xEC5,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)(unsigned int)v15,
        v58);
      v62 = 0;
    }
  }
  switch ( a2 )
  {
    case 4:
      v16 = 13;
      break;
    case 3:
      v16 = 12;
      break;
    case 2:
      v16 = 11;
      break;
    case 1:
      v16 = 10;
      break;
    default:
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xEDF,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        v14);
  }
  v60 = v16;
  std::operator+<unsigned short>(v86, a1 + 296);
  try
  {
    v85[0] = 0;
    v85[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v85[0]) = 0;
    *(_DWORD *)a7 = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::RequestConsentFromUser(
                      a1,
                      v62,
                      (unsigned int)v85,
                      0,
                      a3,
                      v16);
    std::wstring::_Tidy_deallocate(v85);
    Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::QueryUserConsentStoreCreatedCount(v85, v11);
    v59 = *(_BYTE *)(a1 + 29);
    v73 = v79;
    v18 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(a7, v17);
    v67 = std::wstring::wstring(v79, v18);
    v74 = v80;
    LODWORD(v61) = 2;
    v20 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(
            (Windows::Internal::CapabilityAccess::Private *)&v61,
            v19);
    v61 = std::wstring::wstring(v80, v20);
    v21 = 2 - (*(_BYTE *)(a1 + 36) != 0);
    v75 = v81;
    v68 = std::wstring::wstring(v81, a4);
    v76 = v82;
    v22 = std::wstring::wstring(v82, a1 + 264);
    v77 = v83;
    v23 = std::wstring::wstring(v83, a1 + 296);
    v24 = std::wstring::wstring(v84, v11);
    LogPromptAttempted(
      0,
      v24,
      v23,
      v22,
      v68,
      v21,
      v61,
      v67,
      v59,
      1,
      v16,
      0,
      DWORD2(v85[0]),
      *(unsigned __int64 *)&v85[0]);
    if ( (Microsoft_Windows_Privacy_AuditingEnableBits & 0x10) != 0 )
    {
      v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v70);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
      Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(a7, v26);
      v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v86);
      McTemplateU0zzzzdztzz_EventWriteTransfer(
        v28,
        (unsigned int)PromptAnsweredSuccessEvent,
        v29,
        v32,
        (__int64)&Format,
        v31,
        0,
        v27,
        0,
        v30,
        v25);
    }
  }
  catch ( wil::ResultException )
  {
    v34 = v64;
    v35 = *(_BYTE *)(v64 + 29);
    v78 = v84;
    v36 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(
            v66,
            (const enum Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue *)&v57);
    v64 = std::wstring::wstring(v84, v36);
    v77 = v83;
    LODWORD(v61) = 2;
    v38 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(
            (Windows::Internal::CapabilityAccess::Private *)&v61,
            v37);
    v39 = std::wstring::wstring(v83, v38);
    v40 = 2 - (*(_BYTE *)(v34 + 36) != 0);
    v76 = v82;
    v63 = std::wstring::wstring(v82, v65);
    v75 = v81;
    v41 = std::wstring::wstring(v81, v34 + 264);
    v74 = v80;
    v42 = std::wstring::wstring(v80, v34 + 296);
    v43 = std::wstring::wstring(v79, v34 + 392);
    v45 = wil::ResultFromCaughtException(v44);
    LogPromptAttempted(v45, v43, v42, v41, v63, v40, v39, v64, v35, 0, v60, 0, 0, 0);
    if ( (Microsoft_Windows_Privacy_AuditingEnableBits & 0x20) != 0 )
    {
      v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
      v48 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      v49 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v86);
      wil::ResultFromCaughtException(v50);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34 + 392);
      v52 = (unsigned int)Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(v66, v51);
      McTemplateU0zzzzdztzz_EventWriteTransfer(
        (unsigned int)&Format,
        (unsigned int)PromptAnsweredFailureEvent,
        v52,
        v54,
        (__int64)&Format,
        v53,
        v55,
        v49,
        0,
        v48,
        v47);
    }
    if ( (unsigned int)wil::ResultFromCaughtException(v46) == -2147023673 )
      goto LABEL_16;
    LODWORD(v61) = wil::ResultFromCaughtException(v56);
    std::wstring::_Tidy_deallocate(v86);
    return (unsigned int)v61;
  }
LABEL_16:
  std::wstring::_Tidy_deallocate(v86);
  return 0;
}

```

## disassembly

```asm
0x18006c2bc  push    rbx
0x18006c2be  push    rsi
0x18006c2bf  push    rdi
0x18006c2c0  push    r12
0x18006c2c2  push    r13
0x18006c2c4  push    r14
0x18006c2c6  push    r15
0x18006c2c8  sub     rsp, 210h
0x18006c2cf  mov     rax, cs:__security_cookie
0x18006c2d6  xor     rax, rsp
0x18006c2d9  mov     [rsp+248h+var_40], rax
0x18006c2e1  mov     r12, r9
0x18006c2e4  mov     [rsp+248h+var_1C0], r9
0x18006c2ec  mov     rsi, r8
0x18006c2ef  mov     ebx, edx
0x18006c2f1  mov     rdi, rcx
0x18006c2f4  mov     [rsp+248h+var_1B8], rcx
0x18006c2fc  mov     [rsp+248h+var_1B0], r9
0x18006c304  mov     rax, [rsp+248h+arg_20]
0x18006c30c  mov     [rsp+248h+var_188], rax
0x18006c314  mov     [rsp+248h+var_178], rax
0x18006c31c  mov     rax, [rsp+248h+arg_28]
0x18006c324  mov     [rsp+248h+var_190], rax
0x18006c32c  mov     [rsp+248h+var_180], rax
0x18006c334  mov     r15, [rsp+248h+arg_30]
0x18006c33c  mov     [rsp+248h+var_1A8], r15
0x18006c344  mov     [rsp+248h+var_1C8], 0
0x18006c350  lea     r13, [rcx+188h]
0x18006c357  mov     rcx, r13
0x18006c35a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006c35f  lea     rdx, [rsp+248h+var_1C8]
0x18006c367  mov     rcx, rax
0x18006c36a  call    cs:__imp_UMgrQueryUserContextFromSid
0x18006c370  mov     rcx, [rsp+248h]; this
0x18006c378  test    eax, eax
0x18006c37a  jns     short loc_18006C3D1
0x18006c37c  mov     r9d, eax; char *
0x18006c37f  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x18006c386  mov     edx, 0EC3h; void *
0x18006c38b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c390  lea     rdx, [rsp+248h+var_1C8]
0x18006c398  mov     rcx, [rdi+1C0h]
0x18006c39f  call    cs:__imp_UMgrQueryUserContext
0x18006c3a5  mov     rcx, [rsp+248h]; this
0x18006c3ad  test    eax, eax
0x18006c3af  jns     short loc_18006C3D1
0x18006c3b1  mov     r9d, eax; char *
0x18006c3b4  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x18006c3bb  mov     edx, 0EC5h; void *
0x18006c3c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c3c5  mov     [rsp+248h+var_1C8], 0
0x18006c3d1  cmp     ebx, 4
0x18006c3d4  jnz     short loc_18006C3DD
0x18006c3d6  mov     ebx, 0Dh
0x18006c3db  jmp     short loc_18006C403
0x18006c3dd  cmp     ebx, 3
0x18006c3e0  jnz     short loc_18006C3E9
0x18006c3e2  mov     ebx, 0Ch
0x18006c3e7  jmp     short loc_18006C403
0x18006c3e9  cmp     ebx, 2
0x18006c3ec  jnz     short loc_18006C3F5
0x18006c3ee  mov     ebx, 0Bh
0x18006c3f3  jmp     short loc_18006C403
0x18006c3f5  cmp     ebx, 1
0x18006c3f8  jnz     loc_18006C6D3
0x18006c3fe  mov     ebx, 0Ah
0x18006c403  mov     [rsp+248h+var_1D4], ebx
0x18006c407  lea     r14, [rdi+128h]
0x18006c40e  mov     rdx, r14
0x18006c411  lea     rcx, [rsp+248h+var_60]
0x18006c419  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18006c41e  nop
0x18006c41f  xorps   xmm0, xmm0
0x18006c422  movups  [rsp+248h+var_80], xmm0
0x18006c42a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006c432  movdqu  [rsp+248h+var_70], xmm1
0x18006c43b  xor     eax, eax
0x18006c43d  mov     word ptr [rsp+248h+var_80], ax
0x18006c445  mov     dword ptr [rsp+248h+var_220], ebx
0x18006c449  mov     [rsp+248h+var_228], rsi
0x18006c44e  xor     r9d, r9d
0x18006c451  lea     r8, [rsp+248h+var_80]
0x18006c459  mov     rdx, [rsp+248h+var_1C8]
0x18006c461  mov     rcx, rdi
0x18006c464  call    ?RequestConsentFromUser@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAA?AW4CapabilityConsentValue@2345@_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N1W4DeviceAccessConsentType@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::RequestConsentFromUser(unsigned __int64,std::wstring const &,bool,std::wstring const &,DeviceAccessConsentType)
0x18006c469  mov     [r15], eax
0x18006c46c  lea     rcx, [rsp+248h+var_80]
0x18006c474  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c479  mov     rdx, r13
0x18006c47c  lea     rcx, [rsp+248h+var_80]
0x18006c484  call    ?QueryUserConsentStoreCreatedCount@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$tuple@I_K@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::QueryUserConsentStoreCreatedCount(std::wstring const &)
0x18006c489  mov     al, [rdi+1Dh]
0x18006c48c  mov     [rsp+248h+var_1D8], al
0x18006c490  lea     rcx, [rsp+248h+var_140]
0x18006c498  mov     [rsp+248h+var_170], rcx
0x18006c4a0  mov     rcx, r15; this
0x18006c4a3  call    ?CapabilityConsentValueToString@Private@CapabilityAccess@Internal@Windows@@YAPEBGAEBW4CapabilityConsentValue@1234@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue const &)
0x18006c4a8  mov     rdx, rax
0x18006c4ab  lea     rcx, [rsp+248h+var_140]
0x18006c4b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006c4b8  mov     [rsp+248h+var_1A0], rax
0x18006c4c0  lea     rax, [rsp+248h+var_120]
0x18006c4c8  mov     [rsp+248h+var_168], rax
0x18006c4d0  mov     dword ptr [rsp+248h+var_1D0], 2
0x18006c4d8  lea     rcx, [rsp+248h+var_1D0]; this
0x18006c4dd  call    ?CapabilityConsentValueToString@Private@CapabilityAccess@Internal@Windows@@YAPEBGAEBW4CapabilityConsentValue@1234@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue const &)
0x18006c4e2  mov     rdx, rax
0x18006c4e5  lea     rcx, [rsp+248h+var_120]
0x18006c4ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006c4f2  mov     [rsp+248h+var_1D0], rax
0x18006c4f7  mov     cl, [rdi+24h]
0x18006c4fa  neg     cl
0x18006c4fc  sbb     esi, esi
0x18006c4fe  add     esi, 2
0x18006c501  lea     rax, [rsp+248h+var_100]
0x18006c509  mov     [rsp+248h+var_160], rax
0x18006c511  mov     rdx, r12
0x18006c514  lea     rcx, [rsp+248h+var_100]
0x18006c51c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006c521  mov     [rsp+248h+var_198], rax
0x18006c529  lea     rax, [rsp+248h+var_E0]
0x18006c531  mov     [rsp+248h+var_158], rax
0x18006c539  lea     rdx, [rdi+108h]
0x18006c540  lea     rcx, [rsp+248h+var_E0]
0x18006c548  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006c54d  mov     r12, rax
0x18006c550  lea     rax, [rsp+248h+var_C0]
0x18006c558  mov     [rsp+248h+var_150], rax
0x18006c560  mov     rdx, r14
0x18006c563  lea     rcx, [rsp+248h+var_C0]
0x18006c56b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006c570  mov     rdi, rax
0x18006c573  mov     rdx, r13
0x18006c576  lea     rcx, [rsp+248h+var_A0]
0x18006c57e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006c583  nop
0x18006c584  mov     rcx, qword ptr [rsp+248h+var_80]
0x18006c58c  mov     [rsp+248h+var_1E0], rcx
0x18006c591  mov     ecx, dword ptr [rsp+248h+var_80+8]
0x18006c598  mov     [rsp+248h+var_1E8], ecx
0x18006c59c  xor     r14d, r14d
0x18006c59f  mov     [rsp+248h+var_1F0], r14
0x18006c5a4  mov     dword ptr [rsp+248h+var_1F8], ebx
0x18006c5a8  mov     byte ptr [rsp+248h+var_200], 1
0x18006c5ad  mov     dl, [rsp+248h+var_1D8]
0x18006c5b1  mov     byte ptr [rsp+248h+var_208], dl
0x18006c5b5  mov     rdx, [rsp+248h+var_1A0]
0x18006c5bd  mov     [rsp+248h+var_210], rdx
0x18006c5c2  mov     rdx, [rsp+248h+var_1D0]
0x18006c5c7  mov     [rsp+248h+var_218], rdx
0x18006c5cc  mov     dword ptr [rsp+248h+var_220], esi
0x18006c5d0  mov     rdx, [rsp+248h+var_198]
0x18006c5d8  mov     [rsp+248h+var_228], rdx
0x18006c5dd  mov     r9, r12
0x18006c5e0  mov     r8, rdi
0x18006c5e3  mov     rdx, rax
0x18006c5e6  xor     ecx, ecx
0x18006c5e8  call    ?LogPromptAttempted@@YAXJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000W4AppIdType@Private@CapabilityAccess@Internal@Windows@@00_N2I_KI3@Z; LogPromptAttempted(long,std::wstring,std::wstring,std::wstring,std::wstring,Windows::Internal::CapabilityAccess::Private::AppIdType,std::wstring,std::wstring,bool,bool,uint,unsigned __int64,uint,unsigned __int64)
0x18006c5ed  test    cs:Microsoft_Windows_Privacy_AuditingEnableBits, 10h
0x18006c5f4  jz      loc_18006C686
0x18006c5fa  mov     rcx, [rsp+248h+var_190]
0x18006c602  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006c607  mov     rbx, rax
0x18006c60a  mov     rcx, [rsp+248h+var_188]
0x18006c612  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006c617  mov     r9, rax
0x18006c61a  mov     rcx, [rsp+248h+var_1C0]
0x18006c622  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006c627  mov     r10, rax
0x18006c62a  mov     rcx, r13
0x18006c62d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006c632  mov     r11, rax
0x18006c635  mov     rcx, r15; this
0x18006c638  call    ?CapabilityConsentValueToString@Private@CapabilityAccess@Internal@Windows@@YAPEBGAEBW4CapabilityConsentValue@1234@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue const &)
0x18006c63d  mov     r8, rax
0x18006c640  lea     rcx, [rsp+248h+var_60]
0x18006c648  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006c64d  mov     [rsp+248h+var_1F8], rbx
0x18006c652  mov     [rsp+248h+var_200], r9
0x18006c657  mov     [rsp+248h+var_208], r14d
0x18006c65c  mov     [rsp+248h+var_210], rax
0x18006c661  mov     dword ptr [rsp+248h+var_218], r14d
0x18006c666  mov     [rsp+248h+var_220], r10
0x18006c66b  lea     rax, Format
0x18006c672  mov     [rsp+248h+var_228], rax
0x18006c677  mov     r9, r11
0x18006c67a  lea     rdx, PromptAnsweredSuccessEvent
0x18006c681  call    McTemplateU0zzzzdztzz_EventWriteTransfer
0x18006c686  jmp     short loc_18006C69B
0x18006c688  lea     rcx, [rsp+248h+var_60]
0x18006c690  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c695  mov     eax, dword ptr [rsp+248h+var_1D0]
0x18006c699  jmp     short loc_18006C6B0
0x18006c69b  lea     rcx, [rsp+248h+var_60]
0x18006c6a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c6a8  xor     eax, eax
0x18006c6aa  jmp     short loc_18006C6B0
0x18006c6ac  mov     eax, dword ptr [rsp+248h+var_1D0]
0x18006c6b0  mov     rcx, [rsp+248h+var_40]
0x18006c6b8  xor     rcx, rsp; StackCookie
0x18006c6bb  call    __security_check_cookie
0x18006c6c0  add     rsp, 210h
0x18006c6c7  pop     r15
0x18006c6c9  pop     r14
0x18006c6cb  pop     r13
0x18006c6cd  pop     r12
0x18006c6cf  pop     rdi
0x18006c6d0  pop     rsi
0x18006c6d1  pop     rbx
0x18006c6d2  retn
0x18006c6d3  mov     rcx, [rsp+248h]; this
0x18006c6db  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x18006c6e2  mov     edx, 0EDFh; void *
0x18006c6e7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
