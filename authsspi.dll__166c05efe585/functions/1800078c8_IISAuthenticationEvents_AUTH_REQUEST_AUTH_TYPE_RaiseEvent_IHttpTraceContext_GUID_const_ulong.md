# IISAuthenticationEvents::AUTH_REQUEST_AUTH_TYPE::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x1800078c8`
- end: `0x1800079f9`
- name: `?RaiseEvent@AUTH_REQUEST_AUTH_TYPE@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007120`

## callees

- `0x1800078c8`
- `0x180009010`

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
0x1800078c8  mov     [rsp-8+arg_10], r8d
0x1800078cd  push    rbp
0x1800078ce  lea     rbp, [rsp-57h]
0x1800078d3  sub     rsp, 0D0h
0x1800078da  xor     r9d, r9d
0x1800078dd  mov     [rbp+57h+var_A8], 2
0x1800078e5  mov     [rbp+57h+var_98], 1Bh
0x1800078ed  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800078f4  mov     [rbp+57h+var_B0], rax
0x1800078f8  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800078ff  mov     [rbp+57h+var_A0], rax
0x180007903  lea     rax, aAuthRequestAut; "AUTH_REQUEST_AUTH_TYPE"
0x18000790a  mov     [rbp+57h+var_90], rax
0x18000790e  mov     r10d, 2
0x180007914  mov     [rbp+57h+var_68], 2
0x18000791c  xorps   xmm0, xmm0
0x18000791f  movdqa  [rbp+57h+var_80], xmm0
0x180007924  mov     [rbp+57h+var_70], r9d
0x180007928  mov     [rbp+57h+var_48], 48h ; 'H'
0x18000792f  lea     eax, [r10-1]
0x180007933  mov     [rbp+57h+var_88], eax
0x180007936  lea     edx, [rax+3]
0x180007939  mov     [rbp+57h+var_6C], eax
0x18000793c  lea     rax, aContextid; "ContextId"
0x180007943  mov     [rbp+57h+var_50], rax
0x180007947  lea     rax, aRequestauthtyp; "RequestAuthType"
0x18000794e  mov     [rbp+57h+var_28], rax
0x180007952  lea     rax, [rbp+57h+arg_10]
0x180007956  mov     [rbp+57h+var_18], rax
0x18000795a  mov     [rbp+57h+var_84], edx
0x18000795d  mov     [rbp+57h+var_40], r9
0x180007961  mov     [rbp+57h+var_38], 10h
0x180007968  mov     [rbp+57h+var_30], r9
0x18000796c  mov     [rbp+57h+var_20], 13h
0x180007973  mov     [rbp+57h+var_10], edx
0x180007976  sub     r8d, 1
0x18000797a  jz      short loc_1800079CB
0x18000797c  sub     r8d, 1
0x180007980  jz      short loc_1800079C2
0x180007982  sub     r8d, r10d
0x180007985  jz      short loc_1800079B9
0x180007987  sub     r8d, 0Ch
0x18000798b  jz      short loc_1800079B0
0x18000798d  sub     r8d, 30h ; '0'
0x180007991  jz      short loc_1800079A7
0x180007993  cmp     r8d, 40h ; '@'
0x180007997  jz      short loc_18000799E
0x180007999  mov     eax, r9d
0x18000799c  jmp     short loc_1800079D2
0x18000799e  lea     rax, aCertmap; "CertMap"
0x1800079a5  jmp     short loc_1800079D2
0x1800079a7  lea     rax, aPassport; "Passport"
0x1800079ae  jmp     short loc_1800079D2
0x1800079b0  lea     rax, aDigest; "Digest"
0x1800079b7  jmp     short loc_1800079D2
0x1800079b9  lea     rax, aNt; "NT"
0x1800079c0  jmp     short loc_1800079D2
0x1800079c2  lea     rax, aBasic; "Basic"
0x1800079c9  jmp     short loc_1800079D2
0x1800079cb  lea     rax, aAnonymous; "Anonymous"
0x1800079d2  mov     [rbp+57h+var_8], rax
0x1800079d6  lea     rdx, [rbp+57h+var_B0]
0x1800079da  lea     rax, [rbp+57h+var_50]
0x1800079de  mov     [rbp+57h+var_60], rax
0x1800079e2  mov     rax, [rcx]
0x1800079e5  mov     rax, [rax+10h]
0x1800079e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079ee  xor     eax, eax
0x1800079f0  add     rsp, 0D0h
0x1800079f7  pop     rbp
0x1800079f8  retn
```
