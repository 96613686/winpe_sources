# CProcessStateManager::RecordSuccessfulLogon(ushort const *,ushort const *,ushort const *)

- ea: `0x18001aad0`
- end: `0x18001ac87`
- name: `?RecordSuccessfulLogon@CProcessStateManager@@QEAAXPEBG00@Z`
- size: `439`
- prototype: `void __fastcall(CProcessStateManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001ac90`

## callees

- `0x18000fd2c`
- `0x18001a648`
- `0x18001a780`
- `0x18001aad0`
- `0x180026e70`
- `0x18002bc20`
- `0x1800328e0`
- `0x18003a100`
- `0x18003b910`
- `0x18006c000`
- `0x18006e688`

## import_xrefs

- `CredProvCommonCore!__imp_?WriteLoggedOnUserinfo@@YAXPEBG00@Z` at `0x18001ac20`
- `CredProvCommonCore!__imp_?WriteLoggedOnUserinfo@@YAXPEBG00@Z` at `0x18001ac20`
- `CredProvCommonCore!__imp_?WriteLastLoggedOnUserinfo@@YAXPEBG00@Z` at `0x18001abdc`
- `CredProvCommonCore!__imp_?WriteLastLoggedOnUserinfo@@YAXPEBG00@Z` at `0x18001abdc`
- `CredProvCommonCore!__imp_?FormatLastLoggedOn@@YAJW4_CREDENTIAL_PROVIDER_USAGE_SCENARIO@@PEBG1PEAPEAG@Z` at `0x18001ab95`
- `CredProvCommonCore!__imp_?FormatLastLoggedOn@@YAJW4_CREDENTIAL_PROVIDER_USAGE_SCENARIO@@PEBG1PEAPEAG@Z` at `0x18001ab95`
- `KERNEL32!LocalFree` at `0x18001ab4c`
- `KERNEL32!LocalFree` at `0x18001ab4c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001ac10`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001ac10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ac63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ac63`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001abc8`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001abc8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001ab23`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001ab23`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x18001ab35`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x18001ab35`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CProcessStateManager::RecordSuccessfulLogon(
        CProcessStateManager *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  CProcessStateManager *v10; // rcx
  int v11; // [rsp+20h] [rbp-60h] BYREF
  PSID Sid; // [rsp+28h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  __int64 v14; // [rsp+38h] [rbp-48h]
  __int64 v15; // [rsp+40h] [rbp-40h]
  const unsigned __int16 *v16; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-30h] BYREF

  v16 = a4;
  v11 = 0;
  if ( (unsigned __int8)IsCamGetCandidateAccountCredzPresent() && a4 )
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(a4, &Sid) && (int)CamIsCandidateUser(Sid, &v11) < 0 )
      v11 = 0;
    if ( Sid )
      LocalFree(Sid);
  }
  pv = 0;
  v14 = 0;
  v15 = 0;
  if ( a2 && *a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    v14 = -1;
    v15 = -1;
    if ( (int)FormatLastLoggedOn(CPUS_LOGON, a2, 0, (unsigned __int16 **)&pv) < 0 )
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (__int64)&pv,
        a2,
        0xFFFFFFFFFFFFFFFFuLL);
    v8 = (const unsigned __int16 *)pv;
    if ( pv && *(_WORD *)pv )
    {
      if ( !v11 )
      {
        if ( !GetSystemMetrics(4096) )
        {
          WriteLastLoggedOnUserinfo((const unsigned __int16 *)pv, a3, a4);
          if ( a4 )
          {
            Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&Sid, (char *)this + 416);
            Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 432, &v16);
            if ( Sid )
              ReleaseSRWLockExclusive((PSRWLOCK)Sid);
          }
        }
        v8 = (const unsigned __int16 *)pv;
      }
      WriteLoggedOnUserinfo(v8, a3, a4);
    }
  }
  if ( a4 )
  {
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v17, &v16);
    CProcessStateManager::_SetUserSid(this, *(HSTRING *)(v9 + 24), 1);
  }
  CProcessStateManager::_WriteColorKeysIfNecessary(this, a4);
  CProcessStateManager::_ResetUserSwitchState(v10);
  if ( pv )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x18001aad0  push    rbp
