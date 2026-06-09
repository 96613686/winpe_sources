# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004994`
- end: `0x180004c4a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003220`
- `0x1800034a0`
- `0x1800054b8`
- `0x180007780`
- `0x180007eec`
- `0x18000c9cf`
- `0x18000cb03`

## callees

- `0x180004994`
- `0x1800057b8`
- `0x18000c4f2`
- `0x18000c530`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b47`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ac6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ac6`

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
          v7 = (const char *)&byte_180010F60;
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
0x180004994  mov     [rsp+arg_18], rbx
0x180004999  push    rbp
0x18000499a  push    rsi
0x18000499b  push    rdi
0x18000499c  push    r14
0x18000499e  push    r15
0x1800049a0  sub     rsp, 250h
0x1800049a7  mov     rax, cs:__security_cookie
0x1800049ae  xor     rax, rsp
0x1800049b1  mov     [rsp+278h+var_38], rax
0x1800049b9  mov     rbx, r8
0x1800049bc  mov     rsi, rdx
0x1800049bf  mov     r14, rcx
0x1800049c2  xor     r15d, r15d
0x1800049c5  test    rdx, rdx
0x1800049c8  jz      loc_180004C21
0x1800049ce  test    rcx, rcx
0x1800049d1  jz      loc_180004C21
0x1800049d7  mov     [rcx], r15w
0x1800049db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800049e2  test    rax, rax
0x1800049e5  jz      short loc_180004A08
0x1800049e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800049ee  jz      short loc_180004A08
0x1800049f0  mov     r8, rdx
0x1800049f3  mov     rdx, rcx
0x1800049f6  mov     rcx, rbx
0x1800049f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049fe  cmp     [r14], r15w
0x180004a02  jnz     loc_180004C21
0x180004a08  mov     ecx, [rbx]
0x180004a0a  mov     bpl, 8
0x180004a0d  test    ecx, ecx
0x180004a0f  jz      short loc_180004A5A
0x180004a11  sub     ecx, 1
0x180004a14  jz      short loc_180004A42
0x180004a16  sub     ecx, 1
0x180004a19  jz      short loc_180004A32
0x180004a1b  cmp     ecx, 1
0x180004a1e  jz      short loc_180004A29
0x180004a20  lea     rdi, byte_180010F60
0x180004a27  jmp     short loc_180004A61
0x180004a29  lea     rdi, aFailfast; "FailFast"
0x180004a30  jmp     short loc_180004A61
0x180004a32  lea     rax, aLoghr; "LogHr"
0x180004a39  lea     rdi, aLognt; "LogNt"
0x180004a40  jmp     short loc_180004A50
0x180004a42  lea     rax, aReturnhr; "ReturnHr"
0x180004a49  lea     rdi, aReturnnt; "ReturnNt"
0x180004a50  test    [rbx+4], bpl
0x180004a54  cmovz   rdi, rax
0x180004a58  jmp     short loc_180004A61
0x180004a5a  lea     rdi, aException; "Exception"
0x180004a61  xor     edx, edx; Val
0x180004a63  mov     r8d, 200h; Size
0x180004a69  lea     rcx, [rsp+278h+Buffer]; void *
0x180004a6e  call    memset_0
0x180004a73  test    [rbx+4], bpl
0x180004a77  jz      short loc_180004A9C
0x180004a79  mov     ebp, [rbx+0Ch]
0x180004a7c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004a83  test    rax, rax
0x180004a86  jz      short loc_180004ACC
0x180004a88  mov     r8d, 100h
0x180004a8e  lea     rdx, [rsp+278h+Buffer]
0x180004a93  mov     ecx, ebp
0x180004a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a9a  jmp     short loc_180004ACC
0x180004a9c  mov     ebp, [rbx+8]
0x180004a9f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004aa4  mov     [rsp+278h+nSize], 100h; nSize
0x180004aac  lea     rax, [rsp+278h+Buffer]
0x180004ab1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004ab6  mov     r9d, 400h; dwLanguageId
0x180004abc  mov     r8d, ebp; dwMessageId
0x180004abf  xor     edx, edx; lpSource
0x180004ac1  mov     ecx, 1200h; dwFlags
0x180004ac6  call    cs:__imp_FormatMessageW
0x180004acc  lea     rsi, [r14+rsi*2]
0x180004ad0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004ad4  mov     rax, [rbx+88h]
0x180004adb  mov     rcx, [rbx+80h]
0x180004ae2  mov     rdx, rsi; unsigned __int16 *
0x180004ae5  test    r9, r9
0x180004ae8  jz      short loc_180004B0C
0x180004aea  mov     [rsp+278h+Arguments], rax
0x180004aef  mov     qword ptr [rsp+278h+nSize], rcx
0x180004af4  mov     eax, [rbx+40h]
0x180004af7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004afb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004b02  mov     rcx, r14; this
0x180004b05  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b0a  jmp     short loc_180004B23
0x180004b0c  mov     [rsp+278h+lpBuffer], rax
0x180004b11  mov     r9, rcx; unsigned __int16 *
0x180004b14  lea     r8, aHsP; "%hs!%p: "
0x180004b1b  mov     rcx, r14; this
0x180004b1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b23  mov     r14, rax
0x180004b26  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004b2d  test    r9, r9
0x180004b30  jz      short loc_180004B47
0x180004b32  lea     r8, aCallerP; "(caller: %p) "
0x180004b39  mov     rdx, rsi; unsigned __int16 *
0x180004b3c  mov     rcx, rax; this
0x180004b3f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b44  mov     r14, rax
0x180004b47  call    cs:__imp_GetCurrentThreadId
0x180004b4d  lea     rcx, [rsp+278h+Buffer]
0x180004b52  mov     [rsp+278h+var_240], rcx
0x180004b57  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004b5b  mov     [rsp+278h+nSize], eax
0x180004b5f  mov     eax, [rbx+44h]
0x180004b62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004b66  mov     r9, rdi; unsigned __int16 *
0x180004b69  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004b70  mov     rdx, rsi; unsigned __int16 *
0x180004b73  mov     rcx, r14; this
0x180004b76  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b7b  cmp     [rbx+18h], r15
0x180004b7f  jnz     short loc_180004B91
0x180004b81  cmp     [rbx+48h], r15
0x180004b85  jnz     short loc_180004B91
0x180004b87  cmp     [rbx+30h], r15
0x180004b8b  jz      loc_180004C21
0x180004b91  lea     r8, asc_180011050; "    "
0x180004b98  mov     rdx, rsi; unsigned __int16 *
0x180004b9b  mov     rcx, rax; this
0x180004b9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ba3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004ba7  test    r9, r9
0x180004baa  jz      short loc_180004BBE
0x180004bac  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004bb3  mov     rdx, rsi; unsigned __int16 *
0x180004bb6  mov     rcx, rax; this
0x180004bb9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bbe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004bc2  test    r9, r9
0x180004bc5  jz      short loc_180004BD9
0x180004bc7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004bce  mov     rdx, rsi; unsigned __int16 *
0x180004bd1  mov     rcx, rax; this
0x180004bd4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bd9  mov     rcx, [rbx+28h]
0x180004bdd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004be1  mov     rdx, rsi; unsigned __int16 *
0x180004be4  test    rcx, rcx
0x180004be7  jz      short loc_180004BFF
0x180004be9  mov     [rsp+278h+lpBuffer], rcx
0x180004bee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004bf5  mov     rcx, rax; this
0x180004bf8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bfd  jmp     short loc_180004C21
0x180004bff  mov     rcx, rax; this
0x180004c02  test    r9, r9
0x180004c05  jz      short loc_180004C15
0x180004c07  lea     r8, aHs; "[%hs]\n"
0x180004c0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c13  jmp     short loc_180004C21
0x180004c15  lea     r8, asc_1800110C8; "\n"
0x180004c1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c21  xor     eax, eax
0x180004c23  mov     rcx, [rsp+278h+var_38]
0x180004c2b  xor     rcx, rsp; StackCookie
0x180004c2e  call    __security_check_cookie
0x180004c33  mov     rbx, [rsp+278h+arg_18]
0x180004c3b  add     rsp, 250h
0x180004c42  pop     r15
0x180004c44  pop     r14
0x180004c46  pop     rdi
0x180004c47  pop     rsi
0x180004c48  pop     rbp
0x180004c49  retn
```
