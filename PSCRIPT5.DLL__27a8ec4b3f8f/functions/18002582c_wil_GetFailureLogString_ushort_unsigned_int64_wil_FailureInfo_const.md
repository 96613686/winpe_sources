# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002582c`
- end: `0x180025aef`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18002381c`
- `0x180023a94`
- `0x18002627c`

## callees

- `0x180001f20`
- `0x180002938`
- `0x18002582c`
- `0x180026590`
- `0x18005f010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18002595e`
- `KERNEL32!FormatMessageW` at `0x18002595e`
- `KERNEL32!GetCurrentThreadId` at `0x1800259e5`
- `KERNEL32!GetCurrentThreadId` at `0x1800259e5`

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
  char *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  unsigned __int16 *v16; // r14
  unsigned __int16 *v17; // rax
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
          v8 = (const char *)&dword_1800644DC;
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
  v12 = (char *)this + 2 * (_QWORD)a2;
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
  v16 = v14;
  if ( v15 )
    v16 = wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          (wil::details *)v16,
          v12,
          L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v8,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf((wil::details *)v17, v12, L"    ", v18);
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
0x18002582c  mov     [rsp+arg_18], rbx
0x180025831  push    rbp
0x180025832  push    rsi
0x180025833  push    rdi
0x180025834  push    r14
0x180025836  push    r15
0x180025838  sub     rsp, 250h
0x18002583f  mov     rax, cs:__security_cookie
0x180025846  xor     rax, rsp
0x180025849  mov     [rsp+278h+var_38], rax
0x180025851  xor     r15d, r15d
0x180025854  mov     rbx, r8
0x180025857  mov     rsi, rdx
0x18002585a  mov     r14, rcx
0x18002585d  test    rdx, rdx
0x180025860  jz      loc_180025AC5
0x180025866  test    rcx, rcx
0x180025869  jz      loc_180025AC5
0x18002586f  mov     rax, cs:g_pfnResultLoggingCallback
0x180025876  mov     [rcx], r15w
0x18002587a  test    rax, rax
0x18002587d  jz      short loc_1800258A0
0x18002587f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180025886  jz      short loc_1800258A0
0x180025888  mov     r8, rdx
0x18002588b  mov     rdx, rcx
0x18002588e  mov     rcx, rbx
0x180025891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025896  cmp     [r14], r15w
0x18002589a  jnz     loc_180025AC5
0x1800258a0  mov     ecx, [rbx]
0x1800258a2  mov     bpl, 8
0x1800258a5  test    ecx, ecx
0x1800258a7  jz      short loc_1800258F2
0x1800258a9  sub     ecx, 1
0x1800258ac  jz      short loc_1800258DA
0x1800258ae  sub     ecx, 1
0x1800258b1  jz      short loc_1800258CA
0x1800258b3  cmp     ecx, 1
0x1800258b6  jz      short loc_1800258C1
0x1800258b8  lea     rdi, dword_1800644DC
0x1800258bf  jmp     short loc_1800258F9
0x1800258c1  lea     rdi, aFailfast; "FailFast"
0x1800258c8  jmp     short loc_1800258F9
0x1800258ca  lea     rax, aLoghr; "LogHr"
0x1800258d1  lea     rdi, aLognt; "LogNt"
0x1800258d8  jmp     short loc_1800258E8
0x1800258da  lea     rax, aReturnhr; "ReturnHr"
0x1800258e1  lea     rdi, aReturnnt; "ReturnNt"
0x1800258e8  test    [rbx+4], bpl
0x1800258ec  cmovz   rdi, rax
0x1800258f0  jmp     short loc_1800258F9
0x1800258f2  lea     rdi, aException; "Exception"
0x1800258f9  xor     edx, edx; Val
0x1800258fb  lea     rcx, [rsp+278h+Buffer]; void *
0x180025900  mov     r8d, 200h; Size
0x180025906  call    memset_0
0x18002590b  test    [rbx+4], bpl
0x18002590f  jz      short loc_180025934
0x180025911  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180025918  mov     ebp, [rbx+0Ch]
0x18002591b  test    rax, rax
0x18002591e  jz      short loc_18002596A
0x180025920  mov     r8d, 100h
0x180025926  lea     rdx, [rsp+278h+Buffer]
0x18002592b  mov     ecx, ebp
0x18002592d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025932  jmp     short loc_18002596A
0x180025934  mov     ebp, [rbx+8]
0x180025937  lea     rax, [rsp+278h+Buffer]
0x18002593c  mov     [rsp+278h+Arguments], r15; Arguments
0x180025941  mov     r8d, ebp; dwMessageId
0x180025944  mov     [rsp+278h+nSize], 100h; nSize
0x18002594c  mov     r9d, 400h; dwLanguageId
0x180025952  xor     edx, edx; lpSource
0x180025954  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180025959  mov     ecx, 1200h; dwFlags
0x18002595e  call    cs:__imp_FormatMessageW
0x180025965  nop     dword ptr [rax+rax+00h]
0x18002596a  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002596e  lea     rsi, [r14+rsi*2]
0x180025972  mov     rax, [rbx+88h]
0x180025979  mov     rdx, rsi; unsigned __int16 *
0x18002597c  mov     rcx, [rbx+80h]
0x180025983  test    r9, r9
0x180025986  jz      short loc_1800259AA
0x180025988  mov     [rsp+278h+Arguments], rax
0x18002598d  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180025994  mov     eax, [rbx+40h]
0x180025997  mov     qword ptr [rsp+278h+nSize], rcx
0x18002599c  mov     rcx, r14; this
0x18002599f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800259a3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800259a8  jmp     short loc_1800259C1
0x1800259aa  mov     r9, rcx; unsigned __int16 *
0x1800259ad  mov     [rsp+278h+lpBuffer], rax
0x1800259b2  mov     rcx, r14; this
0x1800259b5  lea     r8, aHsP; "%hs!%p: "
0x1800259bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800259c1  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800259c8  mov     r14, rax
0x1800259cb  test    r9, r9
0x1800259ce  jz      short loc_1800259E5
0x1800259d0  lea     r8, aCallerP; "(caller: %p) "
0x1800259d7  mov     rdx, rsi; unsigned __int16 *
0x1800259da  mov     rcx, rax; this
0x1800259dd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800259e2  mov     r14, rax
0x1800259e5  call    cs:__imp_GetCurrentThreadId
0x1800259ec  nop     dword ptr [rax+rax+00h]
0x1800259f1  lea     rcx, [rsp+278h+Buffer]
0x1800259f6  mov     r9, rdi; unsigned __int16 *
0x1800259f9  mov     [rsp+278h+var_240], rcx
0x1800259fe  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180025a05  mov     dword ptr [rsp+278h+Arguments], ebp
0x180025a09  mov     rdx, rsi; unsigned __int16 *
0x180025a0c  mov     [rsp+278h+nSize], eax
0x180025a10  mov     rcx, r14; this
0x180025a13  mov     eax, [rbx+44h]
0x180025a16  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180025a1a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025a1f  cmp     [rbx+18h], r15
0x180025a23  jnz     short loc_180025A35
0x180025a25  cmp     [rbx+48h], r15
0x180025a29  jnz     short loc_180025A35
0x180025a2b  cmp     [rbx+30h], r15
0x180025a2f  jz      loc_180025AC5
0x180025a35  lea     r8, asc_180066B88; "    "
0x180025a3c  mov     rdx, rsi; unsigned __int16 *
0x180025a3f  mov     rcx, rax; this
0x180025a42  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025a47  mov     r9, [rbx+18h]; unsigned __int16 *
0x180025a4b  test    r9, r9
0x180025a4e  jz      short loc_180025A62
0x180025a50  lea     r8, aMsgWs; "Msg:[%ws] "
0x180025a57  mov     rdx, rsi; unsigned __int16 *
0x180025a5a  mov     rcx, rax; this
0x180025a5d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025a62  mov     r9, [rbx+48h]; unsigned __int16 *
0x180025a66  test    r9, r9
0x180025a69  jz      short loc_180025A7D
0x180025a6b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180025a72  mov     rdx, rsi; unsigned __int16 *
0x180025a75  mov     rcx, rax; this
0x180025a78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025a7d  mov     rcx, [rbx+28h]
0x180025a81  mov     rdx, rsi; unsigned __int16 *
0x180025a84  mov     r9, [rbx+30h]; unsigned __int16 *
0x180025a88  test    rcx, rcx
0x180025a8b  jz      short loc_180025AA3
0x180025a8d  mov     [rsp+278h+lpBuffer], rcx
0x180025a92  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180025a99  mov     rcx, rax; this
0x180025a9c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025aa1  jmp     short loc_180025AC5
0x180025aa3  mov     rcx, rax; this
0x180025aa6  test    r9, r9
0x180025aa9  jz      short loc_180025AB9
0x180025aab  lea     r8, aHs; "[%hs]\n"
0x180025ab2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025ab7  jmp     short loc_180025AC5
0x180025ab9  lea     r8, asc_180066C00; "\n"
0x180025ac0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025ac5  xor     eax, eax
0x180025ac7  mov     rcx, [rsp+278h+var_38]
0x180025acf  xor     rcx, rsp; StackCookie
0x180025ad2  call    __security_check_cookie
0x180025ad7  mov     rbx, [rsp+278h+arg_18]
0x180025adf  add     rsp, 250h
0x180025ae6  pop     r15
0x180025ae8  pop     r14
0x180025aea  pop     rdi
0x180025aeb  pop     rsi
0x180025aec  pop     rbp
0x180025aed  retn
```
