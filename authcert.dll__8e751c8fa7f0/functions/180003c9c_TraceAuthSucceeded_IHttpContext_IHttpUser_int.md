# TraceAuthSucceeded(IHttpContext *,IHttpUser *,int)

- ea: `0x180003c9c`
- end: `0x180003deb`
- name: `?TraceAuthSucceeded@@YAJPEAVIHttpContext@@PEAVIHttpUser@@H@Z`
- size: `335`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IHttpUser *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001e90`

## callees

- `0x180003a60`
- `0x180003c9c`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d68`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003d5e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003d5e`

## pseudocode

```c
__int64 __fastcall TraceAuthSucceeded(struct IHttpContext *a1, struct IHttpUser *a2)
{
  unsigned int v2; // ebx
  int (__fastcall ***v5)(_QWORD, GUID **); // rax
  void *v6; // rax
  signed int LastError; // eax
  unsigned int v8; // esi
  const unsigned __int16 *v9; // rdi
  const unsigned __int16 *v10; // rbx
  struct IHttpTraceContext *v11; // rax
  const struct _GUID *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  GUID *v16; // [rsp+40h] [rbp-38h] BYREF
  __int128 v17; // [rsp+48h] [rbp-30h]
  DWORD ReturnLength; // [rsp+80h] [rbp+8h] BYREF
  int TokenInformation; // [rsp+90h] [rbp+18h] BYREF

  v2 = 0;
  ReturnLength = 0;
  TokenInformation = 4;
  v5 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  v16 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v17 = 0;
  if ( (**v5)(v5, &v16) >= 0 && DWORD2(v17) && DWORD1(v17) >= 4 && ((_DWORD)v17 == 2 || (v17 & 2) != 0) )
  {
    v6 = (void *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a2 + 32LL))(a2);
    if ( !v6 || GetTokenInformation(v6, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength) )
    {
      v8 = TokenInformation;
      v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a2 + 8LL))(a2);
      v10 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(struct IHttpUser *))a2)(a2);
      v11 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      return (unsigned int)IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(v11, v12, v13, v14, v10, v9, v8);
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180003c9c  mov     rax, rsp
0x180003c9f  mov     [rax+10h], rbx
0x180003ca3  mov     [rax+20h], rsi
0x180003ca7  mov     [rax+18h], r8d
0x180003cab  push    rdi
0x180003cac  push    r14
0x180003cae  push    r15
0x180003cb0  sub     rsp, 60h
0x180003cb4  xor     ebx, ebx
0x180003cb6  mov     r14, rdx
0x180003cb9  mov     [rax+8], ebx
0x180003cbc  mov     r15, rcx
0x180003cbf  lea     edi, [rbx+4]
0x180003cc2  mov     [rax+18h], edi
0x180003cc5  mov     rax, [rcx]
0x180003cc8  mov     rax, [rax+110h]
0x180003ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cd4  mov     rcx, rax
0x180003cd7  lea     rdx, [rsp+78h+var_38]
0x180003cdc  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180003ce3  xorps   xmm0, xmm0
0x180003ce6  mov     [rsp+78h+var_38], rax
0x180003ceb  movdqu  [rsp+78h+var_30], xmm0
0x180003cf1  mov     rax, [rcx]
0x180003cf4  mov     rax, [rax]
0x180003cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cfc  test    eax, eax
0x180003cfe  js      loc_180003DD3
0x180003d04  cmp     dword ptr [rsp+78h+var_30+8], ebx
0x180003d08  jz      loc_180003DD3
0x180003d0e  cmp     dword ptr [rsp+78h+var_30+4], edi
0x180003d12  jb      loc_180003DD3
0x180003d18  cmp     dword ptr [rsp+78h+var_30], 2
0x180003d1d  jz      short loc_180003D2A
0x180003d1f  test    byte ptr [rsp+78h+var_30], 2
0x180003d24  jz      loc_180003DD3
0x180003d2a  mov     rax, [r14]
0x180003d2d  mov     rcx, r14
0x180003d30  mov     rax, [rax+20h]
0x180003d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d39  test    rax, rax
0x180003d3c  jz      short loc_180003D7F
0x180003d3e  lea     rcx, [rsp+78h+arg_0]
0x180003d46  mov     r9d, edi; TokenInformationLength
0x180003d49  mov     [rsp+78h+ReturnLength], rcx; ReturnLength
0x180003d4e  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x180003d56  mov     rcx, rax; TokenHandle
0x180003d59  mov     edx, 9; TokenInformationClass
0x180003d5e  call    cs:__imp_GetTokenInformation
0x180003d64  test    eax, eax
0x180003d66  jnz     short loc_180003D7F
0x180003d68  call    cs:__imp_GetLastError
0x180003d6e  mov     ebx, eax
0x180003d70  test    eax, eax
0x180003d72  jle     short loc_180003DD3
0x180003d74  movzx   ebx, ax
0x180003d77  or      ebx, 80070000h
0x180003d7d  jmp     short loc_180003DD3
0x180003d7f  mov     rax, [r14]
0x180003d82  mov     rcx, r14
0x180003d85  mov     esi, [rsp+78h+TokenInformation]
0x180003d8c  mov     rax, [rax+8]
0x180003d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d95  mov     rdi, rax
0x180003d98  mov     rcx, r14
0x180003d9b  mov     rax, [r14]
0x180003d9e  mov     rax, [rax]
0x180003da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da6  mov     rbx, rax
0x180003da9  mov     rcx, r15
0x180003dac  mov     rax, [r15]
0x180003daf  mov     rax, [rax+110h]
0x180003db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dbb  mov     [rsp+78h+var_48], esi; unsigned int
0x180003dbf  mov     rcx, rax; struct IHttpTraceContext *
0x180003dc2  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x180003dc7  mov     [rsp+78h+ReturnLength], rbx; unsigned __int16 *
0x180003dcc  call    ?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z; IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)
0x180003dd1  mov     ebx, eax
0x180003dd3  lea     r11, [rsp+78h+var_18]
0x180003dd8  mov     eax, ebx
0x180003dda  mov     rbx, [r11+28h]
0x180003dde  mov     rsi, [r11+38h]
0x180003de2  mov     rsp, r11
0x180003de5  pop     r15
0x180003de7  pop     r14
0x180003de9  pop     rdi
0x180003dea  retn
```
