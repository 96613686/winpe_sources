# IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)

- ea: `0x1800086d0`
- end: `0x180008909`
- name: `?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z`
- size: `569`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int, int, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008910`

## callees

- `0x1800086d0`
- `0x180008ba0`
- `0x180009010`

## string_xrefs

- `0x1800088c8`: `ImpersonationAnonymous`
- `0x1800088bf`: `ImpersonationIdentify`
- `0x1800088b6`: `ImpersonationImpersonate`
- `0x1800088ad`: `ImpersonationDelegate`
- `0x1800088a4`: `ImpersonationUnknown`
- `0x18000885c`: `TokenImpersonationLevel`

## pseudocode

```c
__int64 __fastcall IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        __int64 a3,
        int a4,
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
  _QWORD v15[5]; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+5Ch] [rbp-A4h]
  __int128 v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+70h] [rbp-90h]
  int v20; // [rsp+74h] [rbp-8Ch]
  int v21; // [rsp+78h] [rbp-88h]
  _QWORD v22[2]; // [rsp+7Ch] [rbp-84h] BYREF
  const wchar_t *v23; // [rsp+90h] [rbp-70h] BYREF
  int v24; // [rsp+98h] [rbp-68h]
  __int64 v25; // [rsp+A0h] [rbp-60h]
  int v26; // [rsp+A8h] [rbp-58h]
  __int64 v27; // [rsp+B0h] [rbp-50h]
  const wchar_t *v28; // [rsp+B8h] [rbp-48h]
  int v29; // [rsp+C0h] [rbp-40h]
  int *v30; // [rsp+C8h] [rbp-38h]
  int v31; // [rsp+D0h] [rbp-30h]
  const wchar_t *v32; // [rsp+D8h] [rbp-28h]
  const wchar_t *v33; // [rsp+E0h] [rbp-20h]
  int v34; // [rsp+E8h] [rbp-18h]
  int *v35; // [rsp+F0h] [rbp-10h]
  int v36; // [rsp+F8h] [rbp-8h]
  __int64 v37; // [rsp+100h] [rbp+0h]
  const wchar_t *v38; // [rsp+108h] [rbp+8h]
  int v39; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v40; // [rsp+118h] [rbp+18h]
  int v41; // [rsp+120h] [rbp+20h]
  __int64 v42; // [rsp+128h] [rbp+28h]
  const wchar_t *v43; // [rsp+130h] [rbp+30h]
  int v44; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v45; // [rsp+140h] [rbp+40h]
  int v46; // [rsp+148h] [rbp+48h]
  __int64 v47; // [rsp+150h] [rbp+50h]
  const wchar_t *v48; // [rsp+158h] [rbp+58h]
  int v49; // [rsp+160h] [rbp+60h]
  unsigned int *v50; // [rsp+168h] [rbp+68h]
  int v51; // [rsp+170h] [rbp+70h]
  const wchar_t *v52; // [rsp+178h] [rbp+78h]
  int v53; // [rsp+1B8h] [rbp+B8h] BYREF

  v53 = a4;
  memset(v22, 0, 12);
  v14 = 4;
  v15[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v15[1] = 2;
  v15[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
  v15[3] = 11;
  v15[4] = L"AUTH_SUCCEEDED";
  v17 = 4;
  v16 = 1;
  v20 = 1;
  v23 = L"ContextId";
  v28 = L"AuthType";
  v30 = &v14;
  v32 = L"NT";
  v33 = L"NTLMUsed";
  v35 = &v53;
  v38 = L"RemoteUserName";
  v8 = -1;
  v21 = 6;
  v18 = 0;
  v19 = 0;
  v24 = 72;
  v25 = 0;
  v26 = 16;
  v27 = 0;
  v29 = 19;
  v31 = 4;
  v34 = 11;
  v36 = 4;
  v37 = 0;
  v39 = 31;
  v40 = a5;
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
  v41 = v9;
  v43 = L"AuthUserName";
  v42 = 0;
  v44 = 31;
  v45 = a6;
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
  v46 = v11;
  v48 = L"TokenImpersonationLevel";
  v50 = &a7;
  v47 = 0;
  v49 = 19;
  v51 = 4;
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
  v52 = v12;
  *(_QWORD *)((char *)v22 + 4) = &v23;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v15);
  return 0;
}

