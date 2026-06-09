# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18005bbb4`
- end: `0x18005be6a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18005472c`
- `0x18005c8ec`
- `0x18005ec00`

## callees

- `0x180058b30`
- `0x1800595ac`
- `0x18005bbb4`
- `0x18005c5f0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bd67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bd67`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18005bce6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18005bce6`

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
          v7 = (const char *)&byte_1800BF57D;
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
0x18005bbb4  mov     [rsp+arg_18], rbx
0x18005bbb9  push    rbp
0x18005bbba  push    rsi
0x18005bbbb  push    rdi
0x18005bbbc  push    r14
0x18005bbbe  push    r15
0x18005bbc0  sub     rsp, 250h
0x18005bbc7  mov     rax, cs:__security_cookie
0x18005bbce  xor     rax, rsp
0x18005bbd1  mov     [rsp+278h+var_38], rax
0x18005bbd9  mov     rbx, r8
0x18005bbdc  mov     rsi, rdx
0x18005bbdf  mov     r14, rcx
0x18005bbe2  xor     r15d, r15d
0x18005bbe5  test    rdx, rdx
0x18005bbe8  jz      loc_18005BE41
0x18005bbee  test    rcx, rcx
0x18005bbf1  jz      loc_18005BE41
0x18005bbf7  mov     [rcx], r15w
0x18005bbfb  mov     rax, cs:g_pfnResultLoggingCallback
0x18005bc02  test    rax, rax
0x18005bc05  jz      short loc_18005BC28
0x18005bc07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005bc0e  jz      short loc_18005BC28
0x18005bc10  mov     r8, rdx
0x18005bc13  mov     rdx, rcx
0x18005bc16  mov     rcx, rbx
0x18005bc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc1e  cmp     [r14], r15w
0x18005bc22  jnz     loc_18005BE41
0x18005bc28  mov     ecx, [rbx]
0x18005bc2a  mov     bpl, 8
0x18005bc2d  test    ecx, ecx
0x18005bc2f  jz      short loc_18005BC7A
0x18005bc31  sub     ecx, 1
0x18005bc34  jz      short loc_18005BC62
0x18005bc36  sub     ecx, 1
0x18005bc39  jz      short loc_18005BC52
0x18005bc3b  cmp     ecx, 1
0x18005bc3e  jz      short loc_18005BC49
0x18005bc40  lea     rdi, byte_1800BF57D
0x18005bc47  jmp     short loc_18005BC81
0x18005bc49  lea     rdi, aFailfast; "FailFast"
0x18005bc50  jmp     short loc_18005BC81
0x18005bc52  lea     rax, aLoghr; "LogHr"
0x18005bc59  lea     rdi, aLognt; "LogNt"
0x18005bc60  jmp     short loc_18005BC70
0x18005bc62  lea     rax, aReturnhr; "ReturnHr"
0x18005bc69  lea     rdi, aReturnnt; "ReturnNt"
0x18005bc70  test    [rbx+4], bpl
0x18005bc74  cmovz   rdi, rax
0x18005bc78  jmp     short loc_18005BC81
0x18005bc7a  lea     rdi, aException; "Exception"
0x18005bc81  xor     edx, edx; Val
0x18005bc83  mov     r8d, 200h; Size
0x18005bc89  lea     rcx, [rsp+278h+Buffer]; void *
0x18005bc8e  call    memset_0
0x18005bc93  test    [rbx+4], bpl
0x18005bc97  jz      short loc_18005BCBC
0x18005bc99  mov     ebp, [rbx+0Ch]
0x18005bc9c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18005bca3  test    rax, rax
0x18005bca6  jz      short loc_18005BCEC
0x18005bca8  mov     r8d, 100h
0x18005bcae  lea     rdx, [rsp+278h+Buffer]
0x18005bcb3  mov     ecx, ebp
0x18005bcb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcba  jmp     short loc_18005BCEC
0x18005bcbc  mov     ebp, [rbx+8]
0x18005bcbf  mov     [rsp+278h+Arguments], r15; Arguments
0x18005bcc4  mov     [rsp+278h+nSize], 100h; nSize
0x18005bccc  lea     rax, [rsp+278h+Buffer]
0x18005bcd1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18005bcd6  mov     r9d, 400h; dwLanguageId
0x18005bcdc  mov     r8d, ebp; dwMessageId
0x18005bcdf  xor     edx, edx; lpSource
0x18005bce1  mov     ecx, 1200h; dwFlags
0x18005bce6  call    cs:__imp_FormatMessageW
0x18005bcec  lea     rsi, [r14+rsi*2]
0x18005bcf0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18005bcf4  mov     rax, [rbx+88h]
0x18005bcfb  mov     rcx, [rbx+80h]
0x18005bd02  mov     rdx, rsi; unsigned __int16 *
0x18005bd05  test    r9, r9
0x18005bd08  jz      short loc_18005BD2C
0x18005bd0a  mov     [rsp+278h+Arguments], rax
0x18005bd0f  mov     qword ptr [rsp+278h+nSize], rcx
0x18005bd14  mov     eax, [rbx+40h]
0x18005bd17  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18005bd1b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18005bd22  mov     rcx, r14; this
0x18005bd25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bd2a  jmp     short loc_18005BD43
0x18005bd2c  mov     [rsp+278h+lpBuffer], rax
0x18005bd31  mov     r9, rcx; unsigned __int16 *
0x18005bd34  lea     r8, aHsP; "%hs!%p: "
0x18005bd3b  mov     rcx, r14; this
0x18005bd3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bd43  mov     r14, rax
0x18005bd46  mov     r9, [rbx+90h]; unsigned __int16 *
0x18005bd4d  test    r9, r9
0x18005bd50  jz      short loc_18005BD67
0x18005bd52  lea     r8, aCallerP; "(caller: %p) "
0x18005bd59  mov     rdx, rsi; unsigned __int16 *
0x18005bd5c  mov     rcx, rax; this
0x18005bd5f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bd64  mov     r14, rax
0x18005bd67  call    cs:__imp_GetCurrentThreadId
0x18005bd6d  lea     rcx, [rsp+278h+Buffer]
0x18005bd72  mov     [rsp+278h+var_240], rcx
0x18005bd77  mov     dword ptr [rsp+278h+Arguments], ebp
0x18005bd7b  mov     [rsp+278h+nSize], eax
0x18005bd7f  mov     eax, [rbx+44h]
0x18005bd82  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18005bd86  mov     r9, rdi; unsigned __int16 *
0x18005bd89  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18005bd90  mov     rdx, rsi; unsigned __int16 *
0x18005bd93  mov     rcx, r14; this
0x18005bd96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bd9b  cmp     [rbx+18h], r15
0x18005bd9f  jnz     short loc_18005BDB1
0x18005bda1  cmp     [rbx+48h], r15
0x18005bda5  jnz     short loc_18005BDB1
0x18005bda7  cmp     [rbx+30h], r15
0x18005bdab  jz      loc_18005BE41
0x18005bdb1  lea     r8, asc_1800B3730; "    "
0x18005bdb8  mov     rdx, rsi; unsigned __int16 *
0x18005bdbb  mov     rcx, rax; this
0x18005bdbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bdc3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18005bdc7  test    r9, r9
0x18005bdca  jz      short loc_18005BDDE
0x18005bdcc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18005bdd3  mov     rdx, rsi; unsigned __int16 *
0x18005bdd6  mov     rcx, rax; this
0x18005bdd9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bdde  mov     r9, [rbx+48h]; unsigned __int16 *
0x18005bde2  test    r9, r9
0x18005bde5  jz      short loc_18005BDF9
0x18005bde7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18005bdee  mov     rdx, rsi; unsigned __int16 *
0x18005bdf1  mov     rcx, rax; this
0x18005bdf4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bdf9  mov     rcx, [rbx+28h]
0x18005bdfd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18005be01  mov     rdx, rsi; unsigned __int16 *
0x18005be04  test    rcx, rcx
0x18005be07  jz      short loc_18005BE1F
0x18005be09  mov     [rsp+278h+lpBuffer], rcx
0x18005be0e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18005be15  mov     rcx, rax; this
0x18005be18  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005be1d  jmp     short loc_18005BE41
0x18005be1f  mov     rcx, rax; this
0x18005be22  test    r9, r9
0x18005be25  jz      short loc_18005BE35
0x18005be27  lea     r8, aHs; "[%hs]\n"
0x18005be2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005be33  jmp     short loc_18005BE41
0x18005be35  lea     r8, asc_1800B2D8C; "\n"
0x18005be3c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005be41  xor     eax, eax
0x18005be43  mov     rcx, [rsp+278h+var_38]
0x18005be4b  xor     rcx, rsp; StackCookie
0x18005be4e  call    __security_check_cookie
0x18005be53  mov     rbx, [rsp+278h+arg_18]
0x18005be5b  add     rsp, 250h
0x18005be62  pop     r15
0x18005be64  pop     r14
0x18005be66  pop     rdi
0x18005be67  pop     rsi
0x18005be68  pop     rbp
0x18005be69  retn
```
