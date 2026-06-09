# IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)

- ea: `0x18000619c`
- end: `0x1800063d2`
- name: `?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z`
- size: `566`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int, int, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800063d8`

## callees

- `0x18000619c`
- `0x180006600`
- `0x180007010`

## string_xrefs

- `0x180006391`: `ImpersonationAnonymous`
- `0x180006388`: `ImpersonationIdentify`
- `0x18000637f`: `ImpersonationImpersonate`
- `0x180006376`: `ImpersonationDelegate`
- `0x18000636d`: `ImpersonationUnknown`
- `0x180006325`: `TokenImpersonationLevel`

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
0x18000619c  push    rbp
0x18000619e  lea     rbp, [rsp-90h]
0x1800061a6  sub     rsp, 190h
0x1800061ad  mov     rax, cs:__security_cookie
0x1800061b4  xor     rax, rsp
0x1800061b7  mov     [rbp+90h+var_10], rax
0x1800061be  mov     rdx, [rbp+90h+arg_20]
0x1800061c5  xor     eax, eax
0x1800061c7  mov     [rsp+190h+var_114], rax
0x1800061cc  xor     r9d, r9d
0x1800061cf  mov     [rbp+90h+var_10C], eax
0x1800061d2  mov     r8, rcx
0x1800061d5  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800061dc  mov     [rsp+190h+var_168], r9d
0x1800061e1  mov     [rsp+190h+var_160], rax
0x1800061e6  xorps   xmm0, xmm0
0x1800061e9  lea     r10d, [r9+4]
0x1800061ed  mov     [rsp+190h+var_158], 2
0x1800061f6  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800061fd  mov     [rsp+190h+var_170], r10d
0x180006202  mov     [rsp+190h+var_150], rax
0x180006207  lea     ecx, [r9+0Bh]
0x18000620b  lea     rax, aAuthSucceeded; "AUTH_SUCCEEDED"
0x180006212  mov     [rsp+190h+var_148], 0Bh
0x18000621b  mov     [rsp+190h+var_140], rax
0x180006220  lea     r11d, [r9+1Fh]
0x180006224  lea     eax, [rcx-0Ah]
0x180006227  mov     [rsp+190h+var_134], r10d
0x18000622c  mov     [rsp+190h+var_138], eax
0x180006230  mov     [rsp+190h+var_11C], eax
0x180006234  lea     rax, aContextid; "ContextId"
0x18000623b  mov     [rbp+90h+var_100], rax
0x18000623f  lea     rax, aAuthtype; "AuthType"
0x180006246  mov     [rbp+90h+var_D8], rax
0x18000624a  lea     rax, [rsp+190h+var_170]
0x18000624f  mov     [rbp+90h+var_C8], rax
0x180006253  lea     rax, aNt; "NT"
0x18000625a  mov     [rbp+90h+var_B8], rax
0x18000625e  lea     rax, aNtlmused; "NTLMUsed"
0x180006265  mov     [rbp+90h+var_B0], rax
0x180006269  lea     rax, [rsp+190h+var_168]
0x18000626e  mov     [rbp+90h+var_A0], rax
0x180006272  lea     rax, aRemoteusername; "RemoteUserName"
0x180006279  mov     [rbp+90h+var_88], rax
0x18000627d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006281  mov     [rsp+190h+var_118], 6
0x180006289  movdqa  [rsp+190h+var_130], xmm0
0x18000628f  mov     [rsp+190h+var_120], r9d
0x180006294  mov     [rbp+90h+var_F8], 48h ; 'H'
0x18000629b  mov     [rbp+90h+var_F0], r9
0x18000629f  mov     [rbp+90h+var_E8], 10h
0x1800062a6  mov     [rbp+90h+var_E0], r9
0x1800062aa  mov     [rbp+90h+var_D0], 13h
0x1800062b1  mov     [rbp+90h+var_C0], r10d
0x1800062b5  mov     [rbp+90h+var_A8], ecx
0x1800062b8  mov     [rbp+90h+var_98], r10d
0x1800062bc  mov     [rbp+90h+var_90], r9
0x1800062c0  mov     [rbp+90h+var_80], r11d
0x1800062c4  mov     [rbp+90h+var_78], rdx
0x1800062c8  test    rdx, rdx
0x1800062cb  jnz     short loc_1800062D2
0x1800062cd  mov     ecx, r9d
0x1800062d0  jmp     short loc_1800062E6
0x1800062d2  mov     rcx, rax
0x1800062d5  inc     rcx
0x1800062d8  cmp     [rdx+rcx*2], r9w
0x1800062dd  jnz     short loc_1800062D5
0x1800062df  lea     ecx, ds:2[rcx*2]
0x1800062e6  mov     [rbp+90h+var_70], ecx
0x1800062e9  lea     rcx, aAuthusername; "AuthUserName"
0x1800062f0  mov     [rbp+90h+var_60], rcx
0x1800062f4  mov     rcx, [rbp+90h+arg_28]
0x1800062fb  mov     [rbp+90h+var_68], r9
0x1800062ff  mov     [rbp+90h+var_58], r11d
0x180006303  mov     [rbp+90h+var_50], rcx
0x180006307  test    rcx, rcx
0x18000630a  jnz     short loc_180006311
0x18000630c  mov     eax, r9d
0x18000630f  jmp     short loc_180006322
0x180006311  inc     rax
0x180006314  cmp     [rcx+rax*2], r9w
0x180006319  jnz     short loc_180006311
0x18000631b  lea     eax, ds:2[rax*2]
0x180006322  mov     [rbp+90h+var_48], eax
0x180006325  lea     rax, aTokenimpersona; "TokenImpersonationLevel"
0x18000632c  mov     [rbp+90h+var_38], rax
0x180006330  lea     rax, [rbp+90h+arg_30]
0x180006337  mov     [rbp+90h+var_28], rax
0x18000633b  mov     eax, [rbp+90h+arg_30]
0x180006341  mov     [rbp+90h+var_40], r9
0x180006345  mov     [rbp+90h+var_30], 13h
0x18000634c  mov     [rbp+90h+var_20], r10d
0x180006350  test    eax, eax
0x180006352  jz      short loc_180006391
0x180006354  sub     eax, 1
0x180006357  jz      short loc_180006388
0x180006359  sub     eax, 1
0x18000635c  jz      short loc_18000637F
0x18000635e  sub     eax, 1
0x180006361  jz      short loc_180006376
0x180006363  cmp     eax, 1
0x180006366  jz      short loc_18000636D
0x180006368  mov     rax, r9
0x18000636b  jmp     short loc_180006398
0x18000636d  lea     rax, aImpersonationu; "ImpersonationUnknown"
0x180006374  jmp     short loc_180006398
0x180006376  lea     rax, aImpersonationd; "ImpersonationDelegate"
0x18000637d  jmp     short loc_180006398
0x18000637f  lea     rax, aImpersonationi; "ImpersonationImpersonate"
0x180006386  jmp     short loc_180006398
0x180006388  lea     rax, aImpersonationi_0; "ImpersonationIdentify"
0x18000638f  jmp     short loc_180006398
0x180006391  lea     rax, aImpersonationa; "ImpersonationAnonymous"
0x180006398  mov     [rbp+90h+var_18], rax
0x18000639c  lea     rdx, [rsp+190h+var_160]
0x1800063a1  lea     rax, [rbp+90h+var_100]
0x1800063a5  mov     rcx, r8
0x1800063a8  mov     [rbp+90h+var_114+4], rax
0x1800063ac  mov     rax, [r8]
0x1800063af  mov     rax, [rax+10h]
0x1800063b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063b8  xor     eax, eax
0x1800063ba  mov     rcx, [rbp+90h+var_10]
0x1800063c1  xor     rcx, rsp; StackCookie
0x1800063c4  call    __security_check_cookie
0x1800063c9  add     rsp, 190h
0x1800063d0  pop     rbp
0x1800063d1  retn
```
