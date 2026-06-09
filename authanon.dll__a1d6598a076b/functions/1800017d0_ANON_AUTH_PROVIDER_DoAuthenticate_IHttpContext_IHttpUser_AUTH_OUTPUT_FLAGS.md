# ANON_AUTH_PROVIDER::DoAuthenticate(IHttpContext *,IHttpUser * *,AUTH_OUTPUT_FLAGS *)

- ea: `0x1800017d0`
- end: `0x1800019c9`
- name: `?DoAuthenticate@ANON_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAPEAVIHttpUser@@PEAW4AUTH_OUTPUT_FLAGS@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(ANON_AUTH_PROVIDER *__hidden this, struct IHttpContext *, struct IHttpUser **, enum AUTH_OUTPUT_FLAGS *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800017d0`
- `0x1800019d0`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800019b0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800019b0`

## pseudocode

```c
__int64 __fastcall ANON_AUTH_PROVIDER::DoAuthenticate(
        ANON_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        struct IHttpUser **a3,
        enum AUTH_OUTPUT_FLAGS *a4)
{
  __int64 v6; // rax
  __int64 (__fastcall ***v7)(_QWORD, void *); // rax
  __int64 v8; // rax
  struct IHttpUser *v9; // r14
  __int64 v10; // rax
  int (__fastcall ***v11)(_QWORD, GUID **); // rax
  void *v13; // rax
  unsigned int v14; // ebp
  const unsigned __int16 *v15; // rsi
  const unsigned __int16 *v16; // rdi
  struct IHttpTraceContext *v17; // rax
  const struct _GUID *v18; // rdx
  unsigned int v19; // r8d
  int v20; // r9d
  DWORD ReturnLength; // [rsp+40h] [rbp-38h] BYREF
  GUID *v22; // [rsp+48h] [rbp-30h] BYREF
  __int128 v23; // [rsp+50h] [rbp-28h]
  int TokenInformation; // [rsp+90h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147942487LL;
  *(_DWORD *)a4 = 1;
  if ( !(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 48LL))(a2) )
  {
    v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
    v7 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
    v8 = (**v7)(v7, s_pModuleContext);
    v9 = *(struct IHttpUser **)(v8 + 136);
    if ( v9 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 48LL))(*(_QWORD *)(v8 + 136));
      *a3 = v9;
      v10 = *(_QWORD *)a2;
      TokenInformation = 4;
      ReturnLength = 0;
      v11 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(v10 + 272))(a2);
      v22 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v23 = 0;
      if ( (**v11)(v11, &v22) >= 0 && DWORD2(v23) && DWORD1(v23) >= 4 && ((_DWORD)v23 == 2 || (v23 & 2) != 0) )
      {
        v13 = (void *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)v9 + 32LL))(v9);
        if ( !v13 || GetTokenInformation(v13, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength) )
        {
          v14 = TokenInformation;
          v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)v9 + 8LL))(v9);
          v16 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(struct IHttpUser *))v9)(v9);
          v17 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
          IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(v17, v18, v19, v20, v16, v15, v14);
        }
        else
        {
          GetLastError();
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800017d0  push    rbx
0x1800017d2  push    rdi
0x1800017d3  sub     rsp, 68h
0x1800017d7  mov     rdi, r8
0x1800017da  mov     rbx, rdx
0x1800017dd  test    r8, r8
0x1800017e0  jz      loc_180001960
0x1800017e6  mov     dword ptr [r9], 1
0x1800017ed  mov     rcx, rdx
0x1800017f0  mov     rax, [rdx]
0x1800017f3  mov     rax, [rax+30h]
0x1800017f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017fc  test    rax, rax
0x1800017ff  jnz     loc_1800018C8
0x180001805  mov     rax, [rbx]
0x180001808  mov     rcx, rbx
0x18000180b  mov     [rsp+78h+var_18], r14
0x180001810  mov     rax, [rax+0A0h]
0x180001817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000181c  mov     rdx, rax
0x18000181f  mov     rcx, [rax]
0x180001822  mov     rax, [rcx+18h]
0x180001826  mov     rcx, rdx
0x180001829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000182e  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180001835  mov     r8, rax
0x180001838  mov     rcx, [rax]
0x18000183b  mov     rax, [rcx]
0x18000183e  mov     rcx, r8
0x180001841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001846  mov     r14, [rax+88h]
0x18000184d  test    r14, r14
0x180001850  jz      short loc_1800018C3
0x180001852  mov     rax, [r14]
0x180001855  mov     rcx, r14
0x180001858  mov     rax, [rax+30h]
0x18000185c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001861  mov     [rdi], r14
0x180001864  mov     rcx, rbx
0x180001867  mov     rax, [rbx]
0x18000186a  mov     [rsp+78h+TokenInformation], 4
0x180001875  mov     [rsp+78h+var_38], 0
0x18000187d  mov     rax, [rax+110h]
0x180001884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001889  mov     r8, rax
0x18000188c  lea     rdx, [rsp+78h+var_30]
0x180001891  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001898  xorps   xmm0, xmm0
0x18000189b  mov     [rsp+78h+var_30], rax
0x1800018a0  movdqu  [rsp+78h+var_28], xmm0
0x1800018a6  mov     rcx, [r8]
0x1800018a9  mov     rax, [rcx]
0x1800018ac  mov     rcx, r8
0x1800018af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018b4  test    eax, eax
0x1800018b6  js      short loc_1800018C3
0x1800018b8  cmp     dword ptr [rsp+78h+var_28+8], 0
0x1800018bd  jnz     loc_18000196A
0x1800018c3  mov     r14, [rsp+78h+var_18]
0x1800018c8  xor     eax, eax
0x1800018ca  add     rsp, 68h
0x1800018ce  pop     rdi
0x1800018cf  pop     rbx
0x1800018d0  retn
0x1800018d1  mov     rax, [r14]
0x1800018d4  mov     rcx, r14
0x1800018d7  mov     rax, [rax+20h]
0x1800018db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018e0  test    rax, rax
0x1800018e3  jnz     loc_180001990
0x1800018e9  mov     rax, [r14]
0x1800018ec  mov     rcx, r14
0x1800018ef  mov     [rsp+78h+arg_0], rbp
0x1800018f7  mov     ebp, [rsp+78h+TokenInformation]
0x1800018fe  mov     [rsp+78h+arg_8], rsi
0x180001906  mov     rax, [rax+8]
0x18000190a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000190f  mov     rdx, [r14]
0x180001912  mov     rsi, rax
0x180001915  mov     rcx, r14
0x180001918  mov     rax, [rdx]
0x18000191b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001920  mov     rcx, [rbx]
0x180001923  mov     rdi, rax
0x180001926  mov     rax, [rcx+110h]
0x18000192d  mov     rcx, rbx
0x180001930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001935  mov     [rsp+78h+var_48], ebp; unsigned int
0x180001939  mov     rcx, rax; struct IHttpTraceContext *
0x18000193c  mov     [rsp+78h+var_50], rsi; unsigned __int16 *
0x180001941  mov     [rsp+78h+ReturnLength], rdi; unsigned __int16 *
0x180001946  call    ?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z; IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)
0x18000194b  mov     rsi, [rsp+78h+arg_8]
0x180001953  mov     rbp, [rsp+78h+arg_0]
0x18000195b  jmp     loc_1800018C3
0x180001960  mov     eax, 80070057h
0x180001965  jmp     loc_1800018CA
0x18000196a  cmp     dword ptr [rsp+78h+var_28+4], 4
0x18000196f  jb      loc_1800018C3
0x180001975  mov     rax, qword ptr [rsp+78h+var_28]
0x18000197a  cmp     eax, 2
0x18000197d  jz      loc_1800018D1
0x180001983  test    al, 2
0x180001985  jz      loc_1800018C3
0x18000198b  jmp     loc_1800018D1
0x180001990  lea     rcx, [rsp+78h+var_38]
0x180001995  mov     r9d, 4; TokenInformationLength
0x18000199b  mov     [rsp+78h+ReturnLength], rcx; ReturnLength
0x1800019a0  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x1800019a8  mov     rcx, rax; TokenHandle
0x1800019ab  mov     edx, 9; TokenInformationClass
0x1800019b0  call    cs:__imp_GetTokenInformation
0x1800019b6  test    eax, eax
0x1800019b8  jnz     loc_1800018E9
0x1800019be  call    cs:__imp_GetLastError
0x1800019c4  jmp     loc_1800018C3
```
