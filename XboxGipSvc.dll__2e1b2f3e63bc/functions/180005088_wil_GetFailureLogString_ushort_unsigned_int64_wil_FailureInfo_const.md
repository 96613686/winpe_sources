# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005088`
- end: `0x18000533e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180003f18`
- `0x1800059f0`
- `0x180006c68`
- `0x180009350`
- `0x18000bccc`

## callees

- `0x1800016c0`
- `0x180002158`
- `0x180005088`
- `0x180005cf0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000523b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000523b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800051ba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800051ba`

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
          v7 = (const char *)&qword_180015A08;
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
0x180005088  mov     [rsp+arg_18], rbx
0x18000508d  push    rbp
0x18000508e  push    rsi
0x18000508f  push    rdi
0x180005090  push    r14
0x180005092  push    r15
0x180005094  sub     rsp, 250h
0x18000509b  mov     rax, cs:__security_cookie
0x1800050a2  xor     rax, rsp
0x1800050a5  mov     [rsp+278h+var_38], rax
0x1800050ad  mov     rbx, r8
0x1800050b0  mov     rsi, rdx
0x1800050b3  mov     r14, rcx
0x1800050b6  xor     r15d, r15d
0x1800050b9  test    rdx, rdx
0x1800050bc  jz      loc_180005315
0x1800050c2  test    rcx, rcx
0x1800050c5  jz      loc_180005315
0x1800050cb  mov     [rcx], r15w
0x1800050cf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050d6  test    rax, rax
0x1800050d9  jz      short loc_1800050FC
0x1800050db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800050e2  jz      short loc_1800050FC
0x1800050e4  mov     r8, rdx
0x1800050e7  mov     rdx, rcx
0x1800050ea  mov     rcx, rbx
0x1800050ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050f2  cmp     [r14], r15w
0x1800050f6  jnz     loc_180005315
0x1800050fc  mov     ecx, [rbx]
0x1800050fe  mov     bpl, 8
0x180005101  test    ecx, ecx
0x180005103  jz      short loc_18000514E
0x180005105  sub     ecx, 1
0x180005108  jz      short loc_180005136
0x18000510a  sub     ecx, 1
0x18000510d  jz      short loc_180005126
0x18000510f  cmp     ecx, 1
0x180005112  jz      short loc_18000511D
0x180005114  lea     rdi, qword_180015A08
0x18000511b  jmp     short loc_180005155
0x18000511d  lea     rdi, aFailfast; "FailFast"
0x180005124  jmp     short loc_180005155
0x180005126  lea     rax, aLoghr; "LogHr"
0x18000512d  lea     rdi, aLognt; "LogNt"
0x180005134  jmp     short loc_180005144
0x180005136  lea     rax, aReturnhr; "ReturnHr"
0x18000513d  lea     rdi, aReturnnt; "ReturnNt"
0x180005144  test    [rbx+4], bpl
0x180005148  cmovz   rdi, rax
0x18000514c  jmp     short loc_180005155
0x18000514e  lea     rdi, aException; "Exception"
0x180005155  xor     edx, edx; Val
0x180005157  mov     r8d, 200h; Size
0x18000515d  lea     rcx, [rsp+278h+Buffer]; void *
0x180005162  call    memset_0
0x180005167  test    [rbx+4], bpl
0x18000516b  jz      short loc_180005190
0x18000516d  mov     ebp, [rbx+0Ch]
0x180005170  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005177  test    rax, rax
0x18000517a  jz      short loc_1800051C0
0x18000517c  mov     r8d, 100h
0x180005182  lea     rdx, [rsp+278h+Buffer]
0x180005187  mov     ecx, ebp
0x180005189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518e  jmp     short loc_1800051C0
0x180005190  mov     ebp, [rbx+8]
0x180005193  mov     [rsp+278h+Arguments], r15; Arguments
0x180005198  mov     [rsp+278h+nSize], 100h; nSize
0x1800051a0  lea     rax, [rsp+278h+Buffer]
0x1800051a5  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800051aa  mov     r9d, 400h; dwLanguageId
0x1800051b0  mov     r8d, ebp; dwMessageId
0x1800051b3  xor     edx, edx; lpSource
0x1800051b5  mov     ecx, 1200h; dwFlags
0x1800051ba  call    cs:__imp_FormatMessageW
0x1800051c0  lea     rsi, [r14+rsi*2]
0x1800051c4  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800051c8  mov     rax, [rbx+88h]
0x1800051cf  mov     rcx, [rbx+80h]
0x1800051d6  mov     rdx, rsi; unsigned __int16 *
0x1800051d9  test    r9, r9
0x1800051dc  jz      short loc_180005200
0x1800051de  mov     [rsp+278h+Arguments], rax
0x1800051e3  mov     qword ptr [rsp+278h+nSize], rcx
0x1800051e8  mov     eax, [rbx+40h]
0x1800051eb  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800051ef  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800051f6  mov     rcx, r14; this
0x1800051f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051fe  jmp     short loc_180005217
0x180005200  mov     [rsp+278h+lpBuffer], rax
0x180005205  mov     r9, rcx; unsigned __int16 *
0x180005208  lea     r8, aHsP; "%hs!%p: "
0x18000520f  mov     rcx, r14; this
0x180005212  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005217  mov     r14, rax
0x18000521a  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005221  test    r9, r9
0x180005224  jz      short loc_18000523B
0x180005226  lea     r8, aCallerP; "(caller: %p) "
0x18000522d  mov     rdx, rsi; unsigned __int16 *
0x180005230  mov     rcx, rax; this
0x180005233  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005238  mov     r14, rax
0x18000523b  call    cs:__imp_GetCurrentThreadId
0x180005241  lea     rcx, [rsp+278h+Buffer]
0x180005246  mov     [rsp+278h+var_240], rcx
0x18000524b  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000524f  mov     [rsp+278h+nSize], eax
0x180005253  mov     eax, [rbx+44h]
0x180005256  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000525a  mov     r9, rdi; unsigned __int16 *
0x18000525d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005264  mov     rdx, rsi; unsigned __int16 *
0x180005267  mov     rcx, r14; this
0x18000526a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000526f  cmp     [rbx+18h], r15
0x180005273  jnz     short loc_180005285
0x180005275  cmp     [rbx+48h], r15
0x180005279  jnz     short loc_180005285
0x18000527b  cmp     [rbx+30h], r15
0x18000527f  jz      loc_180005315
0x180005285  lea     r8, asc_180015AF8; "    "
0x18000528c  mov     rdx, rsi; unsigned __int16 *
0x18000528f  mov     rcx, rax; this
0x180005292  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005297  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000529b  test    r9, r9
0x18000529e  jz      short loc_1800052B2
0x1800052a0  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800052a7  mov     rdx, rsi; unsigned __int16 *
0x1800052aa  mov     rcx, rax; this
0x1800052ad  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800052b2  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800052b6  test    r9, r9
0x1800052b9  jz      short loc_1800052CD
0x1800052bb  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800052c2  mov     rdx, rsi; unsigned __int16 *
0x1800052c5  mov     rcx, rax; this
0x1800052c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800052cd  mov     rcx, [rbx+28h]
0x1800052d1  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800052d5  mov     rdx, rsi; unsigned __int16 *
0x1800052d8  test    rcx, rcx
0x1800052db  jz      short loc_1800052F3
0x1800052dd  mov     [rsp+278h+lpBuffer], rcx
0x1800052e2  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800052e9  mov     rcx, rax; this
0x1800052ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800052f1  jmp     short loc_180005315
0x1800052f3  mov     rcx, rax; this
0x1800052f6  test    r9, r9
0x1800052f9  jz      short loc_180005309
0x1800052fb  lea     r8, aHs; "[%hs]\n"
0x180005302  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005307  jmp     short loc_180005315
0x180005309  lea     r8, asc_180015B70; "\n"
0x180005310  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005315  xor     eax, eax
0x180005317  mov     rcx, [rsp+278h+var_38]
0x18000531f  xor     rcx, rsp; StackCookie
0x180005322  call    __security_check_cookie
0x180005327  mov     rbx, [rsp+278h+arg_18]
0x18000532f  add     rsp, 250h
0x180005336  pop     r15
0x180005338  pop     r14
0x18000533a  pop     rdi
0x18000533b  pop     rsi
0x18000533c  pop     rbp
0x18000533d  retn
```
