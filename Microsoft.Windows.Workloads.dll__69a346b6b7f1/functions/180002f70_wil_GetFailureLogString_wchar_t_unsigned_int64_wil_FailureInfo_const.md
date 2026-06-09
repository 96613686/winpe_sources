# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002f70`
- end: `0x180003230`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `704`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180003230`
- `0x180003680`
- `0x180010a70`
- `0x180013560`
- `0x18002dbe0`
- `0x18003fef0`
- `0x180040018`
- `0x180040180`
- `0x180040371`

## callees

- `0x180002ef0`
- `0x180002f70`
- `0x180034ef0`
- `0x18003bed0`
- `0x18003c6e0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800030a8`
- `KERNEL32!FormatMessageW` at `0x1800030a8`
- `KERNEL32!GetCurrentThreadId` at `0x180003129`
- `KERNEL32!GetCurrentThreadId` at `0x180003129`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  DWORD v8; // r15d
  wchar_t *v9; // rsi
  const wchar_t *v10; // r9
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  wchar_t *v13; // rax
  wil::details *v14; // rbp
  const wchar_t *v15; // r9
  wil::details *v16; // rax
  const wchar_t *v17; // r9
  wchar_t *v18; // rax
  const wchar_t *v19; // r9
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( a2 )
  {
    if ( this )
    {
      *(_WORD *)this = 0;
      if ( !g_pfnResultLoggingCallback
        || !wil::details::g_resultMessageCallbackSet
        || (g_pfnResultLoggingCallback(a3, this, a2), !*(_WORD *)this) )
      {
        v7 = (const char *)&qword_180047B28;
        if ( *(_DWORD *)a3 )
        {
          switch ( *(_DWORD *)a3 )
          {
            case 1:
              v7 = "ReturnNt";
              if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
                v7 = "ReturnHr";
              break;
            case 2:
              v7 = "LogNt";
              if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
                v7 = "LogHr";
              break;
            case 3:
              v7 = "FailFast";
              break;
          }
        }
        else
        {
          v7 = "Exception";
        }
        memset(Buffer, 0, sizeof(Buffer));
        if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
        {
          v8 = *(_DWORD *)(a3 + 12);
          if ( wil::details::g_pfnFormatNtStatusMsg )
            wil::details::g_pfnFormatNtStatusMsg(v8, Buffer, 0x100u);
        }
        else
        {
          v8 = *(_DWORD *)(a3 + 8);
          FormatMessageW(0x1200u, 0, v8, 0x400u, Buffer, 0x100u, 0);
        }
        v9 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
        v10 = *(const wchar_t **)(a3 + 56);
        v11 = *(_QWORD *)(a3 + 136);
        v12 = *(const wchar_t **)(a3 + 128);
        if ( v10 )
        {
          LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
          v13 = wil::details::LogStringPrintf(this, v9, L"%hs(%u)\\%hs!%p: ", v10, lpBuffer, v12, v11);
        }
        else
        {
          v13 = wil::details::LogStringPrintf(this, v9, L"%hs!%p: ", v12, v11);
        }
        v14 = (wil::details *)v13;
        v15 = *(const wchar_t **)(a3 + 144);
        if ( v15 )
          v14 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v13, v9, L"(caller: %p) ", v15);
        LODWORD(Arguments) = v8;
        nSize[0] = GetCurrentThreadId();
        LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
        v16 = (wil::details *)wil::details::LogStringPrintf(
                                v14,
                                v9,
                                L"%hs(%d) tid(%x) %08X %ws",
                                (const wchar_t *)v7,
                                lpBuffera,
                                *(_QWORD *)nSize,
                                Arguments,
                                Buffer);
        if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
        {
          v18 = wil::details::LogStringPrintf(v16, v9, L"    ", v17);
          v19 = *(const wchar_t **)(a3 + 24);
          if ( v19 )
            v18 = wil::details::LogStringPrintf((wil::details *)v18, v9, L"Msg:[%ws] ", v19);
          v20 = *(const wchar_t **)(a3 + 72);
          if ( v20 )
            v18 = wil::details::LogStringPrintf((wil::details *)v18, v9, L"CallContext:[%hs] ", v20);
          v21 = *(const wchar_t **)(a3 + 48);
          if ( *(_QWORD *)(a3 + 40) )
          {
            wil::details::LogStringPrintf((wil::details *)v18, v9, L"[%hs(%hs)]\n", v21, *(_QWORD *)(a3 + 40));
          }
          else if ( v21 )
          {
            wil::details::LogStringPrintf((wil::details *)v18, v9, L"[%hs]\n", v21);
          }
          else
          {
            wil::details::LogStringPrintf((wil::details *)v18, v9, L"\n", 0);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002f70  mov     [rsp+arg_18], rbx
0x180002f75  push    rbp
0x180002f76  push    rsi
0x180002f77  push    rdi
0x180002f78  push    r14
0x180002f7a  push    r15
0x180002f7c  sub     rsp, 250h
0x180002f83  mov     rax, cs:__security_cookie
0x180002f8a  xor     rax, rsp
0x180002f8d  mov     [rsp+278h+var_38], rax
0x180002f95  mov     rbx, r8
0x180002f98  mov     rsi, rdx
0x180002f9b  mov     r14, rcx
0x180002f9e  test    rdx, rdx
0x180002fa1  jz      loc_180003207
0x180002fa7  test    rcx, rcx
0x180002faa  jz      loc_180003207
0x180002fb0  xor     ebp, ebp
0x180002fb2  mov     [rcx], bp
0x180002fb5  mov     rax, cs:g_pfnResultLoggingCallback
0x180002fbc  test    rax, rax
0x180002fbf  jz      short loc_180002FE3
0x180002fc1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bpl; bool wil::details::g_resultMessageCallbackSet
0x180002fc8  jz      short loc_180002FE3
0x180002fca  mov     r8, rdx
0x180002fcd  mov     rdx, rcx
0x180002fd0  mov     rcx, rbx
0x180002fd3  call    cs:__guard_dispatch_icall_fptr
0x180002fd9  cmp     [r14], bp
0x180002fdd  jnz     loc_180003207
0x180002fe3  lea     rdi, qword_180047B28
0x180002fea  mov     ecx, [rbx]
0x180002fec  test    ecx, ecx
0x180002fee  jz      short loc_180003038
0x180002ff0  sub     ecx, 1
0x180002ff3  jz      short loc_180003020
0x180002ff5  sub     ecx, 1
0x180002ff8  jz      short loc_180003008
0x180002ffa  cmp     ecx, 1
0x180002ffd  jnz     short loc_18000303F
0x180002fff  lea     rdi, aFailfast; "FailFast"
0x180003006  jmp     short loc_18000303F
0x180003008  test    byte ptr [rbx+4], 8
0x18000300c  lea     rax, aLoghr; "LogHr"
0x180003013  lea     rdi, aLognt; "LogNt"
0x18000301a  cmovz   rdi, rax
0x18000301e  jmp     short loc_18000303F
0x180003020  test    byte ptr [rbx+4], 8
0x180003024  lea     rax, aReturnhr; "ReturnHr"
0x18000302b  lea     rdi, aReturnnt; "ReturnNt"
0x180003032  cmovz   rdi, rax
0x180003036  jmp     short loc_18000303F
0x180003038  lea     rdi, aException; "Exception"
0x18000303f  xor     edx, edx; Val
0x180003041  mov     r8d, 200h; Size
0x180003047  lea     rcx, [rsp+278h+Buffer]; void *
0x18000304c  call    memset
0x180003051  test    byte ptr [rbx+4], 8
0x180003055  jz      short loc_18000307D
0x180003057  mov     r15d, [rbx+0Ch]
0x18000305b  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180003062  test    rax, rax
0x180003065  jz      short loc_1800030AE
0x180003067  mov     r8d, 100h
0x18000306d  lea     rdx, [rsp+278h+Buffer]
0x180003072  mov     ecx, r15d
0x180003075  call    cs:__guard_dispatch_icall_fptr
0x18000307b  jmp     short loc_1800030AE
0x18000307d  mov     r15d, [rbx+8]
0x180003081  mov     [rsp+278h+Arguments], rbp; Arguments
0x180003086  mov     [rsp+278h+nSize], 100h; nSize
0x18000308e  lea     rax, [rsp+278h+Buffer]
0x180003093  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003098  mov     r9d, 400h; dwLanguageId
0x18000309e  mov     r8d, r15d; dwMessageId
0x1800030a1  xor     edx, edx; lpSource
0x1800030a3  mov     ecx, 1200h; dwFlags
0x1800030a8  call    cs:__imp_FormatMessageW
0x1800030ae  lea     rsi, [r14+rsi*2]
0x1800030b2  mov     r9, [rbx+38h]; wchar_t *
0x1800030b6  mov     rax, [rbx+88h]
0x1800030bd  mov     rcx, [rbx+80h]
0x1800030c4  mov     rdx, rsi; wchar_t *
0x1800030c7  test    r9, r9
0x1800030ca  jz      short loc_1800030EE
0x1800030cc  mov     [rsp+278h+Arguments], rax
0x1800030d1  mov     qword ptr [rsp+278h+nSize], rcx
0x1800030d6  mov     eax, [rbx+40h]
0x1800030d9  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800030dd  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800030e4  mov     rcx, r14; this
0x1800030e7  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800030ec  jmp     short loc_180003105
0x1800030ee  mov     [rsp+278h+lpBuffer], rax
0x1800030f3  mov     r9, rcx; wchar_t *
0x1800030f6  lea     r8, aHsP; "%hs!%p: "
0x1800030fd  mov     rcx, r14; this
0x180003100  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003105  mov     rbp, rax
0x180003108  mov     r9, [rbx+90h]; wchar_t *
0x18000310f  test    r9, r9
0x180003112  jz      short loc_180003129
0x180003114  lea     r8, aCallerP; "(caller: %p) "
0x18000311b  mov     rdx, rsi; wchar_t *
0x18000311e  mov     rcx, rax; this
0x180003121  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003126  mov     rbp, rax
0x180003129  call    cs:__imp_GetCurrentThreadId
0x18000312f  lea     rcx, [rsp+278h+Buffer]
0x180003134  mov     [rsp+278h+var_240], rcx
0x180003139  mov     dword ptr [rsp+278h+Arguments], r15d
0x18000313e  mov     [rsp+278h+nSize], eax
0x180003142  mov     eax, [rbx+44h]
0x180003145  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003149  mov     r9, rdi; wchar_t *
0x18000314c  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003153  mov     rdx, rsi; wchar_t *
0x180003156  mov     rcx, rbp; this
0x180003159  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000315e  cmp     qword ptr [rbx+18h], 0
0x180003163  jnz     short loc_180003177
0x180003165  cmp     qword ptr [rbx+48h], 0
0x18000316a  jnz     short loc_180003177
0x18000316c  cmp     qword ptr [rbx+30h], 0
0x180003171  jz      loc_180003207
0x180003177  lea     r8, asc_180047C18; "    "
0x18000317e  mov     rdx, rsi; wchar_t *
0x180003181  mov     rcx, rax; this
0x180003184  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003189  mov     r9, [rbx+18h]; wchar_t *
0x18000318d  test    r9, r9
0x180003190  jz      short loc_1800031A4
0x180003192  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003199  mov     rdx, rsi; wchar_t *
0x18000319c  mov     rcx, rax; this
0x18000319f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800031a4  mov     r9, [rbx+48h]; wchar_t *
0x1800031a8  test    r9, r9
0x1800031ab  jz      short loc_1800031BF
0x1800031ad  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800031b4  mov     rdx, rsi; wchar_t *
0x1800031b7  mov     rcx, rax; this
0x1800031ba  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800031bf  mov     rcx, [rbx+28h]
0x1800031c3  mov     r9, [rbx+30h]; wchar_t *
0x1800031c7  mov     rdx, rsi; wchar_t *
0x1800031ca  test    rcx, rcx
0x1800031cd  jz      short loc_1800031E5
0x1800031cf  mov     [rsp+278h+lpBuffer], rcx
0x1800031d4  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800031db  mov     rcx, rax; this
0x1800031de  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800031e3  jmp     short loc_180003207
0x1800031e5  mov     rcx, rax; this
0x1800031e8  test    r9, r9
0x1800031eb  jz      short loc_1800031FB
0x1800031ed  lea     r8, aHs; "[%hs]\n"
0x1800031f4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800031f9  jmp     short loc_180003207
0x1800031fb  lea     r8, asc_180047C90; "\n"
0x180003202  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180003207  xor     eax, eax
0x180003209  mov     rcx, [rsp+278h+var_38]
0x180003211  xor     rcx, rsp; StackCookie
0x180003214  call    __security_check_cookie
0x180003219  mov     rbx, [rsp+278h+arg_18]
0x180003221  add     rsp, 250h
0x180003228  pop     r15
0x18000322a  pop     r14
0x18000322c  pop     rdi
0x18000322d  pop     rsi
0x18000322e  pop     rbp
0x18000322f  retn
```
