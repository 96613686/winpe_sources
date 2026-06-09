# CleanupCallCtx

- ea: `0x180009a00`
- end: `0x180009c74`
- name: `CleanupCallCtx`
- size: `628`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002d40`
- `0x180002d70`
- `0x18000827c`
- `0x180008360`
- `0x180009a00`
- `0x180014ac0`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009a58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009a58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009a86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009a86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009be5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009be5`
- `webio!__imp_WebCloseHttpRequest` at `0x180009aa7`
- `webio!__imp_WebCloseHttpRequest` at `0x180009aa7`
- `webio!__imp_WebCloseSession` at `0x180009b16`
- `webio!__imp_WebCloseSession` at `0x180009b16`

## string_xrefs

- `0x180009ac8`: `CoId=%hs:WebCloseHttpHandle completes with error %d`
- `0x180009b37`: `CoId=%hs:WebCloseSession completes with error %d`

## pseudocode

```c
__int64 __fastcall CleanupCallCtx(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  unsigned int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // r8
  int v10; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v11[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v1 = a1 - 208;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 184));
  HfFreeHandle32(*((_QWORD *)SstpSvcGlobals + 22), v1 + 244);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 184));
  if ( *(_BYTE *)(v1 + 248) )
  {
    v2 = *(_QWORD *)(v1 + 448);
    if ( v2 )
    {
      v3 = WebCloseHttpRequest(v2, 0);
      if ( v3 )
      {
        if ( (byte_18002D803 & 8) != 0 )
        {
          LOWORD(v10) = 0;
          FormatRRASErrorString(&v10, L"CoId=%hs:WebCloseHttpHandle completes with error %d", v1 + 552, v3);
          if ( (byte_18002D803 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v10);
        }
      }
      *(_QWORD *)(v1 + 448) = 0;
    }
    v4 = *(_QWORD *)(v1 + 440);
    if ( v4 )
    {
      v5 = WebCloseSession(v4, 0);
      if ( v5 )
      {
        if ( (byte_18002D803 & 8) != 0 )
        {
          LOWORD(v10) = 0;
          FormatRRASErrorString(&v10, L"CoId=%hs:WebCloseSession completes with error %d", v1 + 552, v5);
          if ( (byte_18002D803 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v10);
        }
      }
      *(_QWORD *)(v1 + 440) = 0;
    }
    v6 = *((_QWORD *)&xmmword_18002DBA0 + 1);
    v7 = *(_QWORD *)(v1 + 544);
    if ( *((_QWORD *)&xmmword_18002DBA0 + 1) )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gHostRoutTemplateFunc)(
        gHostRoutEtwContext,
        *((_QWORD *)&xmmword_18002DBA0 + 1),
        L"Entering ReleaseHostRouteInfoContext");
      v6 = *((_QWORD *)&xmmword_18002DBA0 + 1);
    }
    if ( v7 )
    {
      DereferenceRefCount(v7);
      v6 = *((_QWORD *)&xmmword_18002DBA0 + 1);
    }
    if ( v6 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gHostRoutTemplateFunc)(
        gHostRoutEtwContext,
        v6,
        L"Leaving ReleaseHostRouteInfoContext");
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 288));
  if ( (byte_18002D803 & 8) != 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"CoId=%hs:Freeing up call ctx 0x%p", v1 + 552, v1);
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v10);
  }
  LOBYTE(v8) = 1;
  return FreeBufferToPool((char *)SstpSvcGlobals + 536, v1, v8);
}

```

## disassembly

