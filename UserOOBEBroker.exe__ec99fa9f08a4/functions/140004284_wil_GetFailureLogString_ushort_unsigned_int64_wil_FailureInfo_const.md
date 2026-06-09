# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004284`
- end: `0x14000453a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x140002e74`
- `0x1400030f4`
- `0x140004be8`
- `0x1400068d0`
- `0x14000783c`
- `0x14000e3ff`
- `0x14000e533`

## callees

- `0x14000295f`
- `0x140004284`
- `0x140004ee8`
- `0x14000e1c0`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004437`
- `KERNEL32!GetCurrentThreadId` at `0x140004437`
- `KERNEL32!FormatMessageW` at `0x1400043b6`
- `KERNEL32!FormatMessageW` at `0x1400043b6`

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
          v7 = (const char *)&qword_1400131D0;
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
0x140004284  mov     [rsp+arg_18], rbx
0x140004289  push    rbp
0x14000428a  push    rsi
0x14000428b  push    rdi
0x14000428c  push    r14
0x14000428e  push    r15
0x140004290  sub     rsp, 250h
0x140004297  mov     rax, cs:__security_cookie
0x14000429e  xor     rax, rsp
0x1400042a1  mov     [rsp+278h+var_38], rax
0x1400042a9  mov     rbx, r8
0x1400042ac  mov     rsi, rdx
0x1400042af  mov     r14, rcx
0x1400042b2  xor     r15d, r15d
0x1400042b5  test    rdx, rdx
0x1400042b8  jz      loc_140004511
0x1400042be  test    rcx, rcx
0x1400042c1  jz      loc_140004511
0x1400042c7  mov     [rcx], r15w
0x1400042cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1400042d2  test    rax, rax
0x1400042d5  jz      short loc_1400042F8
0x1400042d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400042de  jz      short loc_1400042F8
0x1400042e0  mov     r8, rdx
0x1400042e3  mov     rdx, rcx
0x1400042e6  mov     rcx, rbx
0x1400042e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042ee  cmp     [r14], r15w
0x1400042f2  jnz     loc_140004511
0x1400042f8  mov     ecx, [rbx]
0x1400042fa  mov     bpl, 8
0x1400042fd  test    ecx, ecx
0x1400042ff  jz      short loc_14000434A
0x140004301  sub     ecx, 1
0x140004304  jz      short loc_140004332
0x140004306  sub     ecx, 1
0x140004309  jz      short loc_140004322
0x14000430b  cmp     ecx, 1
0x14000430e  jz      short loc_140004319
0x140004310  lea     rdi, qword_1400131D0
0x140004317  jmp     short loc_140004351
0x140004319  lea     rdi, aFailfast; "FailFast"
0x140004320  jmp     short loc_140004351
0x140004322  lea     rax, aLoghr; "LogHr"
0x140004329  lea     rdi, aLognt; "LogNt"
0x140004330  jmp     short loc_140004340
0x140004332  lea     rax, aReturnhr; "ReturnHr"
0x140004339  lea     rdi, aReturnnt; "ReturnNt"
0x140004340  test    [rbx+4], bpl
0x140004344  cmovz   rdi, rax
0x140004348  jmp     short loc_140004351
0x14000434a  lea     rdi, aException; "Exception"
0x140004351  xor     edx, edx; Val
0x140004353  mov     r8d, 200h; Size
0x140004359  lea     rcx, [rsp+278h+Buffer]; void *
0x14000435e  call    memset_0
0x140004363  test    [rbx+4], bpl
0x140004367  jz      short loc_14000438C
0x140004369  mov     ebp, [rbx+0Ch]
0x14000436c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004373  test    rax, rax
0x140004376  jz      short loc_1400043BC
0x140004378  mov     r8d, 100h
0x14000437e  lea     rdx, [rsp+278h+Buffer]
0x140004383  mov     ecx, ebp
0x140004385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000438a  jmp     short loc_1400043BC
0x14000438c  mov     ebp, [rbx+8]
0x14000438f  mov     [rsp+278h+Arguments], r15; Arguments
0x140004394  mov     [rsp+278h+nSize], 100h; nSize
0x14000439c  lea     rax, [rsp+278h+Buffer]
0x1400043a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400043a6  mov     r9d, 400h; dwLanguageId
0x1400043ac  mov     r8d, ebp; dwMessageId
0x1400043af  xor     edx, edx; lpSource
0x1400043b1  mov     ecx, 1200h; dwFlags
0x1400043b6  call    cs:__imp_FormatMessageW
0x1400043bc  lea     rsi, [r14+rsi*2]
0x1400043c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400043c4  mov     rax, [rbx+88h]
0x1400043cb  mov     rcx, [rbx+80h]
0x1400043d2  mov     rdx, rsi; unsigned __int16 *
0x1400043d5  test    r9, r9
0x1400043d8  jz      short loc_1400043FC
0x1400043da  mov     [rsp+278h+Arguments], rax
0x1400043df  mov     qword ptr [rsp+278h+nSize], rcx
0x1400043e4  mov     eax, [rbx+40h]
0x1400043e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400043eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400043f2  mov     rcx, r14; this
0x1400043f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400043fa  jmp     short loc_140004413
0x1400043fc  mov     [rsp+278h+lpBuffer], rax
0x140004401  mov     r9, rcx; unsigned __int16 *
0x140004404  lea     r8, aHsP; "%hs!%p: "
0x14000440b  mov     rcx, r14; this
0x14000440e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004413  mov     r14, rax
0x140004416  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000441d  test    r9, r9
0x140004420  jz      short loc_140004437
0x140004422  lea     r8, aCallerP; "(caller: %p) "
0x140004429  mov     rdx, rsi; unsigned __int16 *
0x14000442c  mov     rcx, rax; this
0x14000442f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004434  mov     r14, rax
0x140004437  call    cs:__imp_GetCurrentThreadId
0x14000443d  lea     rcx, [rsp+278h+Buffer]
0x140004442  mov     [rsp+278h+var_240], rcx
0x140004447  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000444b  mov     [rsp+278h+nSize], eax
0x14000444f  mov     eax, [rbx+44h]
0x140004452  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004456  mov     r9, rdi; unsigned __int16 *
0x140004459  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004460  mov     rdx, rsi; unsigned __int16 *
0x140004463  mov     rcx, r14; this
0x140004466  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000446b  cmp     [rbx+18h], r15
0x14000446f  jnz     short loc_140004481
0x140004471  cmp     [rbx+48h], r15
0x140004475  jnz     short loc_140004481
0x140004477  cmp     [rbx+30h], r15
0x14000447b  jz      loc_140004511
0x140004481  lea     r8, asc_1400132C0; "    "
0x140004488  mov     rdx, rsi; unsigned __int16 *
0x14000448b  mov     rcx, rax; this
0x14000448e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004493  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004497  test    r9, r9
0x14000449a  jz      short loc_1400044AE
0x14000449c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400044a3  mov     rdx, rsi; unsigned __int16 *
0x1400044a6  mov     rcx, rax; this
0x1400044a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400044b2  test    r9, r9
0x1400044b5  jz      short loc_1400044C9
0x1400044b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400044be  mov     rdx, rsi; unsigned __int16 *
0x1400044c1  mov     rcx, rax; this
0x1400044c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044c9  mov     rcx, [rbx+28h]
0x1400044cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400044d1  mov     rdx, rsi; unsigned __int16 *
0x1400044d4  test    rcx, rcx
0x1400044d7  jz      short loc_1400044EF
0x1400044d9  mov     [rsp+278h+lpBuffer], rcx
0x1400044de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400044e5  mov     rcx, rax; this
0x1400044e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400044ed  jmp     short loc_140004511
0x1400044ef  mov     rcx, rax; this
0x1400044f2  test    r9, r9
0x1400044f5  jz      short loc_140004505
0x1400044f7  lea     r8, aHs; "[%hs]\n"
0x1400044fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004503  jmp     short loc_140004511
0x140004505  lea     r8, asc_140013338; "\n"
0x14000450c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004511  xor     eax, eax
0x140004513  mov     rcx, [rsp+278h+var_38]
0x14000451b  xor     rcx, rsp; StackCookie
0x14000451e  call    __security_check_cookie
0x140004523  mov     rbx, [rsp+278h+arg_18]
0x14000452b  add     rsp, 250h
0x140004532  pop     r15
0x140004534  pop     r14
0x140004536  pop     rdi
0x140004537  pop     rsi
0x140004538  pop     rbp
0x140004539  retn
```
