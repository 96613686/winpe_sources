# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009a20`
- end: `0x180009cd6`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004ae4`
- `0x180004d4c`
- `0x18000bb60`
- `0x180011fd0`

## callees

- `0x180009a20`
- `0x18000be60`
- `0x1800142d2`
- `0x180014310`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009bd3`
- `KERNEL32!GetCurrentThreadId` at `0x180009bd3`
- `KERNEL32!FormatMessageW` at `0x180009b52`
- `KERNEL32!FormatMessageW` at `0x180009b52`

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
          v7 = (const char *)&byte_180018980;
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
0x180009a20  mov     [rsp+arg_18], rbx
0x180009a25  push    rbp
0x180009a26  push    rsi
0x180009a27  push    rdi
0x180009a28  push    r14
0x180009a2a  push    r15
0x180009a2c  sub     rsp, 250h
0x180009a33  mov     rax, cs:__security_cookie
0x180009a3a  xor     rax, rsp
0x180009a3d  mov     [rsp+278h+var_38], rax
0x180009a45  mov     rbx, r8
0x180009a48  mov     rsi, rdx
0x180009a4b  mov     r14, rcx
0x180009a4e  xor     r15d, r15d
0x180009a51  test    rdx, rdx
0x180009a54  jz      loc_180009CAD
0x180009a5a  test    rcx, rcx
0x180009a5d  jz      loc_180009CAD
0x180009a63  mov     [rcx], r15w
0x180009a67  mov     rax, cs:g_pfnResultLoggingCallback
0x180009a6e  test    rax, rax
0x180009a71  jz      short loc_180009A94
0x180009a73  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009a7a  jz      short loc_180009A94
0x180009a7c  mov     r8, rdx
0x180009a7f  mov     rdx, rcx
0x180009a82  mov     rcx, rbx
0x180009a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8a  cmp     [r14], r15w
0x180009a8e  jnz     loc_180009CAD
0x180009a94  mov     ecx, [rbx]
0x180009a96  mov     bpl, 8
0x180009a99  test    ecx, ecx
0x180009a9b  jz      short loc_180009AE6
0x180009a9d  sub     ecx, 1
0x180009aa0  jz      short loc_180009ACE
0x180009aa2  sub     ecx, 1
0x180009aa5  jz      short loc_180009ABE
0x180009aa7  cmp     ecx, 1
0x180009aaa  jz      short loc_180009AB5
0x180009aac  lea     rdi, byte_180018980
0x180009ab3  jmp     short loc_180009AED
0x180009ab5  lea     rdi, aFailfast; "FailFast"
0x180009abc  jmp     short loc_180009AED
0x180009abe  lea     rax, aLoghr; "LogHr"
0x180009ac5  lea     rdi, aLognt; "LogNt"
0x180009acc  jmp     short loc_180009ADC
0x180009ace  lea     rax, aReturnhr; "ReturnHr"
0x180009ad5  lea     rdi, aReturnnt; "ReturnNt"
0x180009adc  test    [rbx+4], bpl
0x180009ae0  cmovz   rdi, rax
0x180009ae4  jmp     short loc_180009AED
0x180009ae6  lea     rdi, aException; "Exception"
0x180009aed  xor     edx, edx; Val
0x180009aef  mov     r8d, 200h; Size
0x180009af5  lea     rcx, [rsp+278h+Buffer]; void *
0x180009afa  call    memset_0
0x180009aff  test    [rbx+4], bpl
0x180009b03  jz      short loc_180009B28
0x180009b05  mov     ebp, [rbx+0Ch]
0x180009b08  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009b0f  test    rax, rax
0x180009b12  jz      short loc_180009B58
0x180009b14  mov     r8d, 100h
0x180009b1a  lea     rdx, [rsp+278h+Buffer]
0x180009b1f  mov     ecx, ebp
0x180009b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b26  jmp     short loc_180009B58
0x180009b28  mov     ebp, [rbx+8]
0x180009b2b  mov     [rsp+278h+Arguments], r15; Arguments
0x180009b30  mov     [rsp+278h+nSize], 100h; nSize
0x180009b38  lea     rax, [rsp+278h+Buffer]
0x180009b3d  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009b42  mov     r9d, 400h; dwLanguageId
0x180009b48  mov     r8d, ebp; dwMessageId
0x180009b4b  xor     edx, edx; lpSource
0x180009b4d  mov     ecx, 1200h; dwFlags
0x180009b52  call    cs:__imp_FormatMessageW
0x180009b58  lea     rsi, [r14+rsi*2]
0x180009b5c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009b60  mov     rax, [rbx+88h]
0x180009b67  mov     rcx, [rbx+80h]
0x180009b6e  mov     rdx, rsi; unsigned __int16 *
0x180009b71  test    r9, r9
0x180009b74  jz      short loc_180009B98
0x180009b76  mov     [rsp+278h+Arguments], rax
0x180009b7b  mov     qword ptr [rsp+278h+nSize], rcx
0x180009b80  mov     eax, [rbx+40h]
0x180009b83  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009b87  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009b8e  mov     rcx, r14; this
0x180009b91  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009b96  jmp     short loc_180009BAF
0x180009b98  mov     [rsp+278h+lpBuffer], rax
0x180009b9d  mov     r9, rcx; unsigned __int16 *
0x180009ba0  lea     r8, aHsP; "%hs!%p: "
0x180009ba7  mov     rcx, r14; this
0x180009baa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009baf  mov     r14, rax
0x180009bb2  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009bb9  test    r9, r9
0x180009bbc  jz      short loc_180009BD3
0x180009bbe  lea     r8, aCallerP; "(caller: %p) "
0x180009bc5  mov     rdx, rsi; unsigned __int16 *
0x180009bc8  mov     rcx, rax; this
0x180009bcb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009bd0  mov     r14, rax
0x180009bd3  call    cs:__imp_GetCurrentThreadId
0x180009bd9  lea     rcx, [rsp+278h+Buffer]
0x180009bde  mov     [rsp+278h+var_240], rcx
0x180009be3  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009be7  mov     [rsp+278h+nSize], eax
0x180009beb  mov     eax, [rbx+44h]
0x180009bee  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009bf2  mov     r9, rdi; unsigned __int16 *
0x180009bf5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009bfc  mov     rdx, rsi; unsigned __int16 *
0x180009bff  mov     rcx, r14; this
0x180009c02  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c07  cmp     [rbx+18h], r15
0x180009c0b  jnz     short loc_180009C1D
0x180009c0d  cmp     [rbx+48h], r15
0x180009c11  jnz     short loc_180009C1D
0x180009c13  cmp     [rbx+30h], r15
0x180009c17  jz      loc_180009CAD
0x180009c1d  lea     r8, asc_180018AF0; "    "
0x180009c24  mov     rdx, rsi; unsigned __int16 *
0x180009c27  mov     rcx, rax; this
0x180009c2a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c2f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009c33  test    r9, r9
0x180009c36  jz      short loc_180009C4A
0x180009c38  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009c3f  mov     rdx, rsi; unsigned __int16 *
0x180009c42  mov     rcx, rax; this
0x180009c45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c4a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009c4e  test    r9, r9
0x180009c51  jz      short loc_180009C65
0x180009c53  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009c5a  mov     rdx, rsi; unsigned __int16 *
0x180009c5d  mov     rcx, rax; this
0x180009c60  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c65  mov     rcx, [rbx+28h]
0x180009c69  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009c6d  mov     rdx, rsi; unsigned __int16 *
0x180009c70  test    rcx, rcx
0x180009c73  jz      short loc_180009C8B
0x180009c75  mov     [rsp+278h+lpBuffer], rcx
0x180009c7a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009c81  mov     rcx, rax; this
0x180009c84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c89  jmp     short loc_180009CAD
0x180009c8b  mov     rcx, rax; this
0x180009c8e  test    r9, r9
0x180009c91  jz      short loc_180009CA1
0x180009c93  lea     r8, aHs; "[%hs]\n"
0x180009c9a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c9f  jmp     short loc_180009CAD
0x180009ca1  lea     r8, asc_180018B68; "\n"
0x180009ca8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cad  xor     eax, eax
0x180009caf  mov     rcx, [rsp+278h+var_38]
0x180009cb7  xor     rcx, rsp; StackCookie
0x180009cba  call    __security_check_cookie
0x180009cbf  mov     rbx, [rsp+278h+arg_18]
0x180009cc7  add     rsp, 250h
0x180009cce  pop     r15
0x180009cd0  pop     r14
0x180009cd2  pop     rdi
0x180009cd3  pop     rsi
0x180009cd4  pop     rbp
0x180009cd5  retn
```
