# _anonymous_namespace_::UpdateTimezonePolicy

- ea: `0x18002567c`
- end: `0x18002586f`
- name: `_anonymous_namespace_::UpdateTimezonePolicy`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800927cc`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x180006ee0`
- `0x180009a80`
- `0x18000ecc0`
- `0x18001d4e0`
- `0x18002207c`
- `0x18002567c`
- `0x180035e0c`
- `0x180062ac8`
- `0x1800ae010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180025715`
- `ntdll!RtlNtStatusToDosError` at `0x180025756`
- `ntdll!RtlNtStatusToDosError` at `0x180025715`
- `ntdll!RtlNtStatusToDosError` at `0x180025756`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18002570d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18002570d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x18002574e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x18002574e`

## string_xrefs

- `0x1800256e3`: `SeTimeZonePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::UpdateTimezonePolicy(char a1)
{
  volatile signed __int32 *v2; // rdi
  void *v3; // rcx
  NTSTATUS v4; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  signed int v8; // eax
  signed int v9; // ebx
  _BYTE v11[8]; // [rsp+30h] [rbp-79h] BYREF
  struct _LSA_UNICODE_STRING UserRights; // [rsp+38h] [rbp-71h] BYREF
  void *v13; // [rsp+48h] [rbp-61h]
  volatile signed __int32 *v14; // [rsp+50h] [rbp-59h]
  _BYTE pExceptionObject[40]; // [rsp+58h] [rbp-51h] BYREF
  void *AccountSid[9]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v17[40]; // [rsp+C8h] [rbp+1Fh] BYREF

  Sid::FromWellKnownSid(AccountSid, WinBuiltinUsersSid);
  v13 = operator new(0x20u);
  v2 = (volatile signed __int32 *)std::_Ref_count_obj2_Lazy_std::shared_ptr_void__Optional___::_Ref_count_obj2_Lazy_std::shared_ptr_void__Optional_____lambda_5ead74b4d734f6c27653397ddc974cd2___(
                                    v13,
                                    v11);
  v13 = (void *)(v2 + 4);
  v14 = v2;
  *(_QWORD *)&UserRights.Length = 2621478;
  UserRights.Buffer = L"SeTimeZonePrivilege";
  v3 = *(void **)Lazy<std::shared_ptr<void>,Optional>::operator->();
  if ( a1 )
  {
    v4 = LsaRemoveAccountRights(v3, AccountSid, 0, &UserRights, 1u);
    v5 = RtlNtStatusToDosError(v4);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147024894 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_63b6f7e99d2a3b3cdf4ede57ea2e6971_Traceguids, v6);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v6);
      throw (ErrorCodeException *)pExceptionObject;
    }
  }
  else
  {
    v7 = LsaAddAccountRights(v3, AccountSid, &UserRights, 1u);
    v8 = RtlNtStatusToDosError(v7);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_63b6f7e99d2a3b3cdf4ede57ea2e6971_Traceguids,
          (unsigned int)v9);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v9);
      throw (ErrorCodeException *)pExceptionObject;
    }
  }
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  return std::wstring::~wstring(v17);
}

