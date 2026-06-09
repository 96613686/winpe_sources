# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003824`
- end: `0x180003ada`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800041bc`
- `0x18000462c`
- `0x1800057e0`

## callees

- `0x180001620`
- `0x180001fd0`
- `0x180003824`
- `0x1800044b8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003956`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003956`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  wil::details *v15; // r14
  const unsigned __int16 *v16; // r9
  wil::details *v17; // rax
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
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
          v7 = (const char *)&qword_180011F20;
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
  v10 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
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
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x180003824  mov     [rsp+arg_18], rbx
0x180003829  push    rbp
0x18000382a  push    rsi
0x18000382b  push    rdi
0x18000382c  push    r14
0x18000382e  push    r15
0x180003830  sub     rsp, 250h
0x180003837  mov     rax, cs:__security_cookie
0x18000383e  xor     rax, rsp
0x180003841  mov     [rsp+278h+var_38], rax
0x180003849  mov     rbx, r8
0x18000384c  mov     rsi, rdx
0x18000384f  mov     r14, rcx
0x180003852  xor     r15d, r15d
0x180003855  test    rdx, rdx
0x180003858  jz      loc_180003AB1
0x18000385e  test    rcx, rcx
0x180003861  jz      loc_180003AB1
0x180003867  mov     [rcx], r15w
0x18000386b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003872  test    rax, rax
0x180003875  jz      short loc_180003898
0x180003877  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000387e  jz      short loc_180003898
0x180003880  mov     r8, rdx
0x180003883  mov     rdx, rcx
0x180003886  mov     rcx, rbx
0x180003889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388e  cmp     [r14], r15w
0x180003892  jnz     loc_180003AB1
0x180003898  mov     ecx, [rbx]
0x18000389a  mov     bpl, 8
0x18000389d  test    ecx, ecx
0x18000389f  jz      short loc_1800038EA
0x1800038a1  sub     ecx, 1
0x1800038a4  jz      short loc_1800038D2
0x1800038a6  sub     ecx, 1
0x1800038a9  jz      short loc_1800038C2
0x1800038ab  cmp     ecx, 1
0x1800038ae  jz      short loc_1800038B9
0x1800038b0  lea     rdi, qword_180011F20
0x1800038b7  jmp     short loc_1800038F1
0x1800038b9  lea     rdi, aFailfast; "FailFast"
0x1800038c0  jmp     short loc_1800038F1
0x1800038c2  lea     rax, aLoghr; "LogHr"
0x1800038c9  lea     rdi, aLognt; "LogNt"
0x1800038d0  jmp     short loc_1800038E0
0x1800038d2  lea     rax, aReturnhr; "ReturnHr"
0x1800038d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800038e0  test    [rbx+4], bpl
0x1800038e4  cmovz   rdi, rax
0x1800038e8  jmp     short loc_1800038F1
0x1800038ea  lea     rdi, aException; "Exception"
0x1800038f1  xor     edx, edx; Val
0x1800038f3  mov     r8d, 200h; Size
0x1800038f9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800038fe  call    memset_0
0x180003903  test    [rbx+4], bpl
0x180003907  jz      short loc_18000392C
0x180003909  mov     ebp, [rbx+0Ch]
0x18000390c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003913  test    rax, rax
0x180003916  jz      short loc_18000395C
0x180003918  mov     r8d, 100h
0x18000391e  lea     rdx, [rsp+278h+Buffer]
0x180003923  mov     ecx, ebp
0x180003925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000392a  jmp     short loc_18000395C
0x18000392c  mov     ebp, [rbx+8]
0x18000392f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003934  mov     [rsp+278h+nSize], 100h; nSize
0x18000393c  lea     rax, [rsp+278h+Buffer]
0x180003941  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003946  mov     r9d, 400h; dwLanguageId
0x18000394c  mov     r8d, ebp; dwMessageId
0x18000394f  xor     edx, edx; lpSource
0x180003951  mov     ecx, 1200h; dwFlags
0x180003956  call    cs:__imp_FormatMessageW
0x18000395c  lea     rsi, [r14+rsi*2]
0x180003960  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003964  mov     rax, [rbx+88h]
0x18000396b  mov     rcx, [rbx+80h]
0x180003972  mov     rdx, rsi; unsigned __int16 *
0x180003975  test    r9, r9
0x180003978  jz      short loc_18000399C
0x18000397a  mov     [rsp+278h+Arguments], rax
0x18000397f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003984  mov     eax, [rbx+40h]
0x180003987  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000398b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003992  mov     rcx, r14; this
0x180003995  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000399a  jmp     short loc_1800039B3
0x18000399c  mov     [rsp+278h+lpBuffer], rax
0x1800039a1  mov     r9, rcx; unsigned __int16 *
0x1800039a4  lea     r8, aHsP; "%hs!%p: "
0x1800039ab  mov     rcx, r14; this
0x1800039ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800039b3  mov     r14, rax
0x1800039b6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800039bd  test    r9, r9
0x1800039c0  jz      short loc_1800039D7
0x1800039c2  lea     r8, aCallerP; "(caller: %p) "
0x1800039c9  mov     rdx, rsi; unsigned __int16 *
0x1800039cc  mov     rcx, rax; this
0x1800039cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800039d4  mov     r14, rax
0x1800039d7  call    cs:__imp_GetCurrentThreadId
0x1800039dd  lea     rcx, [rsp+278h+Buffer]
0x1800039e2  mov     [rsp+278h+var_240], rcx
0x1800039e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800039eb  mov     [rsp+278h+nSize], eax
0x1800039ef  mov     eax, [rbx+44h]
0x1800039f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800039f6  mov     r9, rdi; unsigned __int16 *
0x1800039f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003a00  mov     rdx, rsi; unsigned __int16 *
0x180003a03  mov     rcx, r14; this
0x180003a06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a0b  cmp     [rbx+18h], r15
0x180003a0f  jnz     short loc_180003A21
0x180003a11  cmp     [rbx+48h], r15
0x180003a15  jnz     short loc_180003A21
0x180003a17  cmp     [rbx+30h], r15
0x180003a1b  jz      loc_180003AB1
0x180003a21  lea     r8, asc_180012028; "    "
0x180003a28  mov     rdx, rsi; unsigned __int16 *
0x180003a2b  mov     rcx, rax; this
0x180003a2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a33  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003a37  test    r9, r9
0x180003a3a  jz      short loc_180003A4E
0x180003a3c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003a43  mov     rdx, rsi; unsigned __int16 *
0x180003a46  mov     rcx, rax; this
0x180003a49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a4e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003a52  test    r9, r9
0x180003a55  jz      short loc_180003A69
0x180003a57  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003a5e  mov     rdx, rsi; unsigned __int16 *
0x180003a61  mov     rcx, rax; this
0x180003a64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a69  mov     rcx, [rbx+28h]
0x180003a6d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003a71  mov     rdx, rsi; unsigned __int16 *
0x180003a74  test    rcx, rcx
0x180003a77  jz      short loc_180003A8F
0x180003a79  mov     [rsp+278h+lpBuffer], rcx
0x180003a7e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003a85  mov     rcx, rax; this
0x180003a88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a8d  jmp     short loc_180003AB1
0x180003a8f  mov     rcx, rax; this
0x180003a92  test    r9, r9
0x180003a95  jz      short loc_180003AA5
0x180003a97  lea     r8, aHs; "[%hs]\n"
0x180003a9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003aa3  jmp     short loc_180003AB1
0x180003aa5  lea     r8, asc_1800120A0; "\n"
0x180003aac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ab1  xor     eax, eax
0x180003ab3  mov     rcx, [rsp+278h+var_38]
0x180003abb  xor     rcx, rsp; StackCookie
0x180003abe  call    __security_check_cookie
0x180003ac3  mov     rbx, [rsp+278h+arg_18]
0x180003acb  add     rsp, 250h
0x180003ad2  pop     r15
0x180003ad4  pop     r14
0x180003ad6  pop     rdi
0x180003ad7  pop     rsi
0x180003ad8  pop     rbp
0x180003ad9  retn
```
