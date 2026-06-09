# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180054054`
- end: `0x180054317`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800520e8`
- `0x18005502c`

## callees

- `0x180049d00`
- `0x18004a71c`
- `0x180054054`
- `0x180055384`
- `0x180077010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180054186`
- `KERNEL32!FormatMessageW` at `0x180054186`
- `KERNEL32!GetCurrentThreadId` at `0x18005420d`
- `KERNEL32!GetCurrentThreadId` at `0x18005420d`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wchar_t *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wchar_t *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
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
  v7 = (void (__fastcall *)(__int64, wchar_t *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *this )
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
          v8 = (const char *)&dword_180082074;
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
  v12 = (char *)&this[(_QWORD)a2];
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
    v16 = wil::details::LogStringPrintf(v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf(v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180054054  mov     [rsp+arg_18], rbx
0x180054059  push    rbp
0x18005405a  push    rsi
0x18005405b  push    rdi
0x18005405c  push    r14
0x18005405e  push    r15
0x180054060  sub     rsp, 250h
0x180054067  mov     rax, cs:__security_cookie
0x18005406e  xor     rax, rsp
0x180054071  mov     [rsp+278h+var_38], rax
0x180054079  xor     r15d, r15d
0x18005407c  mov     rbx, r8
0x18005407f  mov     rsi, rdx
0x180054082  mov     r14, rcx
0x180054085  test    rdx, rdx
0x180054088  jz      loc_1800542ED
0x18005408e  test    rcx, rcx
0x180054091  jz      loc_1800542ED
0x180054097  mov     rax, cs:g_pfnResultLoggingCallback
0x18005409e  mov     [rcx], r15w
0x1800540a2  test    rax, rax
0x1800540a5  jz      short loc_1800540C8
0x1800540a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800540ae  jz      short loc_1800540C8
0x1800540b0  mov     r8, rdx
0x1800540b3  mov     rdx, rcx
0x1800540b6  mov     rcx, rbx
0x1800540b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540be  cmp     [r14], r15w
0x1800540c2  jnz     loc_1800542ED
0x1800540c8  mov     ecx, [rbx]
0x1800540ca  mov     bpl, 8
0x1800540cd  test    ecx, ecx
0x1800540cf  jz      short loc_18005411A
0x1800540d1  sub     ecx, 1
0x1800540d4  jz      short loc_180054102
0x1800540d6  sub     ecx, 1
0x1800540d9  jz      short loc_1800540F2
0x1800540db  cmp     ecx, 1
0x1800540de  jz      short loc_1800540E9
0x1800540e0  lea     rdi, dword_180082074
0x1800540e7  jmp     short loc_180054121
0x1800540e9  lea     rdi, aFailfast; "FailFast"
0x1800540f0  jmp     short loc_180054121
0x1800540f2  lea     rax, aLoghr; "LogHr"
0x1800540f9  lea     rdi, aLognt; "LogNt"
0x180054100  jmp     short loc_180054110
0x180054102  lea     rax, aReturnhr; "ReturnHr"
0x180054109  lea     rdi, aReturnnt; "ReturnNt"
0x180054110  test    [rbx+4], bpl
0x180054114  cmovz   rdi, rax
0x180054118  jmp     short loc_180054121
0x18005411a  lea     rdi, aException; "Exception"
0x180054121  xor     edx, edx; Val
0x180054123  lea     rcx, [rsp+278h+Buffer]; void *
0x180054128  mov     r8d, 200h; Size
0x18005412e  call    memset_0
0x180054133  test    [rbx+4], bpl
0x180054137  jz      short loc_18005415C
0x180054139  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180054140  mov     ebp, [rbx+0Ch]
0x180054143  test    rax, rax
0x180054146  jz      short loc_180054192
0x180054148  mov     r8d, 100h
0x18005414e  lea     rdx, [rsp+278h+Buffer]
0x180054153  mov     ecx, ebp
0x180054155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005415a  jmp     short loc_180054192
0x18005415c  mov     ebp, [rbx+8]
0x18005415f  lea     rax, [rsp+278h+Buffer]
0x180054164  mov     [rsp+278h+Arguments], r15; Arguments
0x180054169  mov     r8d, ebp; dwMessageId
0x18005416c  mov     [rsp+278h+nSize], 100h; nSize
0x180054174  mov     r9d, 400h; dwLanguageId
0x18005417a  xor     edx, edx; lpSource
0x18005417c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180054181  mov     ecx, 1200h; dwFlags
0x180054186  call    cs:__imp_FormatMessageW
0x18005418d  nop     dword ptr [rax+rax+00h]
0x180054192  mov     r9, [rbx+38h]; unsigned __int16 *
0x180054196  lea     rsi, [r14+rsi*2]
0x18005419a  mov     rax, [rbx+88h]
0x1800541a1  mov     rdx, rsi; unsigned __int16 *
0x1800541a4  mov     rcx, [rbx+80h]
0x1800541ab  test    r9, r9
0x1800541ae  jz      short loc_1800541D2
0x1800541b0  mov     [rsp+278h+Arguments], rax
0x1800541b5  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800541bc  mov     eax, [rbx+40h]
0x1800541bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800541c4  mov     rcx, r14; this
0x1800541c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800541cb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800541d0  jmp     short loc_1800541E9
0x1800541d2  mov     r9, rcx; unsigned __int16 *
0x1800541d5  mov     [rsp+278h+lpBuffer], rax
0x1800541da  mov     rcx, r14; this
0x1800541dd  lea     r8, aHsP; "%hs!%p: "
0x1800541e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800541e9  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800541f0  mov     r14, rax
0x1800541f3  test    r9, r9
0x1800541f6  jz      short loc_18005420D
0x1800541f8  lea     r8, aCallerP; "(caller: %p) "
0x1800541ff  mov     rdx, rsi; unsigned __int16 *
0x180054202  mov     rcx, rax; this
0x180054205  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005420a  mov     r14, rax
0x18005420d  call    cs:__imp_GetCurrentThreadId
0x180054214  nop     dword ptr [rax+rax+00h]
0x180054219  lea     rcx, [rsp+278h+Buffer]
0x18005421e  mov     r9, rdi; unsigned __int16 *
0x180054221  mov     [rsp+278h+var_240], rcx
0x180054226  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18005422d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180054231  mov     rdx, rsi; unsigned __int16 *
0x180054234  mov     [rsp+278h+nSize], eax
0x180054238  mov     rcx, r14; this
0x18005423b  mov     eax, [rbx+44h]
0x18005423e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180054242  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180054247  cmp     [rbx+18h], r15
0x18005424b  jnz     short loc_18005425D
0x18005424d  cmp     [rbx+48h], r15
0x180054251  jnz     short loc_18005425D
0x180054253  cmp     [rbx+30h], r15
0x180054257  jz      loc_1800542ED
0x18005425d  lea     r8, asc_180082D68; "    "
0x180054264  mov     rdx, rsi; unsigned __int16 *
0x180054267  mov     rcx, rax; this
0x18005426a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005426f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180054273  test    r9, r9
0x180054276  jz      short loc_18005428A
0x180054278  lea     r8, aMsgWs; "Msg:[%ws] "
0x18005427f  mov     rdx, rsi; unsigned __int16 *
0x180054282  mov     rcx, rax; this
0x180054285  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005428a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18005428e  test    r9, r9
0x180054291  jz      short loc_1800542A5
0x180054293  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18005429a  mov     rdx, rsi; unsigned __int16 *
0x18005429d  mov     rcx, rax; this
0x1800542a0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800542a5  mov     rcx, [rbx+28h]
0x1800542a9  mov     rdx, rsi; unsigned __int16 *
0x1800542ac  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800542b0  test    rcx, rcx
0x1800542b3  jz      short loc_1800542CB
0x1800542b5  mov     [rsp+278h+lpBuffer], rcx
0x1800542ba  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800542c1  mov     rcx, rax; this
0x1800542c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800542c9  jmp     short loc_1800542ED
0x1800542cb  mov     rcx, rax; this
0x1800542ce  test    r9, r9
0x1800542d1  jz      short loc_1800542E1
0x1800542d3  lea     r8, aHs; "[%hs]\n"
0x1800542da  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800542df  jmp     short loc_1800542ED
0x1800542e1  lea     r8, asc_180082DE0; "\n"
0x1800542e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800542ed  xor     eax, eax
0x1800542ef  mov     rcx, [rsp+278h+var_38]
0x1800542f7  xor     rcx, rsp; StackCookie
0x1800542fa  call    __security_check_cookie
0x1800542ff  mov     rbx, [rsp+278h+arg_18]
0x180054307  add     rsp, 250h
0x18005430e  pop     r15
0x180054310  pop     r14
0x180054312  pop     rdi
0x180054313  pop     rsi
0x180054314  pop     rbp
0x180054315  retn
```
