# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001e9a4`
- end: `0x18001ec5a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f740`
- `0x180022910`

## callees

- `0x18001be10`
- `0x18001c7a8`
- `0x18001e9a4`
- `0x18001fa3c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eb57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eb57`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001ead6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001ead6`

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
          v7 = (const char *)&byte_18003925D;
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
0x18001e9a4  mov     [rsp+arg_18], rbx
0x18001e9a9  push    rbp
0x18001e9aa  push    rsi
0x18001e9ab  push    rdi
0x18001e9ac  push    r14
0x18001e9ae  push    r15
0x18001e9b0  sub     rsp, 250h
0x18001e9b7  mov     rax, cs:__security_cookie
0x18001e9be  xor     rax, rsp
0x18001e9c1  mov     [rsp+278h+var_38], rax
0x18001e9c9  mov     rbx, r8
0x18001e9cc  mov     rsi, rdx
0x18001e9cf  mov     r14, rcx
0x18001e9d2  xor     r15d, r15d
0x18001e9d5  test    rdx, rdx
0x18001e9d8  jz      loc_18001EC31
0x18001e9de  test    rcx, rcx
0x18001e9e1  jz      loc_18001EC31
0x18001e9e7  mov     [rcx], r15w
0x18001e9eb  mov     rax, cs:g_pfnResultLoggingCallback
0x18001e9f2  test    rax, rax
0x18001e9f5  jz      short loc_18001EA18
0x18001e9f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001e9fe  jz      short loc_18001EA18
0x18001ea00  mov     r8, rdx
0x18001ea03  mov     rdx, rcx
0x18001ea06  mov     rcx, rbx
0x18001ea09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea0e  cmp     [r14], r15w
0x18001ea12  jnz     loc_18001EC31
0x18001ea18  mov     ecx, [rbx]
0x18001ea1a  mov     bpl, 8
0x18001ea1d  test    ecx, ecx
0x18001ea1f  jz      short loc_18001EA6A
0x18001ea21  sub     ecx, 1
0x18001ea24  jz      short loc_18001EA52
0x18001ea26  sub     ecx, 1
0x18001ea29  jz      short loc_18001EA42
0x18001ea2b  cmp     ecx, 1
0x18001ea2e  jz      short loc_18001EA39
0x18001ea30  lea     rdi, byte_18003925D
0x18001ea37  jmp     short loc_18001EA71
0x18001ea39  lea     rdi, aFailfast; "FailFast"
0x18001ea40  jmp     short loc_18001EA71
0x18001ea42  lea     rax, aLoghr; "LogHr"
0x18001ea49  lea     rdi, aLognt; "LogNt"
0x18001ea50  jmp     short loc_18001EA60
0x18001ea52  lea     rax, aReturnhr; "ReturnHr"
0x18001ea59  lea     rdi, aReturnnt; "ReturnNt"
0x18001ea60  test    [rbx+4], bpl
0x18001ea64  cmovz   rdi, rax
0x18001ea68  jmp     short loc_18001EA71
0x18001ea6a  lea     rdi, aException; "Exception"
0x18001ea71  xor     edx, edx; Val
0x18001ea73  mov     r8d, 200h; Size
0x18001ea79  lea     rcx, [rsp+278h+Buffer]; void *
0x18001ea7e  call    memset_0
0x18001ea83  test    [rbx+4], bpl
0x18001ea87  jz      short loc_18001EAAC
0x18001ea89  mov     ebp, [rbx+0Ch]
0x18001ea8c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001ea93  test    rax, rax
0x18001ea96  jz      short loc_18001EADC
0x18001ea98  mov     r8d, 100h
0x18001ea9e  lea     rdx, [rsp+278h+Buffer]
0x18001eaa3  mov     ecx, ebp
0x18001eaa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaaa  jmp     short loc_18001EADC
0x18001eaac  mov     ebp, [rbx+8]
0x18001eaaf  mov     [rsp+278h+Arguments], r15; Arguments
0x18001eab4  mov     [rsp+278h+nSize], 100h; nSize
0x18001eabc  lea     rax, [rsp+278h+Buffer]
0x18001eac1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001eac6  mov     r9d, 400h; dwLanguageId
0x18001eacc  mov     r8d, ebp; dwMessageId
0x18001eacf  xor     edx, edx; lpSource
0x18001ead1  mov     ecx, 1200h; dwFlags
0x18001ead6  call    cs:__imp_FormatMessageW
0x18001eadc  lea     rsi, [r14+rsi*2]
0x18001eae0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001eae4  mov     rax, [rbx+88h]
0x18001eaeb  mov     rcx, [rbx+80h]
0x18001eaf2  mov     rdx, rsi; unsigned __int16 *
0x18001eaf5  test    r9, r9
0x18001eaf8  jz      short loc_18001EB1C
0x18001eafa  mov     [rsp+278h+Arguments], rax
0x18001eaff  mov     qword ptr [rsp+278h+nSize], rcx
0x18001eb04  mov     eax, [rbx+40h]
0x18001eb07  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001eb0b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001eb12  mov     rcx, r14; this
0x18001eb15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001eb1a  jmp     short loc_18001EB33
0x18001eb1c  mov     [rsp+278h+lpBuffer], rax
0x18001eb21  mov     r9, rcx; unsigned __int16 *
0x18001eb24  lea     r8, aHsP; "%hs!%p: "
0x18001eb2b  mov     rcx, r14; this
0x18001eb2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001eb33  mov     r14, rax
0x18001eb36  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001eb3d  test    r9, r9
0x18001eb40  jz      short loc_18001EB57
0x18001eb42  lea     r8, aCallerP; "(caller: %p) "
0x18001eb49  mov     rdx, rsi; unsigned __int16 *
0x18001eb4c  mov     rcx, rax; this
0x18001eb4f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001eb54  mov     r14, rax
0x18001eb57  call    cs:__imp_GetCurrentThreadId
0x18001eb5d  lea     rcx, [rsp+278h+Buffer]
0x18001eb62  mov     [rsp+278h+var_240], rcx
0x18001eb67  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001eb6b  mov     [rsp+278h+nSize], eax
0x18001eb6f  mov     eax, [rbx+44h]
0x18001eb72  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001eb76  mov     r9, rdi; unsigned __int16 *
0x18001eb79  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001eb80  mov     rdx, rsi; unsigned __int16 *
0x18001eb83  mov     rcx, r14; this
0x18001eb86  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001eb8b  cmp     [rbx+18h], r15
0x18001eb8f  jnz     short loc_18001EBA1
0x18001eb91  cmp     [rbx+48h], r15
0x18001eb95  jnz     short loc_18001EBA1
0x18001eb97  cmp     [rbx+30h], r15
0x18001eb9b  jz      loc_18001EC31
0x18001eba1  lea     r8, asc_180039370; "    "
0x18001eba8  mov     rdx, rsi; unsigned __int16 *
0x18001ebab  mov     rcx, rax; this
0x18001ebae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ebb3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001ebb7  test    r9, r9
0x18001ebba  jz      short loc_18001EBCE
0x18001ebbc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001ebc3  mov     rdx, rsi; unsigned __int16 *
0x18001ebc6  mov     rcx, rax; this
0x18001ebc9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ebce  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001ebd2  test    r9, r9
0x18001ebd5  jz      short loc_18001EBE9
0x18001ebd7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001ebde  mov     rdx, rsi; unsigned __int16 *
0x18001ebe1  mov     rcx, rax; this
0x18001ebe4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ebe9  mov     rcx, [rbx+28h]
0x18001ebed  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001ebf1  mov     rdx, rsi; unsigned __int16 *
0x18001ebf4  test    rcx, rcx
0x18001ebf7  jz      short loc_18001EC0F
0x18001ebf9  mov     [rsp+278h+lpBuffer], rcx
0x18001ebfe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001ec05  mov     rcx, rax; this
0x18001ec08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ec0d  jmp     short loc_18001EC31
0x18001ec0f  mov     rcx, rax; this
0x18001ec12  test    r9, r9
0x18001ec15  jz      short loc_18001EC25
0x18001ec17  lea     r8, aHs; "[%hs]\n"
0x18001ec1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ec23  jmp     short loc_18001EC31
0x18001ec25  lea     r8, asc_1800393E8; "\n"
0x18001ec2c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001ec31  xor     eax, eax
0x18001ec33  mov     rcx, [rsp+278h+var_38]
0x18001ec3b  xor     rcx, rsp; StackCookie
0x18001ec3e  call    __security_check_cookie
0x18001ec43  mov     rbx, [rsp+278h+arg_18]
0x18001ec4b  add     rsp, 250h
0x18001ec52  pop     r15
0x18001ec54  pop     r14
0x18001ec56  pop     rdi
0x18001ec57  pop     rsi
0x18001ec58  pop     rbp
0x18001ec59  retn
```
