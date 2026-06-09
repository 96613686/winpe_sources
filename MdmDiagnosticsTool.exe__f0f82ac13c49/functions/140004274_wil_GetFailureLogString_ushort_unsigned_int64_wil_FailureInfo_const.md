# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004274`
- end: `0x14000452a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140002840`
- `0x1400052e0`
- `0x1400057a8`
- `0x140007fa0`

## callees

- `0x140004274`
- `0x1400055e0`
- `0x140009696`
- `0x1400096d0`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004427`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004427`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400043a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400043a6`

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
          v7 = (const char *)&dword_14000CC44;
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
0x140004274  mov     [rsp+arg_18], rbx
0x140004279  push    rbp
0x14000427a  push    rsi
0x14000427b  push    rdi
0x14000427c  push    r14
0x14000427e  push    r15
0x140004280  sub     rsp, 250h
0x140004287  mov     rax, cs:__security_cookie
0x14000428e  xor     rax, rsp
0x140004291  mov     [rsp+278h+var_38], rax
0x140004299  mov     rbx, r8
0x14000429c  mov     rsi, rdx
0x14000429f  mov     r14, rcx
0x1400042a2  xor     r15d, r15d
0x1400042a5  test    rdx, rdx
0x1400042a8  jz      loc_140004501
0x1400042ae  test    rcx, rcx
0x1400042b1  jz      loc_140004501
0x1400042b7  mov     [rcx], r15w
0x1400042bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1400042c2  test    rax, rax
0x1400042c5  jz      short loc_1400042E8
0x1400042c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400042ce  jz      short loc_1400042E8
0x1400042d0  mov     r8, rdx
0x1400042d3  mov     rdx, rcx
0x1400042d6  mov     rcx, rbx
0x1400042d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042de  cmp     [r14], r15w
0x1400042e2  jnz     loc_140004501
0x1400042e8  mov     ecx, [rbx]
0x1400042ea  mov     bpl, 8
0x1400042ed  test    ecx, ecx
0x1400042ef  jz      short loc_14000433A
0x1400042f1  sub     ecx, 1
0x1400042f4  jz      short loc_140004322
0x1400042f6  sub     ecx, 1
0x1400042f9  jz      short loc_140004312
0x1400042fb  cmp     ecx, 1
0x1400042fe  jz      short loc_140004309
0x140004300  lea     rdi, dword_14000CC44
0x140004307  jmp     short loc_140004341
0x140004309  lea     rdi, aFailfast; "FailFast"
0x140004310  jmp     short loc_140004341
0x140004312  lea     rax, aLoghr; "LogHr"
0x140004319  lea     rdi, aLognt; "LogNt"
0x140004320  jmp     short loc_140004330
0x140004322  lea     rax, aReturnhr; "ReturnHr"
0x140004329  lea     rdi, aReturnnt; "ReturnNt"
0x140004330  test    [rbx+4], bpl
0x140004334  cmovz   rdi, rax
0x140004338  jmp     short loc_140004341
0x14000433a  lea     rdi, aException; "Exception"
0x140004341  xor     edx, edx; Val
0x140004343  mov     r8d, 200h; Size
0x140004349  lea     rcx, [rsp+278h+Buffer]; void *
0x14000434e  call    memset_0
0x140004353  test    [rbx+4], bpl
0x140004357  jz      short loc_14000437C
0x140004359  mov     ebp, [rbx+0Ch]
0x14000435c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004363  test    rax, rax
0x140004366  jz      short loc_1400043AC
0x140004368  mov     r8d, 100h
0x14000436e  lea     rdx, [rsp+278h+Buffer]
0x140004373  mov     ecx, ebp
0x140004375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000437a  jmp     short loc_1400043AC
0x14000437c  mov     ebp, [rbx+8]
0x14000437f  mov     [rsp+278h+Arguments], r15; Arguments
0x140004384  mov     [rsp+278h+nSize], 100h; nSize
0x14000438c  lea     rax, [rsp+278h+Buffer]
0x140004391  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004396  mov     r9d, 400h; dwLanguageId
0x14000439c  mov     r8d, ebp; dwMessageId
0x14000439f  xor     edx, edx; lpSource
0x1400043a1  mov     ecx, 1200h; dwFlags
0x1400043a6  call    cs:__imp_FormatMessageW
0x1400043ac  lea     rsi, [r14+rsi*2]
0x1400043b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400043b4  mov     rax, [rbx+88h]
0x1400043bb  mov     rcx, [rbx+80h]
0x1400043c2  mov     rdx, rsi; unsigned __int16 *
0x1400043c5  test    r9, r9
0x1400043c8  jz      short loc_1400043EC
0x1400043ca  mov     [rsp+278h+Arguments], rax
0x1400043cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1400043d4  mov     eax, [rbx+40h]
0x1400043d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400043db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400043e2  mov     rcx, r14; this
0x1400043e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400043ea  jmp     short loc_140004403
0x1400043ec  mov     [rsp+278h+lpBuffer], rax
0x1400043f1  mov     r9, rcx; unsigned __int16 *
0x1400043f4  lea     r8, aHsP; "%hs!%p: "
0x1400043fb  mov     rcx, r14; this
0x1400043fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004403  mov     r14, rax
0x140004406  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000440d  test    r9, r9
0x140004410  jz      short loc_140004427
0x140004412  lea     r8, aCallerP; "(caller: %p) "
0x140004419  mov     rdx, rsi; unsigned __int16 *
0x14000441c  mov     rcx, rax; this
0x14000441f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004424  mov     r14, rax
0x140004427  call    cs:__imp_GetCurrentThreadId
0x14000442d  lea     rcx, [rsp+278h+Buffer]
0x140004432  mov     [rsp+278h+var_240], rcx
0x140004437  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000443b  mov     [rsp+278h+nSize], eax
0x14000443f  mov     eax, [rbx+44h]
0x140004442  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004446  mov     r9, rdi; unsigned __int16 *
0x140004449  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004450  mov     rdx, rsi; unsigned __int16 *
0x140004453  mov     rcx, r14; this
0x140004456  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000445b  cmp     [rbx+18h], r15
0x14000445f  jnz     short loc_140004471
0x140004461  cmp     [rbx+48h], r15
0x140004465  jnz     short loc_140004471
0x140004467  cmp     [rbx+30h], r15
0x14000446b  jz      loc_140004501
0x140004471  lea     r8, asc_14000CD38; "    "
0x140004478  mov     rdx, rsi; unsigned __int16 *
0x14000447b  mov     rcx, rax; this
0x14000447e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004483  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004487  test    r9, r9
0x14000448a  jz      short loc_14000449E
0x14000448c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004493  mov     rdx, rsi; unsigned __int16 *
0x140004496  mov     rcx, rax; this
0x140004499  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000449e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400044a2  test    r9, r9
0x1400044a5  jz      short loc_1400044B9
0x1400044a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400044ae  mov     rdx, rsi; unsigned __int16 *
0x1400044b1  mov     rcx, rax; this
0x1400044b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044b9  mov     rcx, [rbx+28h]
0x1400044bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400044c1  mov     rdx, rsi; unsigned __int16 *
0x1400044c4  test    rcx, rcx
0x1400044c7  jz      short loc_1400044DF
0x1400044c9  mov     [rsp+278h+lpBuffer], rcx
0x1400044ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400044d5  mov     rcx, rax; this
0x1400044d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044dd  jmp     short loc_140004501
0x1400044df  mov     rcx, rax; this
0x1400044e2  test    r9, r9
0x1400044e5  jz      short loc_1400044F5
0x1400044e7  lea     r8, aHs; "[%hs]\n"
0x1400044ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044f3  jmp     short loc_140004501
0x1400044f5  lea     r8, Format; "\n"
0x1400044fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004501  xor     eax, eax
0x140004503  mov     rcx, [rsp+278h+var_38]
0x14000450b  xor     rcx, rsp; StackCookie
0x14000450e  call    __security_check_cookie
0x140004513  mov     rbx, [rsp+278h+arg_18]
0x14000451b  add     rsp, 250h
0x140004522  pop     r15
0x140004524  pop     r14
0x140004526  pop     rdi
0x140004527  pop     rsi
0x140004528  pop     rbp
0x140004529  retn
```
