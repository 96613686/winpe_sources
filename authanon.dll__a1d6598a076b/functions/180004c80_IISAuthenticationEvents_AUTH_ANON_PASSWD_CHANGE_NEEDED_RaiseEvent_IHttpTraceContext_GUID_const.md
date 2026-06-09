# IISAuthenticationEvents::AUTH_ANON_PASSWD_CHANGE_NEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x180004c80`
- end: `0x180004d29`
- name: `?RaiseEvent@AUTH_ANON_PASSWD_CHANGE_NEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800043b8`

## callees

- `0x180006010`

## pseudocode

```c
__int64 __fastcall IISAuthenticationEvents::AUTH_ANON_PASSWD_CHANGE_NEEDED::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2)
{
  __int64 v2; // rax
  void (__fastcall *v3)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v5[5]; // [rsp+20h] [rbp-39h] BYREF
  int v6; // [rsp+48h] [rbp-11h]
  int v7; // [rsp+4Ch] [rbp-Dh]
  __int128 v8; // [rsp+50h] [rbp-9h]
  int v9; // [rsp+60h] [rbp+7h]
  int v10; // [rsp+64h] [rbp+Bh]
  __int64 v11; // [rsp+68h] [rbp+Fh]
  const wchar_t **v12; // [rsp+70h] [rbp+17h]
  const wchar_t *v13; // [rsp+80h] [rbp+27h] BYREF
  int v14; // [rsp+88h] [rbp+2Fh]
  __int64 v15; // [rsp+90h] [rbp+37h]
  int v16; // [rsp+98h] [rbp+3Fh]
  __int64 v17; // [rsp+A0h] [rbp+47h]

  v5[1] = 2;
  v7 = 2;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v5[3] = 24;
  v5[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"AUTH_ANON_PASSWD_CHANGE_NEEDED";
  v6 = 1;
  v10 = 1;
  v13 = L"ContextId";
  v12 = &v13;
  v2 = *(_QWORD *)a1;
  v9 = 0;
  v15 = 0;
  v17 = 0;
  v3 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v2 + 16);
  v11 = 1;
  v8 = 0;
  v14 = 72;
  v16 = 16;
  v3(a1, v5);
  return 0;
}

```

## disassembly

```asm
0x180004c80  push    rbp
0x180004c82  lea     rbp, [rsp-57h]
0x180004c87  sub     rsp, 0B0h
0x180004c8e  mov     edx, 2
0x180004c93  mov     [rbp+57h+var_88], 2
0x180004c9b  mov     [rbp+57h+var_64], edx
0x180004c9e  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004ca5  mov     [rbp+57h+var_90], rax
0x180004ca9  xorps   xmm0, xmm0
0x180004cac  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180004cb3  mov     [rbp+57h+var_78], 18h
0x180004cbb  mov     [rbp+57h+var_80], rax
0x180004cbf  lea     rax, aAuthAnonPasswd; "AUTH_ANON_PASSWD_CHANGE_NEEDED"
0x180004cc6  mov     [rbp+57h+var_70], rax
0x180004cca  lea     eax, [rdx-1]
0x180004ccd  mov     [rbp+57h+var_68], eax
0x180004cd0  xor     edx, edx
0x180004cd2  mov     [rbp+57h+var_4C], eax
0x180004cd5  lea     rax, aContextid; "ContextId"
0x180004cdc  mov     [rbp+57h+var_30], rax
0x180004ce0  lea     rax, [rbp+57h+var_30]
0x180004ce4  mov     [rbp+57h+var_40], rax
0x180004ce8  mov     rax, [rcx]
0x180004ceb  mov     [rbp+57h+var_50], edx
0x180004cee  mov     [rbp+57h+var_20], rdx
0x180004cf2  mov     [rbp+57h+var_10], rdx
0x180004cf6  lea     rdx, [rbp+57h+var_90]
0x180004cfa  mov     rax, [rax+10h]
0x180004cfe  mov     [rbp+57h+var_48], 1
0x180004d06  movdqa  [rbp+57h+var_60], xmm0
0x180004d0b  mov     [rbp+57h+var_28], 48h ; 'H'
0x180004d12  mov     [rbp+57h+var_18], 10h
0x180004d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d1e  xor     eax, eax
0x180004d20  add     rsp, 0B0h
0x180004d27  pop     rbp
0x180004d28  retn
```
