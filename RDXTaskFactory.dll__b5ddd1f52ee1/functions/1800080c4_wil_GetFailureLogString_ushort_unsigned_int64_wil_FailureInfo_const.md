# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800080c4`
- end: `0x18000837a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005ea0`
- `0x180008e0c`
- `0x1800094ec`
- `0x18000c790`

## callees

- `0x180003390`
- `0x180003e00`
- `0x1800080c4`
- `0x18000910c`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008277`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800081f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800081f6`

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
          v7 = (const char *)&dword_180057BDC;
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
0x1800080c4  mov     [rsp+arg_18], rbx
0x1800080c9  push    rbp
0x1800080ca  push    rsi
0x1800080cb  push    rdi
0x1800080cc  push    r14
0x1800080ce  push    r15
0x1800080d0  sub     rsp, 250h
0x1800080d7  mov     rax, cs:__security_cookie
0x1800080de  xor     rax, rsp
0x1800080e1  mov     [rsp+278h+var_38], rax
0x1800080e9  mov     rbx, r8
0x1800080ec  mov     rsi, rdx
0x1800080ef  mov     r14, rcx
0x1800080f2  xor     r15d, r15d
0x1800080f5  test    rdx, rdx
0x1800080f8  jz      loc_180008351
0x1800080fe  test    rcx, rcx
0x180008101  jz      loc_180008351
0x180008107  mov     [rcx], r15w
0x18000810b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008112  test    rax, rax
0x180008115  jz      short loc_180008138
0x180008117  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000811e  jz      short loc_180008138
0x180008120  mov     r8, rdx
0x180008123  mov     rdx, rcx
0x180008126  mov     rcx, rbx
0x180008129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000812e  cmp     [r14], r15w
0x180008132  jnz     loc_180008351
0x180008138  mov     ecx, [rbx]
0x18000813a  mov     bpl, 8
0x18000813d  test    ecx, ecx
0x18000813f  jz      short loc_18000818A
0x180008141  sub     ecx, 1
0x180008144  jz      short loc_180008172
0x180008146  sub     ecx, 1
0x180008149  jz      short loc_180008162
0x18000814b  cmp     ecx, 1
0x18000814e  jz      short loc_180008159
0x180008150  lea     rdi, dword_180057BDC
0x180008157  jmp     short loc_180008191
0x180008159  lea     rdi, aFailfast; "FailFast"
0x180008160  jmp     short loc_180008191
0x180008162  lea     rax, aLoghr; "LogHr"
0x180008169  lea     rdi, aLognt; "LogNt"
0x180008170  jmp     short loc_180008180
0x180008172  lea     rax, aReturnhr; "ReturnHr"
0x180008179  lea     rdi, aReturnnt; "ReturnNt"
0x180008180  test    [rbx+4], bpl
0x180008184  cmovz   rdi, rax
0x180008188  jmp     short loc_180008191
0x18000818a  lea     rdi, aException; "Exception"
0x180008191  xor     edx, edx; Val
0x180008193  mov     r8d, 200h; Size
0x180008199  lea     rcx, [rsp+278h+Buffer]; void *
0x18000819e  call    memset_0
0x1800081a3  test    [rbx+4], bpl
0x1800081a7  jz      short loc_1800081CC
0x1800081a9  mov     ebp, [rbx+0Ch]
0x1800081ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800081b3  test    rax, rax
0x1800081b6  jz      short loc_1800081FC
0x1800081b8  mov     r8d, 100h
0x1800081be  lea     rdx, [rsp+278h+Buffer]
0x1800081c3  mov     ecx, ebp
0x1800081c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ca  jmp     short loc_1800081FC
0x1800081cc  mov     ebp, [rbx+8]
0x1800081cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800081d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800081dc  lea     rax, [rsp+278h+Buffer]
0x1800081e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800081e6  mov     r9d, 400h; dwLanguageId
0x1800081ec  mov     r8d, ebp; dwMessageId
0x1800081ef  xor     edx, edx; lpSource
0x1800081f1  mov     ecx, 1200h; dwFlags
0x1800081f6  call    cs:__imp_FormatMessageW
0x1800081fc  lea     rsi, [r14+rsi*2]
0x180008200  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008204  mov     rax, [rbx+88h]
0x18000820b  mov     rcx, [rbx+80h]
0x180008212  mov     rdx, rsi; unsigned __int16 *
0x180008215  test    r9, r9
0x180008218  jz      short loc_18000823C
0x18000821a  mov     [rsp+278h+Arguments], rax
0x18000821f  mov     qword ptr [rsp+278h+nSize], rcx
0x180008224  mov     eax, [rbx+40h]
0x180008227  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000822b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008232  mov     rcx, r14; this
0x180008235  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000823a  jmp     short loc_180008253
0x18000823c  mov     [rsp+278h+lpBuffer], rax
0x180008241  mov     r9, rcx; unsigned __int16 *
0x180008244  lea     r8, aHsP; "%hs!%p: "
0x18000824b  mov     rcx, r14; this
0x18000824e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008253  mov     r14, rax
0x180008256  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000825d  test    r9, r9
0x180008260  jz      short loc_180008277
0x180008262  lea     r8, aCallerP; "(caller: %p) "
0x180008269  mov     rdx, rsi; unsigned __int16 *
0x18000826c  mov     rcx, rax; this
0x18000826f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008274  mov     r14, rax
0x180008277  call    cs:__imp_GetCurrentThreadId
0x18000827d  lea     rcx, [rsp+278h+Buffer]
0x180008282  mov     [rsp+278h+var_240], rcx
0x180008287  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000828b  mov     [rsp+278h+nSize], eax
0x18000828f  mov     eax, [rbx+44h]
0x180008292  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008296  mov     r9, rdi; unsigned __int16 *
0x180008299  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800082a0  mov     rdx, rsi; unsigned __int16 *
0x1800082a3  mov     rcx, r14; this
0x1800082a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800082ab  cmp     [rbx+18h], r15
0x1800082af  jnz     short loc_1800082C1
0x1800082b1  cmp     [rbx+48h], r15
0x1800082b5  jnz     short loc_1800082C1
0x1800082b7  cmp     [rbx+30h], r15
0x1800082bb  jz      loc_180008351
0x1800082c1  lea     r8, asc_180057D50; "    "
0x1800082c8  mov     rdx, rsi; unsigned __int16 *
0x1800082cb  mov     rcx, rax; this
0x1800082ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800082d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800082d7  test    r9, r9
0x1800082da  jz      short loc_1800082EE
0x1800082dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800082e3  mov     rdx, rsi; unsigned __int16 *
0x1800082e6  mov     rcx, rax; this
0x1800082e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800082ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800082f2  test    r9, r9
0x1800082f5  jz      short loc_180008309
0x1800082f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800082fe  mov     rdx, rsi; unsigned __int16 *
0x180008301  mov     rcx, rax; this
0x180008304  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008309  mov     rcx, [rbx+28h]
0x18000830d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008311  mov     rdx, rsi; unsigned __int16 *
0x180008314  test    rcx, rcx
0x180008317  jz      short loc_18000832F
0x180008319  mov     [rsp+278h+lpBuffer], rcx
0x18000831e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008325  mov     rcx, rax; this
0x180008328  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000832d  jmp     short loc_180008351
0x18000832f  mov     rcx, rax; this
0x180008332  test    r9, r9
0x180008335  jz      short loc_180008345
0x180008337  lea     r8, aHs; "[%hs]\n"
0x18000833e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008343  jmp     short loc_180008351
0x180008345  lea     r8, asc_180057DC8; "\n"
0x18000834c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008351  xor     eax, eax
0x180008353  mov     rcx, [rsp+278h+var_38]
0x18000835b  xor     rcx, rsp; StackCookie
0x18000835e  call    __security_check_cookie
0x180008363  mov     rbx, [rsp+278h+arg_18]
0x18000836b  add     rsp, 250h
0x180008372  pop     r15
0x180008374  pop     r14
0x180008376  pop     rdi
0x180008377  pop     rsi
0x180008378  pop     rbp
0x180008379  retn
```
