# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400037e4`
- end: `0x140003a9a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140004850`
- `0x140004e28`
- `0x1400080f4`
- `0x14000835c`

## callees

- `0x1400023d0`
- `0x140002fcc`
- `0x1400037e4`
- `0x140003d90`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003997`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003997`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003916`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003916`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

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
          v7 = (const char *)&byte_140013F31;
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
                          Buffer);
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
0x1400037e4  mov     [rsp+arg_18], rbx
0x1400037e9  push    rbp
0x1400037ea  push    rsi
0x1400037eb  push    rdi
0x1400037ec  push    r14
0x1400037ee  push    r15
0x1400037f0  sub     rsp, 250h
0x1400037f7  mov     rax, cs:__security_cookie
0x1400037fe  xor     rax, rsp
0x140003801  mov     [rsp+278h+var_38], rax
0x140003809  mov     rbx, r8
0x14000380c  mov     rsi, rdx
0x14000380f  mov     r14, rcx
0x140003812  xor     r15d, r15d
0x140003815  test    rdx, rdx
0x140003818  jz      loc_140003A71
0x14000381e  test    rcx, rcx
0x140003821  jz      loc_140003A71
0x140003827  mov     [rcx], r15w
0x14000382b  mov     rax, cs:g_pfnResultLoggingCallback
0x140003832  test    rax, rax
0x140003835  jz      short loc_140003858
0x140003837  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000383e  jz      short loc_140003858
0x140003840  mov     r8, rdx
0x140003843  mov     rdx, rcx
0x140003846  mov     rcx, rbx
0x140003849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000384e  cmp     [r14], r15w
0x140003852  jnz     loc_140003A71
0x140003858  mov     ecx, [rbx]
0x14000385a  mov     bpl, 8
0x14000385d  test    ecx, ecx
0x14000385f  jz      short loc_1400038AA
0x140003861  sub     ecx, 1
0x140003864  jz      short loc_140003892
0x140003866  sub     ecx, 1
0x140003869  jz      short loc_140003882
0x14000386b  cmp     ecx, 1
0x14000386e  jz      short loc_140003879
0x140003870  lea     rdi, byte_140013F31
0x140003877  jmp     short loc_1400038B1
0x140003879  lea     rdi, aFailfast; "FailFast"
0x140003880  jmp     short loc_1400038B1
0x140003882  lea     rax, aLoghr; "LogHr"
0x140003889  lea     rdi, aLognt; "LogNt"
0x140003890  jmp     short loc_1400038A0
0x140003892  lea     rax, aReturnhr; "ReturnHr"
0x140003899  lea     rdi, aReturnnt; "ReturnNt"
0x1400038a0  test    [rbx+4], bpl
0x1400038a4  cmovz   rdi, rax
0x1400038a8  jmp     short loc_1400038B1
0x1400038aa  lea     rdi, aException; "Exception"
0x1400038b1  xor     edx, edx; Val
0x1400038b3  mov     r8d, 200h; Size
0x1400038b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400038be  call    memset_0
0x1400038c3  test    [rbx+4], bpl
0x1400038c7  jz      short loc_1400038EC
0x1400038c9  mov     ebp, [rbx+0Ch]
0x1400038cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1400038d3  test    rax, rax
0x1400038d6  jz      short loc_14000391C
0x1400038d8  mov     r8d, 100h
0x1400038de  lea     rdx, [rsp+278h+Buffer]
0x1400038e3  mov     ecx, ebp
0x1400038e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038ea  jmp     short loc_14000391C
0x1400038ec  mov     ebp, [rbx+8]
0x1400038ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1400038f4  mov     [rsp+278h+nSize], 100h; nSize
0x1400038fc  lea     rax, [rsp+278h+Buffer]
0x140003901  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003906  mov     r9d, 400h; dwLanguageId
0x14000390c  mov     r8d, ebp; dwMessageId
0x14000390f  xor     edx, edx; lpSource
0x140003911  mov     ecx, 1200h; dwFlags
0x140003916  call    cs:__imp_FormatMessageW
0x14000391c  lea     rsi, [r14+rsi*2]
0x140003920  mov     r9, [rbx+38h]; wchar_t *
0x140003924  mov     rax, [rbx+88h]
0x14000392b  mov     rcx, [rbx+80h]
0x140003932  mov     rdx, rsi; wchar_t *
0x140003935  test    r9, r9
0x140003938  jz      short loc_14000395C
0x14000393a  mov     [rsp+278h+Arguments], rax
0x14000393f  mov     qword ptr [rsp+278h+nSize], rcx
0x140003944  mov     eax, [rbx+40h]
0x140003947  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000394b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140003952  mov     rcx, r14; this
0x140003955  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000395a  jmp     short loc_140003973
0x14000395c  mov     [rsp+278h+lpBuffer], rax
0x140003961  mov     r9, rcx; wchar_t *
0x140003964  lea     r8, aHsP; "%hs!%p: "
0x14000396b  mov     rcx, r14; this
0x14000396e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140003973  mov     r14, rax
0x140003976  mov     r9, [rbx+90h]; wchar_t *
0x14000397d  test    r9, r9
0x140003980  jz      short loc_140003997
0x140003982  lea     r8, aCallerP; "(caller: %p) "
0x140003989  mov     rdx, rsi; wchar_t *
0x14000398c  mov     rcx, rax; this
0x14000398f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140003994  mov     r14, rax
0x140003997  call    cs:__imp_GetCurrentThreadId
0x14000399d  lea     rcx, [rsp+278h+Buffer]
0x1400039a2  mov     [rsp+278h+var_240], rcx
0x1400039a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400039ab  mov     [rsp+278h+nSize], eax
0x1400039af  mov     eax, [rbx+44h]
0x1400039b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400039b6  mov     r9, rdi; wchar_t *
0x1400039b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400039c0  mov     rdx, rsi; wchar_t *
0x1400039c3  mov     rcx, r14; this
0x1400039c6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400039cb  cmp     [rbx+18h], r15
0x1400039cf  jnz     short loc_1400039E1
0x1400039d1  cmp     [rbx+48h], r15
0x1400039d5  jnz     short loc_1400039E1
0x1400039d7  cmp     [rbx+30h], r15
0x1400039db  jz      loc_140003A71
0x1400039e1  lea     r8, asc_140014038; "    "
0x1400039e8  mov     rdx, rsi; wchar_t *
0x1400039eb  mov     rcx, rax; this
0x1400039ee  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400039f3  mov     r9, [rbx+18h]; wchar_t *
0x1400039f7  test    r9, r9
0x1400039fa  jz      short loc_140003A0E
0x1400039fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x140003a03  mov     rdx, rsi; wchar_t *
0x140003a06  mov     rcx, rax; this
0x140003a09  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140003a0e  mov     r9, [rbx+48h]; wchar_t *
0x140003a12  test    r9, r9
0x140003a15  jz      short loc_140003A29
0x140003a17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140003a1e  mov     rdx, rsi; wchar_t *
0x140003a21  mov     rcx, rax; this
0x140003a24  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140003a29  mov     rcx, [rbx+28h]
0x140003a2d  mov     r9, [rbx+30h]; wchar_t *
0x140003a31  mov     rdx, rsi; wchar_t *
0x140003a34  test    rcx, rcx
0x140003a37  jz      short loc_140003A4F
0x140003a39  mov     [rsp+278h+lpBuffer], rcx
0x140003a3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003a45  mov     rcx, rax; this
0x140003a48  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140003a4d  jmp     short loc_140003A71
0x140003a4f  mov     rcx, rax; this
0x140003a52  test    r9, r9
0x140003a55  jz      short loc_140003A65
0x140003a57  lea     r8, aHs; "[%hs]\n"
0x140003a5e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140003a63  jmp     short loc_140003A71
0x140003a65  lea     r8, asc_1400140B0; "\n"
0x140003a6c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140003a71  xor     eax, eax
0x140003a73  mov     rcx, [rsp+278h+var_38]
0x140003a7b  xor     rcx, rsp; StackCookie
0x140003a7e  call    __security_check_cookie
0x140003a83  mov     rbx, [rsp+278h+arg_18]
0x140003a8b  add     rsp, 250h
0x140003a92  pop     r15
0x140003a94  pop     r14
0x140003a96  pop     rdi
0x140003a97  pop     rsi
0x140003a98  pop     rbp
0x140003a99  retn
```
