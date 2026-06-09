# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800127e4`
- end: `0x180012aa7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001040c`
- `0x180010688`
- `0x180013298`
- `0x1800169e0`

## callees

- `0x1800127e4`
- `0x1800135ac`
- `0x18001899e`
- `0x1800189d0`
- `0x180019010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180012916`
- `KERNEL32!FormatMessageW` at `0x180012916`
- `KERNEL32!GetCurrentThreadId` at `0x18001299d`
- `KERNEL32!GetCurrentThreadId` at `0x18001299d`

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
          v7 = (const char *)&word_18006C9A2;
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
0x1800127e4  mov     [rsp+arg_18], rbx
0x1800127e9  push    rbp
0x1800127ea  push    rsi
0x1800127eb  push    rdi
0x1800127ec  push    r14
0x1800127ee  push    r15
0x1800127f0  sub     rsp, 250h
0x1800127f7  mov     rax, cs:__security_cookie
0x1800127fe  xor     rax, rsp
0x180012801  mov     [rsp+278h+var_38], rax
0x180012809  mov     rbx, r8
0x18001280c  mov     rsi, rdx
0x18001280f  mov     r14, rcx
0x180012812  xor     r15d, r15d
0x180012815  test    rdx, rdx
0x180012818  jz      loc_180012A7D
0x18001281e  test    rcx, rcx
0x180012821  jz      loc_180012A7D
0x180012827  mov     [rcx], r15w
0x18001282b  mov     rax, cs:g_pfnResultLoggingCallback
0x180012832  test    rax, rax
0x180012835  jz      short loc_180012858
0x180012837  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001283e  jz      short loc_180012858
0x180012840  mov     r8, rdx
0x180012843  mov     rdx, rcx
0x180012846  mov     rcx, rbx
0x180012849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001284e  cmp     [r14], r15w
0x180012852  jnz     loc_180012A7D
0x180012858  mov     ecx, [rbx]
0x18001285a  mov     bpl, 8
0x18001285d  test    ecx, ecx
0x18001285f  jz      short loc_1800128AA
0x180012861  sub     ecx, 1
0x180012864  jz      short loc_180012892
0x180012866  sub     ecx, 1
0x180012869  jz      short loc_180012882
0x18001286b  cmp     ecx, 1
0x18001286e  jz      short loc_180012879
0x180012870  lea     rdi, word_18006C9A2
0x180012877  jmp     short loc_1800128B1
0x180012879  lea     rdi, aFailfast; "FailFast"
0x180012880  jmp     short loc_1800128B1
0x180012882  lea     rax, aLoghr; "LogHr"
0x180012889  lea     rdi, aLognt; "LogNt"
0x180012890  jmp     short loc_1800128A0
0x180012892  lea     rax, aReturnhr; "ReturnHr"
0x180012899  lea     rdi, aReturnnt; "ReturnNt"
0x1800128a0  test    [rbx+4], bpl
0x1800128a4  cmovz   rdi, rax
0x1800128a8  jmp     short loc_1800128B1
0x1800128aa  lea     rdi, aException; "Exception"
0x1800128b1  xor     edx, edx; Val
0x1800128b3  mov     r8d, 200h; Size
0x1800128b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800128be  call    memset_0
0x1800128c3  test    [rbx+4], bpl
0x1800128c7  jz      short loc_1800128EC
0x1800128c9  mov     ebp, [rbx+0Ch]
0x1800128cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800128d3  test    rax, rax
0x1800128d6  jz      short loc_180012922
0x1800128d8  mov     r8d, 100h
0x1800128de  lea     rdx, [rsp+278h+Buffer]
0x1800128e3  mov     ecx, ebp
0x1800128e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128ea  jmp     short loc_180012922
0x1800128ec  mov     ebp, [rbx+8]
0x1800128ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800128f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800128fc  lea     rax, [rsp+278h+Buffer]
0x180012901  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180012906  mov     r9d, 400h; dwLanguageId
0x18001290c  mov     r8d, ebp; dwMessageId
0x18001290f  xor     edx, edx; lpSource
0x180012911  mov     ecx, 1200h; dwFlags
0x180012916  call    cs:__imp_FormatMessageW
0x18001291d  nop     dword ptr [rax+rax+00h]
0x180012922  lea     rsi, [r14+rsi*2]
0x180012926  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001292a  mov     rax, [rbx+88h]
0x180012931  mov     rcx, [rbx+80h]
0x180012938  mov     rdx, rsi; unsigned __int16 *
0x18001293b  test    r9, r9
0x18001293e  jz      short loc_180012962
0x180012940  mov     [rsp+278h+Arguments], rax
0x180012945  mov     qword ptr [rsp+278h+nSize], rcx
0x18001294a  mov     eax, [rbx+40h]
0x18001294d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180012951  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180012958  mov     rcx, r14; this
0x18001295b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012960  jmp     short loc_180012979
0x180012962  mov     [rsp+278h+lpBuffer], rax
0x180012967  mov     r9, rcx; unsigned __int16 *
0x18001296a  lea     r8, aHsP; "%hs!%p: "
0x180012971  mov     rcx, r14; this
0x180012974  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012979  mov     r14, rax
0x18001297c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180012983  test    r9, r9
0x180012986  jz      short loc_18001299D
0x180012988  lea     r8, aCallerP; "(caller: %p) "
0x18001298f  mov     rdx, rsi; unsigned __int16 *
0x180012992  mov     rcx, rax; this
0x180012995  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001299a  mov     r14, rax
0x18001299d  call    cs:__imp_GetCurrentThreadId
0x1800129a4  nop     dword ptr [rax+rax+00h]
0x1800129a9  lea     rcx, [rsp+278h+Buffer]
0x1800129ae  mov     [rsp+278h+var_240], rcx
0x1800129b3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800129b7  mov     [rsp+278h+nSize], eax
0x1800129bb  mov     eax, [rbx+44h]
0x1800129be  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800129c2  mov     r9, rdi; unsigned __int16 *
0x1800129c5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800129cc  mov     rdx, rsi; unsigned __int16 *
0x1800129cf  mov     rcx, r14; this
0x1800129d2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800129d7  cmp     [rbx+18h], r15
0x1800129db  jnz     short loc_1800129ED
0x1800129dd  cmp     [rbx+48h], r15
0x1800129e1  jnz     short loc_1800129ED
0x1800129e3  cmp     [rbx+30h], r15
0x1800129e7  jz      loc_180012A7D
0x1800129ed  lea     r8, asc_18006CA38; "    "
0x1800129f4  mov     rdx, rsi; unsigned __int16 *
0x1800129f7  mov     rcx, rax; this
0x1800129fa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800129ff  mov     r9, [rbx+18h]; unsigned __int16 *
0x180012a03  test    r9, r9
0x180012a06  jz      short loc_180012A1A
0x180012a08  lea     r8, aMsgWs; "Msg:[%ws] "
0x180012a0f  mov     rdx, rsi; unsigned __int16 *
0x180012a12  mov     rcx, rax; this
0x180012a15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012a1a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180012a1e  test    r9, r9
0x180012a21  jz      short loc_180012A35
0x180012a23  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180012a2a  mov     rdx, rsi; unsigned __int16 *
0x180012a2d  mov     rcx, rax; this
0x180012a30  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012a35  mov     rcx, [rbx+28h]
0x180012a39  mov     r9, [rbx+30h]; unsigned __int16 *
0x180012a3d  mov     rdx, rsi; unsigned __int16 *
0x180012a40  test    rcx, rcx
0x180012a43  jz      short loc_180012A5B
0x180012a45  mov     [rsp+278h+lpBuffer], rcx
0x180012a4a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180012a51  mov     rcx, rax; this
0x180012a54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012a59  jmp     short loc_180012A7D
0x180012a5b  mov     rcx, rax; this
0x180012a5e  test    r9, r9
0x180012a61  jz      short loc_180012A71
0x180012a63  lea     r8, aHs; "[%hs]\n"
0x180012a6a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012a6f  jmp     short loc_180012A7D
0x180012a71  lea     r8, asc_18006C9A4; "\n"
0x180012a78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012a7d  xor     eax, eax
0x180012a7f  mov     rcx, [rsp+278h+var_38]
0x180012a87  xor     rcx, rsp; StackCookie
0x180012a8a  call    __security_check_cookie
0x180012a8f  mov     rbx, [rsp+278h+arg_18]
0x180012a97  add     rsp, 250h
0x180012a9e  pop     r15
0x180012aa0  pop     r14
0x180012aa2  pop     rdi
0x180012aa3  pop     rsi
0x180012aa4  pop     rbp
0x180012aa5  retn
```
