# WinHttpRequest::GetCopyOfResponseBuffer(ushort * *,ulong *)

- ea: `0x1800964e4`
- end: `0x18009670b`
- name: `?GetCopyOfResponseBuffer@WinHttpRequest@@QEAAJPEAPEAGPEAK@Z`
- size: `551`
- prototype: `__int64 __fastcall(WinHttpRequest *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800992bc`

## callees

- `0x180004a24`
- `0x180005f24`
- `0x180007df8`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x1800964e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800966d0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800966de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800966d0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800966de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009660b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009669e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009660b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009669e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800965ff`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180096691`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800965ff`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180096691`

## string_xrefs

- `0x18009650d`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x180096527`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x180096549`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x18009658f`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x180096623`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x18009665e`: `WinHttpRequest::GetCopyOfResponseBuffer`
- `0x1800966e7`: `WinHttpRequest::GetCopyOfResponseBuffer`

## pseudocode

```c
__int64 __fastcall WinHttpRequest::GetCopyOfResponseBuffer(
        WinHttpRequest *this,
        unsigned __int16 **a2,
        unsigned int *a3)
{
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  void *v8; // rax
  void *v9; // rbp
  int v10; // edi
  unsigned int v11; // eax
  unsigned __int64 cchWideChar; // rbx
  DWORD LastError; // eax
  unsigned __int16 *v14; // rsi
  size_t v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // r12d

  if ( !a2 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpRequest::GetCopyOfResponseBuffer", L"ppszOut");
    v7 = L"ppszOut";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"WinHttpRequest::GetCopyOfResponseBuffer", v7);
    goto LABEL_25;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpRequest::GetCopyOfResponseBuffer", L"pdwOut");
    v7 = L"pdwOut";
    goto LABEL_3;
  }
  *a2 = 0;
  *a3 = 0;
  v8 = operator new[]((unsigned int)(*((_DWORD *)this + 34) + 1), (const struct std::nothrow_t *)std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    v6 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"WinHttpRequest::GetCopyOfResponseBuffer");
    goto LABEL_25;
  }
  v10 = 0;
  memset_0(v8, 0, (unsigned int)(*((_DWORD *)this + 34) + 1));
  memcpy_s_0(v9, *((unsigned int *)this + 34), *((const void *const *)this + 16), *((unsigned int *)this + 34));
  *((_BYTE *)v9 + *((unsigned int *)this + 34)) = 0;
  v11 = MultiByteToWideChar(0xFDE9u, 8u, (LPCCH)v9, -1, 0, 0);
  cchWideChar = v11;
  if ( v11 || (LastError = GetLastError(), (v10 = LastError) == 0) )
  {
    v15 = 2 * cchWideChar;
    if ( !is_mul_ok(cchWideChar, 2u) )
      v15 = -1;
    lpWideCharStr = (WCHAR *)operator new[](v15, (const struct std::nothrow_t *)std::nothrow);
    v14 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      v17 = MultiByteToWideChar(0xFDE9u, 8u, (LPCCH)v9, -1, lpWideCharStr, cchWideChar);
      if ( !v17 )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError )
          goto LABEL_11;
      }
      *a2 = v14;
      v6 = 0;
      v14 = 0;
      *a3 = v17;
    }
    else
    {
      v6 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"WinHttpRequest::GetCopyOfResponseBuffer");
    }
    if ( !v10 )
      goto LABEL_23;
    goto LABEL_20;
  }
  v14 = 0;
LABEL_11:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"WinHttpRequest::GetCopyOfResponseBuffer",
    L"MultiByteToWideChar",
    LastError);
LABEL_20:
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  else
    v6 = v10;
LABEL_23:
  free(v9);
  if ( v14 )
    free(v14);
LABEL_25:
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"WinHttpRequest::GetCopyOfResponseBuffer", v6);
  return v6;
}

