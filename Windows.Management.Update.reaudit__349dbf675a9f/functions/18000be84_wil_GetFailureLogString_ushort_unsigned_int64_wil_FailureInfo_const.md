# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000be84`
- end: `0x18000c145`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180009320`
- `0x18000959c`
- `0x18000ca04`
- `0x180010890`
- `0x1800185c8`

## callees

- `0x180002880`
- `0x1800035cc`
- `0x18000be84`
- `0x18000cd1c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c03b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c03b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bfb4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bfb4`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rdi
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
  v7 = (const char *)&byte_180030C41;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
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
0x18000be84  mov     [rsp+arg_18], rbx
0x18000be89  push    rbp
0x18000be8a  push    rsi
0x18000be8b  push    rdi
0x18000be8c  push    r14
0x18000be8e  push    r15
0x18000be90  sub     rsp, 250h
0x18000be97  mov     rax, cs:__security_cookie
0x18000be9e  xor     rax, rsp
0x18000bea1  mov     [rsp+278h+var_38], rax
0x18000bea9  mov     rbx, r8
0x18000beac  mov     rdi, rdx
0x18000beaf  mov     r14, rcx
0x18000beb2  xor     r15d, r15d
0x18000beb5  test    rdx, rdx
0x18000beb8  jz      loc_18000C11B
0x18000bebe  test    rcx, rcx
0x18000bec1  jz      loc_18000C11B
0x18000bec7  mov     [rcx], r15w
0x18000becb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bed2  test    rax, rax
0x18000bed5  jz      short loc_18000BEF8
0x18000bed7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000bede  jz      short loc_18000BEF8
0x18000bee0  mov     r8, rdx
0x18000bee3  mov     rdx, rcx
0x18000bee6  mov     rcx, rbx
0x18000bee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beee  cmp     [r14], r15w
0x18000bef2  jnz     loc_18000C11B
0x18000bef8  lea     rsi, byte_180030C41
0x18000beff  mov     ecx, [rbx]
0x18000bf01  mov     bpl, 8
0x18000bf04  test    ecx, ecx
0x18000bf06  jz      short loc_18000BF48
0x18000bf08  sub     ecx, 1
0x18000bf0b  jz      short loc_18000BF30
0x18000bf0d  sub     ecx, 1
0x18000bf10  jz      short loc_18000BF20
0x18000bf12  cmp     ecx, 1
0x18000bf15  jnz     short loc_18000BF4F
0x18000bf17  lea     rsi, aFailfast; "FailFast"
0x18000bf1e  jmp     short loc_18000BF4F
0x18000bf20  lea     rax, aLoghr; "LogHr"
0x18000bf27  lea     rsi, aLognt; "LogNt"
0x18000bf2e  jmp     short loc_18000BF3E
0x18000bf30  lea     rax, aReturnhr; "ReturnHr"
0x18000bf37  lea     rsi, aReturnnt; "ReturnNt"
0x18000bf3e  test    [rbx+4], bpl
0x18000bf42  cmovz   rsi, rax
0x18000bf46  jmp     short loc_18000BF4F
0x18000bf48  lea     rsi, aException; "Exception"
0x18000bf4f  xor     edx, edx; Val
0x18000bf51  mov     r8d, 200h; Size
0x18000bf57  lea     rcx, [rsp+278h+Buffer]; void *
0x18000bf5c  call    memset_0
0x18000bf61  test    [rbx+4], bpl
0x18000bf65  jz      short loc_18000BF8A
0x18000bf67  mov     ebp, [rbx+0Ch]
0x18000bf6a  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000bf71  test    rax, rax
0x18000bf74  jz      short loc_18000BFC0
0x18000bf76  mov     r8d, 100h
0x18000bf7c  lea     rdx, [rsp+278h+Buffer]
0x18000bf81  mov     ecx, ebp
0x18000bf83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf88  jmp     short loc_18000BFC0
0x18000bf8a  mov     ebp, [rbx+8]
0x18000bf8d  mov     [rsp+278h+Arguments], r15; Arguments
0x18000bf92  mov     [rsp+278h+nSize], 100h; nSize
0x18000bf9a  lea     rax, [rsp+278h+Buffer]
0x18000bf9f  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000bfa4  mov     r9d, 400h; dwLanguageId
0x18000bfaa  mov     r8d, ebp; dwMessageId
0x18000bfad  xor     edx, edx; lpSource
0x18000bfaf  mov     ecx, 1200h; dwFlags
0x18000bfb4  call    cs:__imp_FormatMessageW
0x18000bfbb  nop     dword ptr [rax+rax+00h]
0x18000bfc0  lea     rdi, [r14+rdi*2]
0x18000bfc4  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000bfc8  mov     rax, [rbx+88h]
0x18000bfcf  mov     rcx, [rbx+80h]
0x18000bfd6  mov     rdx, rdi; unsigned __int16 *
0x18000bfd9  test    r9, r9
0x18000bfdc  jz      short loc_18000C000
0x18000bfde  mov     [rsp+278h+Arguments], rax
0x18000bfe3  mov     qword ptr [rsp+278h+nSize], rcx
0x18000bfe8  mov     eax, [rbx+40h]
0x18000bfeb  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000bfef  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000bff6  mov     rcx, r14; this
0x18000bff9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bffe  jmp     short loc_18000C017
0x18000c000  mov     [rsp+278h+lpBuffer], rax
0x18000c005  mov     r9, rcx; unsigned __int16 *
0x18000c008  lea     r8, aHsP; "%hs!%p: "
0x18000c00f  mov     rcx, r14; this
0x18000c012  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c017  mov     r14, rax
0x18000c01a  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000c021  test    r9, r9
0x18000c024  jz      short loc_18000C03B
0x18000c026  lea     r8, aCallerP; "(caller: %p) "
0x18000c02d  mov     rdx, rdi; unsigned __int16 *
0x18000c030  mov     rcx, rax; this
0x18000c033  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c038  mov     r14, rax
0x18000c03b  call    cs:__imp_GetCurrentThreadId
0x18000c042  nop     dword ptr [rax+rax+00h]
0x18000c047  mov     ecx, [rbx+44h]
0x18000c04a  lea     rdx, [rsp+278h+Buffer]
0x18000c04f  mov     [rsp+278h+var_240], rdx
0x18000c054  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000c058  mov     [rsp+278h+nSize], eax
0x18000c05c  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x18000c060  mov     r9, rsi; unsigned __int16 *
0x18000c063  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000c06a  mov     rdx, rdi; unsigned __int16 *
0x18000c06d  mov     rcx, r14; this
0x18000c070  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c075  cmp     [rbx+18h], r15
0x18000c079  jnz     short loc_18000C08B
0x18000c07b  cmp     [rbx+48h], r15
0x18000c07f  jnz     short loc_18000C08B
0x18000c081  cmp     [rbx+30h], r15
0x18000c085  jz      loc_18000C11B
0x18000c08b  lea     r8, asc_180030D48; "    "
0x18000c092  mov     rdx, rdi; unsigned __int16 *
0x18000c095  mov     rcx, rax; this
0x18000c098  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c09d  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000c0a1  test    r9, r9
0x18000c0a4  jz      short loc_18000C0B8
0x18000c0a6  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000c0ad  mov     rdx, rdi; unsigned __int16 *
0x18000c0b0  mov     rcx, rax; this
0x18000c0b3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c0b8  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000c0bc  test    r9, r9
0x18000c0bf  jz      short loc_18000C0D3
0x18000c0c1  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000c0c8  mov     rdx, rdi; unsigned __int16 *
0x18000c0cb  mov     rcx, rax; this
0x18000c0ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c0d3  mov     rcx, [rbx+28h]
0x18000c0d7  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000c0db  mov     rdx, rdi; unsigned __int16 *
0x18000c0de  test    rcx, rcx
0x18000c0e1  jz      short loc_18000C0F9
0x18000c0e3  mov     [rsp+278h+lpBuffer], rcx
0x18000c0e8  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000c0ef  mov     rcx, rax; this
0x18000c0f2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c0f7  jmp     short loc_18000C11B
0x18000c0f9  mov     rcx, rax; this
0x18000c0fc  test    r9, r9
0x18000c0ff  jz      short loc_18000C10F
0x18000c101  lea     r8, aHs; "[%hs]\n"
0x18000c108  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c10d  jmp     short loc_18000C11B
0x18000c10f  lea     r8, asc_180030DC0; "\n"
0x18000c116  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c11b  xor     eax, eax
0x18000c11d  mov     rcx, [rsp+278h+var_38]
0x18000c125  xor     rcx, rsp; StackCookie
0x18000c128  call    __security_check_cookie
0x18000c12d  mov     rbx, [rsp+278h+arg_18]
0x18000c135  add     rsp, 250h
0x18000c13c  pop     r15
0x18000c13e  pop     r14
0x18000c140  pop     rdi
0x18000c141  pop     rsi
0x18000c142  pop     rbp
0x18000c143  retn
```
