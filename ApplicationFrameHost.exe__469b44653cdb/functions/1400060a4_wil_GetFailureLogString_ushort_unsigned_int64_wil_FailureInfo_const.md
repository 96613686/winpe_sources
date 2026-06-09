# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400060a4`
- end: `0x14000635a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400045e4`
- `0x1400069e0`
- `0x1400099c0`

## callees

- `0x1400031b0`
- `0x140003de8`
- `0x1400060a4`
- `0x140006ce0`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006257`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400061d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400061d6`

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
          v7 = (const char *)&byte_14000DA80;
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
0x1400060a4  mov     [rsp+arg_18], rbx
0x1400060a9  push    rbp
0x1400060aa  push    rsi
0x1400060ab  push    rdi
0x1400060ac  push    r14
0x1400060ae  push    r15
0x1400060b0  sub     rsp, 250h
0x1400060b7  mov     rax, cs:__security_cookie
0x1400060be  xor     rax, rsp
0x1400060c1  mov     [rsp+278h+var_38], rax
0x1400060c9  mov     rbx, r8
0x1400060cc  mov     rsi, rdx
0x1400060cf  mov     r14, rcx
0x1400060d2  xor     r15d, r15d
0x1400060d5  test    rdx, rdx
0x1400060d8  jz      loc_140006331
0x1400060de  test    rcx, rcx
0x1400060e1  jz      loc_140006331
0x1400060e7  mov     [rcx], r15w
0x1400060eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1400060f2  test    rax, rax
0x1400060f5  jz      short loc_140006118
0x1400060f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400060fe  jz      short loc_140006118
0x140006100  mov     r8, rdx
0x140006103  mov     rdx, rcx
0x140006106  mov     rcx, rbx
0x140006109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000610e  cmp     [r14], r15w
0x140006112  jnz     loc_140006331
0x140006118  mov     ecx, [rbx]
0x14000611a  mov     bpl, 8
0x14000611d  test    ecx, ecx
0x14000611f  jz      short loc_14000616A
0x140006121  sub     ecx, 1
0x140006124  jz      short loc_140006152
0x140006126  sub     ecx, 1
0x140006129  jz      short loc_140006142
0x14000612b  cmp     ecx, 1
0x14000612e  jz      short loc_140006139
0x140006130  lea     rdi, byte_14000DA80
0x140006137  jmp     short loc_140006171
0x140006139  lea     rdi, aFailfast; "FailFast"
0x140006140  jmp     short loc_140006171
0x140006142  lea     rax, aLoghr; "LogHr"
0x140006149  lea     rdi, aLognt; "LogNt"
0x140006150  jmp     short loc_140006160
0x140006152  lea     rax, aReturnhr; "ReturnHr"
0x140006159  lea     rdi, aReturnnt; "ReturnNt"
0x140006160  test    [rbx+4], bpl
0x140006164  cmovz   rdi, rax
0x140006168  jmp     short loc_140006171
0x14000616a  lea     rdi, aException; "Exception"
0x140006171  xor     edx, edx; Val
0x140006173  mov     r8d, 200h; Size
0x140006179  lea     rcx, [rsp+278h+Buffer]; void *
0x14000617e  call    memset_0
0x140006183  test    [rbx+4], bpl
0x140006187  jz      short loc_1400061AC
0x140006189  mov     ebp, [rbx+0Ch]
0x14000618c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140006193  test    rax, rax
0x140006196  jz      short loc_1400061DC
0x140006198  mov     r8d, 100h
0x14000619e  lea     rdx, [rsp+278h+Buffer]
0x1400061a3  mov     ecx, ebp
0x1400061a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061aa  jmp     short loc_1400061DC
0x1400061ac  mov     ebp, [rbx+8]
0x1400061af  mov     [rsp+278h+Arguments], r15; Arguments
0x1400061b4  mov     [rsp+278h+nSize], 100h; nSize
0x1400061bc  lea     rax, [rsp+278h+Buffer]
0x1400061c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400061c6  mov     r9d, 400h; dwLanguageId
0x1400061cc  mov     r8d, ebp; dwMessageId
0x1400061cf  xor     edx, edx; lpSource
0x1400061d1  mov     ecx, 1200h; dwFlags
0x1400061d6  call    cs:__imp_FormatMessageW
0x1400061dc  lea     rsi, [r14+rsi*2]
0x1400061e0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400061e4  mov     rax, [rbx+88h]
0x1400061eb  mov     rcx, [rbx+80h]
0x1400061f2  mov     rdx, rsi; unsigned __int16 *
0x1400061f5  test    r9, r9
0x1400061f8  jz      short loc_14000621C
0x1400061fa  mov     [rsp+278h+Arguments], rax
0x1400061ff  mov     qword ptr [rsp+278h+nSize], rcx
0x140006204  mov     eax, [rbx+40h]
0x140006207  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000620b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140006212  mov     rcx, r14; this
0x140006215  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000621a  jmp     short loc_140006233
0x14000621c  mov     [rsp+278h+lpBuffer], rax
0x140006221  mov     r9, rcx; unsigned __int16 *
0x140006224  lea     r8, aHsP; "%hs!%p: "
0x14000622b  mov     rcx, r14; this
0x14000622e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006233  mov     r14, rax
0x140006236  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000623d  test    r9, r9
0x140006240  jz      short loc_140006257
0x140006242  lea     r8, aCallerP; "(caller: %p) "
0x140006249  mov     rdx, rsi; unsigned __int16 *
0x14000624c  mov     rcx, rax; this
0x14000624f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006254  mov     r14, rax
0x140006257  call    cs:__imp_GetCurrentThreadId
0x14000625d  lea     rcx, [rsp+278h+Buffer]
0x140006262  mov     [rsp+278h+var_240], rcx
0x140006267  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000626b  mov     [rsp+278h+nSize], eax
0x14000626f  mov     eax, [rbx+44h]
0x140006272  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140006276  mov     r9, rdi; unsigned __int16 *
0x140006279  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140006280  mov     rdx, rsi; unsigned __int16 *
0x140006283  mov     rcx, r14; this
0x140006286  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000628b  cmp     [rbx+18h], r15
0x14000628f  jnz     short loc_1400062A1
0x140006291  cmp     [rbx+48h], r15
0x140006295  jnz     short loc_1400062A1
0x140006297  cmp     [rbx+30h], r15
0x14000629b  jz      loc_140006331
0x1400062a1  lea     r8, asc_14000DB88; "    "
0x1400062a8  mov     rdx, rsi; unsigned __int16 *
0x1400062ab  mov     rcx, rax; this
0x1400062ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400062b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400062b7  test    r9, r9
0x1400062ba  jz      short loc_1400062CE
0x1400062bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400062c3  mov     rdx, rsi; unsigned __int16 *
0x1400062c6  mov     rcx, rax; this
0x1400062c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400062ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400062d2  test    r9, r9
0x1400062d5  jz      short loc_1400062E9
0x1400062d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400062de  mov     rdx, rsi; unsigned __int16 *
0x1400062e1  mov     rcx, rax; this
0x1400062e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400062e9  mov     rcx, [rbx+28h]
0x1400062ed  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400062f1  mov     rdx, rsi; unsigned __int16 *
0x1400062f4  test    rcx, rcx
0x1400062f7  jz      short loc_14000630F
0x1400062f9  mov     [rsp+278h+lpBuffer], rcx
0x1400062fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140006305  mov     rcx, rax; this
0x140006308  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000630d  jmp     short loc_140006331
0x14000630f  mov     rcx, rax; this
0x140006312  test    r9, r9
0x140006315  jz      short loc_140006325
0x140006317  lea     r8, aHs; "[%hs]\n"
0x14000631e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006323  jmp     short loc_140006331
0x140006325  lea     r8, asc_14000DC00; "\n"
0x14000632c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006331  xor     eax, eax
0x140006333  mov     rcx, [rsp+278h+var_38]
0x14000633b  xor     rcx, rsp; StackCookie
0x14000633e  call    __security_check_cookie
0x140006343  mov     rbx, [rsp+278h+arg_18]
0x14000634b  add     rsp, 250h
0x140006352  pop     r15
0x140006354  pop     r14
0x140006356  pop     rdi
0x140006357  pop     rsi
0x140006358  pop     rbp
0x140006359  retn
```
