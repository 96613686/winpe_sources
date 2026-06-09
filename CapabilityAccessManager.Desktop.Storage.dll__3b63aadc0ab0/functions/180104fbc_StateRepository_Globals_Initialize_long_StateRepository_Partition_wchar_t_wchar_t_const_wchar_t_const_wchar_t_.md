# StateRepository::Globals::Initialize(long (*)(StateRepository::Partition,wchar_t * *),wchar_t const *,wchar_t const *,wchar_t const *,StateRepository::Globals::Flags)

- ea: `0x180104fbc`
- end: `0x1801052a0`
- name: `?Initialize@Globals@StateRepository@@YAJP6AJW4Partition@2@PEAPEA_W@ZPEB_W33W4Flags@12@@Z`
- size: `740`
- prototype: `__int64 __fastcall(__int64, __int64, void *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18010165c`

## callees

- `0x1800eabd4`
- `0x1800eabf4`
- `0x1800fb7f0`
- `0x180102288`
- `0x180104fbc`
- `0x180105bbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180105174`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801051d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010523c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180105174`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801051d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010523c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801051c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105229`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801051c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105229`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010516c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180105191`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801051d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801051f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180105234`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180105259`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010516c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180105191`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801051d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801051f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180105234`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180105259`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18010507d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18010507d`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1801050af`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180105110`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1801050af`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180105110`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1801050be`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18010511f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1801050be`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18010511f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180105003`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180105003`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180105041`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180105041`

## string_xrefs

- `0x1801050cf`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1801050e5`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180105014`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x180105052`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x18010508b`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StateRepository::Globals::Initialize(__int64 a1, __int64 a2, void *a3, __int64 a4, unsigned int a5)
{
  NTSTATUS v5; // eax
  int Settings; // ebx
  unsigned __int64 v7; // r8
  NTSTATUS v8; // eax
  int LastError; // eax
  const char *v10; // r9
  PVOID v11; // rcx
  bool v12; // zf
  __int64 v13; // rdx
  PVOID v15; // rcx
  HLOCAL *hlocal_string_nothrow; // rdi
  unsigned __int64 v17; // r8
  HLOCAL v18; // r14
  HLOCAL v19; // rsi
  DWORD v20; // ebx
  HLOCAL *v21; // rdi
  unsigned __int64 v22; // r8
  HLOCAL v23; // r14
  HLOCAL v24; // rsi
  DWORD v25; // ebx
  HLOCAL *v26; // rdi
  HLOCAL v27; // r14
  HLOCAL v28; // rsi
  DWORD v29; // ebx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  PVOID PolicyHandle; // [rsp+88h] [rbp+38h] BYREF
  PVOID DomainInfo; // [rsp+90h] [rbp+40h] BYREF
  HLOCAL cbSid; // [rsp+98h] [rbp+48h] BYREF

  HIDWORD(cbSid) = HIDWORD(a4);
  DomainInfo = a3;
  LODWORD(cbSid) = 68;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  v5 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  if ( v5 >= 0 )
  {
    DomainInfo = 0;
    v8 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
    if ( v8 >= 0 )
    {
      if ( CreateWellKnownSid(
             WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
             *((PSID *)DomainInfo + 2),
             qword_1801404B0,
             (DWORD *)&cbSid) )
      {
        v15 = DomainInfo;
        DomainInfo = 0;
        if ( v15 )
          LsaLookupFreeMemory(v15);
        if ( PolicyHandle )
          LsaLookupClose(PolicyHandle);
        goto LABEL_18;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x83,
                    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                    v10);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x81,
                    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                    (const char *)(unsigned int)v8,
                    ObjectAttributes.Length);
    }
    v11 = DomainInfo;
    v12 = DomainInfo == 0;
    DomainInfo = 0;
    Settings = LastError;
    if ( !v12 )
      LsaLookupFreeMemory(v11);
  }
  else
  {
    Settings = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)0x7E,
                 (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                 (const char *)(unsigned int)v5,
                 ObjectAttributes.Length);
  }
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  if ( Settings < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)Settings,
      ObjectAttributes.Length);
    v13 = 203;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)Settings,
      ObjectAttributes.Length);
    return (unsigned int)Settings;
  }
