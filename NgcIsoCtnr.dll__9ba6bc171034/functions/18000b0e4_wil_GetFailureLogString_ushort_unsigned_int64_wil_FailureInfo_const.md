# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b0e4`
- end: `0x18000b39a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180009648`
- `0x18000bd80`
- `0x18000c460`
- `0x18000efc0`

## callees

- `0x180007670`
- `0x1800084c8`
- `0x18000b0e4`
- `0x18000c080`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b297`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b297`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b216`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b216`

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
          v7 = qword_180093A70;
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
0x18000b0e4  mov     [rsp+arg_18], rbx
0x18000b0e9  push    rbp
0x18000b0ea  push    rsi
0x18000b0eb  push    rdi
0x18000b0ec  push    r14
0x18000b0ee  push    r15
0x18000b0f0  sub     rsp, 250h
0x18000b0f7  mov     rax, cs:__security_cookie
0x18000b0fe  xor     rax, rsp
0x18000b101  mov     [rsp+278h+var_38], rax
0x18000b109  mov     rbx, r8
0x18000b10c  mov     rsi, rdx
0x18000b10f  mov     r14, rcx
0x18000b112  xor     r15d, r15d
0x18000b115  test    rdx, rdx
0x18000b118  jz      loc_18000B371
0x18000b11e  test    rcx, rcx
0x18000b121  jz      loc_18000B371
0x18000b127  mov     [rcx], r15w
0x18000b12b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b132  test    rax, rax
0x18000b135  jz      short loc_18000B158
0x18000b137  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b13e  jz      short loc_18000B158
0x18000b140  mov     r8, rdx
0x18000b143  mov     rdx, rcx
0x18000b146  mov     rcx, rbx
0x18000b149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b14e  cmp     [r14], r15w
0x18000b152  jnz     loc_18000B371
0x18000b158  mov     ecx, [rbx]
0x18000b15a  mov     bpl, 8
0x18000b15d  test    ecx, ecx
0x18000b15f  jz      short loc_18000B1AA
0x18000b161  sub     ecx, 1
0x18000b164  jz      short loc_18000B192
0x18000b166  sub     ecx, 1
0x18000b169  jz      short loc_18000B182
0x18000b16b  cmp     ecx, 1
0x18000b16e  jz      short loc_18000B179
0x18000b170  lea     rdi, qword_180093A70
0x18000b177  jmp     short loc_18000B1B1
0x18000b179  lea     rdi, aFailfast; "FailFast"
0x18000b180  jmp     short loc_18000B1B1
0x18000b182  lea     rax, aLoghr; "LogHr"
0x18000b189  lea     rdi, aLognt; "LogNt"
0x18000b190  jmp     short loc_18000B1A0
0x18000b192  lea     rax, aReturnhr; "ReturnHr"
0x18000b199  lea     rdi, aReturnnt; "ReturnNt"
0x18000b1a0  test    [rbx+4], bpl
0x18000b1a4  cmovz   rdi, rax
0x18000b1a8  jmp     short loc_18000B1B1
0x18000b1aa  lea     rdi, aException; "Exception"
0x18000b1b1  xor     edx, edx; Val
0x18000b1b3  mov     r8d, 200h; Size
0x18000b1b9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000b1be  call    memset_0
0x18000b1c3  test    [rbx+4], bpl
0x18000b1c7  jz      short loc_18000B1EC
0x18000b1c9  mov     ebp, [rbx+0Ch]
0x18000b1cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000b1d3  test    rax, rax
0x18000b1d6  jz      short loc_18000B21C
0x18000b1d8  mov     r8d, 100h
0x18000b1de  lea     rdx, [rsp+278h+Buffer]
0x18000b1e3  mov     ecx, ebp
0x18000b1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1ea  jmp     short loc_18000B21C
0x18000b1ec  mov     ebp, [rbx+8]
0x18000b1ef  mov     [rsp+278h+Arguments], r15; Arguments
0x18000b1f4  mov     [rsp+278h+nSize], 100h; nSize
0x18000b1fc  lea     rax, [rsp+278h+Buffer]
0x18000b201  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000b206  mov     r9d, 400h; dwLanguageId
0x18000b20c  mov     r8d, ebp; dwMessageId
0x18000b20f  xor     edx, edx; lpSource
0x18000b211  mov     ecx, 1200h; dwFlags
0x18000b216  call    cs:__imp_FormatMessageW
0x18000b21c  lea     rsi, [r14+rsi*2]
0x18000b220  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000b224  mov     rax, [rbx+88h]
0x18000b22b  mov     rcx, [rbx+80h]
0x18000b232  mov     rdx, rsi; unsigned __int16 *
0x18000b235  test    r9, r9
0x18000b238  jz      short loc_18000B25C
0x18000b23a  mov     [rsp+278h+Arguments], rax
0x18000b23f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000b244  mov     eax, [rbx+40h]
0x18000b247  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b24b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000b252  mov     rcx, r14; this
0x18000b255  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b25a  jmp     short loc_18000B273
0x18000b25c  mov     [rsp+278h+lpBuffer], rax
0x18000b261  mov     r9, rcx; unsigned __int16 *
0x18000b264  lea     r8, aHsP; "%hs!%p: "
0x18000b26b  mov     rcx, r14; this
0x18000b26e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b273  mov     r14, rax
0x18000b276  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000b27d  test    r9, r9
0x18000b280  jz      short loc_18000B297
0x18000b282  lea     r8, aCallerP; "(caller: %p) "
0x18000b289  mov     rdx, rsi; unsigned __int16 *
0x18000b28c  mov     rcx, rax; this
0x18000b28f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b294  mov     r14, rax
0x18000b297  call    cs:__imp_GetCurrentThreadId
0x18000b29d  lea     rcx, [rsp+278h+Buffer]
0x18000b2a2  mov     [rsp+278h+var_240], rcx
0x18000b2a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000b2ab  mov     [rsp+278h+nSize], eax
0x18000b2af  mov     eax, [rbx+44h]
0x18000b2b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b2b6  mov     r9, rdi; unsigned __int16 *
0x18000b2b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b2c0  mov     rdx, rsi; unsigned __int16 *
0x18000b2c3  mov     rcx, r14; this
0x18000b2c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b2cb  cmp     [rbx+18h], r15
0x18000b2cf  jnz     short loc_18000B2E1
0x18000b2d1  cmp     [rbx+48h], r15
0x18000b2d5  jnz     short loc_18000B2E1
0x18000b2d7  cmp     [rbx+30h], r15
0x18000b2db  jz      loc_18000B371
0x18000b2e1  lea     r8, asc_180093B78; "    "
0x18000b2e8  mov     rdx, rsi; unsigned __int16 *
0x18000b2eb  mov     rcx, rax; this
0x18000b2ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b2f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000b2f7  test    r9, r9
0x18000b2fa  jz      short loc_18000B30E
0x18000b2fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000b303  mov     rdx, rsi; unsigned __int16 *
0x18000b306  mov     rcx, rax; this
0x18000b309  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b30e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000b312  test    r9, r9
0x18000b315  jz      short loc_18000B329
0x18000b317  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000b31e  mov     rdx, rsi; unsigned __int16 *
0x18000b321  mov     rcx, rax; this
0x18000b324  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b329  mov     rcx, [rbx+28h]
0x18000b32d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000b331  mov     rdx, rsi; unsigned __int16 *
0x18000b334  test    rcx, rcx
0x18000b337  jz      short loc_18000B34F
0x18000b339  mov     [rsp+278h+lpBuffer], rcx
0x18000b33e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000b345  mov     rcx, rax; this
0x18000b348  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b34d  jmp     short loc_18000B371
0x18000b34f  mov     rcx, rax; this
0x18000b352  test    r9, r9
0x18000b355  jz      short loc_18000B365
0x18000b357  lea     r8, aHs; "[%hs]\n"
0x18000b35e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b363  jmp     short loc_18000B371
0x18000b365  lea     r8, asc_180093BF0; "\n"
0x18000b36c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b371  xor     eax, eax
0x18000b373  mov     rcx, [rsp+278h+var_38]
0x18000b37b  xor     rcx, rsp; StackCookie
0x18000b37e  call    __security_check_cookie
0x18000b383  mov     rbx, [rsp+278h+arg_18]
0x18000b38b  add     rsp, 250h
0x18000b392  pop     r15
0x18000b394  pop     r14
0x18000b396  pop     rdi
0x18000b397  pop     rsi
0x18000b398  pop     rbp
0x18000b399  retn
```
