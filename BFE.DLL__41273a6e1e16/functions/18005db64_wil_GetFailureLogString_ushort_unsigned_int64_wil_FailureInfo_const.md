# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18005db64`
- end: `0x18005de27`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180056574`
- `0x18005e914`
- `0x180060e50`

## callees

- `0x18005aa60`
- `0x18005b4fc`
- `0x18005db64`
- `0x18005e618`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dd1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dd1d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18005dc96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18005dc96`

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
          v7 = (const char *)&byte_1800C251D;
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
0x18005db64  mov     [rsp+arg_18], rbx
0x18005db69  push    rbp
0x18005db6a  push    rsi
0x18005db6b  push    rdi
0x18005db6c  push    r14
0x18005db6e  push    r15
0x18005db70  sub     rsp, 250h
0x18005db77  mov     rax, cs:__security_cookie
0x18005db7e  xor     rax, rsp
0x18005db81  mov     [rsp+278h+var_38], rax
0x18005db89  mov     rbx, r8
0x18005db8c  mov     rsi, rdx
0x18005db8f  mov     r14, rcx
0x18005db92  xor     r15d, r15d
0x18005db95  test    rdx, rdx
0x18005db98  jz      loc_18005DDFD
0x18005db9e  test    rcx, rcx
0x18005dba1  jz      loc_18005DDFD
0x18005dba7  mov     [rcx], r15w
0x18005dbab  mov     rax, cs:g_pfnResultLoggingCallback
0x18005dbb2  test    rax, rax
0x18005dbb5  jz      short loc_18005DBD8
0x18005dbb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005dbbe  jz      short loc_18005DBD8
0x18005dbc0  mov     r8, rdx
0x18005dbc3  mov     rdx, rcx
0x18005dbc6  mov     rcx, rbx
0x18005dbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dbce  cmp     [r14], r15w
0x18005dbd2  jnz     loc_18005DDFD
0x18005dbd8  mov     ecx, [rbx]
0x18005dbda  mov     bpl, 8
0x18005dbdd  test    ecx, ecx
0x18005dbdf  jz      short loc_18005DC2A
0x18005dbe1  sub     ecx, 1
0x18005dbe4  jz      short loc_18005DC12
0x18005dbe6  sub     ecx, 1
0x18005dbe9  jz      short loc_18005DC02
0x18005dbeb  cmp     ecx, 1
0x18005dbee  jz      short loc_18005DBF9
0x18005dbf0  lea     rdi, byte_1800C251D
0x18005dbf7  jmp     short loc_18005DC31
0x18005dbf9  lea     rdi, aFailfast; "FailFast"
0x18005dc00  jmp     short loc_18005DC31
0x18005dc02  lea     rax, aLoghr; "LogHr"
0x18005dc09  lea     rdi, aLognt; "LogNt"
0x18005dc10  jmp     short loc_18005DC20
0x18005dc12  lea     rax, aReturnhr; "ReturnHr"
0x18005dc19  lea     rdi, aReturnnt; "ReturnNt"
0x18005dc20  test    [rbx+4], bpl
0x18005dc24  cmovz   rdi, rax
0x18005dc28  jmp     short loc_18005DC31
0x18005dc2a  lea     rdi, aException; "Exception"
0x18005dc31  xor     edx, edx; Val
0x18005dc33  mov     r8d, 200h; Size
0x18005dc39  lea     rcx, [rsp+278h+Buffer]; void *
0x18005dc3e  call    memset_0
0x18005dc43  test    [rbx+4], bpl
0x18005dc47  jz      short loc_18005DC6C
0x18005dc49  mov     ebp, [rbx+0Ch]
0x18005dc4c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18005dc53  test    rax, rax
0x18005dc56  jz      short loc_18005DCA2
0x18005dc58  mov     r8d, 100h
0x18005dc5e  lea     rdx, [rsp+278h+Buffer]
0x18005dc63  mov     ecx, ebp
0x18005dc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc6a  jmp     short loc_18005DCA2
0x18005dc6c  mov     ebp, [rbx+8]
0x18005dc6f  mov     [rsp+278h+Arguments], r15; Arguments
0x18005dc74  mov     [rsp+278h+nSize], 100h; nSize
0x18005dc7c  lea     rax, [rsp+278h+Buffer]
0x18005dc81  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18005dc86  mov     r9d, 400h; dwLanguageId
0x18005dc8c  mov     r8d, ebp; dwMessageId
0x18005dc8f  xor     edx, edx; lpSource
0x18005dc91  mov     ecx, 1200h; dwFlags
0x18005dc96  call    cs:__imp_FormatMessageW
0x18005dc9d  nop     dword ptr [rax+rax+00h]
0x18005dca2  lea     rsi, [r14+rsi*2]
0x18005dca6  mov     r9, [rbx+38h]; unsigned __int16 *
0x18005dcaa  mov     rax, [rbx+88h]
0x18005dcb1  mov     rcx, [rbx+80h]
0x18005dcb8  mov     rdx, rsi; unsigned __int16 *
0x18005dcbb  test    r9, r9
0x18005dcbe  jz      short loc_18005DCE2
0x18005dcc0  mov     [rsp+278h+Arguments], rax
0x18005dcc5  mov     qword ptr [rsp+278h+nSize], rcx
0x18005dcca  mov     eax, [rbx+40h]
0x18005dccd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18005dcd1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18005dcd8  mov     rcx, r14; this
0x18005dcdb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005dce0  jmp     short loc_18005DCF9
0x18005dce2  mov     [rsp+278h+lpBuffer], rax
0x18005dce7  mov     r9, rcx; unsigned __int16 *
0x18005dcea  lea     r8, aHsP; "%hs!%p: "
0x18005dcf1  mov     rcx, r14; this
0x18005dcf4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005dcf9  mov     r14, rax
0x18005dcfc  mov     r9, [rbx+90h]; unsigned __int16 *
0x18005dd03  test    r9, r9
0x18005dd06  jz      short loc_18005DD1D
0x18005dd08  lea     r8, aCallerP; "(caller: %p) "
0x18005dd0f  mov     rdx, rsi; unsigned __int16 *
0x18005dd12  mov     rcx, rax; this
0x18005dd15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005dd1a  mov     r14, rax
0x18005dd1d  call    cs:__imp_GetCurrentThreadId
0x18005dd24  nop     dword ptr [rax+rax+00h]
0x18005dd29  lea     rcx, [rsp+278h+Buffer]
0x18005dd2e  mov     [rsp+278h+var_240], rcx
0x18005dd33  mov     dword ptr [rsp+278h+Arguments], ebp
0x18005dd37  mov     [rsp+278h+nSize], eax
0x18005dd3b  mov     eax, [rbx+44h]
0x18005dd3e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18005dd42  mov     r9, rdi; unsigned __int16 *
0x18005dd45  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18005dd4c  mov     rdx, rsi; unsigned __int16 *
0x18005dd4f  mov     rcx, r14; this
0x18005dd52  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005dd57  cmp     [rbx+18h], r15
0x18005dd5b  jnz     short loc_18005DD6D
0x18005dd5d  cmp     [rbx+48h], r15
0x18005dd61  jnz     short loc_18005DD6D
0x18005dd63  cmp     [rbx+30h], r15
0x18005dd67  jz      loc_18005DDFD
0x18005dd6d  lea     r8, asc_1800B6728; "    "
0x18005dd74  mov     rdx, rsi; unsigned __int16 *
0x18005dd77  mov     rcx, rax; this
0x18005dd7a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005dd7f  mov     r9, [rbx+18h]; unsigned __int16 *
0x18005dd83  test    r9, r9
0x18005dd86  jz      short loc_18005DD9A
0x18005dd88  lea     r8, aMsgWs; "Msg:[%ws] "
0x18005dd8f  mov     rdx, rsi; unsigned __int16 *
0x18005dd92  mov     rcx, rax; this
0x18005dd95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005dd9a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18005dd9e  test    r9, r9
0x18005dda1  jz      short loc_18005DDB5
0x18005dda3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18005ddaa  mov     rdx, rsi; unsigned __int16 *
0x18005ddad  mov     rcx, rax; this
0x18005ddb0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005ddb5  mov     rcx, [rbx+28h]
0x18005ddb9  mov     r9, [rbx+30h]; unsigned __int16 *
0x18005ddbd  mov     rdx, rsi; unsigned __int16 *
0x18005ddc0  test    rcx, rcx
0x18005ddc3  jz      short loc_18005DDDB
0x18005ddc5  mov     [rsp+278h+lpBuffer], rcx
0x18005ddca  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18005ddd1  mov     rcx, rax; this
0x18005ddd4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005ddd9  jmp     short loc_18005DDFD
0x18005dddb  mov     rcx, rax; this
0x18005ddde  test    r9, r9
0x18005dde1  jz      short loc_18005DDF1
0x18005dde3  lea     r8, aHs; "[%hs]\n"
0x18005ddea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005ddef  jmp     short loc_18005DDFD
0x18005ddf1  lea     r8, asc_1800B5D6C; "\n"
0x18005ddf8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005ddfd  xor     eax, eax
0x18005ddff  mov     rcx, [rsp+278h+var_38]
0x18005de07  xor     rcx, rsp; StackCookie
0x18005de0a  call    __security_check_cookie
0x18005de0f  mov     rbx, [rsp+278h+arg_18]
0x18005de17  add     rsp, 250h
0x18005de1e  pop     r15
0x18005de20  pop     r14
0x18005de22  pop     rdi
0x18005de23  pop     rsi
0x18005de24  pop     rbp
0x18005de25  retn
```
