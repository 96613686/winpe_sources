# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001f9d8`
- end: `0x18001fc99`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800119d4`

## callees

- `0x18001f9d8`
- `0x180020128`
- `0x1800444ba`
- `0x1800444e0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fb8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fb8f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001fb08`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001fb08`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rsi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdi
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
  v8 = (const char *)&word_18004A3E8;
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
        goto LABEL_17;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_17;
  }
  v8 = "Exception";
LABEL_17:
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
0x18001f9d8  mov     [rsp+arg_18], rbx
0x18001f9dd  push    rbp
0x18001f9de  push    rsi
0x18001f9df  push    rdi
0x18001f9e0  push    r14
0x18001f9e2  push    r15
0x18001f9e4  sub     rsp, 250h
0x18001f9eb  mov     rax, cs:__security_cookie
0x18001f9f2  xor     rax, rsp
0x18001f9f5  mov     [rsp+278h+var_38], rax
0x18001f9fd  xor     r15d, r15d
0x18001fa00  mov     rbx, r8
0x18001fa03  mov     rdi, rdx
0x18001fa06  mov     r14, rcx
0x18001fa09  test    rdx, rdx
0x18001fa0c  jz      loc_18001FC6F
0x18001fa12  test    rcx, rcx
0x18001fa15  jz      loc_18001FC6F
0x18001fa1b  mov     rax, cs:g_pfnResultLoggingCallback
0x18001fa22  mov     [rcx], r15w
0x18001fa26  test    rax, rax
0x18001fa29  jz      short loc_18001FA4C
0x18001fa2b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001fa32  jz      short loc_18001FA4C
0x18001fa34  mov     r8, rdx
0x18001fa37  mov     rdx, rcx
0x18001fa3a  mov     rcx, rbx
0x18001fa3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa42  cmp     [r14], r15w
0x18001fa46  jnz     loc_18001FC6F
0x18001fa4c  mov     ecx, [rbx]
0x18001fa4e  lea     rsi, word_18004A3E8
0x18001fa55  mov     bpl, 8
0x18001fa58  test    ecx, ecx
0x18001fa5a  jz      short loc_18001FA9C
0x18001fa5c  sub     ecx, 1
0x18001fa5f  jz      short loc_18001FA84
0x18001fa61  sub     ecx, 1
0x18001fa64  jz      short loc_18001FA74
0x18001fa66  cmp     ecx, 1
0x18001fa69  jnz     short loc_18001FAA3
0x18001fa6b  lea     rsi, aFailfast; "FailFast"
0x18001fa72  jmp     short loc_18001FAA3
0x18001fa74  lea     rax, aLoghr; "LogHr"
0x18001fa7b  lea     rsi, aLognt; "LogNt"
0x18001fa82  jmp     short loc_18001FA92
0x18001fa84  lea     rax, aReturnhr; "ReturnHr"
0x18001fa8b  lea     rsi, aReturnnt; "ReturnNt"
0x18001fa92  test    [rbx+4], bpl
0x18001fa96  cmovz   rsi, rax
0x18001fa9a  jmp     short loc_18001FAA3
0x18001fa9c  lea     rsi, aException; "Exception"
0x18001faa3  xor     edx, edx; Val
0x18001faa5  lea     rcx, [rsp+278h+Buffer]; void *
0x18001faaa  mov     r8d, 200h; Size
0x18001fab0  call    memset_0
0x18001fab5  test    [rbx+4], bpl
0x18001fab9  jz      short loc_18001FADE
0x18001fabb  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001fac2  mov     ebp, [rbx+0Ch]
0x18001fac5  test    rax, rax
0x18001fac8  jz      short loc_18001FB14
0x18001faca  mov     r8d, 100h
0x18001fad0  lea     rdx, [rsp+278h+Buffer]
0x18001fad5  mov     ecx, ebp
0x18001fad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fadc  jmp     short loc_18001FB14
0x18001fade  mov     ebp, [rbx+8]
0x18001fae1  lea     rax, [rsp+278h+Buffer]
0x18001fae6  mov     [rsp+278h+Arguments], r15; Arguments
0x18001faeb  mov     r8d, ebp; dwMessageId
0x18001faee  mov     [rsp+278h+nSize], 100h; nSize
0x18001faf6  mov     r9d, 400h; dwLanguageId
0x18001fafc  xor     edx, edx; lpSource
0x18001fafe  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001fb03  mov     ecx, 1200h; dwFlags
0x18001fb08  call    cs:__imp_FormatMessageW
0x18001fb0f  nop     dword ptr [rax+rax+00h]
0x18001fb14  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001fb18  lea     rdi, [r14+rdi*2]
0x18001fb1c  mov     rax, [rbx+88h]
0x18001fb23  mov     rdx, rdi; unsigned __int16 *
0x18001fb26  mov     rcx, [rbx+80h]
0x18001fb2d  test    r9, r9
0x18001fb30  jz      short loc_18001FB54
0x18001fb32  mov     [rsp+278h+Arguments], rax
0x18001fb37  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001fb3e  mov     eax, [rbx+40h]
0x18001fb41  mov     qword ptr [rsp+278h+nSize], rcx
0x18001fb46  mov     rcx, r14; this
0x18001fb49  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001fb4d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001fb52  jmp     short loc_18001FB6B
0x18001fb54  mov     r9, rcx; unsigned __int16 *
0x18001fb57  mov     [rsp+278h+lpBuffer], rax
0x18001fb5c  mov     rcx, r14; this
0x18001fb5f  lea     r8, aHsP; "%hs!%p: "
0x18001fb66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001fb6b  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001fb72  mov     r14, rax
0x18001fb75  test    r9, r9
0x18001fb78  jz      short loc_18001FB8F
0x18001fb7a  lea     r8, aCallerP; "(caller: %p) "
0x18001fb81  mov     rdx, rdi; unsigned __int16 *
0x18001fb84  mov     rcx, rax; this
0x18001fb87  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001fb8c  mov     r14, rax
0x18001fb8f  call    cs:__imp_GetCurrentThreadId
0x18001fb96  nop     dword ptr [rax+rax+00h]
0x18001fb9b  mov     ecx, [rbx+44h]
0x18001fb9e  lea     rdx, [rsp+278h+Buffer]
0x18001fba3  mov     [rsp+278h+var_240], rdx
0x18001fba8  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001fbaf  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001fbb3  mov     r9, rsi; unsigned __int16 *
0x18001fbb6  mov     [rsp+278h+nSize], eax
0x18001fbba  mov     rdx, rdi; unsigned __int16 *
0x18001fbbd  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x18001fbc1  mov     rcx, r14; this
0x18001fbc4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001fbc9  cmp     [rbx+18h], r15
0x18001fbcd  jnz     short loc_18001FBDF
0x18001fbcf  cmp     [rbx+48h], r15
0x18001fbd3  jnz     short loc_18001FBDF
0x18001fbd5  cmp     [rbx+30h], r15
0x18001fbd9  jz      loc_18001FC6F
0x18001fbdf  lea     r8, asc_18004C2B8; "    "
0x18001fbe6  mov     rdx, rdi; unsigned __int16 *
0x18001fbe9  mov     rcx, rax; this
0x18001fbec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001fbf1  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001fbf5  test    r9, r9
0x18001fbf8  jz      short loc_18001FC0C
0x18001fbfa  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001fc01  mov     rdx, rdi; unsigned __int16 *
0x18001fc04  mov     rcx, rax; this
0x18001fc07  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001fc0c  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001fc10  test    r9, r9
0x18001fc13  jz      short loc_18001FC27
0x18001fc15  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001fc1c  mov     rdx, rdi; unsigned __int16 *
0x18001fc1f  mov     rcx, rax; this
0x18001fc22  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001fc27  mov     rcx, [rbx+28h]
0x18001fc2b  mov     rdx, rdi; unsigned __int16 *
0x18001fc2e  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001fc32  test    rcx, rcx
0x18001fc35  jz      short loc_18001FC4D
0x18001fc37  mov     [rsp+278h+lpBuffer], rcx
0x18001fc3c  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001fc43  mov     rcx, rax; this
0x18001fc46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001fc4b  jmp     short loc_18001FC6F
0x18001fc4d  mov     rcx, rax; this
0x18001fc50  test    r9, r9
0x18001fc53  jz      short loc_18001FC63
0x18001fc55  lea     r8, aHs; "[%hs]\n"
0x18001fc5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001fc61  jmp     short loc_18001FC6F
0x18001fc63  lea     r8, asc_18004C330; "\n"
0x18001fc6a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001fc6f  xor     eax, eax
0x18001fc71  mov     rcx, [rsp+278h+var_38]
0x18001fc79  xor     rcx, rsp; StackCookie
0x18001fc7c  call    __security_check_cookie
0x18001fc81  mov     rbx, [rsp+278h+arg_18]
0x18001fc89  add     rsp, 250h
0x18001fc90  pop     r15
0x18001fc92  pop     r14
0x18001fc94  pop     rdi
0x18001fc95  pop     rsi
0x18001fc96  pop     rbp
0x18001fc97  retn
```
