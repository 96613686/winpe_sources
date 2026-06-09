# IISAuthenticationEvents::AUTH_KERBEROS_FAILED::RaiseEvent(IHttpTraceContext *,_GUID const *,int,ushort const *,ushort const *,int,ushort const *)

- ea: `0x1800058fc`
- end: `0x180005ad3`
- name: `?RaiseEvent@AUTH_KERBEROS_FAILED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@HPEBG2H2@Z`
- size: `471`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, int, const unsigned __int16 *, const unsigned __int16 *, char, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003654`

## callees

- `0x1800058fc`
- `0x180008ba0`
- `0x180009010`

## string_xrefs

- `0x180005a4c`: `ADConfigIsOK`

## pseudocode

```c
__int64 __fastcall IISAuthenticationEvents::AUTH_KERBEROS_FAILED::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        char a6)
{
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rax
  void (__fastcall *v12)(struct IHttpTraceContext *, _QWORD *); // rax
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
  __int64 v32; // [rsp+D8h] [rbp-28h]
  const wchar_t *v33; // [rsp+E0h] [rbp-20h]
  int v34; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v35; // [rsp+F0h] [rbp-10h]
  int v36; // [rsp+F8h] [rbp-8h]
  __int64 v37; // [rsp+100h] [rbp+0h]
  const wchar_t *v38; // [rsp+108h] [rbp+8h]
  int v39; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v40; // [rsp+118h] [rbp+18h]
  int v41; // [rsp+120h] [rbp+20h]
  __int64 v42; // [rsp+128h] [rbp+28h]
  const wchar_t *v43; // [rsp+130h] [rbp+30h]
  int v44; // [rsp+138h] [rbp+38h]
  char *v45; // [rsp+140h] [rbp+40h]
  int v46; // [rsp+148h] [rbp+48h]
  __int64 v47; // [rsp+150h] [rbp+50h]
  const wchar_t *v48; // [rsp+158h] [rbp+58h]
  int v49; // [rsp+160h] [rbp+60h]
  int *v50; // [rsp+168h] [rbp+68h]
  int v51; // [rsp+170h] [rbp+70h]
  __int64 v52; // [rsp+178h] [rbp+78h]

  v15[1] = 2;
  memset(v22, 0, 12);
  v14 = 0;
  v15[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v7 = -1;
  v15[3] = 55;
  v15[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
  v15[4] = L"AUTH_KERBEROS_FAILED";
  v16 = 1;
  v20 = 1;
  v23 = L"ContextId";
  v28 = L"KMUsed";
  v30 = &v14;
  v33 = L"APUserName";
  v17 = 3;
  v21 = 6;
  v18 = 0;
  v19 = 0;
  v24 = 72;
  v25 = 0;
  v26 = 16;
  v27 = 0;
  v29 = 11;
  v31 = 4;
  v32 = 0;
  v34 = 31;
  v35 = a4;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v8 = 2 * v9 + 2;
  }
  else
  {
    v8 = 0;
  }
  v36 = v8;
  v38 = L"SPNName";
  v37 = 0;
  v39 = 31;
  v40 = a5;
  if ( a5 )
  {
    do
      ++v7;
    while ( a5[v7] );
    v10 = 2 * v7 + 2;
  }
  else
  {
    v10 = 0;
  }
  v41 = v10;
  v43 = L"ADConfigIsOK";
  v42 = 0;
  v45 = &a6;
  v48 = L"KerberosInfo";
  v50 = &dword_18000B0EC;
  *(_QWORD *)((char *)v22 + 4) = &v23;
  v11 = *(_QWORD *)a1;
  v47 = 0;
  v52 = 0;
  v44 = 11;
  v12 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v11 + 16);
  v46 = 4;
  v49 = 31;
  v51 = 2;
  v12(a1, v15);
  return 0;
}

