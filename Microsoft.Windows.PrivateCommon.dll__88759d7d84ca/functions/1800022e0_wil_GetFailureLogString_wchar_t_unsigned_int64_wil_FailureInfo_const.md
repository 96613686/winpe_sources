# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800022e0`
- end: `0x1800025a0`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `704`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003580`
- `0x1800039a0`
- `0x180004f10`
- `0x1800053e0`

## callees

- `0x180002260`
- `0x1800022e0`
- `0x180007280`
- `0x18000b930`
- `0x18000b990`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002499`
- `KERNEL32!GetCurrentThreadId` at `0x180002499`
- `KERNEL32!FormatMessageW` at `0x180002418`
- `KERNEL32!FormatMessageW` at `0x180002418`

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
        v7 = (const char *)&byte_18000E647;
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
0x1800022e0  mov     [rsp+arg_18], rbx
0x1800022e5  push    rbp
0x1800022e6  push    rsi
0x1800022e7  push    rdi
0x1800022e8  push    r14
0x1800022ea  push    r15
0x1800022ec  sub     rsp, 250h
0x1800022f3  mov     rax, cs:__security_cookie
0x1800022fa  xor     rax, rsp
0x1800022fd  mov     [rsp+278h+var_38], rax
0x180002305  mov     rbx, r8
0x180002308  mov     rsi, rdx
0x18000230b  mov     r14, rcx
0x18000230e  test    rdx, rdx
0x180002311  jz      loc_180002577
0x180002317  test    rcx, rcx
0x18000231a  jz      loc_180002577
0x180002320  xor     ebp, ebp
0x180002322  mov     [rcx], bp
0x180002325  mov     rax, cs:g_pfnResultLoggingCallback
0x18000232c  test    rax, rax
0x18000232f  jz      short loc_180002353
0x180002331  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bpl; bool wil::details::g_resultMessageCallbackSet
0x180002338  jz      short loc_180002353
0x18000233a  mov     r8, rdx
0x18000233d  mov     rdx, rcx
0x180002340  mov     rcx, rbx
0x180002343  call    cs:__guard_dispatch_icall_fptr
0x180002349  cmp     [r14], bp
0x18000234d  jnz     loc_180002577
0x180002353  lea     rdi, byte_18000E647
0x18000235a  mov     ecx, [rbx]
0x18000235c  test    ecx, ecx
0x18000235e  jz      short loc_1800023A8
0x180002360  sub     ecx, 1
0x180002363  jz      short loc_180002390
0x180002365  sub     ecx, 1
0x180002368  jz      short loc_180002378
0x18000236a  cmp     ecx, 1
0x18000236d  jnz     short loc_1800023AF
0x18000236f  lea     rdi, aFailfast; "FailFast"
0x180002376  jmp     short loc_1800023AF
0x180002378  test    byte ptr [rbx+4], 8
0x18000237c  lea     rax, aLoghr; "LogHr"
0x180002383  lea     rdi, aLognt; "LogNt"
0x18000238a  cmovz   rdi, rax
0x18000238e  jmp     short loc_1800023AF
0x180002390  test    byte ptr [rbx+4], 8
0x180002394  lea     rax, aReturnhr; "ReturnHr"
0x18000239b  lea     rdi, aReturnnt; "ReturnNt"
0x1800023a2  cmovz   rdi, rax
0x1800023a6  jmp     short loc_1800023AF
0x1800023a8  lea     rdi, aException; "Exception"
0x1800023af  xor     edx, edx; Val
0x1800023b1  mov     r8d, 200h; Size
0x1800023b7  lea     rcx, [rsp+278h+Buffer]; void *
0x1800023bc  call    memset
0x1800023c1  test    byte ptr [rbx+4], 8
0x1800023c5  jz      short loc_1800023ED
0x1800023c7  mov     r15d, [rbx+0Ch]
0x1800023cb  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800023d2  test    rax, rax
0x1800023d5  jz      short loc_18000241E
0x1800023d7  mov     r8d, 100h
0x1800023dd  lea     rdx, [rsp+278h+Buffer]
0x1800023e2  mov     ecx, r15d
0x1800023e5  call    cs:__guard_dispatch_icall_fptr
0x1800023eb  jmp     short loc_18000241E
0x1800023ed  mov     r15d, [rbx+8]
0x1800023f1  mov     [rsp+278h+Arguments], rbp; Arguments
0x1800023f6  mov     [rsp+278h+nSize], 100h; nSize
0x1800023fe  lea     rax, [rsp+278h+Buffer]
0x180002403  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180002408  mov     r9d, 400h; dwLanguageId
0x18000240e  mov     r8d, r15d; dwMessageId
0x180002411  xor     edx, edx; lpSource
0x180002413  mov     ecx, 1200h; dwFlags
0x180002418  call    cs:__imp_FormatMessageW
0x18000241e  lea     rsi, [r14+rsi*2]
0x180002422  mov     r9, [rbx+38h]; wchar_t *
0x180002426  mov     rax, [rbx+88h]
0x18000242d  mov     rcx, [rbx+80h]
0x180002434  mov     rdx, rsi; wchar_t *
0x180002437  test    r9, r9
0x18000243a  jz      short loc_18000245E
0x18000243c  mov     [rsp+278h+Arguments], rax
0x180002441  mov     qword ptr [rsp+278h+nSize], rcx
0x180002446  mov     eax, [rbx+40h]
0x180002449  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000244d  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180002454  mov     rcx, r14; this
0x180002457  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000245c  jmp     short loc_180002475
0x18000245e  mov     [rsp+278h+lpBuffer], rax
0x180002463  mov     r9, rcx; wchar_t *
0x180002466  lea     r8, aHsP; "%hs!%p: "
0x18000246d  mov     rcx, r14; this
0x180002470  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002475  mov     rbp, rax
0x180002478  mov     r9, [rbx+90h]; wchar_t *
0x18000247f  test    r9, r9
0x180002482  jz      short loc_180002499
0x180002484  lea     r8, aCallerP; "(caller: %p) "
0x18000248b  mov     rdx, rsi; wchar_t *
0x18000248e  mov     rcx, rax; this
0x180002491  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002496  mov     rbp, rax
0x180002499  call    cs:__imp_GetCurrentThreadId
0x18000249f  lea     rcx, [rsp+278h+Buffer]
0x1800024a4  mov     [rsp+278h+var_240], rcx
0x1800024a9  mov     dword ptr [rsp+278h+Arguments], r15d
0x1800024ae  mov     [rsp+278h+nSize], eax
0x1800024b2  mov     eax, [rbx+44h]
0x1800024b5  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800024b9  mov     r9, rdi; wchar_t *
0x1800024bc  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800024c3  mov     rdx, rsi; wchar_t *
0x1800024c6  mov     rcx, rbp; this
0x1800024c9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800024ce  cmp     qword ptr [rbx+18h], 0
0x1800024d3  jnz     short loc_1800024E7
0x1800024d5  cmp     qword ptr [rbx+48h], 0
0x1800024da  jnz     short loc_1800024E7
0x1800024dc  cmp     qword ptr [rbx+30h], 0
0x1800024e1  jz      loc_180002577
0x1800024e7  lea     r8, asc_18000E730; "    "
0x1800024ee  mov     rdx, rsi; wchar_t *
0x1800024f1  mov     rcx, rax; this
0x1800024f4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800024f9  mov     r9, [rbx+18h]; wchar_t *
0x1800024fd  test    r9, r9
0x180002500  jz      short loc_180002514
0x180002502  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002509  mov     rdx, rsi; wchar_t *
0x18000250c  mov     rcx, rax; this
0x18000250f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002514  mov     r9, [rbx+48h]; wchar_t *
0x180002518  test    r9, r9
0x18000251b  jz      short loc_18000252F
0x18000251d  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180002524  mov     rdx, rsi; wchar_t *
0x180002527  mov     rcx, rax; this
0x18000252a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000252f  mov     rcx, [rbx+28h]
0x180002533  mov     r9, [rbx+30h]; wchar_t *
0x180002537  mov     rdx, rsi; wchar_t *
0x18000253a  test    rcx, rcx
0x18000253d  jz      short loc_180002555
0x18000253f  mov     [rsp+278h+lpBuffer], rcx
0x180002544  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000254b  mov     rcx, rax; this
0x18000254e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002553  jmp     short loc_180002577
0x180002555  mov     rcx, rax; this
0x180002558  test    r9, r9
0x18000255b  jz      short loc_18000256B
0x18000255d  lea     r8, aHs; "[%hs]\n"
0x180002564  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002569  jmp     short loc_180002577
0x18000256b  lea     r8, asc_18000E7A8; "\n"
0x180002572  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002577  xor     eax, eax
0x180002579  mov     rcx, [rsp+278h+var_38]
0x180002581  xor     rcx, rsp; StackCookie
0x180002584  call    __security_check_cookie
0x180002589  mov     rbx, [rsp+278h+arg_18]
0x180002591  add     rsp, 250h
0x180002598  pop     r15
0x18000259a  pop     r14
0x18000259c  pop     rdi
0x18000259d  pop     rsi
0x18000259e  pop     rbp
0x18000259f  retn
```
