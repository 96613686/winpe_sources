# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000cccc`
- end: `0x18000cf82`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008ea0`
- `0x18000db50`
- `0x180012e10`

## callees

- `0x180003fc0`
- `0x180004b78`
- `0x18000cccc`
- `0x18000de50`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce7f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cdfe`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cdfe`

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
          v7 = word_18002B0AA;
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
0x18000cccc  mov     [rsp+arg_18], rbx
0x18000ccd1  push    rbp
0x18000ccd2  push    rsi
0x18000ccd3  push    rdi
0x18000ccd4  push    r14
0x18000ccd6  push    r15
0x18000ccd8  sub     rsp, 250h
0x18000ccdf  mov     rax, cs:__security_cookie
0x18000cce6  xor     rax, rsp
0x18000cce9  mov     [rsp+278h+var_38], rax
0x18000ccf1  mov     rbx, r8
0x18000ccf4  mov     rsi, rdx
0x18000ccf7  mov     r14, rcx
0x18000ccfa  xor     r15d, r15d
0x18000ccfd  test    rdx, rdx
0x18000cd00  jz      loc_18000CF59
0x18000cd06  test    rcx, rcx
0x18000cd09  jz      loc_18000CF59
0x18000cd0f  mov     [rcx], r15w
0x18000cd13  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cd1a  test    rax, rax
0x18000cd1d  jz      short loc_18000CD40
0x18000cd1f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cd26  jz      short loc_18000CD40
0x18000cd28  mov     r8, rdx
0x18000cd2b  mov     rdx, rcx
0x18000cd2e  mov     rcx, rbx
0x18000cd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd36  cmp     [r14], r15w
0x18000cd3a  jnz     loc_18000CF59
0x18000cd40  mov     ecx, [rbx]
0x18000cd42  mov     bpl, 8
0x18000cd45  test    ecx, ecx
0x18000cd47  jz      short loc_18000CD92
0x18000cd49  sub     ecx, 1
0x18000cd4c  jz      short loc_18000CD7A
0x18000cd4e  sub     ecx, 1
0x18000cd51  jz      short loc_18000CD6A
0x18000cd53  cmp     ecx, 1
0x18000cd56  jz      short loc_18000CD61
0x18000cd58  lea     rdi, word_18002B0AA
0x18000cd5f  jmp     short loc_18000CD99
0x18000cd61  lea     rdi, aFailfast; "FailFast"
0x18000cd68  jmp     short loc_18000CD99
0x18000cd6a  lea     rax, aLoghr; "LogHr"
0x18000cd71  lea     rdi, aLognt; "LogNt"
0x18000cd78  jmp     short loc_18000CD88
0x18000cd7a  lea     rax, aReturnhr; "ReturnHr"
0x18000cd81  lea     rdi, aReturnnt; "ReturnNt"
0x18000cd88  test    [rbx+4], bpl
0x18000cd8c  cmovz   rdi, rax
0x18000cd90  jmp     short loc_18000CD99
0x18000cd92  lea     rdi, aException; "Exception"
0x18000cd99  xor     edx, edx; Val
0x18000cd9b  mov     r8d, 200h; Size
0x18000cda1  lea     rcx, [rsp+278h+Buffer]; void *
0x18000cda6  call    memset_0
0x18000cdab  test    [rbx+4], bpl
0x18000cdaf  jz      short loc_18000CDD4
0x18000cdb1  mov     ebp, [rbx+0Ch]
0x18000cdb4  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000cdbb  test    rax, rax
0x18000cdbe  jz      short loc_18000CE04
0x18000cdc0  mov     r8d, 100h
0x18000cdc6  lea     rdx, [rsp+278h+Buffer]
0x18000cdcb  mov     ecx, ebp
0x18000cdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd2  jmp     short loc_18000CE04
0x18000cdd4  mov     ebp, [rbx+8]
0x18000cdd7  mov     [rsp+278h+Arguments], r15; Arguments
0x18000cddc  mov     [rsp+278h+nSize], 100h; nSize
0x18000cde4  lea     rax, [rsp+278h+Buffer]
0x18000cde9  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000cdee  mov     r9d, 400h; dwLanguageId
0x18000cdf4  mov     r8d, ebp; dwMessageId
0x18000cdf7  xor     edx, edx; lpSource
0x18000cdf9  mov     ecx, 1200h; dwFlags
0x18000cdfe  call    cs:__imp_FormatMessageW
0x18000ce04  lea     rsi, [r14+rsi*2]
0x18000ce08  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000ce0c  mov     rax, [rbx+88h]
0x18000ce13  mov     rcx, [rbx+80h]
0x18000ce1a  mov     rdx, rsi; unsigned __int16 *
0x18000ce1d  test    r9, r9
0x18000ce20  jz      short loc_18000CE44
0x18000ce22  mov     [rsp+278h+Arguments], rax
0x18000ce27  mov     qword ptr [rsp+278h+nSize], rcx
0x18000ce2c  mov     eax, [rbx+40h]
0x18000ce2f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ce33  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000ce3a  mov     rcx, r14; this
0x18000ce3d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ce42  jmp     short loc_18000CE5B
0x18000ce44  mov     [rsp+278h+lpBuffer], rax
0x18000ce49  mov     r9, rcx; unsigned __int16 *
0x18000ce4c  lea     r8, aHsP; "%hs!%p: "
0x18000ce53  mov     rcx, r14; this
0x18000ce56  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ce5b  mov     r14, rax
0x18000ce5e  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000ce65  test    r9, r9
0x18000ce68  jz      short loc_18000CE7F
0x18000ce6a  lea     r8, aCallerP; "(caller: %p) "
0x18000ce71  mov     rdx, rsi; unsigned __int16 *
0x18000ce74  mov     rcx, rax; this
0x18000ce77  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ce7c  mov     r14, rax
0x18000ce7f  call    cs:__imp_GetCurrentThreadId
0x18000ce85  lea     rcx, [rsp+278h+Buffer]
0x18000ce8a  mov     [rsp+278h+var_240], rcx
0x18000ce8f  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000ce93  mov     [rsp+278h+nSize], eax
0x18000ce97  mov     eax, [rbx+44h]
0x18000ce9a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ce9e  mov     r9, rdi; unsigned __int16 *
0x18000cea1  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000cea8  mov     rdx, rsi; unsigned __int16 *
0x18000ceab  mov     rcx, r14; this
0x18000ceae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ceb3  cmp     [rbx+18h], r15
0x18000ceb7  jnz     short loc_18000CEC9
0x18000ceb9  cmp     [rbx+48h], r15
0x18000cebd  jnz     short loc_18000CEC9
0x18000cebf  cmp     [rbx+30h], r15
0x18000cec3  jz      loc_18000CF59
0x18000cec9  lea     r8, asc_18002BAF8; "    "
0x18000ced0  mov     rdx, rsi; unsigned __int16 *
0x18000ced3  mov     rcx, rax; this
0x18000ced6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cedb  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000cedf  test    r9, r9
0x18000cee2  jz      short loc_18000CEF6
0x18000cee4  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000ceeb  mov     rdx, rsi; unsigned __int16 *
0x18000ceee  mov     rcx, rax; this
0x18000cef1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cef6  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000cefa  test    r9, r9
0x18000cefd  jz      short loc_18000CF11
0x18000ceff  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000cf06  mov     rdx, rsi; unsigned __int16 *
0x18000cf09  mov     rcx, rax; this
0x18000cf0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf11  mov     rcx, [rbx+28h]
0x18000cf15  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000cf19  mov     rdx, rsi; unsigned __int16 *
0x18000cf1c  test    rcx, rcx
0x18000cf1f  jz      short loc_18000CF37
0x18000cf21  mov     [rsp+278h+lpBuffer], rcx
0x18000cf26  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000cf2d  mov     rcx, rax; this
0x18000cf30  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf35  jmp     short loc_18000CF59
0x18000cf37  mov     rcx, rax; this
0x18000cf3a  test    r9, r9
0x18000cf3d  jz      short loc_18000CF4D
0x18000cf3f  lea     r8, aHs; "[%hs]\n"
0x18000cf46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf4b  jmp     short loc_18000CF59
0x18000cf4d  lea     r8, asc_18002BB70; "\n"
0x18000cf54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cf59  xor     eax, eax
0x18000cf5b  mov     rcx, [rsp+278h+var_38]
0x18000cf63  xor     rcx, rsp; StackCookie
0x18000cf66  call    __security_check_cookie
0x18000cf6b  mov     rbx, [rsp+278h+arg_18]
0x18000cf73  add     rsp, 250h
0x18000cf7a  pop     r15
0x18000cf7c  pop     r14
0x18000cf7e  pop     rdi
0x18000cf7f  pop     rsi
0x18000cf80  pop     rbp
0x18000cf81  retn
```