```asm
0x180009a00  mov     [rsp-8+arg_8], rbx
0x180009a05  mov     [rsp-8+arg_10], rdi
0x180009a0a  push    rbp
0x180009a0b  lea     rbp, [rsp-730h]
0x180009a13  sub     rsp, 830h
0x180009a1a  mov     rax, cs:__security_cookie
0x180009a21  xor     rax, rsp
0x180009a24  mov     [rbp+730h+var_10], rax
0x180009a2b  lea     rbx, [rcx-0D0h]
0x180009a32  xor     eax, eax
0x180009a34  lea     rcx, [rsp+830h+var_80C]; void *
0x180009a39  mov     [rsp+830h+var_810], eax
0x180009a3d  xor     edx, edx; Val
0x180009a3f  mov     r8d, 7FCh; Size
0x180009a45  call    memset_0
0x180009a4a  mov     rcx, cs:SstpSvcGlobals
0x180009a51  add     rcx, 0B8h; lpCriticalSection
0x180009a58  call    cs:__imp_EnterCriticalSection
0x180009a5e  mov     rcx, cs:SstpSvcGlobals
0x180009a65  lea     rdx, [rbx+0F4h]
0x180009a6c  mov     rcx, [rcx+0B0h]
0x180009a73  call    HfFreeHandle32
0x180009a78  mov     rcx, cs:SstpSvcGlobals
0x180009a7f  add     rcx, 0B8h; lpCriticalSection
0x180009a86  call    cs:__imp_LeaveCriticalSection
0x180009a8c  cmp     byte ptr [rbx+0F8h], 0
0x180009a93  jz      loc_180009BDE
0x180009a99  mov     rcx, [rbx+1C0h]
0x180009aa0  test    rcx, rcx
0x180009aa3  jz      short loc_180009B08
0x180009aa5  xor     edx, edx
0x180009aa7  call    cs:__imp_WebCloseHttpRequest
0x180009aad  test    eax, eax
0x180009aaf  jz      short loc_180009AFD
0x180009ab1  test    cs:byte_18002D803, 8
0x180009ab8  jz      short loc_180009AFD
0x180009aba  xor     ecx, ecx
0x180009abc  lea     r8, [rbx+228h]
0x180009ac3  mov     word ptr [rsp+830h+var_810], cx
0x180009ac8  lea     rdx, aCoidHsWebclose; "CoId=%hs:WebCloseHttpHandle completes w"...
0x180009acf  lea     rcx, [rsp+830h+var_810]
0x180009ad4  mov     r9d, eax
0x180009ad7  call    FormatRRASErrorString
0x180009adc  test    cs:byte_18002D803, 8
0x180009ae3  jz      short loc_180009AFD
0x180009ae5  lea     r8, [rsp+830h+var_810]
0x180009aea  lea     rdx, RasSSTPSvcTraceError
0x180009af1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009af8  call    McTemplateU0z_EventWriteTransfer
0x180009afd  mov     qword ptr [rbx+1C0h], 0
0x180009b08  mov     rcx, [rbx+1B8h]
0x180009b0f  test    rcx, rcx
0x180009b12  jz      short loc_180009B77
0x180009b14  xor     edx, edx
0x180009b16  call    cs:__imp_WebCloseSession
0x180009b1c  test    eax, eax
0x180009b1e  jz      short loc_180009B6C
0x180009b20  test    cs:byte_18002D803, 8
0x180009b27  jz      short loc_180009B6C
0x180009b29  xor     ecx, ecx
0x180009b2b  lea     r8, [rbx+228h]
0x180009b32  mov     word ptr [rsp+830h+var_810], cx
0x180009b37  lea     rdx, aCoidHsWebclose_1; "CoId=%hs:WebCloseSession completes with"...
0x180009b3e  lea     rcx, [rsp+830h+var_810]
0x180009b43  mov     r9d, eax
0x180009b46  call    FormatRRASErrorString
0x180009b4b  test    cs:byte_18002D803, 8
0x180009b52  jz      short loc_180009B6C
0x180009b54  lea     r8, [rsp+830h+var_810]
0x180009b59  lea     rdx, RasSSTPSvcTraceError
0x180009b60  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009b67  call    McTemplateU0z_EventWriteTransfer
0x180009b6c  mov     qword ptr [rbx+1B8h], 0
0x180009b77  mov     rdx, qword ptr cs:xmmword_18002DBA0+8
0x180009b7e  mov     rdi, [rbx+220h]
0x180009b85  test    rdx, rdx
0x180009b88  jz      short loc_180009BAB
0x180009b8a  mov     rcx, cs:gHostRoutEtwContext
0x180009b91  lea     r8, aEnteringReleas; "Entering ReleaseHostRouteInfoContext"
0x180009b98  mov     rax, cs:gHostRoutTemplateFunc
0x180009b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba4  mov     rdx, qword ptr cs:xmmword_18002DBA0+8
0x180009bab  test    rdi, rdi
0x180009bae  jz      short loc_180009BBF
0x180009bb0  mov     rcx, rdi
0x180009bb3  call    DereferenceRefCount
0x180009bb8  mov     rdx, qword ptr cs:xmmword_18002DBA0+8
0x180009bbf  test    rdx, rdx
0x180009bc2  jz      short loc_180009BDE
0x180009bc4  mov     rcx, cs:gHostRoutEtwContext
0x180009bcb  lea     r8, aLeavingRelease; "Leaving ReleaseHostRouteInfoContext"
0x180009bd2  mov     rax, cs:gHostRoutTemplateFunc
0x180009bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bde  lea     rcx, [rbx+120h]; lpCriticalSection
0x180009be5  call    cs:__imp_DeleteCriticalSection
0x180009beb  test    cs:byte_18002D803, 8
0x180009bf2  jz      short loc_180009C37
0x180009bf4  xor     eax, eax
0x180009bf6  lea     r8, [rbx+228h]
0x180009bfd  mov     r9, rbx
0x180009c00  mov     word ptr [rsp+830h+var_810], ax
0x180009c05  lea     rdx, aCoidHsFreeingU; "CoId=%hs:Freeing up call ctx 0x%p"
0x180009c0c  lea     rcx, [rsp+830h+var_810]
0x180009c11  call    FormatRRASErrorString
0x180009c16  test    cs:byte_18002D803, 8
0x180009c1d  jz      short loc_180009C37
0x180009c1f  lea     r8, [rsp+830h+var_810]
0x180009c24  lea     rdx, RasSSTPSvcTraceError
0x180009c2b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009c32  call    McTemplateU0z_EventWriteTransfer
0x180009c37  mov     rcx, cs:SstpSvcGlobals
0x180009c3e  mov     r8b, 1
0x180009c41  add     rcx, 218h
0x180009c48  mov     rdx, rbx
0x180009c4b  call    FreeBufferToPool
0x180009c50  mov     rcx, [rbp+730h+var_10]
0x180009c57  xor     rcx, rsp; StackCookie
0x180009c5a  call    __security_check_cookie
0x180009c5f  lea     r11, [rsp+830h+var_s0]
0x180009c67  mov     rbx, [r11+18h]
0x180009c6b  mov     rdi, [r11+20h]
0x180009c6f  mov     rsp, r11
0x180009c72  pop     rbp
0x180009c73  retn
```
