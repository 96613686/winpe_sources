# FetchUserAadToken(_GUID,ushort * *)

- ea: `0x18012b278`
- end: `0x18012b479`
- name: `?FetchUserAadToken@@YAJU_GUID@@PEAPEAG@Z`
- size: `513`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18012a874`

## callees

- `0x18000c8d0`
- `0x18001d090`
- `0x18004d158`
- `0x18012a500`
- `0x18012b278`
- `0x18012bf94`
- `0x18012c77c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012b40c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012b43f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012b40c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012b43f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18012b41c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18012b44f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18012b41c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18012b44f`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18012b39c`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18012b39c`
- `DMCmnUtils!DmGetAadUserToken` at `0x18012b3e4`
- `DMCmnUtils!DmGetAadUserToken` at `0x18012b3e4`
- `DMCmnUtils!DmImpersonate` at `0x18012b3b3`
- `DMCmnUtils!DmImpersonate` at `0x18012b3b3`
- `dmEnrollEngine!GetEnrollmentType` at `0x18012b326`
- `dmEnrollEngine!GetEnrollmentType` at `0x18012b326`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x18012b37a`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x18012b37a`

## string_xrefs

- `0x18012b2f8`: `FetchUserAadToken - IsRunningInSystemContext() failed - Error 0x%1!x!`
- `0x18012b30a`: `FetchUserAadToken - not running as system context`
- `0x18012b3bd`: `FetchUserAadToken - DmImpersonate failed`
- `0x18012b3f0`: `FetchUserAadToken - DmGetAadUserToken failed`
- `0x18012b334`: `FetchUserAadToken - GetEnrollmentType failed`
- `0x18012b35e`: `FetchUserAadToken - not AAD type enrollment, skipping`
- `0x18012b384`: `FetchUserAadToken - GetEnrollmentAadResourceUrl failed`
- `0x18012b3a6`: `FetchUserAadToken - DmGetActiveUserSid failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FetchUserAadToken(struct _GUID *a1, HLOCAL *a2)
{
  void *v4; // rcx
  int EnrollmentAadResourceUrl; // eax
  const unsigned __int16 *v6; // rcx
  int EnrollmentType; // eax
  unsigned int v8; // ebx
  int v10; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-48h] BYREF
  void *v12; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v13; // [rsp+48h] [rbp-38h] BYREF
  __int128 v14; // [rsp+50h] [rbp-30h] BYREF
  void **v15; // [rsp+60h] [rbp-20h]
  HLOCAL *p_hMem; // [rsp+68h] [rbp-18h]
  int *v17; // [rsp+70h] [rbp-10h]
  char v18; // [rsp+78h] [rbp-8h]
  bool v19; // [rsp+B0h] [rbp+30h] BYREF
  int v20; // [rsp+B8h] [rbp+38h] BYREF

  v12 = 0;
  hMem = 0;
  v10 = 63;
  v20 = 0;
  v19 = 0;
  v13 = 0;
  v15 = &v12;
  p_hMem = &hMem;
  v17 = &v20;
  v18 = 1;
  if ( !memcmp_0(a1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
  {
    v4 = 0;
LABEL_22:
    SafeHeapFree(v4);
    LocalFree(hMem);
    hMem = 0;
    if ( v20 )
      RevertToSelf();
    v8 = 0;
    goto LABEL_28;
  }
  EnrollmentAadResourceUrl = IsRunningInSystemContext(&v19);
  if ( EnrollmentAadResourceUrl < 0 )
  {
    v6 = L"FetchUserAadToken - IsRunningInSystemContext() failed - Error 0x%1!x!";
LABEL_20:
    LogTelemetryError(v6, (unsigned int)EnrollmentAadResourceUrl);
    goto LABEL_21;
  }
  if ( !v19 )
  {
    v6 = L"FetchUserAadToken - not running as system context";
    goto LABEL_20;
  }
  v14 = (__int128)*a1;
  EnrollmentType = GetEnrollmentType(&v14, &v10);
  v8 = EnrollmentType;
  if ( EnrollmentType >= 0 )
  {
    if ( ((1LL << v10) & 0x5402060) == 0 && v10 )
    {
      LogTelemetryError(L"FetchUserAadToken - not AAD type enrollment, skipping", (unsigned int)EnrollmentType);
LABEL_21:
      v4 = v12;
      goto LABEL_22;
    }
    v14 = (__int128)*a1;
    EnrollmentAadResourceUrl = GetEnrollmentAadResourceUrl(&v14, &v12);
    if ( EnrollmentAadResourceUrl < 0 )
    {
      v6 = L"FetchUserAadToken - GetEnrollmentAadResourceUrl failed";
      goto LABEL_20;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v13,
      0);
    EnrollmentAadResourceUrl = DmGetActiveUserSid(&v13);
    if ( EnrollmentAadResourceUrl < 0 )
    {
      v6 = L"FetchUserAadToken - DmGetActiveUserSid failed";
      goto LABEL_20;
    }
    EnrollmentAadResourceUrl = DmImpersonate(v13);
    if ( EnrollmentAadResourceUrl < 0 )
    {
      v6 = L"FetchUserAadToken - DmImpersonate failed";
      goto LABEL_20;
    }
    v20 = 1;
    EnrollmentAadResourceUrl = DmGetAadUserToken(
                                 L"de50c81f-5f80-4771-b66b-cebd28ccdfc1",
                                 (const unsigned __int16 *)v12,
                                 0,
                                 (unsigned __int16 **)&hMem,
                                 0);
    v8 = EnrollmentAadResourceUrl;
    if ( EnrollmentAadResourceUrl < 0 )
    {
      v6 = L"FetchUserAadToken - DmGetAadUserToken failed";
      goto LABEL_20;
    }
    *a2 = hMem;
    hMem = 0;
  }
  else
  {
    LogTelemetryError(L"FetchUserAadToken - GetEnrollmentType failed", (unsigned int)EnrollmentType);
  }
  SafeHeapFree(v12);
  LocalFree(hMem);
  hMem = 0;
  if ( v20 )
    RevertToSelf();
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
  return v8;
}

```

## disassembly

```asm
0x18012b278  mov     [rsp-18h+arg_0], rbx
0x18012b27d  mov     [rsp-18h+arg_8], rsi
0x18012b282  push    rbp
0x18012b283  push    rdi
0x18012b284  push    r14
0x18012b286  mov     rbp, rsp
0x18012b289  sub     rsp, 80h
0x18012b290  mov     rsi, rdx
0x18012b293  mov     rdi, rcx
0x18012b296  xor     r14d, r14d
0x18012b299  mov     [rbp+var_40], r14
0x18012b29d  mov     [rbp+hMem], r14
0x18012b2a1  mov     [rbp+var_50], 3Fh ; '?'
0x18012b2a8  mov     [rbp+arg_18], r14d
0x18012b2ac  mov     [rbp+arg_10], r14b
0x18012b2b0  mov     [rbp+var_38], r14
0x18012b2b4  lea     rax, [rbp+var_40]
0x18012b2b8  mov     [rbp+var_20], rax
0x18012b2bc  lea     rax, [rbp+hMem]
0x18012b2c0  mov     [rbp+var_18], rax
0x18012b2c4  lea     rax, [rbp+arg_18]
0x18012b2c8  mov     [rbp+var_10], rax
0x18012b2cc  mov     [rbp+var_8], 1
0x18012b2d0  lea     r8d, [r14+10h]; Size
0x18012b2d4  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18012b2db  call    memcmp_0
0x18012b2e0  test    eax, eax
0x18012b2e2  jnz     short loc_18012B2EB
0x18012b2e4  xor     ecx, ecx
0x18012b2e6  jmp     loc_18012B403
0x18012b2eb  lea     rcx, [rbp+arg_10]; bool *
0x18012b2ef  call    ?IsRunningInSystemContext@@YAJAEA_N@Z; IsRunningInSystemContext(bool &)
0x18012b2f4  test    eax, eax
0x18012b2f6  jns     short loc_18012B304
0x18012b2f8  lea     rcx, aFetchuseraadto_3; "FetchUserAadToken - IsRunningInSystemCo"...
0x18012b2ff  jmp     loc_18012B3F7
0x18012b304  cmp     [rbp+arg_10], r14b
0x18012b308  jnz     short loc_18012B316
0x18012b30a  lea     rcx, aFetchuseraadto; "FetchUserAadToken - not running as syst"...
0x18012b311  jmp     loc_18012B3F7
0x18012b316  movaps  xmm0, xmmword ptr [rdi]
0x18012b319  movdqa  [rbp+var_30], xmm0
0x18012b31e  lea     rdx, [rbp+var_50]
0x18012b322  lea     rcx, [rbp+var_30]
0x18012b326  call    cs:__imp_GetEnrollmentType
0x18012b32c  mov     ebx, eax
0x18012b32e  test    eax, eax
0x18012b330  jns     short loc_18012B345
0x18012b332  mov     edx, eax
0x18012b334  lea     rcx, aFetchuseraadto_0; "FetchUserAadToken - GetEnrollmentType f"...
0x18012b33b  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012b340  jmp     loc_18012B432
0x18012b345  mov     ecx, [rbp+var_50]
0x18012b348  mov     eax, 1
0x18012b34d  shl     rax, cl
0x18012b350  test    rax, 5402060h
0x18012b356  jnz     short loc_18012B36A
0x18012b358  test    ecx, ecx
0x18012b35a  jz      short loc_18012B36A
0x18012b35c  mov     edx, ebx
0x18012b35e  lea     rcx, aFetchuseraadto_2; "FetchUserAadToken - not AAD type enroll"...
0x18012b365  jmp     loc_18012B3F9
0x18012b36a  movaps  xmm0, xmmword ptr [rdi]
0x18012b36d  movdqa  [rbp+var_30], xmm0
0x18012b372  lea     rdx, [rbp+var_40]
0x18012b376  lea     rcx, [rbp+var_30]
0x18012b37a  call    cs:__imp_GetEnrollmentAadResourceUrl
0x18012b380  test    eax, eax
0x18012b382  jns     short loc_18012B38D
0x18012b384  lea     rcx, aFetchuseraadto_1; "FetchUserAadToken - GetEnrollmentAadRes"...
0x18012b38b  jmp     short loc_18012B3F7
0x18012b38d  xor     edx, edx
0x18012b38f  lea     rcx, [rbp+var_38]
0x18012b393  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18012b398  lea     rcx, [rbp+var_38]
0x18012b39c  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18012b3a2  test    eax, eax
0x18012b3a4  jns     short loc_18012B3AF
0x18012b3a6  lea     rcx, aFetchuseraadto_4; "FetchUserAadToken - DmGetActiveUserSid "...
0x18012b3ad  jmp     short loc_18012B3F7
0x18012b3af  mov     rcx, [rbp+var_38]
0x18012b3b3  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18012b3b9  test    eax, eax
0x18012b3bb  jns     short loc_18012B3C6
0x18012b3bd  lea     rcx, aFetchuseraadto_6; "FetchUserAadToken - DmImpersonate faile"...
0x18012b3c4  jmp     short loc_18012B3F7
0x18012b3c6  mov     [rbp+arg_18], 1
0x18012b3cd  mov     [rsp+80h+var_60], r14
0x18012b3d2  lea     r9, [rbp+hMem]
0x18012b3d6  xor     r8d, r8d
0x18012b3d9  mov     rdx, [rbp+var_40]
0x18012b3dd  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x18012b3e4  call    cs:__imp_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z; DmGetAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *,int *)
0x18012b3ea  mov     ebx, eax
0x18012b3ec  test    eax, eax
0x18012b3ee  jns     short loc_18012B427
0x18012b3f0  lea     rcx, aFetchuseraadto_5; "FetchUserAadToken - DmGetAadUserToken f"...
0x18012b3f7  mov     edx, eax
0x18012b3f9  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012b3fe  nop
0x18012b3ff  mov     rcx, [rbp+var_40]; void *
0x18012b403  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18012b408  mov     rcx, [rbp+hMem]; hMem
0x18012b40c  call    cs:__imp_LocalFree
0x18012b412  cmp     [rbp+arg_18], r14d
0x18012b416  mov     [rbp+hMem], r14
0x18012b41a  jz      short loc_18012B422
0x18012b41c  call    cs:__imp_RevertToSelf
0x18012b422  mov     ebx, r14d
0x18012b425  jmp     short loc_18012B456
0x18012b427  mov     rax, [rbp+hMem]
0x18012b42b  mov     [rsi], rax
0x18012b42e  mov     [rbp+hMem], r14
0x18012b432  mov     rcx, [rbp+var_40]; void *
0x18012b436  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18012b43b  mov     rcx, [rbp+hMem]; hMem
0x18012b43f  call    cs:__imp_LocalFree
0x18012b445  cmp     [rbp+arg_18], r14d
0x18012b449  mov     [rbp+hMem], r14
0x18012b44d  jz      short loc_18012B456
0x18012b44f  call    cs:__imp_RevertToSelf
0x18012b455  nop
0x18012b456  lea     rcx, [rbp+var_38]
0x18012b45a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18012b45f  mov     eax, ebx
0x18012b461  lea     r11, [rsp+80h+var_s0]
0x18012b469  mov     rbx, [r11+20h]
0x18012b46d  mov     rsi, [r11+28h]
0x18012b471  mov     rsp, r11
0x18012b474  pop     r14
0x18012b476  pop     rdi
0x18012b477  pop     rbp
0x18012b478  retn
```
