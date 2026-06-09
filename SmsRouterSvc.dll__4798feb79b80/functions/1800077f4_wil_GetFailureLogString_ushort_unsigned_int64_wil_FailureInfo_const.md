# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800077f4`
- end: `0x180007aaa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180005ea0`
- `0x180006108`
- `0x180008160`
- `0x1800099b0`
- `0x18006b8f5`
- `0x18006ba29`

## callees

- `0x180003a60`
- `0x180004998`
- `0x1800077f4`
- `0x180008460`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007926`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007926`

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
          v7 = (const char *)&dword_18007366C;
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
0x1800077f4  mov     [rsp+arg_18], rbx
0x1800077f9  push    rbp
0x1800077fa  push    rsi
0x1800077fb  push    rdi
0x1800077fc  push    r14
0x1800077fe  push    r15
0x180007800  sub     rsp, 250h
0x180007807  mov     rax, cs:__security_cookie
0x18000780e  xor     rax, rsp
0x180007811  mov     [rsp+278h+var_38], rax
0x180007819  mov     rbx, r8
0x18000781c  mov     rsi, rdx
0x18000781f  mov     r14, rcx
0x180007822  xor     r15d, r15d
0x180007825  test    rdx, rdx
0x180007828  jz      loc_180007A81
0x18000782e  test    rcx, rcx
0x180007831  jz      loc_180007A81
0x180007837  mov     [rcx], r15w
0x18000783b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007842  test    rax, rax
0x180007845  jz      short loc_180007868
0x180007847  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000784e  jz      short loc_180007868
0x180007850  mov     r8, rdx
0x180007853  mov     rdx, rcx
0x180007856  mov     rcx, rbx
0x180007859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785e  cmp     [r14], r15w
0x180007862  jnz     loc_180007A81
0x180007868  mov     ecx, [rbx]
0x18000786a  mov     bpl, 8
0x18000786d  test    ecx, ecx
0x18000786f  jz      short loc_1800078BA
0x180007871  sub     ecx, 1
0x180007874  jz      short loc_1800078A2
0x180007876  sub     ecx, 1
0x180007879  jz      short loc_180007892
0x18000787b  cmp     ecx, 1
0x18000787e  jz      short loc_180007889
0x180007880  lea     rdi, dword_18007366C
0x180007887  jmp     short loc_1800078C1
0x180007889  lea     rdi, aFailfast; "FailFast"
0x180007890  jmp     short loc_1800078C1
0x180007892  lea     rax, aLoghr; "LogHr"
0x180007899  lea     rdi, aLognt; "LogNt"
0x1800078a0  jmp     short loc_1800078B0
0x1800078a2  lea     rax, aReturnhr; "ReturnHr"
0x1800078a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800078b0  test    [rbx+4], bpl
0x1800078b4  cmovz   rdi, rax
0x1800078b8  jmp     short loc_1800078C1
0x1800078ba  lea     rdi, aException; "Exception"
0x1800078c1  xor     edx, edx; Val
0x1800078c3  mov     r8d, 200h; Size
0x1800078c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800078ce  call    memset_0
0x1800078d3  test    [rbx+4], bpl
0x1800078d7  jz      short loc_1800078FC
0x1800078d9  mov     ebp, [rbx+0Ch]
0x1800078dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800078e3  test    rax, rax
0x1800078e6  jz      short loc_18000792C
0x1800078e8  mov     r8d, 100h
0x1800078ee  lea     rdx, [rsp+278h+Buffer]
0x1800078f3  mov     ecx, ebp
0x1800078f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078fa  jmp     short loc_18000792C
0x1800078fc  mov     ebp, [rbx+8]
0x1800078ff  mov     [rsp+278h+Arguments], r15; Arguments
0x180007904  mov     [rsp+278h+nSize], 100h; nSize
0x18000790c  lea     rax, [rsp+278h+Buffer]
0x180007911  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007916  mov     r9d, 400h; dwLanguageId
0x18000791c  mov     r8d, ebp; dwMessageId
0x18000791f  xor     edx, edx; lpSource
0x180007921  mov     ecx, 1200h; dwFlags
0x180007926  call    cs:__imp_FormatMessageW
0x18000792c  lea     rsi, [r14+rsi*2]
0x180007930  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007934  mov     rax, [rbx+88h]
0x18000793b  mov     rcx, [rbx+80h]
0x180007942  mov     rdx, rsi; unsigned __int16 *
0x180007945  test    r9, r9
0x180007948  jz      short loc_18000796C
0x18000794a  mov     [rsp+278h+Arguments], rax
0x18000794f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007954  mov     eax, [rbx+40h]
0x180007957  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000795b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007962  mov     rcx, r14; this
0x180007965  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000796a  jmp     short loc_180007983
0x18000796c  mov     [rsp+278h+lpBuffer], rax
0x180007971  mov     r9, rcx; unsigned __int16 *
0x180007974  lea     r8, aHsP; "%hs!%p: "
0x18000797b  mov     rcx, r14; this
0x18000797e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007983  mov     r14, rax
0x180007986  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000798d  test    r9, r9
0x180007990  jz      short loc_1800079A7
0x180007992  lea     r8, aCallerP; "(caller: %p) "
0x180007999  mov     rdx, rsi; unsigned __int16 *
0x18000799c  mov     rcx, rax; this
0x18000799f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800079a4  mov     r14, rax
0x1800079a7  call    cs:__imp_GetCurrentThreadId
0x1800079ad  lea     rcx, [rsp+278h+Buffer]
0x1800079b2  mov     [rsp+278h+var_240], rcx
0x1800079b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800079bb  mov     [rsp+278h+nSize], eax
0x1800079bf  mov     eax, [rbx+44h]
0x1800079c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800079c6  mov     r9, rdi; unsigned __int16 *
0x1800079c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800079d0  mov     rdx, rsi; unsigned __int16 *
0x1800079d3  mov     rcx, r14; this
0x1800079d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800079db  cmp     [rbx+18h], r15
0x1800079df  jnz     short loc_1800079F1
0x1800079e1  cmp     [rbx+48h], r15
0x1800079e5  jnz     short loc_1800079F1
0x1800079e7  cmp     [rbx+30h], r15
0x1800079eb  jz      loc_180007A81
0x1800079f1  lea     r8, asc_180073798; "    "
0x1800079f8  mov     rdx, rsi; unsigned __int16 *
0x1800079fb  mov     rcx, rax; this
0x1800079fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007a03  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007a07  test    r9, r9
0x180007a0a  jz      short loc_180007A1E
0x180007a0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007a13  mov     rdx, rsi; unsigned __int16 *
0x180007a16  mov     rcx, rax; this
0x180007a19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007a1e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007a22  test    r9, r9
0x180007a25  jz      short loc_180007A39
0x180007a27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007a2e  mov     rdx, rsi; unsigned __int16 *
0x180007a31  mov     rcx, rax; this
0x180007a34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007a39  mov     rcx, [rbx+28h]
0x180007a3d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007a41  mov     rdx, rsi; unsigned __int16 *
0x180007a44  test    rcx, rcx
0x180007a47  jz      short loc_180007A5F
0x180007a49  mov     [rsp+278h+lpBuffer], rcx
0x180007a4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007a55  mov     rcx, rax; this
0x180007a58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007a5d  jmp     short loc_180007A81
0x180007a5f  mov     rcx, rax; this
0x180007a62  test    r9, r9
0x180007a65  jz      short loc_180007A75
0x180007a67  lea     r8, aHs; "[%hs]\n"
0x180007a6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007a73  jmp     short loc_180007A81
0x180007a75  lea     r8, asc_180073810; "\n"
0x180007a7c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007a81  xor     eax, eax
0x180007a83  mov     rcx, [rsp+278h+var_38]
0x180007a8b  xor     rcx, rsp; StackCookie
0x180007a8e  call    __security_check_cookie
0x180007a93  mov     rbx, [rsp+278h+arg_18]
0x180007a9b  add     rsp, 250h
0x180007aa2  pop     r15
0x180007aa4  pop     r14
0x180007aa6  pop     rdi
0x180007aa7  pop     rsi
0x180007aa8  pop     rbp
0x180007aa9  retn
```
