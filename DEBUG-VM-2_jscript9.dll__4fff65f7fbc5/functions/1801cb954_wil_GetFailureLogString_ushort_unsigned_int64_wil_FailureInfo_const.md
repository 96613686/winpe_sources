# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1801cb954`
- end: `0x1801cbc21`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `717`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1801c9e10`
- `0x1801ccc20`
- `0x1801cd300`
- `0x1801d00a0`

## callees

- `0x1801c989b`
- `0x1801cb954`
- `0x1801ccf74`
- `0x180341dd0`
- `0x18035e010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801cbb1e`
- `KERNEL32!GetCurrentThreadId` at `0x1801cbb1e`
- `KERNEL32!FormatMessageW` at `0x1801cba9d`
- `KERNEL32!FormatMessageW` at `0x1801cba9d`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&dword_1803BC414;
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
                          Buffer,
                          -2);
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
0x1801cb954  mov     r11, rsp
0x1801cb957  mov     [r11+18h], r8
0x1801cb95b  mov     [r11+10h], rdx
0x1801cb95f  mov     [r11+8], rcx
0x1801cb963  push    rbp
0x1801cb964  push    rsi
0x1801cb965  push    rdi
0x1801cb966  push    r14
0x1801cb968  push    r15
0x1801cb96a  sub     rsp, 260h
0x1801cb971  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x1801cb97a  mov     [r11+20h], rbx
0x1801cb97e  mov     rax, cs:__security_cookie
0x1801cb985  xor     rax, rsp
0x1801cb988  mov     [rsp+288h+var_38], rax
0x1801cb990  mov     rbx, r8
0x1801cb993  mov     r14, rcx
0x1801cb996  mov     rsi, rdx
0x1801cb999  xor     r15d, r15d
0x1801cb99c  test    rdx, rdx
0x1801cb99f  jz      loc_1801CBBF8
0x1801cb9a5  test    rcx, rcx
0x1801cb9a8  jz      loc_1801CBBF8
0x1801cb9ae  mov     [rcx], r15w
0x1801cb9b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1801cb9b9  test    rax, rax
0x1801cb9bc  jz      short loc_1801CB9DF
0x1801cb9be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1801cb9c5  jz      short loc_1801CB9DF
0x1801cb9c7  mov     r8, rdx
0x1801cb9ca  mov     rdx, rcx
0x1801cb9cd  mov     rcx, rbx
0x1801cb9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cb9d5  cmp     [r14], r15w
0x1801cb9d9  jnz     loc_1801CBBF8
0x1801cb9df  mov     ecx, [rbx]
0x1801cb9e1  mov     bpl, 8
0x1801cb9e4  test    ecx, ecx
0x1801cb9e6  jz      short loc_1801CBA31
0x1801cb9e8  sub     ecx, 1
0x1801cb9eb  jz      short loc_1801CBA19
0x1801cb9ed  sub     ecx, 1
0x1801cb9f0  jz      short loc_1801CBA09
0x1801cb9f2  cmp     ecx, 1
0x1801cb9f5  jz      short loc_1801CBA00
0x1801cb9f7  lea     rdi, dword_1803BC414
0x1801cb9fe  jmp     short loc_1801CBA38
0x1801cba00  lea     rdi, aFailfast; "FailFast"
0x1801cba07  jmp     short loc_1801CBA38
0x1801cba09  lea     rax, aLoghr; "LogHr"
0x1801cba10  lea     rdi, aLognt; "LogNt"
0x1801cba17  jmp     short loc_1801CBA27
0x1801cba19  lea     rax, aReturnhr; "ReturnHr"
0x1801cba20  lea     rdi, aReturnnt; "ReturnNt"
0x1801cba27  test    [rbx+4], bpl
0x1801cba2b  cmovz   rdi, rax
0x1801cba2f  jmp     short loc_1801CBA38
0x1801cba31  lea     rdi, aException; "Exception"
0x1801cba38  xor     edx, edx; Val
0x1801cba3a  mov     r8d, 200h; Size
0x1801cba40  lea     rcx, [rsp+288h+Buffer]; void *
0x1801cba45  call    memset_0
0x1801cba4a  test    [rbx+4], bpl
0x1801cba4e  jz      short loc_1801CBA73
0x1801cba50  mov     ebp, [rbx+0Ch]
0x1801cba53  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1801cba5a  test    rax, rax
0x1801cba5d  jz      short loc_1801CBAA3
0x1801cba5f  mov     r8d, 100h
0x1801cba65  lea     rdx, [rsp+288h+Buffer]
0x1801cba6a  mov     ecx, ebp
0x1801cba6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cba71  jmp     short loc_1801CBAA3
0x1801cba73  mov     ebp, [rbx+8]
0x1801cba76  mov     [rsp+288h+Arguments], r15; Arguments
0x1801cba7b  mov     [rsp+288h+nSize], 100h; nSize
0x1801cba83  lea     rax, [rsp+288h+Buffer]
0x1801cba88  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x1801cba8d  mov     r9d, 400h; dwLanguageId
0x1801cba93  mov     r8d, ebp; dwMessageId
0x1801cba96  xor     edx, edx; lpSource
0x1801cba98  mov     ecx, 1200h; dwFlags
0x1801cba9d  call    cs:__imp_FormatMessageW
0x1801cbaa3  lea     rsi, [r14+rsi*2]
0x1801cbaa7  mov     r9, [rbx+38h]; unsigned __int16 *
0x1801cbaab  mov     rax, [rbx+88h]
0x1801cbab2  mov     rcx, [rbx+80h]
0x1801cbab9  mov     rdx, rsi; unsigned __int16 *
0x1801cbabc  test    r9, r9
0x1801cbabf  jz      short loc_1801CBAE3
0x1801cbac1  mov     [rsp+288h+Arguments], rax
0x1801cbac6  mov     qword ptr [rsp+288h+nSize], rcx
0x1801cbacb  mov     eax, [rbx+40h]
0x1801cbace  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1801cbad2  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1801cbad9  mov     rcx, r14; this
0x1801cbadc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801cbae1  jmp     short loc_1801CBAFA
0x1801cbae3  mov     [rsp+288h+lpBuffer], rax
0x1801cbae8  mov     r9, rcx; unsigned __int16 *
0x1801cbaeb  lea     r8, aHsP; "%hs!%p: "
0x1801cbaf2  mov     rcx, r14; this
0x1801cbaf5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801cbafa  mov     r14, rax
0x1801cbafd  mov     r9, [rbx+90h]; unsigned __int16 *
0x1801cbb04  test    r9, r9
0x1801cbb07  jz      short loc_1801CBB1E
0x1801cbb09  lea     r8, aCallerP; "(caller: %p) "
0x1801cbb10  mov     rdx, rsi; unsigned __int16 *
0x1801cbb13  mov     rcx, rax; this
0x1801cbb16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801cbb1b  mov     r14, rax
0x1801cbb1e  call    cs:__imp_GetCurrentThreadId
0x1801cbb24  lea     rcx, [rsp+288h+Buffer]
0x1801cbb29  mov     [rsp+288h+var_250], rcx
0x1801cbb2e  mov     dword ptr [rsp+288h+Arguments], ebp
0x1801cbb32  mov     [rsp+288h+nSize], eax
0x1801cbb36  mov     eax, [rbx+44h]
0x1801cbb39  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1801cbb3d  mov     r9, rdi; unsigned __int16 *
0x1801cbb40  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1801cbb47  mov     rdx, rsi; unsigned __int16 *
0x1801cbb4a  mov     rcx, r14; this
0x1801cbb4d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801cbb52  cmp     [rbx+18h], r15
0x1801cbb56  jnz     short loc_1801CBB68
0x1801cbb58  cmp     [rbx+48h], r15
0x1801cbb5c  jnz     short loc_1801CBB68
0x1801cbb5e  cmp     [rbx+30h], r15
0x1801cbb62  jz      loc_1801CBBF8
0x1801cbb68  lea     r8, asc_1803BC500; "    "
0x1801cbb6f  mov     rdx, rsi; unsigned __int16 *
0x1801cbb72  mov     rcx, rax; this
0x1801cbb75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801cbb7a  mov     r9, [rbx+18h]; unsigned __int16 *
0x1801cbb7e  test    r9, r9
0x1801cbb81  jz      short loc_1801CBB95
0x1801cbb83  lea     r8, aMsgWs; "Msg:[%ws] "
0x1801cbb8a  mov     rdx, rsi; unsigned __int16 *
0x1801cbb8d  mov     rcx, rax; this
0x1801cbb90  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801cbb95  mov     r9, [rbx+48h]; unsigned __int16 *
0x1801cbb99  test    r9, r9
0x1801cbb9c  jz      short loc_1801CBBB0
0x1801cbb9e  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1801cbba5  mov     rdx, rsi; unsigned __int16 *
0x1801cbba8  mov     rcx, rax; this
0x1801cbbab  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801cbbb0  mov     rcx, [rbx+28h]
0x1801cbbb4  mov     r9, [rbx+30h]; unsigned __int16 *
0x1801cbbb8  mov     rdx, rsi; unsigned __int16 *
0x1801cbbbb  test    rcx, rcx
0x1801cbbbe  jz      short loc_1801CBBD6
0x1801cbbc0  mov     [rsp+288h+lpBuffer], rcx
0x1801cbbc5  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1801cbbcc  mov     rcx, rax; this
0x1801cbbcf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801cbbd4  jmp     short loc_1801CBBF8
0x1801cbbd6  mov     rcx, rax; this
0x1801cbbd9  test    r9, r9
0x1801cbbdc  jz      short loc_1801CBBEC
0x1801cbbde  lea     r8, aHs; "[%hs]\n"
0x1801cbbe5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801cbbea  jmp     short loc_1801CBBF8
0x1801cbbec  lea     r8, asc_1803BC410; "\n"
0x1801cbbf3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801cbbf8  xor     eax, eax
0x1801cbbfa  mov     rcx, [rsp+288h+var_38]
0x1801cbc02  xor     rcx, rsp; StackCookie
0x1801cbc05  call    __security_check_cookie
0x1801cbc0a  mov     rbx, [rsp+288h+arg_18]
0x1801cbc12  add     rsp, 260h
0x1801cbc19  pop     r15
0x1801cbc1b  pop     r14
0x1801cbc1d  pop     rdi
0x1801cbc1e  pop     rsi
0x1801cbc1f  pop     rbp
0x1801cbc20  retn
```
