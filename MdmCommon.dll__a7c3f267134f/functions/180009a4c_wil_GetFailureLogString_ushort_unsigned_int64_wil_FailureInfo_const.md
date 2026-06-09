# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009a4c`
- end: `0x180009d0f`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180009274`
- `0x180009508`
- `0x18000a194`
- `0x18001a050`
- `0x18001e986`
- `0x18001eaba`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180009a4c`
- `0x18000a4a8`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c05`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009b7e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009b7e`

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
          v7 = (const char *)&byte_1800240B7;
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
0x180009a4c  mov     [rsp+arg_18], rbx
0x180009a51  push    rbp
0x180009a52  push    rsi
0x180009a53  push    rdi
0x180009a54  push    r14
0x180009a56  push    r15
0x180009a58  sub     rsp, 250h
0x180009a5f  mov     rax, cs:__security_cookie
0x180009a66  xor     rax, rsp
0x180009a69  mov     [rsp+278h+var_38], rax
0x180009a71  mov     rbx, r8
0x180009a74  mov     rsi, rdx
0x180009a77  mov     r14, rcx
0x180009a7a  xor     r15d, r15d
0x180009a7d  test    rdx, rdx
0x180009a80  jz      loc_180009CE5
0x180009a86  test    rcx, rcx
0x180009a89  jz      loc_180009CE5
0x180009a8f  mov     [rcx], r15w
0x180009a93  mov     rax, cs:g_pfnResultLoggingCallback
0x180009a9a  test    rax, rax
0x180009a9d  jz      short loc_180009AC0
0x180009a9f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009aa6  jz      short loc_180009AC0
0x180009aa8  mov     r8, rdx
0x180009aab  mov     rdx, rcx
0x180009aae  mov     rcx, rbx
0x180009ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ab6  cmp     [r14], r15w
0x180009aba  jnz     loc_180009CE5
0x180009ac0  mov     ecx, [rbx]
0x180009ac2  mov     bpl, 8
0x180009ac5  test    ecx, ecx
0x180009ac7  jz      short loc_180009B12
0x180009ac9  sub     ecx, 1
0x180009acc  jz      short loc_180009AFA
0x180009ace  sub     ecx, 1
0x180009ad1  jz      short loc_180009AEA
0x180009ad3  cmp     ecx, 1
0x180009ad6  jz      short loc_180009AE1
0x180009ad8  lea     rdi, byte_1800240B7
0x180009adf  jmp     short loc_180009B19
0x180009ae1  lea     rdi, aFailfast; "FailFast"
0x180009ae8  jmp     short loc_180009B19
0x180009aea  lea     rax, aLoghr; "LogHr"
0x180009af1  lea     rdi, aLognt; "LogNt"
0x180009af8  jmp     short loc_180009B08
0x180009afa  lea     rax, aReturnhr; "ReturnHr"
0x180009b01  lea     rdi, aReturnnt; "ReturnNt"
0x180009b08  test    [rbx+4], bpl
0x180009b0c  cmovz   rdi, rax
0x180009b10  jmp     short loc_180009B19
0x180009b12  lea     rdi, aException; "Exception"
0x180009b19  xor     edx, edx; Val
0x180009b1b  mov     r8d, 200h; Size
0x180009b21  lea     rcx, [rsp+278h+Buffer]; void *
0x180009b26  call    memset_0
0x180009b2b  test    [rbx+4], bpl
0x180009b2f  jz      short loc_180009B54
0x180009b31  mov     ebp, [rbx+0Ch]
0x180009b34  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009b3b  test    rax, rax
0x180009b3e  jz      short loc_180009B8A
0x180009b40  mov     r8d, 100h
0x180009b46  lea     rdx, [rsp+278h+Buffer]
0x180009b4b  mov     ecx, ebp
0x180009b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b52  jmp     short loc_180009B8A
0x180009b54  mov     ebp, [rbx+8]
0x180009b57  mov     [rsp+278h+Arguments], r15; Arguments
0x180009b5c  mov     [rsp+278h+nSize], 100h; nSize
0x180009b64  lea     rax, [rsp+278h+Buffer]
0x180009b69  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009b6e  mov     r9d, 400h; dwLanguageId
0x180009b74  mov     r8d, ebp; dwMessageId
0x180009b77  xor     edx, edx; lpSource
0x180009b79  mov     ecx, 1200h; dwFlags
0x180009b7e  call    cs:__imp_FormatMessageW
0x180009b85  nop     dword ptr [rax+rax+00h]
0x180009b8a  lea     rsi, [r14+rsi*2]
0x180009b8e  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009b92  mov     rax, [rbx+88h]
0x180009b99  mov     rcx, [rbx+80h]
0x180009ba0  mov     rdx, rsi; unsigned __int16 *
0x180009ba3  test    r9, r9
0x180009ba6  jz      short loc_180009BCA
0x180009ba8  mov     [rsp+278h+Arguments], rax
0x180009bad  mov     qword ptr [rsp+278h+nSize], rcx
0x180009bb2  mov     eax, [rbx+40h]
0x180009bb5  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009bb9  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009bc0  mov     rcx, r14; this
0x180009bc3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009bc8  jmp     short loc_180009BE1
0x180009bca  mov     [rsp+278h+lpBuffer], rax
0x180009bcf  mov     r9, rcx; unsigned __int16 *
0x180009bd2  lea     r8, aHsP; "%hs!%p: "
0x180009bd9  mov     rcx, r14; this
0x180009bdc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009be1  mov     r14, rax
0x180009be4  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009beb  test    r9, r9
0x180009bee  jz      short loc_180009C05
0x180009bf0  lea     r8, aCallerP; "(caller: %p) "
0x180009bf7  mov     rdx, rsi; unsigned __int16 *
0x180009bfa  mov     rcx, rax; this
0x180009bfd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c02  mov     r14, rax
0x180009c05  call    cs:__imp_GetCurrentThreadId
0x180009c0c  nop     dword ptr [rax+rax+00h]
0x180009c11  lea     rcx, [rsp+278h+Buffer]
0x180009c16  mov     [rsp+278h+var_240], rcx
0x180009c1b  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009c1f  mov     [rsp+278h+nSize], eax
0x180009c23  mov     eax, [rbx+44h]
0x180009c26  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009c2a  mov     r9, rdi; unsigned __int16 *
0x180009c2d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009c34  mov     rdx, rsi; unsigned __int16 *
0x180009c37  mov     rcx, r14; this
0x180009c3a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c3f  cmp     [rbx+18h], r15
0x180009c43  jnz     short loc_180009C55
0x180009c45  cmp     [rbx+48h], r15
0x180009c49  jnz     short loc_180009C55
0x180009c4b  cmp     [rbx+30h], r15
0x180009c4f  jz      loc_180009CE5
0x180009c55  lea     r8, asc_1800241A0; "    "
0x180009c5c  mov     rdx, rsi; unsigned __int16 *
0x180009c5f  mov     rcx, rax; this
0x180009c62  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c67  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009c6b  test    r9, r9
0x180009c6e  jz      short loc_180009C82
0x180009c70  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009c77  mov     rdx, rsi; unsigned __int16 *
0x180009c7a  mov     rcx, rax; this
0x180009c7d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c82  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009c86  test    r9, r9
0x180009c89  jz      short loc_180009C9D
0x180009c8b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009c92  mov     rdx, rsi; unsigned __int16 *
0x180009c95  mov     rcx, rax; this
0x180009c98  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c9d  mov     rcx, [rbx+28h]
0x180009ca1  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009ca5  mov     rdx, rsi; unsigned __int16 *
0x180009ca8  test    rcx, rcx
0x180009cab  jz      short loc_180009CC3
0x180009cad  mov     [rsp+278h+lpBuffer], rcx
0x180009cb2  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009cb9  mov     rcx, rax; this
0x180009cbc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cc1  jmp     short loc_180009CE5
0x180009cc3  mov     rcx, rax; this
0x180009cc6  test    r9, r9
0x180009cc9  jz      short loc_180009CD9
0x180009ccb  lea     r8, aHs; "[%hs]\n"
0x180009cd2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cd7  jmp     short loc_180009CE5
0x180009cd9  lea     r8, asc_180024218; "\n"
0x180009ce0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009ce5  xor     eax, eax
0x180009ce7  mov     rcx, [rsp+278h+var_38]
0x180009cef  xor     rcx, rsp; StackCookie
0x180009cf2  call    __security_check_cookie
0x180009cf7  mov     rbx, [rsp+278h+arg_18]
0x180009cff  add     rsp, 250h
0x180009d06  pop     r15
0x180009d08  pop     r14
0x180009d0a  pop     rdi
0x180009d0b  pop     rsi
0x180009d0c  pop     rbp
0x180009d0d  retn
```