```

## disassembly

```asm
0x1800058fc  push    rbp
0x1800058fe  lea     rbp, [rsp-90h]
0x180005906  sub     rsp, 190h
0x18000590d  mov     rax, cs:__security_cookie
0x180005914  xor     rax, rsp
0x180005917  mov     [rbp+90h+var_10], rax
0x18000591e  xor     eax, eax
0x180005920  mov     [rsp+190h+var_158], 2
0x180005929  xor     edx, edx
0x18000592b  mov     [rsp+190h+var_114], rax
0x180005930  mov     [rbp+90h+var_10C], eax
0x180005933  mov     r8, rcx
0x180005936  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000593d  mov     [rsp+190h+var_170], edx
0x180005941  mov     [rsp+190h+var_160], rax
0x180005946  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000594a  mov     [rsp+190h+var_148], 37h ; '7'
0x180005953  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000595a  mov     [rsp+190h+var_150], rax
0x18000595f  lea     rax, aAuthKerberosFa; "AUTH_KERBEROS_FAILED"
0x180005966  mov     [rsp+190h+var_140], rax
0x18000596b  lea     eax, [rdx+1]
0x18000596e  mov     [rsp+190h+var_138], eax
0x180005972  xorps   xmm0, xmm0
0x180005975  mov     [rsp+190h+var_11C], eax
0x180005979  lea     rax, aContextid; "ContextId"
0x180005980  mov     [rbp+90h+var_100], rax
0x180005984  lea     rax, aKmused; "KMUsed"
0x18000598b  mov     [rbp+90h+var_D8], rax
0x18000598f  lea     rax, [rsp+190h+var_170]
0x180005994  mov     [rbp+90h+var_C8], rax
0x180005998  lea     rax, aApusername; "APUserName"
0x18000599f  mov     [rbp+90h+var_B0], rax
0x1800059a3  lea     r10d, [rdx+1Fh]
0x1800059a7  mov     [rsp+190h+var_134], 3
0x1800059af  lea     r11d, [rdx+2]
0x1800059b3  mov     [rsp+190h+var_118], 6
0x1800059bb  movdqa  [rsp+190h+var_130], xmm0
0x1800059c1  mov     [rsp+190h+var_120], edx
0x1800059c5  mov     [rbp+90h+var_F8], 48h ; 'H'
0x1800059cc  mov     [rbp+90h+var_F0], rdx
0x1800059d0  mov     [rbp+90h+var_E8], 10h
0x1800059d7  mov     [rbp+90h+var_E0], rdx
0x1800059db  mov     [rbp+90h+var_D0], 0Bh
0x1800059e2  mov     [rbp+90h+var_C0], 4
0x1800059e9  mov     [rbp+90h+var_B8], rdx
0x1800059ed  mov     [rbp+90h+var_A8], r10d
0x1800059f1  mov     [rbp+90h+var_A0], r9
0x1800059f5  test    r9, r9
0x1800059f8  jnz     short loc_1800059FE
0x1800059fa  mov     eax, edx
0x1800059fc  jmp     short loc_180005A12
0x1800059fe  mov     rax, rcx
0x180005a01  inc     rax
0x180005a04  cmp     [r9+rax*2], dx
0x180005a09  jnz     short loc_180005A01
0x180005a0b  lea     eax, ds:2[rax*2]
0x180005a12  mov     [rbp+90h+var_98], eax
0x180005a15  lea     rax, aSpnname; "SPNName"
0x180005a1c  mov     [rbp+90h+var_88], rax
0x180005a20  mov     rax, [rbp+90h+arg_20]
0x180005a27  mov     [rbp+90h+var_90], rdx
0x180005a2b  mov     [rbp+90h+var_80], r10d
0x180005a2f  mov     [rbp+90h+var_78], rax
0x180005a33  test    rax, rax
0x180005a36  jnz     short loc_180005A3C
0x180005a38  mov     ecx, edx
0x180005a3a  jmp     short loc_180005A4C
0x180005a3c  inc     rcx
0x180005a3f  cmp     [rax+rcx*2], dx
0x180005a43  jnz     short loc_180005A3C
0x180005a45  lea     ecx, ds:2[rcx*2]
0x180005a4c  lea     rax, aAdconfigisok; "ADConfigIsOK"
0x180005a53  mov     [rbp+90h+var_70], ecx
0x180005a56  mov     [rbp+90h+var_60], rax
0x180005a5a  mov     rcx, r8
0x180005a5d  lea     rax, [rbp+90h+arg_28]
0x180005a64  mov     [rbp+90h+var_68], rdx
0x180005a68  mov     [rbp+90h+var_50], rax
0x180005a6c  lea     rax, aKerberosinfo; "KerberosInfo"
0x180005a73  mov     [rbp+90h+var_38], rax
0x180005a77  lea     rax, dword_18000B0EC
0x180005a7e  mov     [rbp+90h+var_28], rax
0x180005a82  lea     rax, [rbp+90h+var_100]
0x180005a86  mov     [rbp+90h+var_114+4], rax
0x180005a8a  mov     rax, [r8]
0x180005a8d  mov     [rbp+90h+var_40], rdx
0x180005a91  mov     [rbp+90h+var_18], rdx
0x180005a95  lea     rdx, [rsp+190h+var_160]
0x180005a9a  mov     [rbp+90h+var_58], 0Bh
0x180005aa1  mov     rax, [rax+10h]
0x180005aa5  mov     [rbp+90h+var_48], 4
0x180005aac  mov     [rbp+90h+var_30], r10d
0x180005ab0  mov     [rbp+90h+var_20], r11d
0x180005ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ab9  xor     eax, eax
0x180005abb  mov     rcx, [rbp+90h+var_10]
0x180005ac2  xor     rcx, rsp; StackCookie
0x180005ac5  call    __security_check_cookie
0x180005aca  add     rsp, 190h
0x180005ad1  pop     rbp
0x180005ad2  retn
```
