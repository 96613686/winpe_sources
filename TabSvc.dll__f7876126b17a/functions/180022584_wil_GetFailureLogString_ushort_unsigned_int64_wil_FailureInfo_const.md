# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180022584`
- end: `0x18002283a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180023390`
- `0x180023964`
- `0x18002ace0`

## callees

- `0x18001bbe0`
- `0x18001c684`
- `0x180022584`
- `0x18002368c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022737`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022737`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800226b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800226b6`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&word_1800359BA;
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
0x180022584  mov     [rsp+arg_18], rbx
0x180022589  push    rbp
0x18002258a  push    rsi
0x18002258b  push    rdi
0x18002258c  push    r14
0x18002258e  push    r15
0x180022590  sub     rsp, 250h
0x180022597  mov     rax, cs:__security_cookie
0x18002259e  xor     rax, rsp
0x1800225a1  mov     [rsp+278h+var_38], rax
0x1800225a9  mov     rbx, r8
0x1800225ac  mov     rsi, rdx
0x1800225af  mov     r14, rcx
0x1800225b2  xor     r15d, r15d
0x1800225b5  test    rdx, rdx
0x1800225b8  jz      loc_180022811
0x1800225be  test    rcx, rcx
0x1800225c1  jz      loc_180022811
0x1800225c7  mov     [rcx], r15w
0x1800225cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800225d2  test    rax, rax
0x1800225d5  jz      short loc_1800225F8
0x1800225d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800225de  jz      short loc_1800225F8
0x1800225e0  mov     r8, rdx
0x1800225e3  mov     rdx, rcx
0x1800225e6  mov     rcx, rbx
0x1800225e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225ee  cmp     [r14], r15w
0x1800225f2  jnz     loc_180022811
0x1800225f8  mov     ecx, [rbx]
0x1800225fa  mov     bpl, 8
0x1800225fd  test    ecx, ecx
0x1800225ff  jz      short loc_18002264A
0x180022601  sub     ecx, 1
0x180022604  jz      short loc_180022632
0x180022606  sub     ecx, 1
0x180022609  jz      short loc_180022622
0x18002260b  cmp     ecx, 1
0x18002260e  jz      short loc_180022619
0x180022610  lea     rdi, word_1800359BA
0x180022617  jmp     short loc_180022651
0x180022619  lea     rdi, aFailfast; "FailFast"
0x180022620  jmp     short loc_180022651
0x180022622  lea     rax, aLoghr; "LogHr"
0x180022629  lea     rdi, aLognt; "LogNt"
0x180022630  jmp     short loc_180022640
0x180022632  lea     rax, aReturnhr; "ReturnHr"
0x180022639  lea     rdi, aReturnnt; "ReturnNt"
0x180022640  test    [rbx+4], bpl
0x180022644  cmovz   rdi, rax
0x180022648  jmp     short loc_180022651
0x18002264a  lea     rdi, aException; "Exception"
0x180022651  xor     edx, edx; Val
0x180022653  mov     r8d, 200h; Size
0x180022659  lea     rcx, [rsp+278h+Buffer]; void *
0x18002265e  call    memset_0
0x180022663  test    [rbx+4], bpl
0x180022667  jz      short loc_18002268C
0x180022669  mov     ebp, [rbx+0Ch]
0x18002266c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180022673  test    rax, rax
0x180022676  jz      short loc_1800226BC
0x180022678  mov     r8d, 100h
0x18002267e  lea     rdx, [rsp+278h+Buffer]
0x180022683  mov     ecx, ebp
0x180022685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002268a  jmp     short loc_1800226BC
0x18002268c  mov     ebp, [rbx+8]
0x18002268f  mov     [rsp+278h+Arguments], r15; Arguments
0x180022694  mov     [rsp+278h+nSize], 100h; nSize
0x18002269c  lea     rax, [rsp+278h+Buffer]
0x1800226a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800226a6  mov     r9d, 400h; dwLanguageId
0x1800226ac  mov     r8d, ebp; dwMessageId
0x1800226af  xor     edx, edx; lpSource
0x1800226b1  mov     ecx, 1200h; dwFlags
0x1800226b6  call    cs:__imp_FormatMessageW
0x1800226bc  lea     rsi, [r14+rsi*2]
0x1800226c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800226c4  mov     rax, [rbx+88h]
0x1800226cb  mov     rcx, [rbx+80h]
0x1800226d2  mov     rdx, rsi; unsigned __int16 *
0x1800226d5  test    r9, r9
0x1800226d8  jz      short loc_1800226FC
0x1800226da  mov     [rsp+278h+Arguments], rax
0x1800226df  mov     qword ptr [rsp+278h+nSize], rcx
0x1800226e4  mov     eax, [rbx+40h]
0x1800226e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800226eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800226f2  mov     rcx, r14; this
0x1800226f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800226fa  jmp     short loc_180022713
0x1800226fc  mov     [rsp+278h+lpBuffer], rax
0x180022701  mov     r9, rcx; unsigned __int16 *
0x180022704  lea     r8, aHsP; "%hs!%p: "
0x18002270b  mov     rcx, r14; this
0x18002270e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022713  mov     r14, rax
0x180022716  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002271d  test    r9, r9
0x180022720  jz      short loc_180022737
0x180022722  lea     r8, aCallerP; "(caller: %p) "
0x180022729  mov     rdx, rsi; unsigned __int16 *
0x18002272c  mov     rcx, rax; this
0x18002272f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022734  mov     r14, rax
0x180022737  call    cs:__imp_GetCurrentThreadId
0x18002273d  lea     rcx, [rsp+278h+Buffer]
0x180022742  mov     [rsp+278h+var_240], rcx
0x180022747  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002274b  mov     [rsp+278h+nSize], eax
0x18002274f  mov     eax, [rbx+44h]
0x180022752  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180022756  mov     r9, rdi; unsigned __int16 *
0x180022759  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180022760  mov     rdx, rsi; unsigned __int16 *
0x180022763  mov     rcx, r14; this
0x180022766  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002276b  cmp     [rbx+18h], r15
0x18002276f  jnz     short loc_180022781
0x180022771  cmp     [rbx+48h], r15
0x180022775  jnz     short loc_180022781
0x180022777  cmp     [rbx+30h], r15
0x18002277b  jz      loc_180022811
0x180022781  lea     r8, asc_180036038; "    "
0x180022788  mov     rdx, rsi; unsigned __int16 *
0x18002278b  mov     rcx, rax; this
0x18002278e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022793  mov     r9, [rbx+18h]; unsigned __int16 *
0x180022797  test    r9, r9
0x18002279a  jz      short loc_1800227AE
0x18002279c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800227a3  mov     rdx, rsi; unsigned __int16 *
0x1800227a6  mov     rcx, rax; this
0x1800227a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800227ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800227b2  test    r9, r9
0x1800227b5  jz      short loc_1800227C9
0x1800227b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800227be  mov     rdx, rsi; unsigned __int16 *
0x1800227c1  mov     rcx, rax; this
0x1800227c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800227c9  mov     rcx, [rbx+28h]
0x1800227cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800227d1  mov     rdx, rsi; unsigned __int16 *
0x1800227d4  test    rcx, rcx
0x1800227d7  jz      short loc_1800227EF
0x1800227d9  mov     [rsp+278h+lpBuffer], rcx
0x1800227de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800227e5  mov     rcx, rax; this
0x1800227e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800227ed  jmp     short loc_180022811
0x1800227ef  mov     rcx, rax; this
0x1800227f2  test    r9, r9
0x1800227f5  jz      short loc_180022805
0x1800227f7  lea     r8, aHs; "[%hs]\n"
0x1800227fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022803  jmp     short loc_180022811
0x180022805  lea     r8, asc_1800360B0; "\n"
0x18002280c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022811  xor     eax, eax
0x180022813  mov     rcx, [rsp+278h+var_38]
0x18002281b  xor     rcx, rsp; StackCookie
0x18002281e  call    __security_check_cookie
0x180022823  mov     rbx, [rsp+278h+arg_18]
0x18002282b  add     rsp, 250h
0x180022832  pop     r15
0x180022834  pop     r14
0x180022836  pop     rdi
0x180022837  pop     rsi
0x180022838  pop     rbp
0x180022839  retn
```
