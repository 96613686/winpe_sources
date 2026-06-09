# TraceAuthSucceeded(IHttpContext *,IHttpUser *,int)

- ea: `0x180008910`
- end: `0x180008a5d`
- name: `?TraceAuthSucceeded@@YAJPEAVIHttpContext@@PEAVIHttpUser@@H@Z`
- size: `333`
- prototype: `int(struct IHttpContext *, struct IHttpUser *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800021f0`

## callees

- `0x1800086d0`
- `0x180008910`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089d9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800089cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800089cf`

## pseudocode

```c
__int64 __fastcall TraceAuthSucceeded(struct IHttpContext *a1, struct IHttpUser *a2, int a3)
{
  unsigned int v3; // ebx
  int (__fastcall ***v7)(_QWORD, GUID **); // rax
  void *v8; // rax
  signed int LastError; // eax
  unsigned int v10; // esi
  const unsigned __int16 *v11; // rdi
  const unsigned __int16 *v12; // rbx
  struct IHttpTraceContext *v13; // rax
  const struct _GUID *v14; // rdx
  __int64 v15; // r8
  GUID *v17; // [rsp+40h] [rbp-48h] BYREF
  __int128 v18; // [rsp+48h] [rbp-40h]
  int TokenInformation; // [rsp+90h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+A8h] [rbp+20h] BYREF

  v3 = 0;
  ReturnLength = 0;
  TokenInformation = 4;
  v7 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  v17 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v18 = 0;
  if ( (**v7)(v7, &v17) >= 0 && DWORD2(v18) && DWORD1(v18) >= 4 && ((_DWORD)v18 == 2 || (v18 & 2) != 0) )
  {
    v8 = (void *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a2 + 32LL))(a2);
    if ( !v8 || GetTokenInformation(v8, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength) )
    {
      v10 = TokenInformation;
      v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a2 + 8LL))(a2);
      v12 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(struct IHttpUser *))a2)(a2);
      v13 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      return (unsigned int)IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(v13, v14, v15, a3, v12, v11, v10);
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180008910  mov     rax, rsp
0x180008913  mov     [rax+10h], rbx
0x180008917  push    rbp
0x180008918  push    rsi
0x180008919  push    rdi
0x18000891a  push    r14
0x18000891c  push    r15
0x18000891e  sub     rsp, 60h
0x180008922  xor     ebx, ebx
0x180008924  mov     ebp, r8d
0x180008927  mov     [rax+20h], ebx
0x18000892a  mov     r14, rdx
0x18000892d  mov     r15, rcx
0x180008930  lea     edi, [rbx+4]
0x180008933  mov     [rax+8], edi
0x180008936  mov     rax, [rcx]
0x180008939  mov     rax, [rax+110h]
0x180008940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008945  mov     rcx, rax
0x180008948  lea     rdx, [rsp+88h+var_48]
0x18000894d  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180008954  xorps   xmm0, xmm0
0x180008957  mov     [rsp+88h+var_48], rax
0x18000895c  movdqu  [rsp+88h+var_40], xmm0
0x180008962  mov     rax, [rcx]
0x180008965  mov     rax, [rax]
0x180008968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000896d  test    eax, eax
0x18000896f  js      loc_180008A47
0x180008975  cmp     dword ptr [rsp+88h+var_40+8], ebx
0x180008979  jz      loc_180008A47
0x18000897f  cmp     dword ptr [rsp+88h+var_40+4], edi
0x180008983  jb      loc_180008A47
0x180008989  cmp     dword ptr [rsp+88h+var_40], 2
0x18000898e  jz      short loc_18000899B
0x180008990  test    byte ptr [rsp+88h+var_40], 2
0x180008995  jz      loc_180008A47
0x18000899b  mov     rax, [r14]
0x18000899e  mov     rcx, r14
0x1800089a1  mov     rax, [rax+20h]
0x1800089a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089aa  test    rax, rax
0x1800089ad  jz      short loc_1800089F0
0x1800089af  lea     rcx, [rsp+88h+arg_18]
0x1800089b7  mov     r9d, edi; TokenInformationLength
0x1800089ba  mov     [rsp+88h+ReturnLength], rcx; ReturnLength
0x1800089bf  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x1800089c7  mov     rcx, rax; TokenHandle
0x1800089ca  mov     edx, 9; TokenInformationClass
0x1800089cf  call    cs:__imp_GetTokenInformation
0x1800089d5  test    eax, eax
0x1800089d7  jnz     short loc_1800089F0
0x1800089d9  call    cs:__imp_GetLastError
0x1800089df  mov     ebx, eax
0x1800089e1  test    eax, eax
0x1800089e3  jle     short loc_180008A47
0x1800089e5  movzx   ebx, ax
0x1800089e8  or      ebx, 80070000h
0x1800089ee  jmp     short loc_180008A47
0x1800089f0  mov     rax, [r14]
0x1800089f3  mov     rcx, r14
0x1800089f6  mov     esi, [rsp+88h+TokenInformation]
0x1800089fd  mov     rax, [rax+8]
0x180008a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a06  mov     rdi, rax
0x180008a09  mov     rcx, r14
0x180008a0c  mov     rax, [r14]
0x180008a0f  mov     rax, [rax]
0x180008a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a17  mov     rbx, rax
0x180008a1a  mov     rcx, r15
0x180008a1d  mov     rax, [r15]
0x180008a20  mov     rax, [rax+110h]
0x180008a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a2c  mov     [rsp+88h+var_58], esi; unsigned int
0x180008a30  mov     r9d, ebp; int
0x180008a33  mov     [rsp+88h+var_60], rdi; unsigned __int16 *
0x180008a38  mov     rcx, rax; struct IHttpTraceContext *
0x180008a3b  mov     [rsp+88h+ReturnLength], rbx; unsigned __int16 *
0x180008a40  call    ?RaiseEvent@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KHPEBG2K@Z; IISAuthenticationEvents::AUTH_SUCCEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,int,ushort const *,ushort const *,ulong)
0x180008a45  mov     ebx, eax
0x180008a47  mov     eax, ebx
0x180008a49  mov     rbx, [rsp+88h+arg_8]
0x180008a51  add     rsp, 60h
0x180008a55  pop     r15
0x180008a57  pop     r14
0x180008a59  pop     rdi
0x180008a5a  pop     rsi
0x180008a5b  pop     rbp
0x180008a5c  retn
```
