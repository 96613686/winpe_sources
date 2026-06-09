# TraceAuthSucceeded(IHttpContext *,IHttpUser *,int)

- ea: `0x1800058c8`
- end: `0x180005a17`
- name: `?TraceAuthSucceeded@@YAJPEAVIHttpContext@@PEAVIHttpUser@@H@Z`
- size: `335`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IHttpUser *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001c70`

## callees

- `0x18000568c`
- `0x1800058c8`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005994`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000598a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000598a`

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
0x1800058c8  mov     rax, rsp
0x1800058cb  mov     [rax+10h], rbx
0x1800058cf  mov     [rax+20h], rsi
0x1800058d3  mov     [rax+18h], r8d
0x1800058d7  push    rdi
0x1800058d8  push    r14
0x1800058da  push    r15
0x1800058dc  sub     rsp, 60h
0x1800058e0  xor     ebx, ebx
0x1800058e2  mov     r14, rdx
0x1800058e5  mov     [rax+8], ebx
0x1800058e8  mov     r15, rcx
0x1800058eb  lea     edi, [rbx+4]
0x1800058ee  mov     [rax+18h], edi
0x1800058f1  mov     rax, [rcx]
0x1800058f4  mov     rax, [rax+110h]
0x1800058fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005900  mov     rcx, rax
0x180005903  lea     rdx, [rsp+78h+var_38]
0x180005908  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000590f  xorps   xmm0, xmm0
0x180005912  mov     [rsp+78h+var_38], rax
0x180005917  movdqu  [rsp+78h+var_30], xmm0
0x18000591d  mov     rax, [rcx]
0x180005920  mov     rax, [rax]
0x180005923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005928  test    eax, eax
0x18000592a  js      loc_1800059FF
0x180005930  cmp     dword ptr [rsp+78h+var_30+8], ebx
0x180005934  jz      loc_1800059FF
0x18000593a  cmp     dword ptr [rsp+78h+var_30+4], edi
0x18000593e  jb      loc_1800059FF
0x180005944  cmp     dword ptr [rsp+78h+var_30], 2
0x180005949  jz      short loc_180005956
0x18000594b  test    byte ptr [rsp+78h+var_30], 2
0x180005950  jz      loc_1800059FF
0x180005956  mov     rax, [r14]
0x180005959  mov     rcx, r14
0x18000595c  mov     rax, [rax+20h]
0x180005960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005965  test    rax, rax
0x180005968  jz      short loc_1800059AB
0x18000596a  lea     rcx, [rsp+78h+arg_0]
0x180005972  mov     r9d, edi; TokenInformationLength
0x180005975  mov     [rsp+78h+ReturnLength], rcx; ReturnLength
0x18000597a  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x180005982  mov     rcx, rax; TokenHandle
0x180005985  mov     edx, 9; TokenInformationClass
0x18000598a  call    cs:__imp_GetTokenInformation
0x180005990  test    eax, eax
0x180005992  jnz     short loc_1800059AB
0x180005994  call    cs:__imp_GetLastError
0x18000599a  mov     ebx, eax
0x18000599c  test    eax, eax
0x18000599e  jle     short loc_1800059FF
0x1800059a0  movzx   ebx, ax
0x1800059a3  or      ebx, 80070000h
0x1800059a9  jmp     short loc_1800059FF
0x1800059ab  mov     rax, [r14]
0x1800059ae  mov     rcx, r14
0x1800059b1  mov     esi, [rsp+78h+TokenInformation]
0x1800059b8  mov     rax, [rax+8]
0x1800059bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059c1  mov     rdi, rax
0x1800059c4  mov     rcx, r14
0x1800059c7  mov     rax, [r14]
0x1800059ca  mov     rax, [rax]
0x1800059cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d2  mov     rbx, rax
0x1800059d5  mov     rcx, r15
0x1800059d8  mov     rax, [r15]
0x1800059db  mov     rax, [rax+110h]
0x1800059e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e7  mov     [rsp+78h+var_48], esi; unsigned int
0x1800059eb  mov     rcx, rax; struct IHttpTraceContext *
0x1800059ee  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x1800059f3  mov     [rsp+78h+ReturnLength], rbx; unsigned __int16 *
0x1800059f8  call    ?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z; IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)
0x1800059fd  mov     ebx, eax
0x1800059ff  lea     r11, [rsp+78h+var_18]
0x180005a04  mov     eax, ebx
0x180005a06  mov     rbx, [r11+28h]
0x180005a0a  mov     rsi, [r11+38h]
0x180005a0e  mov     rsp, r11
0x180005a11  pop     r15
0x180005a13  pop     r14
0x180005a15  pop     rdi
0x180005a16  retn
```
