# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001e154`
- end: `0x18001e40a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001c5ac`
- `0x18001eb70`

## callees

- `0x1800174c0`
- `0x180017e20`
- `0x18001e154`
- `0x18001ee70`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e307`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e307`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001e286`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001e286`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&qword_180061980;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001e154  mov     [rsp+arg_18], rbx
0x18001e159  push    rbp
0x18001e15a  push    rsi
0x18001e15b  push    rdi
0x18001e15c  push    r14
0x18001e15e  push    r15
0x18001e160  sub     rsp, 250h
0x18001e167  mov     rax, cs:__security_cookie
0x18001e16e  xor     rax, rsp
0x18001e171  mov     [rsp+278h+var_38], rax
0x18001e179  xor     r15d, r15d
0x18001e17c  mov     rbx, r8
0x18001e17f  mov     rsi, rdx
0x18001e182  mov     r14, rcx
0x18001e185  test    rdx, rdx
0x18001e188  jz      loc_18001E3E1
0x18001e18e  test    rcx, rcx
0x18001e191  jz      loc_18001E3E1
0x18001e197  mov     rax, cs:g_pfnResultLoggingCallback
0x18001e19e  mov     [rcx], r15w
0x18001e1a2  test    rax, rax
0x18001e1a5  jz      short loc_18001E1C8
0x18001e1a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001e1ae  jz      short loc_18001E1C8
0x18001e1b0  mov     r8, rdx
0x18001e1b3  mov     rdx, rcx
0x18001e1b6  mov     rcx, rbx
0x18001e1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1be  cmp     [r14], r15w
0x18001e1c2  jnz     loc_18001E3E1
0x18001e1c8  mov     ecx, [rbx]
0x18001e1ca  mov     bpl, 8
0x18001e1cd  test    ecx, ecx
0x18001e1cf  jz      short loc_18001E21A
0x18001e1d1  sub     ecx, 1
0x18001e1d4  jz      short loc_18001E202
0x18001e1d6  sub     ecx, 1
0x18001e1d9  jz      short loc_18001E1F2
0x18001e1db  cmp     ecx, 1
0x18001e1de  jz      short loc_18001E1E9
0x18001e1e0  lea     rdi, qword_180061980
0x18001e1e7  jmp     short loc_18001E221
0x18001e1e9  lea     rdi, aFailfast; "FailFast"
0x18001e1f0  jmp     short loc_18001E221
0x18001e1f2  lea     rax, aLoghr; "LogHr"
0x18001e1f9  lea     rdi, aLognt; "LogNt"
0x18001e200  jmp     short loc_18001E210
0x18001e202  lea     rax, aReturnhr; "ReturnHr"
0x18001e209  lea     rdi, aReturnnt; "ReturnNt"
0x18001e210  test    [rbx+4], bpl
0x18001e214  cmovz   rdi, rax
0x18001e218  jmp     short loc_18001E221
0x18001e21a  lea     rdi, aException; "Exception"
0x18001e221  xor     edx, edx; Val
0x18001e223  lea     rcx, [rsp+278h+Buffer]; void *
0x18001e228  mov     r8d, 200h; Size
0x18001e22e  call    memset_0
0x18001e233  test    [rbx+4], bpl
0x18001e237  jz      short loc_18001E25C
0x18001e239  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001e240  mov     ebp, [rbx+0Ch]
0x18001e243  test    rax, rax
0x18001e246  jz      short loc_18001E28C
0x18001e248  mov     r8d, 100h
0x18001e24e  lea     rdx, [rsp+278h+Buffer]
0x18001e253  mov     ecx, ebp
0x18001e255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e25a  jmp     short loc_18001E28C
0x18001e25c  mov     ebp, [rbx+8]
0x18001e25f  lea     rax, [rsp+278h+Buffer]
0x18001e264  mov     [rsp+278h+Arguments], r15; Arguments
0x18001e269  mov     r8d, ebp; dwMessageId
0x18001e26c  mov     [rsp+278h+nSize], 100h; nSize
0x18001e274  mov     r9d, 400h; dwLanguageId
0x18001e27a  xor     edx, edx; lpSource
0x18001e27c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001e281  mov     ecx, 1200h; dwFlags
0x18001e286  call    cs:__imp_FormatMessageW
0x18001e28c  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001e290  lea     rsi, [r14+rsi*2]
0x18001e294  mov     rax, [rbx+88h]
0x18001e29b  mov     rdx, rsi; unsigned __int16 *
0x18001e29e  mov     rcx, [rbx+80h]
0x18001e2a5  test    r9, r9
0x18001e2a8  jz      short loc_18001E2CC
0x18001e2aa  mov     [rsp+278h+Arguments], rax
0x18001e2af  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001e2b6  mov     eax, [rbx+40h]
0x18001e2b9  mov     qword ptr [rsp+278h+nSize], rcx
0x18001e2be  mov     rcx, r14; this
0x18001e2c1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001e2c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e2ca  jmp     short loc_18001E2E3
0x18001e2cc  mov     r9, rcx; unsigned __int16 *
0x18001e2cf  mov     [rsp+278h+lpBuffer], rax
0x18001e2d4  mov     rcx, r14; this
0x18001e2d7  lea     r8, aHsP; "%hs!%p: "
0x18001e2de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e2e3  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001e2ea  mov     r14, rax
0x18001e2ed  test    r9, r9
0x18001e2f0  jz      short loc_18001E307
0x18001e2f2  lea     r8, aCallerP; "(caller: %p) "
0x18001e2f9  mov     rdx, rsi; unsigned __int16 *
0x18001e2fc  mov     rcx, rax; this
0x18001e2ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e304  mov     r14, rax
0x18001e307  call    cs:__imp_GetCurrentThreadId
0x18001e30d  lea     rcx, [rsp+278h+Buffer]
0x18001e312  mov     r9, rdi; unsigned __int16 *
0x18001e315  mov     [rsp+278h+var_240], rcx
0x18001e31a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001e321  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001e325  mov     rdx, rsi; unsigned __int16 *
0x18001e328  mov     [rsp+278h+nSize], eax
0x18001e32c  mov     rcx, r14; this
0x18001e32f  mov     eax, [rbx+44h]
0x18001e332  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001e336  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e33b  cmp     [rbx+18h], r15
0x18001e33f  jnz     short loc_18001E351
0x18001e341  cmp     [rbx+48h], r15
0x18001e345  jnz     short loc_18001E351
0x18001e347  cmp     [rbx+30h], r15
0x18001e34b  jz      loc_18001E3E1
0x18001e351  lea     r8, asc_180061078; "    "
0x18001e358  mov     rdx, rsi; unsigned __int16 *
0x18001e35b  mov     rcx, rax; this
0x18001e35e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e363  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001e367  test    r9, r9
0x18001e36a  jz      short loc_18001E37E
0x18001e36c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001e373  mov     rdx, rsi; unsigned __int16 *
0x18001e376  mov     rcx, rax; this
0x18001e379  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e37e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001e382  test    r9, r9
0x18001e385  jz      short loc_18001E399
0x18001e387  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001e38e  mov     rdx, rsi; unsigned __int16 *
0x18001e391  mov     rcx, rax; this
0x18001e394  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e399  mov     rcx, [rbx+28h]
0x18001e39d  mov     rdx, rsi; unsigned __int16 *
0x18001e3a0  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001e3a4  test    rcx, rcx
0x18001e3a7  jz      short loc_18001E3BF
0x18001e3a9  mov     [rsp+278h+lpBuffer], rcx
0x18001e3ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001e3b5  mov     rcx, rax; this
0x18001e3b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e3bd  jmp     short loc_18001E3E1
0x18001e3bf  mov     rcx, rax; this
0x18001e3c2  test    r9, r9
0x18001e3c5  jz      short loc_18001E3D5
0x18001e3c7  lea     r8, aHs; "[%hs]\n"
0x18001e3ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e3d3  jmp     short loc_18001E3E1
0x18001e3d5  lea     r8, asc_1800610F0; "\n"
0x18001e3dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e3e1  xor     eax, eax
0x18001e3e3  mov     rcx, [rsp+278h+var_38]
0x18001e3eb  xor     rcx, rsp; StackCookie
0x18001e3ee  call    __security_check_cookie
0x18001e3f3  mov     rbx, [rsp+278h+arg_18]
0x18001e3fb  add     rsp, 250h
0x18001e402  pop     r15
0x18001e404  pop     r14
0x18001e406  pop     rdi
0x18001e407  pop     rsi
0x18001e408  pop     rbp
0x18001e409  retn
```
