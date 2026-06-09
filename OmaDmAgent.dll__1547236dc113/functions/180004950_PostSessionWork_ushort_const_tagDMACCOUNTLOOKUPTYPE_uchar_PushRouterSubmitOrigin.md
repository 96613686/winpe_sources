# PostSessionWork(ushort const *,tagDMACCOUNTLOOKUPTYPE,uchar,PushRouterSubmitOrigin)

- ea: `0x180004950`
- end: `0x180004f77`
- name: `?PostSessionWork@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@EW4PushRouterSubmitOrigin@@@Z`
- size: `1575`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180004870`

## callees

- `0x180001188`
- `0x18000121c`
- `0x180001284`
- `0x180002a50`
- `0x1800032a8`
- `0x180003310`
- `0x180003378`
- `0x180004950`
- `0x1800062ac`
- `0x180007edc`
- `0x180009304`
- `0x18000c2e8`
- `0x18000da10`
- `0x18000f8e4`
- `0x180010700`
- `0x1800110c0`
- `0x18001f420`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004a57`
- `msvcrt!_wcsicmp` at `0x180004b2a`
- `msvcrt!_wcsicmp` at `0x180004c8a`
- `msvcrt!_wcsicmp` at `0x180004a57`
- `msvcrt!_wcsicmp` at `0x180004b2a`
- `msvcrt!_wcsicmp` at `0x180004c8a`
- `KERNEL32!CloseHandle` at `0x180004d20`
- `KERNEL32!CloseHandle` at `0x180004d20`
- `KERNEL32!LocalFree` at `0x180004ebd`
- `KERNEL32!LocalFree` at `0x180004ef6`
- `KERNEL32!LocalFree` at `0x180004ebd`
- `KERNEL32!LocalFree` at `0x180004ef6`
- `KERNEL32!GetProcessHeap` at `0x180004ece`
- `KERNEL32!GetProcessHeap` at `0x180004ece`
- `KERNEL32!HeapFree` at `0x180004ee2`
- `KERNEL32!HeapFree` at `0x180004ee2`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180004c49`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180004c49`
- `DMCmnUtils!DmRevertToSelf` at `0x180004ea4`
- `DMCmnUtils!DmRevertToSelf` at `0x180004ea4`
- `DMCmnUtils!DmImpersonate` at `0x180004d36`
- `DMCmnUtils!DmImpersonate` at `0x180004d36`
- `DMCmnUtils!DmGetUserTokenFromSid` at `0x180004cab`
- `DMCmnUtils!DmGetUserTokenFromSid` at `0x180004cab`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x180004c67`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x180004c67`
- `omadmapi!__imp_OmaDmInitiateSessionEx` at `0x180004f32`
- `omadmapi!__imp_OmaDmInitiateSessionEx` at `0x180004f32`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x1800049cc`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x1800049cc`
- `MDMRegistration!UnregisterDeviceWithManagement` at `0x180004a6c`
- `MDMRegistration!UnregisterDeviceWithManagement` at `0x180004a6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=2
__int64 __fastcall PostSessionWork(__int64 a1, __int64 a2, unsigned __int8 a3, int a4)
{
  int InternalAcctID; // esi
  int ConfigItem; // ebx
  __int64 v6; // rdx
  wil *v7; // rcx
  const wchar_t *v8; // rcx
  __int64 v9; // r8
  int v10; // ecx
  BOOL v11; // r8d
  int v12; // r9d
  int v13; // ebx
  __int64 v14; // rdx
  wil *v15; // rcx
  const wchar_t *v16; // rcx
  int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // ecx
  BOOL v22; // r8d
  int v23; // r9d
  char *v24; // rdx
  __int64 v25; // r8
  int v26; // eax
  int v27; // r12d
  __int64 v28; // rcx
  __int64 v29; // r8
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  BOOL v33; // r15d
  __int64 *JobHelper; // rbx
  unsigned int v35; // esi
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // r8
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  __int64 v42; // rcx
  __int64 v43; // r8
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  wchar_t *v47; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v49; // rdx
  bool v51; // [rsp+40h] [rbp-108h] BYREF
  BOOL v52; // [rsp+44h] [rbp-104h] BYREF
  unsigned __int8 v53; // [rsp+48h] [rbp-100h]
  int v54; // [rsp+50h] [rbp-F8h]
  wchar_t *String2; // [rsp+58h] [rbp-F0h] BYREF
  int v56; // [rsp+60h] [rbp-E8h] BYREF
  wchar_t *v57; // [rsp+68h] [rbp-E0h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-D8h] BYREF
  unsigned int v59; // [rsp+78h] [rbp-D0h] BYREF
  int v60; // [rsp+80h] [rbp-C8h]
  HLOCAL v61; // [rsp+88h] [rbp-C0h] BYREF
  HANDLE hObject[2]; // [rsp+90h] [rbp-B8h] BYREF
  wchar_t *String1[3]; // [rsp+A0h] [rbp-A8h] BYREF
  unsigned __int64 v64; // [rsp+B8h] [rbp-90h]
  _BYTE v65[32]; // [rsp+C0h] [rbp-88h] BYREF
  _BYTE v66[32]; // [rsp+E0h] [rbp-68h] BYREF

  v53 = a3;
  v60 = a4;
  String2 = 0;
  v61 = 0;
  hObject[0] = 0;
  v59 = 0;
  hMem = 0;
  v56 = 63;
  v64 = 7;
  String1[2] = 0;
  LOWORD(String1[0]) = 0;
  v51 = 0;
  InternalAcctID = OmaDmGetInternalAcctID(a1, a2, &hMem);
  if ( InternalAcctID < 0 )
    goto LABEL_55;
  try
  {
    std::wstring::wstring(v65, L"UnenrollRequestIssued");
    ConfigItem = GetConfigItem(v65, String1);
    LOBYTE(v6) = 1;
    std::wstring::_Tidy(v65, v6, 0);
  }
  catch ( ... )
  {
    v54 = wil::ResultFromCaughtException(v7);
    ConfigItem = v54;
  }
  try
  {
    if ( ConfigItem >= 0 )
    {
      v8 = (const wchar_t *)String1;
      if ( v64 >= 8 )
        v8 = String1[0];
      if ( !_wcsicmp(v8, L"1") )
      {
        v9 = (unsigned int)UnregisterDeviceWithManagement(hMem);
        if ( (unsigned int)dword_18002B000 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn((unsigned int)dword_18002B000, 0x200000000000LL, v9) )
          {
            v52 = v11;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v10,
              (unsigned int)&word_1800249E6,
              v11,
              v12,
              (__int64)&v52);
          }
        }
      }
    }
    std::wstring::wstring(v65, L"LockRequestIssued");
    v13 = GetConfigItem(v65, String1);
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v65, v14, 0);
  }
  catch ( ... )
  {
    v54 = wil::ResultFromCaughtException(v15);
    v13 = v54;
  }
  if ( v13 >= 0 )
  {
    v16 = (const wchar_t *)String1;
    if ( v64 >= 8 )
      v16 = String1[0];
    if ( !_wcsicmp(v16, L"1") )
    {
      std::wstring::wstring(v66, L"0");
      std::wstring::wstring(v65, L"LockRequestIssued");
      v17 = SetConfigItem(v65, v66);
      LOBYTE(v18) = 1;
      std::wstring::_Tidy(v65, v18, 0);
      LOBYTE(v19) = 1;
      std::wstring::_Tidy(v66, v19, 0);
      if ( v17 >= 0 )
      {
        v25 = (unsigned int)ExecuteLockWorkStation();
        if ( (unsigned int)dword_18002B000 <= 5
          || !(unsigned __int8)tlgKeywordOn((unsigned int)dword_18002B000, 0x200000000000LL, v25) )
        {
          goto LABEL_23;
        }
        v52 = v22;
        v24 = byte_180024A95;
      }
      else
      {
        if ( (unsigned int)dword_18002B000 <= 5
          || !(unsigned __int8)tlgKeywordOn((unsigned int)dword_18002B000, 0x200000000000LL, v20) )
        {
          goto LABEL_23;
        }
        v52 = v17;
        v24 = byte_180024ACD;
      }
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v21,
        (_DWORD)v24,
        v22,
        v23,
        (__int64)&v52);
    }
  }
LABEL_23:
  InternalAcctID = DmGetEnrollmentType((const unsigned __int16 *)hMem, (enum EnrollmentEnrollType *)&v56);
  if ( InternalAcctID >= 0 )
  {
    v26 = !v56 || v56 == 13
        ? DmGetEnrollmentSid((const unsigned __int16 *)hMem, &String2)
        : DmGetActiveUserSid(&String2);
    InternalAcctID = v26;
    if ( v26 >= 0 )
    {
      InternalAcctID = DmGetCurrentUserSid((unsigned __int16 **)&v61);
      if ( InternalAcctID >= 0 )
      {
        v27 = _wcsicmp((const wchar_t *)v61, String2);
        if ( (int)DmGetUserTokenFromSid(String2, hObject, &v59) >= 0 )
        {
          v52 = 0;
          CloseHandle(hObject[0]);
          if ( v27 )
          {
            InternalAcctID = DmImpersonate(String2);
            if ( InternalAcctID < 0 )
              goto LABEL_55;
            v52 = InternalAcctID != 1;
          }
          v33 = (unsigned int)(v60 - 7) <= 1;
          LODWORD(v57) = v33;
          JobHelper = (__int64 *)JobHelper::GetJobHelper();
          hObject[1] = JobHelper;
          if ( JobHelper )
          {
            if ( !v27
              || (v35 = v59,
                  v36 = std::wstring::wstring(v66, String2),
                  InternalAcctID = JobHelper::SetImpersonation(JobHelper, v36, v35),
                  InternalAcctID >= 0) )
            {
              InternalAcctID = JobHelper::ProcessAllJobs((JobHelper *)JobHelper, &v51);
              if ( InternalAcctID < 0
                && (unsigned int)dword_18002B000 > 5
                && (unsigned __int8)tlgKeywordOn(v37, 0x200000000000LL, v38) )
              {
                LODWORD(v57) = InternalAcctID;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  v39,
                  (unsigned int)byte_180024A2D,
                  v40,
                  v41,
                  (__int64)&v57);
              }
              if ( v51 && !v33 )
              {
                InternalAcctID = JobHelper::DoJobCleanup((JobHelper *)JobHelper, JobHelper[15]);
                if ( InternalAcctID < 0
                  && (unsigned int)dword_18002B000 > 5
                  && (unsigned __int8)tlgKeywordOn(v42, 0x200000000000LL, v43) )
                {
                  LODWORD(v57) = InternalAcctID;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                    v44,
                    (unsigned int)byte_180024A61,
                    v45,
                    v46,
                    (__int64)&v57);
                }
              }
              JobHelper::CleanupJobHelper();
            }
          }
          else
          {
            InternalAcctID = -2147024882;
          }
          if ( v52 )
            DmRevertToSelf();
        }
        else
        {
          if ( (unsigned int)dword_18002B000 > 5 && (unsigned __int8)tlgKeywordOn(v28, 0x200000000000LL, v29) )
          {
            v57 = String2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              v30,
              (unsigned int)word_180024B02,
              v31,
              v32,
              (__int64)&v57);
          }
          InternalAcctID = 0;
        }
      }
    }
  }
LABEL_55:
  LocalFree(hMem);
  v47 = String2;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v47);
  LocalFree(v61);
  if ( InternalAcctID >= 0 && v51 )
    InternalAcctID = OmaDmInitiateSessionEx(hMem, 1, v53, 0, 0, 0, v60);
  LOBYTE(v49) = 1;
  std::wstring::_Tidy(String1, v49, 0);
  return (unsigned int)InternalAcctID;
}

```

