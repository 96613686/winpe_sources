# IISAuthenticationEvents::AUTH_END::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x180005884`
- end: `0x18000592e`
- name: `?RaiseEvent@AUTH_END@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001030`

## callees

- `0x180006010`

## pseudocode

```c
__int64 __fastcall IISAuthenticationEvents::AUTH_END::RaiseEvent(struct IHttpTraceContext *a1, const struct _GUID *a2)
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
  v9 = 0;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v15 = 0;
  v5[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"AUTH_END";
  v6 = 1;
  v10 = 1;
  v13 = L"ContextId";
  v12 = &v13;
  v2 = *(_QWORD *)a1;
  v17 = 0;
  v5[3] = 28;
  v11 = 1;
  v3 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v2 + 16);
  v7 = 4;
  v8 = 0;
  v14 = 72;
  v16 = 16;
  v3(a1, v5);
  return 0;
}

```

## disassembly

```asm
0x180005884  push    rbp
0x180005886  lea     rbp, [rsp-57h]
0x18000588b  sub     rsp, 0B0h
0x180005892  xor     edx, edx
0x180005894  mov     [rbp+57h+var_88], 2
0x18000589c  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800058a3  mov     [rbp+57h+var_50], edx
0x1800058a6  mov     [rbp+57h+var_90], rax
0x1800058aa  xorps   xmm0, xmm0
0x1800058ad  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800058b4  mov     [rbp+57h+var_20], rdx
0x1800058b8  mov     [rbp+57h+var_80], rax
0x1800058bc  lea     rax, aAuthEnd; "AUTH_END"
0x1800058c3  mov     [rbp+57h+var_70], rax
0x1800058c7  mov     eax, 1
0x1800058cc  mov     [rbp+57h+var_68], eax
0x1800058cf  mov     [rbp+57h+var_4C], eax
0x1800058d2  lea     rax, aContextid; "ContextId"
0x1800058d9  mov     [rbp+57h+var_30], rax
0x1800058dd  lea     rax, [rbp+57h+var_30]
0x1800058e1  mov     [rbp+57h+var_40], rax
0x1800058e5  mov     rax, [rcx]
0x1800058e8  mov     [rbp+57h+var_10], rdx
0x1800058ec  lea     rdx, [rbp+57h+var_90]
0x1800058f0  mov     [rbp+57h+var_78], 1Ch
0x1800058f8  mov     [rbp+57h+var_48], 1
0x180005900  mov     rax, [rax+10h]
0x180005904  mov     [rbp+57h+var_64], 4
0x18000590b  movdqa  [rbp+57h+var_60], xmm0
0x180005910  mov     [rbp+57h+var_28], 48h ; 'H'
0x180005917  mov     [rbp+57h+var_18], 10h
0x18000591e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005923  xor     eax, eax
0x180005925  add     rsp, 0B0h
0x18000592c  pop     rbp
0x18000592d  retn
```
