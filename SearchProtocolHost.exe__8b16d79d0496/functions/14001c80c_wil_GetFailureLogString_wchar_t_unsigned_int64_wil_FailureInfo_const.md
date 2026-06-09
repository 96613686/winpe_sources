# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14001c80c`
- end: `0x14001cacd`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140009394`
- `0x14001fc40`
- `0x140020558`
- `0x1400394c0`

## callees

- `0x140005240`
- `0x140006210`
- `0x14001c80c`
- `0x14001ff48`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14001c949`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14001c949`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c9ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c9ca`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !this )
    return 0;
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v8 = "ReturnHr";
      v7 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v7 = "FailFast";
        else
          v7 = (const char *)&byte_140076968;
        goto LABEL_18;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_18;
  }
  v7 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v9 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v9, Buffer, 0x100u);
  }
  else
  {
    v9 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v9, 0x400u, Buffer, 0x100u, 0);
  }
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = (wil::details *)v14;
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer,
                          -2);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001c80c  mov     rax, rsp
0x14001c80f  push    rbp
0x14001c810  push    rsi
0x14001c811  push    rdi
0x14001c812  push    r14
0x14001c814  push    r15
0x14001c816  sub     rsp, 260h
0x14001c81d  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x14001c826  mov     [rax+20h], rbx
0x14001c82a  mov     rax, cs:__security_cookie
0x14001c831  xor     rax, rsp
0x14001c834  mov     [rsp+288h+var_38], rax
0x14001c83c  mov     rbx, r8
0x14001c83f  mov     rsi, rdx
0x14001c842  mov     r14, rcx
0x14001c845  xor     r15d, r15d
0x14001c848  test    rdx, rdx
0x14001c84b  jz      loc_14001CAA4
0x14001c851  test    rcx, rcx
0x14001c854  jz      loc_14001CAA4
0x14001c85a  mov     [rcx], r15w
0x14001c85e  mov     rax, cs:g_pfnResultLoggingCallback
0x14001c865  test    rax, rax
0x14001c868  jz      short loc_14001C88B
0x14001c86a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14001c871  jz      short loc_14001C88B
0x14001c873  mov     r8, rdx
0x14001c876  mov     rdx, rcx
0x14001c879  mov     rcx, rbx
0x14001c87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c881  cmp     [r14], r15w
0x14001c885  jnz     loc_14001CAA4
0x14001c88b  mov     ecx, [rbx]
0x14001c88d  mov     bpl, 8
0x14001c890  test    ecx, ecx
0x14001c892  jz      short loc_14001C8DD
0x14001c894  sub     ecx, 1
0x14001c897  jz      short loc_14001C8C5
0x14001c899  sub     ecx, 1
0x14001c89c  jz      short loc_14001C8B5
0x14001c89e  cmp     ecx, 1
0x14001c8a1  jz      short loc_14001C8AC
0x14001c8a3  lea     rdi, byte_140076968
0x14001c8aa  jmp     short loc_14001C8E4
0x14001c8ac  lea     rdi, aFailfast; "FailFast"
0x14001c8b3  jmp     short loc_14001C8E4
0x14001c8b5  lea     rax, aLoghr; "LogHr"
0x14001c8bc  lea     rdi, aLognt; "LogNt"
0x14001c8c3  jmp     short loc_14001C8D3
0x14001c8c5  lea     rax, aReturnhr; "ReturnHr"
0x14001c8cc  lea     rdi, aReturnnt; "ReturnNt"
0x14001c8d3  test    [rbx+4], bpl
0x14001c8d7  cmovz   rdi, rax
0x14001c8db  jmp     short loc_14001C8E4
0x14001c8dd  lea     rdi, aException; "Exception"
0x14001c8e4  xor     edx, edx; Val
0x14001c8e6  mov     r8d, 200h; Size
0x14001c8ec  lea     rcx, [rsp+288h+Buffer]; void *
0x14001c8f1  call    memset_0
0x14001c8f6  test    [rbx+4], bpl
0x14001c8fa  jz      short loc_14001C91F
0x14001c8fc  mov     ebp, [rbx+0Ch]
0x14001c8ff  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x14001c906  test    rax, rax
0x14001c909  jz      short loc_14001C94F
0x14001c90b  mov     r8d, 100h
0x14001c911  lea     rdx, [rsp+288h+Buffer]
0x14001c916  mov     ecx, ebp
0x14001c918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c91d  jmp     short loc_14001C94F
0x14001c91f  mov     ebp, [rbx+8]
0x14001c922  mov     [rsp+288h+Arguments], r15; Arguments
0x14001c927  mov     [rsp+288h+nSize], 100h; nSize
0x14001c92f  lea     rax, [rsp+288h+Buffer]
0x14001c934  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x14001c939  mov     r9d, 400h; dwLanguageId
0x14001c93f  mov     r8d, ebp; dwMessageId
0x14001c942  xor     edx, edx; lpSource
0x14001c944  mov     ecx, 1200h; dwFlags
0x14001c949  call    cs:__imp_FormatMessageW
0x14001c94f  lea     rsi, [r14+rsi*2]
0x14001c953  mov     r9, [rbx+38h]; wchar_t *
0x14001c957  mov     rax, [rbx+88h]
0x14001c95e  mov     rcx, [rbx+80h]
0x14001c965  mov     rdx, rsi; wchar_t *
0x14001c968  test    r9, r9
0x14001c96b  jz      short loc_14001C98F
0x14001c96d  mov     [rsp+288h+Arguments], rax
0x14001c972  mov     qword ptr [rsp+288h+nSize], rcx
0x14001c977  mov     eax, [rbx+40h]
0x14001c97a  mov     dword ptr [rsp+288h+lpBuffer], eax
0x14001c97e  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14001c985  mov     rcx, r14; this
0x14001c988  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001c98d  jmp     short loc_14001C9A6
0x14001c98f  mov     [rsp+288h+lpBuffer], rax
0x14001c994  mov     r9, rcx; wchar_t *
0x14001c997  lea     r8, aHsP; "%hs!%p: "
0x14001c99e  mov     rcx, r14; this
0x14001c9a1  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001c9a6  mov     r14, rax
0x14001c9a9  mov     r9, [rbx+90h]; wchar_t *
0x14001c9b0  test    r9, r9
0x14001c9b3  jz      short loc_14001C9CA
0x14001c9b5  lea     r8, aCallerP; "(caller: %p) "
0x14001c9bc  mov     rdx, rsi; wchar_t *
0x14001c9bf  mov     rcx, rax; this
0x14001c9c2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001c9c7  mov     r14, rax
0x14001c9ca  call    cs:__imp_GetCurrentThreadId
0x14001c9d0  lea     rcx, [rsp+288h+Buffer]
0x14001c9d5  mov     [rsp+288h+var_250], rcx
0x14001c9da  mov     dword ptr [rsp+288h+Arguments], ebp
0x14001c9de  mov     [rsp+288h+nSize], eax
0x14001c9e2  mov     eax, [rbx+44h]
0x14001c9e5  mov     dword ptr [rsp+288h+lpBuffer], eax
0x14001c9e9  mov     r9, rdi; wchar_t *
0x14001c9ec  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14001c9f3  mov     rdx, rsi; wchar_t *
0x14001c9f6  mov     rcx, r14; this
0x14001c9f9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001c9fe  cmp     [rbx+18h], r15
0x14001ca02  jnz     short loc_14001CA14
0x14001ca04  cmp     [rbx+48h], r15
0x14001ca08  jnz     short loc_14001CA14
0x14001ca0a  cmp     [rbx+30h], r15
0x14001ca0e  jz      loc_14001CAA4
0x14001ca14  lea     r8, asc_140076A98; "    "
0x14001ca1b  mov     rdx, rsi; wchar_t *
0x14001ca1e  mov     rcx, rax; this
0x14001ca21  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001ca26  mov     r9, [rbx+18h]; wchar_t *
0x14001ca2a  test    r9, r9
0x14001ca2d  jz      short loc_14001CA41
0x14001ca2f  lea     r8, aMsgWs; "Msg:[%ws] "
0x14001ca36  mov     rdx, rsi; wchar_t *
0x14001ca39  mov     rcx, rax; this
0x14001ca3c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001ca41  mov     r9, [rbx+48h]; wchar_t *
0x14001ca45  test    r9, r9
0x14001ca48  jz      short loc_14001CA5C
0x14001ca4a  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14001ca51  mov     rdx, rsi; wchar_t *
0x14001ca54  mov     rcx, rax; this
0x14001ca57  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001ca5c  mov     rcx, [rbx+28h]
0x14001ca60  mov     r9, [rbx+30h]; wchar_t *
0x14001ca64  mov     rdx, rsi; wchar_t *
0x14001ca67  test    rcx, rcx
0x14001ca6a  jz      short loc_14001CA82
0x14001ca6c  mov     [rsp+288h+lpBuffer], rcx
0x14001ca71  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x14001ca78  mov     rcx, rax; this
0x14001ca7b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001ca80  jmp     short loc_14001CAA4
0x14001ca82  mov     rcx, rax; this
0x14001ca85  test    r9, r9
0x14001ca88  jz      short loc_14001CA98
0x14001ca8a  lea     r8, aHs; "[%hs]\n"
0x14001ca91  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001ca96  jmp     short loc_14001CAA4
0x14001ca98  lea     r8, asc_140076B10; "\n"
0x14001ca9f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001caa4  xor     eax, eax
0x14001caa6  mov     rcx, [rsp+288h+var_38]
0x14001caae  xor     rcx, rsp; StackCookie
0x14001cab1  call    __security_check_cookie
0x14001cab6  mov     rbx, [rsp+288h+arg_18]
0x14001cabe  add     rsp, 260h
0x14001cac5  pop     r15
0x14001cac7  pop     r14
0x14001cac9  pop     rdi
0x14001caca  pop     rsi
0x14001cacb  pop     rbp
0x14001cacc  retn
```
