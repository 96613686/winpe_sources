# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001bb28`
- end: `0x18001bdde`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180018640`
- `0x1800188a8`
- `0x18001e53c`
- `0x180031f60`

## callees

- `0x18001bb28`
- `0x18001e83c`
- `0x1800322d2`
- `0x180032310`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bcdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bcdb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001bc5a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001bc5a`

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
          v8 = (const char *)&byte_18003AC50;
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
0x18001bb28  mov     [rsp+arg_18], rbx
0x18001bb2d  push    rbp
0x18001bb2e  push    rsi
0x18001bb2f  push    rdi
0x18001bb30  push    r14
0x18001bb32  push    r15
0x18001bb34  sub     rsp, 250h
0x18001bb3b  mov     rax, cs:__security_cookie
0x18001bb42  xor     rax, rsp
0x18001bb45  mov     [rsp+278h+var_38], rax
0x18001bb4d  xor     r15d, r15d
0x18001bb50  mov     rbx, r8
0x18001bb53  mov     rsi, rdx
0x18001bb56  mov     r14, rcx
0x18001bb59  test    rdx, rdx
0x18001bb5c  jz      loc_18001BDB5
0x18001bb62  test    rcx, rcx
0x18001bb65  jz      loc_18001BDB5
0x18001bb6b  mov     rax, cs:g_pfnResultLoggingCallback
0x18001bb72  mov     [rcx], r15w
0x18001bb76  test    rax, rax
0x18001bb79  jz      short loc_18001BB9C
0x18001bb7b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001bb82  jz      short loc_18001BB9C
0x18001bb84  mov     r8, rdx
0x18001bb87  mov     rdx, rcx
0x18001bb8a  mov     rcx, rbx
0x18001bb8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb92  cmp     [r14], r15w
0x18001bb96  jnz     loc_18001BDB5
0x18001bb9c  mov     ecx, [rbx]
0x18001bb9e  mov     bpl, 8
0x18001bba1  test    ecx, ecx
0x18001bba3  jz      short loc_18001BBEE
0x18001bba5  sub     ecx, 1
0x18001bba8  jz      short loc_18001BBD6
0x18001bbaa  sub     ecx, 1
0x18001bbad  jz      short loc_18001BBC6
0x18001bbaf  cmp     ecx, 1
0x18001bbb2  jz      short loc_18001BBBD
0x18001bbb4  lea     rdi, byte_18003AC50
0x18001bbbb  jmp     short loc_18001BBF5
0x18001bbbd  lea     rdi, aFailfast; "FailFast"
0x18001bbc4  jmp     short loc_18001BBF5
0x18001bbc6  lea     rax, aLoghr; "LogHr"
0x18001bbcd  lea     rdi, aLognt; "LogNt"
0x18001bbd4  jmp     short loc_18001BBE4
0x18001bbd6  lea     rax, aReturnhr; "ReturnHr"
0x18001bbdd  lea     rdi, aReturnnt; "ReturnNt"
0x18001bbe4  test    [rbx+4], bpl
0x18001bbe8  cmovz   rdi, rax
0x18001bbec  jmp     short loc_18001BBF5
0x18001bbee  lea     rdi, aException; "Exception"
0x18001bbf5  xor     edx, edx; Val
0x18001bbf7  lea     rcx, [rsp+278h+Buffer]; void *
0x18001bbfc  mov     r8d, 200h; Size
0x18001bc02  call    memset_0
0x18001bc07  test    [rbx+4], bpl
0x18001bc0b  jz      short loc_18001BC30
0x18001bc0d  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001bc14  mov     ebp, [rbx+0Ch]
0x18001bc17  test    rax, rax
0x18001bc1a  jz      short loc_18001BC60
0x18001bc1c  mov     r8d, 100h
0x18001bc22  lea     rdx, [rsp+278h+Buffer]
0x18001bc27  mov     ecx, ebp
0x18001bc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc2e  jmp     short loc_18001BC60
0x18001bc30  mov     ebp, [rbx+8]
0x18001bc33  lea     rax, [rsp+278h+Buffer]
0x18001bc38  mov     [rsp+278h+Arguments], r15; Arguments
0x18001bc3d  mov     r8d, ebp; dwMessageId
0x18001bc40  mov     [rsp+278h+nSize], 100h; nSize
0x18001bc48  mov     r9d, 400h; dwLanguageId
0x18001bc4e  xor     edx, edx; lpSource
0x18001bc50  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001bc55  mov     ecx, 1200h; dwFlags
0x18001bc5a  call    cs:__imp_FormatMessageW
0x18001bc60  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001bc64  lea     rsi, [r14+rsi*2]
0x18001bc68  mov     rax, [rbx+88h]
0x18001bc6f  mov     rdx, rsi; unsigned __int16 *
0x18001bc72  mov     rcx, [rbx+80h]
0x18001bc79  test    r9, r9
0x18001bc7c  jz      short loc_18001BCA0
0x18001bc7e  mov     [rsp+278h+Arguments], rax
0x18001bc83  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001bc8a  mov     eax, [rbx+40h]
0x18001bc8d  mov     qword ptr [rsp+278h+nSize], rcx
0x18001bc92  mov     rcx, r14; this
0x18001bc95  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001bc99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bc9e  jmp     short loc_18001BCB7
0x18001bca0  mov     r9, rcx; unsigned __int16 *
0x18001bca3  mov     [rsp+278h+lpBuffer], rax
0x18001bca8  mov     rcx, r14; this
0x18001bcab  lea     r8, aHsP; "%hs!%p: "
0x18001bcb2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bcb7  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001bcbe  mov     r14, rax
0x18001bcc1  test    r9, r9
0x18001bcc4  jz      short loc_18001BCDB
0x18001bcc6  lea     r8, aCallerP; "(caller: %p) "
0x18001bccd  mov     rdx, rsi; unsigned __int16 *
0x18001bcd0  mov     rcx, rax; this
0x18001bcd3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bcd8  mov     r14, rax
0x18001bcdb  call    cs:__imp_GetCurrentThreadId
0x18001bce1  lea     rcx, [rsp+278h+Buffer]
0x18001bce6  mov     r9, rdi; unsigned __int16 *
0x18001bce9  mov     [rsp+278h+var_240], rcx
0x18001bcee  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001bcf5  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001bcf9  mov     rdx, rsi; unsigned __int16 *
0x18001bcfc  mov     [rsp+278h+nSize], eax
0x18001bd00  mov     rcx, r14; this
0x18001bd03  mov     eax, [rbx+44h]
0x18001bd06  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001bd0a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bd0f  cmp     [rbx+18h], r15
0x18001bd13  jnz     short loc_18001BD25
0x18001bd15  cmp     [rbx+48h], r15
0x18001bd19  jnz     short loc_18001BD25
0x18001bd1b  cmp     [rbx+30h], r15
0x18001bd1f  jz      loc_18001BDB5
0x18001bd25  lea     r8, asc_180041048; "    "
0x18001bd2c  mov     rdx, rsi; unsigned __int16 *
0x18001bd2f  mov     rcx, rax; this
0x18001bd32  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bd37  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001bd3b  test    r9, r9
0x18001bd3e  jz      short loc_18001BD52
0x18001bd40  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001bd47  mov     rdx, rsi; unsigned __int16 *
0x18001bd4a  mov     rcx, rax; this
0x18001bd4d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bd52  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001bd56  test    r9, r9
0x18001bd59  jz      short loc_18001BD6D
0x18001bd5b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001bd62  mov     rdx, rsi; unsigned __int16 *
0x18001bd65  mov     rcx, rax; this
0x18001bd68  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bd6d  mov     rcx, [rbx+28h]
0x18001bd71  mov     rdx, rsi; unsigned __int16 *
0x18001bd74  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001bd78  test    rcx, rcx
0x18001bd7b  jz      short loc_18001BD93
0x18001bd7d  mov     [rsp+278h+lpBuffer], rcx
0x18001bd82  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001bd89  mov     rcx, rax; this
0x18001bd8c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bd91  jmp     short loc_18001BDB5
0x18001bd93  mov     rcx, rax; this
0x18001bd96  test    r9, r9
0x18001bd99  jz      short loc_18001BDA9
0x18001bd9b  lea     r8, aHs; "[%hs]\n"
0x18001bda2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bda7  jmp     short loc_18001BDB5
0x18001bda9  lea     r8, asc_1800410C0; "\n"
0x18001bdb0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001bdb5  xor     eax, eax
0x18001bdb7  mov     rcx, [rsp+278h+var_38]
0x18001bdbf  xor     rcx, rsp; StackCookie
0x18001bdc2  call    __security_check_cookie
0x18001bdc7  mov     rbx, [rsp+278h+arg_18]
0x18001bdcf  add     rsp, 250h
0x18001bdd6  pop     r15
0x18001bdd8  pop     r14
0x18001bdda  pop     rdi
0x18001bddb  pop     rsi
0x18001bddc  pop     rbp
0x18001bddd  retn
```
