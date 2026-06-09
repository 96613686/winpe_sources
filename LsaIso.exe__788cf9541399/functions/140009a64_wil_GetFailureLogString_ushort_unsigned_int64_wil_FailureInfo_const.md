# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140009a64`
- end: `0x140009d1a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000aaec`
- `0x14000dd10`

## callees

- `0x140009a64`
- `0x14000ade8`
- `0x140038cd2`
- `0x140038d10`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009c17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009c17`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140009b96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140009b96`

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
          v7 = (const char *)&word_140046C0A;
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
0x140009a64  mov     [rsp+arg_18], rbx
0x140009a69  push    rbp
0x140009a6a  push    rsi
0x140009a6b  push    rdi
0x140009a6c  push    r14
0x140009a6e  push    r15
0x140009a70  sub     rsp, 250h
0x140009a77  mov     rax, cs:__security_cookie
0x140009a7e  xor     rax, rsp
0x140009a81  mov     [rsp+278h+var_38], rax
0x140009a89  mov     rbx, r8
0x140009a8c  mov     rsi, rdx
0x140009a8f  mov     r14, rcx
0x140009a92  xor     r15d, r15d
0x140009a95  test    rdx, rdx
0x140009a98  jz      loc_140009CF1
0x140009a9e  test    rcx, rcx
0x140009aa1  jz      loc_140009CF1
0x140009aa7  mov     [rcx], r15w
0x140009aab  mov     rax, cs:g_pfnResultLoggingCallback
0x140009ab2  test    rax, rax
0x140009ab5  jz      short loc_140009AD8
0x140009ab7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140009abe  jz      short loc_140009AD8
0x140009ac0  mov     r8, rdx
0x140009ac3  mov     rdx, rcx
0x140009ac6  mov     rcx, rbx
0x140009ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ace  cmp     [r14], r15w
0x140009ad2  jnz     loc_140009CF1
0x140009ad8  mov     ecx, [rbx]
0x140009ada  mov     bpl, 8
0x140009add  test    ecx, ecx
0x140009adf  jz      short loc_140009B2A
0x140009ae1  sub     ecx, 1
0x140009ae4  jz      short loc_140009B12
0x140009ae6  sub     ecx, 1
0x140009ae9  jz      short loc_140009B02
0x140009aeb  cmp     ecx, 1
0x140009aee  jz      short loc_140009AF9
0x140009af0  lea     rdi, word_140046C0A
0x140009af7  jmp     short loc_140009B31
0x140009af9  lea     rdi, aFailfast; "FailFast"
0x140009b00  jmp     short loc_140009B31
0x140009b02  lea     rax, aLoghr; "LogHr"
0x140009b09  lea     rdi, aLognt; "LogNt"
0x140009b10  jmp     short loc_140009B20
0x140009b12  lea     rax, aReturnhr; "ReturnHr"
0x140009b19  lea     rdi, aReturnnt; "ReturnNt"
0x140009b20  test    [rbx+4], bpl
0x140009b24  cmovz   rdi, rax
0x140009b28  jmp     short loc_140009B31
0x140009b2a  lea     rdi, aException; "Exception"
0x140009b31  xor     edx, edx; Val
0x140009b33  mov     r8d, 200h; Size
0x140009b39  lea     rcx, [rsp+278h+Buffer]; void *
0x140009b3e  call    memset_0
0x140009b43  test    [rbx+4], bpl
0x140009b47  jz      short loc_140009B6C
0x140009b49  mov     ebp, [rbx+0Ch]
0x140009b4c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140009b53  test    rax, rax
0x140009b56  jz      short loc_140009B9C
0x140009b58  mov     r8d, 100h
0x140009b5e  lea     rdx, [rsp+278h+Buffer]
0x140009b63  mov     ecx, ebp
0x140009b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b6a  jmp     short loc_140009B9C
0x140009b6c  mov     ebp, [rbx+8]
0x140009b6f  mov     [rsp+278h+Arguments], r15; Arguments
0x140009b74  mov     [rsp+278h+nSize], 100h; nSize
0x140009b7c  lea     rax, [rsp+278h+Buffer]
0x140009b81  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140009b86  mov     r9d, 400h; dwLanguageId
0x140009b8c  mov     r8d, ebp; dwMessageId
0x140009b8f  xor     edx, edx; lpSource
0x140009b91  mov     ecx, 1200h; dwFlags
0x140009b96  call    cs:__imp_FormatMessageW
0x140009b9c  lea     rsi, [r14+rsi*2]
0x140009ba0  mov     r9, [rbx+38h]; unsigned __int16 *
0x140009ba4  mov     rax, [rbx+88h]
0x140009bab  mov     rcx, [rbx+80h]
0x140009bb2  mov     rdx, rsi; unsigned __int16 *
0x140009bb5  test    r9, r9
0x140009bb8  jz      short loc_140009BDC
0x140009bba  mov     [rsp+278h+Arguments], rax
0x140009bbf  mov     qword ptr [rsp+278h+nSize], rcx
0x140009bc4  mov     eax, [rbx+40h]
0x140009bc7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140009bcb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140009bd2  mov     rcx, r14; this
0x140009bd5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009bda  jmp     short loc_140009BF3
0x140009bdc  mov     [rsp+278h+lpBuffer], rax
0x140009be1  mov     r9, rcx; unsigned __int16 *
0x140009be4  lea     r8, aHsP; "%hs!%p: "
0x140009beb  mov     rcx, r14; this
0x140009bee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009bf3  mov     r14, rax
0x140009bf6  mov     r9, [rbx+90h]; unsigned __int16 *
0x140009bfd  test    r9, r9
0x140009c00  jz      short loc_140009C17
0x140009c02  lea     r8, aCallerP; "(caller: %p) "
0x140009c09  mov     rdx, rsi; unsigned __int16 *
0x140009c0c  mov     rcx, rax; this
0x140009c0f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009c14  mov     r14, rax
0x140009c17  call    cs:__imp_GetCurrentThreadId
0x140009c1d  lea     rcx, [rsp+278h+Buffer]
0x140009c22  mov     [rsp+278h+var_240], rcx
0x140009c27  mov     dword ptr [rsp+278h+Arguments], ebp
0x140009c2b  mov     [rsp+278h+nSize], eax
0x140009c2f  mov     eax, [rbx+44h]
0x140009c32  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140009c36  mov     r9, rdi; unsigned __int16 *
0x140009c39  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140009c40  mov     rdx, rsi; unsigned __int16 *
0x140009c43  mov     rcx, r14; this
0x140009c46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009c4b  cmp     [rbx+18h], r15
0x140009c4f  jnz     short loc_140009C61
0x140009c51  cmp     [rbx+48h], r15
0x140009c55  jnz     short loc_140009C61
0x140009c57  cmp     [rbx+30h], r15
0x140009c5b  jz      loc_140009CF1
0x140009c61  lea     r8, asc_140046CF8; "    "
0x140009c68  mov     rdx, rsi; unsigned __int16 *
0x140009c6b  mov     rcx, rax; this
0x140009c6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009c73  mov     r9, [rbx+18h]; unsigned __int16 *
0x140009c77  test    r9, r9
0x140009c7a  jz      short loc_140009C8E
0x140009c7c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140009c83  mov     rdx, rsi; unsigned __int16 *
0x140009c86  mov     rcx, rax; this
0x140009c89  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009c8e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140009c92  test    r9, r9
0x140009c95  jz      short loc_140009CA9
0x140009c97  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140009c9e  mov     rdx, rsi; unsigned __int16 *
0x140009ca1  mov     rcx, rax; this
0x140009ca4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009ca9  mov     rcx, [rbx+28h]
0x140009cad  mov     r9, [rbx+30h]; unsigned __int16 *
0x140009cb1  mov     rdx, rsi; unsigned __int16 *
0x140009cb4  test    rcx, rcx
0x140009cb7  jz      short loc_140009CCF
0x140009cb9  mov     [rsp+278h+lpBuffer], rcx
0x140009cbe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140009cc5  mov     rcx, rax; this
0x140009cc8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009ccd  jmp     short loc_140009CF1
0x140009ccf  mov     rcx, rax; this
0x140009cd2  test    r9, r9
0x140009cd5  jz      short loc_140009CE5
0x140009cd7  lea     r8, aHs; "[%hs]\n"
0x140009cde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009ce3  jmp     short loc_140009CF1
0x140009ce5  lea     r8, asc_140046D70; "\n"
0x140009cec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009cf1  xor     eax, eax
0x140009cf3  mov     rcx, [rsp+278h+var_38]
0x140009cfb  xor     rcx, rsp; StackCookie
0x140009cfe  call    __security_check_cookie
0x140009d03  mov     rbx, [rsp+278h+arg_18]
0x140009d0b  add     rsp, 250h
0x140009d12  pop     r15
0x140009d14  pop     r14
0x140009d16  pop     rdi
0x140009d17  pop     rsi
0x140009d18  pop     rbp
0x140009d19  retn
```