```

## disassembly

```asm
0x1800086d0  mov     [rsp-8+arg_18], r9d
0x1800086d5  push    rbp
0x1800086d6  lea     rbp, [rsp-90h]
0x1800086de  sub     rsp, 190h
0x1800086e5  mov     rax, cs:__security_cookie
0x1800086ec  xor     rax, rsp
0x1800086ef  mov     [rbp+90h+var_10], rax
0x1800086f6  mov     rdx, [rbp+90h+arg_20]
0x1800086fd  xor     eax, eax
0x1800086ff  mov     [rsp+190h+var_114], rax
0x180008704  mov     r10d, 4
0x18000870a  mov     [rbp+90h+var_10C], eax
0x18000870d  xor     r9d, r9d
0x180008710  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180008717  mov     [rsp+190h+var_170], r10d
0x18000871c  mov     [rsp+190h+var_160], rax
0x180008721  mov     r8, rcx
0x180008724  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000872b  mov     [rsp+190h+var_158], 2
0x180008734  mov     [rsp+190h+var_150], rax
0x180008739  lea     ecx, [r10+7]
0x18000873d  lea     rax, aAuthSucceeded; "AUTH_SUCCEEDED"
0x180008744  mov     [rsp+190h+var_148], 0Bh
0x18000874d  mov     [rsp+190h+var_140], rax
0x180008752  lea     r11d, [r10+1Bh]
0x180008756  lea     eax, [rcx-0Ah]
0x180008759  mov     [rsp+190h+var_134], r10d
0x18000875e  mov     [rsp+190h+var_138], eax
0x180008762  xorps   xmm0, xmm0
0x180008765  mov     [rsp+190h+var_11C], eax
0x180008769  lea     rax, aContextid; "ContextId"
0x180008770  mov     [rbp+90h+var_100], rax
0x180008774  lea     rax, aAuthtype; "AuthType"
0x18000877b  mov     [rbp+90h+var_D8], rax
0x18000877f  lea     rax, [rsp+190h+var_170]
0x180008784  mov     [rbp+90h+var_C8], rax
0x180008788  lea     rax, aNt; "NT"
0x18000878f  mov     [rbp+90h+var_B8], rax
0x180008793  lea     rax, aNtlmused; "NTLMUsed"
0x18000879a  mov     [rbp+90h+var_B0], rax
0x18000879e  lea     rax, [rbp+90h+arg_18]
0x1800087a5  mov     [rbp+90h+var_A0], rax
0x1800087a9  lea     rax, aRemoteusername; "RemoteUserName"
0x1800087b0  mov     [rbp+90h+var_88], rax
0x1800087b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800087b8  mov     [rsp+190h+var_118], 6
0x1800087c0  movdqa  [rsp+190h+var_130], xmm0
0x1800087c6  mov     [rsp+190h+var_120], r9d
0x1800087cb  mov     [rbp+90h+var_F8], 48h ; 'H'
0x1800087d2  mov     [rbp+90h+var_F0], r9
0x1800087d6  mov     [rbp+90h+var_E8], 10h
0x1800087dd  mov     [rbp+90h+var_E0], r9
0x1800087e1  mov     [rbp+90h+var_D0], 13h
0x1800087e8  mov     [rbp+90h+var_C0], r10d
0x1800087ec  mov     [rbp+90h+var_A8], ecx
0x1800087ef  mov     [rbp+90h+var_98], r10d
0x1800087f3  mov     [rbp+90h+var_90], r9
0x1800087f7  mov     [rbp+90h+var_80], r11d
0x1800087fb  mov     [rbp+90h+var_78], rdx
0x1800087ff  test    rdx, rdx
0x180008802  jnz     short loc_180008809
0x180008804  mov     ecx, r9d
0x180008807  jmp     short loc_18000881D
0x180008809  mov     rcx, rax
0x18000880c  inc     rcx
0x18000880f  cmp     [rdx+rcx*2], r9w
0x180008814  jnz     short loc_18000880C
0x180008816  lea     ecx, ds:2[rcx*2]
0x18000881d  mov     [rbp+90h+var_70], ecx
0x180008820  lea     rcx, aAuthusername; "AuthUserName"
0x180008827  mov     [rbp+90h+var_60], rcx
0x18000882b  mov     rcx, [rbp+90h+arg_28]
0x180008832  mov     [rbp+90h+var_68], r9
0x180008836  mov     [rbp+90h+var_58], r11d
0x18000883a  mov     [rbp+90h+var_50], rcx
0x18000883e  test    rcx, rcx
0x180008841  jnz     short loc_180008848
0x180008843  mov     eax, r9d
0x180008846  jmp     short loc_180008859
0x180008848  inc     rax
0x18000884b  cmp     [rcx+rax*2], r9w
0x180008850  jnz     short loc_180008848
0x180008852  lea     eax, ds:2[rax*2]
0x180008859  mov     [rbp+90h+var_48], eax
0x18000885c  lea     rax, aTokenimpersona; "TokenImpersonationLevel"
0x180008863  mov     [rbp+90h+var_38], rax
0x180008867  lea     rax, [rbp+90h+arg_30]
0x18000886e  mov     [rbp+90h+var_28], rax
0x180008872  mov     eax, [rbp+90h+arg_30]
0x180008878  mov     [rbp+90h+var_40], r9
0x18000887c  mov     [rbp+90h+var_30], 13h
0x180008883  mov     [rbp+90h+var_20], r10d
0x180008887  test    eax, eax
0x180008889  jz      short loc_1800088C8
0x18000888b  sub     eax, 1
0x18000888e  jz      short loc_1800088BF
0x180008890  sub     eax, 1
0x180008893  jz      short loc_1800088B6
0x180008895  sub     eax, 1
0x180008898  jz      short loc_1800088AD
0x18000889a  cmp     eax, 1
0x18000889d  jz      short loc_1800088A4
0x18000889f  mov     rax, r9
0x1800088a2  jmp     short loc_1800088CF
0x1800088a4  lea     rax, aImpersonationu; "ImpersonationUnknown"
0x1800088ab  jmp     short loc_1800088CF
0x1800088ad  lea     rax, aImpersonationd; "ImpersonationDelegate"
0x1800088b4  jmp     short loc_1800088CF
0x1800088b6  lea     rax, aImpersonationi; "ImpersonationImpersonate"
0x1800088bd  jmp     short loc_1800088CF
0x1800088bf  lea     rax, aImpersonationi_0; "ImpersonationIdentify"
0x1800088c6  jmp     short loc_1800088CF
0x1800088c8  lea     rax, aImpersonationa; "ImpersonationAnonymous"
0x1800088cf  mov     [rbp+90h+var_18], rax
0x1800088d3  lea     rdx, [rsp+190h+var_160]
0x1800088d8  lea     rax, [rbp+90h+var_100]
0x1800088dc  mov     rcx, r8
0x1800088df  mov     [rbp+90h+var_114+4], rax
0x1800088e3  mov     rax, [r8]
0x1800088e6  mov     rax, [rax+10h]
0x1800088ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ef  xor     eax, eax
0x1800088f1  mov     rcx, [rbp+90h+var_10]
0x1800088f8  xor     rcx, rsp; StackCookie
0x1800088fb  call    __security_check_cookie
0x180008900  add     rsp, 190h
0x180008907  pop     rbp
0x180008908  retn
```
