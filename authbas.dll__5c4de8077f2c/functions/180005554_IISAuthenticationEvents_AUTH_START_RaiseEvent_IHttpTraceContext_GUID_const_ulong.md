# IISAuthenticationEvents::AUTH_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x180005554`
- end: `0x180005685`
- name: `?RaiseEvent@AUTH_START@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c74`

## callees

- `0x180005554`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall IISAuthenticationEvents::AUTH_START::RaiseEvent(
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
  v10[3] = 10;
  v10[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v10[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
  v10[4] = L"AUTH_START";
  v16 = 2;
  v13 = 0;
  v14 = 0;
  v19 = 72;
  v11 = 1;
  v15 = 1;
  v18 = L"ContextId";
  v23 = L"AuthTypeSupported";
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
              v8 = L"MapCliCert";
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
0x180005554  mov     [rsp-8+arg_10], r8d
0x180005559  push    rbp
0x18000555a  lea     rbp, [rsp-57h]
0x18000555f  sub     rsp, 0D0h
0x180005566  xor     r9d, r9d
0x180005569  mov     [rbp+57h+var_A8], 2
0x180005571  mov     [rbp+57h+var_98], 0Ah
0x180005579  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180005580  mov     [rbp+57h+var_B0], rax
0x180005584  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000558b  mov     [rbp+57h+var_A0], rax
0x18000558f  lea     rax, aAuthStart; "AUTH_START"
0x180005596  mov     [rbp+57h+var_90], rax
0x18000559a  mov     r10d, 2
0x1800055a0  mov     [rbp+57h+var_68], 2
0x1800055a8  xorps   xmm0, xmm0
0x1800055ab  movdqa  [rbp+57h+var_80], xmm0
0x1800055b0  mov     [rbp+57h+var_70], r9d
0x1800055b4  mov     [rbp+57h+var_48], 48h ; 'H'
0x1800055bb  lea     eax, [r10-1]
0x1800055bf  mov     [rbp+57h+var_88], eax
0x1800055c2  lea     edx, [rax+3]
0x1800055c5  mov     [rbp+57h+var_6C], eax
0x1800055c8  lea     rax, aContextid; "ContextId"
0x1800055cf  mov     [rbp+57h+var_50], rax
0x1800055d3  lea     rax, aAuthtypesuppor; "AuthTypeSupported"
0x1800055da  mov     [rbp+57h+var_28], rax
0x1800055de  lea     rax, [rbp+57h+arg_10]
0x1800055e2  mov     [rbp+57h+var_18], rax
0x1800055e6  mov     [rbp+57h+var_84], edx
0x1800055e9  mov     [rbp+57h+var_40], r9
0x1800055ed  mov     [rbp+57h+var_38], 10h
0x1800055f4  mov     [rbp+57h+var_30], r9
0x1800055f8  mov     [rbp+57h+var_20], 13h
0x1800055ff  mov     [rbp+57h+var_10], edx
0x180005602  sub     r8d, 1
0x180005606  jz      short loc_180005657
0x180005608  sub     r8d, 1
0x18000560c  jz      short loc_18000564E
0x18000560e  sub     r8d, r10d
0x180005611  jz      short loc_180005645
0x180005613  sub     r8d, 0Ch
0x180005617  jz      short loc_18000563C
0x180005619  sub     r8d, 30h ; '0'
0x18000561d  jz      short loc_180005633
0x18000561f  cmp     r8d, 40h ; '@'
0x180005623  jz      short loc_18000562A
0x180005625  mov     eax, r9d
0x180005628  jmp     short loc_18000565E
0x18000562a  lea     rax, aMapclicert; "MapCliCert"
0x180005631  jmp     short loc_18000565E
0x180005633  lea     rax, aPassport; "Passport"
0x18000563a  jmp     short loc_18000565E
0x18000563c  lea     rax, aDigest; "Digest"
0x180005643  jmp     short loc_18000565E
0x180005645  lea     rax, aNt; "NT"
0x18000564c  jmp     short loc_18000565E
0x18000564e  lea     rax, aBasic_0; "Basic"
0x180005655  jmp     short loc_18000565E
0x180005657  lea     rax, aAnonymous; "Anonymous"
0x18000565e  mov     [rbp+57h+var_8], rax
0x180005662  lea     rdx, [rbp+57h+var_B0]
0x180005666  lea     rax, [rbp+57h+var_50]
0x18000566a  mov     [rbp+57h+var_60], rax
0x18000566e  mov     rax, [rcx]
0x180005671  mov     rax, [rax+10h]
0x180005675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000567a  xor     eax, eax
0x18000567c  add     rsp, 0D0h
0x180005683  pop     rbp
0x180005684  retn
```
