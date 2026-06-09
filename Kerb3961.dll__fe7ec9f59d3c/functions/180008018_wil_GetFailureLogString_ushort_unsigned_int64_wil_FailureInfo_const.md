# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008018`
- end: `0x1800082ce`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004350`
- `0x180008ca0`
- `0x18000fe88`

## callees

- `0x180001d40`
- `0x180002928`
- `0x180008018`
- `0x180008fa0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081cb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000814a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000814a`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&word_1800205DA;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008018  mov     [rsp+arg_18], rbx
0x18000801d  push    rbp
0x18000801e  push    rsi
0x18000801f  push    rdi
0x180008020  push    r14
0x180008022  push    r15
0x180008024  sub     rsp, 250h
0x18000802b  mov     rax, cs:__security_cookie
0x180008032  xor     rax, rsp
0x180008035  mov     [rsp+278h+var_38], rax
0x18000803d  xor     r15d, r15d
0x180008040  mov     rbx, r8
0x180008043  mov     rsi, rdx
0x180008046  mov     r14, rcx
0x180008049  test    rdx, rdx
0x18000804c  jz      loc_1800082A5
0x180008052  test    rcx, rcx
0x180008055  jz      loc_1800082A5
0x18000805b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008062  mov     [rcx], r15w
0x180008066  test    rax, rax
0x180008069  jz      short loc_18000808C
0x18000806b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008072  jz      short loc_18000808C
0x180008074  mov     r8, rdx
0x180008077  mov     rdx, rcx
0x18000807a  mov     rcx, rbx
0x18000807d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008082  cmp     [r14], r15w
0x180008086  jnz     loc_1800082A5
0x18000808c  mov     ecx, [rbx]
0x18000808e  mov     bpl, 8
0x180008091  test    ecx, ecx
0x180008093  jz      short loc_1800080DE
0x180008095  sub     ecx, 1
0x180008098  jz      short loc_1800080C6
0x18000809a  sub     ecx, 1
0x18000809d  jz      short loc_1800080B6
0x18000809f  cmp     ecx, 1
0x1800080a2  jz      short loc_1800080AD
0x1800080a4  lea     rdi, word_1800205DA
0x1800080ab  jmp     short loc_1800080E5
0x1800080ad  lea     rdi, aFailfast; "FailFast"
0x1800080b4  jmp     short loc_1800080E5
0x1800080b6  lea     rax, aLoghr; "LogHr"
0x1800080bd  lea     rdi, aLognt; "LogNt"
0x1800080c4  jmp     short loc_1800080D4
0x1800080c6  lea     rax, aReturnhr; "ReturnHr"
0x1800080cd  lea     rdi, aReturnnt; "ReturnNt"
0x1800080d4  test    [rbx+4], bpl
0x1800080d8  cmovz   rdi, rax
0x1800080dc  jmp     short loc_1800080E5
0x1800080de  lea     rdi, aException; "Exception"
0x1800080e5  xor     edx, edx; Val
0x1800080e7  lea     rcx, [rsp+278h+Buffer]; void *
0x1800080ec  mov     r8d, 200h; Size
0x1800080f2  call    memset_0
0x1800080f7  test    [rbx+4], bpl
0x1800080fb  jz      short loc_180008120
0x1800080fd  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008104  mov     ebp, [rbx+0Ch]
0x180008107  test    rax, rax
0x18000810a  jz      short loc_180008150
0x18000810c  mov     r8d, 100h
0x180008112  lea     rdx, [rsp+278h+Buffer]
0x180008117  mov     ecx, ebp
0x180008119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000811e  jmp     short loc_180008150
0x180008120  mov     ebp, [rbx+8]
0x180008123  lea     rax, [rsp+278h+Buffer]
0x180008128  mov     [rsp+278h+Arguments], r15; Arguments
0x18000812d  mov     r8d, ebp; dwMessageId
0x180008130  mov     [rsp+278h+nSize], 100h; nSize
0x180008138  mov     r9d, 400h; dwLanguageId
0x18000813e  xor     edx, edx; lpSource
0x180008140  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180008145  mov     ecx, 1200h; dwFlags
0x18000814a  call    cs:__imp_FormatMessageW
0x180008150  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008154  lea     rsi, [r14+rsi*2]
0x180008158  mov     rax, [rbx+88h]
0x18000815f  mov     rdx, rsi; unsigned __int16 *
0x180008162  mov     rcx, [rbx+80h]
0x180008169  test    r9, r9
0x18000816c  jz      short loc_180008190
0x18000816e  mov     [rsp+278h+Arguments], rax
0x180008173  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000817a  mov     eax, [rbx+40h]
0x18000817d  mov     qword ptr [rsp+278h+nSize], rcx
0x180008182  mov     rcx, r14; this
0x180008185  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008189  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000818e  jmp     short loc_1800081A7
0x180008190  mov     r9, rcx; unsigned __int16 *
0x180008193  mov     [rsp+278h+lpBuffer], rax
0x180008198  mov     rcx, r14; this
0x18000819b  lea     r8, aHsP; "%hs!%p: "
0x1800081a2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800081a7  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800081ae  mov     r14, rax
0x1800081b1  test    r9, r9
0x1800081b4  jz      short loc_1800081CB
0x1800081b6  lea     r8, aCallerP; "(caller: %p) "
0x1800081bd  mov     rdx, rsi; unsigned __int16 *
0x1800081c0  mov     rcx, rax; this
0x1800081c3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800081c8  mov     r14, rax
0x1800081cb  call    cs:__imp_GetCurrentThreadId
0x1800081d1  lea     rcx, [rsp+278h+Buffer]
0x1800081d6  mov     r9, rdi; unsigned __int16 *
0x1800081d9  mov     [rsp+278h+var_240], rcx
0x1800081de  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800081e5  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800081e9  mov     rdx, rsi; unsigned __int16 *
0x1800081ec  mov     [rsp+278h+nSize], eax
0x1800081f0  mov     rcx, r14; this
0x1800081f3  mov     eax, [rbx+44h]
0x1800081f6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800081fa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800081ff  cmp     [rbx+18h], r15
0x180008203  jnz     short loc_180008215
0x180008205  cmp     [rbx+48h], r15
0x180008209  jnz     short loc_180008215
0x18000820b  cmp     [rbx+30h], r15
0x18000820f  jz      loc_1800082A5
0x180008215  lea     r8, asc_180021918; "    "
0x18000821c  mov     rdx, rsi; unsigned __int16 *
0x18000821f  mov     rcx, rax; this
0x180008222  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008227  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000822b  test    r9, r9
0x18000822e  jz      short loc_180008242
0x180008230  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008237  mov     rdx, rsi; unsigned __int16 *
0x18000823a  mov     rcx, rax; this
0x18000823d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008242  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008246  test    r9, r9
0x180008249  jz      short loc_18000825D
0x18000824b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180008252  mov     rdx, rsi; unsigned __int16 *
0x180008255  mov     rcx, rax; this
0x180008258  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000825d  mov     rcx, [rbx+28h]
0x180008261  mov     rdx, rsi; unsigned __int16 *
0x180008264  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008268  test    rcx, rcx
0x18000826b  jz      short loc_180008283
0x18000826d  mov     [rsp+278h+lpBuffer], rcx
0x180008272  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008279  mov     rcx, rax; this
0x18000827c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008281  jmp     short loc_1800082A5
0x180008283  mov     rcx, rax; this
0x180008286  test    r9, r9
0x180008289  jz      short loc_180008299
0x18000828b  lea     r8, aHs; "[%hs]\n"
0x180008292  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008297  jmp     short loc_1800082A5
0x180008299  lea     r8, asc_180021990; "\n"
0x1800082a0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800082a5  xor     eax, eax
0x1800082a7  mov     rcx, [rsp+278h+var_38]
0x1800082af  xor     rcx, rsp; StackCookie
0x1800082b2  call    __security_check_cookie
0x1800082b7  mov     rbx, [rsp+278h+arg_18]
0x1800082bf  add     rsp, 250h
0x1800082c6  pop     r15
0x1800082c8  pop     r14
0x1800082ca  pop     rdi
0x1800082cb  pop     rsi
0x1800082cc  pop     rbp
0x1800082cd  retn
```
