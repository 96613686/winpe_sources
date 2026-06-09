# IISAuthenticationEvents::AUTH_REQUEST_AUTH_TYPE::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x180002840`
- end: `0x180002971`
- name: `?RaiseEvent@AUTH_REQUEST_AUTH_TYPE@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001030`

## callees

- `0x180002840`
- `0x180006010`

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
0x180002840  mov     [rsp-8+arg_10], r8d
0x180002845  push    rbp
0x180002846  lea     rbp, [rsp-57h]
0x18000284b  sub     rsp, 0D0h
0x180002852  xor     r9d, r9d
0x180002855  mov     [rbp+57h+var_A8], 2
0x18000285d  mov     [rbp+57h+var_98], 1Bh
0x180002865  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000286c  mov     [rbp+57h+var_B0], rax
0x180002870  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180002877  mov     [rbp+57h+var_A0], rax
0x18000287b  lea     rax, aAuthRequestAut; "AUTH_REQUEST_AUTH_TYPE"
0x180002882  mov     [rbp+57h+var_90], rax
0x180002886  mov     r10d, 2
0x18000288c  mov     [rbp+57h+var_68], 2
0x180002894  xorps   xmm0, xmm0
0x180002897  movdqa  [rbp+57h+var_80], xmm0
0x18000289c  mov     [rbp+57h+var_70], r9d
0x1800028a0  mov     [rbp+57h+var_48], 48h ; 'H'
0x1800028a7  lea     eax, [r10-1]
0x1800028ab  mov     [rbp+57h+var_88], eax
0x1800028ae  lea     edx, [rax+3]
0x1800028b1  mov     [rbp+57h+var_6C], eax
0x1800028b4  lea     rax, aContextid; "ContextId"
0x1800028bb  mov     [rbp+57h+var_50], rax
0x1800028bf  lea     rax, aRequestauthtyp; "RequestAuthType"
0x1800028c6  mov     [rbp+57h+var_28], rax
0x1800028ca  lea     rax, [rbp+57h+arg_10]
0x1800028ce  mov     [rbp+57h+var_18], rax
0x1800028d2  mov     [rbp+57h+var_84], edx
0x1800028d5  mov     [rbp+57h+var_40], r9
0x1800028d9  mov     [rbp+57h+var_38], 10h
0x1800028e0  mov     [rbp+57h+var_30], r9
0x1800028e4  mov     [rbp+57h+var_20], 13h
0x1800028eb  mov     [rbp+57h+var_10], edx
0x1800028ee  sub     r8d, 1
0x1800028f2  jz      short loc_180002943
0x1800028f4  sub     r8d, 1
0x1800028f8  jz      short loc_18000293A
0x1800028fa  sub     r8d, r10d
0x1800028fd  jz      short loc_180002931
0x1800028ff  sub     r8d, 0Ch
0x180002903  jz      short loc_180002928
0x180002905  sub     r8d, 30h ; '0'
0x180002909  jz      short loc_18000291F
0x18000290b  cmp     r8d, 40h ; '@'
0x18000290f  jz      short loc_180002916
0x180002911  mov     eax, r9d
0x180002914  jmp     short loc_18000294A
0x180002916  lea     rax, aCertmap; "CertMap"
0x18000291d  jmp     short loc_18000294A
0x18000291f  lea     rax, aPassport; "Passport"
0x180002926  jmp     short loc_18000294A
0x180002928  lea     rax, aDigest; "Digest"
0x18000292f  jmp     short loc_18000294A
0x180002931  lea     rax, aNt; "NT"
0x180002938  jmp     short loc_18000294A
0x18000293a  lea     rax, aBasic; "Basic"
0x180002941  jmp     short loc_18000294A
0x180002943  lea     rax, aAnonymous; "Anonymous"
0x18000294a  mov     [rbp+57h+var_8], rax
0x18000294e  lea     rdx, [rbp+57h+var_B0]
0x180002952  lea     rax, [rbp+57h+var_50]
0x180002956  mov     [rbp+57h+var_60], rax
0x18000295a  mov     rax, [rcx]
0x18000295d  mov     rax, [rax+10h]
0x180002961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002966  xor     eax, eax
0x180002968  add     rsp, 0D0h
0x18000296f  pop     rbp
0x180002970  retn
```
