# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140002f54`
- end: `0x14000320a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140002364`
- `0x140003918`

## callees

- `0x140001600`
- `0x140001fa2`
- `0x140002f54`
- `0x140003c18`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003086`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003086`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003107`

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
          v8 = (const char *)&dword_14000892C;
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
0x140002f54  mov     [rsp+arg_18], rbx
0x140002f59  push    rbp
0x140002f5a  push    rsi
0x140002f5b  push    rdi
0x140002f5c  push    r14
0x140002f5e  push    r15
0x140002f60  sub     rsp, 250h
0x140002f67  mov     rax, cs:__security_cookie
0x140002f6e  xor     rax, rsp
0x140002f71  mov     [rsp+278h+var_38], rax
0x140002f79  xor     r15d, r15d
0x140002f7c  mov     rbx, r8
0x140002f7f  mov     rsi, rdx
0x140002f82  mov     r14, rcx
0x140002f85  test    rdx, rdx
0x140002f88  jz      loc_1400031E1
0x140002f8e  test    rcx, rcx
0x140002f91  jz      loc_1400031E1
0x140002f97  mov     rax, cs:g_pfnResultLoggingCallback
0x140002f9e  mov     [rcx], r15w
0x140002fa2  test    rax, rax
0x140002fa5  jz      short loc_140002FC8
0x140002fa7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002fae  jz      short loc_140002FC8
0x140002fb0  mov     r8, rdx
0x140002fb3  mov     rdx, rcx
0x140002fb6  mov     rcx, rbx
0x140002fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fbe  cmp     [r14], r15w
0x140002fc2  jnz     loc_1400031E1
0x140002fc8  mov     ecx, [rbx]
0x140002fca  mov     bpl, 8
0x140002fcd  test    ecx, ecx
0x140002fcf  jz      short loc_14000301A
0x140002fd1  sub     ecx, 1
0x140002fd4  jz      short loc_140003002
0x140002fd6  sub     ecx, 1
0x140002fd9  jz      short loc_140002FF2
0x140002fdb  cmp     ecx, 1
0x140002fde  jz      short loc_140002FE9
0x140002fe0  lea     rdi, dword_14000892C
0x140002fe7  jmp     short loc_140003021
0x140002fe9  lea     rdi, aFailfast; "FailFast"
0x140002ff0  jmp     short loc_140003021
0x140002ff2  lea     rax, aLoghr; "LogHr"
0x140002ff9  lea     rdi, aLognt; "LogNt"
0x140003000  jmp     short loc_140003010
0x140003002  lea     rax, aReturnhr; "ReturnHr"
0x140003009  lea     rdi, aReturnnt; "ReturnNt"
0x140003010  test    [rbx+4], bpl
0x140003014  cmovz   rdi, rax
0x140003018  jmp     short loc_140003021
0x14000301a  lea     rdi, aException; "Exception"
0x140003021  xor     edx, edx; Val
0x140003023  lea     rcx, [rsp+278h+Buffer]; void *
0x140003028  mov     r8d, 200h; Size
0x14000302e  call    memset_0
0x140003033  test    [rbx+4], bpl
0x140003037  jz      short loc_14000305C
0x140003039  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003040  mov     ebp, [rbx+0Ch]
0x140003043  test    rax, rax
0x140003046  jz      short loc_14000308C
0x140003048  mov     r8d, 100h
0x14000304e  lea     rdx, [rsp+278h+Buffer]
0x140003053  mov     ecx, ebp
0x140003055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000305a  jmp     short loc_14000308C
0x14000305c  mov     ebp, [rbx+8]
0x14000305f  lea     rax, [rsp+278h+Buffer]
0x140003064  mov     [rsp+278h+Arguments], r15; Arguments
0x140003069  mov     r8d, ebp; dwMessageId
0x14000306c  mov     [rsp+278h+nSize], 100h; nSize
0x140003074  mov     r9d, 400h; dwLanguageId
0x14000307a  xor     edx, edx; lpSource
0x14000307c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003081  mov     ecx, 1200h; dwFlags
0x140003086  call    cs:__imp_FormatMessageW
0x14000308c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140003090  lea     rsi, [r14+rsi*2]
0x140003094  mov     rax, [rbx+88h]
0x14000309b  mov     rdx, rsi; unsigned __int16 *
0x14000309e  mov     rcx, [rbx+80h]
0x1400030a5  test    r9, r9
0x1400030a8  jz      short loc_1400030CC
0x1400030aa  mov     [rsp+278h+Arguments], rax
0x1400030af  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400030b6  mov     eax, [rbx+40h]
0x1400030b9  mov     qword ptr [rsp+278h+nSize], rcx
0x1400030be  mov     rcx, r14; this
0x1400030c1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400030c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400030ca  jmp     short loc_1400030E3
0x1400030cc  mov     r9, rcx; unsigned __int16 *
0x1400030cf  mov     [rsp+278h+lpBuffer], rax
0x1400030d4  mov     rcx, r14; this
0x1400030d7  lea     r8, aHsP; "%hs!%p: "
0x1400030de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400030e3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400030ea  mov     r14, rax
0x1400030ed  test    r9, r9
0x1400030f0  jz      short loc_140003107
0x1400030f2  lea     r8, aCallerP; "(caller: %p) "
0x1400030f9  mov     rdx, rsi; unsigned __int16 *
0x1400030fc  mov     rcx, rax; this
0x1400030ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003104  mov     r14, rax
0x140003107  call    cs:__imp_GetCurrentThreadId
0x14000310d  lea     rcx, [rsp+278h+Buffer]
0x140003112  mov     r9, rdi; unsigned __int16 *
0x140003115  mov     [rsp+278h+var_240], rcx
0x14000311a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003121  mov     dword ptr [rsp+278h+Arguments], ebp
0x140003125  mov     rdx, rsi; unsigned __int16 *
0x140003128  mov     [rsp+278h+nSize], eax
0x14000312c  mov     rcx, r14; this
0x14000312f  mov     eax, [rbx+44h]
0x140003132  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003136  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000313b  cmp     [rbx+18h], r15
0x14000313f  jnz     short loc_140003151
0x140003141  cmp     [rbx+48h], r15
0x140003145  jnz     short loc_140003151
0x140003147  cmp     [rbx+30h], r15
0x14000314b  jz      loc_1400031E1
0x140003151  lea     r8, asc_140008718; "    "
0x140003158  mov     rdx, rsi; unsigned __int16 *
0x14000315b  mov     rcx, rax; this
0x14000315e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003163  mov     r9, [rbx+18h]; unsigned __int16 *
0x140003167  test    r9, r9
0x14000316a  jz      short loc_14000317E
0x14000316c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140003173  mov     rdx, rsi; unsigned __int16 *
0x140003176  mov     rcx, rax; this
0x140003179  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000317e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140003182  test    r9, r9
0x140003185  jz      short loc_140003199
0x140003187  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000318e  mov     rdx, rsi; unsigned __int16 *
0x140003191  mov     rcx, rax; this
0x140003194  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003199  mov     rcx, [rbx+28h]
0x14000319d  mov     rdx, rsi; unsigned __int16 *
0x1400031a0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400031a4  test    rcx, rcx
0x1400031a7  jz      short loc_1400031BF
0x1400031a9  mov     [rsp+278h+lpBuffer], rcx
0x1400031ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400031b5  mov     rcx, rax; this
0x1400031b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400031bd  jmp     short loc_1400031E1
0x1400031bf  mov     rcx, rax; this
0x1400031c2  test    r9, r9
0x1400031c5  jz      short loc_1400031D5
0x1400031c7  lea     r8, aHs; "[%hs]\n"
0x1400031ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400031d3  jmp     short loc_1400031E1
0x1400031d5  lea     r8, asc_140008928; "\n"
0x1400031dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400031e1  xor     eax, eax
0x1400031e3  mov     rcx, [rsp+278h+var_38]
0x1400031eb  xor     rcx, rsp; StackCookie
0x1400031ee  call    __security_check_cookie
0x1400031f3  mov     rbx, [rsp+278h+arg_18]
0x1400031fb  add     rsp, 250h
0x140003202  pop     r15
0x140003204  pop     r14
0x140003206  pop     rdi
0x140003207  pop     rsi
0x140003208  pop     rbp
0x140003209  retn
```
