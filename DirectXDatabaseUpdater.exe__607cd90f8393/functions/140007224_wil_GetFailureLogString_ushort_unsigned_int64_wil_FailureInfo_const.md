# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140007224`
- end: `0x1400074da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140004828`
- `0x140008600`
- `0x140008ce0`
- `0x14000eb60`

## callees

- `0x140002f40`
- `0x140003ab8`
- `0x140007224`
- `0x140008900`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400073d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400073d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140007356`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140007356`

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
          v7 = (const char *)&byte_14001C2F5;
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
0x140007224  mov     [rsp+arg_18], rbx
0x140007229  push    rbp
0x14000722a  push    rsi
0x14000722b  push    rdi
0x14000722c  push    r14
0x14000722e  push    r15
0x140007230  sub     rsp, 250h
0x140007237  mov     rax, cs:__security_cookie
0x14000723e  xor     rax, rsp
0x140007241  mov     [rsp+278h+var_38], rax
0x140007249  mov     rbx, r8
0x14000724c  mov     rsi, rdx
0x14000724f  mov     r14, rcx
0x140007252  xor     r15d, r15d
0x140007255  test    rdx, rdx
0x140007258  jz      loc_1400074B1
0x14000725e  test    rcx, rcx
0x140007261  jz      loc_1400074B1
0x140007267  mov     [rcx], r15w
0x14000726b  mov     rax, cs:g_pfnResultLoggingCallback
0x140007272  test    rax, rax
0x140007275  jz      short loc_140007298
0x140007277  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000727e  jz      short loc_140007298
0x140007280  mov     r8, rdx
0x140007283  mov     rdx, rcx
0x140007286  mov     rcx, rbx
0x140007289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000728e  cmp     [r14], r15w
0x140007292  jnz     loc_1400074B1
0x140007298  mov     ecx, [rbx]
0x14000729a  mov     bpl, 8
0x14000729d  test    ecx, ecx
0x14000729f  jz      short loc_1400072EA
0x1400072a1  sub     ecx, 1
0x1400072a4  jz      short loc_1400072D2
0x1400072a6  sub     ecx, 1
0x1400072a9  jz      short loc_1400072C2
0x1400072ab  cmp     ecx, 1
0x1400072ae  jz      short loc_1400072B9
0x1400072b0  lea     rdi, byte_14001C2F5
0x1400072b7  jmp     short loc_1400072F1
0x1400072b9  lea     rdi, aFailfast; "FailFast"
0x1400072c0  jmp     short loc_1400072F1
0x1400072c2  lea     rax, aLoghr; "LogHr"
0x1400072c9  lea     rdi, aLognt; "LogNt"
0x1400072d0  jmp     short loc_1400072E0
0x1400072d2  lea     rax, aReturnhr; "ReturnHr"
0x1400072d9  lea     rdi, aReturnnt; "ReturnNt"
0x1400072e0  test    [rbx+4], bpl
0x1400072e4  cmovz   rdi, rax
0x1400072e8  jmp     short loc_1400072F1
0x1400072ea  lea     rdi, aException; "Exception"
0x1400072f1  xor     edx, edx; Val
0x1400072f3  mov     r8d, 200h; Size
0x1400072f9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400072fe  call    memset_0
0x140007303  test    [rbx+4], bpl
0x140007307  jz      short loc_14000732C
0x140007309  mov     ebp, [rbx+0Ch]
0x14000730c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140007313  test    rax, rax
0x140007316  jz      short loc_14000735C
0x140007318  mov     r8d, 100h
0x14000731e  lea     rdx, [rsp+278h+Buffer]
0x140007323  mov     ecx, ebp
0x140007325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000732a  jmp     short loc_14000735C
0x14000732c  mov     ebp, [rbx+8]
0x14000732f  mov     [rsp+278h+Arguments], r15; Arguments
0x140007334  mov     [rsp+278h+nSize], 100h; nSize
0x14000733c  lea     rax, [rsp+278h+Buffer]
0x140007341  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140007346  mov     r9d, 400h; dwLanguageId
0x14000734c  mov     r8d, ebp; dwMessageId
0x14000734f  xor     edx, edx; lpSource
0x140007351  mov     ecx, 1200h; dwFlags
0x140007356  call    cs:__imp_FormatMessageW
0x14000735c  lea     rsi, [r14+rsi*2]
0x140007360  mov     r9, [rbx+38h]; unsigned __int16 *
0x140007364  mov     rax, [rbx+88h]
0x14000736b  mov     rcx, [rbx+80h]
0x140007372  mov     rdx, rsi; unsigned __int16 *
0x140007375  test    r9, r9
0x140007378  jz      short loc_14000739C
0x14000737a  mov     [rsp+278h+Arguments], rax
0x14000737f  mov     qword ptr [rsp+278h+nSize], rcx
0x140007384  mov     eax, [rbx+40h]
0x140007387  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000738b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140007392  mov     rcx, r14; this
0x140007395  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000739a  jmp     short loc_1400073B3
0x14000739c  mov     [rsp+278h+lpBuffer], rax
0x1400073a1  mov     r9, rcx; unsigned __int16 *
0x1400073a4  lea     r8, aHsP; "%hs!%p: "
0x1400073ab  mov     rcx, r14; this
0x1400073ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400073b3  mov     r14, rax
0x1400073b6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400073bd  test    r9, r9
0x1400073c0  jz      short loc_1400073D7
0x1400073c2  lea     r8, aCallerP; "(caller: %p) "
0x1400073c9  mov     rdx, rsi; unsigned __int16 *
0x1400073cc  mov     rcx, rax; this
0x1400073cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400073d4  mov     r14, rax
0x1400073d7  call    cs:__imp_GetCurrentThreadId
0x1400073dd  lea     rcx, [rsp+278h+Buffer]
0x1400073e2  mov     [rsp+278h+var_240], rcx
0x1400073e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400073eb  mov     [rsp+278h+nSize], eax
0x1400073ef  mov     eax, [rbx+44h]
0x1400073f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400073f6  mov     r9, rdi; unsigned __int16 *
0x1400073f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140007400  mov     rdx, rsi; unsigned __int16 *
0x140007403  mov     rcx, r14; this
0x140007406  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000740b  cmp     [rbx+18h], r15
0x14000740f  jnz     short loc_140007421
0x140007411  cmp     [rbx+48h], r15
0x140007415  jnz     short loc_140007421
0x140007417  cmp     [rbx+30h], r15
0x14000741b  jz      loc_1400074B1
0x140007421  lea     r8, asc_14001C418; "    "
0x140007428  mov     rdx, rsi; unsigned __int16 *
0x14000742b  mov     rcx, rax; this
0x14000742e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007433  mov     r9, [rbx+18h]; unsigned __int16 *
0x140007437  test    r9, r9
0x14000743a  jz      short loc_14000744E
0x14000743c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140007443  mov     rdx, rsi; unsigned __int16 *
0x140007446  mov     rcx, rax; this
0x140007449  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000744e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140007452  test    r9, r9
0x140007455  jz      short loc_140007469
0x140007457  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000745e  mov     rdx, rsi; unsigned __int16 *
0x140007461  mov     rcx, rax; this
0x140007464  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140007469  mov     rcx, [rbx+28h]
0x14000746d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140007471  mov     rdx, rsi; unsigned __int16 *
0x140007474  test    rcx, rcx
0x140007477  jz      short loc_14000748F
0x140007479  mov     [rsp+278h+lpBuffer], rcx
0x14000747e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140007485  mov     rcx, rax; this
0x140007488  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000748d  jmp     short loc_1400074B1
0x14000748f  mov     rcx, rax; this
0x140007492  test    r9, r9
0x140007495  jz      short loc_1400074A5
0x140007497  lea     r8, aHs; "[%hs]\n"
0x14000749e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400074a3  jmp     short loc_1400074B1
0x1400074a5  lea     r8, asc_14001C490; "\n"
0x1400074ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400074b1  xor     eax, eax
0x1400074b3  mov     rcx, [rsp+278h+var_38]
0x1400074bb  xor     rcx, rsp; StackCookie
0x1400074be  call    __security_check_cookie
0x1400074c3  mov     rbx, [rsp+278h+arg_18]
0x1400074cb  add     rsp, 250h
0x1400074d2  pop     r15
0x1400074d4  pop     r14
0x1400074d6  pop     rdi
0x1400074d7  pop     rsi
0x1400074d8  pop     rbp
0x1400074d9  retn
```
