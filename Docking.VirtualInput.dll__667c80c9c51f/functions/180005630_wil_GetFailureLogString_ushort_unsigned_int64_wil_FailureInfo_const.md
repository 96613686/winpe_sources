# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005630`
- end: `0x1800058e6`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800046fc`
- `0x180006048`
- `0x1800074d0`

## callees

- `0x1800036a0`
- `0x180004054`
- `0x180005630`
- `0x180006348`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057e3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005762`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005762`

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
          v7 = (const char *)&word_18001EE3A;
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
0x180005630  mov     [rsp+arg_18], rbx
0x180005635  push    rbp
0x180005636  push    rsi
0x180005637  push    rdi
0x180005638  push    r14
0x18000563a  push    r15
0x18000563c  sub     rsp, 250h
0x180005643  mov     rax, cs:__security_cookie
0x18000564a  xor     rax, rsp
0x18000564d  mov     [rsp+278h+var_38], rax
0x180005655  mov     rbx, r8
0x180005658  mov     rsi, rdx
0x18000565b  mov     r14, rcx
0x18000565e  xor     r15d, r15d
0x180005661  test    rdx, rdx
0x180005664  jz      loc_1800058BD
0x18000566a  test    rcx, rcx
0x18000566d  jz      loc_1800058BD
0x180005673  mov     [rcx], r15w
0x180005677  mov     rax, cs:g_pfnResultLoggingCallback
0x18000567e  test    rax, rax
0x180005681  jz      short loc_1800056A4
0x180005683  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000568a  jz      short loc_1800056A4
0x18000568c  mov     r8, rdx
0x18000568f  mov     rdx, rcx
0x180005692  mov     rcx, rbx
0x180005695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000569a  cmp     [r14], r15w
0x18000569e  jnz     loc_1800058BD
0x1800056a4  mov     ecx, [rbx]
0x1800056a6  mov     bpl, 8
0x1800056a9  test    ecx, ecx
0x1800056ab  jz      short loc_1800056F6
0x1800056ad  sub     ecx, 1
0x1800056b0  jz      short loc_1800056DE
0x1800056b2  sub     ecx, 1
0x1800056b5  jz      short loc_1800056CE
0x1800056b7  cmp     ecx, 1
0x1800056ba  jz      short loc_1800056C5
0x1800056bc  lea     rdi, word_18001EE3A
0x1800056c3  jmp     short loc_1800056FD
0x1800056c5  lea     rdi, aFailfast; "FailFast"
0x1800056cc  jmp     short loc_1800056FD
0x1800056ce  lea     rax, aLoghr; "LogHr"
0x1800056d5  lea     rdi, aLognt; "LogNt"
0x1800056dc  jmp     short loc_1800056EC
0x1800056de  lea     rax, aReturnhr; "ReturnHr"
0x1800056e5  lea     rdi, aReturnnt; "ReturnNt"
0x1800056ec  test    [rbx+4], bpl
0x1800056f0  cmovz   rdi, rax
0x1800056f4  jmp     short loc_1800056FD
0x1800056f6  lea     rdi, aException; "Exception"
0x1800056fd  xor     edx, edx; Val
0x1800056ff  mov     r8d, 200h; Size
0x180005705  lea     rcx, [rsp+278h+Buffer]; void *
0x18000570a  call    memset_0
0x18000570f  test    [rbx+4], bpl
0x180005713  jz      short loc_180005738
0x180005715  mov     ebp, [rbx+0Ch]
0x180005718  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000571f  test    rax, rax
0x180005722  jz      short loc_180005768
0x180005724  mov     r8d, 100h
0x18000572a  lea     rdx, [rsp+278h+Buffer]
0x18000572f  mov     ecx, ebp
0x180005731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005736  jmp     short loc_180005768
0x180005738  mov     ebp, [rbx+8]
0x18000573b  mov     [rsp+278h+Arguments], r15; Arguments
0x180005740  mov     [rsp+278h+nSize], 100h; nSize
0x180005748  lea     rax, [rsp+278h+Buffer]
0x18000574d  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005752  mov     r9d, 400h; dwLanguageId
0x180005758  mov     r8d, ebp; dwMessageId
0x18000575b  xor     edx, edx; lpSource
0x18000575d  mov     ecx, 1200h; dwFlags
0x180005762  call    cs:__imp_FormatMessageW
0x180005768  lea     rsi, [r14+rsi*2]
0x18000576c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005770  mov     rax, [rbx+88h]
0x180005777  mov     rcx, [rbx+80h]
0x18000577e  mov     rdx, rsi; unsigned __int16 *
0x180005781  test    r9, r9
0x180005784  jz      short loc_1800057A8
0x180005786  mov     [rsp+278h+Arguments], rax
0x18000578b  mov     qword ptr [rsp+278h+nSize], rcx
0x180005790  mov     eax, [rbx+40h]
0x180005793  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005797  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000579e  mov     rcx, r14; this
0x1800057a1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057a6  jmp     short loc_1800057BF
0x1800057a8  mov     [rsp+278h+lpBuffer], rax
0x1800057ad  mov     r9, rcx; unsigned __int16 *
0x1800057b0  lea     r8, aHsP; "%hs!%p: "
0x1800057b7  mov     rcx, r14; this
0x1800057ba  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057bf  mov     r14, rax
0x1800057c2  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800057c9  test    r9, r9
0x1800057cc  jz      short loc_1800057E3
0x1800057ce  lea     r8, aCallerP; "(caller: %p) "
0x1800057d5  mov     rdx, rsi; unsigned __int16 *
0x1800057d8  mov     rcx, rax; this
0x1800057db  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057e0  mov     r14, rax
0x1800057e3  call    cs:__imp_GetCurrentThreadId
0x1800057e9  lea     rcx, [rsp+278h+Buffer]
0x1800057ee  mov     [rsp+278h+var_240], rcx
0x1800057f3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800057f7  mov     [rsp+278h+nSize], eax
0x1800057fb  mov     eax, [rbx+44h]
0x1800057fe  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005802  mov     r9, rdi; unsigned __int16 *
0x180005805  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000580c  mov     rdx, rsi; unsigned __int16 *
0x18000580f  mov     rcx, r14; this
0x180005812  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005817  cmp     [rbx+18h], r15
0x18000581b  jnz     short loc_18000582D
0x18000581d  cmp     [rbx+48h], r15
0x180005821  jnz     short loc_18000582D
0x180005823  cmp     [rbx+30h], r15
0x180005827  jz      loc_1800058BD
0x18000582d  lea     r8, asc_18001EF40; "    "
0x180005834  mov     rdx, rsi; unsigned __int16 *
0x180005837  mov     rcx, rax; this
0x18000583a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000583f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005843  test    r9, r9
0x180005846  jz      short loc_18000585A
0x180005848  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000584f  mov     rdx, rsi; unsigned __int16 *
0x180005852  mov     rcx, rax; this
0x180005855  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000585a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000585e  test    r9, r9
0x180005861  jz      short loc_180005875
0x180005863  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000586a  mov     rdx, rsi; unsigned __int16 *
0x18000586d  mov     rcx, rax; this
0x180005870  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005875  mov     rcx, [rbx+28h]
0x180005879  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000587d  mov     rdx, rsi; unsigned __int16 *
0x180005880  test    rcx, rcx
0x180005883  jz      short loc_18000589B
0x180005885  mov     [rsp+278h+lpBuffer], rcx
0x18000588a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005891  mov     rcx, rax; this
0x180005894  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005899  jmp     short loc_1800058BD
0x18000589b  mov     rcx, rax; this
0x18000589e  test    r9, r9
0x1800058a1  jz      short loc_1800058B1
0x1800058a3  lea     r8, aHs; "[%hs]\n"
0x1800058aa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800058af  jmp     short loc_1800058BD
0x1800058b1  lea     r8, asc_18001EFB8; "\n"
0x1800058b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800058bd  xor     eax, eax
0x1800058bf  mov     rcx, [rsp+278h+var_38]
0x1800058c7  xor     rcx, rsp; StackCookie
0x1800058ca  call    __security_check_cookie
0x1800058cf  mov     rbx, [rsp+278h+arg_18]
0x1800058d7  add     rsp, 250h
0x1800058de  pop     r15
0x1800058e0  pop     r14
0x1800058e2  pop     rdi
0x1800058e3  pop     rsi
0x1800058e4  pop     rbp
0x1800058e5  retn
```
