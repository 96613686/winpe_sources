# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400048e4`
- end: `0x140004b9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140003150`
- `0x140005524`

## callees

- `0x1400048e4`
- `0x140005824`
- `0x140045eea`
- `0x140045f30`
- `0x140047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004a97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004a97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004a16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004a16`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
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
          v8 = (const char *)&dword_140049D24;
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
  memset_0(Buffer, 0, sizeof(Buffer));
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
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
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
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x1400048e4  mov     [rsp+arg_18], rbx
0x1400048e9  push    rbp
0x1400048ea  push    rsi
0x1400048eb  push    rdi
0x1400048ec  push    r14
0x1400048ee  push    r15
0x1400048f0  sub     rsp, 250h
0x1400048f7  mov     rax, cs:__security_cookie
0x1400048fe  xor     rax, rsp
0x140004901  mov     [rsp+278h+var_38], rax
0x140004909  xor     r15d, r15d
0x14000490c  mov     rbx, r8
0x14000490f  mov     rsi, rdx
0x140004912  mov     r14, rcx
0x140004915  test    rdx, rdx
0x140004918  jz      loc_140004B71
0x14000491e  test    rcx, rcx
0x140004921  jz      loc_140004B71
0x140004927  mov     rax, cs:g_pfnResultLoggingCallback
0x14000492e  mov     [rcx], r15w
0x140004932  test    rax, rax
0x140004935  jz      short loc_140004958
0x140004937  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000493e  jz      short loc_140004958
0x140004940  mov     r8, rdx
0x140004943  mov     rdx, rcx
0x140004946  mov     rcx, rbx
0x140004949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000494e  cmp     [r14], r15w
0x140004952  jnz     loc_140004B71
0x140004958  mov     ecx, [rbx]
0x14000495a  mov     bpl, 8
0x14000495d  test    ecx, ecx
0x14000495f  jz      short loc_1400049AA
0x140004961  sub     ecx, 1
0x140004964  jz      short loc_140004992
0x140004966  sub     ecx, 1
0x140004969  jz      short loc_140004982
0x14000496b  cmp     ecx, 1
0x14000496e  jz      short loc_140004979
0x140004970  lea     rdi, dword_140049D24
0x140004977  jmp     short loc_1400049B1
0x140004979  lea     rdi, aFailfast; "FailFast"
0x140004980  jmp     short loc_1400049B1
0x140004982  lea     rax, aLoghr; "LogHr"
0x140004989  lea     rdi, aLognt; "LogNt"
0x140004990  jmp     short loc_1400049A0
0x140004992  lea     rax, aReturnhr; "ReturnHr"
0x140004999  lea     rdi, aReturnnt; "ReturnNt"
0x1400049a0  test    [rbx+4], bpl
0x1400049a4  cmovz   rdi, rax
0x1400049a8  jmp     short loc_1400049B1
0x1400049aa  lea     rdi, aException; "Exception"
0x1400049b1  xor     edx, edx; Val
0x1400049b3  lea     rcx, [rsp+278h+Buffer]; void *
0x1400049b8  mov     r8d, 200h; Size
0x1400049be  call    memset_0
0x1400049c3  test    [rbx+4], bpl
0x1400049c7  jz      short loc_1400049EC
0x1400049c9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400049d0  mov     ebp, [rbx+0Ch]
0x1400049d3  test    rax, rax
0x1400049d6  jz      short loc_140004A1C
0x1400049d8  mov     r8d, 100h
0x1400049de  lea     rdx, [rsp+278h+Buffer]
0x1400049e3  mov     ecx, ebp
0x1400049e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049ea  jmp     short loc_140004A1C
0x1400049ec  mov     ebp, [rbx+8]
0x1400049ef  lea     rax, [rsp+278h+Buffer]
0x1400049f4  mov     [rsp+278h+Arguments], r15; Arguments
0x1400049f9  mov     r8d, ebp; dwMessageId
0x1400049fc  mov     [rsp+278h+nSize], 100h; nSize
0x140004a04  mov     r9d, 400h; dwLanguageId
0x140004a0a  xor     edx, edx; lpSource
0x140004a0c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004a11  mov     ecx, 1200h; dwFlags
0x140004a16  call    cs:__imp_FormatMessageW
0x140004a1c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140004a20  lea     rsi, [r14+rsi*2]
0x140004a24  mov     rax, [rbx+88h]
0x140004a2b  mov     rdx, rsi; unsigned __int16 *
0x140004a2e  mov     rcx, [rbx+80h]
0x140004a35  test    r9, r9
0x140004a38  jz      short loc_140004A5C
0x140004a3a  mov     [rsp+278h+Arguments], rax
0x140004a3f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004a46  mov     eax, [rbx+40h]
0x140004a49  mov     qword ptr [rsp+278h+nSize], rcx
0x140004a4e  mov     rcx, r14; this
0x140004a51  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004a55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004a5a  jmp     short loc_140004A73
0x140004a5c  mov     r9, rcx; unsigned __int16 *
0x140004a5f  mov     [rsp+278h+lpBuffer], rax
0x140004a64  mov     rcx, r14; this
0x140004a67  lea     r8, aHsP; "%hs!%p: "
0x140004a6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004a73  mov     r9, [rbx+90h]; unsigned __int16 *
0x140004a7a  mov     r14, rax
0x140004a7d  test    r9, r9
0x140004a80  jz      short loc_140004A97
0x140004a82  lea     r8, aCallerP; "(caller: %p) "
0x140004a89  mov     rdx, rsi; unsigned __int16 *
0x140004a8c  mov     rcx, rax; this
0x140004a8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004a94  mov     r14, rax
0x140004a97  call    cs:__imp_GetCurrentThreadId
0x140004a9d  lea     rcx, [rsp+278h+Buffer]
0x140004aa2  mov     r9, rdi; unsigned __int16 *
0x140004aa5  mov     [rsp+278h+var_240], rcx
0x140004aaa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004ab1  mov     dword ptr [rsp+278h+Arguments], ebp
0x140004ab5  mov     rdx, rsi; unsigned __int16 *
0x140004ab8  mov     [rsp+278h+nSize], eax
0x140004abc  mov     rcx, r14; this
0x140004abf  mov     eax, [rbx+44h]
0x140004ac2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004ac6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004acb  cmp     [rbx+18h], r15
0x140004acf  jnz     short loc_140004AE1
0x140004ad1  cmp     [rbx+48h], r15
0x140004ad5  jnz     short loc_140004AE1
0x140004ad7  cmp     [rbx+30h], r15
0x140004adb  jz      loc_140004B71
0x140004ae1  lea     r8, asc_140049E10; "    "
0x140004ae8  mov     rdx, rsi; unsigned __int16 *
0x140004aeb  mov     rcx, rax; this
0x140004aee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004af3  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004af7  test    r9, r9
0x140004afa  jz      short loc_140004B0E
0x140004afc  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004b03  mov     rdx, rsi; unsigned __int16 *
0x140004b06  mov     rcx, rax; this
0x140004b09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140004b12  test    r9, r9
0x140004b15  jz      short loc_140004B29
0x140004b17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140004b1e  mov     rdx, rsi; unsigned __int16 *
0x140004b21  mov     rcx, rax; this
0x140004b24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b29  mov     rcx, [rbx+28h]
0x140004b2d  mov     rdx, rsi; unsigned __int16 *
0x140004b30  mov     r9, [rbx+30h]; unsigned __int16 *
0x140004b34  test    rcx, rcx
0x140004b37  jz      short loc_140004B4F
0x140004b39  mov     [rsp+278h+lpBuffer], rcx
0x140004b3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004b45  mov     rcx, rax; this
0x140004b48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b4d  jmp     short loc_140004B71
0x140004b4f  mov     rcx, rax; this
0x140004b52  test    r9, r9
0x140004b55  jz      short loc_140004B65
0x140004b57  lea     r8, aHs; "[%hs]\n"
0x140004b5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b63  jmp     short loc_140004B71
0x140004b65  lea     r8, asc_140049E88; "\n"
0x140004b6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b71  xor     eax, eax
0x140004b73  mov     rcx, [rsp+278h+var_38]
0x140004b7b  xor     rcx, rsp; StackCookie
0x140004b7e  call    __security_check_cookie
0x140004b83  mov     rbx, [rsp+278h+arg_18]
0x140004b8b  add     rsp, 250h
0x140004b92  pop     r15
0x140004b94  pop     r14
0x140004b96  pop     rdi
0x140004b97  pop     rsi
0x140004b98  pop     rbp
0x140004b99  retn
```
