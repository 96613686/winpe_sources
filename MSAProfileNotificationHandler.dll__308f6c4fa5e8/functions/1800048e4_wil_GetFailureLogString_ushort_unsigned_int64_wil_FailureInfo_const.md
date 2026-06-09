# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800048e4`
- end: `0x180004b9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000335c`
- `0x1800035cc`
- `0x18000525c`

## callees

- `0x180001cb0`
- `0x1800028f0`
- `0x1800048e4`
- `0x18000555c`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004a16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004a16`

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
          v7 = (const char *)&byte_18000DE48;
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
0x1800048e4  mov     [rsp+arg_18], rbx
0x1800048e9  push    rbp
0x1800048ea  push    rsi
0x1800048eb  push    rdi
0x1800048ec  push    r14
0x1800048ee  push    r15
0x1800048f0  sub     rsp, 250h
0x1800048f7  mov     rax, cs:__security_cookie
0x1800048fe  xor     rax, rsp
0x180004901  mov     [rsp+278h+var_38], rax
0x180004909  mov     rbx, r8
0x18000490c  mov     rsi, rdx
0x18000490f  mov     r14, rcx
0x180004912  xor     r15d, r15d
0x180004915  test    rdx, rdx
0x180004918  jz      loc_180004B71
0x18000491e  test    rcx, rcx
0x180004921  jz      loc_180004B71
0x180004927  mov     [rcx], r15w
0x18000492b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004932  test    rax, rax
0x180004935  jz      short loc_180004958
0x180004937  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000493e  jz      short loc_180004958
0x180004940  mov     r8, rdx
0x180004943  mov     rdx, rcx
0x180004946  mov     rcx, rbx
0x180004949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000494e  cmp     [r14], r15w
0x180004952  jnz     loc_180004B71
0x180004958  mov     ecx, [rbx]
0x18000495a  mov     bpl, 8
0x18000495d  test    ecx, ecx
0x18000495f  jz      short loc_1800049AA
0x180004961  sub     ecx, 1
0x180004964  jz      short loc_180004992
0x180004966  sub     ecx, 1
0x180004969  jz      short loc_180004982
0x18000496b  cmp     ecx, 1
0x18000496e  jz      short loc_180004979
0x180004970  lea     rdi, byte_18000DE48
0x180004977  jmp     short loc_1800049B1
0x180004979  lea     rdi, aFailfast; "FailFast"
0x180004980  jmp     short loc_1800049B1
0x180004982  lea     rax, aLoghr; "LogHr"
0x180004989  lea     rdi, aLognt; "LogNt"
0x180004990  jmp     short loc_1800049A0
0x180004992  lea     rax, aReturnhr; "ReturnHr"
0x180004999  lea     rdi, aReturnnt; "ReturnNt"
0x1800049a0  test    [rbx+4], bpl
0x1800049a4  cmovz   rdi, rax
0x1800049a8  jmp     short loc_1800049B1
0x1800049aa  lea     rdi, aException; "Exception"
0x1800049b1  xor     edx, edx; Val
0x1800049b3  mov     r8d, 200h; Size
0x1800049b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800049be  call    memset_0
0x1800049c3  test    [rbx+4], bpl
0x1800049c7  jz      short loc_1800049EC
0x1800049c9  mov     ebp, [rbx+0Ch]
0x1800049cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800049d3  test    rax, rax
0x1800049d6  jz      short loc_180004A1C
0x1800049d8  mov     r8d, 100h
0x1800049de  lea     rdx, [rsp+278h+Buffer]
0x1800049e3  mov     ecx, ebp
0x1800049e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ea  jmp     short loc_180004A1C
0x1800049ec  mov     ebp, [rbx+8]
0x1800049ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800049f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800049fc  lea     rax, [rsp+278h+Buffer]
0x180004a01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004a06  mov     r9d, 400h; dwLanguageId
0x180004a0c  mov     r8d, ebp; dwMessageId
0x180004a0f  xor     edx, edx; lpSource
0x180004a11  mov     ecx, 1200h; dwFlags
0x180004a16  call    cs:__imp_FormatMessageW
0x180004a1c  lea     rsi, [r14+rsi*2]
0x180004a20  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004a24  mov     rax, [rbx+88h]
0x180004a2b  mov     rcx, [rbx+80h]
0x180004a32  mov     rdx, rsi; unsigned __int16 *
0x180004a35  test    r9, r9
0x180004a38  jz      short loc_180004A5C
0x180004a3a  mov     [rsp+278h+Arguments], rax
0x180004a3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004a44  mov     eax, [rbx+40h]
0x180004a47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004a4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004a52  mov     rcx, r14; this
0x180004a55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a5a  jmp     short loc_180004A73
0x180004a5c  mov     [rsp+278h+lpBuffer], rax
0x180004a61  mov     r9, rcx; unsigned __int16 *
0x180004a64  lea     r8, aHsP; "%hs!%p: "
0x180004a6b  mov     rcx, r14; this
0x180004a6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a73  mov     r14, rax
0x180004a76  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004a7d  test    r9, r9
0x180004a80  jz      short loc_180004A97
0x180004a82  lea     r8, aCallerP; "(caller: %p) "
0x180004a89  mov     rdx, rsi; unsigned __int16 *
0x180004a8c  mov     rcx, rax; this
0x180004a8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a94  mov     r14, rax
0x180004a97  call    cs:__imp_GetCurrentThreadId
0x180004a9d  lea     rcx, [rsp+278h+Buffer]
0x180004aa2  mov     [rsp+278h+var_240], rcx
0x180004aa7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004aab  mov     [rsp+278h+nSize], eax
0x180004aaf  mov     eax, [rbx+44h]
0x180004ab2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004ab6  mov     r9, rdi; unsigned __int16 *
0x180004ab9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004ac0  mov     rdx, rsi; unsigned __int16 *
0x180004ac3  mov     rcx, r14; this
0x180004ac6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004acb  cmp     [rbx+18h], r15
0x180004acf  jnz     short loc_180004AE1
0x180004ad1  cmp     [rbx+48h], r15
0x180004ad5  jnz     short loc_180004AE1
0x180004ad7  cmp     [rbx+30h], r15
0x180004adb  jz      loc_180004B71
0x180004ae1  lea     r8, asc_18000DF50; "    "
0x180004ae8  mov     rdx, rsi; unsigned __int16 *
0x180004aeb  mov     rcx, rax; this
0x180004aee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004af3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004af7  test    r9, r9
0x180004afa  jz      short loc_180004B0E
0x180004afc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004b03  mov     rdx, rsi; unsigned __int16 *
0x180004b06  mov     rcx, rax; this
0x180004b09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004b12  test    r9, r9
0x180004b15  jz      short loc_180004B29
0x180004b17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004b1e  mov     rdx, rsi; unsigned __int16 *
0x180004b21  mov     rcx, rax; this
0x180004b24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b29  mov     rcx, [rbx+28h]
0x180004b2d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004b31  mov     rdx, rsi; unsigned __int16 *
0x180004b34  test    rcx, rcx
0x180004b37  jz      short loc_180004B4F
0x180004b39  mov     [rsp+278h+lpBuffer], rcx
0x180004b3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004b45  mov     rcx, rax; this
0x180004b48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b4d  jmp     short loc_180004B71
0x180004b4f  mov     rcx, rax; this
0x180004b52  test    r9, r9
0x180004b55  jz      short loc_180004B65
0x180004b57  lea     r8, aHs; "[%hs]\n"
0x180004b5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b63  jmp     short loc_180004B71
0x180004b65  lea     r8, asc_18000DFC8; "\n"
0x180004b6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b71  xor     eax, eax
0x180004b73  mov     rcx, [rsp+278h+var_38]
0x180004b7b  xor     rcx, rsp; StackCookie
0x180004b7e  call    __security_check_cookie
0x180004b83  mov     rbx, [rsp+278h+arg_18]
0x180004b8b  add     rsp, 250h
0x180004b92  pop     r15
0x180004b94  pop     r14
0x180004b96  pop     rdi
0x180004b97  pop     rsi
0x180004b98  pop     rbp
0x180004b99  retn
```
