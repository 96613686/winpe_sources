# IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)

- ea: `0x18000568c`
- end: `0x1800058c2`
- name: `?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z`
- size: `566`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int, int, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800058c8`

## callees

- `0x18000568c`
- `0x180005b30`
- `0x180006010`

## string_xrefs

- `0x180005881`: `ImpersonationAnonymous`
- `0x180005878`: `ImpersonationIdentify`
- `0x18000586f`: `ImpersonationImpersonate`
- `0x180005866`: `ImpersonationDelegate`
- `0x18000585d`: `ImpersonationUnknown`
- `0x180005815`: `TokenImpersonationLevel`

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
0x18000568c  push    rbp
0x18000568e  lea     rbp, [rsp-90h]
0x180005696  sub     rsp, 190h
0x18000569d  mov     rax, cs:__security_cookie
0x1800056a4  xor     rax, rsp
0x1800056a7  mov     [rbp+90h+var_10], rax
0x1800056ae  mov     rdx, [rbp+90h+arg_20]
0x1800056b5  xor     eax, eax
0x1800056b7  mov     [rsp+190h+var_114], rax
0x1800056bc  xor     r9d, r9d
0x1800056bf  mov     [rbp+90h+var_10C], eax
0x1800056c2  mov     r8, rcx
0x1800056c5  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800056cc  mov     [rsp+190h+var_168], r9d
0x1800056d1  mov     [rsp+190h+var_160], rax
0x1800056d6  xorps   xmm0, xmm0
0x1800056d9  lea     r10d, [r9+4]
0x1800056dd  mov     [rsp+190h+var_158], 2
0x1800056e6  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800056ed  mov     [rsp+190h+var_170], r10d
0x1800056f2  mov     [rsp+190h+var_150], rax
0x1800056f7  lea     ecx, [r9+0Bh]
0x1800056fb  lea     rax, aAuthSucceeded; "AUTH_SUCCEEDED"
0x180005702  mov     [rsp+190h+var_148], 0Bh
0x18000570b  mov     [rsp+190h+var_140], rax
0x180005710  lea     r11d, [r9+1Fh]
0x180005714  lea     eax, [rcx-0Ah]
0x180005717  mov     [rsp+190h+var_134], r10d
0x18000571c  mov     [rsp+190h+var_138], eax
0x180005720  mov     [rsp+190h+var_11C], eax
0x180005724  lea     rax, aContextid; "ContextId"
0x18000572b  mov     [rbp+90h+var_100], rax
0x18000572f  lea     rax, aAuthtype; "AuthType"
0x180005736  mov     [rbp+90h+var_D8], rax
0x18000573a  lea     rax, [rsp+190h+var_170]
0x18000573f  mov     [rbp+90h+var_C8], rax
0x180005743  lea     rax, aNt; "NT"
0x18000574a  mov     [rbp+90h+var_B8], rax
0x18000574e  lea     rax, aNtlmused; "NTLMUsed"
0x180005755  mov     [rbp+90h+var_B0], rax
0x180005759  lea     rax, [rsp+190h+var_168]
0x18000575e  mov     [rbp+90h+var_A0], rax
0x180005762  lea     rax, aRemoteusername; "RemoteUserName"
0x180005769  mov     [rbp+90h+var_88], rax
0x18000576d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005771  mov     [rsp+190h+var_118], 6
0x180005779  movdqa  [rsp+190h+var_130], xmm0
0x18000577f  mov     [rsp+190h+var_120], r9d
0x180005784  mov     [rbp+90h+var_F8], 48h ; 'H'
0x18000578b  mov     [rbp+90h+var_F0], r9
0x18000578f  mov     [rbp+90h+var_E8], 10h
0x180005796  mov     [rbp+90h+var_E0], r9
0x18000579a  mov     [rbp+90h+var_D0], 13h
0x1800057a1  mov     [rbp+90h+var_C0], r10d
0x1800057a5  mov     [rbp+90h+var_A8], ecx
0x1800057a8  mov     [rbp+90h+var_98], r10d
0x1800057ac  mov     [rbp+90h+var_90], r9
0x1800057b0  mov     [rbp+90h+var_80], r11d
0x1800057b4  mov     [rbp+90h+var_78], rdx
0x1800057b8  test    rdx, rdx
0x1800057bb  jnz     short loc_1800057C2
0x1800057bd  mov     ecx, r9d
0x1800057c0  jmp     short loc_1800057D6
0x1800057c2  mov     rcx, rax
0x1800057c5  inc     rcx
0x1800057c8  cmp     [rdx+rcx*2], r9w
0x1800057cd  jnz     short loc_1800057C5
0x1800057cf  lea     ecx, ds:2[rcx*2]
0x1800057d6  mov     [rbp+90h+var_70], ecx
0x1800057d9  lea     rcx, aAuthusername; "AuthUserName"
0x1800057e0  mov     [rbp+90h+var_60], rcx
0x1800057e4  mov     rcx, [rbp+90h+arg_28]
0x1800057eb  mov     [rbp+90h+var_68], r9
0x1800057ef  mov     [rbp+90h+var_58], r11d
0x1800057f3  mov     [rbp+90h+var_50], rcx
0x1800057f7  test    rcx, rcx
0x1800057fa  jnz     short loc_180005801
0x1800057fc  mov     eax, r9d
0x1800057ff  jmp     short loc_180005812
0x180005801  inc     rax
0x180005804  cmp     [rcx+rax*2], r9w
0x180005809  jnz     short loc_180005801
0x18000580b  lea     eax, ds:2[rax*2]
0x180005812  mov     [rbp+90h+var_48], eax
0x180005815  lea     rax, aTokenimpersona; "TokenImpersonationLevel"
0x18000581c  mov     [rbp+90h+var_38], rax
0x180005820  lea     rax, [rbp+90h+arg_30]
0x180005827  mov     [rbp+90h+var_28], rax
0x18000582b  mov     eax, [rbp+90h+arg_30]
0x180005831  mov     [rbp+90h+var_40], r9
0x180005835  mov     [rbp+90h+var_30], 13h
0x18000583c  mov     [rbp+90h+var_20], r10d
0x180005840  test    eax, eax
0x180005842  jz      short loc_180005881
0x180005844  sub     eax, 1
0x180005847  jz      short loc_180005878
0x180005849  sub     eax, 1
0x18000584c  jz      short loc_18000586F
0x18000584e  sub     eax, 1
0x180005851  jz      short loc_180005866
0x180005853  cmp     eax, 1
0x180005856  jz      short loc_18000585D
0x180005858  mov     rax, r9
0x18000585b  jmp     short loc_180005888
0x18000585d  lea     rax, aImpersonationu; "ImpersonationUnknown"
0x180005864  jmp     short loc_180005888
0x180005866  lea     rax, aImpersonationd; "ImpersonationDelegate"
0x18000586d  jmp     short loc_180005888
0x18000586f  lea     rax, aImpersonationi; "ImpersonationImpersonate"
0x180005876  jmp     short loc_180005888
0x180005878  lea     rax, aImpersonationi_0; "ImpersonationIdentify"
0x18000587f  jmp     short loc_180005888
0x180005881  lea     rax, aImpersonationa; "ImpersonationAnonymous"
0x180005888  mov     [rbp+90h+var_18], rax
0x18000588c  lea     rdx, [rsp+190h+var_160]
0x180005891  lea     rax, [rbp+90h+var_100]
0x180005895  mov     rcx, r8
0x180005898  mov     [rbp+90h+var_114+4], rax
0x18000589c  mov     rax, [r8]
0x18000589f  mov     rax, [rax+10h]
0x1800058a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a8  xor     eax, eax
0x1800058aa  mov     rcx, [rbp+90h+var_10]
0x1800058b1  xor     rcx, rsp; StackCookie
0x1800058b4  call    __security_check_cookie
0x1800058b9  add     rsp, 190h
0x1800058c0  pop     rbp
0x1800058c1  retn
```
