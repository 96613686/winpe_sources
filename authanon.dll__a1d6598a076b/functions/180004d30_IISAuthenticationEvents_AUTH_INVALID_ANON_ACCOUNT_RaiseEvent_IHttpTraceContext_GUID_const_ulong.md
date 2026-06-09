# IISAuthenticationEvents::AUTH_INVALID_ANON_ACCOUNT::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x180004d30`
- end: `0x180004e02`
- name: `?RaiseEvent@AUTH_INVALID_ANON_ACCOUNT@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `210`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800043b8`

## callees

- `0x180006010`

## pseudocode

```c
__int64 __fastcall IISAuthenticationEvents::AUTH_INVALID_ANON_ACCOUNT::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3)
{
  __int64 v3; // rax
  void (__fastcall *v4)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v6[5]; // [rsp+20h] [rbp-59h] BYREF
  int v7; // [rsp+48h] [rbp-31h]
  int v8; // [rsp+4Ch] [rbp-2Dh]
  __int128 v9; // [rsp+50h] [rbp-29h]
  int v10; // [rsp+60h] [rbp-19h]
  int v11; // [rsp+64h] [rbp-15h]
  __int64 v12; // [rsp+68h] [rbp-11h]
  const wchar_t **v13; // [rsp+70h] [rbp-9h]
  const wchar_t *v14; // [rsp+80h] [rbp+7h] BYREF
  int v15; // [rsp+88h] [rbp+Fh]
  __int64 v16; // [rsp+90h] [rbp+17h]
  int v17; // [rsp+98h] [rbp+1Fh]
  __int64 v18; // [rsp+A0h] [rbp+27h]
  const wchar_t *v19; // [rsp+A8h] [rbp+2Fh]
  int v20; // [rsp+B0h] [rbp+37h]
  int *v21; // [rsp+B8h] [rbp+3Fh]
  int v22; // [rsp+C0h] [rbp+47h]
  __int64 v23; // [rsp+C8h] [rbp+4Fh]
  int v24; // [rsp+F0h] [rbp+77h] BYREF

  v24 = a3;
  v6[1] = 2;
  v8 = 2;
  v6[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v6[3] = 13;
  v6[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
  v6[4] = L"AUTH_INVALID_ANON_ACCOUNT";
  v7 = 1;
  v11 = 1;
  v14 = L"ContextId";
  v19 = L"ErrorCode";
  v21 = &v24;
  v13 = &v14;
  v3 = *(_QWORD *)a1;
  v10 = 0;
  v16 = 0;
  v18 = 0;
  v4 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v3 + 16);
  v23 = 0;
  v12 = 2;
  v9 = 0;
  v15 = 72;
  v17 = 16;
  v20 = 19;
  v22 = 4;
  v4(a1, v6);
  return 0;
}

```

## disassembly

```asm
0x180004d30  mov     [rsp-8+arg_10], r8d
0x180004d35  push    rbp
0x180004d36  lea     rbp, [rsp-57h]
0x180004d3b  sub     rsp, 0D0h
0x180004d42  mov     edx, 2
0x180004d47  mov     [rbp+57h+var_A8], 2
0x180004d4f  mov     [rbp+57h+var_84], edx
0x180004d52  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004d59  mov     [rbp+57h+var_B0], rax
0x180004d5d  xorps   xmm0, xmm0
0x180004d60  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180004d67  mov     [rbp+57h+var_98], 0Dh
0x180004d6f  mov     [rbp+57h+var_A0], rax
0x180004d73  lea     rax, aAuthInvalidAno; "AUTH_INVALID_ANON_ACCOUNT"
0x180004d7a  mov     [rbp+57h+var_90], rax
0x180004d7e  lea     eax, [rdx-1]
0x180004d81  mov     [rbp+57h+var_88], eax
0x180004d84  xor     edx, edx
0x180004d86  mov     [rbp+57h+var_6C], eax
0x180004d89  lea     rax, aContextid; "ContextId"
0x180004d90  mov     [rbp+57h+var_50], rax
0x180004d94  lea     rax, aErrorcode; "ErrorCode"
0x180004d9b  mov     [rbp+57h+var_28], rax
0x180004d9f  lea     rax, [rbp+57h+arg_10]
0x180004da3  mov     [rbp+57h+var_18], rax
0x180004da7  lea     rax, [rbp+57h+var_50]
0x180004dab  mov     [rbp+57h+var_60], rax
0x180004daf  mov     rax, [rcx]
0x180004db2  mov     [rbp+57h+var_70], edx
0x180004db5  mov     [rbp+57h+var_40], rdx
0x180004db9  mov     [rbp+57h+var_30], rdx
0x180004dbd  mov     rax, [rax+10h]
0x180004dc1  mov     [rbp+57h+var_8], rdx
0x180004dc5  lea     rdx, [rbp+57h+var_B0]
0x180004dc9  mov     [rbp+57h+var_68], 2
0x180004dd1  movdqa  [rbp+57h+var_80], xmm0
0x180004dd6  mov     [rbp+57h+var_48], 48h ; 'H'
0x180004ddd  mov     [rbp+57h+var_38], 10h
0x180004de4  mov     [rbp+57h+var_20], 13h
0x180004deb  mov     [rbp+57h+var_10], 4
0x180004df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004df7  xor     eax, eax
0x180004df9  add     rsp, 0D0h
0x180004e00  pop     rbp
0x180004e01  retn
```