```

## disassembly

```asm
0x1800964e4  push    rbx
0x1800964e6  push    rbp
0x1800964e7  push    rsi
0x1800964e8  push    rdi
0x1800964e9  push    r12
0x1800964eb  push    r14
0x1800964ed  push    r15
0x1800964ef  sub     rsp, 30h
0x1800964f3  mov     r14, r8
0x1800964f6  mov     r15, rdx
0x1800964f9  mov     rbx, rcx
0x1800964fc  test    rdx, rdx
0x1800964ff  jnz     short loc_180096538
0x180096501  lea     r8, aPpszout; "ppszOut"
0x180096508  mov     ebx, 80070057h
0x18009650d  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x180096514  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18009651b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180096520  lea     rdx, aPpszout; "ppszOut"
0x180096527  lea     rcx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x18009652e  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180096533  jmp     loc_1800966E4
0x180096538  test    r14, r14
0x18009653b  jnz     short loc_180096565
0x18009653d  lea     r8, aPdwout; "pdwOut"
0x180096544  mov     ebx, 80070057h
0x180096549  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x180096550  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180096557  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009655c  lea     rdx, aPdwout; "pdwOut"
0x180096563  jmp     short loc_180096527
0x180096565  mov     qword ptr [rdx], 0
0x18009656c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180096573  mov     dword ptr [r8], 0
0x18009657a  mov     ecx, [rcx+88h]
0x180096580  inc     ecx; unsigned __int64
0x180096582  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180096587  mov     rbp, rax
0x18009658a  test    rax, rax
0x18009658d  jnz     short loc_1800965AC
0x18009658f  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x180096596  mov     ebx, 8007000Eh
0x18009659b  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800965a2  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800965a7  jmp     loc_1800966E4
0x1800965ac  mov     r8d, [rbx+88h]
0x1800965b3  xor     edx, edx; Val
0x1800965b5  inc     r8d; Size
0x1800965b8  mov     rcx, rbp; void *
0x1800965bb  xor     edi, edi
0x1800965bd  call    memset_0
0x1800965c2  mov     edx, [rbx+88h]; DestinationSize
0x1800965c8  mov     rcx, rbp; Destination
0x1800965cb  mov     r8, [rbx+80h]; Source
0x1800965d2  mov     r9d, edx; SourceSize
0x1800965d5  call    memcpy_s_0
0x1800965da  mov     eax, [rbx+88h]
0x1800965e0  lea     edx, [rdi+8]; dwFlags
0x1800965e3  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800965e7  mov     [rsp+68h+cchWideChar], edi; cchWideChar
0x1800965eb  mov     r9d, r12d; cbMultiByte
0x1800965ee  mov     [rsp+68h+lpWideCharStr], rdi; lpWideCharStr
0x1800965f3  mov     r8, rbp; lpMultiByteStr
0x1800965f6  mov     ecx, 0FDE9h; CodePage
0x1800965fb  mov     [rax+rbp], dil
0x1800965ff  call    cs:__imp_MultiByteToWideChar
0x180096605  mov     ebx, eax
0x180096607  test    eax, eax
0x180096609  jnz     short loc_18009663B
0x18009660b  call    cs:__imp_GetLastError
0x180096611  mov     edi, eax
0x180096613  test    eax, eax
0x180096615  jz      short loc_18009663B
0x180096617  xor     esi, esi
0x180096619  mov     r9d, eax
0x18009661c  lea     r8, aMultibytetowid; "MultiByteToWideChar"
0x180096623  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x18009662a  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180096631  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180096636  jmp     loc_1800966BC
0x18009663b  mov     eax, 2
0x180096640  mul     rbx
0x180096643  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009664a  cmovb   rax, r12
0x18009664e  mov     rcx, rax; unsigned __int64
0x180096651  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180096656  mov     rsi, rax
0x180096659  test    rax, rax
0x18009665c  jnz     short loc_180096678
0x18009665e  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x180096665  mov     ebx, 8007000Eh
0x18009666a  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180096671  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180096676  jmp     short loc_1800966B8
0x180096678  mov     [rsp+68h+cchWideChar], ebx; cchWideChar
0x18009667c  mov     r9d, r12d; cbMultiByte
0x18009667f  mov     r8, rbp; lpMultiByteStr
0x180096682  mov     [rsp+68h+lpWideCharStr], rsi; lpWideCharStr
0x180096687  mov     edx, 8; dwFlags
0x18009668c  mov     ecx, 0FDE9h; CodePage
0x180096691  call    cs:__imp_MultiByteToWideChar
0x180096697  mov     r12d, eax
0x18009669a  test    eax, eax
0x18009669c  jnz     short loc_1800966AE
0x18009669e  call    cs:__imp_GetLastError
0x1800966a4  mov     edi, eax
0x1800966a6  test    eax, eax
0x1800966a8  jnz     loc_180096619
0x1800966ae  mov     [r15], rsi
0x1800966b1  xor     ebx, ebx
0x1800966b3  xor     esi, esi
0x1800966b5  mov     [r14], r12d
0x1800966b8  test    edi, edi
0x1800966ba  jz      short loc_1800966CD
0x1800966bc  test    edi, edi
0x1800966be  jg      short loc_1800966C4
0x1800966c0  mov     ebx, edi
0x1800966c2  jmp     short loc_1800966CD
0x1800966c4  movzx   ebx, di
0x1800966c7  or      ebx, 80070000h
0x1800966cd  mov     rcx, rbp; Block
0x1800966d0  call    cs:__imp_free
0x1800966d6  test    rsi, rsi
0x1800966d9  jz      short loc_1800966E4
0x1800966db  mov     rcx, rsi; Block
0x1800966de  call    cs:__imp_free
0x1800966e4  mov     r8d, ebx
0x1800966e7  lea     rdx, aWinhttprequest_8; "WinHttpRequest::GetCopyOfResponseBuffer"
0x1800966ee  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800966f5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800966fa  mov     eax, ebx
0x1800966fc  add     rsp, 30h
0x180096700  pop     r15
0x180096702  pop     r14
0x180096704  pop     r12
0x180096706  pop     rdi
0x180096707  pop     rsi
0x180096708  pop     rbp
0x180096709  pop     rbx
0x18009670a  retn
```
