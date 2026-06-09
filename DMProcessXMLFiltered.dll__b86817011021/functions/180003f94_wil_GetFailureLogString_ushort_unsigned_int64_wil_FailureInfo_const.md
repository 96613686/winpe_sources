# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003f94`
- end: `0x18000424a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180002938`
- `0x180002bb8`
- `0x1800048f8`
- `0x180006130`
- `0x180006da3`
- `0x180006ed7`

## callees

- `0x180001520`
- `0x180001e5a`
- `0x180003f94`
- `0x180004bf8`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004147`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004147`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800040c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800040c6`

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
          v7 = (const char *)&word_18000970A;
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
0x180003f94  mov     [rsp+arg_18], rbx
0x180003f99  push    rbp
0x180003f9a  push    rsi
0x180003f9b  push    rdi
0x180003f9c  push    r14
0x180003f9e  push    r15
0x180003fa0  sub     rsp, 250h
0x180003fa7  mov     rax, cs:__security_cookie
0x180003fae  xor     rax, rsp
0x180003fb1  mov     [rsp+278h+var_38], rax
0x180003fb9  mov     rbx, r8
0x180003fbc  mov     rsi, rdx
0x180003fbf  mov     r14, rcx
0x180003fc2  xor     r15d, r15d
0x180003fc5  test    rdx, rdx
0x180003fc8  jz      loc_180004221
0x180003fce  test    rcx, rcx
0x180003fd1  jz      loc_180004221
0x180003fd7  mov     [rcx], r15w
0x180003fdb  mov     rax, cs:g_pfnResultLoggingCallback
0x180003fe2  test    rax, rax
0x180003fe5  jz      short loc_180004008
0x180003fe7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003fee  jz      short loc_180004008
0x180003ff0  mov     r8, rdx
0x180003ff3  mov     rdx, rcx
0x180003ff6  mov     rcx, rbx
0x180003ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ffe  cmp     [r14], r15w
0x180004002  jnz     loc_180004221
0x180004008  mov     ecx, [rbx]
0x18000400a  mov     bpl, 8
0x18000400d  test    ecx, ecx
0x18000400f  jz      short loc_18000405A
0x180004011  sub     ecx, 1
0x180004014  jz      short loc_180004042
0x180004016  sub     ecx, 1
0x180004019  jz      short loc_180004032
0x18000401b  cmp     ecx, 1
0x18000401e  jz      short loc_180004029
0x180004020  lea     rdi, word_18000970A
0x180004027  jmp     short loc_180004061
0x180004029  lea     rdi, aFailfast; "FailFast"
0x180004030  jmp     short loc_180004061
0x180004032  lea     rax, aLoghr; "LogHr"
0x180004039  lea     rdi, aLognt; "LogNt"
0x180004040  jmp     short loc_180004050
0x180004042  lea     rax, aReturnhr; "ReturnHr"
0x180004049  lea     rdi, aReturnnt; "ReturnNt"
0x180004050  test    [rbx+4], bpl
0x180004054  cmovz   rdi, rax
0x180004058  jmp     short loc_180004061
0x18000405a  lea     rdi, aException; "Exception"
0x180004061  xor     edx, edx; Val
0x180004063  mov     r8d, 200h; Size
0x180004069  lea     rcx, [rsp+278h+Buffer]; void *
0x18000406e  call    memset_0
0x180004073  test    [rbx+4], bpl
0x180004077  jz      short loc_18000409C
0x180004079  mov     ebp, [rbx+0Ch]
0x18000407c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004083  test    rax, rax
0x180004086  jz      short loc_1800040CC
0x180004088  mov     r8d, 100h
0x18000408e  lea     rdx, [rsp+278h+Buffer]
0x180004093  mov     ecx, ebp
0x180004095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000409a  jmp     short loc_1800040CC
0x18000409c  mov     ebp, [rbx+8]
0x18000409f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800040a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800040ac  lea     rax, [rsp+278h+Buffer]
0x1800040b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800040b6  mov     r9d, 400h; dwLanguageId
0x1800040bc  mov     r8d, ebp; dwMessageId
0x1800040bf  xor     edx, edx; lpSource
0x1800040c1  mov     ecx, 1200h; dwFlags
0x1800040c6  call    cs:__imp_FormatMessageW
0x1800040cc  lea     rsi, [r14+rsi*2]
0x1800040d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800040d4  mov     rax, [rbx+88h]
0x1800040db  mov     rcx, [rbx+80h]
0x1800040e2  mov     rdx, rsi; unsigned __int16 *
0x1800040e5  test    r9, r9
0x1800040e8  jz      short loc_18000410C
0x1800040ea  mov     [rsp+278h+Arguments], rax
0x1800040ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800040f4  mov     eax, [rbx+40h]
0x1800040f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800040fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004102  mov     rcx, r14; this
0x180004105  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000410a  jmp     short loc_180004123
0x18000410c  mov     [rsp+278h+lpBuffer], rax
0x180004111  mov     r9, rcx; unsigned __int16 *
0x180004114  lea     r8, aHsP; "%hs!%p: "
0x18000411b  mov     rcx, r14; this
0x18000411e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004123  mov     r14, rax
0x180004126  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000412d  test    r9, r9
0x180004130  jz      short loc_180004147
0x180004132  lea     r8, aCallerP; "(caller: %p) "
0x180004139  mov     rdx, rsi; unsigned __int16 *
0x18000413c  mov     rcx, rax; this
0x18000413f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004144  mov     r14, rax
0x180004147  call    cs:__imp_GetCurrentThreadId
0x18000414d  lea     rcx, [rsp+278h+Buffer]
0x180004152  mov     [rsp+278h+var_240], rcx
0x180004157  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000415b  mov     [rsp+278h+nSize], eax
0x18000415f  mov     eax, [rbx+44h]
0x180004162  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004166  mov     r9, rdi; unsigned __int16 *
0x180004169  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004170  mov     rdx, rsi; unsigned __int16 *
0x180004173  mov     rcx, r14; this
0x180004176  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000417b  cmp     [rbx+18h], r15
0x18000417f  jnz     short loc_180004191
0x180004181  cmp     [rbx+48h], r15
0x180004185  jnz     short loc_180004191
0x180004187  cmp     [rbx+30h], r15
0x18000418b  jz      loc_180004221
0x180004191  lea     r8, asc_1800097F8; "    "
0x180004198  mov     rdx, rsi; unsigned __int16 *
0x18000419b  mov     rcx, rax; this
0x18000419e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800041a7  test    r9, r9
0x1800041aa  jz      short loc_1800041BE
0x1800041ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800041b3  mov     rdx, rsi; unsigned __int16 *
0x1800041b6  mov     rcx, rax; this
0x1800041b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800041c2  test    r9, r9
0x1800041c5  jz      short loc_1800041D9
0x1800041c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800041ce  mov     rdx, rsi; unsigned __int16 *
0x1800041d1  mov     rcx, rax; this
0x1800041d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041d9  mov     rcx, [rbx+28h]
0x1800041dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800041e1  mov     rdx, rsi; unsigned __int16 *
0x1800041e4  test    rcx, rcx
0x1800041e7  jz      short loc_1800041FF
0x1800041e9  mov     [rsp+278h+lpBuffer], rcx
0x1800041ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800041f5  mov     rcx, rax; this
0x1800041f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041fd  jmp     short loc_180004221
0x1800041ff  mov     rcx, rax; this
0x180004202  test    r9, r9
0x180004205  jz      short loc_180004215
0x180004207  lea     r8, aHs; "[%hs]\n"
0x18000420e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004213  jmp     short loc_180004221
0x180004215  lea     r8, asc_180009870; "\n"
0x18000421c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004221  xor     eax, eax
0x180004223  mov     rcx, [rsp+278h+var_38]
0x18000422b  xor     rcx, rsp; StackCookie
0x18000422e  call    __security_check_cookie
0x180004233  mov     rbx, [rsp+278h+arg_18]
0x18000423b  add     rsp, 250h
0x180004242  pop     r15
0x180004244  pop     r14
0x180004246  pop     rdi
0x180004247  pop     rsi
0x180004248  pop     rbp
0x180004249  retn
```
