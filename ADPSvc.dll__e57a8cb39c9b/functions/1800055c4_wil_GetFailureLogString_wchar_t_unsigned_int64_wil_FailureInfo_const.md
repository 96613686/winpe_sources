# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800055c4`
- end: `0x18000587a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180003f18`
- `0x180004198`
- `0x180005f30`
- `0x180007bb0`
- `0x18000bda8`
- `0x1800c70f3`
- `0x1800c7227`
- `0x1800c7390`
- `0x1800c760d`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x1800055c4`
- `0x180006230`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005777`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005777`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800056f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800056f6`

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
          v7 = (const char *)&Src;
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
0x1800055c4  mov     [rsp+arg_18], rbx
0x1800055c9  push    rbp
0x1800055ca  push    rsi
0x1800055cb  push    rdi
0x1800055cc  push    r14
0x1800055ce  push    r15
0x1800055d0  sub     rsp, 250h
0x1800055d7  mov     rax, cs:__security_cookie
0x1800055de  xor     rax, rsp
0x1800055e1  mov     [rsp+278h+var_38], rax
0x1800055e9  mov     rbx, r8
0x1800055ec  mov     rsi, rdx
0x1800055ef  mov     r14, rcx
0x1800055f2  xor     r15d, r15d
0x1800055f5  test    rdx, rdx
0x1800055f8  jz      loc_180005851
0x1800055fe  test    rcx, rcx
0x180005601  jz      loc_180005851
0x180005607  mov     [rcx], r15w
0x18000560b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005612  test    rax, rax
0x180005615  jz      short loc_180005638
0x180005617  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000561e  jz      short loc_180005638
0x180005620  mov     r8, rdx
0x180005623  mov     rdx, rcx
0x180005626  mov     rcx, rbx
0x180005629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000562e  cmp     [r14], r15w
0x180005632  jnz     loc_180005851
0x180005638  mov     ecx, [rbx]
0x18000563a  mov     bpl, 8
0x18000563d  test    ecx, ecx
0x18000563f  jz      short loc_18000568A
0x180005641  sub     ecx, 1
0x180005644  jz      short loc_180005672
0x180005646  sub     ecx, 1
0x180005649  jz      short loc_180005662
0x18000564b  cmp     ecx, 1
0x18000564e  jz      short loc_180005659
0x180005650  lea     rdi, Src
0x180005657  jmp     short loc_180005691
0x180005659  lea     rdi, aFailfast; "FailFast"
0x180005660  jmp     short loc_180005691
0x180005662  lea     rax, aLoghr; "LogHr"
0x180005669  lea     rdi, aLognt; "LogNt"
0x180005670  jmp     short loc_180005680
0x180005672  lea     rax, aReturnhr; "ReturnHr"
0x180005679  lea     rdi, aReturnnt; "ReturnNt"
0x180005680  test    [rbx+4], bpl
0x180005684  cmovz   rdi, rax
0x180005688  jmp     short loc_180005691
0x18000568a  lea     rdi, aException; "Exception"
0x180005691  xor     edx, edx; Val
0x180005693  mov     r8d, 200h; Size
0x180005699  lea     rcx, [rsp+278h+Buffer]; void *
0x18000569e  call    memset_0
0x1800056a3  test    [rbx+4], bpl
0x1800056a7  jz      short loc_1800056CC
0x1800056a9  mov     ebp, [rbx+0Ch]
0x1800056ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800056b3  test    rax, rax
0x1800056b6  jz      short loc_1800056FC
0x1800056b8  mov     r8d, 100h
0x1800056be  lea     rdx, [rsp+278h+Buffer]
0x1800056c3  mov     ecx, ebp
0x1800056c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ca  jmp     short loc_1800056FC
0x1800056cc  mov     ebp, [rbx+8]
0x1800056cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800056d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800056dc  lea     rax, [rsp+278h+Buffer]
0x1800056e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800056e6  mov     r9d, 400h; dwLanguageId
0x1800056ec  mov     r8d, ebp; dwMessageId
0x1800056ef  xor     edx, edx; lpSource
0x1800056f1  mov     ecx, 1200h; dwFlags
0x1800056f6  call    cs:__imp_FormatMessageW
0x1800056fc  lea     rsi, [r14+rsi*2]
0x180005700  mov     r9, [rbx+38h]; wchar_t *
0x180005704  mov     rax, [rbx+88h]
0x18000570b  mov     rcx, [rbx+80h]
0x180005712  mov     rdx, rsi; wchar_t *
0x180005715  test    r9, r9
0x180005718  jz      short loc_18000573C
0x18000571a  mov     [rsp+278h+Arguments], rax
0x18000571f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005724  mov     eax, [rbx+40h]
0x180005727  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000572b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005732  mov     rcx, r14; this
0x180005735  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000573a  jmp     short loc_180005753
0x18000573c  mov     [rsp+278h+lpBuffer], rax
0x180005741  mov     r9, rcx; wchar_t *
0x180005744  lea     r8, aHsP; "%hs!%p: "
0x18000574b  mov     rcx, r14; this
0x18000574e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005753  mov     r14, rax
0x180005756  mov     r9, [rbx+90h]; wchar_t *
0x18000575d  test    r9, r9
0x180005760  jz      short loc_180005777
0x180005762  lea     r8, aCallerP; "(caller: %p) "
0x180005769  mov     rdx, rsi; wchar_t *
0x18000576c  mov     rcx, rax; this
0x18000576f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005774  mov     r14, rax
0x180005777  call    cs:__imp_GetCurrentThreadId
0x18000577d  lea     rcx, [rsp+278h+Buffer]
0x180005782  mov     [rsp+278h+var_240], rcx
0x180005787  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000578b  mov     [rsp+278h+nSize], eax
0x18000578f  mov     eax, [rbx+44h]
0x180005792  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005796  mov     r9, rdi; wchar_t *
0x180005799  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800057a0  mov     rdx, rsi; wchar_t *
0x1800057a3  mov     rcx, r14; this
0x1800057a6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800057ab  cmp     [rbx+18h], r15
0x1800057af  jnz     short loc_1800057C1
0x1800057b1  cmp     [rbx+48h], r15
0x1800057b5  jnz     short loc_1800057C1
0x1800057b7  cmp     [rbx+30h], r15
0x1800057bb  jz      loc_180005851
0x1800057c1  lea     r8, asc_1800ECE90; "    "
0x1800057c8  mov     rdx, rsi; wchar_t *
0x1800057cb  mov     rcx, rax; this
0x1800057ce  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800057d3  mov     r9, [rbx+18h]; wchar_t *
0x1800057d7  test    r9, r9
0x1800057da  jz      short loc_1800057EE
0x1800057dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800057e3  mov     rdx, rsi; wchar_t *
0x1800057e6  mov     rcx, rax; this
0x1800057e9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800057ee  mov     r9, [rbx+48h]; wchar_t *
0x1800057f2  test    r9, r9
0x1800057f5  jz      short loc_180005809
0x1800057f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800057fe  mov     rdx, rsi; wchar_t *
0x180005801  mov     rcx, rax; this
0x180005804  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005809  mov     rcx, [rbx+28h]
0x18000580d  mov     r9, [rbx+30h]; wchar_t *
0x180005811  mov     rdx, rsi; wchar_t *
0x180005814  test    rcx, rcx
0x180005817  jz      short loc_18000582F
0x180005819  mov     [rsp+278h+lpBuffer], rcx
0x18000581e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005825  mov     rcx, rax; this
0x180005828  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000582d  jmp     short loc_180005851
0x18000582f  mov     rcx, rax; this
0x180005832  test    r9, r9
0x180005835  jz      short loc_180005845
0x180005837  lea     r8, aHs_0; "[%hs]\n"
0x18000583e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005843  jmp     short loc_180005851
0x180005845  lea     r8, asc_1800ECF08; "\n"
0x18000584c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005851  xor     eax, eax
0x180005853  mov     rcx, [rsp+278h+var_38]
0x18000585b  xor     rcx, rsp; StackCookie
0x18000585e  call    __security_check_cookie
0x180005863  mov     rbx, [rsp+278h+arg_18]
0x18000586b  add     rsp, 250h
0x180005872  pop     r15
0x180005874  pop     r14
0x180005876  pop     rdi
0x180005877  pop     rsi
0x180005878  pop     rbp
0x180005879  retn
```
