# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180010984`
- end: `0x180010c3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f924`
- `0x180011474`
- `0x180011964`
- `0x180013180`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x180010984`
- `0x180011758`
- `0x18012d010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180010ab6`
- `KERNEL32!FormatMessageW` at `0x180010ab6`
- `KERNEL32!GetCurrentThreadId` at `0x180010b37`
- `KERNEL32!GetCurrentThreadId` at `0x180010b37`

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
          v7 = (const char *)&word_18013829C;
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
0x180010984  mov     [rsp+arg_18], rbx
0x180010989  push    rbp
0x18001098a  push    rsi
0x18001098b  push    rdi
0x18001098c  push    r14
0x18001098e  push    r15
0x180010990  sub     rsp, 250h
0x180010997  mov     rax, cs:__security_cookie
0x18001099e  xor     rax, rsp
0x1800109a1  mov     [rsp+278h+var_38], rax
0x1800109a9  mov     rbx, r8
0x1800109ac  mov     rsi, rdx
0x1800109af  mov     r14, rcx
0x1800109b2  xor     r15d, r15d
0x1800109b5  test    rdx, rdx
0x1800109b8  jz      loc_180010C11
0x1800109be  test    rcx, rcx
0x1800109c1  jz      loc_180010C11
0x1800109c7  mov     [rcx], r15w
0x1800109cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800109d2  test    rax, rax
0x1800109d5  jz      short loc_1800109F8
0x1800109d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800109de  jz      short loc_1800109F8
0x1800109e0  mov     r8, rdx
0x1800109e3  mov     rdx, rcx
0x1800109e6  mov     rcx, rbx
0x1800109e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ee  cmp     [r14], r15w
0x1800109f2  jnz     loc_180010C11
0x1800109f8  mov     ecx, [rbx]
0x1800109fa  mov     bpl, 8
0x1800109fd  test    ecx, ecx
0x1800109ff  jz      short loc_180010A4A
0x180010a01  sub     ecx, 1
0x180010a04  jz      short loc_180010A32
0x180010a06  sub     ecx, 1
0x180010a09  jz      short loc_180010A22
0x180010a0b  cmp     ecx, 1
0x180010a0e  jz      short loc_180010A19
0x180010a10  lea     rdi, word_18013829C
0x180010a17  jmp     short loc_180010A51
0x180010a19  lea     rdi, aFailfast; "FailFast"
0x180010a20  jmp     short loc_180010A51
0x180010a22  lea     rax, aLoghr; "LogHr"
0x180010a29  lea     rdi, aLognt; "LogNt"
0x180010a30  jmp     short loc_180010A40
0x180010a32  lea     rax, aReturnhr; "ReturnHr"
0x180010a39  lea     rdi, aReturnnt; "ReturnNt"
0x180010a40  test    [rbx+4], bpl
0x180010a44  cmovz   rdi, rax
0x180010a48  jmp     short loc_180010A51
0x180010a4a  lea     rdi, aException; "Exception"
0x180010a51  xor     edx, edx; Val
0x180010a53  mov     r8d, 200h; Size
0x180010a59  lea     rcx, [rsp+278h+Buffer]; void *
0x180010a5e  call    memset_0
0x180010a63  test    [rbx+4], bpl
0x180010a67  jz      short loc_180010A8C
0x180010a69  mov     ebp, [rbx+0Ch]
0x180010a6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180010a73  test    rax, rax
0x180010a76  jz      short loc_180010ABC
0x180010a78  mov     r8d, 100h
0x180010a7e  lea     rdx, [rsp+278h+Buffer]
0x180010a83  mov     ecx, ebp
0x180010a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a8a  jmp     short loc_180010ABC
0x180010a8c  mov     ebp, [rbx+8]
0x180010a8f  mov     [rsp+278h+Arguments], r15; Arguments
0x180010a94  mov     [rsp+278h+nSize], 100h; nSize
0x180010a9c  lea     rax, [rsp+278h+Buffer]
0x180010aa1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180010aa6  mov     r9d, 400h; dwLanguageId
0x180010aac  mov     r8d, ebp; dwMessageId
0x180010aaf  xor     edx, edx; lpSource
0x180010ab1  mov     ecx, 1200h; dwFlags
0x180010ab6  call    cs:__imp_FormatMessageW
0x180010abc  lea     rsi, [r14+rsi*2]
0x180010ac0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180010ac4  mov     rax, [rbx+88h]
0x180010acb  mov     rcx, [rbx+80h]
0x180010ad2  mov     rdx, rsi; unsigned __int16 *
0x180010ad5  test    r9, r9
0x180010ad8  jz      short loc_180010AFC
0x180010ada  mov     [rsp+278h+Arguments], rax
0x180010adf  mov     qword ptr [rsp+278h+nSize], rcx
0x180010ae4  mov     eax, [rbx+40h]
0x180010ae7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180010aeb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180010af2  mov     rcx, r14; this
0x180010af5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010afa  jmp     short loc_180010B13
0x180010afc  mov     [rsp+278h+lpBuffer], rax
0x180010b01  mov     r9, rcx; unsigned __int16 *
0x180010b04  lea     r8, aHsP; "%hs!%p: "
0x180010b0b  mov     rcx, r14; this
0x180010b0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010b13  mov     r14, rax
0x180010b16  mov     r9, [rbx+90h]; unsigned __int16 *
0x180010b1d  test    r9, r9
0x180010b20  jz      short loc_180010B37
0x180010b22  lea     r8, aCallerP; "(caller: %p) "
0x180010b29  mov     rdx, rsi; unsigned __int16 *
0x180010b2c  mov     rcx, rax; this
0x180010b2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010b34  mov     r14, rax
0x180010b37  call    cs:__imp_GetCurrentThreadId
0x180010b3d  lea     rcx, [rsp+278h+Buffer]
0x180010b42  mov     [rsp+278h+var_240], rcx
0x180010b47  mov     dword ptr [rsp+278h+Arguments], ebp
0x180010b4b  mov     [rsp+278h+nSize], eax
0x180010b4f  mov     eax, [rbx+44h]
0x180010b52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180010b56  mov     r9, rdi; unsigned __int16 *
0x180010b59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180010b60  mov     rdx, rsi; unsigned __int16 *
0x180010b63  mov     rcx, r14; this
0x180010b66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010b6b  cmp     [rbx+18h], r15
0x180010b6f  jnz     short loc_180010B81
0x180010b71  cmp     [rbx+48h], r15
0x180010b75  jnz     short loc_180010B81
0x180010b77  cmp     [rbx+30h], r15
0x180010b7b  jz      loc_180010C11
0x180010b81  lea     r8, asc_1801383B8; "    "
0x180010b88  mov     rdx, rsi; unsigned __int16 *
0x180010b8b  mov     rcx, rax; this
0x180010b8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010b93  mov     r9, [rbx+18h]; unsigned __int16 *
0x180010b97  test    r9, r9
0x180010b9a  jz      short loc_180010BAE
0x180010b9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180010ba3  mov     rdx, rsi; unsigned __int16 *
0x180010ba6  mov     rcx, rax; this
0x180010ba9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010bae  mov     r9, [rbx+48h]; unsigned __int16 *
0x180010bb2  test    r9, r9
0x180010bb5  jz      short loc_180010BC9
0x180010bb7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180010bbe  mov     rdx, rsi; unsigned __int16 *
0x180010bc1  mov     rcx, rax; this
0x180010bc4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010bc9  mov     rcx, [rbx+28h]
0x180010bcd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180010bd1  mov     rdx, rsi; unsigned __int16 *
0x180010bd4  test    rcx, rcx
0x180010bd7  jz      short loc_180010BEF
0x180010bd9  mov     [rsp+278h+lpBuffer], rcx
0x180010bde  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180010be5  mov     rcx, rax; this
0x180010be8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010bed  jmp     short loc_180010C11
0x180010bef  mov     rcx, rax; this
0x180010bf2  test    r9, r9
0x180010bf5  jz      short loc_180010C05
0x180010bf7  lea     r8, aHs; "[%hs]\n"
0x180010bfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010c03  jmp     short loc_180010C11
0x180010c05  lea     r8, asc_180138430; "\n"
0x180010c0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010c11  xor     eax, eax
0x180010c13  mov     rcx, [rsp+278h+var_38]
0x180010c1b  xor     rcx, rsp; StackCookie
0x180010c1e  call    __security_check_cookie
0x180010c23  mov     rbx, [rsp+278h+arg_18]
0x180010c2b  add     rsp, 250h
0x180010c32  pop     r15
0x180010c34  pop     r14
0x180010c36  pop     rdi
0x180010c37  pop     rsi
0x180010c38  pop     rbp
0x180010c39  retn
```
