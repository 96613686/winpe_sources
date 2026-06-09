# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000bc24`
- end: `0x18000beda`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180009c4c`
- `0x18000c948`
- `0x18000d028`
- `0x18000fea0`

## callees

- `0x180003c80`
- `0x180004814`
- `0x18000bc24`
- `0x18000cc48`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bdd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bdd7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bd56`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bd56`

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
          v7 = (const char *)&dword_18004DF54;
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
0x18000bc24  mov     [rsp+arg_18], rbx
0x18000bc29  push    rbp
0x18000bc2a  push    rsi
0x18000bc2b  push    rdi
0x18000bc2c  push    r14
0x18000bc2e  push    r15
0x18000bc30  sub     rsp, 250h
0x18000bc37  mov     rax, cs:__security_cookie
0x18000bc3e  xor     rax, rsp
0x18000bc41  mov     [rsp+278h+var_38], rax
0x18000bc49  mov     rbx, r8
0x18000bc4c  mov     rsi, rdx
0x18000bc4f  mov     r14, rcx
0x18000bc52  xor     r15d, r15d
0x18000bc55  test    rdx, rdx
0x18000bc58  jz      loc_18000BEB1
0x18000bc5e  test    rcx, rcx
0x18000bc61  jz      loc_18000BEB1
0x18000bc67  mov     [rcx], r15w
0x18000bc6b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bc72  test    rax, rax
0x18000bc75  jz      short loc_18000BC98
0x18000bc77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000bc7e  jz      short loc_18000BC98
0x18000bc80  mov     r8, rdx
0x18000bc83  mov     rdx, rcx
0x18000bc86  mov     rcx, rbx
0x18000bc89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc8e  cmp     [r14], r15w
0x18000bc92  jnz     loc_18000BEB1
0x18000bc98  mov     ecx, [rbx]
0x18000bc9a  mov     bpl, 8
0x18000bc9d  test    ecx, ecx
0x18000bc9f  jz      short loc_18000BCEA
0x18000bca1  sub     ecx, 1
0x18000bca4  jz      short loc_18000BCD2
0x18000bca6  sub     ecx, 1
0x18000bca9  jz      short loc_18000BCC2
0x18000bcab  cmp     ecx, 1
0x18000bcae  jz      short loc_18000BCB9
0x18000bcb0  lea     rdi, dword_18004DF54
0x18000bcb7  jmp     short loc_18000BCF1
0x18000bcb9  lea     rdi, aFailfast; "FailFast"
0x18000bcc0  jmp     short loc_18000BCF1
0x18000bcc2  lea     rax, aLoghr; "LogHr"
0x18000bcc9  lea     rdi, aLognt; "LogNt"
0x18000bcd0  jmp     short loc_18000BCE0
0x18000bcd2  lea     rax, aReturnhr; "ReturnHr"
0x18000bcd9  lea     rdi, aReturnnt; "ReturnNt"
0x18000bce0  test    [rbx+4], bpl
0x18000bce4  cmovz   rdi, rax
0x18000bce8  jmp     short loc_18000BCF1
0x18000bcea  lea     rdi, aException; "Exception"
0x18000bcf1  xor     edx, edx; Val
0x18000bcf3  mov     r8d, 200h; Size
0x18000bcf9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000bcfe  call    memset_0
0x18000bd03  test    [rbx+4], bpl
0x18000bd07  jz      short loc_18000BD2C
0x18000bd09  mov     ebp, [rbx+0Ch]
0x18000bd0c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000bd13  test    rax, rax
0x18000bd16  jz      short loc_18000BD5C
0x18000bd18  mov     r8d, 100h
0x18000bd1e  lea     rdx, [rsp+278h+Buffer]
0x18000bd23  mov     ecx, ebp
0x18000bd25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd2a  jmp     short loc_18000BD5C
0x18000bd2c  mov     ebp, [rbx+8]
0x18000bd2f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000bd34  mov     [rsp+278h+nSize], 100h; nSize
0x18000bd3c  lea     rax, [rsp+278h+Buffer]
0x18000bd41  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000bd46  mov     r9d, 400h; dwLanguageId
0x18000bd4c  mov     r8d, ebp; dwMessageId
0x18000bd4f  xor     edx, edx; lpSource
0x18000bd51  mov     ecx, 1200h; dwFlags
0x18000bd56  call    cs:__imp_FormatMessageW
0x18000bd5c  lea     rsi, [r14+rsi*2]
0x18000bd60  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000bd64  mov     rax, [rbx+88h]
0x18000bd6b  mov     rcx, [rbx+80h]
0x18000bd72  mov     rdx, rsi; unsigned __int16 *
0x18000bd75  test    r9, r9
0x18000bd78  jz      short loc_18000BD9C
0x18000bd7a  mov     [rsp+278h+Arguments], rax
0x18000bd7f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000bd84  mov     eax, [rbx+40h]
0x18000bd87  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000bd8b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000bd92  mov     rcx, r14; this
0x18000bd95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bd9a  jmp     short loc_18000BDB3
0x18000bd9c  mov     [rsp+278h+lpBuffer], rax
0x18000bda1  mov     r9, rcx; unsigned __int16 *
0x18000bda4  lea     r8, aHsP; "%hs!%p: "
0x18000bdab  mov     rcx, r14; this
0x18000bdae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bdb3  mov     r14, rax
0x18000bdb6  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000bdbd  test    r9, r9
0x18000bdc0  jz      short loc_18000BDD7
0x18000bdc2  lea     r8, aCallerP; "(caller: %p) "
0x18000bdc9  mov     rdx, rsi; unsigned __int16 *
0x18000bdcc  mov     rcx, rax; this
0x18000bdcf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bdd4  mov     r14, rax
0x18000bdd7  call    cs:__imp_GetCurrentThreadId
0x18000bddd  lea     rcx, [rsp+278h+Buffer]
0x18000bde2  mov     [rsp+278h+var_240], rcx
0x18000bde7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000bdeb  mov     [rsp+278h+nSize], eax
0x18000bdef  mov     eax, [rbx+44h]
0x18000bdf2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000bdf6  mov     r9, rdi; unsigned __int16 *
0x18000bdf9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000be00  mov     rdx, rsi; unsigned __int16 *
0x18000be03  mov     rcx, r14; this
0x18000be06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000be0b  cmp     [rbx+18h], r15
0x18000be0f  jnz     short loc_18000BE21
0x18000be11  cmp     [rbx+48h], r15
0x18000be15  jnz     short loc_18000BE21
0x18000be17  cmp     [rbx+30h], r15
0x18000be1b  jz      loc_18000BEB1
0x18000be21  lea     r8, asc_18004E070; "    "
0x18000be28  mov     rdx, rsi; unsigned __int16 *
0x18000be2b  mov     rcx, rax; this
0x18000be2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000be33  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000be37  test    r9, r9
0x18000be3a  jz      short loc_18000BE4E
0x18000be3c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000be43  mov     rdx, rsi; unsigned __int16 *
0x18000be46  mov     rcx, rax; this
0x18000be49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000be4e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000be52  test    r9, r9
0x18000be55  jz      short loc_18000BE69
0x18000be57  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000be5e  mov     rdx, rsi; unsigned __int16 *
0x18000be61  mov     rcx, rax; this
0x18000be64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000be69  mov     rcx, [rbx+28h]
0x18000be6d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000be71  mov     rdx, rsi; unsigned __int16 *
0x18000be74  test    rcx, rcx
0x18000be77  jz      short loc_18000BE8F
0x18000be79  mov     [rsp+278h+lpBuffer], rcx
0x18000be7e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000be85  mov     rcx, rax; this
0x18000be88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000be8d  jmp     short loc_18000BEB1
0x18000be8f  mov     rcx, rax; this
0x18000be92  test    r9, r9
0x18000be95  jz      short loc_18000BEA5
0x18000be97  lea     r8, aHs; "[%hs]\n"
0x18000be9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bea3  jmp     short loc_18000BEB1
0x18000bea5  lea     r8, asc_18004E0E8; "\n"
0x18000beac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000beb1  xor     eax, eax
0x18000beb3  mov     rcx, [rsp+278h+var_38]
0x18000bebb  xor     rcx, rsp; StackCookie
0x18000bebe  call    __security_check_cookie
0x18000bec3  mov     rbx, [rsp+278h+arg_18]
0x18000becb  add     rsp, 250h
0x18000bed2  pop     r15
0x18000bed4  pop     r14
0x18000bed6  pop     rdi
0x18000bed7  pop     rsi
0x18000bed8  pop     rbp
0x18000bed9  retn
```
