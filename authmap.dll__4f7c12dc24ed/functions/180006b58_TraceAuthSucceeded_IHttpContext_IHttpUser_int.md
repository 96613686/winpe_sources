# TraceAuthSucceeded(IHttpContext *,IHttpUser *,int)

- ea: `0x180006b58`
- end: `0x180006ca7`
- name: `?TraceAuthSucceeded@@YAJPEAVIHttpContext@@PEAVIHttpUser@@H@Z`
- size: `335`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IHttpUser *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001da0`

## callees

- `0x18000691c`
- `0x180006b58`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c24`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006c1a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006c1a`

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
0x180006b58  mov     rax, rsp
0x180006b5b  mov     [rax+10h], rbx
0x180006b5f  mov     [rax+20h], rsi
0x180006b63  mov     [rax+18h], r8d
0x180006b67  push    rdi
0x180006b68  push    r14
0x180006b6a  push    r15
0x180006b6c  sub     rsp, 60h
0x180006b70  xor     ebx, ebx
0x180006b72  mov     r14, rdx
0x180006b75  mov     [rax+8], ebx
0x180006b78  mov     r15, rcx
0x180006b7b  lea     edi, [rbx+4]
0x180006b7e  mov     [rax+18h], edi
0x180006b81  mov     rax, [rcx]
0x180006b84  mov     rax, [rax+110h]
0x180006b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b90  mov     rcx, rax
0x180006b93  lea     rdx, [rsp+78h+var_38]
0x180006b98  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180006b9f  xorps   xmm0, xmm0
0x180006ba2  mov     [rsp+78h+var_38], rax
0x180006ba7  movdqu  [rsp+78h+var_30], xmm0
0x180006bad  mov     rax, [rcx]
0x180006bb0  mov     rax, [rax]
0x180006bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb8  test    eax, eax
0x180006bba  js      loc_180006C8F
0x180006bc0  cmp     dword ptr [rsp+78h+var_30+8], ebx
0x180006bc4  jz      loc_180006C8F
0x180006bca  cmp     dword ptr [rsp+78h+var_30+4], edi
0x180006bce  jb      loc_180006C8F
0x180006bd4  cmp     dword ptr [rsp+78h+var_30], 2
0x180006bd9  jz      short loc_180006BE6
0x180006bdb  test    byte ptr [rsp+78h+var_30], 2
0x180006be0  jz      loc_180006C8F
0x180006be6  mov     rax, [r14]
0x180006be9  mov     rcx, r14
0x180006bec  mov     rax, [rax+20h]
0x180006bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf5  test    rax, rax
0x180006bf8  jz      short loc_180006C3B
0x180006bfa  lea     rcx, [rsp+78h+arg_0]
0x180006c02  mov     r9d, edi; TokenInformationLength
0x180006c05  mov     [rsp+78h+ReturnLength], rcx; ReturnLength
0x180006c0a  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x180006c12  mov     rcx, rax; TokenHandle
0x180006c15  mov     edx, 9; TokenInformationClass
0x180006c1a  call    cs:__imp_GetTokenInformation
0x180006c20  test    eax, eax
0x180006c22  jnz     short loc_180006C3B
0x180006c24  call    cs:__imp_GetLastError
0x180006c2a  mov     ebx, eax
0x180006c2c  test    eax, eax
0x180006c2e  jle     short loc_180006C8F
0x180006c30  movzx   ebx, ax
0x180006c33  or      ebx, 80070000h
0x180006c39  jmp     short loc_180006C8F
0x180006c3b  mov     rax, [r14]
0x180006c3e  mov     rcx, r14
0x180006c41  mov     esi, [rsp+78h+TokenInformation]
0x180006c48  mov     rax, [rax+8]
0x180006c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c51  mov     rdi, rax
0x180006c54  mov     rcx, r14
0x180006c57  mov     rax, [r14]
0x180006c5a  mov     rax, [rax]
0x180006c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c62  mov     rbx, rax
0x180006c65  mov     rcx, r15
0x180006c68  mov     rax, [r15]
0x180006c6b  mov     rax, [rax+110h]
0x180006c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c77  mov     [rsp+78h+var_48], esi; unsigned int
0x180006c7b  mov     rcx, rax; struct IHttpTraceContext *
0x180006c7e  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x180006c83  mov     [rsp+78h+ReturnLength], rbx; unsigned __int16 *
0x180006c88  call    ?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z; IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)
0x180006c8d  mov     ebx, eax
0x180006c8f  lea     r11, [rsp+78h+var_18]
0x180006c94  mov     eax, ebx
0x180006c96  mov     rbx, [r11+28h]
0x180006c9a  mov     rsi, [r11+38h]
0x180006c9e  mov     rsp, r11
0x180006ca1  pop     r15
0x180006ca3  pop     r14
0x180006ca5  pop     rdi
0x180006ca6  retn
```
