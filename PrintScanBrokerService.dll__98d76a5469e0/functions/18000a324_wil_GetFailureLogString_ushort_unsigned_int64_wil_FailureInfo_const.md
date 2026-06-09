# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000a324`
- end: `0x18000a5da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005998`
- `0x18000b884`
- `0x18000bf5c`
- `0x180011690`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000a324`
- `0x18000bb84`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a4d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a4d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a456`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a456`

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
          v7 = (const char *)&dword_18004B9CC;
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
0x18000a324  mov     [rsp+arg_18], rbx
0x18000a329  push    rbp
0x18000a32a  push    rsi
0x18000a32b  push    rdi
0x18000a32c  push    r14
0x18000a32e  push    r15
0x18000a330  sub     rsp, 250h
0x18000a337  mov     rax, cs:__security_cookie
0x18000a33e  xor     rax, rsp
0x18000a341  mov     [rsp+278h+var_38], rax
0x18000a349  mov     rbx, r8
0x18000a34c  mov     rsi, rdx
0x18000a34f  mov     r14, rcx
0x18000a352  xor     r15d, r15d
0x18000a355  test    rdx, rdx
0x18000a358  jz      loc_18000A5B1
0x18000a35e  test    rcx, rcx
0x18000a361  jz      loc_18000A5B1
0x18000a367  mov     [rcx], r15w
0x18000a36b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a372  test    rax, rax
0x18000a375  jz      short loc_18000A398
0x18000a377  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a37e  jz      short loc_18000A398
0x18000a380  mov     r8, rdx
0x18000a383  mov     rdx, rcx
0x18000a386  mov     rcx, rbx
0x18000a389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a38e  cmp     [r14], r15w
0x18000a392  jnz     loc_18000A5B1
0x18000a398  mov     ecx, [rbx]
0x18000a39a  mov     bpl, 8
0x18000a39d  test    ecx, ecx
0x18000a39f  jz      short loc_18000A3EA
0x18000a3a1  sub     ecx, 1
0x18000a3a4  jz      short loc_18000A3D2
0x18000a3a6  sub     ecx, 1
0x18000a3a9  jz      short loc_18000A3C2
0x18000a3ab  cmp     ecx, 1
0x18000a3ae  jz      short loc_18000A3B9
0x18000a3b0  lea     rdi, dword_18004B9CC
0x18000a3b7  jmp     short loc_18000A3F1
0x18000a3b9  lea     rdi, aFailfast; "FailFast"
0x18000a3c0  jmp     short loc_18000A3F1
0x18000a3c2  lea     rax, aLoghr; "LogHr"
0x18000a3c9  lea     rdi, aLognt; "LogNt"
0x18000a3d0  jmp     short loc_18000A3E0
0x18000a3d2  lea     rax, aReturnhr; "ReturnHr"
0x18000a3d9  lea     rdi, aReturnnt; "ReturnNt"
0x18000a3e0  test    [rbx+4], bpl
0x18000a3e4  cmovz   rdi, rax
0x18000a3e8  jmp     short loc_18000A3F1
0x18000a3ea  lea     rdi, aException; "Exception"
0x18000a3f1  xor     edx, edx; Val
0x18000a3f3  mov     r8d, 200h; Size
0x18000a3f9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000a3fe  call    memset_0
0x18000a403  test    [rbx+4], bpl
0x18000a407  jz      short loc_18000A42C
0x18000a409  mov     ebp, [rbx+0Ch]
0x18000a40c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000a413  test    rax, rax
0x18000a416  jz      short loc_18000A45C
0x18000a418  mov     r8d, 100h
0x18000a41e  lea     rdx, [rsp+278h+Buffer]
0x18000a423  mov     ecx, ebp
0x18000a425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a42a  jmp     short loc_18000A45C
0x18000a42c  mov     ebp, [rbx+8]
0x18000a42f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000a434  mov     [rsp+278h+nSize], 100h; nSize
0x18000a43c  lea     rax, [rsp+278h+Buffer]
0x18000a441  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000a446  mov     r9d, 400h; dwLanguageId
0x18000a44c  mov     r8d, ebp; dwMessageId
0x18000a44f  xor     edx, edx; lpSource
0x18000a451  mov     ecx, 1200h; dwFlags
0x18000a456  call    cs:__imp_FormatMessageW
0x18000a45c  lea     rsi, [r14+rsi*2]
0x18000a460  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000a464  mov     rax, [rbx+88h]
0x18000a46b  mov     rcx, [rbx+80h]
0x18000a472  mov     rdx, rsi; unsigned __int16 *
0x18000a475  test    r9, r9
0x18000a478  jz      short loc_18000A49C
0x18000a47a  mov     [rsp+278h+Arguments], rax
0x18000a47f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000a484  mov     eax, [rbx+40h]
0x18000a487  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a48b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000a492  mov     rcx, r14; this
0x18000a495  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a49a  jmp     short loc_18000A4B3
0x18000a49c  mov     [rsp+278h+lpBuffer], rax
0x18000a4a1  mov     r9, rcx; unsigned __int16 *
0x18000a4a4  lea     r8, aHsP; "%hs!%p: "
0x18000a4ab  mov     rcx, r14; this
0x18000a4ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a4b3  mov     r14, rax
0x18000a4b6  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000a4bd  test    r9, r9
0x18000a4c0  jz      short loc_18000A4D7
0x18000a4c2  lea     r8, aCallerP; "(caller: %p) "
0x18000a4c9  mov     rdx, rsi; unsigned __int16 *
0x18000a4cc  mov     rcx, rax; this
0x18000a4cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a4d4  mov     r14, rax
0x18000a4d7  call    cs:__imp_GetCurrentThreadId
0x18000a4dd  lea     rcx, [rsp+278h+Buffer]
0x18000a4e2  mov     [rsp+278h+var_240], rcx
0x18000a4e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000a4eb  mov     [rsp+278h+nSize], eax
0x18000a4ef  mov     eax, [rbx+44h]
0x18000a4f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a4f6  mov     r9, rdi; unsigned __int16 *
0x18000a4f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000a500  mov     rdx, rsi; unsigned __int16 *
0x18000a503  mov     rcx, r14; this
0x18000a506  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a50b  cmp     [rbx+18h], r15
0x18000a50f  jnz     short loc_18000A521
0x18000a511  cmp     [rbx+48h], r15
0x18000a515  jnz     short loc_18000A521
0x18000a517  cmp     [rbx+30h], r15
0x18000a51b  jz      loc_18000A5B1
0x18000a521  lea     r8, asc_18004BB00; "    "
0x18000a528  mov     rdx, rsi; unsigned __int16 *
0x18000a52b  mov     rcx, rax; this
0x18000a52e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a533  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000a537  test    r9, r9
0x18000a53a  jz      short loc_18000A54E
0x18000a53c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000a543  mov     rdx, rsi; unsigned __int16 *
0x18000a546  mov     rcx, rax; this
0x18000a549  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a54e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000a552  test    r9, r9
0x18000a555  jz      short loc_18000A569
0x18000a557  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000a55e  mov     rdx, rsi; unsigned __int16 *
0x18000a561  mov     rcx, rax; this
0x18000a564  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a569  mov     rcx, [rbx+28h]
0x18000a56d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000a571  mov     rdx, rsi; unsigned __int16 *
0x18000a574  test    rcx, rcx
0x18000a577  jz      short loc_18000A58F
0x18000a579  mov     [rsp+278h+lpBuffer], rcx
0x18000a57e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000a585  mov     rcx, rax; this
0x18000a588  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a58d  jmp     short loc_18000A5B1
0x18000a58f  mov     rcx, rax; this
0x18000a592  test    r9, r9
0x18000a595  jz      short loc_18000A5A5
0x18000a597  lea     r8, aHs; "[%hs]\n"
0x18000a59e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a5a3  jmp     short loc_18000A5B1
0x18000a5a5  lea     r8, asc_18004BB78; "\n"
0x18000a5ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a5b1  xor     eax, eax
0x18000a5b3  mov     rcx, [rsp+278h+var_38]
0x18000a5bb  xor     rcx, rsp; StackCookie
0x18000a5be  call    __security_check_cookie
0x18000a5c3  mov     rbx, [rsp+278h+arg_18]
0x18000a5cb  add     rsp, 250h
0x18000a5d2  pop     r15
0x18000a5d4  pop     r14
0x18000a5d6  pop     rdi
0x18000a5d7  pop     rsi
0x18000a5d8  pop     rbp
0x18000a5d9  retn
```
