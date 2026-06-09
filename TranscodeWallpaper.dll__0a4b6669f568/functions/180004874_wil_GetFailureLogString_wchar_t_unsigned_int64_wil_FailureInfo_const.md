# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004874`
- end: `0x180004b2a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180003298`
- `0x180003518`
- `0x1800051e0`
- `0x180006e10`
- `0x18000728c`
- `0x18000df61`
- `0x18000e095`
- `0x18000e1fe`
- `0x18000e47b`

## callees

- `0x180002170`
- `0x180002cb4`
- `0x180004874`
- `0x1800054e0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a27`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800049a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800049a6`

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
          v7 = (const char *)&byte_1800110BF;
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
0x180004874  mov     [rsp+arg_18], rbx
0x180004879  push    rbp
0x18000487a  push    rsi
0x18000487b  push    rdi
0x18000487c  push    r14
0x18000487e  push    r15
0x180004880  sub     rsp, 250h
0x180004887  mov     rax, cs:__security_cookie
0x18000488e  xor     rax, rsp
0x180004891  mov     [rsp+278h+var_38], rax
0x180004899  mov     rbx, r8
0x18000489c  mov     rsi, rdx
0x18000489f  mov     r14, rcx
0x1800048a2  xor     r15d, r15d
0x1800048a5  test    rdx, rdx
0x1800048a8  jz      loc_180004B01
0x1800048ae  test    rcx, rcx
0x1800048b1  jz      loc_180004B01
0x1800048b7  mov     [rcx], r15w
0x1800048bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800048c2  test    rax, rax
0x1800048c5  jz      short loc_1800048E8
0x1800048c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800048ce  jz      short loc_1800048E8
0x1800048d0  mov     r8, rdx
0x1800048d3  mov     rdx, rcx
0x1800048d6  mov     rcx, rbx
0x1800048d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048de  cmp     [r14], r15w
0x1800048e2  jnz     loc_180004B01
0x1800048e8  mov     ecx, [rbx]
0x1800048ea  mov     bpl, 8
0x1800048ed  test    ecx, ecx
0x1800048ef  jz      short loc_18000493A
0x1800048f1  sub     ecx, 1
0x1800048f4  jz      short loc_180004922
0x1800048f6  sub     ecx, 1
0x1800048f9  jz      short loc_180004912
0x1800048fb  cmp     ecx, 1
0x1800048fe  jz      short loc_180004909
0x180004900  lea     rdi, byte_1800110BF
0x180004907  jmp     short loc_180004941
0x180004909  lea     rdi, aFailfast; "FailFast"
0x180004910  jmp     short loc_180004941
0x180004912  lea     rax, aLoghr; "LogHr"
0x180004919  lea     rdi, aLognt; "LogNt"
0x180004920  jmp     short loc_180004930
0x180004922  lea     rax, aReturnhr; "ReturnHr"
0x180004929  lea     rdi, aReturnnt; "ReturnNt"
0x180004930  test    [rbx+4], bpl
0x180004934  cmovz   rdi, rax
0x180004938  jmp     short loc_180004941
0x18000493a  lea     rdi, aException; "Exception"
0x180004941  xor     edx, edx; Val
0x180004943  mov     r8d, 200h; Size
0x180004949  lea     rcx, [rsp+278h+Buffer]; void *
0x18000494e  call    memset_0
0x180004953  test    [rbx+4], bpl
0x180004957  jz      short loc_18000497C
0x180004959  mov     ebp, [rbx+0Ch]
0x18000495c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180004963  test    rax, rax
0x180004966  jz      short loc_1800049AC
0x180004968  mov     r8d, 100h
0x18000496e  lea     rdx, [rsp+278h+Buffer]
0x180004973  mov     ecx, ebp
0x180004975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000497a  jmp     short loc_1800049AC
0x18000497c  mov     ebp, [rbx+8]
0x18000497f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004984  mov     [rsp+278h+nSize], 100h; nSize
0x18000498c  lea     rax, [rsp+278h+Buffer]
0x180004991  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004996  mov     r9d, 400h; dwLanguageId
0x18000499c  mov     r8d, ebp; dwMessageId
0x18000499f  xor     edx, edx; lpSource
0x1800049a1  mov     ecx, 1200h; dwFlags
0x1800049a6  call    cs:__imp_FormatMessageW
0x1800049ac  lea     rsi, [r14+rsi*2]
0x1800049b0  mov     r9, [rbx+38h]; wchar_t *
0x1800049b4  mov     rax, [rbx+88h]
0x1800049bb  mov     rcx, [rbx+80h]
0x1800049c2  mov     rdx, rsi; wchar_t *
0x1800049c5  test    r9, r9
0x1800049c8  jz      short loc_1800049EC
0x1800049ca  mov     [rsp+278h+Arguments], rax
0x1800049cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800049d4  mov     eax, [rbx+40h]
0x1800049d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800049db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800049e2  mov     rcx, r14; this
0x1800049e5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800049ea  jmp     short loc_180004A03
0x1800049ec  mov     [rsp+278h+lpBuffer], rax
0x1800049f1  mov     r9, rcx; wchar_t *
0x1800049f4  lea     r8, aHsP; "%hs!%p: "
0x1800049fb  mov     rcx, r14; this
0x1800049fe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004a03  mov     r14, rax
0x180004a06  mov     r9, [rbx+90h]; wchar_t *
0x180004a0d  test    r9, r9
0x180004a10  jz      short loc_180004A27
0x180004a12  lea     r8, aCallerP; "(caller: %p) "
0x180004a19  mov     rdx, rsi; wchar_t *
0x180004a1c  mov     rcx, rax; this
0x180004a1f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004a24  mov     r14, rax
0x180004a27  call    cs:__imp_GetCurrentThreadId
0x180004a2d  lea     rcx, [rsp+278h+Buffer]
0x180004a32  mov     [rsp+278h+var_240], rcx
0x180004a37  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004a3b  mov     [rsp+278h+nSize], eax
0x180004a3f  mov     eax, [rbx+44h]
0x180004a42  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004a46  mov     r9, rdi; wchar_t *
0x180004a49  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004a50  mov     rdx, rsi; wchar_t *
0x180004a53  mov     rcx, r14; this
0x180004a56  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004a5b  cmp     [rbx+18h], r15
0x180004a5f  jnz     short loc_180004A71
0x180004a61  cmp     [rbx+48h], r15
0x180004a65  jnz     short loc_180004A71
0x180004a67  cmp     [rbx+30h], r15
0x180004a6b  jz      loc_180004B01
0x180004a71  lea     r8, asc_1800111B0; "    "
0x180004a78  mov     rdx, rsi; wchar_t *
0x180004a7b  mov     rcx, rax; this
0x180004a7e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004a83  mov     r9, [rbx+18h]; wchar_t *
0x180004a87  test    r9, r9
0x180004a8a  jz      short loc_180004A9E
0x180004a8c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004a93  mov     rdx, rsi; wchar_t *
0x180004a96  mov     rcx, rax; this
0x180004a99  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004a9e  mov     r9, [rbx+48h]; wchar_t *
0x180004aa2  test    r9, r9
0x180004aa5  jz      short loc_180004AB9
0x180004aa7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004aae  mov     rdx, rsi; wchar_t *
0x180004ab1  mov     rcx, rax; this
0x180004ab4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004ab9  mov     rcx, [rbx+28h]
0x180004abd  mov     r9, [rbx+30h]; wchar_t *
0x180004ac1  mov     rdx, rsi; wchar_t *
0x180004ac4  test    rcx, rcx
0x180004ac7  jz      short loc_180004ADF
0x180004ac9  mov     [rsp+278h+lpBuffer], rcx
0x180004ace  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004ad5  mov     rcx, rax; this
0x180004ad8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004add  jmp     short loc_180004B01
0x180004adf  mov     rcx, rax; this
0x180004ae2  test    r9, r9
0x180004ae5  jz      short loc_180004AF5
0x180004ae7  lea     r8, aHs; "[%hs]\n"
0x180004aee  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004af3  jmp     short loc_180004B01
0x180004af5  lea     r8, asc_180011228; "\n"
0x180004afc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004b01  xor     eax, eax
0x180004b03  mov     rcx, [rsp+278h+var_38]
0x180004b0b  xor     rcx, rsp; StackCookie
0x180004b0e  call    __security_check_cookie
0x180004b13  mov     rbx, [rsp+278h+arg_18]
0x180004b1b  add     rsp, 250h
0x180004b22  pop     r15
0x180004b24  pop     r14
0x180004b26  pop     rdi
0x180004b27  pop     rsi
0x180004b28  pop     rbp
0x180004b29  retn
```
