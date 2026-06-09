# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800038f4`
- end: `0x180003bb7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002758`
- `0x180004334`
- `0x180004854`
- `0x180006600`

## callees

- `0x1800038f4`
- `0x180004648`
- `0x180009efe`
- `0x180009f30`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003aad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003aad`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003a26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003a26`

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
          v7 = (const char *)&dword_18000CF24;
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
0x1800038f4  mov     [rsp+arg_18], rbx
0x1800038f9  push    rbp
0x1800038fa  push    rsi
0x1800038fb  push    rdi
0x1800038fc  push    r14
0x1800038fe  push    r15
0x180003900  sub     rsp, 250h
0x180003907  mov     rax, cs:__security_cookie
0x18000390e  xor     rax, rsp
0x180003911  mov     [rsp+278h+var_38], rax
0x180003919  mov     rbx, r8
0x18000391c  mov     rsi, rdx
0x18000391f  mov     r14, rcx
0x180003922  xor     r15d, r15d
0x180003925  test    rdx, rdx
0x180003928  jz      loc_180003B8D
0x18000392e  test    rcx, rcx
0x180003931  jz      loc_180003B8D
0x180003937  mov     [rcx], r15w
0x18000393b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003942  test    rax, rax
0x180003945  jz      short loc_180003968
0x180003947  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000394e  jz      short loc_180003968
0x180003950  mov     r8, rdx
0x180003953  mov     rdx, rcx
0x180003956  mov     rcx, rbx
0x180003959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000395e  cmp     [r14], r15w
0x180003962  jnz     loc_180003B8D
0x180003968  mov     ecx, [rbx]
0x18000396a  mov     bpl, 8
0x18000396d  test    ecx, ecx
0x18000396f  jz      short loc_1800039BA
0x180003971  sub     ecx, 1
0x180003974  jz      short loc_1800039A2
0x180003976  sub     ecx, 1
0x180003979  jz      short loc_180003992
0x18000397b  cmp     ecx, 1
0x18000397e  jz      short loc_180003989
0x180003980  lea     rdi, dword_18000CF24
0x180003987  jmp     short loc_1800039C1
0x180003989  lea     rdi, aFailfast; "FailFast"
0x180003990  jmp     short loc_1800039C1
0x180003992  lea     rax, aLoghr; "LogHr"
0x180003999  lea     rdi, aLognt; "LogNt"
0x1800039a0  jmp     short loc_1800039B0
0x1800039a2  lea     rax, aReturnhr; "ReturnHr"
0x1800039a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800039b0  test    [rbx+4], bpl
0x1800039b4  cmovz   rdi, rax
0x1800039b8  jmp     short loc_1800039C1
0x1800039ba  lea     rdi, aException; "Exception"
0x1800039c1  xor     edx, edx; Val
0x1800039c3  mov     r8d, 200h; Size
0x1800039c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800039ce  call    memset_0
0x1800039d3  test    [rbx+4], bpl
0x1800039d7  jz      short loc_1800039FC
0x1800039d9  mov     ebp, [rbx+0Ch]
0x1800039dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800039e3  test    rax, rax
0x1800039e6  jz      short loc_180003A32
0x1800039e8  mov     r8d, 100h
0x1800039ee  lea     rdx, [rsp+278h+Buffer]
0x1800039f3  mov     ecx, ebp
0x1800039f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039fa  jmp     short loc_180003A32
0x1800039fc  mov     ebp, [rbx+8]
0x1800039ff  mov     [rsp+278h+Arguments], r15; Arguments
0x180003a04  mov     [rsp+278h+nSize], 100h; nSize
0x180003a0c  lea     rax, [rsp+278h+Buffer]
0x180003a11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003a16  mov     r9d, 400h; dwLanguageId
0x180003a1c  mov     r8d, ebp; dwMessageId
0x180003a1f  xor     edx, edx; lpSource
0x180003a21  mov     ecx, 1200h; dwFlags
0x180003a26  call    cs:__imp_FormatMessageW
0x180003a2d  nop     dword ptr [rax+rax+00h]
0x180003a32  lea     rsi, [r14+rsi*2]
0x180003a36  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003a3a  mov     rax, [rbx+88h]
0x180003a41  mov     rcx, [rbx+80h]
0x180003a48  mov     rdx, rsi; unsigned __int16 *
0x180003a4b  test    r9, r9
0x180003a4e  jz      short loc_180003A72
0x180003a50  mov     [rsp+278h+Arguments], rax
0x180003a55  mov     qword ptr [rsp+278h+nSize], rcx
0x180003a5a  mov     eax, [rbx+40h]
0x180003a5d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003a61  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003a68  mov     rcx, r14; this
0x180003a6b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a70  jmp     short loc_180003A89
0x180003a72  mov     [rsp+278h+lpBuffer], rax
0x180003a77  mov     r9, rcx; unsigned __int16 *
0x180003a7a  lea     r8, aHsP; "%hs!%p: "
0x180003a81  mov     rcx, r14; this
0x180003a84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a89  mov     r14, rax
0x180003a8c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003a93  test    r9, r9
0x180003a96  jz      short loc_180003AAD
0x180003a98  lea     r8, aCallerP; "(caller: %p) "
0x180003a9f  mov     rdx, rsi; unsigned __int16 *
0x180003aa2  mov     rcx, rax; this
0x180003aa5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003aaa  mov     r14, rax
0x180003aad  call    cs:__imp_GetCurrentThreadId
0x180003ab4  nop     dword ptr [rax+rax+00h]
0x180003ab9  lea     rcx, [rsp+278h+Buffer]
0x180003abe  mov     [rsp+278h+var_240], rcx
0x180003ac3  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003ac7  mov     [rsp+278h+nSize], eax
0x180003acb  mov     eax, [rbx+44h]
0x180003ace  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003ad2  mov     r9, rdi; unsigned __int16 *
0x180003ad5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003adc  mov     rdx, rsi; unsigned __int16 *
0x180003adf  mov     rcx, r14; this
0x180003ae2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ae7  cmp     [rbx+18h], r15
0x180003aeb  jnz     short loc_180003AFD
0x180003aed  cmp     [rbx+48h], r15
0x180003af1  jnz     short loc_180003AFD
0x180003af3  cmp     [rbx+30h], r15
0x180003af7  jz      loc_180003B8D
0x180003afd  lea     r8, asc_18000D010; "    "
0x180003b04  mov     rdx, rsi; unsigned __int16 *
0x180003b07  mov     rcx, rax; this
0x180003b0a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b0f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003b13  test    r9, r9
0x180003b16  jz      short loc_180003B2A
0x180003b18  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003b1f  mov     rdx, rsi; unsigned __int16 *
0x180003b22  mov     rcx, rax; this
0x180003b25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b2a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003b2e  test    r9, r9
0x180003b31  jz      short loc_180003B45
0x180003b33  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003b3a  mov     rdx, rsi; unsigned __int16 *
0x180003b3d  mov     rcx, rax; this
0x180003b40  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b45  mov     rcx, [rbx+28h]
0x180003b49  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003b4d  mov     rdx, rsi; unsigned __int16 *
0x180003b50  test    rcx, rcx
0x180003b53  jz      short loc_180003B6B
0x180003b55  mov     [rsp+278h+lpBuffer], rcx
0x180003b5a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003b61  mov     rcx, rax; this
0x180003b64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b69  jmp     short loc_180003B8D
0x180003b6b  mov     rcx, rax; this
0x180003b6e  test    r9, r9
0x180003b71  jz      short loc_180003B81
0x180003b73  lea     r8, aHs; "[%hs]\n"
0x180003b7a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b7f  jmp     short loc_180003B8D
0x180003b81  lea     r8, asc_18000D088; "\n"
0x180003b88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b8d  xor     eax, eax
0x180003b8f  mov     rcx, [rsp+278h+var_38]
0x180003b97  xor     rcx, rsp; StackCookie
0x180003b9a  call    __security_check_cookie
0x180003b9f  mov     rbx, [rsp+278h+arg_18]
0x180003ba7  add     rsp, 250h
0x180003bae  pop     r15
0x180003bb0  pop     r14
0x180003bb2  pop     rdi
0x180003bb3  pop     rsi
0x180003bb4  pop     rbp
0x180003bb5  retn
```
