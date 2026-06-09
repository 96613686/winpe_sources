# IISAuthenticationEvents::AUTH_REQUEST_AUTH_TYPE::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x1800037f0`
- end: `0x180003921`
- name: `?RaiseEvent@AUTH_REQUEST_AUTH_TYPE@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003048`

## callees

- `0x1800037f0`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall IISAuthenticationEvents::AUTH_REQUEST_AUTH_TYPE::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3)
{
  int v3; // r8d
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  const wchar_t *v8; // rax
  _QWORD v10[5]; // [rsp+20h] [rbp-59h] BYREF
  int v11; // [rsp+48h] [rbp-31h]
  int v12; // [rsp+4Ch] [rbp-2Dh]
  __int128 v13; // [rsp+50h] [rbp-29h]
  int v14; // [rsp+60h] [rbp-19h]
  int v15; // [rsp+64h] [rbp-15h]
  __int64 v16; // [rsp+68h] [rbp-11h]
  const wchar_t **v17; // [rsp+70h] [rbp-9h]
  const wchar_t *v18; // [rsp+80h] [rbp+7h] BYREF
  int v19; // [rsp+88h] [rbp+Fh]
  __int64 v20; // [rsp+90h] [rbp+17h]
  int v21; // [rsp+98h] [rbp+1Fh]
  __int64 v22; // [rsp+A0h] [rbp+27h]
  const wchar_t *v23; // [rsp+A8h] [rbp+2Fh]
  int v24; // [rsp+B0h] [rbp+37h]
  int *v25; // [rsp+B8h] [rbp+3Fh]
  int v26; // [rsp+C0h] [rbp+47h]
  const wchar_t *v27; // [rsp+C8h] [rbp+4Fh]
  int v28; // [rsp+F0h] [rbp+77h] BYREF

  v28 = a3;
  v10[1] = 2;
  v10[3] = 27;
  v10[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v10[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
  v10[4] = L"AUTH_REQUEST_AUTH_TYPE";
  v16 = 2;
  v13 = 0;
  v14 = 0;
  v19 = 72;
  v11 = 1;
  v15 = 1;
  v18 = L"ContextId";
  v23 = L"RequestAuthType";
  v25 = &v28;
  v12 = 4;
  v20 = 0;
  v21 = 16;
  v22 = 0;
  v24 = 19;
  v26 = 4;
  v3 = a3 - 1;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      v5 = v4 - 2;
      if ( v5 )
      {
        v6 = v5 - 12;
        if ( v6 )
        {
          v7 = v6 - 48;
          if ( v7 )
          {
            if ( v7 == 64 )
              v8 = L"CertMap";
            else
              v8 = 0;
          }
          else
          {
            v8 = L"Passport";
          }
        }
        else
        {
          v8 = L"Digest";
        }
      }
      else
      {
        v8 = L"NT";
      }
    }
    else
    {
      v8 = L"Basic";
    }
  }
  else
  {
    v8 = L"Anonymous";
  }
  v27 = v8;
  v17 = &v18;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v10);
  return 0;
}

```

## disassembly

```asm
0x1800037f0  mov     [rsp-8+arg_10], r8d
0x1800037f5  push    rbp
0x1800037f6  lea     rbp, [rsp-57h]
0x1800037fb  sub     rsp, 0D0h
0x180003802  xor     r9d, r9d
0x180003805  mov     [rbp+57h+var_A8], 2
0x18000380d  mov     [rbp+57h+var_98], 1Bh
0x180003815  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000381c  mov     [rbp+57h+var_B0], rax
0x180003820  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180003827  mov     [rbp+57h+var_A0], rax
0x18000382b  lea     rax, aAuthRequestAut; "AUTH_REQUEST_AUTH_TYPE"
0x180003832  mov     [rbp+57h+var_90], rax
0x180003836  mov     r10d, 2
0x18000383c  mov     [rbp+57h+var_68], 2
0x180003844  xorps   xmm0, xmm0
0x180003847  movdqa  [rbp+57h+var_80], xmm0
0x18000384c  mov     [rbp+57h+var_70], r9d
0x180003850  mov     [rbp+57h+var_48], 48h ; 'H'
0x180003857  lea     eax, [r10-1]
0x18000385b  mov     [rbp+57h+var_88], eax
0x18000385e  lea     edx, [rax+3]
0x180003861  mov     [rbp+57h+var_6C], eax
0x180003864  lea     rax, aContextid; "ContextId"
0x18000386b  mov     [rbp+57h+var_50], rax
0x18000386f  lea     rax, aRequestauthtyp; "RequestAuthType"
0x180003876  mov     [rbp+57h+var_28], rax
0x18000387a  lea     rax, [rbp+57h+arg_10]
0x18000387e  mov     [rbp+57h+var_18], rax
0x180003882  mov     [rbp+57h+var_84], edx
0x180003885  mov     [rbp+57h+var_40], r9
0x180003889  mov     [rbp+57h+var_38], 10h
0x180003890  mov     [rbp+57h+var_30], r9
0x180003894  mov     [rbp+57h+var_20], 13h
0x18000389b  mov     [rbp+57h+var_10], edx
0x18000389e  sub     r8d, 1
0x1800038a2  jz      short loc_1800038F3
0x1800038a4  sub     r8d, 1
0x1800038a8  jz      short loc_1800038EA
0x1800038aa  sub     r8d, r10d
0x1800038ad  jz      short loc_1800038E1
0x1800038af  sub     r8d, 0Ch
0x1800038b3  jz      short loc_1800038D8
0x1800038b5  sub     r8d, 30h ; '0'
0x1800038b9  jz      short loc_1800038CF
0x1800038bb  cmp     r8d, 40h ; '@'
0x1800038bf  jz      short loc_1800038C6
0x1800038c1  mov     eax, r9d
0x1800038c4  jmp     short loc_1800038FA
0x1800038c6  lea     rax, aCertmap; "CertMap"
0x1800038cd  jmp     short loc_1800038FA
0x1800038cf  lea     rax, aPassport; "Passport"
0x1800038d6  jmp     short loc_1800038FA
0x1800038d8  lea     rax, aDigest; "Digest"
0x1800038df  jmp     short loc_1800038FA
0x1800038e1  lea     rax, aNt; "NT"
0x1800038e8  jmp     short loc_1800038FA
0x1800038ea  lea     rax, aBasic; "Basic"
0x1800038f1  jmp     short loc_1800038FA
0x1800038f3  lea     rax, aAnonymous; "Anonymous"
0x1800038fa  mov     [rbp+57h+var_8], rax
0x1800038fe  lea     rdx, [rbp+57h+var_B0]
0x180003902  lea     rax, [rbp+57h+var_50]
0x180003906  mov     [rbp+57h+var_60], rax
0x18000390a  mov     rax, [rcx]
0x18000390d  mov     rax, [rax+10h]
0x180003911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003916  xor     eax, eax
0x180003918  add     rsp, 0D0h
0x18000391f  pop     rbp
0x180003920  retn
```
