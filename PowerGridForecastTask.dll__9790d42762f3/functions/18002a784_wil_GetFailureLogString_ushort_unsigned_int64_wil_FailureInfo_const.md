# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002a784`
- end: `0x18002aa3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18002737c`
- `0x1800275e4`
- `0x18002b400`
- `0x180030670`

## callees

- `0x1800268ef`
- `0x18002a784`
- `0x18002b700`
- `0x1800350e0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a937`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a8b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a8b6`

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
          v7 = (const char *)&byte_18003D198;
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
0x18002a784  mov     [rsp+arg_18], rbx
0x18002a789  push    rbp
0x18002a78a  push    rsi
0x18002a78b  push    rdi
0x18002a78c  push    r14
0x18002a78e  push    r15
0x18002a790  sub     rsp, 250h
0x18002a797  mov     rax, cs:__security_cookie
0x18002a79e  xor     rax, rsp
0x18002a7a1  mov     [rsp+278h+var_38], rax
0x18002a7a9  mov     rbx, r8
0x18002a7ac  mov     rsi, rdx
0x18002a7af  mov     r14, rcx
0x18002a7b2  xor     r15d, r15d
0x18002a7b5  test    rdx, rdx
0x18002a7b8  jz      loc_18002AA11
0x18002a7be  test    rcx, rcx
0x18002a7c1  jz      loc_18002AA11
0x18002a7c7  mov     [rcx], r15w
0x18002a7cb  mov     rax, cs:g_pfnResultLoggingCallback
0x18002a7d2  test    rax, rax
0x18002a7d5  jz      short loc_18002A7F8
0x18002a7d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002a7de  jz      short loc_18002A7F8
0x18002a7e0  mov     r8, rdx
0x18002a7e3  mov     rdx, rcx
0x18002a7e6  mov     rcx, rbx
0x18002a7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7ee  cmp     [r14], r15w
0x18002a7f2  jnz     loc_18002AA11
0x18002a7f8  mov     ecx, [rbx]
0x18002a7fa  mov     bpl, 8
0x18002a7fd  test    ecx, ecx
0x18002a7ff  jz      short loc_18002A84A
0x18002a801  sub     ecx, 1
0x18002a804  jz      short loc_18002A832
0x18002a806  sub     ecx, 1
0x18002a809  jz      short loc_18002A822
0x18002a80b  cmp     ecx, 1
0x18002a80e  jz      short loc_18002A819
0x18002a810  lea     rdi, byte_18003D198
0x18002a817  jmp     short loc_18002A851
0x18002a819  lea     rdi, aFailfast; "FailFast"
0x18002a820  jmp     short loc_18002A851
0x18002a822  lea     rax, aLoghr; "LogHr"
0x18002a829  lea     rdi, aLognt; "LogNt"
0x18002a830  jmp     short loc_18002A840
0x18002a832  lea     rax, aReturnhr; "ReturnHr"
0x18002a839  lea     rdi, aReturnnt; "ReturnNt"
0x18002a840  test    [rbx+4], bpl
0x18002a844  cmovz   rdi, rax
0x18002a848  jmp     short loc_18002A851
0x18002a84a  lea     rdi, aException; "Exception"
0x18002a851  xor     edx, edx; Val
0x18002a853  mov     r8d, 200h; Size
0x18002a859  lea     rcx, [rsp+278h+Buffer]; void *
0x18002a85e  call    memset_0
0x18002a863  test    [rbx+4], bpl
0x18002a867  jz      short loc_18002A88C
0x18002a869  mov     ebp, [rbx+0Ch]
0x18002a86c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002a873  test    rax, rax
0x18002a876  jz      short loc_18002A8BC
0x18002a878  mov     r8d, 100h
0x18002a87e  lea     rdx, [rsp+278h+Buffer]
0x18002a883  mov     ecx, ebp
0x18002a885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a88a  jmp     short loc_18002A8BC
0x18002a88c  mov     ebp, [rbx+8]
0x18002a88f  mov     [rsp+278h+Arguments], r15; Arguments
0x18002a894  mov     [rsp+278h+nSize], 100h; nSize
0x18002a89c  lea     rax, [rsp+278h+Buffer]
0x18002a8a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002a8a6  mov     r9d, 400h; dwLanguageId
0x18002a8ac  mov     r8d, ebp; dwMessageId
0x18002a8af  xor     edx, edx; lpSource
0x18002a8b1  mov     ecx, 1200h; dwFlags
0x18002a8b6  call    cs:__imp_FormatMessageW
0x18002a8bc  lea     rsi, [r14+rsi*2]
0x18002a8c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002a8c4  mov     rax, [rbx+88h]
0x18002a8cb  mov     rcx, [rbx+80h]
0x18002a8d2  mov     rdx, rsi; unsigned __int16 *
0x18002a8d5  test    r9, r9
0x18002a8d8  jz      short loc_18002A8FC
0x18002a8da  mov     [rsp+278h+Arguments], rax
0x18002a8df  mov     qword ptr [rsp+278h+nSize], rcx
0x18002a8e4  mov     eax, [rbx+40h]
0x18002a8e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002a8eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002a8f2  mov     rcx, r14; this
0x18002a8f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a8fa  jmp     short loc_18002A913
0x18002a8fc  mov     [rsp+278h+lpBuffer], rax
0x18002a901  mov     r9, rcx; unsigned __int16 *
0x18002a904  lea     r8, aHsP; "%hs!%p: "
0x18002a90b  mov     rcx, r14; this
0x18002a90e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a913  mov     r14, rax
0x18002a916  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002a91d  test    r9, r9
0x18002a920  jz      short loc_18002A937
0x18002a922  lea     r8, aCallerP; "(caller: %p) "
0x18002a929  mov     rdx, rsi; unsigned __int16 *
0x18002a92c  mov     rcx, rax; this
0x18002a92f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a934  mov     r14, rax
0x18002a937  call    cs:__imp_GetCurrentThreadId
0x18002a93d  lea     rcx, [rsp+278h+Buffer]
0x18002a942  mov     [rsp+278h+var_240], rcx
0x18002a947  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002a94b  mov     [rsp+278h+nSize], eax
0x18002a94f  mov     eax, [rbx+44h]
0x18002a952  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002a956  mov     r9, rdi; unsigned __int16 *
0x18002a959  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002a960  mov     rdx, rsi; unsigned __int16 *
0x18002a963  mov     rcx, r14; this
0x18002a966  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a96b  cmp     [rbx+18h], r15
0x18002a96f  jnz     short loc_18002A981
0x18002a971  cmp     [rbx+48h], r15
0x18002a975  jnz     short loc_18002A981
0x18002a977  cmp     [rbx+30h], r15
0x18002a97b  jz      loc_18002AA11
0x18002a981  lea     r8, asc_18003D288; "    "
0x18002a988  mov     rdx, rsi; unsigned __int16 *
0x18002a98b  mov     rcx, rax; this
0x18002a98e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a993  mov     r9, [rbx+18h]; unsigned __int16 *
0x18002a997  test    r9, r9
0x18002a99a  jz      short loc_18002A9AE
0x18002a99c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002a9a3  mov     rdx, rsi; unsigned __int16 *
0x18002a9a6  mov     rcx, rax; this
0x18002a9a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a9ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x18002a9b2  test    r9, r9
0x18002a9b5  jz      short loc_18002A9C9
0x18002a9b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002a9be  mov     rdx, rsi; unsigned __int16 *
0x18002a9c1  mov     rcx, rax; this
0x18002a9c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a9c9  mov     rcx, [rbx+28h]
0x18002a9cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18002a9d1  mov     rdx, rsi; unsigned __int16 *
0x18002a9d4  test    rcx, rcx
0x18002a9d7  jz      short loc_18002A9EF
0x18002a9d9  mov     [rsp+278h+lpBuffer], rcx
0x18002a9de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002a9e5  mov     rcx, rax; this
0x18002a9e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002a9ed  jmp     short loc_18002AA11
0x18002a9ef  mov     rcx, rax; this
0x18002a9f2  test    r9, r9
0x18002a9f5  jz      short loc_18002AA05
0x18002a9f7  lea     r8, aHs; "[%hs]\n"
0x18002a9fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002aa03  jmp     short loc_18002AA11
0x18002aa05  lea     r8, asc_18003D300; "\n"
0x18002aa0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002aa11  xor     eax, eax
0x18002aa13  mov     rcx, [rsp+278h+var_38]
0x18002aa1b  xor     rcx, rsp; StackCookie
0x18002aa1e  call    __security_check_cookie
0x18002aa23  mov     rbx, [rsp+278h+arg_18]
0x18002aa2b  add     rsp, 250h
0x18002aa32  pop     r15
0x18002aa34  pop     r14
0x18002aa36  pop     rdi
0x18002aa37  pop     rsi
0x18002aa38  pop     rbp
0x18002aa39  retn
```