```

## disassembly

```asm
0x18002567c  mov     [rsp-8+arg_0], rbx
0x180025681  mov     [rsp-8+arg_8], rdi
0x180025686  push    rbp
0x180025687  lea     rbp, [rsp-57h]
0x18002568c  sub     rsp, 100h
0x180025693  mov     rax, cs:__security_cookie
0x18002569a  xor     rax, rsp
0x18002569d  mov     [rbp+57h+var_10], rax
0x1800256a1  mov     bl, cl
0x1800256a3  mov     edx, 1Bh
0x1800256a8  lea     rcx, [rbp+57h+AccountSid]
0x1800256ac  call    ?FromWellKnownSid@Sid@@SA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z; Sid::FromWellKnownSid(WELL_KNOWN_SID_TYPE)
0x1800256b1  nop
0x1800256b2  mov     ecx, 20h ; ' '; Size
0x1800256b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800256bc  mov     [rbp+57h+var_B8], rax
0x1800256c0  lea     rdx, [rbp+57h+var_D0]
0x1800256c4  mov     rcx, rax
0x1800256c7  call    std___Ref_count_obj2_Lazy_std__shared_ptr_void__Optional______Ref_count_obj2_Lazy_std__shared_ptr_void__Optional_____lambda_5ead74b4d734f6c27653397ddc974cd2___
0x1800256cc  mov     rdi, rax
0x1800256cf  lea     rcx, [rax+10h]
0x1800256d3  mov     [rbp+57h+var_B8], rcx
0x1800256d7  mov     [rbp+57h+var_B0], rax
0x1800256db  mov     qword ptr [rbp+57h+UserRights.Length], 280026h
0x1800256e3  lea     rax, aSetimezonepriv; "SeTimeZonePrivilege"
0x1800256ea  mov     [rbp+57h+UserRights.Buffer], rax
0x1800256ee  call    ??C?$Lazy@V?$shared_ptr@X@std@@VOptional@@@@QEAAPEAV?$shared_ptr@X@std@@XZ; Lazy<std::shared_ptr<void>,Optional>::operator->(void)
0x1800256f3  lea     rdx, [rbp+57h+AccountSid]; AccountSid
0x1800256f7  mov     rcx, [rax]; PolicyHandle
0x1800256fa  test    bl, bl
0x1800256fc  jz      short loc_180025744
0x1800256fe  mov     [rsp+100h+CountOfRights], 1; CountOfRights
0x180025706  lea     r9, [rbp+57h+UserRights]; UserRights
0x18002570a  xor     r8d, r8d; AllRights
0x18002570d  call    cs:__imp_LsaRemoveAccountRights
0x180025713  mov     ecx, eax; Status
0x180025715  call    cs:__imp_RtlNtStatusToDosError
0x18002571b  mov     ebx, eax
0x18002571d  test    eax, eax
0x18002571f  jle     short loc_18002572A
0x180025721  movzx   ebx, ax
0x180025724  or      ebx, 80070000h
0x18002572a  mov     ecx, 80000000h
0x18002572f  lea     eax, [rbx+rcx]
0x180025732  test    ecx, eax
0x180025734  jnz     short loc_18002576F
0x180025736  cmp     ebx, 80070002h
0x18002573c  jnz     loc_180025822
0x180025742  jmp     short loc_18002576F
0x180025744  mov     r9d, 1; CountOfRights
0x18002574a  lea     r8, [rbp+57h+UserRights]; UserRights
0x18002574e  call    cs:__imp_LsaAddAccountRights
0x180025754  mov     ecx, eax; Status
0x180025756  call    cs:__imp_RtlNtStatusToDosError
0x18002575c  mov     ebx, eax
0x18002575e  test    eax, eax
0x180025760  jle     short loc_18002576B
0x180025762  movzx   ebx, ax
0x180025765  or      ebx, 80070000h
0x18002576b  test    ebx, ebx
0x18002576d  js      short loc_1800257D5
0x18002576f  test    rdi, rdi
0x180025772  jz      short loc_1800257AB
0x180025774  or      ebx, 0FFFFFFFFh
0x180025777  mov     eax, ebx
0x180025779  lock xadd [rdi+8], eax
0x18002577e  add     eax, ebx
0x180025780  jnz     short loc_1800257AB
0x180025782  mov     rax, [rdi]
0x180025785  mov     rcx, rdi
0x180025788  mov     rax, [rax]
0x18002578b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025790  mov     eax, ebx
0x180025792  lock xadd [rdi+0Ch], eax
0x180025797  add     eax, ebx
0x180025799  jnz     short loc_1800257AB
0x18002579b  mov     rax, [rdi]
0x18002579e  mov     rcx, rdi
0x1800257a1  mov     rax, [rax+8]
0x1800257a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257aa  nop
0x1800257ab  lea     rcx, [rbp+57h+var_38]
0x1800257af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800257b4  mov     rcx, [rbp+57h+var_10]
0x1800257b8  xor     rcx, rsp; StackCookie
0x1800257bb  call    __security_check_cookie
0x1800257c0  lea     r11, [rsp+100h+var_s0]
0x1800257c8  mov     rbx, [r11+10h]
0x1800257cc  mov     rdi, [r11+18h]
0x1800257d0  mov     rsp, r11
0x1800257d3  pop     rbp
0x1800257d4  retn
0x1800257d5  lea     rax, WPP_GLOBAL_Control
0x1800257dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257e3  cmp     rcx, rax
0x1800257e6  jz      short loc_180025806
0x1800257e8  test    byte ptr [rcx+1Ch], 1
0x1800257ec  jz      short loc_180025806
0x1800257ee  mov     edx, 0Ch
0x1800257f3  mov     r9d, ebx
0x1800257f6  lea     r8, WPP_63b6f7e99d2a3b3cdf4ede57ea2e6971_Traceguids
0x1800257fd  mov     rcx, [rcx+10h]
0x180025801  call    WPP_SF_d
0x180025806  mov     edx, ebx; int
0x180025808  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002580c  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180025811  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180025818  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002581c  call    _CxxThrowException_0
0x180025822  lea     rax, WPP_GLOBAL_Control
0x180025829  mov     rcx, cs:WPP_GLOBAL_Control
0x180025830  cmp     rcx, rax
0x180025833  jz      short loc_180025853
0x180025835  test    byte ptr [rcx+1Ch], 1
0x180025839  jz      short loc_180025853
0x18002583b  mov     edx, 0Bh
0x180025840  mov     r9d, ebx
0x180025843  lea     r8, WPP_63b6f7e99d2a3b3cdf4ede57ea2e6971_Traceguids
0x18002584a  mov     rcx, [rcx+10h]
0x18002584e  call    WPP_SF_d
0x180025853  mov     edx, ebx; int
0x180025855  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180025859  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18002585e  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180025865  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180025869  call    _CxxThrowException_0
```