0x18001aad2  push    rbx
0x18001aad3  push    rsi
0x18001aad4  push    rdi
0x18001aad5  push    r12
0x18001aad7  push    r14
0x18001aad9  push    r15
0x18001aadb  mov     rbp, rsp
0x18001aade  sub     rsp, 80h
0x18001aae5  mov     rax, cs:__security_cookie
0x18001aaec  xor     rax, rsp
0x18001aaef  mov     [rbp+var_10], rax
0x18001aaf3  mov     rbx, r9
0x18001aaf6  mov     r14, r8
0x18001aaf9  mov     rdi, rdx
0x18001aafc  mov     rsi, rcx
0x18001aaff  mov     [rbp+var_38], rbx
0x18001ab03  xor     r15d, r15d
0x18001ab06  mov     [rbp+var_60], r15d
0x18001ab0a  call    IsCamGetCandidateAccountCredzPresent
0x18001ab0f  test    al, al
0x18001ab11  jz      short loc_18001AB52
0x18001ab13  test    rbx, rbx
0x18001ab16  jz      short loc_18001AB52
0x18001ab18  mov     [rbp+Sid], r15
0x18001ab1c  lea     rdx, [rbp+Sid]; Sid
0x18001ab20  mov     rcx, rbx; StringSid
0x18001ab23  call    cs:__imp_ConvertStringSidToSidW
0x18001ab29  test    eax, eax
0x18001ab2b  jz      short loc_18001AB43
0x18001ab2d  lea     rdx, [rbp+var_60]
0x18001ab31  mov     rcx, [rbp+Sid]
0x18001ab35  call    cs:__imp_CamIsCandidateUser
0x18001ab3b  test    eax, eax
0x18001ab3d  jns     short loc_18001AB43
0x18001ab3f  mov     [rbp+var_60], r15d
0x18001ab43  mov     rcx, [rbp+Sid]; hMem
0x18001ab47  test    rcx, rcx
0x18001ab4a  jz      short loc_18001AB52
0x18001ab4c  call    cs:__imp_LocalFree
0x18001ab52  mov     [rbp+pv], r15
0x18001ab56  mov     [rbp+var_48], r15
0x18001ab5a  mov     [rbp+var_40], r15
0x18001ab5e  test    rdi, rdi
0x18001ab61  jz      loc_18001AC26
0x18001ab67  cmp     [rdi], r15w
0x18001ab6b  jz      loc_18001AC26
0x18001ab71  lea     rcx, [rbp+pv]
0x18001ab75  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001ab7a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001ab7e  mov     [rbp+var_48], r12
0x18001ab82  mov     [rbp+var_40], r12
0x18001ab86  lea     r9, [rbp+pv]
0x18001ab8a  xor     r8d, r8d
0x18001ab8d  mov     rdx, rdi
0x18001ab90  lea     ecx, [r12+2]
0x18001ab95  call    cs:__imp_?FormatLastLoggedOn@@YAJW4_CREDENTIAL_PROVIDER_USAGE_SCENARIO@@PEBG1PEAPEAG@Z; FormatLastLoggedOn(_CREDENTIAL_PROVIDER_USAGE_SCENARIO,ushort const *,ushort const *,ushort * *)
0x18001ab9b  test    eax, eax
0x18001ab9d  jns     short loc_18001ABAE
0x18001ab9f  mov     r8, r12
0x18001aba2  mov     rdx, rdi
0x18001aba5  lea     rcx, [rbp+pv]
0x18001aba9  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001abae  mov     rcx, [rbp+pv]
0x18001abb2  test    rcx, rcx
0x18001abb5  jz      short loc_18001AC26
0x18001abb7  cmp     [rcx], r15w
0x18001abbb  jz      short loc_18001AC26
0x18001abbd  cmp     [rbp+var_60], r15d
0x18001abc1  jnz     short loc_18001AC1A
0x18001abc3  mov     ecx, 1000h; nIndex
0x18001abc8  call    cs:__imp_GetSystemMetrics
0x18001abce  test    eax, eax
0x18001abd0  jnz     short loc_18001AC16
0x18001abd2  mov     r8, rbx
0x18001abd5  mov     rdx, r14
0x18001abd8  mov     rcx, [rbp+pv]
0x18001abdc  call    cs:__imp_?WriteLastLoggedOnUserinfo@@YAXPEBG00@Z; WriteLastLoggedOnUserinfo(ushort const *,ushort const *,ushort const *)
0x18001abe2  test    rbx, rbx
0x18001abe5  jz      short loc_18001AC16
0x18001abe7  lea     rdx, [rsi+1A0h]
0x18001abee  lea     rcx, [rbp+Sid]
0x18001abf2  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001abf7  lea     rcx, [rsi+1B0h]
0x18001abfe  lea     rdx, [rbp+var_38]
0x18001ac02  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ac07  mov     rcx, [rbp+Sid]; SRWLock
0x18001ac0b  test    rcx, rcx
0x18001ac0e  jz      short loc_18001AC16
0x18001ac10  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ac16  mov     rcx, [rbp+pv]
0x18001ac1a  mov     r8, rbx
0x18001ac1d  mov     rdx, r14
0x18001ac20  call    cs:__imp_?WriteLoggedOnUserinfo@@YAXPEBG00@Z; WriteLoggedOnUserinfo(ushort const *,ushort const *,ushort const *)
0x18001ac26  test    rbx, rbx
0x18001ac29  jz      short loc_18001AC49
0x18001ac2b  lea     rdx, [rbp+var_38]
0x18001ac2f  lea     rcx, [rbp+var_30]
0x18001ac33  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ac38  nop
0x18001ac39  mov     r8b, 1; bool
0x18001ac3c  mov     rdx, [rax+18h]; HSTRING
0x18001ac40  mov     rcx, rsi; this
0x18001ac43  call    ?_SetUserSid@CProcessStateManager@@AEAAJPEAUHSTRING__@@_N@Z; CProcessStateManager::_SetUserSid(HSTRING__ *,bool)
0x18001ac48  nop
0x18001ac49  mov     rdx, rbx; unsigned __int16 *
0x18001ac4c  mov     rcx, rsi; this
0x18001ac4f  call    ?_WriteColorKeysIfNecessary@CProcessStateManager@@AEAAXPEBG@Z; CProcessStateManager::_WriteColorKeysIfNecessary(ushort const *)
0x18001ac54  call    ?_ResetUserSwitchState@CProcessStateManager@@AEAAXXZ; CProcessStateManager::_ResetUserSwitchState(void)
0x18001ac59  nop
0x18001ac5a  mov     rcx, [rbp+pv]; pv
0x18001ac5e  test    rcx, rcx
0x18001ac61  jz      short loc_18001AC69
0x18001ac63  call    cs:__imp_CoTaskMemFree
0x18001ac69  mov     rcx, [rbp+var_10]
0x18001ac6d  xor     rcx, rsp; StackCookie
0x18001ac70  call    __security_check_cookie
0x18001ac75  add     rsp, 80h
0x18001ac7c  pop     r15
0x18001ac7e  pop     r14
0x18001ac80  pop     r12
0x18001ac82  pop     rdi
0x18001ac83  pop     rsi
0x18001ac84  pop     rbx
0x18001ac85  pop     rbp
0x18001ac86  retn
```
