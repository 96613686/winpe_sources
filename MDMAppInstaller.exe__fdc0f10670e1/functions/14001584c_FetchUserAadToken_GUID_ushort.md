# FetchUserAadToken(_GUID,ushort * *)

- ea: `0x14001584c`
- end: `0x140015a30`
- name: `?FetchUserAadToken@@YAJU_GUID@@PEAPEAG@Z`
- size: `484`
- prototype: `__int64 __fastcall(struct _GUID *, HLOCAL *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140010a2c`

## callees

- `0x140007318`
- `0x14000740c`
- `0x1400074d4`
- `0x14001584c`
- `0x140017a88`
- `0x140018140`
- `0x14001a886`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x140015a13`
- `ADVAPI32!RevertToSelf` at `0x140015a13`
- `KERNEL32!LocalFree` at `0x140015a00`
- `KERNEL32!LocalFree` at `0x140015a00`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x140015939`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x140015939`
- `dmEnrollEngine!GetEnrollmentType` at `0x1400158ed`
- `dmEnrollEngine!GetEnrollmentType` at `0x1400158ed`
- `DMCmnUtils!DmGetAadUserToken` at `0x1400159c6`
- `DMCmnUtils!DmGetAadUserToken` at `0x1400159c6`
- `DMCmnUtils!DmGetActiveUserSid` at `0x14001595a`
- `DMCmnUtils!DmGetActiveUserSid` at `0x14001595a`
- `DMCmnUtils!DmImpersonate` at `0x14001597a`
- `DMCmnUtils!DmImpersonate` at `0x14001597a`

## string_xrefs

- `0x1400158bd`: `FetchUserAadToken - IsRunningInSystemContext() failed - Error 0x%1!x!`
- `0x1400158d4`: `FetchUserAadToken - not running as SYSTEM.`
- `0x140015918`: `FetchUserAadToken - Not an AAD enrollment, and not a full MDM enrollment, nothing to do.  eEnrollmentType = %1!d!`
- `0x140015945`: `FetchUserAadToken - Could not retrieve the AAD Resource Url. METHOD_RETVAL=0x%1!x!.`
- `0x140015964`: `FetchUserAadToken - DmGetActiveUserSid failed.  METHOD_RETVAL=0x%1!x!.`
- `0x14001598a`: `FetchUserAadToken - DmImpersonate failed.  METHOD_RETVAL=0x%1!x!. User SID : %s`
- `0x14001599f`: `FetchUserAadToken - Successfully impersonated to User SID : %s`
- `0x1400159d2`: `FetchUserAadToken - Could not retrieve the AAD token.  Is the user an AAD user?  METHOD_RETVAL=0x%1!x!.`

## pseudocode

```c
__int64 __fastcall FetchUserAadToken(struct _GUID *a1, HLOCAL *a2)
{
  int v4; // r14d
  int EnrollmentType; // ebx
  int v6; // eax
  int EnrollmentAadResourceUrl; // eax
  int ActiveUserSid; // eax
  int v9; // eax
  int AadUserToken; // eax
  const unsigned __int16 *v12; // [rsp+30h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-28h] BYREF
  void *v14; // [rsp+40h] [rbp-20h] BYREF
  __int128 v15; // [rsp+50h] [rbp-10h] BYREF
  bool v16; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v17; // [rsp+98h] [rbp+38h] BYREF

  v14 = 0;
  hMem = 0;
  v17 = 63;
  v4 = 0;
  v16 = 0;
  if ( !memcmp_0(a1, &GUID_NULL, 0x10u) )
  {
    LogInfo(L"No MDM enrollment key, nothing to do.");
LABEL_3:
    EnrollmentType = 0;
    goto LABEL_24;
  }
  v6 = IsRunningInSystemContext(&v16);
  EnrollmentType = v6;
  if ( v6 < 0 )
  {
    LogError(L"FetchUserAadToken - IsRunningInSystemContext() failed - Error 0x%1!x!", (unsigned int)v6);
    goto LABEL_24;
  }
  if ( !v16 )
  {
    LogInfo(L"FetchUserAadToken - not running as SYSTEM.");
    goto LABEL_3;
  }
  v15 = (__int128)*a1;
  EnrollmentType = GetEnrollmentType(&v15, &v17);
  if ( EnrollmentType >= 0 )
  {
    if ( ((1LL << v17) & 0x5402060) == 0 && v17 )
    {
      LogInfo(
        L"FetchUserAadToken - Not an AAD enrollment, and not a full MDM enrollment, nothing to do.  eEnrollmentType = %1!d!",
        v17);
      goto LABEL_3;
    }
    v15 = (__int128)*a1;
    EnrollmentAadResourceUrl = GetEnrollmentAadResourceUrl(&v15, &v14);
    if ( EnrollmentAadResourceUrl < 0 )
    {
      LogInfo(
        L"FetchUserAadToken - Could not retrieve the AAD Resource Url. METHOD_RETVAL=0x%1!x!.",
        (unsigned int)EnrollmentAadResourceUrl);
      goto LABEL_3;
    }
    v12 = 0;
    ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&v12);
    if ( ActiveUserSid >= 0 )
    {
      v9 = DmImpersonate(v12);
      if ( v9 >= 0 )
      {
        v4 = 1;
        LogInfo(L"FetchUserAadToken - Successfully impersonated to User SID : %s", v12);
        AadUserToken = DmGetAadUserToken(
                         L"de50c81f-5f80-4771-b66b-cebd28ccdfc1",
                         (const unsigned __int16 *)v14,
                         0,
                         (unsigned __int16 **)&hMem,
                         0);
        EnrollmentType = AadUserToken;
        if ( AadUserToken >= 0 )
        {
          *a2 = hMem;
          hMem = 0;
          goto LABEL_23;
        }
        LogInfo(
          L"FetchUserAadToken - Could not retrieve the AAD token.  Is the user an AAD user?  METHOD_RETVAL=0x%1!x!.",
          (unsigned int)AadUserToken);
      }
      else
      {
        LogInfo(
          L"FetchUserAadToken - DmImpersonate failed.  METHOD_RETVAL=0x%1!x!. User SID : %s",
          (unsigned int)v9,
          v12);
      }
    }
    else
    {
      LogInfo(L"FetchUserAadToken - DmGetActiveUserSid failed.  METHOD_RETVAL=0x%1!x!.", (unsigned int)ActiveUserSid);
    }
    EnrollmentType = 0;
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v12);
  }
