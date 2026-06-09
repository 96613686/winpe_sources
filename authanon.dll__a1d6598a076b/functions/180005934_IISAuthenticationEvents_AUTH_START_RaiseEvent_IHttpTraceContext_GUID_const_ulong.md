# IISAuthenticationEvents::AUTH_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x180005934`
- end: `0x180005a65`
- name: `?RaiseEvent@AUTH_START@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001030`

## callees

- `0x180005934`
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
0x180005934  mov     [rsp-8+arg_10], r8d
0x180005939  push    rbp
0x18000593a  lea     rbp, [rsp-57h]
0x18000593f  sub     rsp, 0D0h
0x180005946  xor     r9d, r9d
0x180005949  mov     [rbp+57h+var_A8], 2
0x180005951  mov     [rbp+57h+var_98], 0Ah
0x180005959  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180005960  mov     [rbp+57h+var_B0], rax
0x180005964  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000596b  mov     [rbp+57h+var_A0], rax
0x18000596f  lea     rax, aAuthStart; "AUTH_START"
0x180005976  mov     [rbp+57h+var_90], rax
0x18000597a  mov     r10d, 2
0x180005980  mov     [rbp+57h+var_68], 2
0x180005988  xorps   xmm0, xmm0
0x18000598b  movdqa  [rbp+57h+var_80], xmm0
0x180005990  mov     [rbp+57h+var_70], r9d
0x180005994  mov     [rbp+57h+var_48], 48h ; 'H'
0x18000599b  lea     eax, [r10-1]
0x18000599f  mov     [rbp+57h+var_88], eax
0x1800059a2  lea     edx, [rax+3]
0x1800059a5  mov     [rbp+57h+var_6C], eax
0x1800059a8  lea     rax, aContextid; "ContextId"
0x1800059af  mov     [rbp+57h+var_50], rax
0x1800059b3  lea     rax, aAuthtypesuppor; "AuthTypeSupported"
0x1800059ba  mov     [rbp+57h+var_28], rax
0x1800059be  lea     rax, [rbp+57h+arg_10]
0x1800059c2  mov     [rbp+57h+var_18], rax
0x1800059c6  mov     [rbp+57h+var_84], edx
0x1800059c9  mov     [rbp+57h+var_40], r9
0x1800059cd  mov     [rbp+57h+var_38], 10h
0x1800059d4  mov     [rbp+57h+var_30], r9
0x1800059d8  mov     [rbp+57h+var_20], 13h
0x1800059df  mov     [rbp+57h+var_10], edx
0x1800059e2  sub     r8d, 1
0x1800059e6  jz      short loc_180005A37
0x1800059e8  sub     r8d, 1
0x1800059ec  jz      short loc_180005A2E
0x1800059ee  sub     r8d, r10d
0x1800059f1  jz      short loc_180005A25
0x1800059f3  sub     r8d, 0Ch
0x1800059f7  jz      short loc_180005A1C
0x1800059f9  sub     r8d, 30h ; '0'
0x1800059fd  jz      short loc_180005A13
0x1800059ff  cmp     r8d, 40h ; '@'
0x180005a03  jz      short loc_180005A0A
0x180005a05  mov     eax, r9d
0x180005a08  jmp     short loc_180005A3E
0x180005a0a  lea     rax, aMapclicert; "MapCliCert"
0x180005a11  jmp     short loc_180005A3E
0x180005a13  lea     rax, aPassport; "Passport"
0x180005a1a  jmp     short loc_180005A3E
0x180005a1c  lea     rax, aDigest; "Digest"
0x180005a23  jmp     short loc_180005A3E
0x180005a25  lea     rax, aNt; "NT"
0x180005a2c  jmp     short loc_180005A3E
0x180005a2e  lea     rax, aBasic; "Basic"
0x180005a35  jmp     short loc_180005A3E
0x180005a37  lea     rax, aAnonymous; "Anonymous"
0x180005a3e  mov     [rbp+57h+var_8], rax
0x180005a42  lea     rdx, [rbp+57h+var_B0]
0x180005a46  lea     rax, [rbp+57h+var_50]
0x180005a4a  mov     [rbp+57h+var_60], rax
0x180005a4e  mov     rax, [rcx]
0x180005a51  mov     rax, [rax+10h]
0x180005a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a5a  xor     eax, eax
0x180005a5c  add     rsp, 0D0h
0x180005a63  pop     rbp
0x180005a64  retn
```