## disassembly

```asm
0x180004950  mov     r11, rsp
0x180004953  push    rbx
0x180004954  push    rsi
0x180004955  push    rdi
0x180004956  push    r12
0x180004958  push    r14
0x18000495a  push    r15
0x18000495c  sub     rsp, 118h
0x180004963  mov     rax, cs:__security_cookie
0x18000496a  xor     rax, rsp
0x18000496d  mov     [rsp+148h+var_48], rax
0x180004975  mov     [rsp+148h+var_100], r8b
0x18000497a  mov     [rsp+148h+var_C8], r9d
0x180004982  xor     edi, edi
0x180004984  mov     [rsp+148h+String2], rdi
0x180004989  mov     [r11-0C0h], rdi
0x180004990  mov     [r11-0B8h], rdi
0x180004997  mov     [rsp+148h+var_D0], edi
0x18000499b  mov     [rsp+148h+hMem], rdi
0x1800049a0  mov     [rsp+148h+var_E8], 3Fh ; '?'
0x1800049a8  mov     qword ptr [r11-90h], 7
0x1800049b3  mov     [r11-98h], rdi
0x1800049ba  mov     word ptr [rsp+148h+String1], di
0x1800049c2  mov     [rsp+148h+var_108], dil
0x1800049c7  lea     r8, [rsp+148h+hMem]
0x1800049cc  call    cs:__imp_OmaDmGetInternalAcctID
0x1800049d3  nop     dword ptr [rax+rax+00h]
0x1800049d8  mov     esi, eax
0x1800049da  test    eax, eax
0x1800049dc  js      loc_180004EB2
0x1800049e2  lea     rdx, aUnenrollreques; "UnenrollRequestIssued"
0x1800049e9  lea     rcx, [rsp+148h+var_88]
0x1800049f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800049f6  nop
0x1800049f7  lea     rdx, [rsp+148h+String1]
0x1800049ff  lea     rcx, [rsp+148h+var_88]
0x180004a07  call    ?GetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetConfigItem(std::wstring const &,std::wstring &)
0x180004a0c  mov     ebx, eax
0x180004a0e  xor     r8d, r8d
0x180004a11  lea     r14d, [rdi+1]
0x180004a15  mov     dl, r14b
0x180004a18  lea     rcx, [rsp+148h+var_88]
0x180004a20  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180004a25  nop
0x180004a26  jmp     short loc_180004A32
0x180004a28  xor     edi, edi
0x180004a2a  lea     r14d, [rdi+1]
0x180004a2e  mov     ebx, [rsp+148h+var_F8]
0x180004a32  test    ebx, ebx
0x180004a34  js      short loc_180004AB5
0x180004a36  lea     rcx, [rsp+148h+String1]
0x180004a3e  cmp     [rsp+148h+var_90], 8
0x180004a47  cmovnb  rcx, [rsp+148h+String1]; String1
0x180004a50  lea     rdx, a1; "1"
0x180004a57  call    cs:__imp__wcsicmp
0x180004a5e  nop     dword ptr [rax+rax+00h]
0x180004a63  test    eax, eax
0x180004a65  jnz     short loc_180004AB5
0x180004a67  mov     rcx, [rsp+148h+hMem]
0x180004a6c  call    cs:__imp_UnregisterDeviceWithManagement
0x180004a73  nop     dword ptr [rax+rax+00h]
0x180004a78  mov     r8d, eax
0x180004a7b  mov     ecx, cs:dword_18002B000
0x180004a81  cmp     ecx, 5
0x180004a84  jbe     short loc_180004AB5
0x180004a86  mov     rdx, 200000000000h
0x180004a90  call    _tlgKeywordOn
0x180004a95  test    al, al
0x180004a97  jz      short loc_180004AB5
0x180004a99  mov     [rsp+148h+var_104], r8d
0x180004a9e  lea     rax, [rsp+148h+var_104]
0x180004aa3  mov     [rsp+148h+var_128], rax
0x180004aa8  lea     rdx, word_1800249E6
0x180004aaf  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180004ab4  nop
0x180004ab5  lea     rdx, aLockrequestiss; "LockRequestIssued"
0x180004abc  lea     rcx, [rsp+148h+var_88]
0x180004ac4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180004ac9  nop
0x180004aca  lea     rdx, [rsp+148h+String1]
0x180004ad2  lea     rcx, [rsp+148h+var_88]
0x180004ada  call    ?GetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetConfigItem(std::wstring const &,std::wstring &)
0x180004adf  mov     ebx, eax
0x180004ae1  xor     r8d, r8d
0x180004ae4  mov     dl, r14b
0x180004ae7  lea     rcx, [rsp+148h+var_88]
0x180004aef  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180004af4  nop
0x180004af5  jmp     short loc_180004B01
0x180004af7  xor     edi, edi
0x180004af9  lea     r14d, [rdi+1]
0x180004afd  mov     ebx, [rsp+148h+var_F8]
0x180004b01  test    ebx, ebx
0x180004b03  js      loc_180004C16
0x180004b09  lea     rcx, [rsp+148h+String1]
0x180004b11  cmp     [rsp+148h+var_90], 8
0x180004b1a  cmovnb  rcx, [rsp+148h+String1]; String1
0x180004b23  lea     rdx, a1; "1"
0x180004b2a  call    cs:__imp__wcsicmp
0x180004b31  nop     dword ptr [rax+rax+00h]
0x180004b36  test    eax, eax
0x180004b38  jnz     loc_180004C16
0x180004b3e  lea     rdx, a0; "0"
0x180004b45  lea     rcx, [rsp+148h+var_68]
0x180004b4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180004b52  nop
0x180004b53  lea     rdx, aLockrequestiss; "LockRequestIssued"
0x180004b5a  lea     rcx, [rsp+148h+var_88]
0x180004b62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180004b67  nop
0x180004b68  lea     rdx, [rsp+148h+var_68]
0x180004b70  lea     rcx, [rsp+148h+var_88]
0x180004b78  call    ?SetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; SetConfigItem(std::wstring const &,std::wstring const &)
0x180004b7d  mov     ebx, eax
0x180004b7f  xor     r8d, r8d
0x180004b82  mov     dl, r14b
0x180004b85  lea     rcx, [rsp+148h+var_88]
0x180004b8d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180004b92  nop
0x180004b93  xor     r8d, r8d
0x180004b96  mov     dl, r14b
0x180004b99  lea     rcx, [rsp+148h+var_68]
0x180004ba1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180004ba6  test    ebx, ebx
0x180004ba8  jns     short loc_180004BD5
0x180004baa  mov     ecx, cs:dword_18002B000
0x180004bb0  cmp     ecx, 5
0x180004bb3  jbe     short loc_180004C16
0x180004bb5  mov     rdx, 200000000000h
0x180004bbf  call    _tlgKeywordOn
0x180004bc4  test    al, al
0x180004bc6  jz      short loc_180004C16
0x180004bc8  mov     [rsp+148h+var_104], ebx
0x180004bcc  lea     rdx, byte_180024ACD
0x180004bd3  jmp     short loc_180004C07
0x180004bd5  call    ?ExecuteLockWorkStation@@YAJXZ; ExecuteLockWorkStation(void)
0x180004bda  mov     r8d, eax
0x180004bdd  mov     ecx, cs:dword_18002B000
0x180004be3  cmp     ecx, 5
0x180004be6  jbe     short loc_180004C16
0x180004be8  mov     rdx, 200000000000h
0x180004bf2  call    _tlgKeywordOn
0x180004bf7  test    al, al
0x180004bf9  jz      short loc_180004C16
0x180004bfb  mov     [rsp+148h+var_104], r8d
0x180004c00  lea     rdx, byte_180024A95
0x180004c07  lea     rax, [rsp+148h+var_104]
0x180004c0c  mov     [rsp+148h+var_128], rax
0x180004c11  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180004c16  lea     rdx, [rsp+148h+var_E8]; enum EnrollmentEnrollType *
0x180004c1b  mov     rcx, [rsp+148h+hMem]; unsigned __int16 *
0x180004c20  call    ?DmGetEnrollmentType@@YAJPEBGPEAW4EnrollmentEnrollType@@@Z; DmGetEnrollmentType(ushort const *,EnrollmentEnrollType *)
0x180004c25  mov     esi, eax
0x180004c27  test    eax, eax
0x180004c29  js      loc_180004EB8
0x180004c2f  cmp     [rsp+148h+var_E8], edi
0x180004c33  jz      loc_180004D00
0x180004c39  cmp     [rsp+148h+var_E8], 0Dh
0x180004c3e  jz      loc_180004D00
0x180004c44  lea     rcx, [rsp+148h+String2]
0x180004c49  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180004c50  nop     dword ptr [rax+rax+00h]
0x180004c55  test    eax, eax
0x180004c57  mov     esi, eax
0x180004c59  js      loc_180004EB8
0x180004c5f  lea     rcx, [rsp+148h+var_C0]
0x180004c67  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x180004c6e  nop     dword ptr [rax+rax+00h]
0x180004c73  mov     esi, eax
0x180004c75  test    eax, eax
0x180004c77  js      loc_180004EB8
0x180004c7d  mov     rdx, [rsp+148h+String2]; String2
0x180004c82  mov     rcx, [rsp+148h+var_C0]; String1
0x180004c8a  call    cs:__imp__wcsicmp
0x180004c91  nop     dword ptr [rax+rax+00h]
0x180004c96  mov     r12d, eax
0x180004c99  lea     r8, [rsp+148h+var_D0]
0x180004c9e  lea     rdx, [rsp+148h+hObject]
0x180004ca6  mov     rcx, [rsp+148h+String2]
0x180004cab  call    cs:__imp_?DmGetUserTokenFromSid@@YAJPEBGPEAPEAXPEAK@Z; DmGetUserTokenFromSid(ushort const *,void * *,ulong *)
0x180004cb2  nop     dword ptr [rax+rax+00h]
0x180004cb7  test    eax, eax
0x180004cb9  jns     short loc_180004D14
0x180004cbb  mov     eax, cs:dword_18002B000
0x180004cc1  cmp     eax, 5
0x180004cc4  jbe     short loc_180004CF9
0x180004cc6  mov     rdx, 200000000000h
0x180004cd0  call    _tlgKeywordOn
0x180004cd5  test    al, al
0x180004cd7  jz      short loc_180004CF9
0x180004cd9  mov     rax, [rsp+148h+String2]
0x180004cde  mov     [rsp+148h+var_E0], rax
0x180004ce3  lea     rax, [rsp+148h+var_E0]
0x180004ce8  mov     [rsp+148h+var_128], rax
0x180004ced  lea     rdx, word_180024B02
0x180004cf4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180004cf9  mov     esi, edi
0x180004cfb  jmp     loc_180004EB8
0x180004d00  lea     rdx, [rsp+148h+String2]; unsigned __int16 **
0x180004d05  mov     rcx, [rsp+148h+hMem]; unsigned __int16 *
0x180004d0a  call    ?DmGetEnrollmentSid@@YAJPEBGPEAPEAG@Z; DmGetEnrollmentSid(ushort const *,ushort * *)
0x180004d0f  jmp     loc_180004C55
0x180004d14  mov     [rsp+148h+var_104], edi
0x180004d18  mov     rcx, [rsp+148h+hObject]; hObject
0x180004d20  call    cs:__imp_CloseHandle
0x180004d27  nop     dword ptr [rax+rax+00h]
0x180004d2c  test    r12d, r12d
0x180004d2f  jz      short loc_180004D59
0x180004d31  mov     rcx, [rsp+148h+String2]
0x180004d36  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180004d3d  nop     dword ptr [rax+rax+00h]
0x180004d42  mov     esi, eax
0x180004d44  test    eax, eax
0x180004d46  js      loc_180004EB8
0x180004d4c  mov     eax, edi
0x180004d4e  cmp     esi, r14d
0x180004d51  cmovnz  eax, r14d
0x180004d55  mov     [rsp+148h+var_104], eax
0x180004d59  mov     eax, [rsp+148h+var_C8]
0x180004d60  add     eax, 0FFFFFFF9h
0x180004d63  mov     r15d, edi
0x180004d66  cmp     eax, r14d
0x180004d69  setbe   r15b
0x180004d6d  mov     dword ptr [rsp+148h+var_E0], r15d
0x180004d72  call    ?GetJobHelper@JobHelper@@SAPEAV1@XZ; JobHelper::GetJobHelper(void)
0x180004d77  mov     rbx, rax
0x180004d7a  mov     [rsp+148h+var_B0], rax
0x180004d82  test    rax, rax
0x180004d85  jnz     short loc_180004D91
0x180004d87  mov     esi, 8007000Eh
0x180004d8c  jmp     loc_180004E9E
0x180004d91  test    r12d, r12d
0x180004d94  jz      short loc_180004DC5
0x180004d96  mov     esi, [rsp+148h+var_D0]
0x180004d9a  mov     rdx, [rsp+148h+String2]
0x180004d9f  lea     rcx, [rsp+148h+var_68]
0x180004da7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180004dac  mov     r8d, esi
0x180004daf  mov     rdx, rax
0x180004db2  mov     rcx, rbx
0x180004db5  call    ?SetImpersonation@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; JobHelper::SetImpersonation(std::wstring,ulong)
0x180004dba  mov     esi, eax
0x180004dbc  test    eax, eax
0x180004dbe  jns     short loc_180004DC5
0x180004dc0  jmp     loc_180004E9E
0x180004dc5  lea     rdx, [rsp+148h+var_108]; bool *
0x180004dca  mov     rcx, rbx; this
0x180004dcd  call    ?ProcessAllJobs@JobHelper@@QEAAJAEA_N@Z; JobHelper::ProcessAllJobs(bool &)
0x180004dd2  mov     esi, eax
0x180004dd4  jmp     short loc_180004DED
0x180004dd6  xor     edi, edi
0x180004dd8  lea     r14d, [rdi+1]
0x180004ddc  mov     esi, [rsp+148h+var_F8]
0x180004de0  mov     r15d, dword ptr [rsp+148h+var_E0]
0x180004de5  mov     rbx, [rsp+148h+var_B0]
0x180004ded  test    esi, esi
0x180004def  jns     short loc_180004E29
0x180004df1  mov     eax, cs:dword_18002B000
0x180004df7  cmp     eax, 5
0x180004dfa  jbe     short loc_180004E29
0x180004dfc  mov     rdx, 200000000000h
0x180004e06  call    _tlgKeywordOn
0x180004e0b  test    al, al
0x180004e0d  jz      short loc_180004E29
0x180004e0f  mov     dword ptr [rsp+148h+var_E0], esi
0x180004e13  lea     rax, [rsp+148h+var_E0]
0x180004e18  mov     [rsp+148h+var_128], rax
0x180004e1d  lea     rdx, byte_180024A2D
0x180004e24  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180004e29  cmp     [rsp+148h+var_108], dil
0x180004e2e  jz      short loc_180004E8C
0x180004e30  test    r15d, r15d
0x180004e33  jnz     short loc_180004E8C
0x180004e35  mov     rdx, [rbx+78h]; __int64
0x180004e39  mov     rcx, rbx; this
0x180004e3c  call    ?DoJobCleanup@JobHelper@@QEAAJ_J@Z; JobHelper::DoJobCleanup(__int64)
0x180004e41  mov     esi, eax
0x180004e43  jmp     short loc_180004E4F
0x180004e45  xor     edi, edi
0x180004e47  lea     r14d, [rdi+1]
0x180004e4b  mov     esi, [rsp+148h+var_F8]
0x180004e4f  test    esi, esi
0x180004e51  jns     short loc_180004E8C
0x180004e53  mov     eax, cs:dword_18002B000
0x180004e59  cmp     eax, 5
0x180004e5c  jbe     short loc_180004E8C
0x180004e5e  mov     rdx, 200000000000h
0x180004e68  call    _tlgKeywordOn
0x180004e6d  test    al, al
0x180004e6f  jz      short loc_180004E8C
0x180004e71  mov     dword ptr [rsp+148h+var_E0], esi
0x180004e75  lea     rax, [rsp+148h+var_E0]
0x180004e7a  mov     [rsp+148h+var_128], rax
0x180004e7f  lea     rdx, byte_180024A61
0x180004e86  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180004e8b  nop
0x180004e8c  call    ?CleanupJobHelper@JobHelper@@SAXXZ; JobHelper::CleanupJobHelper(void)
0x180004e91  nop
0x180004e92  jmp     short loc_180004E9E
0x180004e94  xor     edi, edi
  ... truncated ...
```