LABEL_24:
  SafeHeapFree(v14);
  LocalFree(hMem);
  hMem = 0;
  if ( v4 )
    RevertToSelf();
  return (unsigned int)EnrollmentType;
}

```

## disassembly

```asm
0x14001584c  mov     [rsp-18h+arg_0], rbx
0x140015851  mov     [rsp-18h+arg_8], rsi
0x140015856  push    rbp
0x140015857  push    rdi
0x140015858  push    r14
0x14001585a  mov     rbp, rsp
0x14001585d  sub     rsp, 60h
0x140015861  mov     rsi, rdx
0x140015864  mov     rdi, rcx
0x140015867  mov     [rbp+var_20], 0
0x14001586f  mov     [rbp+hMem], 0
0x140015877  mov     [rbp+arg_18], 3Fh ; '?'
0x14001587e  xor     r14d, r14d
0x140015881  mov     [rbp+arg_10], r14b
0x140015885  lea     r8d, [r14+10h]; Size
0x140015889  lea     rdx, GUID_NULL; Buf2
0x140015890  call    memcmp_0
0x140015895  test    eax, eax
0x140015897  jnz     short loc_1400158AC
0x140015899  lea     rcx, aNoMdmEnrollmen; "No MDM enrollment key, nothing to do."
0x1400158a0  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x1400158a5  xor     ebx, ebx
0x1400158a7  jmp     loc_1400159F3
0x1400158ac  lea     rcx, [rbp+arg_10]; bool *
0x1400158b0  call    ?IsRunningInSystemContext@@YAJAEA_N@Z; IsRunningInSystemContext(bool &)
0x1400158b5  mov     ebx, eax
0x1400158b7  test    eax, eax
0x1400158b9  jns     short loc_1400158CE
0x1400158bb  mov     edx, eax
0x1400158bd  lea     rcx, aFetchuseraadto_3; "FetchUserAadToken - IsRunningInSystemCo"...
0x1400158c4  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400158c9  jmp     loc_1400159F3
0x1400158ce  cmp     [rbp+arg_10], r14b
0x1400158d2  jnz     short loc_1400158DD
0x1400158d4  lea     rcx, aFetchuseraadto_0; "FetchUserAadToken - not running as SYST"...
0x1400158db  jmp     short loc_1400158A0
0x1400158dd  movaps  xmm0, xmmword ptr [rdi]
0x1400158e0  movdqa  [rbp+var_10], xmm0
0x1400158e5  lea     rdx, [rbp+arg_18]
0x1400158e9  lea     rcx, [rbp+var_10]
0x1400158ed  call    cs:__imp_GetEnrollmentType
0x1400158f3  mov     ebx, eax
0x1400158f5  test    eax, eax
0x1400158f7  js      loc_1400159F3
0x1400158fd  mov     ecx, [rbp+arg_18]
0x140015900  mov     ebx, 1
0x140015905  mov     eax, ebx
0x140015907  shl     rax, cl
0x14001590a  test    rax, 5402060h
0x140015910  jnz     short loc_140015929
0x140015912  test    ecx, ecx
0x140015914  jz      short loc_140015929
0x140015916  mov     edx, ecx
0x140015918  lea     rcx, aFetchuseraadto_4; "FetchUserAadToken - Not an AAD enrollme"...
0x14001591f  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140015924  jmp     loc_1400158A5
0x140015929  movaps  xmm0, xmmword ptr [rdi]
0x14001592c  movdqa  [rbp+var_10], xmm0
0x140015931  lea     rdx, [rbp+var_20]
0x140015935  lea     rcx, [rbp+var_10]
0x140015939  call    cs:__imp_GetEnrollmentAadResourceUrl
0x14001593f  test    eax, eax
0x140015941  jns     short loc_14001594E
0x140015943  mov     edx, eax
0x140015945  lea     rcx, aFetchuseraadto_6; "FetchUserAadToken - Could not retrieve "...
0x14001594c  jmp     short loc_14001591F
0x14001594e  mov     [rbp+var_30], 0
0x140015956  lea     rcx, [rbp+var_30]
0x14001595a  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x140015960  test    eax, eax
0x140015962  jns     short loc_140015976
0x140015964  lea     rcx, aFetchuseraadto_2; "FetchUserAadToken - DmGetActiveUserSid "...
0x14001596b  mov     edx, eax
0x14001596d  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140015972  xor     ebx, ebx
0x140015974  jmp     short loc_1400159EA
0x140015976  mov     rcx, [rbp+var_30]
0x14001597a  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x140015980  test    eax, eax
0x140015982  jns     short loc_140015998
0x140015984  mov     r8, [rbp+var_30]
0x140015988  mov     edx, eax
0x14001598a  lea     rcx, aFetchuseraadto; "FetchUserAadToken - DmImpersonate faile"...
0x140015991  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140015996  jmp     short loc_140015972
0x140015998  mov     r14d, ebx
0x14001599b  mov     rdx, [rbp+var_30]
0x14001599f  lea     rcx, aFetchuseraadto_5; "FetchUserAadToken - Successfully impers"...
0x1400159a6  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x1400159ab  mov     [rsp+60h+var_40], 0
0x1400159b4  lea     r9, [rbp+hMem]
0x1400159b8  xor     r8d, r8d
0x1400159bb  mov     rdx, [rbp+var_20]
0x1400159bf  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x1400159c6  call    cs:__imp_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z; DmGetAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *,int *)
0x1400159cc  mov     ebx, eax
0x1400159ce  test    eax, eax
0x1400159d0  jns     short loc_1400159DB
0x1400159d2  lea     rcx, aFetchuseraadto_1; "FetchUserAadToken - Could not retrieve "...
0x1400159d9  jmp     short loc_14001596B
0x1400159db  mov     rax, [rbp+hMem]
0x1400159df  mov     [rsi], rax
0x1400159e2  mov     [rbp+hMem], 0
0x1400159ea  lea     rcx, [rbp+var_30]
0x1400159ee  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400159f3  mov     rcx, [rbp+var_20]; void *
0x1400159f7  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x1400159fc  mov     rcx, [rbp+hMem]; hMem
0x140015a00  call    cs:__imp_LocalFree
0x140015a06  mov     [rbp+hMem], 0
0x140015a0e  test    r14d, r14d
0x140015a11  jz      short loc_140015A19
0x140015a13  call    cs:__imp_RevertToSelf
0x140015a19  mov     eax, ebx
0x140015a1b  lea     r11, [rsp+60h+var_s0]
0x140015a20  mov     rbx, [r11+20h]
0x140015a24  mov     rsi, [r11+28h]
0x140015a28  mov     rsp, r11
0x140015a2b  pop     r14
0x140015a2d  pop     rdi
0x140015a2e  pop     rbp
0x140015a2f  retn
```
