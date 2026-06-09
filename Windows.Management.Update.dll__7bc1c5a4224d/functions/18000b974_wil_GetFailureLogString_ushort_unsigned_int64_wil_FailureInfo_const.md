# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b974`
- end: `0x18000bc2a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180008dd4`
- `0x18000903c`
- `0x18000c488`
- `0x18000fda0`
- `0x1800178f8`

## callees

- `0x1800028f0`
- `0x1800033e8`
- `0x18000b974`
- `0x18000c788`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bb27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bb27`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000baa6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000baa6`

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
          v7 = (const char *)&byte_18002EB91;
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
0x18000b974  mov     [rsp+arg_18], rbx
0x18000b979  push    rbp
0x18000b97a  push    rsi
0x18000b97b  push    rdi
0x18000b97c  push    r14
0x18000b97e  push    r15
0x18000b980  sub     rsp, 250h
0x18000b987  mov     rax, cs:__security_cookie
0x18000b98e  xor     rax, rsp
0x18000b991  mov     [rsp+278h+var_38], rax
0x18000b999  mov     rbx, r8
0x18000b99c  mov     rsi, rdx
0x18000b99f  mov     r14, rcx
0x18000b9a2  xor     r15d, r15d
0x18000b9a5  test    rdx, rdx
0x18000b9a8  jz      loc_18000BC01
0x18000b9ae  test    rcx, rcx
0x18000b9b1  jz      loc_18000BC01
0x18000b9b7  mov     [rcx], r15w
0x18000b9bb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b9c2  test    rax, rax
0x18000b9c5  jz      short loc_18000B9E8
0x18000b9c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b9ce  jz      short loc_18000B9E8
0x18000b9d0  mov     r8, rdx
0x18000b9d3  mov     rdx, rcx
0x18000b9d6  mov     rcx, rbx
0x18000b9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9de  cmp     [r14], r15w
0x18000b9e2  jnz     loc_18000BC01
0x18000b9e8  mov     ecx, [rbx]
0x18000b9ea  mov     bpl, 8
0x18000b9ed  test    ecx, ecx
0x18000b9ef  jz      short loc_18000BA3A
0x18000b9f1  sub     ecx, 1
0x18000b9f4  jz      short loc_18000BA22
0x18000b9f6  sub     ecx, 1
0x18000b9f9  jz      short loc_18000BA12
0x18000b9fb  cmp     ecx, 1
0x18000b9fe  jz      short loc_18000BA09
0x18000ba00  lea     rdi, byte_18002EB91
0x18000ba07  jmp     short loc_18000BA41
0x18000ba09  lea     rdi, aFailfast; "FailFast"
0x18000ba10  jmp     short loc_18000BA41
0x18000ba12  lea     rax, aLoghr; "LogHr"
0x18000ba19  lea     rdi, aLognt; "LogNt"
0x18000ba20  jmp     short loc_18000BA30
0x18000ba22  lea     rax, aReturnhr; "ReturnHr"
0x18000ba29  lea     rdi, aReturnnt; "ReturnNt"
0x18000ba30  test    [rbx+4], bpl
0x18000ba34  cmovz   rdi, rax
0x18000ba38  jmp     short loc_18000BA41
0x18000ba3a  lea     rdi, aException; "Exception"
0x18000ba41  xor     edx, edx; Val
0x18000ba43  mov     r8d, 200h; Size
0x18000ba49  lea     rcx, [rsp+278h+Buffer]; void *
0x18000ba4e  call    memset_0
0x18000ba53  test    [rbx+4], bpl
0x18000ba57  jz      short loc_18000BA7C
0x18000ba59  mov     ebp, [rbx+0Ch]
0x18000ba5c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000ba63  test    rax, rax
0x18000ba66  jz      short loc_18000BAAC
0x18000ba68  mov     r8d, 100h
0x18000ba6e  lea     rdx, [rsp+278h+Buffer]
0x18000ba73  mov     ecx, ebp
0x18000ba75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba7a  jmp     short loc_18000BAAC
0x18000ba7c  mov     ebp, [rbx+8]
0x18000ba7f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000ba84  mov     [rsp+278h+nSize], 100h; nSize
0x18000ba8c  lea     rax, [rsp+278h+Buffer]
0x18000ba91  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000ba96  mov     r9d, 400h; dwLanguageId
0x18000ba9c  mov     r8d, ebp; dwMessageId
0x18000ba9f  xor     edx, edx; lpSource
0x18000baa1  mov     ecx, 1200h; dwFlags
0x18000baa6  call    cs:__imp_FormatMessageW
0x18000baac  lea     rsi, [r14+rsi*2]
0x18000bab0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000bab4  mov     rax, [rbx+88h]
0x18000babb  mov     rcx, [rbx+80h]
0x18000bac2  mov     rdx, rsi; unsigned __int16 *
0x18000bac5  test    r9, r9
0x18000bac8  jz      short loc_18000BAEC
0x18000baca  mov     [rsp+278h+Arguments], rax
0x18000bacf  mov     qword ptr [rsp+278h+nSize], rcx
0x18000bad4  mov     eax, [rbx+40h]
0x18000bad7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000badb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000bae2  mov     rcx, r14; this
0x18000bae5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000baea  jmp     short loc_18000BB03
0x18000baec  mov     [rsp+278h+lpBuffer], rax
0x18000baf1  mov     r9, rcx; unsigned __int16 *
0x18000baf4  lea     r8, aHsP; "%hs!%p: "
0x18000bafb  mov     rcx, r14; this
0x18000bafe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb03  mov     r14, rax
0x18000bb06  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000bb0d  test    r9, r9
0x18000bb10  jz      short loc_18000BB27
0x18000bb12  lea     r8, aCallerP; "(caller: %p) "
0x18000bb19  mov     rdx, rsi; unsigned __int16 *
0x18000bb1c  mov     rcx, rax; this
0x18000bb1f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb24  mov     r14, rax
0x18000bb27  call    cs:__imp_GetCurrentThreadId
0x18000bb2d  lea     rcx, [rsp+278h+Buffer]
0x18000bb32  mov     [rsp+278h+var_240], rcx
0x18000bb37  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000bb3b  mov     [rsp+278h+nSize], eax
0x18000bb3f  mov     eax, [rbx+44h]
0x18000bb42  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000bb46  mov     r9, rdi; unsigned __int16 *
0x18000bb49  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000bb50  mov     rdx, rsi; unsigned __int16 *
0x18000bb53  mov     rcx, r14; this
0x18000bb56  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb5b  cmp     [rbx+18h], r15
0x18000bb5f  jnz     short loc_18000BB71
0x18000bb61  cmp     [rbx+48h], r15
0x18000bb65  jnz     short loc_18000BB71
0x18000bb67  cmp     [rbx+30h], r15
0x18000bb6b  jz      loc_18000BC01
0x18000bb71  lea     r8, asc_18002EC98; "    "
0x18000bb78  mov     rdx, rsi; unsigned __int16 *
0x18000bb7b  mov     rcx, rax; this
0x18000bb7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb83  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000bb87  test    r9, r9
0x18000bb8a  jz      short loc_18000BB9E
0x18000bb8c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000bb93  mov     rdx, rsi; unsigned __int16 *
0x18000bb96  mov     rcx, rax; this
0x18000bb99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bb9e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000bba2  test    r9, r9
0x18000bba5  jz      short loc_18000BBB9
0x18000bba7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000bbae  mov     rdx, rsi; unsigned __int16 *
0x18000bbb1  mov     rcx, rax; this
0x18000bbb4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bbb9  mov     rcx, [rbx+28h]
0x18000bbbd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000bbc1  mov     rdx, rsi; unsigned __int16 *
0x18000bbc4  test    rcx, rcx
0x18000bbc7  jz      short loc_18000BBDF
0x18000bbc9  mov     [rsp+278h+lpBuffer], rcx
0x18000bbce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000bbd5  mov     rcx, rax; this
0x18000bbd8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bbdd  jmp     short loc_18000BC01
0x18000bbdf  mov     rcx, rax; this
0x18000bbe2  test    r9, r9
0x18000bbe5  jz      short loc_18000BBF5
0x18000bbe7  lea     r8, aHs; "[%hs]\n"
0x18000bbee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bbf3  jmp     short loc_18000BC01
0x18000bbf5  lea     r8, asc_18002ED10; "\n"
0x18000bbfc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000bc01  xor     eax, eax
0x18000bc03  mov     rcx, [rsp+278h+var_38]
0x18000bc0b  xor     rcx, rsp; StackCookie
0x18000bc0e  call    __security_check_cookie
0x18000bc13  mov     rbx, [rsp+278h+arg_18]
0x18000bc1b  add     rsp, 250h
0x18000bc22  pop     r15
0x18000bc24  pop     r14
0x18000bc26  pop     rdi
0x18000bc27  pop     rsi
0x18000bc28  pop     rbp
0x18000bc29  retn
```
