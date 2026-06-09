# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009868`
- end: `0x180009b1e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1800090bc`
- `0x18000933c`
- `0x180009f98`
- `0x180019b50`
- `0x18001e2a6`
- `0x18001e3da`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180009868`
- `0x18000a298`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a1b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000999a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000999a`

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
          v7 = (const char *)&byte_1800240B7;
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
0x180009868  mov     [rsp+arg_18], rbx
0x18000986d  push    rbp
0x18000986e  push    rsi
0x18000986f  push    rdi
0x180009870  push    r14
0x180009872  push    r15
0x180009874  sub     rsp, 250h
0x18000987b  mov     rax, cs:__security_cookie
0x180009882  xor     rax, rsp
0x180009885  mov     [rsp+278h+var_38], rax
0x18000988d  mov     rbx, r8
0x180009890  mov     rsi, rdx
0x180009893  mov     r14, rcx
0x180009896  xor     r15d, r15d
0x180009899  test    rdx, rdx
0x18000989c  jz      loc_180009AF5
0x1800098a2  test    rcx, rcx
0x1800098a5  jz      loc_180009AF5
0x1800098ab  mov     [rcx], r15w
0x1800098af  mov     rax, cs:g_pfnResultLoggingCallback
0x1800098b6  test    rax, rax
0x1800098b9  jz      short loc_1800098DC
0x1800098bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800098c2  jz      short loc_1800098DC
0x1800098c4  mov     r8, rdx
0x1800098c7  mov     rdx, rcx
0x1800098ca  mov     rcx, rbx
0x1800098cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098d2  cmp     [r14], r15w
0x1800098d6  jnz     loc_180009AF5
0x1800098dc  mov     ecx, [rbx]
0x1800098de  mov     bpl, 8
0x1800098e1  test    ecx, ecx
0x1800098e3  jz      short loc_18000992E
0x1800098e5  sub     ecx, 1
0x1800098e8  jz      short loc_180009916
0x1800098ea  sub     ecx, 1
0x1800098ed  jz      short loc_180009906
0x1800098ef  cmp     ecx, 1
0x1800098f2  jz      short loc_1800098FD
0x1800098f4  lea     rdi, byte_1800240B7
0x1800098fb  jmp     short loc_180009935
0x1800098fd  lea     rdi, aFailfast; "FailFast"
0x180009904  jmp     short loc_180009935
0x180009906  lea     rax, aLoghr; "LogHr"
0x18000990d  lea     rdi, aLognt; "LogNt"
0x180009914  jmp     short loc_180009924
0x180009916  lea     rax, aReturnhr; "ReturnHr"
0x18000991d  lea     rdi, aReturnnt; "ReturnNt"
0x180009924  test    [rbx+4], bpl
0x180009928  cmovz   rdi, rax
0x18000992c  jmp     short loc_180009935
0x18000992e  lea     rdi, aException; "Exception"
0x180009935  xor     edx, edx; Val
0x180009937  mov     r8d, 200h; Size
0x18000993d  lea     rcx, [rsp+278h+Buffer]; void *
0x180009942  call    memset_0
0x180009947  test    [rbx+4], bpl
0x18000994b  jz      short loc_180009970
0x18000994d  mov     ebp, [rbx+0Ch]
0x180009950  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009957  test    rax, rax
0x18000995a  jz      short loc_1800099A0
0x18000995c  mov     r8d, 100h
0x180009962  lea     rdx, [rsp+278h+Buffer]
0x180009967  mov     ecx, ebp
0x180009969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000996e  jmp     short loc_1800099A0
0x180009970  mov     ebp, [rbx+8]
0x180009973  mov     [rsp+278h+Arguments], r15; Arguments
0x180009978  mov     [rsp+278h+nSize], 100h; nSize
0x180009980  lea     rax, [rsp+278h+Buffer]
0x180009985  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000998a  mov     r9d, 400h; dwLanguageId
0x180009990  mov     r8d, ebp; dwMessageId
0x180009993  xor     edx, edx; lpSource
0x180009995  mov     ecx, 1200h; dwFlags
0x18000999a  call    cs:__imp_FormatMessageW
0x1800099a0  lea     rsi, [r14+rsi*2]
0x1800099a4  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800099a8  mov     rax, [rbx+88h]
0x1800099af  mov     rcx, [rbx+80h]
0x1800099b6  mov     rdx, rsi; unsigned __int16 *
0x1800099b9  test    r9, r9
0x1800099bc  jz      short loc_1800099E0
0x1800099be  mov     [rsp+278h+Arguments], rax
0x1800099c3  mov     qword ptr [rsp+278h+nSize], rcx
0x1800099c8  mov     eax, [rbx+40h]
0x1800099cb  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800099cf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800099d6  mov     rcx, r14; this
0x1800099d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800099de  jmp     short loc_1800099F7
0x1800099e0  mov     [rsp+278h+lpBuffer], rax
0x1800099e5  mov     r9, rcx; unsigned __int16 *
0x1800099e8  lea     r8, aHsP; "%hs!%p: "
0x1800099ef  mov     rcx, r14; this
0x1800099f2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800099f7  mov     r14, rax
0x1800099fa  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009a01  test    r9, r9
0x180009a04  jz      short loc_180009A1B
0x180009a06  lea     r8, aCallerP; "(caller: %p) "
0x180009a0d  mov     rdx, rsi; unsigned __int16 *
0x180009a10  mov     rcx, rax; this
0x180009a13  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a18  mov     r14, rax
0x180009a1b  call    cs:__imp_GetCurrentThreadId
0x180009a21  lea     rcx, [rsp+278h+Buffer]
0x180009a26  mov     [rsp+278h+var_240], rcx
0x180009a2b  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009a2f  mov     [rsp+278h+nSize], eax
0x180009a33  mov     eax, [rbx+44h]
0x180009a36  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009a3a  mov     r9, rdi; unsigned __int16 *
0x180009a3d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009a44  mov     rdx, rsi; unsigned __int16 *
0x180009a47  mov     rcx, r14; this
0x180009a4a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a4f  cmp     [rbx+18h], r15
0x180009a53  jnz     short loc_180009A65
0x180009a55  cmp     [rbx+48h], r15
0x180009a59  jnz     short loc_180009A65
0x180009a5b  cmp     [rbx+30h], r15
0x180009a5f  jz      loc_180009AF5
0x180009a65  lea     r8, asc_1800241A0; "    "
0x180009a6c  mov     rdx, rsi; unsigned __int16 *
0x180009a6f  mov     rcx, rax; this
0x180009a72  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a77  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009a7b  test    r9, r9
0x180009a7e  jz      short loc_180009A92
0x180009a80  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009a87  mov     rdx, rsi; unsigned __int16 *
0x180009a8a  mov     rcx, rax; this
0x180009a8d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009a92  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009a96  test    r9, r9
0x180009a99  jz      short loc_180009AAD
0x180009a9b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009aa2  mov     rdx, rsi; unsigned __int16 *
0x180009aa5  mov     rcx, rax; this
0x180009aa8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009aad  mov     rcx, [rbx+28h]
0x180009ab1  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009ab5  mov     rdx, rsi; unsigned __int16 *
0x180009ab8  test    rcx, rcx
0x180009abb  jz      short loc_180009AD3
0x180009abd  mov     [rsp+278h+lpBuffer], rcx
0x180009ac2  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009ac9  mov     rcx, rax; this
0x180009acc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009ad1  jmp     short loc_180009AF5
0x180009ad3  mov     rcx, rax; this
0x180009ad6  test    r9, r9
0x180009ad9  jz      short loc_180009AE9
0x180009adb  lea     r8, aHs; "[%hs]\n"
0x180009ae2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009ae7  jmp     short loc_180009AF5
0x180009ae9  lea     r8, asc_180024218; "\n"
0x180009af0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009af5  xor     eax, eax
0x180009af7  mov     rcx, [rsp+278h+var_38]
0x180009aff  xor     rcx, rsp; StackCookie
0x180009b02  call    __security_check_cookie
0x180009b07  mov     rbx, [rsp+278h+arg_18]
0x180009b0f  add     rsp, 250h
0x180009b16  pop     r15
0x180009b18  pop     r14
0x180009b1a  pop     rdi
0x180009b1b  pop     rsi
0x180009b1c  pop     rbp
0x180009b1d  retn
```
