# TraceAuthSucceeded(IHttpContext *,IHttpUser *,int)

- ea: `0x1800063d8`
- end: `0x180006527`
- name: `?TraceAuthSucceeded@@YAJPEAVIHttpContext@@PEAVIHttpUser@@H@Z`
- size: `335`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IHttpUser *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001e00`

## callees

- `0x18000619c`
- `0x1800063d8`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000649a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000649a`

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
0x1800063d8  mov     rax, rsp
0x1800063db  mov     [rax+10h], rbx
0x1800063df  mov     [rax+20h], rsi
0x1800063e3  mov     [rax+18h], r8d
0x1800063e7  push    rdi
0x1800063e8  push    r14
0x1800063ea  push    r15
0x1800063ec  sub     rsp, 60h
0x1800063f0  xor     ebx, ebx
0x1800063f2  mov     r14, rdx
0x1800063f5  mov     [rax+8], ebx
0x1800063f8  mov     r15, rcx
0x1800063fb  lea     edi, [rbx+4]
0x1800063fe  mov     [rax+18h], edi
0x180006401  mov     rax, [rcx]
0x180006404  mov     rax, [rax+110h]
0x18000640b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006410  mov     rcx, rax
0x180006413  lea     rdx, [rsp+78h+var_38]
0x180006418  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000641f  xorps   xmm0, xmm0
0x180006422  mov     [rsp+78h+var_38], rax
0x180006427  movdqu  [rsp+78h+var_30], xmm0
0x18000642d  mov     rax, [rcx]
0x180006430  mov     rax, [rax]
0x180006433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006438  test    eax, eax
0x18000643a  js      loc_18000650F
0x180006440  cmp     dword ptr [rsp+78h+var_30+8], ebx
0x180006444  jz      loc_18000650F
0x18000644a  cmp     dword ptr [rsp+78h+var_30+4], edi
0x18000644e  jb      loc_18000650F
0x180006454  cmp     dword ptr [rsp+78h+var_30], 2
0x180006459  jz      short loc_180006466
0x18000645b  test    byte ptr [rsp+78h+var_30], 2
0x180006460  jz      loc_18000650F
0x180006466  mov     rax, [r14]
0x180006469  mov     rcx, r14
0x18000646c  mov     rax, [rax+20h]
0x180006470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006475  test    rax, rax
0x180006478  jz      short loc_1800064BB
0x18000647a  lea     rcx, [rsp+78h+arg_0]
0x180006482  mov     r9d, edi; TokenInformationLength
0x180006485  mov     [rsp+78h+ReturnLength], rcx; ReturnLength
0x18000648a  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x180006492  mov     rcx, rax; TokenHandle
0x180006495  mov     edx, 9; TokenInformationClass
0x18000649a  call    cs:__imp_GetTokenInformation
0x1800064a0  test    eax, eax
0x1800064a2  jnz     short loc_1800064BB
0x1800064a4  call    cs:__imp_GetLastError
0x1800064aa  mov     ebx, eax
0x1800064ac  test    eax, eax
0x1800064ae  jle     short loc_18000650F
0x1800064b0  movzx   ebx, ax
0x1800064b3  or      ebx, 80070000h
0x1800064b9  jmp     short loc_18000650F
0x1800064bb  mov     rax, [r14]
0x1800064be  mov     rcx, r14
0x1800064c1  mov     esi, [rsp+78h+TokenInformation]
0x1800064c8  mov     rax, [rax+8]
0x1800064cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d1  mov     rdi, rax
0x1800064d4  mov     rcx, r14
0x1800064d7  mov     rax, [r14]
0x1800064da  mov     rax, [rax]
0x1800064dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e2  mov     rbx, rax
0x1800064e5  mov     rcx, r15
0x1800064e8  mov     rax, [r15]
0x1800064eb  mov     rax, [rax+110h]
0x1800064f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064f7  mov     [rsp+78h+var_48], esi; unsigned int
0x1800064fb  mov     rcx, rax; struct IHttpTraceContext *
0x1800064fe  mov     [rsp+78h+var_50], rdi; unsigned __int16 *
0x180006503  mov     [rsp+78h+ReturnLength], rbx; unsigned __int16 *
0x180006508  call    ?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z; IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)
0x18000650d  mov     ebx, eax
0x18000650f  lea     r11, [rsp+78h+var_18]
0x180006514  mov     eax, ebx
0x180006516  mov     rbx, [r11+28h]
0x18000651a  mov     rsi, [r11+38h]
0x18000651e  mov     rsp, r11
0x180006521  pop     r15
0x180006523  pop     r14
0x180006525  pop     rdi
0x180006526  retn
```
