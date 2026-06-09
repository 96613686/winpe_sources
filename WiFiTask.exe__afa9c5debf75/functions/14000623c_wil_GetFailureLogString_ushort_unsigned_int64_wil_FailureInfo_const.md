# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000623c`
- end: `0x1400064f2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140002744`
- `0x1400029ac`
- `0x14000771c`
- `0x14000ba10`

## callees

- `0x1400016a0`
- `0x140002168`
- `0x14000623c`
- `0x140007a1c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400063ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400063ef`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000636e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000636e`

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
          v7 = (const char *)&byte_140013C4D;
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
0x14000623c  mov     [rsp+arg_18], rbx
0x140006241  push    rbp
0x140006242  push    rsi
0x140006243  push    rdi
0x140006244  push    r14
0x140006246  push    r15
0x140006248  sub     rsp, 250h
0x14000624f  mov     rax, cs:__security_cookie
0x140006256  xor     rax, rsp
0x140006259  mov     [rsp+278h+var_38], rax
0x140006261  mov     rbx, r8
0x140006264  mov     rsi, rdx
0x140006267  mov     r14, rcx
0x14000626a  xor     r15d, r15d
0x14000626d  test    rdx, rdx
0x140006270  jz      loc_1400064C9
0x140006276  test    rcx, rcx
0x140006279  jz      loc_1400064C9
0x14000627f  mov     [rcx], r15w
0x140006283  mov     rax, cs:g_pfnResultLoggingCallback
0x14000628a  test    rax, rax
0x14000628d  jz      short loc_1400062B0
0x14000628f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140006296  jz      short loc_1400062B0
0x140006298  mov     r8, rdx
0x14000629b  mov     rdx, rcx
0x14000629e  mov     rcx, rbx
0x1400062a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062a6  cmp     [r14], r15w
0x1400062aa  jnz     loc_1400064C9
0x1400062b0  mov     ecx, [rbx]
0x1400062b2  mov     bpl, 8
0x1400062b5  test    ecx, ecx
0x1400062b7  jz      short loc_140006302
0x1400062b9  sub     ecx, 1
0x1400062bc  jz      short loc_1400062EA
0x1400062be  sub     ecx, 1
0x1400062c1  jz      short loc_1400062DA
0x1400062c3  cmp     ecx, 1
0x1400062c6  jz      short loc_1400062D1
0x1400062c8  lea     rdi, byte_140013C4D
0x1400062cf  jmp     short loc_140006309
0x1400062d1  lea     rdi, aFailfast; "FailFast"
0x1400062d8  jmp     short loc_140006309
0x1400062da  lea     rax, aLoghr; "LogHr"
0x1400062e1  lea     rdi, aLognt; "LogNt"
0x1400062e8  jmp     short loc_1400062F8
0x1400062ea  lea     rax, aReturnhr; "ReturnHr"
0x1400062f1  lea     rdi, aReturnnt; "ReturnNt"
0x1400062f8  test    [rbx+4], bpl
0x1400062fc  cmovz   rdi, rax
0x140006300  jmp     short loc_140006309
0x140006302  lea     rdi, aException; "Exception"
0x140006309  xor     edx, edx; Val
0x14000630b  mov     r8d, 200h; Size
0x140006311  lea     rcx, [rsp+278h+Buffer]; void *
0x140006316  call    memset_0
0x14000631b  test    [rbx+4], bpl
0x14000631f  jz      short loc_140006344
0x140006321  mov     ebp, [rbx+0Ch]
0x140006324  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000632b  test    rax, rax
0x14000632e  jz      short loc_140006374
0x140006330  mov     r8d, 100h
0x140006336  lea     rdx, [rsp+278h+Buffer]
0x14000633b  mov     ecx, ebp
0x14000633d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006342  jmp     short loc_140006374
0x140006344  mov     ebp, [rbx+8]
0x140006347  mov     [rsp+278h+Arguments], r15; Arguments
0x14000634c  mov     [rsp+278h+nSize], 100h; nSize
0x140006354  lea     rax, [rsp+278h+Buffer]
0x140006359  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000635e  mov     r9d, 400h; dwLanguageId
0x140006364  mov     r8d, ebp; dwMessageId
0x140006367  xor     edx, edx; lpSource
0x140006369  mov     ecx, 1200h; dwFlags
0x14000636e  call    cs:__imp_FormatMessageW
0x140006374  lea     rsi, [r14+rsi*2]
0x140006378  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000637c  mov     rax, [rbx+88h]
0x140006383  mov     rcx, [rbx+80h]
0x14000638a  mov     rdx, rsi; unsigned __int16 *
0x14000638d  test    r9, r9
0x140006390  jz      short loc_1400063B4
0x140006392  mov     [rsp+278h+Arguments], rax
0x140006397  mov     qword ptr [rsp+278h+nSize], rcx
0x14000639c  mov     eax, [rbx+40h]
0x14000639f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400063a3  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400063aa  mov     rcx, r14; this
0x1400063ad  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400063b2  jmp     short loc_1400063CB
0x1400063b4  mov     [rsp+278h+lpBuffer], rax
0x1400063b9  mov     r9, rcx; unsigned __int16 *
0x1400063bc  lea     r8, aHsP; "%hs!%p: "
0x1400063c3  mov     rcx, r14; this
0x1400063c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400063cb  mov     r14, rax
0x1400063ce  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400063d5  test    r9, r9
0x1400063d8  jz      short loc_1400063EF
0x1400063da  lea     r8, aCallerP; "(caller: %p) "
0x1400063e1  mov     rdx, rsi; unsigned __int16 *
0x1400063e4  mov     rcx, rax; this
0x1400063e7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400063ec  mov     r14, rax
0x1400063ef  call    cs:__imp_GetCurrentThreadId
0x1400063f5  lea     rcx, [rsp+278h+Buffer]
0x1400063fa  mov     [rsp+278h+var_240], rcx
0x1400063ff  mov     dword ptr [rsp+278h+Arguments], ebp
0x140006403  mov     [rsp+278h+nSize], eax
0x140006407  mov     eax, [rbx+44h]
0x14000640a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000640e  mov     r9, rdi; unsigned __int16 *
0x140006411  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140006418  mov     rdx, rsi; unsigned __int16 *
0x14000641b  mov     rcx, r14; this
0x14000641e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006423  cmp     [rbx+18h], r15
0x140006427  jnz     short loc_140006439
0x140006429  cmp     [rbx+48h], r15
0x14000642d  jnz     short loc_140006439
0x14000642f  cmp     [rbx+30h], r15
0x140006433  jz      loc_1400064C9
0x140006439  lea     r8, asc_140013D38; "    "
0x140006440  mov     rdx, rsi; unsigned __int16 *
0x140006443  mov     rcx, rax; this
0x140006446  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000644b  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000644f  test    r9, r9
0x140006452  jz      short loc_140006466
0x140006454  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000645b  mov     rdx, rsi; unsigned __int16 *
0x14000645e  mov     rcx, rax; this
0x140006461  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006466  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000646a  test    r9, r9
0x14000646d  jz      short loc_140006481
0x14000646f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140006476  mov     rdx, rsi; unsigned __int16 *
0x140006479  mov     rcx, rax; this
0x14000647c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006481  mov     rcx, [rbx+28h]
0x140006485  mov     r9, [rbx+30h]; unsigned __int16 *
0x140006489  mov     rdx, rsi; unsigned __int16 *
0x14000648c  test    rcx, rcx
0x14000648f  jz      short loc_1400064A7
0x140006491  mov     [rsp+278h+lpBuffer], rcx
0x140006496  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000649d  mov     rcx, rax; this
0x1400064a0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400064a5  jmp     short loc_1400064C9
0x1400064a7  mov     rcx, rax; this
0x1400064aa  test    r9, r9
0x1400064ad  jz      short loc_1400064BD
0x1400064af  lea     r8, aHs; "[%hs]\n"
0x1400064b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400064bb  jmp     short loc_1400064C9
0x1400064bd  lea     r8, asc_140013DB0; "\n"
0x1400064c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400064c9  xor     eax, eax
0x1400064cb  mov     rcx, [rsp+278h+var_38]
0x1400064d3  xor     rcx, rsp; StackCookie
0x1400064d6  call    __security_check_cookie
0x1400064db  mov     rbx, [rsp+278h+arg_18]
0x1400064e3  add     rsp, 250h
0x1400064ea  pop     r15
0x1400064ec  pop     r14
0x1400064ee  pop     rdi
0x1400064ef  pop     rsi
0x1400064f0  pop     rbp
0x1400064f1  retn
```
