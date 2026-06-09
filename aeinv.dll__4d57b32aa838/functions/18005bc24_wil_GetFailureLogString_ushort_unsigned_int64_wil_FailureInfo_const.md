# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18005bc24`
- end: `0x18005bee5`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `29`
- callee_count: `5`
- tags: ``

## callers

- `0x18002f13c`
- `0x18005bf54`
- `0x18005c9d0`
- `0x18012568c`
- `0x180125987`
- `0x180125b5c`
- `0x1801264fc`
- `0x180127353`
- `0x180127577`
- `0x18012902c`
- `0x1801292d0`
- `0x1801296dc`
- `0x1801298b7`
- `0x180129c63`
- `0x18012a688`
- `0x18012a889`
- `0x18012aaa9`
- `0x18012ac90`
- `0x18012afcd`
- `0x18012b190`
- `0x18012b8f4`
- `0x18012bbf2`
- `0x18012c040`
- `0x18012c29b`
- `0x18012c68d`
- `0x18012d2ba`
- `0x18012d5e3`
- `0x18012d7c0`
- `0x18012e07c`

## callees

- `0x180059920`
- `0x18005a8bc`
- `0x18005bc24`
- `0x18005bf04`
- `0x180130010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18005bd61`
- `KERNEL32!FormatMessageW` at `0x18005bd61`
- `KERNEL32!GetCurrentThreadId` at `0x18005bde2`
- `KERNEL32!GetCurrentThreadId` at `0x18005bde2`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !this )
    return 0;
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&dword_18013AE3C;
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
                          Buffer,
                          -2);
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
0x18005bc24  mov     rax, rsp
0x18005bc27  push    rbp
0x18005bc28  push    rsi
0x18005bc29  push    rdi
0x18005bc2a  push    r14
0x18005bc2c  push    r15
0x18005bc2e  sub     rsp, 260h
0x18005bc35  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18005bc3e  mov     [rax+20h], rbx
0x18005bc42  mov     rax, cs:__security_cookie
0x18005bc49  xor     rax, rsp
0x18005bc4c  mov     [rsp+288h+var_38], rax
0x18005bc54  mov     rbx, r8
0x18005bc57  mov     rsi, rdx
0x18005bc5a  mov     r14, rcx
0x18005bc5d  xor     r15d, r15d
0x18005bc60  test    rdx, rdx
0x18005bc63  jz      loc_18005BEBC
0x18005bc69  test    rcx, rcx
0x18005bc6c  jz      loc_18005BEBC
0x18005bc72  mov     [rcx], r15w
0x18005bc76  mov     rax, cs:g_pfnResultLoggingCallback
0x18005bc7d  test    rax, rax
0x18005bc80  jz      short loc_18005BCA3
0x18005bc82  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005bc89  jz      short loc_18005BCA3
0x18005bc8b  mov     r8, rdx
0x18005bc8e  mov     rdx, rcx
0x18005bc91  mov     rcx, rbx
0x18005bc94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc99  cmp     [r14], r15w
0x18005bc9d  jnz     loc_18005BEBC
0x18005bca3  mov     ecx, [rbx]
0x18005bca5  mov     bpl, 8
0x18005bca8  test    ecx, ecx
0x18005bcaa  jz      short loc_18005BCF5
0x18005bcac  sub     ecx, 1
0x18005bcaf  jz      short loc_18005BCDD
0x18005bcb1  sub     ecx, 1
0x18005bcb4  jz      short loc_18005BCCD
0x18005bcb6  cmp     ecx, 1
0x18005bcb9  jz      short loc_18005BCC4
0x18005bcbb  lea     rdi, dword_18013AE3C
0x18005bcc2  jmp     short loc_18005BCFC
0x18005bcc4  lea     rdi, aFailfast; "FailFast"
0x18005bccb  jmp     short loc_18005BCFC
0x18005bccd  lea     rax, aLoghr; "LogHr"
0x18005bcd4  lea     rdi, aLognt; "LogNt"
0x18005bcdb  jmp     short loc_18005BCEB
0x18005bcdd  lea     rax, aReturnhr; "ReturnHr"
0x18005bce4  lea     rdi, aReturnnt; "ReturnNt"
0x18005bceb  test    [rbx+4], bpl
0x18005bcef  cmovz   rdi, rax
0x18005bcf3  jmp     short loc_18005BCFC
0x18005bcf5  lea     rdi, aException; "Exception"
0x18005bcfc  xor     edx, edx; Val
0x18005bcfe  mov     r8d, 200h; Size
0x18005bd04  lea     rcx, [rsp+288h+Buffer]; void *
0x18005bd09  call    memset_0
0x18005bd0e  test    [rbx+4], bpl
0x18005bd12  jz      short loc_18005BD37
0x18005bd14  mov     ebp, [rbx+0Ch]
0x18005bd17  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18005bd1e  test    rax, rax
0x18005bd21  jz      short loc_18005BD67
0x18005bd23  mov     r8d, 100h
0x18005bd29  lea     rdx, [rsp+288h+Buffer]
0x18005bd2e  mov     ecx, ebp
0x18005bd30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd35  jmp     short loc_18005BD67
0x18005bd37  mov     ebp, [rbx+8]
0x18005bd3a  mov     [rsp+288h+Arguments], r15; Arguments
0x18005bd3f  mov     [rsp+288h+nSize], 100h; nSize
0x18005bd47  lea     rax, [rsp+288h+Buffer]
0x18005bd4c  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18005bd51  mov     r9d, 400h; dwLanguageId
0x18005bd57  mov     r8d, ebp; dwMessageId
0x18005bd5a  xor     edx, edx; lpSource
0x18005bd5c  mov     ecx, 1200h; dwFlags
0x18005bd61  call    cs:__imp_FormatMessageW
0x18005bd67  lea     rsi, [r14+rsi*2]
0x18005bd6b  mov     r9, [rbx+38h]; unsigned __int16 *
0x18005bd6f  mov     rax, [rbx+88h]
0x18005bd76  mov     rcx, [rbx+80h]
0x18005bd7d  mov     rdx, rsi; unsigned __int16 *
0x18005bd80  test    r9, r9
0x18005bd83  jz      short loc_18005BDA7
0x18005bd85  mov     [rsp+288h+Arguments], rax
0x18005bd8a  mov     qword ptr [rsp+288h+nSize], rcx
0x18005bd8f  mov     eax, [rbx+40h]
0x18005bd92  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18005bd96  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18005bd9d  mov     rcx, r14; this
0x18005bda0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bda5  jmp     short loc_18005BDBE
0x18005bda7  mov     [rsp+288h+lpBuffer], rax
0x18005bdac  mov     r9, rcx; unsigned __int16 *
0x18005bdaf  lea     r8, aHsP; "%hs!%p: "
0x18005bdb6  mov     rcx, r14; this
0x18005bdb9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bdbe  mov     r14, rax
0x18005bdc1  mov     r9, [rbx+90h]; unsigned __int16 *
0x18005bdc8  test    r9, r9
0x18005bdcb  jz      short loc_18005BDE2
0x18005bdcd  lea     r8, aCallerP; "(caller: %p) "
0x18005bdd4  mov     rdx, rsi; unsigned __int16 *
0x18005bdd7  mov     rcx, rax; this
0x18005bdda  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bddf  mov     r14, rax
0x18005bde2  call    cs:__imp_GetCurrentThreadId
0x18005bde8  lea     rcx, [rsp+288h+Buffer]
0x18005bded  mov     [rsp+288h+var_250], rcx
0x18005bdf2  mov     dword ptr [rsp+288h+Arguments], ebp
0x18005bdf6  mov     [rsp+288h+nSize], eax
0x18005bdfa  mov     eax, [rbx+44h]
0x18005bdfd  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18005be01  mov     r9, rdi; unsigned __int16 *
0x18005be04  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18005be0b  mov     rdx, rsi; unsigned __int16 *
0x18005be0e  mov     rcx, r14; this
0x18005be11  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005be16  cmp     [rbx+18h], r15
0x18005be1a  jnz     short loc_18005BE2C
0x18005be1c  cmp     [rbx+48h], r15
0x18005be20  jnz     short loc_18005BE2C
0x18005be22  cmp     [rbx+30h], r15
0x18005be26  jz      loc_18005BEBC
0x18005be2c  lea     r8, asc_18013E028; "    "
0x18005be33  mov     rdx, rsi; unsigned __int16 *
0x18005be36  mov     rcx, rax; this
0x18005be39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005be3e  mov     r9, [rbx+18h]; unsigned __int16 *
0x18005be42  test    r9, r9
0x18005be45  jz      short loc_18005BE59
0x18005be47  lea     r8, aMsgWs; "Msg:[%ws] "
0x18005be4e  mov     rdx, rsi; unsigned __int16 *
0x18005be51  mov     rcx, rax; this
0x18005be54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005be59  mov     r9, [rbx+48h]; unsigned __int16 *
0x18005be5d  test    r9, r9
0x18005be60  jz      short loc_18005BE74
0x18005be62  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18005be69  mov     rdx, rsi; unsigned __int16 *
0x18005be6c  mov     rcx, rax; this
0x18005be6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005be74  mov     rcx, [rbx+28h]
0x18005be78  mov     r9, [rbx+30h]; unsigned __int16 *
0x18005be7c  mov     rdx, rsi; unsigned __int16 *
0x18005be7f  test    rcx, rcx
0x18005be82  jz      short loc_18005BE9A
0x18005be84  mov     [rsp+288h+lpBuffer], rcx
0x18005be89  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x18005be90  mov     rcx, rax; this
0x18005be93  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005be98  jmp     short loc_18005BEBC
0x18005be9a  mov     rcx, rax; this
0x18005be9d  test    r9, r9
0x18005bea0  jz      short loc_18005BEB0
0x18005bea2  lea     r8, aHs_0; "[%hs]\n"
0x18005bea9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005beae  jmp     short loc_18005BEBC
0x18005beb0  lea     r8, asc_18013E0A0; "\n"
0x18005beb7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005bebc  xor     eax, eax
0x18005bebe  mov     rcx, [rsp+288h+var_38]
0x18005bec6  xor     rcx, rsp; StackCookie
0x18005bec9  call    __security_check_cookie
0x18005bece  mov     rbx, [rsp+288h+arg_18]
0x18005bed6  add     rsp, 260h
0x18005bedd  pop     r15
0x18005bedf  pop     r14
0x18005bee1  pop     rdi
0x18005bee2  pop     rsi
0x18005bee3  pop     rbp
0x18005bee4  retn
```
