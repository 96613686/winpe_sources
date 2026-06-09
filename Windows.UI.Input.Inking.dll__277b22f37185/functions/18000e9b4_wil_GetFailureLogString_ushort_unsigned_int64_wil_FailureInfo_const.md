# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000e9b4`
- end: `0x18000ec6a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a898`
- `0x1800104e8`
- `0x180010c24`
- `0x180014f80`

## callees

- `0x1800062a0`
- `0x180006f00`
- `0x18000e9b4`
- `0x1800107e8`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eb67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eb67`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000eae6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000eae6`

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
          v7 = (const char *)&byte_180112D88;
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
0x18000e9b4  mov     [rsp+arg_18], rbx
0x18000e9b9  push    rbp
0x18000e9ba  push    rsi
0x18000e9bb  push    rdi
0x18000e9bc  push    r14
0x18000e9be  push    r15
0x18000e9c0  sub     rsp, 250h
0x18000e9c7  mov     rax, cs:__security_cookie
0x18000e9ce  xor     rax, rsp
0x18000e9d1  mov     [rsp+278h+var_38], rax
0x18000e9d9  mov     rbx, r8
0x18000e9dc  mov     rsi, rdx
0x18000e9df  mov     r14, rcx
0x18000e9e2  xor     r15d, r15d
0x18000e9e5  test    rdx, rdx
0x18000e9e8  jz      loc_18000EC41
0x18000e9ee  test    rcx, rcx
0x18000e9f1  jz      loc_18000EC41
0x18000e9f7  mov     [rcx], r15w
0x18000e9fb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ea02  test    rax, rax
0x18000ea05  jz      short loc_18000EA28
0x18000ea07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000ea0e  jz      short loc_18000EA28
0x18000ea10  mov     r8, rdx
0x18000ea13  mov     rdx, rcx
0x18000ea16  mov     rcx, rbx
0x18000ea19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea1e  cmp     [r14], r15w
0x18000ea22  jnz     loc_18000EC41
0x18000ea28  mov     ecx, [rbx]
0x18000ea2a  mov     bpl, 8
0x18000ea2d  test    ecx, ecx
0x18000ea2f  jz      short loc_18000EA7A
0x18000ea31  sub     ecx, 1
0x18000ea34  jz      short loc_18000EA62
0x18000ea36  sub     ecx, 1
0x18000ea39  jz      short loc_18000EA52
0x18000ea3b  cmp     ecx, 1
0x18000ea3e  jz      short loc_18000EA49
0x18000ea40  lea     rdi, byte_180112D88
0x18000ea47  jmp     short loc_18000EA81
0x18000ea49  lea     rdi, aFailfast; "FailFast"
0x18000ea50  jmp     short loc_18000EA81
0x18000ea52  lea     rax, aLoghr; "LogHr"
0x18000ea59  lea     rdi, aLognt; "LogNt"
0x18000ea60  jmp     short loc_18000EA70
0x18000ea62  lea     rax, aReturnhr; "ReturnHr"
0x18000ea69  lea     rdi, aReturnnt; "ReturnNt"
0x18000ea70  test    [rbx+4], bpl
0x18000ea74  cmovz   rdi, rax
0x18000ea78  jmp     short loc_18000EA81
0x18000ea7a  lea     rdi, aException; "Exception"
0x18000ea81  xor     edx, edx; Val
0x18000ea83  mov     r8d, 200h; Size
0x18000ea89  lea     rcx, [rsp+278h+Buffer]; void *
0x18000ea8e  call    memset_0
0x18000ea93  test    [rbx+4], bpl
0x18000ea97  jz      short loc_18000EABC
0x18000ea99  mov     ebp, [rbx+0Ch]
0x18000ea9c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000eaa3  test    rax, rax
0x18000eaa6  jz      short loc_18000EAEC
0x18000eaa8  mov     r8d, 100h
0x18000eaae  lea     rdx, [rsp+278h+Buffer]
0x18000eab3  mov     ecx, ebp
0x18000eab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaba  jmp     short loc_18000EAEC
0x18000eabc  mov     ebp, [rbx+8]
0x18000eabf  mov     [rsp+278h+Arguments], r15; Arguments
0x18000eac4  mov     [rsp+278h+nSize], 100h; nSize
0x18000eacc  lea     rax, [rsp+278h+Buffer]
0x18000ead1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000ead6  mov     r9d, 400h; dwLanguageId
0x18000eadc  mov     r8d, ebp; dwMessageId
0x18000eadf  xor     edx, edx; lpSource
0x18000eae1  mov     ecx, 1200h; dwFlags
0x18000eae6  call    cs:__imp_FormatMessageW
0x18000eaec  lea     rsi, [r14+rsi*2]
0x18000eaf0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000eaf4  mov     rax, [rbx+88h]
0x18000eafb  mov     rcx, [rbx+80h]
0x18000eb02  mov     rdx, rsi; unsigned __int16 *
0x18000eb05  test    r9, r9
0x18000eb08  jz      short loc_18000EB2C
0x18000eb0a  mov     [rsp+278h+Arguments], rax
0x18000eb0f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000eb14  mov     eax, [rbx+40h]
0x18000eb17  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000eb1b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000eb22  mov     rcx, r14; this
0x18000eb25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eb2a  jmp     short loc_18000EB43
0x18000eb2c  mov     [rsp+278h+lpBuffer], rax
0x18000eb31  mov     r9, rcx; unsigned __int16 *
0x18000eb34  lea     r8, aHsP; "%hs!%p: "
0x18000eb3b  mov     rcx, r14; this
0x18000eb3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eb43  mov     r14, rax
0x18000eb46  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000eb4d  test    r9, r9
0x18000eb50  jz      short loc_18000EB67
0x18000eb52  lea     r8, aCallerP; "(caller: %p) "
0x18000eb59  mov     rdx, rsi; unsigned __int16 *
0x18000eb5c  mov     rcx, rax; this
0x18000eb5f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eb64  mov     r14, rax
0x18000eb67  call    cs:__imp_GetCurrentThreadId
0x18000eb6d  lea     rcx, [rsp+278h+Buffer]
0x18000eb72  mov     [rsp+278h+var_240], rcx
0x18000eb77  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000eb7b  mov     [rsp+278h+nSize], eax
0x18000eb7f  mov     eax, [rbx+44h]
0x18000eb82  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000eb86  mov     r9, rdi; unsigned __int16 *
0x18000eb89  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000eb90  mov     rdx, rsi; unsigned __int16 *
0x18000eb93  mov     rcx, r14; this
0x18000eb96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000eb9b  cmp     [rbx+18h], r15
0x18000eb9f  jnz     short loc_18000EBB1
0x18000eba1  cmp     [rbx+48h], r15
0x18000eba5  jnz     short loc_18000EBB1
0x18000eba7  cmp     [rbx+30h], r15
0x18000ebab  jz      loc_18000EC41
0x18000ebb1  lea     r8, asc_180112E90; "    "
0x18000ebb8  mov     rdx, rsi; unsigned __int16 *
0x18000ebbb  mov     rcx, rax; this
0x18000ebbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ebc3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000ebc7  test    r9, r9
0x18000ebca  jz      short loc_18000EBDE
0x18000ebcc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000ebd3  mov     rdx, rsi; unsigned __int16 *
0x18000ebd6  mov     rcx, rax; this
0x18000ebd9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ebde  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000ebe2  test    r9, r9
0x18000ebe5  jz      short loc_18000EBF9
0x18000ebe7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000ebee  mov     rdx, rsi; unsigned __int16 *
0x18000ebf1  mov     rcx, rax; this
0x18000ebf4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ebf9  mov     rcx, [rbx+28h]
0x18000ebfd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000ec01  mov     rdx, rsi; unsigned __int16 *
0x18000ec04  test    rcx, rcx
0x18000ec07  jz      short loc_18000EC1F
0x18000ec09  mov     [rsp+278h+lpBuffer], rcx
0x18000ec0e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000ec15  mov     rcx, rax; this
0x18000ec18  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ec1d  jmp     short loc_18000EC41
0x18000ec1f  mov     rcx, rax; this
0x18000ec22  test    r9, r9
0x18000ec25  jz      short loc_18000EC35
0x18000ec27  lea     r8, aHs; "[%hs]\n"
0x18000ec2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ec33  jmp     short loc_18000EC41
0x18000ec35  lea     r8, asc_180112F08; "\n"
0x18000ec3c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ec41  xor     eax, eax
0x18000ec43  mov     rcx, [rsp+278h+var_38]
0x18000ec4b  xor     rcx, rsp; StackCookie
0x18000ec4e  call    __security_check_cookie
0x18000ec53  mov     rbx, [rsp+278h+arg_18]
0x18000ec5b  add     rsp, 250h
0x18000ec62  pop     r15
0x18000ec64  pop     r14
0x18000ec66  pop     rdi
0x18000ec67  pop     rsi
0x18000ec68  pop     rbp
0x18000ec69  retn
```
