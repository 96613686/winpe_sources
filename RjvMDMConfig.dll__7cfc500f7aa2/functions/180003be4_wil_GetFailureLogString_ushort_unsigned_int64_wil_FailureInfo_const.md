# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003be4`
- end: `0x180003ea7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800048d0`
- `0x180005750`
- `0x180006b38`
- `0x18000af94`

## callees

- `0x180001c60`
- `0x1800026d8`
- `0x180003be4`
- `0x18000487c`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d9d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003d16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003d16`

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
          v7 = (const char *)&qword_180020258;
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
0x180003be4  mov     [rsp+arg_18], rbx
0x180003be9  push    rbp
0x180003bea  push    rsi
0x180003beb  push    rdi
0x180003bec  push    r14
0x180003bee  push    r15
0x180003bf0  sub     rsp, 250h
0x180003bf7  mov     rax, cs:__security_cookie
0x180003bfe  xor     rax, rsp
0x180003c01  mov     [rsp+278h+var_38], rax
0x180003c09  mov     rbx, r8
0x180003c0c  mov     rsi, rdx
0x180003c0f  mov     r14, rcx
0x180003c12  xor     r15d, r15d
0x180003c15  test    rdx, rdx
0x180003c18  jz      loc_180003E7D
0x180003c1e  test    rcx, rcx
0x180003c21  jz      loc_180003E7D
0x180003c27  mov     [rcx], r15w
0x180003c2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c32  test    rax, rax
0x180003c35  jz      short loc_180003C58
0x180003c37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003c3e  jz      short loc_180003C58
0x180003c40  mov     r8, rdx
0x180003c43  mov     rdx, rcx
0x180003c46  mov     rcx, rbx
0x180003c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4e  cmp     [r14], r15w
0x180003c52  jnz     loc_180003E7D
0x180003c58  mov     ecx, [rbx]
0x180003c5a  mov     bpl, 8
0x180003c5d  test    ecx, ecx
0x180003c5f  jz      short loc_180003CAA
0x180003c61  sub     ecx, 1
0x180003c64  jz      short loc_180003C92
0x180003c66  sub     ecx, 1
0x180003c69  jz      short loc_180003C82
0x180003c6b  cmp     ecx, 1
0x180003c6e  jz      short loc_180003C79
0x180003c70  lea     rdi, qword_180020258
0x180003c77  jmp     short loc_180003CB1
0x180003c79  lea     rdi, aFailfast; "FailFast"
0x180003c80  jmp     short loc_180003CB1
0x180003c82  lea     rax, aLoghr; "LogHr"
0x180003c89  lea     rdi, aLognt; "LogNt"
0x180003c90  jmp     short loc_180003CA0
0x180003c92  lea     rax, aReturnhr; "ReturnHr"
0x180003c99  lea     rdi, aReturnnt; "ReturnNt"
0x180003ca0  test    [rbx+4], bpl
0x180003ca4  cmovz   rdi, rax
0x180003ca8  jmp     short loc_180003CB1
0x180003caa  lea     rdi, aException; "Exception"
0x180003cb1  xor     edx, edx; Val
0x180003cb3  mov     r8d, 200h; Size
0x180003cb9  lea     rcx, [rsp+278h+Buffer]; void *
0x180003cbe  call    memset_0
0x180003cc3  test    [rbx+4], bpl
0x180003cc7  jz      short loc_180003CEC
0x180003cc9  mov     ebp, [rbx+0Ch]
0x180003ccc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003cd3  test    rax, rax
0x180003cd6  jz      short loc_180003D22
0x180003cd8  mov     r8d, 100h
0x180003cde  lea     rdx, [rsp+278h+Buffer]
0x180003ce3  mov     ecx, ebp
0x180003ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cea  jmp     short loc_180003D22
0x180003cec  mov     ebp, [rbx+8]
0x180003cef  mov     [rsp+278h+Arguments], r15; Arguments
0x180003cf4  mov     [rsp+278h+nSize], 100h; nSize
0x180003cfc  lea     rax, [rsp+278h+Buffer]
0x180003d01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003d06  mov     r9d, 400h; dwLanguageId
0x180003d0c  mov     r8d, ebp; dwMessageId
0x180003d0f  xor     edx, edx; lpSource
0x180003d11  mov     ecx, 1200h; dwFlags
0x180003d16  call    cs:__imp_FormatMessageW
0x180003d1d  nop     dword ptr [rax+rax+00h]
0x180003d22  lea     rsi, [r14+rsi*2]
0x180003d26  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003d2a  mov     rax, [rbx+88h]
0x180003d31  mov     rcx, [rbx+80h]
0x180003d38  mov     rdx, rsi; unsigned __int16 *
0x180003d3b  test    r9, r9
0x180003d3e  jz      short loc_180003D62
0x180003d40  mov     [rsp+278h+Arguments], rax
0x180003d45  mov     qword ptr [rsp+278h+nSize], rcx
0x180003d4a  mov     eax, [rbx+40h]
0x180003d4d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003d51  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003d58  mov     rcx, r14; this
0x180003d5b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d60  jmp     short loc_180003D79
0x180003d62  mov     [rsp+278h+lpBuffer], rax
0x180003d67  mov     r9, rcx; unsigned __int16 *
0x180003d6a  lea     r8, aHsP; "%hs!%p: "
0x180003d71  mov     rcx, r14; this
0x180003d74  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d79  mov     r14, rax
0x180003d7c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003d83  test    r9, r9
0x180003d86  jz      short loc_180003D9D
0x180003d88  lea     r8, aCallerP; "(caller: %p) "
0x180003d8f  mov     rdx, rsi; unsigned __int16 *
0x180003d92  mov     rcx, rax; this
0x180003d95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d9a  mov     r14, rax
0x180003d9d  call    cs:__imp_GetCurrentThreadId
0x180003da4  nop     dword ptr [rax+rax+00h]
0x180003da9  lea     rcx, [rsp+278h+Buffer]
0x180003dae  mov     [rsp+278h+var_240], rcx
0x180003db3  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003db7  mov     [rsp+278h+nSize], eax
0x180003dbb  mov     eax, [rbx+44h]
0x180003dbe  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003dc2  mov     r9, rdi; unsigned __int16 *
0x180003dc5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003dcc  mov     rdx, rsi; unsigned __int16 *
0x180003dcf  mov     rcx, r14; this
0x180003dd2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003dd7  cmp     [rbx+18h], r15
0x180003ddb  jnz     short loc_180003DED
0x180003ddd  cmp     [rbx+48h], r15
0x180003de1  jnz     short loc_180003DED
0x180003de3  cmp     [rbx+30h], r15
0x180003de7  jz      loc_180003E7D
0x180003ded  lea     r8, asc_180020348; "    "
0x180003df4  mov     rdx, rsi; unsigned __int16 *
0x180003df7  mov     rcx, rax; this
0x180003dfa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003dff  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003e03  test    r9, r9
0x180003e06  jz      short loc_180003E1A
0x180003e08  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003e0f  mov     rdx, rsi; unsigned __int16 *
0x180003e12  mov     rcx, rax; this
0x180003e15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003e1a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003e1e  test    r9, r9
0x180003e21  jz      short loc_180003E35
0x180003e23  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003e2a  mov     rdx, rsi; unsigned __int16 *
0x180003e2d  mov     rcx, rax; this
0x180003e30  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003e35  mov     rcx, [rbx+28h]
0x180003e39  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003e3d  mov     rdx, rsi; unsigned __int16 *
0x180003e40  test    rcx, rcx
0x180003e43  jz      short loc_180003E5B
0x180003e45  mov     [rsp+278h+lpBuffer], rcx
0x180003e4a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003e51  mov     rcx, rax; this
0x180003e54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003e59  jmp     short loc_180003E7D
0x180003e5b  mov     rcx, rax; this
0x180003e5e  test    r9, r9
0x180003e61  jz      short loc_180003E71
0x180003e63  lea     r8, aHs; "[%hs]\n"
0x180003e6a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003e6f  jmp     short loc_180003E7D
0x180003e71  lea     r8, OutputString; "\n"
0x180003e78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003e7d  xor     eax, eax
0x180003e7f  mov     rcx, [rsp+278h+var_38]
0x180003e87  xor     rcx, rsp; StackCookie
0x180003e8a  call    __security_check_cookie
0x180003e8f  mov     rbx, [rsp+278h+arg_18]
0x180003e97  add     rsp, 250h
0x180003e9e  pop     r15
0x180003ea0  pop     r14
0x180003ea2  pop     rdi
0x180003ea3  pop     rsi
0x180003ea4  pop     rbp
0x180003ea5  retn
```
