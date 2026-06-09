# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800097dc`
- end: `0x180009a92`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800082cc`
- `0x18000a2a0`
- `0x18000d980`

## callees

- `0x1800097dc`
- `0x18000a5a0`
- `0x18000f076`
- `0x18000f0a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000990e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000990e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000998f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000998f`

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
          v7 = (const char *)&word_18001423A;
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
0x1800097dc  mov     [rsp+arg_18], rbx
0x1800097e1  push    rbp
0x1800097e2  push    rsi
0x1800097e3  push    rdi
0x1800097e4  push    r14
0x1800097e6  push    r15
0x1800097e8  sub     rsp, 250h
0x1800097ef  mov     rax, cs:__security_cookie
0x1800097f6  xor     rax, rsp
0x1800097f9  mov     [rsp+278h+var_38], rax
0x180009801  mov     rbx, r8
0x180009804  mov     rsi, rdx
0x180009807  mov     r14, rcx
0x18000980a  xor     r15d, r15d
0x18000980d  test    rdx, rdx
0x180009810  jz      loc_180009A69
0x180009816  test    rcx, rcx
0x180009819  jz      loc_180009A69
0x18000981f  mov     [rcx], r15w
0x180009823  mov     rax, cs:g_pfnResultLoggingCallback
0x18000982a  test    rax, rax
0x18000982d  jz      short loc_180009850
0x18000982f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009836  jz      short loc_180009850
0x180009838  mov     r8, rdx
0x18000983b  mov     rdx, rcx
0x18000983e  mov     rcx, rbx
0x180009841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009846  cmp     [r14], r15w
0x18000984a  jnz     loc_180009A69
0x180009850  mov     ecx, [rbx]
0x180009852  mov     bpl, 8
0x180009855  test    ecx, ecx
0x180009857  jz      short loc_1800098A2
0x180009859  sub     ecx, 1
0x18000985c  jz      short loc_18000988A
0x18000985e  sub     ecx, 1
0x180009861  jz      short loc_18000987A
0x180009863  cmp     ecx, 1
0x180009866  jz      short loc_180009871
0x180009868  lea     rdi, word_18001423A
0x18000986f  jmp     short loc_1800098A9
0x180009871  lea     rdi, aFailfast; "FailFast"
0x180009878  jmp     short loc_1800098A9
0x18000987a  lea     rax, aLoghr; "LogHr"
0x180009881  lea     rdi, aLognt; "LogNt"
0x180009888  jmp     short loc_180009898
0x18000988a  lea     rax, aReturnhr; "ReturnHr"
0x180009891  lea     rdi, aReturnnt; "ReturnNt"
0x180009898  test    [rbx+4], bpl
0x18000989c  cmovz   rdi, rax
0x1800098a0  jmp     short loc_1800098A9
0x1800098a2  lea     rdi, aException; "Exception"
0x1800098a9  xor     edx, edx; Val
0x1800098ab  mov     r8d, 200h; Size
0x1800098b1  lea     rcx, [rsp+278h+Buffer]; void *
0x1800098b6  call    memset_0
0x1800098bb  test    [rbx+4], bpl
0x1800098bf  jz      short loc_1800098E4
0x1800098c1  mov     ebp, [rbx+0Ch]
0x1800098c4  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800098cb  test    rax, rax
0x1800098ce  jz      short loc_180009914
0x1800098d0  mov     r8d, 100h
0x1800098d6  lea     rdx, [rsp+278h+Buffer]
0x1800098db  mov     ecx, ebp
0x1800098dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098e2  jmp     short loc_180009914
0x1800098e4  mov     ebp, [rbx+8]
0x1800098e7  mov     [rsp+278h+Arguments], r15; Arguments
0x1800098ec  mov     [rsp+278h+nSize], 100h; nSize
0x1800098f4  lea     rax, [rsp+278h+Buffer]
0x1800098f9  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800098fe  mov     r9d, 400h; dwLanguageId
0x180009904  mov     r8d, ebp; dwMessageId
0x180009907  xor     edx, edx; lpSource
0x180009909  mov     ecx, 1200h; dwFlags
0x18000990e  call    cs:__imp_FormatMessageW
0x180009914  lea     rsi, [r14+rsi*2]
0x180009918  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000991c  mov     rax, [rbx+88h]
0x180009923  mov     rcx, [rbx+80h]
0x18000992a  mov     rdx, rsi; unsigned __int16 *
0x18000992d  test    r9, r9
0x180009930  jz      short loc_180009954
0x180009932  mov     [rsp+278h+Arguments], rax
0x180009937  mov     qword ptr [rsp+278h+nSize], rcx
0x18000993c  mov     eax, [rbx+40h]
0x18000993f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009943  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000994a  mov     rcx, r14; this
0x18000994d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009952  jmp     short loc_18000996B
0x180009954  mov     [rsp+278h+lpBuffer], rax
0x180009959  mov     r9, rcx; unsigned __int16 *
0x18000995c  lea     r8, aHsP; "%hs!%p: "
0x180009963  mov     rcx, r14; this
0x180009966  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000996b  mov     r14, rax
0x18000996e  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009975  test    r9, r9
0x180009978  jz      short loc_18000998F
0x18000997a  lea     r8, aCallerP; "(caller: %p) "
0x180009981  mov     rdx, rsi; unsigned __int16 *
0x180009984  mov     rcx, rax; this
0x180009987  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000998c  mov     r14, rax
0x18000998f  call    cs:__imp_GetCurrentThreadId
0x180009995  lea     rcx, [rsp+278h+Buffer]
0x18000999a  mov     [rsp+278h+var_240], rcx
0x18000999f  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800099a3  mov     [rsp+278h+nSize], eax
0x1800099a7  mov     eax, [rbx+44h]
0x1800099aa  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800099ae  mov     r9, rdi; unsigned __int16 *
0x1800099b1  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800099b8  mov     rdx, rsi; unsigned __int16 *
0x1800099bb  mov     rcx, r14; this
0x1800099be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800099c3  cmp     [rbx+18h], r15
0x1800099c7  jnz     short loc_1800099D9
0x1800099c9  cmp     [rbx+48h], r15
0x1800099cd  jnz     short loc_1800099D9
0x1800099cf  cmp     [rbx+30h], r15
0x1800099d3  jz      loc_180009A69
0x1800099d9  lea     r8, asc_180013C38; "    "
0x1800099e0  mov     rdx, rsi; unsigned __int16 *
0x1800099e3  mov     rcx, rax; this
0x1800099e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800099eb  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800099ef  test    r9, r9
0x1800099f2  jz      short loc_180009A06
0x1800099f4  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800099fb  mov     rdx, rsi; unsigned __int16 *
0x1800099fe  mov     rcx, rax; this
0x180009a01  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a06  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009a0a  test    r9, r9
0x180009a0d  jz      short loc_180009A21
0x180009a0f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009a16  mov     rdx, rsi; unsigned __int16 *
0x180009a19  mov     rcx, rax; this
0x180009a1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a21  mov     rcx, [rbx+28h]
0x180009a25  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009a29  mov     rdx, rsi; unsigned __int16 *
0x180009a2c  test    rcx, rcx
0x180009a2f  jz      short loc_180009A47
0x180009a31  mov     [rsp+278h+lpBuffer], rcx
0x180009a36  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009a3d  mov     rcx, rax; this
0x180009a40  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a45  jmp     short loc_180009A69
0x180009a47  mov     rcx, rax; this
0x180009a4a  test    r9, r9
0x180009a4d  jz      short loc_180009A5D
0x180009a4f  lea     r8, aHs; "[%hs]\n"
0x180009a56  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a5b  jmp     short loc_180009A69
0x180009a5d  lea     r8, asc_180013CB0; "\n"
0x180009a64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a69  xor     eax, eax
0x180009a6b  mov     rcx, [rsp+278h+var_38]
0x180009a73  xor     rcx, rsp; StackCookie
0x180009a76  call    __security_check_cookie
0x180009a7b  mov     rbx, [rsp+278h+arg_18]
0x180009a83  add     rsp, 250h
0x180009a8a  pop     r15
0x180009a8c  pop     r14
0x180009a8e  pop     rdi
0x180009a8f  pop     rsi
0x180009a90  pop     rbp
0x180009a91  retn
```
