# IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)

- ea: `0x1800019d0`
- end: `0x180001c27`
- name: `?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z`
- size: `599`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int, int, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800017d0`

## callees

- `0x1800019d0`
- `0x180001c30`
- `0x180005b70`
- `0x180006010`

## string_xrefs

- `0x180001b77`: `TokenImpersonationLevel`
- `0x180001be6`: `ImpersonationAnonymous`
- `0x180001bdd`: `ImpersonationIdentify`
- `0x180001bd4`: `ImpersonationImpersonate`
- `0x180001bcb`: `ImpersonationDelegate`
- `0x180001bc2`: `ImpersonationUnknown`

## pseudocode

```c
__int64 __fastcall IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned int a7)
{
  __int64 v7; // r8
  const wchar_t *v8; // r9
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rcx
  bool v12; // zf
  int v13; // eax
  const wchar_t *v14; // rax
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v18[5]; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+5Ch] [rbp-A4h]
  __int128 v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+70h] [rbp-90h]
  int v23; // [rsp+74h] [rbp-8Ch]
  int v24; // [rsp+78h] [rbp-88h]
  _QWORD v25[2]; // [rsp+7Ch] [rbp-84h] BYREF
  const wchar_t *v26; // [rsp+90h] [rbp-70h] BYREF
  int v27; // [rsp+98h] [rbp-68h]
  __int64 v28; // [rsp+A0h] [rbp-60h]
  int v29; // [rsp+A8h] [rbp-58h]
  __int64 v30; // [rsp+B0h] [rbp-50h]
  const wchar_t *v31; // [rsp+B8h] [rbp-48h]
  int v32; // [rsp+C0h] [rbp-40h]
  int *v33; // [rsp+C8h] [rbp-38h]
  int v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  const wchar_t *v36; // [rsp+E0h] [rbp-20h]
  int v37; // [rsp+E8h] [rbp-18h]
  int *v38; // [rsp+F0h] [rbp-10h]
  int v39; // [rsp+F8h] [rbp-8h]
  const wchar_t *v40; // [rsp+100h] [rbp+0h]
  const wchar_t *v41; // [rsp+108h] [rbp+8h]
  int v42; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v43; // [rsp+118h] [rbp+18h]
  int v44; // [rsp+120h] [rbp+20h]
  const wchar_t *v45; // [rsp+128h] [rbp+28h]
  const wchar_t *v46; // [rsp+130h] [rbp+30h]
  int v47; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v48; // [rsp+140h] [rbp+40h]
  int v49; // [rsp+148h] [rbp+48h]
  const wchar_t *v50; // [rsp+150h] [rbp+50h]
  const wchar_t *v51; // [rsp+158h] [rbp+58h]
  int v52; // [rsp+160h] [rbp+60h]
  unsigned int *v53; // [rsp+168h] [rbp+68h]
  int v54; // [rsp+170h] [rbp+70h]
  const wchar_t *v55; // [rsp+178h] [rbp+78h]

  v16 = 4;
  memset(v25, 0, 12);
  v17 = 0;
  v18[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v18[1] = 2;
  v18[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
  v18[3] = 11;
  v18[4] = L"AUTH_SUCCEEDED";
  v26 = L"ContextId";
  v31 = L"AuthType";
  v33 = &v16;
  v19 = 1;
  v20 = 4;
  v24 = 6;
  v21 = 0;
  v22 = 0;
  v23 = 1;
  v27 = 72;
  v28 = 0;
  v29 = 16;
  v30 = 0;
  v32 = 19;
  v34 = 4;
  v35 = IISAuthenticationEvents::AUTH_SUCCEEDED::TranslateEnumAuthTypeToString(4, a2, a1);
  v36 = L"NTLMUsed";
  v38 = &v17;
  v41 = L"RemoteUserName";
  v9 = -1;
  v37 = 11;
  v39 = 4;
  v40 = v8;
  v42 = 31;
  v43 = a5;
  if ( a5 )
  {
    v11 = -1;
    do
      v12 = a5[++v11] == (unsigned __int16)v8;
    while ( !v12 );
    v10 = 2 * v11 + 2;
  }
  else
  {
    v10 = (int)v8;
  }
  v44 = v10;
  v46 = L"AuthUserName";
  v45 = v8;
  v47 = 31;
  v48 = a6;
  if ( a6 )
  {
    do
      v12 = a6[++v9] == (unsigned __int16)v8;
    while ( !v12 );
    v13 = 2 * v9 + 2;
  }
  else
  {
    v13 = (int)v8;
  }
  v49 = v13;
  v51 = L"TokenImpersonationLevel";
  v53 = &a7;
  v50 = v8;
  v52 = 19;
  v54 = 4;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1u:
        v14 = L"ImpersonationIdentify";
        break;
      case 2u:
        v14 = L"ImpersonationImpersonate";
        break;
      case 3u:
        v14 = L"ImpersonationDelegate";
        break;
      case 4u:
        v14 = L"ImpersonationUnknown";
        break;
      default:
        v14 = v8;
        break;
    }
  }
  else
  {
    v14 = L"ImpersonationAnonymous";
  }
  v55 = v14;
  *(_QWORD *)((char *)v25 + 4) = &v26;
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 16LL))(v7, v18);
  return 0;
}

