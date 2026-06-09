# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000f984`
- end: `0x18000fc3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e408`
- `0x18000e688`
- `0x1800102f0`
- `0x180011bf0`
- `0x1800166e4`
- `0x18004c2ae`
- `0x18004c3e2`
- `0x18004c669`
- `0x18004caaf`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x18000f984`
- `0x1800105f0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000fab6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000fab6`

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
          v7 = (const char *)&byte_1800532A7;
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
0x18000f984  mov     [rsp+arg_18], rbx
0x18000f989  push    rbp
0x18000f98a  push    rsi
0x18000f98b  push    rdi
0x18000f98c  push    r14
0x18000f98e  push    r15
0x18000f990  sub     rsp, 250h
0x18000f997  mov     rax, cs:__security_cookie
0x18000f99e  xor     rax, rsp
0x18000f9a1  mov     [rsp+278h+var_38], rax
0x18000f9a9  mov     rbx, r8
0x18000f9ac  mov     rsi, rdx
0x18000f9af  mov     r14, rcx
0x18000f9b2  xor     r15d, r15d
0x18000f9b5  test    rdx, rdx
0x18000f9b8  jz      loc_18000FC11
0x18000f9be  test    rcx, rcx
0x18000f9c1  jz      loc_18000FC11
0x18000f9c7  mov     [rcx], r15w
0x18000f9cb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f9d2  test    rax, rax
0x18000f9d5  jz      short loc_18000F9F8
0x18000f9d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000f9de  jz      short loc_18000F9F8
0x18000f9e0  mov     r8, rdx
0x18000f9e3  mov     rdx, rcx
0x18000f9e6  mov     rcx, rbx
0x18000f9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9ee  cmp     [r14], r15w
0x18000f9f2  jnz     loc_18000FC11
0x18000f9f8  mov     ecx, [rbx]
0x18000f9fa  mov     bpl, 8
0x18000f9fd  test    ecx, ecx
0x18000f9ff  jz      short loc_18000FA4A
0x18000fa01  sub     ecx, 1
0x18000fa04  jz      short loc_18000FA32
0x18000fa06  sub     ecx, 1
0x18000fa09  jz      short loc_18000FA22
0x18000fa0b  cmp     ecx, 1
0x18000fa0e  jz      short loc_18000FA19
0x18000fa10  lea     rdi, byte_1800532A7
0x18000fa17  jmp     short loc_18000FA51
0x18000fa19  lea     rdi, aFailfast; "FailFast"
0x18000fa20  jmp     short loc_18000FA51
0x18000fa22  lea     rax, aLoghr; "LogHr"
0x18000fa29  lea     rdi, aLognt; "LogNt"
0x18000fa30  jmp     short loc_18000FA40
0x18000fa32  lea     rax, aReturnhr; "ReturnHr"
0x18000fa39  lea     rdi, aReturnnt; "ReturnNt"
0x18000fa40  test    [rbx+4], bpl
0x18000fa44  cmovz   rdi, rax
0x18000fa48  jmp     short loc_18000FA51
0x18000fa4a  lea     rdi, aException; "Exception"
0x18000fa51  xor     edx, edx; Val
0x18000fa53  mov     r8d, 200h; Size
0x18000fa59  lea     rcx, [rsp+278h+Buffer]; void *
0x18000fa5e  call    memset_0
0x18000fa63  test    [rbx+4], bpl
0x18000fa67  jz      short loc_18000FA8C
0x18000fa69  mov     ebp, [rbx+0Ch]
0x18000fa6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000fa73  test    rax, rax
0x18000fa76  jz      short loc_18000FABC
0x18000fa78  mov     r8d, 100h
0x18000fa7e  lea     rdx, [rsp+278h+Buffer]
0x18000fa83  mov     ecx, ebp
0x18000fa85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa8a  jmp     short loc_18000FABC
0x18000fa8c  mov     ebp, [rbx+8]
0x18000fa8f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000fa94  mov     [rsp+278h+nSize], 100h; nSize
0x18000fa9c  lea     rax, [rsp+278h+Buffer]
0x18000faa1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000faa6  mov     r9d, 400h; dwLanguageId
0x18000faac  mov     r8d, ebp; dwMessageId
0x18000faaf  xor     edx, edx; lpSource
0x18000fab1  mov     ecx, 1200h; dwFlags
0x18000fab6  call    cs:__imp_FormatMessageW
0x18000fabc  lea     rsi, [r14+rsi*2]
0x18000fac0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000fac4  mov     rax, [rbx+88h]
0x18000facb  mov     rcx, [rbx+80h]
0x18000fad2  mov     rdx, rsi; unsigned __int16 *
0x18000fad5  test    r9, r9
0x18000fad8  jz      short loc_18000FAFC
0x18000fada  mov     [rsp+278h+Arguments], rax
0x18000fadf  mov     qword ptr [rsp+278h+nSize], rcx
0x18000fae4  mov     eax, [rbx+40h]
0x18000fae7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000faeb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000faf2  mov     rcx, r14; this
0x18000faf5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fafa  jmp     short loc_18000FB13
0x18000fafc  mov     [rsp+278h+lpBuffer], rax
0x18000fb01  mov     r9, rcx; unsigned __int16 *
0x18000fb04  lea     r8, aHsP; "%hs!%p: "
0x18000fb0b  mov     rcx, r14; this
0x18000fb0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fb13  mov     r14, rax
0x18000fb16  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000fb1d  test    r9, r9
0x18000fb20  jz      short loc_18000FB37
0x18000fb22  lea     r8, aCallerP; "(caller: %p) "
0x18000fb29  mov     rdx, rsi; unsigned __int16 *
0x18000fb2c  mov     rcx, rax; this
0x18000fb2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fb34  mov     r14, rax
0x18000fb37  call    cs:__imp_GetCurrentThreadId
0x18000fb3d  lea     rcx, [rsp+278h+Buffer]
0x18000fb42  mov     [rsp+278h+var_240], rcx
0x18000fb47  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000fb4b  mov     [rsp+278h+nSize], eax
0x18000fb4f  mov     eax, [rbx+44h]
0x18000fb52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000fb56  mov     r9, rdi; unsigned __int16 *
0x18000fb59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000fb60  mov     rdx, rsi; unsigned __int16 *
0x18000fb63  mov     rcx, r14; this
0x18000fb66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fb6b  cmp     [rbx+18h], r15
0x18000fb6f  jnz     short loc_18000FB81
0x18000fb71  cmp     [rbx+48h], r15
0x18000fb75  jnz     short loc_18000FB81
0x18000fb77  cmp     [rbx+30h], r15
0x18000fb7b  jz      loc_18000FC11
0x18000fb81  lea     r8, asc_1800533A8; "    "
0x18000fb88  mov     rdx, rsi; unsigned __int16 *
0x18000fb8b  mov     rcx, rax; this
0x18000fb8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fb93  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000fb97  test    r9, r9
0x18000fb9a  jz      short loc_18000FBAE
0x18000fb9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000fba3  mov     rdx, rsi; unsigned __int16 *
0x18000fba6  mov     rcx, rax; this
0x18000fba9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fbae  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000fbb2  test    r9, r9
0x18000fbb5  jz      short loc_18000FBC9
0x18000fbb7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000fbbe  mov     rdx, rsi; unsigned __int16 *
0x18000fbc1  mov     rcx, rax; this
0x18000fbc4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fbc9  mov     rcx, [rbx+28h]
0x18000fbcd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000fbd1  mov     rdx, rsi; unsigned __int16 *
0x18000fbd4  test    rcx, rcx
0x18000fbd7  jz      short loc_18000FBEF
0x18000fbd9  mov     [rsp+278h+lpBuffer], rcx
0x18000fbde  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000fbe5  mov     rcx, rax; this
0x18000fbe8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fbed  jmp     short loc_18000FC11
0x18000fbef  mov     rcx, rax; this
0x18000fbf2  test    r9, r9
0x18000fbf5  jz      short loc_18000FC05
0x18000fbf7  lea     r8, aHs; "[%hs]\n"
0x18000fbfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fc03  jmp     short loc_18000FC11
0x18000fc05  lea     r8, asc_180053420; "\n"
0x18000fc0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fc11  xor     eax, eax
0x18000fc13  mov     rcx, [rsp+278h+var_38]
0x18000fc1b  xor     rcx, rsp; StackCookie
0x18000fc1e  call    __security_check_cookie
0x18000fc23  mov     rbx, [rsp+278h+arg_18]
0x18000fc2b  add     rsp, 250h
0x18000fc32  pop     r15
0x18000fc34  pop     r14
0x18000fc36  pop     rdi
0x18000fc37  pop     rsi
0x18000fc38  pop     rbp
0x18000fc39  retn
```