LABEL_18:
  qword_180140670 = (__int64)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetPartitionDatabaseFilename;
  hlocal_string_nothrow = (HLOCAL *)wil::make_hlocal_string_nothrow(
                                      (wil *)&cbSid,
                                      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CapabilityConsentStorage\\Repository",
                                      v7);
  if ( &qword_180140658 != hlocal_string_nothrow )
  {
    v18 = *hlocal_string_nothrow;
    v19 = qword_180140658;
    if ( qword_180140658 )
    {
      v20 = GetLastError();
      LocalFree(v19);
      SetLastError(v20);
    }
    qword_180140658 = v18;
    *hlocal_string_nothrow = 0;
  }
  if ( cbSid )
    LocalFree(cbSid);
  v21 = (HLOCAL *)wil::make_hlocal_string_nothrow((wil *)&cbSid, L"CapabilityConsentStorageStatus", v17);
  if ( &qword_180140660 != v21 )
  {
    v23 = *v21;
    v24 = qword_180140660;
    if ( qword_180140660 )
    {
      v25 = GetLastError();
      LocalFree(v24);
      SetLastError(v25);
    }
    qword_180140660 = v23;
    *v21 = 0;
  }
  if ( cbSid )
    LocalFree(cbSid);
  v26 = (HLOCAL *)wil::make_hlocal_string_nothrow(
                    (wil *)&cbSid,
                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CapabilityConsentStorage\\RepositoryStatus",
                    v22);
  if ( &qword_180140668 != v26 )
  {
    v27 = *v26;
    v28 = qword_180140668;
    if ( qword_180140668 )
    {
      v29 = GetLastError();
      LocalFree(v28);
      SetLastError(v29);
    }
    qword_180140668 = v27;
    *v26 = 0;
  }
  if ( cbSid )
    LocalFree(cbSid);
  qword_180140490 = qword_180140660;
  qword_180140498 = (__int64)qword_180140668;
  Settings = StateRepository::Globals::LoadSettings(a5);
  if ( Settings < 0 )
  {
    v13 = 211;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x180104fbc  mov     [rsp-28h+cbSid], r9
0x180104fc1  mov     [rsp-28h+DomainInfo], r8
0x180104fc6  mov     [rsp-28h+PolicyHandle], rdx
0x180104fcb  push    rbp
0x180104fcc  push    rbx
0x180104fcd  push    rsi
0x180104fce  push    rdi
0x180104fcf  push    r14
0x180104fd1  mov     rbp, rsp
0x180104fd4  sub     rsp, 50h
0x180104fd8  mov     dword ptr [rbp+cbSid], 44h ; 'D'
0x180104fdf  xorps   xmm0, xmm0
0x180104fe2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180104fe6  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180104fea  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180104fee  mov     [rbp+PolicyHandle], 0
0x180104ff6  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x180104ffa  mov     edx, 1; AccessMask
0x180104fff  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x180105003  call    cs:__imp_LsaLookupOpenLocalPolicy
0x180105009  test    eax, eax
0x18010500b  jns     short loc_18010502C
0x18010500d  mov     rcx, [rbp+28h]; this
0x180105011  mov     r9d, eax; char *
0x180105014  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\StateRepositor"...
0x18010501b  mov     edx, 7Eh ; '~'; void *
0x180105020  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180105025  mov     ebx, eax
0x180105027  jmp     loc_1801050B5
0x18010502c  mov     [rbp+DomainInfo], 0
0x180105034  lea     r8, [rbp+DomainInfo]; DomainInfo
0x180105038  mov     edx, 5; DomainInfoClass
0x18010503d  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180105041  call    cs:__imp_LsaLookupGetDomainInfo
0x180105047  test    eax, eax
0x180105049  jns     short loc_180105065
0x18010504b  mov     rcx, [rbp+28h]; this
0x18010504f  mov     r9d, eax; char *
0x180105052  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\StateRepositor"...
0x180105059  mov     edx, 81h; void *
0x18010505e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180105063  jmp     short loc_18010509C
0x180105065  lea     r9, [rbp+cbSid]; cbSid
0x180105069  lea     r8, qword_1801404B0; pSid
0x180105070  mov     rdx, [rbp+DomainInfo]
0x180105074  mov     rdx, [rdx+10h]; DomainSid
0x180105078  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x18010507d  call    cs:__imp_CreateWellKnownSid
0x180105083  test    eax, eax
0x180105085  jnz     short loc_1801050FF
0x180105087  mov     rcx, [rbp+28h]; this
0x18010508b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\StateRepositor"...
0x180105092  mov     edx, 83h; void *
0x180105097  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010509c  mov     rcx, [rbp+DomainInfo]; Buffer
0x1801050a0  test    rcx, rcx
0x1801050a3  mov     [rbp+DomainInfo], 0
0x1801050ab  mov     ebx, eax
0x1801050ad  jz      short loc_1801050B5
0x1801050af  call    cs:__imp_LsaLookupFreeMemory
0x1801050b5  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1801050b9  test    rcx, rcx
0x1801050bc  jz      short loc_1801050C4
0x1801050be  call    cs:__imp_LsaLookupClose
0x1801050c4  test    ebx, ebx
0x1801050c6  jns     short loc_180105125
0x1801050c8  mov     rcx, [rbp+28h]; this
0x1801050cc  mov     r9d, ebx; char *
0x1801050cf  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1801050d6  mov     edx, 0C0h; void *
0x1801050db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801050e0  mov     edx, 0CBh; void *
0x1801050e5  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1801050ec  mov     r9d, ebx; char *
0x1801050ef  mov     rcx, [rbp+28h]; this
0x1801050f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801050f8  mov     eax, ebx
0x1801050fa  jmp     loc_180105295
0x1801050ff  mov     rcx, [rbp+DomainInfo]; Buffer
0x180105103  mov     [rbp+DomainInfo], 0
0x18010510b  test    rcx, rcx
0x18010510e  jz      short loc_180105116
0x180105110  call    cs:__imp_LsaLookupFreeMemory
0x180105116  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18010511a  test    rcx, rcx
0x18010511d  jz      short loc_180105125
0x18010511f  call    cs:__imp_LsaLookupClose
0x180105125  lea     rax, ?GetPartitionDatabaseFilename@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAJW4Partition@StateRepository@@PEAPEAG@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetPartitionDatabaseFilename(StateRepository::Partition,ushort * *)
0x18010512c  mov     cs:qword_180140670, rax
0x180105133  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18010513a  lea     rcx, [rbp+cbSid]; this
0x18010513e  call    ?make_hlocal_string_nothrow@wil@@YA@PEB_W_K@Z; wil::make_hlocal_string_nothrow(wchar_t const *,unsigned __int64)
0x180105143  mov     rdi, rax
0x180105146  lea     rax, qword_180140658
0x18010514d  cmp     rax, rdi
0x180105150  jz      short loc_180105188
0x180105152  mov     r14, [rdi]
0x180105155  mov     rsi, cs:qword_180140658
0x18010515c  test    rsi, rsi
0x18010515f  jz      short loc_18010517A
0x180105161  call    cs:__imp_GetLastError
0x180105167  mov     ebx, eax
0x180105169  mov     rcx, rsi; hMem
0x18010516c  call    cs:__imp_LocalFree
0x180105172  mov     ecx, ebx; dwErrCode
0x180105174  call    cs:__imp_SetLastError
0x18010517a  mov     cs:qword_180140658, r14
0x180105181  mov     qword ptr [rdi], 0
0x180105188  mov     rcx, [rbp+cbSid]; hMem
0x18010518c  test    rcx, rcx
0x18010518f  jz      short loc_180105197
0x180105191  call    cs:__imp_LocalFree
0x180105197  lea     rdx, aCapabilitycons_2; "CapabilityConsentStorageStatus"
0x18010519e  lea     rcx, [rbp+cbSid]; this
0x1801051a2  call    ?make_hlocal_string_nothrow@wil@@YA@PEB_W_K@Z; wil::make_hlocal_string_nothrow(wchar_t const *,unsigned __int64)
0x1801051a7  mov     rdi, rax
0x1801051aa  lea     rax, qword_180140660
0x1801051b1  cmp     rax, rdi
0x1801051b4  jz      short loc_1801051EC
0x1801051b6  mov     r14, [rdi]
0x1801051b9  mov     rsi, cs:qword_180140660
0x1801051c0  test    rsi, rsi
0x1801051c3  jz      short loc_1801051DE
0x1801051c5  call    cs:__imp_GetLastError
0x1801051cb  mov     ebx, eax
0x1801051cd  mov     rcx, rsi; hMem
0x1801051d0  call    cs:__imp_LocalFree
0x1801051d6  mov     ecx, ebx; dwErrCode
0x1801051d8  call    cs:__imp_SetLastError
0x1801051de  mov     cs:qword_180140660, r14
0x1801051e5  mov     qword ptr [rdi], 0
0x1801051ec  mov     rcx, [rbp+cbSid]; hMem
0x1801051f0  test    rcx, rcx
0x1801051f3  jz      short loc_1801051FB
0x1801051f5  call    cs:__imp_LocalFree
0x1801051fb  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180105202  lea     rcx, [rbp+cbSid]; this
0x180105206  call    ?make_hlocal_string_nothrow@wil@@YA@PEB_W_K@Z; wil::make_hlocal_string_nothrow(wchar_t const *,unsigned __int64)
0x18010520b  mov     rdi, rax
0x18010520e  lea     rax, qword_180140668
0x180105215  cmp     rax, rdi
0x180105218  jz      short loc_180105250
0x18010521a  mov     r14, [rdi]
0x18010521d  mov     rsi, cs:qword_180140668
0x180105224  test    rsi, rsi
0x180105227  jz      short loc_180105242
0x180105229  call    cs:__imp_GetLastError
0x18010522f  mov     ebx, eax
0x180105231  mov     rcx, rsi; hMem
0x180105234  call    cs:__imp_LocalFree
0x18010523a  mov     ecx, ebx; dwErrCode
0x18010523c  call    cs:__imp_SetLastError
0x180105242  mov     cs:qword_180140668, r14
0x180105249  mov     qword ptr [rdi], 0
0x180105250  mov     rcx, [rbp+cbSid]; hMem
0x180105254  test    rcx, rcx
0x180105257  jz      short loc_18010525F
0x180105259  call    cs:__imp_LocalFree
0x18010525f  mov     rax, cs:qword_180140660
0x180105266  mov     cs:qword_180140490, rax
0x18010526d  mov     rax, cs:qword_180140668
0x180105274  mov     cs:qword_180140498, rax
0x18010527b  mov     ecx, [rbp+arg_20]
0x18010527e  call    ?LoadSettings@Globals@StateRepository@@YAJW4Flags@12@@Z; StateRepository::Globals::LoadSettings(StateRepository::Globals::Flags)
0x180105283  mov     ebx, eax
0x180105285  test    eax, eax
0x180105287  jns     short loc_180105293
0x180105289  mov     edx, 0D3h
0x18010528e  jmp     loc_1801050E5
0x180105293  xor     eax, eax
0x180105295  add     rsp, 50h
0x180105299  pop     r14
0x18010529b  pop     rdi
0x18010529c  pop     rsi
0x18010529d  pop     rbx
0x18010529e  pop     rbp
0x18010529f  retn
```