```

## disassembly

```asm
0x1800019d0  push    rbp
0x1800019d2  lea     rbp, [rsp-90h]
0x1800019da  sub     rsp, 190h
0x1800019e1  mov     rax, cs:__security_cookie
0x1800019e8  xor     rax, rsp
0x1800019eb  mov     [rbp+90h+var_10], rax
0x1800019f2  xor     eax, eax
0x1800019f4  mov     [rsp+190h+var_170], 4
0x1800019fc  mov     [rsp+190h+var_114], rax
0x180001a01  xor     r9d, r9d
0x180001a04  mov     [rbp+90h+var_10C], eax
0x180001a07  mov     r8, rcx
0x180001a0a  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001a11  mov     [rsp+190h+var_168], r9d
0x180001a16  mov     [rsp+190h+var_160], rax
0x180001a1b  xorps   xmm0, xmm0
0x180001a1e  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180001a25  mov     [rsp+190h+var_158], 2
0x180001a2e  mov     [rsp+190h+var_150], rax
0x180001a33  mov     ecx, 4
0x180001a38  lea     rax, aAuthSucceeded; "AUTH_SUCCEEDED"
0x180001a3f  mov     [rsp+190h+var_148], 0Bh
0x180001a48  mov     [rsp+190h+var_140], rax
0x180001a4d  lea     rax, aContextid; "ContextId"
0x180001a54  mov     [rbp+90h+var_100], rax
0x180001a58  lea     rax, aAuthtype; "AuthType"
0x180001a5f  mov     [rbp+90h+var_D8], rax
0x180001a63  lea     rax, [rsp+190h+var_170]
0x180001a68  mov     [rbp+90h+var_C8], rax
0x180001a6c  mov     [rsp+190h+var_138], 1
0x180001a74  mov     [rsp+190h+var_134], 4
0x180001a7c  mov     [rsp+190h+var_118], 6
0x180001a84  movdqa  [rsp+190h+var_130], xmm0
0x180001a8a  mov     [rsp+190h+var_120], r9d
0x180001a8f  mov     [rsp+190h+var_11C], 1
0x180001a97  mov     [rbp+90h+var_F8], 48h ; 'H'
0x180001a9e  mov     [rbp+90h+var_F0], r9
0x180001aa2  mov     [rbp+90h+var_E8], 10h
0x180001aa9  mov     [rbp+90h+var_E0], r9
0x180001aad  mov     [rbp+90h+var_D0], 13h
0x180001ab4  mov     [rbp+90h+var_C0], 4
0x180001abb  call    ?TranslateEnumAuthTypeToString@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAPEBGW4enumAuthType@12@@Z; IISAuthenticationEvents::AUTH_SUCCEEDED::TranslateEnumAuthTypeToString(IISAuthenticationEvents::AUTH_SUCCEEDED::enumAuthType)
0x180001ac0  mov     rdx, [rbp+90h+arg_20]
0x180001ac7  mov     [rbp+90h+var_B8], rax
0x180001acb  lea     rax, aNtlmused; "NTLMUsed"
0x180001ad2  mov     [rbp+90h+var_B0], rax
0x180001ad6  lea     rax, [rsp+190h+var_168]
0x180001adb  mov     [rbp+90h+var_A0], rax
0x180001adf  lea     rax, aRemoteusername; "RemoteUserName"
0x180001ae6  mov     [rbp+90h+var_88], rax
0x180001aea  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001af1  mov     [rbp+90h+var_A8], 0Bh
0x180001af8  mov     [rbp+90h+var_98], 4
0x180001aff  mov     [rbp+90h+var_90], r9
0x180001b03  mov     [rbp+90h+var_80], 1Fh
0x180001b0a  mov     [rbp+90h+var_78], rdx
0x180001b0e  test    rdx, rdx
0x180001b11  jnz     short loc_180001B18
0x180001b13  mov     ecx, r9d
0x180001b16  jmp     short loc_180001B33
0x180001b18  mov     rcx, rax
0x180001b1b  nop     dword ptr [rax+rax+00h]
0x180001b20  cmp     [rdx+rcx*2+2], r9w
0x180001b26  lea     rcx, [rcx+1]
0x180001b2a  jnz     short loc_180001B20
0x180001b2c  lea     ecx, ds:2[rcx*2]
0x180001b33  mov     [rbp+90h+var_70], ecx
0x180001b36  lea     rcx, aAuthusername; "AuthUserName"
0x180001b3d  mov     [rbp+90h+var_60], rcx
0x180001b41  mov     rcx, [rbp+90h+arg_28]
0x180001b48  mov     [rbp+90h+var_68], r9
0x180001b4c  mov     [rbp+90h+var_58], 1Fh
0x180001b53  mov     [rbp+90h+var_50], rcx
0x180001b57  test    rcx, rcx
0x180001b5a  jnz     short loc_180001B61
0x180001b5c  mov     eax, r9d
0x180001b5f  jmp     short loc_180001B74
0x180001b61  cmp     [rcx+rax*2+2], r9w
0x180001b67  lea     rax, [rax+1]
0x180001b6b  jnz     short loc_180001B61
0x180001b6d  lea     eax, ds:2[rax*2]
0x180001b74  mov     [rbp+90h+var_48], eax
0x180001b77  lea     rax, aTokenimpersona; "TokenImpersonationLevel"
0x180001b7e  mov     [rbp+90h+var_38], rax
0x180001b82  lea     rax, [rbp+90h+arg_30]
0x180001b89  mov     [rbp+90h+var_28], rax
0x180001b8d  mov     eax, [rbp+90h+arg_30]
0x180001b93  mov     [rbp+90h+var_40], r9
0x180001b97  mov     [rbp+90h+var_30], 13h
0x180001b9e  mov     [rbp+90h+var_20], 4
0x180001ba5  test    eax, eax
0x180001ba7  jz      short loc_180001BE6
0x180001ba9  sub     eax, 1
0x180001bac  jz      short loc_180001BDD
0x180001bae  sub     eax, 1
0x180001bb1  jz      short loc_180001BD4
0x180001bb3  sub     eax, 1
0x180001bb6  jz      short loc_180001BCB
0x180001bb8  cmp     eax, 1
0x180001bbb  jz      short loc_180001BC2
0x180001bbd  mov     rax, r9
0x180001bc0  jmp     short loc_180001BED
0x180001bc2  lea     rax, aImpersonationu; "ImpersonationUnknown"
0x180001bc9  jmp     short loc_180001BED
0x180001bcb  lea     rax, aImpersonationd; "ImpersonationDelegate"
0x180001bd2  jmp     short loc_180001BED
0x180001bd4  lea     rax, aImpersonationi; "ImpersonationImpersonate"
0x180001bdb  jmp     short loc_180001BED
0x180001bdd  lea     rax, aImpersonationi_0; "ImpersonationIdentify"
0x180001be4  jmp     short loc_180001BED
0x180001be6  lea     rax, aImpersonationa; "ImpersonationAnonymous"
0x180001bed  mov     [rbp+90h+var_18], rax
0x180001bf1  lea     rdx, [rsp+190h+var_160]
0x180001bf6  lea     rax, [rbp+90h+var_100]
0x180001bfa  mov     rcx, r8
0x180001bfd  mov     [rbp+90h+var_114+4], rax
0x180001c01  mov     rax, [r8]
0x180001c04  mov     rax, [rax+10h]
0x180001c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c0d  xor     eax, eax
0x180001c0f  mov     rcx, [rbp+90h+var_10]
0x180001c16  xor     rcx, rsp; StackCookie
0x180001c19  call    __security_check_cookie
0x180001c1e  add     rsp, 190h
0x180001c25  pop     rbp
0x180001c26  retn
```
