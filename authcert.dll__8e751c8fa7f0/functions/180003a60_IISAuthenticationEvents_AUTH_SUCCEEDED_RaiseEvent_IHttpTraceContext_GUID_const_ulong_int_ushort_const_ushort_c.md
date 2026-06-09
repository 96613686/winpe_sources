# IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)

- ea: `0x180003a60`
- end: `0x180003c96`
- name: `?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z`
- size: `566`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int, int, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003c9c`

## callees

- `0x180003a60`
- `0x180003ef0`
- `0x180005010`

## string_xrefs

- `0x180003c55`: `ImpersonationAnonymous`
- `0x180003c4c`: `ImpersonationIdentify`
- `0x180003c43`: `ImpersonationImpersonate`
- `0x180003c3a`: `ImpersonationDelegate`
- `0x180003c31`: `ImpersonationUnknown`
- `0x180003be9`: `TokenImpersonationLevel`

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
  __int64 v8; // rax
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // eax
  const wchar_t *v12; // rax
  int v14; // [rsp+20h] [rbp-E0h] BYREF
  int v15; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v16[5]; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h]
  __int128 v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+74h] [rbp-8Ch]
  int v22; // [rsp+78h] [rbp-88h]
  _QWORD v23[2]; // [rsp+7Ch] [rbp-84h] BYREF
  const wchar_t *v24; // [rsp+90h] [rbp-70h] BYREF
  int v25; // [rsp+98h] [rbp-68h]
  __int64 v26; // [rsp+A0h] [rbp-60h]
  int v27; // [rsp+A8h] [rbp-58h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  const wchar_t *v29; // [rsp+B8h] [rbp-48h]
  int v30; // [rsp+C0h] [rbp-40h]
  int *v31; // [rsp+C8h] [rbp-38h]
  int v32; // [rsp+D0h] [rbp-30h]
  const wchar_t *v33; // [rsp+D8h] [rbp-28h]
  const wchar_t *v34; // [rsp+E0h] [rbp-20h]
  int v35; // [rsp+E8h] [rbp-18h]
  int *v36; // [rsp+F0h] [rbp-10h]
  int v37; // [rsp+F8h] [rbp-8h]
  __int64 v38; // [rsp+100h] [rbp+0h]
  const wchar_t *v39; // [rsp+108h] [rbp+8h]
  int v40; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v41; // [rsp+118h] [rbp+18h]
  int v42; // [rsp+120h] [rbp+20h]
  __int64 v43; // [rsp+128h] [rbp+28h]
  const wchar_t *v44; // [rsp+130h] [rbp+30h]
  int v45; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v46; // [rsp+140h] [rbp+40h]
  int v47; // [rsp+148h] [rbp+48h]
  __int64 v48; // [rsp+150h] [rbp+50h]
  const wchar_t *v49; // [rsp+158h] [rbp+58h]
  int v50; // [rsp+160h] [rbp+60h]
  unsigned int *v51; // [rsp+168h] [rbp+68h]
  int v52; // [rsp+170h] [rbp+70h]
  const wchar_t *v53; // [rsp+178h] [rbp+78h]

  memset(v23, 0, 12);
  v15 = 0;
  v16[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v16[1] = 2;
  v14 = 4;
  v16[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
  v16[3] = 11;
  v16[4] = L"AUTH_SUCCEEDED";
  v18 = 4;
  v17 = 1;
  v21 = 1;
  v24 = L"ContextId";
  v29 = L"AuthType";
  v31 = &v14;
  v33 = L"NT";
  v34 = L"NTLMUsed";
  v36 = &v15;
  v39 = L"RemoteUserName";
  v8 = -1;
  v22 = 6;
  v19 = 0;
  v20 = 0;
  v25 = 72;
  v26 = 0;
  v27 = 16;
  v28 = 0;
  v30 = 19;
  v32 = 4;
  v35 = 11;
  v37 = 4;
  v38 = 0;
  v40 = 31;
  v41 = a5;
  if ( a5 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a5[v10] );
    v9 = 2 * v10 + 2;
  }
  else
  {
    v9 = 0;
  }
  v42 = v9;
  v44 = L"AuthUserName";
  v43 = 0;
  v45 = 31;
  v46 = a6;
  if ( a6 )
  {
    do
      ++v8;
    while ( a6[v8] );
    v11 = 2 * v8 + 2;
  }
  else
  {
    v11 = 0;
  }
  v47 = v11;
  v49 = L"TokenImpersonationLevel";
  v51 = &a7;
  v48 = 0;
  v50 = 19;
  v52 = 4;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1u:
        v12 = L"ImpersonationIdentify";
        break;
      case 2u:
        v12 = L"ImpersonationImpersonate";
        break;
      case 3u:
        v12 = L"ImpersonationDelegate";
        break;
      case 4u:
        v12 = L"ImpersonationUnknown";
        break;
      default:
        v12 = 0;
        break;
    }
  }
  else
  {
    v12 = L"ImpersonationAnonymous";
  }
  v53 = v12;
  *(_QWORD *)((char *)v23 + 4) = &v24;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v16);
  return 0;
}

```

