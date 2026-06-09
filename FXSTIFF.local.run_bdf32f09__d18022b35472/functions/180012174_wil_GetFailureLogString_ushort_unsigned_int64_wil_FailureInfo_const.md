# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180012174`
- end: `0x18001242a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fc64`
- `0x18000fecc`
- `0x180012b9c`
- `0x180015d90`

## callees

- `0x180012174`
- `0x180012e9c`
- `0x180017bce`
- `0x180017c00`
- `0x180019010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800122a6`
- `KERNEL32!FormatMessageW` at `0x1800122a6`
- `KERNEL32!GetCurrentThreadId` at `0x180012327`
- `KERNEL32!GetCurrentThreadId` at `0x180012327`

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
          v7 = (const char *)&word_18006C97A;
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
0x180012174  mov     [rsp+arg_18], rbx
0x180012179  push    rbp
0x18001217a  push    rsi
0x18001217b  push    rdi
0x18001217c  push    r14
0x18001217e  push    r15
0x180012180  sub     rsp, 250h
0x180012187  mov     rax, cs:__security_cookie
0x18001218e  xor     rax, rsp
0x180012191  mov     [rsp+278h+var_38], rax
0x180012199  mov     rbx, r8
0x18001219c  mov     rsi, rdx
0x18001219f  mov     r14, rcx
0x1800121a2  xor     r15d, r15d
0x1800121a5  test    rdx, rdx
0x1800121a8  jz      loc_180012401
0x1800121ae  test    rcx, rcx
0x1800121b1  jz      loc_180012401
0x1800121b7  mov     [rcx], r15w
0x1800121bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800121c2  test    rax, rax
0x1800121c5  jz      short loc_1800121E8
0x1800121c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800121ce  jz      short loc_1800121E8
0x1800121d0  mov     r8, rdx
0x1800121d3  mov     rdx, rcx
0x1800121d6  mov     rcx, rbx
0x1800121d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121de  cmp     [r14], r15w
0x1800121e2  jnz     loc_180012401
0x1800121e8  mov     ecx, [rbx]
0x1800121ea  mov     bpl, 8
0x1800121ed  test    ecx, ecx
0x1800121ef  jz      short loc_18001223A
0x1800121f1  sub     ecx, 1
0x1800121f4  jz      short loc_180012222
0x1800121f6  sub     ecx, 1
0x1800121f9  jz      short loc_180012212
0x1800121fb  cmp     ecx, 1
0x1800121fe  jz      short loc_180012209
0x180012200  lea     rdi, word_18006C97A
0x180012207  jmp     short loc_180012241
0x180012209  lea     rdi, aFailfast; "FailFast"
0x180012210  jmp     short loc_180012241
0x180012212  lea     rax, aLoghr; "LogHr"
0x180012219  lea     rdi, aLognt; "LogNt"
0x180012220  jmp     short loc_180012230
0x180012222  lea     rax, aReturnhr; "ReturnHr"
0x180012229  lea     rdi, aReturnnt; "ReturnNt"
0x180012230  test    [rbx+4], bpl
0x180012234  cmovz   rdi, rax
0x180012238  jmp     short loc_180012241
0x18001223a  lea     rdi, aException; "Exception"
0x180012241  xor     edx, edx; Val
0x180012243  mov     r8d, 200h; Size
0x180012249  lea     rcx, [rsp+278h+Buffer]; void *
0x18001224e  call    memset_0
0x180012253  test    [rbx+4], bpl
0x180012257  jz      short loc_18001227C
0x180012259  mov     ebp, [rbx+0Ch]
0x18001225c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180012263  test    rax, rax
0x180012266  jz      short loc_1800122AC
0x180012268  mov     r8d, 100h
0x18001226e  lea     rdx, [rsp+278h+Buffer]
0x180012273  mov     ecx, ebp
0x180012275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001227a  jmp     short loc_1800122AC
0x18001227c  mov     ebp, [rbx+8]
0x18001227f  mov     [rsp+278h+Arguments], r15; Arguments
0x180012284  mov     [rsp+278h+nSize], 100h; nSize
0x18001228c  lea     rax, [rsp+278h+Buffer]
0x180012291  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180012296  mov     r9d, 400h; dwLanguageId
0x18001229c  mov     r8d, ebp; dwMessageId
0x18001229f  xor     edx, edx; lpSource
0x1800122a1  mov     ecx, 1200h; dwFlags
0x1800122a6  call    cs:__imp_FormatMessageW
0x1800122ac  lea     rsi, [r14+rsi*2]
0x1800122b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800122b4  mov     rax, [rbx+88h]
0x1800122bb  mov     rcx, [rbx+80h]
0x1800122c2  mov     rdx, rsi; unsigned __int16 *
0x1800122c5  test    r9, r9
0x1800122c8  jz      short loc_1800122EC
0x1800122ca  mov     [rsp+278h+Arguments], rax
0x1800122cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800122d4  mov     eax, [rbx+40h]
0x1800122d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800122db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800122e2  mov     rcx, r14; this
0x1800122e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800122ea  jmp     short loc_180012303
0x1800122ec  mov     [rsp+278h+lpBuffer], rax
0x1800122f1  mov     r9, rcx; unsigned __int16 *
0x1800122f4  lea     r8, aHsP; "%hs!%p: "
0x1800122fb  mov     rcx, r14; this
0x1800122fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012303  mov     r14, rax
0x180012306  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001230d  test    r9, r9
0x180012310  jz      short loc_180012327
0x180012312  lea     r8, aCallerP; "(caller: %p) "
0x180012319  mov     rdx, rsi; unsigned __int16 *
0x18001231c  mov     rcx, rax; this
0x18001231f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012324  mov     r14, rax
0x180012327  call    cs:__imp_GetCurrentThreadId
0x18001232d  lea     rcx, [rsp+278h+Buffer]
0x180012332  mov     [rsp+278h+var_240], rcx
0x180012337  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001233b  mov     [rsp+278h+nSize], eax
0x18001233f  mov     eax, [rbx+44h]
0x180012342  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180012346  mov     r9, rdi; unsigned __int16 *
0x180012349  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180012350  mov     rdx, rsi; unsigned __int16 *
0x180012353  mov     rcx, r14; this
0x180012356  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001235b  cmp     [rbx+18h], r15
0x18001235f  jnz     short loc_180012371
0x180012361  cmp     [rbx+48h], r15
0x180012365  jnz     short loc_180012371
0x180012367  cmp     [rbx+30h], r15
0x18001236b  jz      loc_180012401
0x180012371  lea     r8, asc_18006CA10; "    "
0x180012378  mov     rdx, rsi; unsigned __int16 *
0x18001237b  mov     rcx, rax; this
0x18001237e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012383  mov     r9, [rbx+18h]; unsigned __int16 *
0x180012387  test    r9, r9
0x18001238a  jz      short loc_18001239E
0x18001238c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180012393  mov     rdx, rsi; unsigned __int16 *
0x180012396  mov     rcx, rax; this
0x180012399  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001239e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800123a2  test    r9, r9
0x1800123a5  jz      short loc_1800123B9
0x1800123a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800123ae  mov     rdx, rsi; unsigned __int16 *
0x1800123b1  mov     rcx, rax; this
0x1800123b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800123b9  mov     rcx, [rbx+28h]
0x1800123bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800123c1  mov     rdx, rsi; unsigned __int16 *
0x1800123c4  test    rcx, rcx
0x1800123c7  jz      short loc_1800123DF
0x1800123c9  mov     [rsp+278h+lpBuffer], rcx
0x1800123ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800123d5  mov     rcx, rax; this
0x1800123d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800123dd  jmp     short loc_180012401
0x1800123df  mov     rcx, rax; this
0x1800123e2  test    r9, r9
0x1800123e5  jz      short loc_1800123F5
0x1800123e7  lea     r8, aHs; "[%hs]\n"
0x1800123ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800123f3  jmp     short loc_180012401
0x1800123f5  lea     r8, asc_18006C97C; "\n"
0x1800123fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012401  xor     eax, eax
0x180012403  mov     rcx, [rsp+278h+var_38]
0x18001240b  xor     rcx, rsp; StackCookie
0x18001240e  call    __security_check_cookie
0x180012413  mov     rbx, [rsp+278h+arg_18]
0x18001241b  add     rsp, 250h
0x180012422  pop     r15
0x180012424  pop     r14
0x180012426  pop     rdi
0x180012427  pop     rsi
0x180012428  pop     rbp
0x180012429  retn
```
