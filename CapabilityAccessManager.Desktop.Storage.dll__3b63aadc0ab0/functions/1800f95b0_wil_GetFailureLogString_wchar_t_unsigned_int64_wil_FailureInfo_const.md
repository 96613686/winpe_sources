# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800f95b0`
- end: `0x1800f9860`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `688`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800f7a10`
- `0x1800f7d7c`
- `0x1800f8024`

## callees

- `0x180003060`
- `0x180003a40`
- `0x1800e8bc0`
- `0x1800f95b0`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f975d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f975d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800f96d9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800f96d9`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  void (__fastcall *v6)(__int64, wil *, __int64, const struct wil::FailureInfo *); // rax
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  const unsigned __int16 *v10; // r9
  unsigned __int16 *v11; // rsi
  __int64 v12; // rax
  unsigned __int16 *v13; // rdx
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

  if ( !this )
    return 0;
  v6 = (void (__fastcall *)(__int64, wil *, __int64, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v6 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v6(a3, this, 2048, a4);
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
          v7 = byte_180122168;
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
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
  v10 = *(const unsigned __int16 **)(a3 + 56);
  v11 = (unsigned __int16 *)((char *)this + 4096);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = (unsigned __int16 *)((char *)this + 4096);
  if ( v10 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v13, L"%hs(%u)\\%hs!%p: ", v10, lpBuffer, *(_QWORD *)(a3 + 128), v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v13, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v12);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v11, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v11,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v11, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v11, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v11, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v11, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v11, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v11, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800f95b0  mov     [rsp+arg_8], rbx
0x1800f95b5  push    rbp
0x1800f95b6  push    rsi
0x1800f95b7  push    rdi
0x1800f95b8  push    r14
0x1800f95ba  push    r15
0x1800f95bc  sub     rsp, 250h
0x1800f95c3  mov     rax, cs:__security_cookie
0x1800f95ca  xor     rax, rsp
0x1800f95cd  mov     [rsp+278h+var_38], rax
0x1800f95d5  xor     r15d, r15d
0x1800f95d8  mov     rbx, r8
0x1800f95db  mov     r14, rcx
0x1800f95de  test    rcx, rcx
0x1800f95e1  jz      loc_1800F9837
0x1800f95e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f95ee  mov     [rcx], r15w
0x1800f95f2  test    rax, rax
0x1800f95f5  jz      short loc_1800F961B
0x1800f95f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800f95fe  jz      short loc_1800F961B
0x1800f9600  mov     rdx, rcx
0x1800f9603  mov     r8d, 800h
0x1800f9609  mov     rcx, rbx
0x1800f960c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9611  cmp     [r14], r15w
0x1800f9615  jnz     loc_1800F9837
0x1800f961b  mov     ecx, [rbx]
0x1800f961d  mov     sil, 8
0x1800f9620  test    ecx, ecx
0x1800f9622  jz      short loc_1800F966D
0x1800f9624  sub     ecx, 1
0x1800f9627  jz      short loc_1800F9655
0x1800f9629  sub     ecx, 1
0x1800f962c  jz      short loc_1800F9645
0x1800f962e  cmp     ecx, 1
0x1800f9631  jz      short loc_1800F963C
0x1800f9633  lea     rdi, byte_180122168
0x1800f963a  jmp     short loc_1800F9674
0x1800f963c  lea     rdi, aFailfast; "FailFast"
0x1800f9643  jmp     short loc_1800F9674
0x1800f9645  lea     rax, aLoghr; "LogHr"
0x1800f964c  lea     rdi, aLognt; "LogNt"
0x1800f9653  jmp     short loc_1800F9663
0x1800f9655  lea     rax, aReturnhr; "ReturnHr"
0x1800f965c  lea     rdi, aReturnnt; "ReturnNt"
0x1800f9663  test    [rbx+4], sil
0x1800f9667  cmovz   rdi, rax
0x1800f966b  jmp     short loc_1800F9674
0x1800f966d  lea     rdi, aException; "Exception"
0x1800f9674  xor     edx, edx; Val
0x1800f9676  lea     rcx, [rsp+278h+Buffer]; void *
0x1800f967b  mov     r8d, 200h; Size
0x1800f9681  call    memset_0
0x1800f9686  test    [rbx+4], sil
0x1800f968a  jz      short loc_1800F96AF
0x1800f968c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800f9693  mov     ebp, [rbx+0Ch]
0x1800f9696  test    rax, rax
0x1800f9699  jz      short loc_1800F96DF
0x1800f969b  mov     r8d, 100h
0x1800f96a1  lea     rdx, [rsp+278h+Buffer]
0x1800f96a6  mov     ecx, ebp
0x1800f96a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f96ad  jmp     short loc_1800F96DF
0x1800f96af  mov     ebp, [rbx+8]
0x1800f96b2  lea     rax, [rsp+278h+Buffer]
0x1800f96b7  mov     [rsp+278h+Arguments], r15; Arguments
0x1800f96bc  mov     r8d, ebp; dwMessageId
0x1800f96bf  mov     [rsp+278h+nSize], 100h; nSize
0x1800f96c7  mov     r9d, 400h; dwLanguageId
0x1800f96cd  xor     edx, edx; lpSource
0x1800f96cf  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800f96d4  mov     ecx, 1200h; dwFlags
0x1800f96d9  call    cs:__imp_FormatMessageW
0x1800f96df  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800f96e3  lea     rsi, [r14+1000h]
0x1800f96ea  mov     rax, [rbx+88h]
0x1800f96f1  mov     rdx, rsi; unsigned __int16 *
0x1800f96f4  mov     rcx, [rbx+80h]
0x1800f96fb  test    r9, r9
0x1800f96fe  jz      short loc_1800F9722
0x1800f9700  mov     [rsp+278h+Arguments], rax
0x1800f9705  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800f970c  mov     eax, [rbx+40h]
0x1800f970f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800f9714  mov     rcx, r14; this
0x1800f9717  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800f971b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800f9720  jmp     short loc_1800F9739
0x1800f9722  mov     r9, rcx; unsigned __int16 *
0x1800f9725  mov     [rsp+278h+lpBuffer], rax
0x1800f972a  mov     rcx, r14; this
0x1800f972d  lea     r8, aHsP; "%hs!%p: "
0x1800f9734  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800f9739  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800f9740  mov     r14, rax
0x1800f9743  test    r9, r9
0x1800f9746  jz      short loc_1800F975D
0x1800f9748  lea     r8, aCallerP; "(caller: %p) "
0x1800f974f  mov     rdx, rsi; unsigned __int16 *
0x1800f9752  mov     rcx, rax; this
0x1800f9755  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800f975a  mov     r14, rax
0x1800f975d  call    cs:__imp_GetCurrentThreadId
0x1800f9763  lea     rcx, [rsp+278h+Buffer]
0x1800f9768  mov     r9, rdi; unsigned __int16 *
0x1800f976b  mov     [rsp+278h+var_240], rcx
0x1800f9770  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800f9777  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800f977b  mov     rdx, rsi; unsigned __int16 *
0x1800f977e  mov     [rsp+278h+nSize], eax
0x1800f9782  mov     rcx, r14; this
0x1800f9785  mov     eax, [rbx+44h]
0x1800f9788  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800f978c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800f9791  cmp     [rbx+18h], r15
0x1800f9795  jnz     short loc_1800F97A7
0x1800f9797  cmp     [rbx+48h], r15
0x1800f979b  jnz     short loc_1800F97A7
0x1800f979d  cmp     [rbx+30h], r15
0x1800f97a1  jz      loc_1800F9837
0x1800f97a7  lea     r8, asc_180122270; "    "
0x1800f97ae  mov     rdx, rsi; unsigned __int16 *
0x1800f97b1  mov     rcx, rax; this
0x1800f97b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800f97b9  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800f97bd  test    r9, r9
0x1800f97c0  jz      short loc_1800F97D4
0x1800f97c2  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800f97c9  mov     rdx, rsi; unsigned __int16 *
0x1800f97cc  mov     rcx, rax; this
0x1800f97cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800f97d4  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800f97d8  test    r9, r9
0x1800f97db  jz      short loc_1800F97EF
0x1800f97dd  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800f97e4  mov     rdx, rsi; unsigned __int16 *
0x1800f97e7  mov     rcx, rax; this
0x1800f97ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800f97ef  mov     rcx, [rbx+28h]
0x1800f97f3  mov     rdx, rsi; unsigned __int16 *
0x1800f97f6  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800f97fa  test    rcx, rcx
0x1800f97fd  jz      short loc_1800F9815
0x1800f97ff  mov     [rsp+278h+lpBuffer], rcx
0x1800f9804  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800f980b  mov     rcx, rax; this
0x1800f980e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800f9813  jmp     short loc_1800F9837
0x1800f9815  mov     rcx, rax; this
0x1800f9818  test    r9, r9
0x1800f981b  jz      short loc_1800F982B
0x1800f981d  lea     r8, aHs; "[%hs]\n"
0x1800f9824  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800f9829  jmp     short loc_1800F9837
0x1800f982b  lea     r8, asc_1801222E8; "\n"
0x1800f9832  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800f9837  xor     eax, eax
0x1800f9839  mov     rcx, [rsp+278h+var_38]
0x1800f9841  xor     rcx, rsp; StackCookie
0x1800f9844  call    __security_check_cookie
0x1800f9849  mov     rbx, [rsp+278h+arg_8]
0x1800f9851  add     rsp, 250h
0x1800f9858  pop     r15
0x1800f985a  pop     r14
0x1800f985c  pop     rdi
0x1800f985d  pop     rsi
0x1800f985e  pop     rbp
0x1800f985f  retn
```