## disassembly

```asm
0x180003a60  push    rbp
0x180003a62  lea     rbp, [rsp-90h]
0x180003a6a  sub     rsp, 190h
0x180003a71  mov     rax, cs:__security_cookie
0x180003a78  xor     rax, rsp
0x180003a7b  mov     [rbp+90h+var_10], rax
0x180003a82  mov     rdx, [rbp+90h+arg_20]
0x180003a89  xor     eax, eax
0x180003a8b  mov     [rsp+190h+var_114], rax
0x180003a90  xor     r9d, r9d
0x180003a93  mov     [rbp+90h+var_10C], eax
0x180003a96  mov     r8, rcx
0x180003a99  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180003aa0  mov     [rsp+190h+var_168], r9d
0x180003aa5  mov     [rsp+190h+var_160], rax
0x180003aaa  xorps   xmm0, xmm0
0x180003aad  lea     r10d, [r9+4]
0x180003ab1  mov     [rsp+190h+var_158], 2
0x180003aba  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180003ac1  mov     [rsp+190h+var_170], r10d
0x180003ac6  mov     [rsp+190h+var_150], rax
0x180003acb  lea     ecx, [r9+0Bh]
0x180003acf  lea     rax, aAuthSucceeded; "AUTH_SUCCEEDED"
0x180003ad6  mov     [rsp+190h+var_148], 0Bh
0x180003adf  mov     [rsp+190h+var_140], rax
0x180003ae4  lea     r11d, [r9+1Fh]
0x180003ae8  lea     eax, [rcx-0Ah]
0x180003aeb  mov     [rsp+190h+var_134], r10d
0x180003af0  mov     [rsp+190h+var_138], eax
0x180003af4  mov     [rsp+190h+var_11C], eax
0x180003af8  lea     rax, aContextid; "ContextId"
0x180003aff  mov     [rbp+90h+var_100], rax
0x180003b03  lea     rax, aAuthtype; "AuthType"
0x180003b0a  mov     [rbp+90h+var_D8], rax
0x180003b0e  lea     rax, [rsp+190h+var_170]
0x180003b13  mov     [rbp+90h+var_C8], rax
0x180003b17  lea     rax, aNt; "NT"
0x180003b1e  mov     [rbp+90h+var_B8], rax
0x180003b22  lea     rax, aNtlmused; "NTLMUsed"
0x180003b29  mov     [rbp+90h+var_B0], rax
0x180003b2d  lea     rax, [rsp+190h+var_168]
0x180003b32  mov     [rbp+90h+var_A0], rax
0x180003b36  lea     rax, aRemoteusername; "RemoteUserName"
0x180003b3d  mov     [rbp+90h+var_88], rax
0x180003b41  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003b45  mov     [rsp+190h+var_118], 6
0x180003b4d  movdqa  [rsp+190h+var_130], xmm0
0x180003b53  mov     [rsp+190h+var_120], r9d
0x180003b58  mov     [rbp+90h+var_F8], 48h ; 'H'
0x180003b5f  mov     [rbp+90h+var_F0], r9
0x180003b63  mov     [rbp+90h+var_E8], 10h
0x180003b6a  mov     [rbp+90h+var_E0], r9
0x180003b6e  mov     [rbp+90h+var_D0], 13h
0x180003b75  mov     [rbp+90h+var_C0], r10d
0x180003b79  mov     [rbp+90h+var_A8], ecx
0x180003b7c  mov     [rbp+90h+var_98], r10d
0x180003b80  mov     [rbp+90h+var_90], r9
0x180003b84  mov     [rbp+90h+var_80], r11d
0x180003b88  mov     [rbp+90h+var_78], rdx
0x180003b8c  test    rdx, rdx
0x180003b8f  jnz     short loc_180003B96
0x180003b91  mov     ecx, r9d
0x180003b94  jmp     short loc_180003BAA
0x180003b96  mov     rcx, rax
0x180003b99  inc     rcx
0x180003b9c  cmp     [rdx+rcx*2], r9w
0x180003ba1  jnz     short loc_180003B99
0x180003ba3  lea     ecx, ds:2[rcx*2]
0x180003baa  mov     [rbp+90h+var_70], ecx
0x180003bad  lea     rcx, aAuthusername; "AuthUserName"
0x180003bb4  mov     [rbp+90h+var_60], rcx
0x180003bb8  mov     rcx, [rbp+90h+arg_28]
0x180003bbf  mov     [rbp+90h+var_68], r9
0x180003bc3  mov     [rbp+90h+var_58], r11d
0x180003bc7  mov     [rbp+90h+var_50], rcx
0x180003bcb  test    rcx, rcx
0x180003bce  jnz     short loc_180003BD5
0x180003bd0  mov     eax, r9d
0x180003bd3  jmp     short loc_180003BE6
0x180003bd5  inc     rax
0x180003bd8  cmp     [rcx+rax*2], r9w
0x180003bdd  jnz     short loc_180003BD5
0x180003bdf  lea     eax, ds:2[rax*2]
0x180003be6  mov     [rbp+90h+var_48], eax
0x180003be9  lea     rax, aTokenimpersona; "TokenImpersonationLevel"
0x180003bf0  mov     [rbp+90h+var_38], rax
0x180003bf4  lea     rax, [rbp+90h+arg_30]
0x180003bfb  mov     [rbp+90h+var_28], rax
0x180003bff  mov     eax, [rbp+90h+arg_30]
0x180003c05  mov     [rbp+90h+var_40], r9
0x180003c09  mov     [rbp+90h+var_30], 13h
0x180003c10  mov     [rbp+90h+var_20], r10d
0x180003c14  test    eax, eax
0x180003c16  jz      short loc_180003C55
0x180003c18  sub     eax, 1
0x180003c1b  jz      short loc_180003C4C
0x180003c1d  sub     eax, 1
0x180003c20  jz      short loc_180003C43
0x180003c22  sub     eax, 1
0x180003c25  jz      short loc_180003C3A
0x180003c27  cmp     eax, 1
0x180003c2a  jz      short loc_180003C31
0x180003c2c  mov     rax, r9
0x180003c2f  jmp     short loc_180003C5C
0x180003c31  lea     rax, aImpersonationu; "ImpersonationUnknown"
0x180003c38  jmp     short loc_180003C5C
0x180003c3a  lea     rax, aImpersonationd; "ImpersonationDelegate"
0x180003c41  jmp     short loc_180003C5C
0x180003c43  lea     rax, aImpersonationi; "ImpersonationImpersonate"
0x180003c4a  jmp     short loc_180003C5C
0x180003c4c  lea     rax, aImpersonationi_0; "ImpersonationIdentify"
0x180003c53  jmp     short loc_180003C5C
0x180003c55  lea     rax, aImpersonationa; "ImpersonationAnonymous"
0x180003c5c  mov     [rbp+90h+var_18], rax
0x180003c60  lea     rdx, [rsp+190h+var_160]
0x180003c65  lea     rax, [rbp+90h+var_100]
0x180003c69  mov     rcx, r8
0x180003c6c  mov     [rbp+90h+var_114+4], rax
0x180003c70  mov     rax, [r8]
0x180003c73  mov     rax, [rax+10h]
0x180003c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c7c  xor     eax, eax
0x180003c7e  mov     rcx, [rbp+90h+var_10]
0x180003c85  xor     rcx, rsp; StackCookie
0x180003c88  call    __security_check_cookie
0x180003c8d  add     rsp, 190h
0x180003c94  pop     rbp
0x180003c95  retn
```
