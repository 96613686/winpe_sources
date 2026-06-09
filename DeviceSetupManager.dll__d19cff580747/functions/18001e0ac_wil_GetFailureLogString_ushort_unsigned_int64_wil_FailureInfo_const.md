# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001e0ac`
- end: `0x18001e362`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800114cc`
- `0x18001ed4c`
- `0x180020d30`

## callees

- `0x18001af70`
- `0x18001ba48`
- `0x18001e0ac`
- `0x18001e9d0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e25f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e25f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001e1de`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001e1de`

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
          v7 = (const char *)&word_18004C1DC;
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
0x18001e0ac  mov     [rsp+arg_18], rbx
0x18001e0b1  push    rbp
0x18001e0b2  push    rsi
0x18001e0b3  push    rdi
0x18001e0b4  push    r14
0x18001e0b6  push    r15
0x18001e0b8  sub     rsp, 250h
0x18001e0bf  mov     rax, cs:__security_cookie
0x18001e0c6  xor     rax, rsp
0x18001e0c9  mov     [rsp+278h+var_38], rax
0x18001e0d1  mov     rbx, r8
0x18001e0d4  mov     rsi, rdx
0x18001e0d7  mov     r14, rcx
0x18001e0da  xor     r15d, r15d
0x18001e0dd  test    rdx, rdx
0x18001e0e0  jz      loc_18001E339
0x18001e0e6  test    rcx, rcx
0x18001e0e9  jz      loc_18001E339
0x18001e0ef  mov     [rcx], r15w
0x18001e0f3  mov     rax, cs:g_pfnResultLoggingCallback
0x18001e0fa  test    rax, rax
0x18001e0fd  jz      short loc_18001E120
0x18001e0ff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001e106  jz      short loc_18001E120
0x18001e108  mov     r8, rdx
0x18001e10b  mov     rdx, rcx
0x18001e10e  mov     rcx, rbx
0x18001e111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e116  cmp     [r14], r15w
0x18001e11a  jnz     loc_18001E339
0x18001e120  mov     ecx, [rbx]
0x18001e122  mov     bpl, 8
0x18001e125  test    ecx, ecx
0x18001e127  jz      short loc_18001E172
0x18001e129  sub     ecx, 1
0x18001e12c  jz      short loc_18001E15A
0x18001e12e  sub     ecx, 1
0x18001e131  jz      short loc_18001E14A
0x18001e133  cmp     ecx, 1
0x18001e136  jz      short loc_18001E141
0x18001e138  lea     rdi, word_18004C1DC
0x18001e13f  jmp     short loc_18001E179
0x18001e141  lea     rdi, aFailfast; "FailFast"
0x18001e148  jmp     short loc_18001E179
0x18001e14a  lea     rax, aLoghr; "LogHr"
0x18001e151  lea     rdi, aLognt; "LogNt"
0x18001e158  jmp     short loc_18001E168
0x18001e15a  lea     rax, aReturnhr; "ReturnHr"
0x18001e161  lea     rdi, aReturnnt; "ReturnNt"
0x18001e168  test    [rbx+4], bpl
0x18001e16c  cmovz   rdi, rax
0x18001e170  jmp     short loc_18001E179
0x18001e172  lea     rdi, aException; "Exception"
0x18001e179  xor     edx, edx; Val
0x18001e17b  mov     r8d, 200h; Size
0x18001e181  lea     rcx, [rsp+278h+Buffer]; void *
0x18001e186  call    memset_0
0x18001e18b  test    [rbx+4], bpl
0x18001e18f  jz      short loc_18001E1B4
0x18001e191  mov     ebp, [rbx+0Ch]
0x18001e194  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001e19b  test    rax, rax
0x18001e19e  jz      short loc_18001E1E4
0x18001e1a0  mov     r8d, 100h
0x18001e1a6  lea     rdx, [rsp+278h+Buffer]
0x18001e1ab  mov     ecx, ebp
0x18001e1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1b2  jmp     short loc_18001E1E4
0x18001e1b4  mov     ebp, [rbx+8]
0x18001e1b7  mov     [rsp+278h+Arguments], r15; Arguments
0x18001e1bc  mov     [rsp+278h+nSize], 100h; nSize
0x18001e1c4  lea     rax, [rsp+278h+Buffer]
0x18001e1c9  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001e1ce  mov     r9d, 400h; dwLanguageId
0x18001e1d4  mov     r8d, ebp; dwMessageId
0x18001e1d7  xor     edx, edx; lpSource
0x18001e1d9  mov     ecx, 1200h; dwFlags
0x18001e1de  call    cs:__imp_FormatMessageW
0x18001e1e4  lea     rsi, [r14+rsi*2]
0x18001e1e8  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001e1ec  mov     rax, [rbx+88h]
0x18001e1f3  mov     rcx, [rbx+80h]
0x18001e1fa  mov     rdx, rsi; unsigned __int16 *
0x18001e1fd  test    r9, r9
0x18001e200  jz      short loc_18001E224
0x18001e202  mov     [rsp+278h+Arguments], rax
0x18001e207  mov     qword ptr [rsp+278h+nSize], rcx
0x18001e20c  mov     eax, [rbx+40h]
0x18001e20f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001e213  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001e21a  mov     rcx, r14; this
0x18001e21d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e222  jmp     short loc_18001E23B
0x18001e224  mov     [rsp+278h+lpBuffer], rax
0x18001e229  mov     r9, rcx; unsigned __int16 *
0x18001e22c  lea     r8, aHsP; "%hs!%p: "
0x18001e233  mov     rcx, r14; this
0x18001e236  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e23b  mov     r14, rax
0x18001e23e  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001e245  test    r9, r9
0x18001e248  jz      short loc_18001E25F
0x18001e24a  lea     r8, aCallerP; "(caller: %p) "
0x18001e251  mov     rdx, rsi; unsigned __int16 *
0x18001e254  mov     rcx, rax; this
0x18001e257  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e25c  mov     r14, rax
0x18001e25f  call    cs:__imp_GetCurrentThreadId
0x18001e265  lea     rcx, [rsp+278h+Buffer]
0x18001e26a  mov     [rsp+278h+var_240], rcx
0x18001e26f  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001e273  mov     [rsp+278h+nSize], eax
0x18001e277  mov     eax, [rbx+44h]
0x18001e27a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001e27e  mov     r9, rdi; unsigned __int16 *
0x18001e281  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001e288  mov     rdx, rsi; unsigned __int16 *
0x18001e28b  mov     rcx, r14; this
0x18001e28e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e293  cmp     [rbx+18h], r15
0x18001e297  jnz     short loc_18001E2A9
0x18001e299  cmp     [rbx+48h], r15
0x18001e29d  jnz     short loc_18001E2A9
0x18001e29f  cmp     [rbx+30h], r15
0x18001e2a3  jz      loc_18001E339
0x18001e2a9  lea     r8, asc_18004C2E0; "    "
0x18001e2b0  mov     rdx, rsi; unsigned __int16 *
0x18001e2b3  mov     rcx, rax; this
0x18001e2b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e2bb  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001e2bf  test    r9, r9
0x18001e2c2  jz      short loc_18001E2D6
0x18001e2c4  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001e2cb  mov     rdx, rsi; unsigned __int16 *
0x18001e2ce  mov     rcx, rax; this
0x18001e2d1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e2d6  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001e2da  test    r9, r9
0x18001e2dd  jz      short loc_18001E2F1
0x18001e2df  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001e2e6  mov     rdx, rsi; unsigned __int16 *
0x18001e2e9  mov     rcx, rax; this
0x18001e2ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e2f1  mov     rcx, [rbx+28h]
0x18001e2f5  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001e2f9  mov     rdx, rsi; unsigned __int16 *
0x18001e2fc  test    rcx, rcx
0x18001e2ff  jz      short loc_18001E317
0x18001e301  mov     [rsp+278h+lpBuffer], rcx
0x18001e306  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001e30d  mov     rcx, rax; this
0x18001e310  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e315  jmp     short loc_18001E339
0x18001e317  mov     rcx, rax; this
0x18001e31a  test    r9, r9
0x18001e31d  jz      short loc_18001E32D
0x18001e31f  lea     r8, aHs; "[%hs]\n"
0x18001e326  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e32b  jmp     short loc_18001E339
0x18001e32d  lea     r8, asc_18004C358; "\n"
0x18001e334  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e339  xor     eax, eax
0x18001e33b  mov     rcx, [rsp+278h+var_38]
0x18001e343  xor     rcx, rsp; StackCookie
0x18001e346  call    __security_check_cookie
0x18001e34b  mov     rbx, [rsp+278h+arg_18]
0x18001e353  add     rsp, 250h
0x18001e35a  pop     r15
0x18001e35c  pop     r14
0x18001e35e  pop     rdi
0x18001e35f  pop     rsi
0x18001e360  pop     rbp
0x18001e361  retn
```
