# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004074`
- end: `0x18000432a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002ce4`
- `0x180002f64`
- `0x1800049c4`
- `0x1800061c0`
- `0x1800067fc`
- `0x180011f03`
- `0x180012037`

## callees

- `0x180001960`
- `0x1800022ea`
- `0x180004074`
- `0x180004cc4`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004227`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800041a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800041a6`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&word_1800150F1;
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
0x180004074  mov     [rsp+arg_18], rbx
0x180004079  push    rbp
0x18000407a  push    rsi
0x18000407b  push    rdi
0x18000407c  push    r14
0x18000407e  push    r15
0x180004080  sub     rsp, 250h
0x180004087  mov     rax, cs:__security_cookie
0x18000408e  xor     rax, rsp
0x180004091  mov     [rsp+278h+var_38], rax
0x180004099  mov     rbx, r8
0x18000409c  mov     rsi, rdx
0x18000409f  mov     r14, rcx
0x1800040a2  xor     r15d, r15d
0x1800040a5  test    rdx, rdx
0x1800040a8  jz      loc_180004301
0x1800040ae  test    rcx, rcx
0x1800040b1  jz      loc_180004301
0x1800040b7  mov     [rcx], r15w
0x1800040bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800040c2  test    rax, rax
0x1800040c5  jz      short loc_1800040E8
0x1800040c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800040ce  jz      short loc_1800040E8
0x1800040d0  mov     r8, rdx
0x1800040d3  mov     rdx, rcx
0x1800040d6  mov     rcx, rbx
0x1800040d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040de  cmp     [r14], r15w
0x1800040e2  jnz     loc_180004301
0x1800040e8  mov     ecx, [rbx]
0x1800040ea  mov     bpl, 8
0x1800040ed  test    ecx, ecx
0x1800040ef  jz      short loc_18000413A
0x1800040f1  sub     ecx, 1
0x1800040f4  jz      short loc_180004122
0x1800040f6  sub     ecx, 1
0x1800040f9  jz      short loc_180004112
0x1800040fb  cmp     ecx, 1
0x1800040fe  jz      short loc_180004109
0x180004100  lea     rdi, word_1800150F1
0x180004107  jmp     short loc_180004141
0x180004109  lea     rdi, aFailfast; "FailFast"
0x180004110  jmp     short loc_180004141
0x180004112  lea     rax, aLoghr; "LogHr"
0x180004119  lea     rdi, aLognt; "LogNt"
0x180004120  jmp     short loc_180004130
0x180004122  lea     rax, aReturnhr; "ReturnHr"
0x180004129  lea     rdi, aReturnnt; "ReturnNt"
0x180004130  test    [rbx+4], bpl
0x180004134  cmovz   rdi, rax
0x180004138  jmp     short loc_180004141
0x18000413a  lea     rdi, aException; "Exception"
0x180004141  xor     edx, edx; Val
0x180004143  mov     r8d, 200h; Size
0x180004149  lea     rcx, [rsp+278h+Buffer]; void *
0x18000414e  call    memset_0
0x180004153  test    [rbx+4], bpl
0x180004157  jz      short loc_18000417C
0x180004159  mov     ebp, [rbx+0Ch]
0x18000415c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004163  test    rax, rax
0x180004166  jz      short loc_1800041AC
0x180004168  mov     r8d, 100h
0x18000416e  lea     rdx, [rsp+278h+Buffer]
0x180004173  mov     ecx, ebp
0x180004175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000417a  jmp     short loc_1800041AC
0x18000417c  mov     ebp, [rbx+8]
0x18000417f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004184  mov     [rsp+278h+nSize], 100h; nSize
0x18000418c  lea     rax, [rsp+278h+Buffer]
0x180004191  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004196  mov     r9d, 400h; dwLanguageId
0x18000419c  mov     r8d, ebp; dwMessageId
0x18000419f  xor     edx, edx; lpSource
0x1800041a1  mov     ecx, 1200h; dwFlags
0x1800041a6  call    cs:__imp_FormatMessageW
0x1800041ac  lea     rsi, [r14+rsi*2]
0x1800041b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800041b4  mov     rax, [rbx+88h]
0x1800041bb  mov     rcx, [rbx+80h]
0x1800041c2  mov     rdx, rsi; unsigned __int16 *
0x1800041c5  test    r9, r9
0x1800041c8  jz      short loc_1800041EC
0x1800041ca  mov     [rsp+278h+Arguments], rax
0x1800041cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800041d4  mov     eax, [rbx+40h]
0x1800041d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800041db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800041e2  mov     rcx, r14; this
0x1800041e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041ea  jmp     short loc_180004203
0x1800041ec  mov     [rsp+278h+lpBuffer], rax
0x1800041f1  mov     r9, rcx; unsigned __int16 *
0x1800041f4  lea     r8, aHsP; "%hs!%p: "
0x1800041fb  mov     rcx, r14; this
0x1800041fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004203  mov     r14, rax
0x180004206  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000420d  test    r9, r9
0x180004210  jz      short loc_180004227
0x180004212  lea     r8, aCallerP; "(caller: %p) "
0x180004219  mov     rdx, rsi; unsigned __int16 *
0x18000421c  mov     rcx, rax; this
0x18000421f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004224  mov     r14, rax
0x180004227  call    cs:__imp_GetCurrentThreadId
0x18000422d  lea     rcx, [rsp+278h+Buffer]
0x180004232  mov     [rsp+278h+var_240], rcx
0x180004237  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000423b  mov     [rsp+278h+nSize], eax
0x18000423f  mov     eax, [rbx+44h]
0x180004242  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004246  mov     r9, rdi; unsigned __int16 *
0x180004249  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004250  mov     rdx, rsi; unsigned __int16 *
0x180004253  mov     rcx, r14; this
0x180004256  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000425b  cmp     [rbx+18h], r15
0x18000425f  jnz     short loc_180004271
0x180004261  cmp     [rbx+48h], r15
0x180004265  jnz     short loc_180004271
0x180004267  cmp     [rbx+30h], r15
0x18000426b  jz      loc_180004301
0x180004271  lea     r8, asc_1800151F8; "    "
0x180004278  mov     rdx, rsi; unsigned __int16 *
0x18000427b  mov     rcx, rax; this
0x18000427e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004283  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004287  test    r9, r9
0x18000428a  jz      short loc_18000429E
0x18000428c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004293  mov     rdx, rsi; unsigned __int16 *
0x180004296  mov     rcx, rax; this
0x180004299  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000429e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800042a2  test    r9, r9
0x1800042a5  jz      short loc_1800042B9
0x1800042a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800042ae  mov     rdx, rsi; unsigned __int16 *
0x1800042b1  mov     rcx, rax; this
0x1800042b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800042b9  mov     rcx, [rbx+28h]
0x1800042bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800042c1  mov     rdx, rsi; unsigned __int16 *
0x1800042c4  test    rcx, rcx
0x1800042c7  jz      short loc_1800042DF
0x1800042c9  mov     [rsp+278h+lpBuffer], rcx
0x1800042ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800042d5  mov     rcx, rax; this
0x1800042d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800042dd  jmp     short loc_180004301
0x1800042df  mov     rcx, rax; this
0x1800042e2  test    r9, r9
0x1800042e5  jz      short loc_1800042F5
0x1800042e7  lea     r8, aHs; "[%hs]\n"
0x1800042ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800042f3  jmp     short loc_180004301
0x1800042f5  lea     r8, asc_180015270; "\n"
0x1800042fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004301  xor     eax, eax
0x180004303  mov     rcx, [rsp+278h+var_38]
0x18000430b  xor     rcx, rsp; StackCookie
0x18000430e  call    __security_check_cookie
0x180004313  mov     rbx, [rsp+278h+arg_18]
0x18000431b  add     rsp, 250h
0x180004322  pop     r15
0x180004324  pop     r14
0x180004326  pop     rdi
0x180004327  pop     rsi
0x180004328  pop     rbp
0x180004329  retn
```
