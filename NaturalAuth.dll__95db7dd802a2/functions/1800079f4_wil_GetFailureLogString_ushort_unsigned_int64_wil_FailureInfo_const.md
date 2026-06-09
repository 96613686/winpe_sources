# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800079f4`
- end: `0x180007caa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000672c`
- `0x18000846c`
- `0x180008920`
- `0x18000a5a0`

## callees

- `0x180004170`
- `0x180005140`
- `0x1800079f4`
- `0x18000876c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ba7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ba7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007b26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007b26`

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
          v7 = word_18004AAB2;
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
0x1800079f4  mov     [rsp+arg_18], rbx
0x1800079f9  push    rbp
0x1800079fa  push    rsi
0x1800079fb  push    rdi
0x1800079fc  push    r14
0x1800079fe  push    r15
0x180007a00  sub     rsp, 250h
0x180007a07  mov     rax, cs:__security_cookie
0x180007a0e  xor     rax, rsp
0x180007a11  mov     [rsp+278h+var_38], rax
0x180007a19  mov     rbx, r8
0x180007a1c  mov     rsi, rdx
0x180007a1f  mov     r14, rcx
0x180007a22  xor     r15d, r15d
0x180007a25  test    rdx, rdx
0x180007a28  jz      loc_180007C81
0x180007a2e  test    rcx, rcx
0x180007a31  jz      loc_180007C81
0x180007a37  mov     [rcx], r15w
0x180007a3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007a42  test    rax, rax
0x180007a45  jz      short loc_180007A68
0x180007a47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007a4e  jz      short loc_180007A68
0x180007a50  mov     r8, rdx
0x180007a53  mov     rdx, rcx
0x180007a56  mov     rcx, rbx
0x180007a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a5e  cmp     [r14], r15w
0x180007a62  jnz     loc_180007C81
0x180007a68  mov     ecx, [rbx]
0x180007a6a  mov     bpl, 8
0x180007a6d  test    ecx, ecx
0x180007a6f  jz      short loc_180007ABA
0x180007a71  sub     ecx, 1
0x180007a74  jz      short loc_180007AA2
0x180007a76  sub     ecx, 1
0x180007a79  jz      short loc_180007A92
0x180007a7b  cmp     ecx, 1
0x180007a7e  jz      short loc_180007A89
0x180007a80  lea     rdi, word_18004AAB2
0x180007a87  jmp     short loc_180007AC1
0x180007a89  lea     rdi, aFailfast; "FailFast"
0x180007a90  jmp     short loc_180007AC1
0x180007a92  lea     rax, aLoghr; "LogHr"
0x180007a99  lea     rdi, aLognt; "LogNt"
0x180007aa0  jmp     short loc_180007AB0
0x180007aa2  lea     rax, aReturnhr; "ReturnHr"
0x180007aa9  lea     rdi, aReturnnt; "ReturnNt"
0x180007ab0  test    [rbx+4], bpl
0x180007ab4  cmovz   rdi, rax
0x180007ab8  jmp     short loc_180007AC1
0x180007aba  lea     rdi, aException; "Exception"
0x180007ac1  xor     edx, edx; Val
0x180007ac3  mov     r8d, 200h; Size
0x180007ac9  lea     rcx, [rsp+278h+Buffer]; void *
0x180007ace  call    memset_0
0x180007ad3  test    [rbx+4], bpl
0x180007ad7  jz      short loc_180007AFC
0x180007ad9  mov     ebp, [rbx+0Ch]
0x180007adc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007ae3  test    rax, rax
0x180007ae6  jz      short loc_180007B2C
0x180007ae8  mov     r8d, 100h
0x180007aee  lea     rdx, [rsp+278h+Buffer]
0x180007af3  mov     ecx, ebp
0x180007af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007afa  jmp     short loc_180007B2C
0x180007afc  mov     ebp, [rbx+8]
0x180007aff  mov     [rsp+278h+Arguments], r15; Arguments
0x180007b04  mov     [rsp+278h+nSize], 100h; nSize
0x180007b0c  lea     rax, [rsp+278h+Buffer]
0x180007b11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007b16  mov     r9d, 400h; dwLanguageId
0x180007b1c  mov     r8d, ebp; dwMessageId
0x180007b1f  xor     edx, edx; lpSource
0x180007b21  mov     ecx, 1200h; dwFlags
0x180007b26  call    cs:__imp_FormatMessageW
0x180007b2c  lea     rsi, [r14+rsi*2]
0x180007b30  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007b34  mov     rax, [rbx+88h]
0x180007b3b  mov     rcx, [rbx+80h]
0x180007b42  mov     rdx, rsi; unsigned __int16 *
0x180007b45  test    r9, r9
0x180007b48  jz      short loc_180007B6C
0x180007b4a  mov     [rsp+278h+Arguments], rax
0x180007b4f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007b54  mov     eax, [rbx+40h]
0x180007b57  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007b5b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007b62  mov     rcx, r14; this
0x180007b65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b6a  jmp     short loc_180007B83
0x180007b6c  mov     [rsp+278h+lpBuffer], rax
0x180007b71  mov     r9, rcx; unsigned __int16 *
0x180007b74  lea     r8, aHsP; "%hs!%p: "
0x180007b7b  mov     rcx, r14; this
0x180007b7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b83  mov     r14, rax
0x180007b86  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007b8d  test    r9, r9
0x180007b90  jz      short loc_180007BA7
0x180007b92  lea     r8, aCallerP; "(caller: %p) "
0x180007b99  mov     rdx, rsi; unsigned __int16 *
0x180007b9c  mov     rcx, rax; this
0x180007b9f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007ba4  mov     r14, rax
0x180007ba7  call    cs:__imp_GetCurrentThreadId
0x180007bad  lea     rcx, [rsp+278h+Buffer]
0x180007bb2  mov     [rsp+278h+var_240], rcx
0x180007bb7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007bbb  mov     [rsp+278h+nSize], eax
0x180007bbf  mov     eax, [rbx+44h]
0x180007bc2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007bc6  mov     r9, rdi; unsigned __int16 *
0x180007bc9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007bd0  mov     rdx, rsi; unsigned __int16 *
0x180007bd3  mov     rcx, r14; this
0x180007bd6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007bdb  cmp     [rbx+18h], r15
0x180007bdf  jnz     short loc_180007BF1
0x180007be1  cmp     [rbx+48h], r15
0x180007be5  jnz     short loc_180007BF1
0x180007be7  cmp     [rbx+30h], r15
0x180007beb  jz      loc_180007C81
0x180007bf1  lea     r8, asc_18004ABA0; "    "
0x180007bf8  mov     rdx, rsi; unsigned __int16 *
0x180007bfb  mov     rcx, rax; this
0x180007bfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007c03  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007c07  test    r9, r9
0x180007c0a  jz      short loc_180007C1E
0x180007c0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007c13  mov     rdx, rsi; unsigned __int16 *
0x180007c16  mov     rcx, rax; this
0x180007c19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007c1e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007c22  test    r9, r9
0x180007c25  jz      short loc_180007C39
0x180007c27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007c2e  mov     rdx, rsi; unsigned __int16 *
0x180007c31  mov     rcx, rax; this
0x180007c34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007c39  mov     rcx, [rbx+28h]
0x180007c3d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007c41  mov     rdx, rsi; unsigned __int16 *
0x180007c44  test    rcx, rcx
0x180007c47  jz      short loc_180007C5F
0x180007c49  mov     [rsp+278h+lpBuffer], rcx
0x180007c4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007c55  mov     rcx, rax; this
0x180007c58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007c5d  jmp     short loc_180007C81
0x180007c5f  mov     rcx, rax; this
0x180007c62  test    r9, r9
0x180007c65  jz      short loc_180007C75
0x180007c67  lea     r8, aHs; "[%hs]\n"
0x180007c6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007c73  jmp     short loc_180007C81
0x180007c75  lea     r8, asc_18004AC18; "\n"
0x180007c7c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007c81  xor     eax, eax
0x180007c83  mov     rcx, [rsp+278h+var_38]
0x180007c8b  xor     rcx, rsp; StackCookie
0x180007c8e  call    __security_check_cookie
0x180007c93  mov     rbx, [rsp+278h+arg_18]
0x180007c9b  add     rsp, 250h
0x180007ca2  pop     r15
0x180007ca4  pop     r14
0x180007ca6  pop     rdi
0x180007ca7  pop     rsi
0x180007ca8  pop     rbp
0x180007ca9  retn
```
