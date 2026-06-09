# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004514`
- end: `0x1800047ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x18000317c`
- `0x1800033e4`
- `0x180004e74`
- `0x180006670`
- `0x18000ea85`
- `0x18000ebb9`

## callees

- `0x180001c80`
- `0x180002802`
- `0x180004514`
- `0x180005174`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004646`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004646`

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
          v7 = (const char *)&byte_180011D95;
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
0x180004514  mov     [rsp+arg_18], rbx
0x180004519  push    rbp
0x18000451a  push    rsi
0x18000451b  push    rdi
0x18000451c  push    r14
0x18000451e  push    r15
0x180004520  sub     rsp, 250h
0x180004527  mov     rax, cs:__security_cookie
0x18000452e  xor     rax, rsp
0x180004531  mov     [rsp+278h+var_38], rax
0x180004539  mov     rbx, r8
0x18000453c  mov     rsi, rdx
0x18000453f  mov     r14, rcx
0x180004542  xor     r15d, r15d
0x180004545  test    rdx, rdx
0x180004548  jz      loc_1800047A1
0x18000454e  test    rcx, rcx
0x180004551  jz      loc_1800047A1
0x180004557  mov     [rcx], r15w
0x18000455b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004562  test    rax, rax
0x180004565  jz      short loc_180004588
0x180004567  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000456e  jz      short loc_180004588
0x180004570  mov     r8, rdx
0x180004573  mov     rdx, rcx
0x180004576  mov     rcx, rbx
0x180004579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000457e  cmp     [r14], r15w
0x180004582  jnz     loc_1800047A1
0x180004588  mov     ecx, [rbx]
0x18000458a  mov     bpl, 8
0x18000458d  test    ecx, ecx
0x18000458f  jz      short loc_1800045DA
0x180004591  sub     ecx, 1
0x180004594  jz      short loc_1800045C2
0x180004596  sub     ecx, 1
0x180004599  jz      short loc_1800045B2
0x18000459b  cmp     ecx, 1
0x18000459e  jz      short loc_1800045A9
0x1800045a0  lea     rdi, byte_180011D95
0x1800045a7  jmp     short loc_1800045E1
0x1800045a9  lea     rdi, aFailfast; "FailFast"
0x1800045b0  jmp     short loc_1800045E1
0x1800045b2  lea     rax, aLoghr; "LogHr"
0x1800045b9  lea     rdi, aLognt; "LogNt"
0x1800045c0  jmp     short loc_1800045D0
0x1800045c2  lea     rax, aReturnhr; "ReturnHr"
0x1800045c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800045d0  test    [rbx+4], bpl
0x1800045d4  cmovz   rdi, rax
0x1800045d8  jmp     short loc_1800045E1
0x1800045da  lea     rdi, aException; "Exception"
0x1800045e1  xor     edx, edx; Val
0x1800045e3  mov     r8d, 200h; Size
0x1800045e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800045ee  call    memset_0
0x1800045f3  test    [rbx+4], bpl
0x1800045f7  jz      short loc_18000461C
0x1800045f9  mov     ebp, [rbx+0Ch]
0x1800045fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004603  test    rax, rax
0x180004606  jz      short loc_18000464C
0x180004608  mov     r8d, 100h
0x18000460e  lea     rdx, [rsp+278h+Buffer]
0x180004613  mov     ecx, ebp
0x180004615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000461a  jmp     short loc_18000464C
0x18000461c  mov     ebp, [rbx+8]
0x18000461f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004624  mov     [rsp+278h+nSize], 100h; nSize
0x18000462c  lea     rax, [rsp+278h+Buffer]
0x180004631  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004636  mov     r9d, 400h; dwLanguageId
0x18000463c  mov     r8d, ebp; dwMessageId
0x18000463f  xor     edx, edx; lpSource
0x180004641  mov     ecx, 1200h; dwFlags
0x180004646  call    cs:__imp_FormatMessageW
0x18000464c  lea     rsi, [r14+rsi*2]
0x180004650  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004654  mov     rax, [rbx+88h]
0x18000465b  mov     rcx, [rbx+80h]
0x180004662  mov     rdx, rsi; unsigned __int16 *
0x180004665  test    r9, r9
0x180004668  jz      short loc_18000468C
0x18000466a  mov     [rsp+278h+Arguments], rax
0x18000466f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004674  mov     eax, [rbx+40h]
0x180004677  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000467b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004682  mov     rcx, r14; this
0x180004685  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000468a  jmp     short loc_1800046A3
0x18000468c  mov     [rsp+278h+lpBuffer], rax
0x180004691  mov     r9, rcx; unsigned __int16 *
0x180004694  lea     r8, aHsP; "%hs!%p: "
0x18000469b  mov     rcx, r14; this
0x18000469e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046a3  mov     r14, rax
0x1800046a6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800046ad  test    r9, r9
0x1800046b0  jz      short loc_1800046C7
0x1800046b2  lea     r8, aCallerP; "(caller: %p) "
0x1800046b9  mov     rdx, rsi; unsigned __int16 *
0x1800046bc  mov     rcx, rax; this
0x1800046bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046c4  mov     r14, rax
0x1800046c7  call    cs:__imp_GetCurrentThreadId
0x1800046cd  lea     rcx, [rsp+278h+Buffer]
0x1800046d2  mov     [rsp+278h+var_240], rcx
0x1800046d7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800046db  mov     [rsp+278h+nSize], eax
0x1800046df  mov     eax, [rbx+44h]
0x1800046e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800046e6  mov     r9, rdi; unsigned __int16 *
0x1800046e9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800046f0  mov     rdx, rsi; unsigned __int16 *
0x1800046f3  mov     rcx, r14; this
0x1800046f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046fb  cmp     [rbx+18h], r15
0x1800046ff  jnz     short loc_180004711
0x180004701  cmp     [rbx+48h], r15
0x180004705  jnz     short loc_180004711
0x180004707  cmp     [rbx+30h], r15
0x18000470b  jz      loc_1800047A1
0x180004711  lea     r8, asc_180011E98; "    "
0x180004718  mov     rdx, rsi; unsigned __int16 *
0x18000471b  mov     rcx, rax; this
0x18000471e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004723  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004727  test    r9, r9
0x18000472a  jz      short loc_18000473E
0x18000472c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004733  mov     rdx, rsi; unsigned __int16 *
0x180004736  mov     rcx, rax; this
0x180004739  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000473e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004742  test    r9, r9
0x180004745  jz      short loc_180004759
0x180004747  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000474e  mov     rdx, rsi; unsigned __int16 *
0x180004751  mov     rcx, rax; this
0x180004754  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004759  mov     rcx, [rbx+28h]
0x18000475d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004761  mov     rdx, rsi; unsigned __int16 *
0x180004764  test    rcx, rcx
0x180004767  jz      short loc_18000477F
0x180004769  mov     [rsp+278h+lpBuffer], rcx
0x18000476e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004775  mov     rcx, rax; this
0x180004778  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000477d  jmp     short loc_1800047A1
0x18000477f  mov     rcx, rax; this
0x180004782  test    r9, r9
0x180004785  jz      short loc_180004795
0x180004787  lea     r8, aHs; "[%hs]\n"
0x18000478e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004793  jmp     short loc_1800047A1
0x180004795  lea     r8, asc_180011F10; "\n"
0x18000479c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047a1  xor     eax, eax
0x1800047a3  mov     rcx, [rsp+278h+var_38]
0x1800047ab  xor     rcx, rsp; StackCookie
0x1800047ae  call    __security_check_cookie
0x1800047b3  mov     rbx, [rsp+278h+arg_18]
0x1800047bb  add     rsp, 250h
0x1800047c2  pop     r15
0x1800047c4  pop     r14
0x1800047c6  pop     rdi
0x1800047c7  pop     rsi
0x1800047c8  pop     rbp
0x1800047c9  retn
```
