# IISAuthenticationEvents::AUTH_SSPI_CONTINUE_NEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)

- ea: `0x180005adc`
- end: `0x180005bc8`
- name: `?RaiseEvent@AUTH_SSPI_CONTINUE_NEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z`
- size: `236`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021f0`

## callees

- `0x180005adc`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall IISAuthenticationEvents::AUTH_SSPI_CONTINUE_NEEDED::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  int v3; // eax
  __int64 v4; // rax
  __int64 v5; // rax
  _QWORD v7[5]; // [rsp+20h] [rbp-59h] BYREF
  int v8; // [rsp+48h] [rbp-31h]
  int v9; // [rsp+4Ch] [rbp-2Dh]
  __int128 v10; // [rsp+50h] [rbp-29h]
  int v11; // [rsp+60h] [rbp-19h]
  int v12; // [rsp+64h] [rbp-15h]
  int v13; // [rsp+68h] [rbp-11h]
  _QWORD v14[2]; // [rsp+6Ch] [rbp-Dh] BYREF
  const wchar_t *v15; // [rsp+80h] [rbp+7h] BYREF
  int v16; // [rsp+88h] [rbp+Fh]
  __int64 v17; // [rsp+90h] [rbp+17h]
  int v18; // [rsp+98h] [rbp+1Fh]
  __int64 v19; // [rsp+A0h] [rbp+27h]
  const wchar_t *v20; // [rsp+A8h] [rbp+2Fh]
  int v21; // [rsp+B0h] [rbp+37h]
  const unsigned __int16 *v22; // [rsp+B8h] [rbp+3Fh]
  int v23; // [rsp+C0h] [rbp+47h]
  __int64 v24; // [rsp+C8h] [rbp+4Fh]

  v7[1] = 2;
  memset(v14, 0, 12);
  v13 = 2;
  v7[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v7[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
  v7[4] = L"AUTH_SSPI_CONTINUE_NEEDED";
  v8 = 1;
  v12 = 1;
  v15 = L"ContextId";
  v20 = L"PackageName";
  v7[3] = 23;
  v9 = 4;
  v10 = 0;
  v11 = 0;
  v16 = 72;
  v17 = 0;
  v18 = 16;
  v19 = 0;
  v21 = 31;
  v22 = a3;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v3 = 2 * v4 + 2;
  }
  else
  {
    v3 = 0;
  }
  v23 = v3;
  *(_QWORD *)((char *)v14 + 4) = &v15;
  v5 = *(_QWORD *)a1;
  v24 = 0;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v5 + 16))(a1, v7);
  return 0;
}

```

## disassembly

```asm
0x180005adc  push    rbp
0x180005ade  lea     rbp, [rsp-57h]
0x180005ae3  sub     rsp, 0D0h
0x180005aea  xor     eax, eax
0x180005aec  mov     [rbp+57h+var_A8], 2
0x180005af4  mov     [rbp+57h+var_64], rax
0x180005af8  mov     edx, 2
0x180005afd  mov     [rbp+57h+var_5C], eax
0x180005b00  xorps   xmm0, xmm0
0x180005b03  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180005b0a  mov     [rbp+57h+var_68], edx
0x180005b0d  mov     [rbp+57h+var_B0], rax
0x180005b11  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180005b18  mov     [rbp+57h+var_A0], rax
0x180005b1c  lea     rax, aAuthSspiContin; "AUTH_SSPI_CONTINUE_NEEDED"
0x180005b23  mov     [rbp+57h+var_90], rax
0x180005b27  lea     eax, [rdx-1]
0x180005b2a  xor     edx, edx
0x180005b2c  mov     [rbp+57h+var_88], eax
0x180005b2f  mov     [rbp+57h+var_6C], eax
0x180005b32  lea     rax, aContextid; "ContextId"
0x180005b39  mov     [rbp+57h+var_50], rax
0x180005b3d  lea     rax, aPackagename; "PackageName"
0x180005b44  mov     [rbp+57h+var_28], rax
0x180005b48  mov     [rbp+57h+var_98], 17h
0x180005b50  mov     [rbp+57h+var_84], 4
0x180005b57  movdqa  [rbp+57h+var_80], xmm0
0x180005b5c  mov     [rbp+57h+var_70], edx
0x180005b5f  mov     [rbp+57h+var_48], 48h ; 'H'
0x180005b66  mov     [rbp+57h+var_40], rdx
0x180005b6a  mov     [rbp+57h+var_38], 10h
0x180005b71  mov     [rbp+57h+var_30], rdx
0x180005b75  mov     [rbp+57h+var_20], 1Fh
0x180005b7c  mov     [rbp+57h+var_18], r8
0x180005b80  test    r8, r8
0x180005b83  jnz     short loc_180005B89
0x180005b85  mov     eax, edx
0x180005b87  jmp     short loc_180005B9E
0x180005b89  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005b8d  inc     rax
0x180005b90  cmp     [r8+rax*2], dx
0x180005b95  jnz     short loc_180005B8D
0x180005b97  lea     eax, ds:2[rax*2]
0x180005b9e  mov     [rbp+57h+var_10], eax
0x180005ba1  lea     rax, [rbp+57h+var_50]
0x180005ba5  mov     [rbp+57h+var_64+4], rax
0x180005ba9  mov     rax, [rcx]
0x180005bac  mov     [rbp+57h+var_8], rdx
0x180005bb0  lea     rdx, [rbp+57h+var_B0]
0x180005bb4  mov     rax, [rax+10h]
0x180005bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bbd  xor     eax, eax
0x180005bbf  add     rsp, 0D0h
0x180005bc6  pop     rbp
0x180005bc7  retn
```
