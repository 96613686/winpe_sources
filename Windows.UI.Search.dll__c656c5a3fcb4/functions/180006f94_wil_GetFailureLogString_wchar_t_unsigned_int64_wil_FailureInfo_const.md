# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006f94`
- end: `0x18000724a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004968`
- `0x180007e2c`
- `0x1800084ec`
- `0x18000c2d0`

## callees

- `0x1800030b6`
- `0x180006f94`
- `0x18000810c`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007147`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007147`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800070c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800070c6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
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
          v7 = (const char *)&byte_18008A910;
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x180006f94  mov     [rsp+arg_18], rbx
0x180006f99  push    rbp
0x180006f9a  push    rsi
0x180006f9b  push    rdi
0x180006f9c  push    r14
0x180006f9e  push    r15
0x180006fa0  sub     rsp, 250h
0x180006fa7  mov     rax, cs:__security_cookie
0x180006fae  xor     rax, rsp
0x180006fb1  mov     [rsp+278h+var_38], rax
0x180006fb9  mov     rbx, r8
0x180006fbc  mov     rsi, rdx
0x180006fbf  mov     r14, rcx
0x180006fc2  xor     r15d, r15d
0x180006fc5  test    rdx, rdx
0x180006fc8  jz      loc_180007221
0x180006fce  test    rcx, rcx
0x180006fd1  jz      loc_180007221
0x180006fd7  mov     [rcx], r15w
0x180006fdb  mov     rax, cs:g_pfnResultLoggingCallback
0x180006fe2  test    rax, rax
0x180006fe5  jz      short loc_180007008
0x180006fe7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006fee  jz      short loc_180007008
0x180006ff0  mov     r8, rdx
0x180006ff3  mov     rdx, rcx
0x180006ff6  mov     rcx, rbx
0x180006ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffe  cmp     [r14], r15w
0x180007002  jnz     loc_180007221
0x180007008  mov     ecx, [rbx]
0x18000700a  mov     bpl, 8
0x18000700d  test    ecx, ecx
0x18000700f  jz      short loc_18000705A
0x180007011  sub     ecx, 1
0x180007014  jz      short loc_180007042
0x180007016  sub     ecx, 1
0x180007019  jz      short loc_180007032
0x18000701b  cmp     ecx, 1
0x18000701e  jz      short loc_180007029
0x180007020  lea     rdi, byte_18008A910
0x180007027  jmp     short loc_180007061
0x180007029  lea     rdi, aFailfast; "FailFast"
0x180007030  jmp     short loc_180007061
0x180007032  lea     rax, aLoghr; "LogHr"
0x180007039  lea     rdi, aLognt; "LogNt"
0x180007040  jmp     short loc_180007050
0x180007042  lea     rax, aReturnhr; "ReturnHr"
0x180007049  lea     rdi, aReturnnt; "ReturnNt"
0x180007050  test    [rbx+4], bpl
0x180007054  cmovz   rdi, rax
0x180007058  jmp     short loc_180007061
0x18000705a  lea     rdi, aException; "Exception"
0x180007061  xor     edx, edx; Val
0x180007063  mov     r8d, 200h; Size
0x180007069  lea     rcx, [rsp+278h+Buffer]; void *
0x18000706e  call    memset_0
0x180007073  test    [rbx+4], bpl
0x180007077  jz      short loc_18000709C
0x180007079  mov     ebp, [rbx+0Ch]
0x18000707c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180007083  test    rax, rax
0x180007086  jz      short loc_1800070CC
0x180007088  mov     r8d, 100h
0x18000708e  lea     rdx, [rsp+278h+Buffer]
0x180007093  mov     ecx, ebp
0x180007095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000709a  jmp     short loc_1800070CC
0x18000709c  mov     ebp, [rbx+8]
0x18000709f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800070a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800070ac  lea     rax, [rsp+278h+Buffer]
0x1800070b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800070b6  mov     r9d, 400h; dwLanguageId
0x1800070bc  mov     r8d, ebp; dwMessageId
0x1800070bf  xor     edx, edx; lpSource
0x1800070c1  mov     ecx, 1200h; dwFlags
0x1800070c6  call    cs:__imp_FormatMessageW
0x1800070cc  lea     rsi, [r14+rsi*2]
0x1800070d0  mov     r9, [rbx+38h]; wchar_t *
0x1800070d4  mov     rax, [rbx+88h]
0x1800070db  mov     rcx, [rbx+80h]
0x1800070e2  mov     rdx, rsi; wchar_t *
0x1800070e5  test    r9, r9
0x1800070e8  jz      short loc_18000710C
0x1800070ea  mov     [rsp+278h+Arguments], rax
0x1800070ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800070f4  mov     eax, [rbx+40h]
0x1800070f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800070fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007102  mov     rcx, r14; this
0x180007105  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000710a  jmp     short loc_180007123
0x18000710c  mov     [rsp+278h+lpBuffer], rax
0x180007111  mov     r9, rcx; wchar_t *
0x180007114  lea     r8, aHsP; "%hs!%p: "
0x18000711b  mov     rcx, r14; this
0x18000711e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007123  mov     r14, rax
0x180007126  mov     r9, [rbx+90h]; wchar_t *
0x18000712d  test    r9, r9
0x180007130  jz      short loc_180007147
0x180007132  lea     r8, aCallerP; "(caller: %p) "
0x180007139  mov     rdx, rsi; wchar_t *
0x18000713c  mov     rcx, rax; this
0x18000713f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007144  mov     r14, rax
0x180007147  call    cs:__imp_GetCurrentThreadId
0x18000714d  lea     rcx, [rsp+278h+Buffer]
0x180007152  mov     [rsp+278h+var_240], rcx
0x180007157  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000715b  mov     [rsp+278h+nSize], eax
0x18000715f  mov     eax, [rbx+44h]
0x180007162  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007166  mov     r9, rdi; wchar_t *
0x180007169  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007170  mov     rdx, rsi; wchar_t *
0x180007173  mov     rcx, r14; this
0x180007176  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000717b  cmp     [rbx+18h], r15
0x18000717f  jnz     short loc_180007191
0x180007181  cmp     [rbx+48h], r15
0x180007185  jnz     short loc_180007191
0x180007187  cmp     [rbx+30h], r15
0x18000718b  jz      loc_180007221
0x180007191  lea     r8, asc_18008AA00; "    "
0x180007198  mov     rdx, rsi; wchar_t *
0x18000719b  mov     rcx, rax; this
0x18000719e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800071a3  mov     r9, [rbx+18h]; wchar_t *
0x1800071a7  test    r9, r9
0x1800071aa  jz      short loc_1800071BE
0x1800071ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800071b3  mov     rdx, rsi; wchar_t *
0x1800071b6  mov     rcx, rax; this
0x1800071b9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800071be  mov     r9, [rbx+48h]; wchar_t *
0x1800071c2  test    r9, r9
0x1800071c5  jz      short loc_1800071D9
0x1800071c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800071ce  mov     rdx, rsi; wchar_t *
0x1800071d1  mov     rcx, rax; this
0x1800071d4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800071d9  mov     rcx, [rbx+28h]
0x1800071dd  mov     r9, [rbx+30h]; wchar_t *
0x1800071e1  mov     rdx, rsi; wchar_t *
0x1800071e4  test    rcx, rcx
0x1800071e7  jz      short loc_1800071FF
0x1800071e9  mov     [rsp+278h+lpBuffer], rcx
0x1800071ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800071f5  mov     rcx, rax; this
0x1800071f8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800071fd  jmp     short loc_180007221
0x1800071ff  mov     rcx, rax; this
0x180007202  test    r9, r9
0x180007205  jz      short loc_180007215
0x180007207  lea     r8, aHs; "[%hs]\n"
0x18000720e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007213  jmp     short loc_180007221
0x180007215  lea     r8, asc_18008AA78; "\n"
0x18000721c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007221  xor     eax, eax
0x180007223  mov     rcx, [rsp+278h+var_38]
0x18000722b  xor     rcx, rsp; StackCookie
0x18000722e  call    __security_check_cookie
0x180007233  mov     rbx, [rsp+278h+arg_18]
0x18000723b  add     rsp, 250h
0x180007242  pop     r15
0x180007244  pop     r14
0x180007246  pop     rdi
0x180007247  pop     rsi
0x180007248  pop     rbp
0x180007249  retn
```
