# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001cc84`
- end: `0x18001cf3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180019d94`
- `0x18001a004`
- `0x18001d6dc`
- `0x180020100`

## callees

- `0x180001870`
- `0x180002420`
- `0x18001cc84`
- `0x18001d9dc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ce37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ce37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001cdb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001cdb6`

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
          v7 = (const char *)&word_18002D655;
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
0x18001cc84  mov     [rsp+arg_18], rbx
0x18001cc89  push    rbp
0x18001cc8a  push    rsi
0x18001cc8b  push    rdi
0x18001cc8c  push    r14
0x18001cc8e  push    r15
0x18001cc90  sub     rsp, 250h
0x18001cc97  mov     rax, cs:__security_cookie
0x18001cc9e  xor     rax, rsp
0x18001cca1  mov     [rsp+278h+var_38], rax
0x18001cca9  mov     rbx, r8
0x18001ccac  mov     rsi, rdx
0x18001ccaf  mov     r14, rcx
0x18001ccb2  xor     r15d, r15d
0x18001ccb5  test    rdx, rdx
0x18001ccb8  jz      loc_18001CF11
0x18001ccbe  test    rcx, rcx
0x18001ccc1  jz      loc_18001CF11
0x18001ccc7  mov     [rcx], r15w
0x18001cccb  mov     rax, cs:g_pfnResultLoggingCallback
0x18001ccd2  test    rax, rax
0x18001ccd5  jz      short loc_18001CCF8
0x18001ccd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001ccde  jz      short loc_18001CCF8
0x18001cce0  mov     r8, rdx
0x18001cce3  mov     rdx, rcx
0x18001cce6  mov     rcx, rbx
0x18001cce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccee  cmp     [r14], r15w
0x18001ccf2  jnz     loc_18001CF11
0x18001ccf8  mov     ecx, [rbx]
0x18001ccfa  mov     bpl, 8
0x18001ccfd  test    ecx, ecx
0x18001ccff  jz      short loc_18001CD4A
0x18001cd01  sub     ecx, 1
0x18001cd04  jz      short loc_18001CD32
0x18001cd06  sub     ecx, 1
0x18001cd09  jz      short loc_18001CD22
0x18001cd0b  cmp     ecx, 1
0x18001cd0e  jz      short loc_18001CD19
0x18001cd10  lea     rdi, word_18002D655
0x18001cd17  jmp     short loc_18001CD51
0x18001cd19  lea     rdi, aFailfast; "FailFast"
0x18001cd20  jmp     short loc_18001CD51
0x18001cd22  lea     rax, aLoghr; "LogHr"
0x18001cd29  lea     rdi, aLognt; "LogNt"
0x18001cd30  jmp     short loc_18001CD40
0x18001cd32  lea     rax, aReturnhr; "ReturnHr"
0x18001cd39  lea     rdi, aReturnnt; "ReturnNt"
0x18001cd40  test    [rbx+4], bpl
0x18001cd44  cmovz   rdi, rax
0x18001cd48  jmp     short loc_18001CD51
0x18001cd4a  lea     rdi, aException; "Exception"
0x18001cd51  xor     edx, edx; Val
0x18001cd53  mov     r8d, 200h; Size
0x18001cd59  lea     rcx, [rsp+278h+Buffer]; void *
0x18001cd5e  call    memset_0
0x18001cd63  test    [rbx+4], bpl
0x18001cd67  jz      short loc_18001CD8C
0x18001cd69  mov     ebp, [rbx+0Ch]
0x18001cd6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001cd73  test    rax, rax
0x18001cd76  jz      short loc_18001CDBC
0x18001cd78  mov     r8d, 100h
0x18001cd7e  lea     rdx, [rsp+278h+Buffer]
0x18001cd83  mov     ecx, ebp
0x18001cd85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd8a  jmp     short loc_18001CDBC
0x18001cd8c  mov     ebp, [rbx+8]
0x18001cd8f  mov     [rsp+278h+Arguments], r15; Arguments
0x18001cd94  mov     [rsp+278h+nSize], 100h; nSize
0x18001cd9c  lea     rax, [rsp+278h+Buffer]
0x18001cda1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001cda6  mov     r9d, 400h; dwLanguageId
0x18001cdac  mov     r8d, ebp; dwMessageId
0x18001cdaf  xor     edx, edx; lpSource
0x18001cdb1  mov     ecx, 1200h; dwFlags
0x18001cdb6  call    cs:__imp_FormatMessageW
0x18001cdbc  lea     rsi, [r14+rsi*2]
0x18001cdc0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001cdc4  mov     rax, [rbx+88h]
0x18001cdcb  mov     rcx, [rbx+80h]
0x18001cdd2  mov     rdx, rsi; unsigned __int16 *
0x18001cdd5  test    r9, r9
0x18001cdd8  jz      short loc_18001CDFC
0x18001cdda  mov     [rsp+278h+Arguments], rax
0x18001cddf  mov     qword ptr [rsp+278h+nSize], rcx
0x18001cde4  mov     eax, [rbx+40h]
0x18001cde7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001cdeb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001cdf2  mov     rcx, r14; this
0x18001cdf5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cdfa  jmp     short loc_18001CE13
0x18001cdfc  mov     [rsp+278h+lpBuffer], rax
0x18001ce01  mov     r9, rcx; unsigned __int16 *
0x18001ce04  lea     r8, aHsP; "%hs!%p: "
0x18001ce0b  mov     rcx, r14; this
0x18001ce0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ce13  mov     r14, rax
0x18001ce16  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001ce1d  test    r9, r9
0x18001ce20  jz      short loc_18001CE37
0x18001ce22  lea     r8, aCallerP; "(caller: %p) "
0x18001ce29  mov     rdx, rsi; unsigned __int16 *
0x18001ce2c  mov     rcx, rax; this
0x18001ce2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ce34  mov     r14, rax
0x18001ce37  call    cs:__imp_GetCurrentThreadId
0x18001ce3d  lea     rcx, [rsp+278h+Buffer]
0x18001ce42  mov     [rsp+278h+var_240], rcx
0x18001ce47  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001ce4b  mov     [rsp+278h+nSize], eax
0x18001ce4f  mov     eax, [rbx+44h]
0x18001ce52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001ce56  mov     r9, rdi; unsigned __int16 *
0x18001ce59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001ce60  mov     rdx, rsi; unsigned __int16 *
0x18001ce63  mov     rcx, r14; this
0x18001ce66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ce6b  cmp     [rbx+18h], r15
0x18001ce6f  jnz     short loc_18001CE81
0x18001ce71  cmp     [rbx+48h], r15
0x18001ce75  jnz     short loc_18001CE81
0x18001ce77  cmp     [rbx+30h], r15
0x18001ce7b  jz      loc_18001CF11
0x18001ce81  lea     r8, asc_18002E748; "    "
0x18001ce88  mov     rdx, rsi; unsigned __int16 *
0x18001ce8b  mov     rcx, rax; this
0x18001ce8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ce93  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001ce97  test    r9, r9
0x18001ce9a  jz      short loc_18001CEAE
0x18001ce9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001cea3  mov     rdx, rsi; unsigned __int16 *
0x18001cea6  mov     rcx, rax; this
0x18001cea9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ceae  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001ceb2  test    r9, r9
0x18001ceb5  jz      short loc_18001CEC9
0x18001ceb7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001cebe  mov     rdx, rsi; unsigned __int16 *
0x18001cec1  mov     rcx, rax; this
0x18001cec4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cec9  mov     rcx, [rbx+28h]
0x18001cecd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001ced1  mov     rdx, rsi; unsigned __int16 *
0x18001ced4  test    rcx, rcx
0x18001ced7  jz      short loc_18001CEEF
0x18001ced9  mov     [rsp+278h+lpBuffer], rcx
0x18001cede  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001cee5  mov     rcx, rax; this
0x18001cee8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ceed  jmp     short loc_18001CF11
0x18001ceef  mov     rcx, rax; this
0x18001cef2  test    r9, r9
0x18001cef5  jz      short loc_18001CF05
0x18001cef7  lea     r8, aHs; "[%hs]\n"
0x18001cefe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cf03  jmp     short loc_18001CF11
0x18001cf05  lea     r8, asc_18002E7C0; "\n"
0x18001cf0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001cf11  xor     eax, eax
0x18001cf13  mov     rcx, [rsp+278h+var_38]
0x18001cf1b  xor     rcx, rsp; StackCookie
0x18001cf1e  call    __security_check_cookie
0x18001cf23  mov     rbx, [rsp+278h+arg_18]
0x18001cf2b  add     rsp, 250h
0x18001cf32  pop     r15
0x18001cf34  pop     r14
0x18001cf36  pop     rdi
0x18001cf37  pop     rsi
0x18001cf38  pop     rbp
0x18001cf39  retn
```
