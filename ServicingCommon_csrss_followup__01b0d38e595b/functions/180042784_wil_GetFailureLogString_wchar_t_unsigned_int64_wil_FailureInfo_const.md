# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180042784`
- end: `0x180042a47`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180041580`
- `0x180042c68`

## callees

- `0x18002d2b0`
- `0x180042784`
- `0x180042f7c`
- `0x180097e20`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18004293d`
- `KERNEL32!GetCurrentThreadId` at `0x18004293d`
- `KERNEL32!FormatMessageW` at `0x1800428b6`
- `KERNEL32!FormatMessageW` at `0x1800428b6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, wchar_t *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const wchar_t *v11; // r9
  wchar_t *v12; // rsi
  __int64 v13; // rax
  wchar_t *v14; // rax
  const wchar_t *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, wchar_t *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
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
        else
          v8 = (const char *)&byte_1800AEEA5;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset(Buffer, 0, sizeof(Buffer));
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
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const wchar_t **)(a3 + 128), v13);
  }
  v15 = *(const wchar_t **)(a3 + 144);
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
                          (const wchar_t *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x180042784  mov     [rsp+arg_18], rbx
0x180042789  push    rbp
0x18004278a  push    rsi
0x18004278b  push    rdi
0x18004278c  push    r14
0x18004278e  push    r15
0x180042790  sub     rsp, 250h
0x180042797  mov     rax, cs:__security_cookie
0x18004279e  xor     rax, rsp
0x1800427a1  mov     [rsp+278h+var_38], rax
0x1800427a9  xor     r15d, r15d
0x1800427ac  mov     rbx, r8
0x1800427af  mov     rsi, rdx
0x1800427b2  mov     r14, rcx
0x1800427b5  test    rdx, rdx
0x1800427b8  jz      loc_180042A1D
0x1800427be  test    rcx, rcx
0x1800427c1  jz      loc_180042A1D
0x1800427c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800427ce  mov     [rcx], r15w
0x1800427d2  test    rax, rax
0x1800427d5  jz      short loc_1800427F8
0x1800427d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800427de  jz      short loc_1800427F8
0x1800427e0  mov     r8, rdx
0x1800427e3  mov     rdx, rcx
0x1800427e6  mov     rcx, rbx
0x1800427e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427ee  cmp     [r14], r15w
0x1800427f2  jnz     loc_180042A1D
0x1800427f8  mov     ecx, [rbx]
0x1800427fa  mov     bpl, 8
0x1800427fd  test    ecx, ecx
0x1800427ff  jz      short loc_18004284A
0x180042801  sub     ecx, 1
0x180042804  jz      short loc_180042832
0x180042806  sub     ecx, 1
0x180042809  jz      short loc_180042822
0x18004280b  cmp     ecx, 1
0x18004280e  jz      short loc_180042819
0x180042810  lea     rdi, byte_1800AEEA5
0x180042817  jmp     short loc_180042851
0x180042819  lea     rdi, aFailfast; "FailFast"
0x180042820  jmp     short loc_180042851
0x180042822  lea     rax, aLoghr; "LogHr"
0x180042829  lea     rdi, aLognt; "LogNt"
0x180042830  jmp     short loc_180042840
0x180042832  lea     rax, aReturnhr; "ReturnHr"
0x180042839  lea     rdi, aReturnnt; "ReturnNt"
0x180042840  test    [rbx+4], bpl
0x180042844  cmovz   rdi, rax
0x180042848  jmp     short loc_180042851
0x18004284a  lea     rdi, aException; "Exception"
0x180042851  xor     edx, edx; Val
0x180042853  lea     rcx, [rsp+278h+Buffer]; void *
0x180042858  mov     r8d, 200h; Size
0x18004285e  call    memset
0x180042863  test    [rbx+4], bpl
0x180042867  jz      short loc_18004288C
0x180042869  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180042870  mov     ebp, [rbx+0Ch]
0x180042873  test    rax, rax
0x180042876  jz      short loc_1800428C2
0x180042878  mov     r8d, 100h
0x18004287e  lea     rdx, [rsp+278h+Buffer]
0x180042883  mov     ecx, ebp
0x180042885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004288a  jmp     short loc_1800428C2
0x18004288c  mov     ebp, [rbx+8]
0x18004288f  lea     rax, [rsp+278h+Buffer]
0x180042894  mov     [rsp+278h+Arguments], r15; Arguments
0x180042899  mov     r8d, ebp; dwMessageId
0x18004289c  mov     [rsp+278h+nSize], 100h; nSize
0x1800428a4  mov     r9d, 400h; dwLanguageId
0x1800428aa  xor     edx, edx; lpSource
0x1800428ac  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800428b1  mov     ecx, 1200h; dwFlags
0x1800428b6  call    cs:__imp_FormatMessageW
0x1800428bd  nop     dword ptr [rax+rax+00h]
0x1800428c2  mov     r9, [rbx+38h]; wchar_t *
0x1800428c6  lea     rsi, [r14+rsi*2]
0x1800428ca  mov     rax, [rbx+88h]
0x1800428d1  mov     rdx, rsi; wchar_t *
0x1800428d4  mov     rcx, [rbx+80h]
0x1800428db  test    r9, r9
0x1800428de  jz      short loc_180042902
0x1800428e0  mov     [rsp+278h+Arguments], rax
0x1800428e5  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800428ec  mov     eax, [rbx+40h]
0x1800428ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800428f4  mov     rcx, r14; this
0x1800428f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800428fb  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180042900  jmp     short loc_180042919
0x180042902  mov     r9, rcx; wchar_t *
0x180042905  mov     [rsp+278h+lpBuffer], rax
0x18004290a  mov     rcx, r14; this
0x18004290d  lea     r8, aHsP; "%hs!%p: "
0x180042914  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180042919  mov     r9, [rbx+90h]; wchar_t *
0x180042920  mov     r14, rax
0x180042923  test    r9, r9
0x180042926  jz      short loc_18004293D
0x180042928  lea     r8, aCallerP; "(caller: %p) "
0x18004292f  mov     rdx, rsi; wchar_t *
0x180042932  mov     rcx, rax; this
0x180042935  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18004293a  mov     r14, rax
0x18004293d  call    cs:__imp_GetCurrentThreadId
0x180042944  nop     dword ptr [rax+rax+00h]
0x180042949  lea     rcx, [rsp+278h+Buffer]
0x18004294e  mov     r9, rdi; wchar_t *
0x180042951  mov     [rsp+278h+var_240], rcx
0x180042956  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18004295d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180042961  mov     rdx, rsi; wchar_t *
0x180042964  mov     [rsp+278h+nSize], eax
0x180042968  mov     rcx, r14; this
0x18004296b  mov     eax, [rbx+44h]
0x18004296e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180042972  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180042977  cmp     [rbx+18h], r15
0x18004297b  jnz     short loc_18004298D
0x18004297d  cmp     [rbx+48h], r15
0x180042981  jnz     short loc_18004298D
0x180042983  cmp     [rbx+30h], r15
0x180042987  jz      loc_180042A1D
0x18004298d  lea     r8, asc_1800AEF90; "    "
0x180042994  mov     rdx, rsi; wchar_t *
0x180042997  mov     rcx, rax; this
0x18004299a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18004299f  mov     r9, [rbx+18h]; wchar_t *
0x1800429a3  test    r9, r9
0x1800429a6  jz      short loc_1800429BA
0x1800429a8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800429af  mov     rdx, rsi; wchar_t *
0x1800429b2  mov     rcx, rax; this
0x1800429b5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800429ba  mov     r9, [rbx+48h]; wchar_t *
0x1800429be  test    r9, r9
0x1800429c1  jz      short loc_1800429D5
0x1800429c3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800429ca  mov     rdx, rsi; wchar_t *
0x1800429cd  mov     rcx, rax; this
0x1800429d0  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800429d5  mov     rcx, [rbx+28h]
0x1800429d9  mov     rdx, rsi; wchar_t *
0x1800429dc  mov     r9, [rbx+30h]; wchar_t *
0x1800429e0  test    rcx, rcx
0x1800429e3  jz      short loc_1800429FB
0x1800429e5  mov     [rsp+278h+lpBuffer], rcx
0x1800429ea  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800429f1  mov     rcx, rax; this
0x1800429f4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800429f9  jmp     short loc_180042A1D
0x1800429fb  mov     rcx, rax; this
0x1800429fe  test    r9, r9
0x180042a01  jz      short loc_180042A11
0x180042a03  lea     r8, aHs_0; "[%hs]\n"
0x180042a0a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180042a0f  jmp     short loc_180042A1D
0x180042a11  lea     r8, asc_1800AF008; "\n"
0x180042a18  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180042a1d  xor     eax, eax
0x180042a1f  mov     rcx, [rsp+278h+var_38]
0x180042a27  xor     rcx, rsp; StackCookie
0x180042a2a  call    __security_check_cookie
0x180042a2f  mov     rbx, [rsp+278h+arg_18]
0x180042a37  add     rsp, 250h
0x180042a3e  pop     r15
0x180042a40  pop     r14
0x180042a42  pop     rdi
0x180042a43  pop     rsi
0x180042a44  pop     rbp
0x180042a45  retn
```
