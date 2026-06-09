# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180014984`
- end: `0x180014c45`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cb5c`
- `0x180013bbc`
- `0x18001522c`
- `0x1800162d0`

## callees

- `0x18000e320`
- `0x180014984`
- `0x180022792`
- `0x1800227c0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014b42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014b42`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180014ac1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180014ac1`

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
          v7 = (const char *)&qword_18002E948;
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
0x180014984  mov     rax, rsp
0x180014987  push    rbp
0x180014988  push    rsi
0x180014989  push    rdi
0x18001498a  push    r14
0x18001498c  push    r15
0x18001498e  sub     rsp, 260h
0x180014995  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18001499e  mov     [rax+20h], rbx
0x1800149a2  mov     rax, cs:__security_cookie
0x1800149a9  xor     rax, rsp
0x1800149ac  mov     [rsp+288h+var_38], rax
0x1800149b4  mov     rbx, r8
0x1800149b7  mov     rsi, rdx
0x1800149ba  mov     r14, rcx
0x1800149bd  xor     r15d, r15d
0x1800149c0  test    rdx, rdx
0x1800149c3  jz      loc_180014C1C
0x1800149c9  test    rcx, rcx
0x1800149cc  jz      loc_180014C1C
0x1800149d2  mov     [rcx], r15w
0x1800149d6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800149dd  test    rax, rax
0x1800149e0  jz      short loc_180014A03
0x1800149e2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800149e9  jz      short loc_180014A03
0x1800149eb  mov     r8, rdx
0x1800149ee  mov     rdx, rcx
0x1800149f1  mov     rcx, rbx
0x1800149f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149f9  cmp     [r14], r15w
0x1800149fd  jnz     loc_180014C1C
0x180014a03  mov     ecx, [rbx]
0x180014a05  mov     bpl, 8
0x180014a08  test    ecx, ecx
0x180014a0a  jz      short loc_180014A55
0x180014a0c  sub     ecx, 1
0x180014a0f  jz      short loc_180014A3D
0x180014a11  sub     ecx, 1
0x180014a14  jz      short loc_180014A2D
0x180014a16  cmp     ecx, 1
0x180014a19  jz      short loc_180014A24
0x180014a1b  lea     rdi, qword_18002E948
0x180014a22  jmp     short loc_180014A5C
0x180014a24  lea     rdi, aFailfast; "FailFast"
0x180014a2b  jmp     short loc_180014A5C
0x180014a2d  lea     rax, aLoghr; "LogHr"
0x180014a34  lea     rdi, aLognt; "LogNt"
0x180014a3b  jmp     short loc_180014A4B
0x180014a3d  lea     rax, aReturnhr; "ReturnHr"
0x180014a44  lea     rdi, aReturnnt; "ReturnNt"
0x180014a4b  test    [rbx+4], bpl
0x180014a4f  cmovz   rdi, rax
0x180014a53  jmp     short loc_180014A5C
0x180014a55  lea     rdi, aException; "Exception"
0x180014a5c  xor     edx, edx; Val
0x180014a5e  mov     r8d, 200h; Size
0x180014a64  lea     rcx, [rsp+288h+Buffer]; void *
0x180014a69  call    memset_0
0x180014a6e  test    [rbx+4], bpl
0x180014a72  jz      short loc_180014A97
0x180014a74  mov     ebp, [rbx+0Ch]
0x180014a77  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180014a7e  test    rax, rax
0x180014a81  jz      short loc_180014AC7
0x180014a83  mov     r8d, 100h
0x180014a89  lea     rdx, [rsp+288h+Buffer]
0x180014a8e  mov     ecx, ebp
0x180014a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a95  jmp     short loc_180014AC7
0x180014a97  mov     ebp, [rbx+8]
0x180014a9a  mov     [rsp+288h+Arguments], r15; Arguments
0x180014a9f  mov     [rsp+288h+nSize], 100h; nSize
0x180014aa7  lea     rax, [rsp+288h+Buffer]
0x180014aac  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180014ab1  mov     r9d, 400h; dwLanguageId
0x180014ab7  mov     r8d, ebp; dwMessageId
0x180014aba  xor     edx, edx; lpSource
0x180014abc  mov     ecx, 1200h; dwFlags
0x180014ac1  call    cs:__imp_FormatMessageW
0x180014ac7  lea     rsi, [r14+rsi*2]
0x180014acb  mov     r9, [rbx+38h]; unsigned __int16 *
0x180014acf  mov     rax, [rbx+88h]
0x180014ad6  mov     rcx, [rbx+80h]
0x180014add  mov     rdx, rsi; unsigned __int16 *
0x180014ae0  test    r9, r9
0x180014ae3  jz      short loc_180014B07
0x180014ae5  mov     [rsp+288h+Arguments], rax
0x180014aea  mov     qword ptr [rsp+288h+nSize], rcx
0x180014aef  mov     eax, [rbx+40h]
0x180014af2  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180014af6  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180014afd  mov     rcx, r14; this
0x180014b00  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014b05  jmp     short loc_180014B1E
0x180014b07  mov     [rsp+288h+lpBuffer], rax
0x180014b0c  mov     r9, rcx; unsigned __int16 *
0x180014b0f  lea     r8, aHsP; "%hs!%p: "
0x180014b16  mov     rcx, r14; this
0x180014b19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014b1e  mov     r14, rax
0x180014b21  mov     r9, [rbx+90h]; unsigned __int16 *
0x180014b28  test    r9, r9
0x180014b2b  jz      short loc_180014B42
0x180014b2d  lea     r8, aCallerP; "(caller: %p) "
0x180014b34  mov     rdx, rsi; unsigned __int16 *
0x180014b37  mov     rcx, rax; this
0x180014b3a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014b3f  mov     r14, rax
0x180014b42  call    cs:__imp_GetCurrentThreadId
0x180014b48  lea     rcx, [rsp+288h+Buffer]
0x180014b4d  mov     [rsp+288h+var_250], rcx
0x180014b52  mov     dword ptr [rsp+288h+Arguments], ebp
0x180014b56  mov     [rsp+288h+nSize], eax
0x180014b5a  mov     eax, [rbx+44h]
0x180014b5d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180014b61  mov     r9, rdi; unsigned __int16 *
0x180014b64  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180014b6b  mov     rdx, rsi; unsigned __int16 *
0x180014b6e  mov     rcx, r14; this
0x180014b71  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014b76  cmp     [rbx+18h], r15
0x180014b7a  jnz     short loc_180014B8C
0x180014b7c  cmp     [rbx+48h], r15
0x180014b80  jnz     short loc_180014B8C
0x180014b82  cmp     [rbx+30h], r15
0x180014b86  jz      loc_180014C1C
0x180014b8c  lea     r8, asc_18002EA38; "    "
0x180014b93  mov     rdx, rsi; unsigned __int16 *
0x180014b96  mov     rcx, rax; this
0x180014b99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014b9e  mov     r9, [rbx+18h]; unsigned __int16 *
0x180014ba2  test    r9, r9
0x180014ba5  jz      short loc_180014BB9
0x180014ba7  lea     r8, aMsgWs; "Msg:[%ws] "
0x180014bae  mov     rdx, rsi; unsigned __int16 *
0x180014bb1  mov     rcx, rax; this
0x180014bb4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014bb9  mov     r9, [rbx+48h]; unsigned __int16 *
0x180014bbd  test    r9, r9
0x180014bc0  jz      short loc_180014BD4
0x180014bc2  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180014bc9  mov     rdx, rsi; unsigned __int16 *
0x180014bcc  mov     rcx, rax; this
0x180014bcf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014bd4  mov     rcx, [rbx+28h]
0x180014bd8  mov     r9, [rbx+30h]; unsigned __int16 *
0x180014bdc  mov     rdx, rsi; unsigned __int16 *
0x180014bdf  test    rcx, rcx
0x180014be2  jz      short loc_180014BFA
0x180014be4  mov     [rsp+288h+lpBuffer], rcx
0x180014be9  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180014bf0  mov     rcx, rax; this
0x180014bf3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014bf8  jmp     short loc_180014C1C
0x180014bfa  mov     rcx, rax; this
0x180014bfd  test    r9, r9
0x180014c00  jz      short loc_180014C10
0x180014c02  lea     r8, aHs; "[%hs]\n"
0x180014c09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014c0e  jmp     short loc_180014C1C
0x180014c10  lea     r8, asc_18002EAB0; "\n"
0x180014c17  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014c1c  xor     eax, eax
0x180014c1e  mov     rcx, [rsp+288h+var_38]
0x180014c26  xor     rcx, rsp; StackCookie
0x180014c29  call    __security_check_cookie
0x180014c2e  mov     rbx, [rsp+288h+arg_18]
0x180014c36  add     rsp, 260h
0x180014c3d  pop     r15
0x180014c3f  pop     r14
0x180014c41  pop     rdi
0x180014c42  pop     rsi
0x180014c43  pop     rbp
0x180014c44  retn
```
