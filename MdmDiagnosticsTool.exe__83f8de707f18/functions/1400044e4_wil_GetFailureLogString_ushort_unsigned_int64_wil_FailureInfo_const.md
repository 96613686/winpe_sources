# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400044e4`
- end: `0x1400047a7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14000289c`
- `0x1400055b8`
- `0x140005a94`
- `0x140008480`

## callees

- `0x1400044e4`
- `0x1400058cc`
- `0x140009cc6`
- `0x140009d00`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000469d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000469d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004616`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004616`

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
          v7 = (const char *)&dword_14000DC44;
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
0x1400044e4  mov     [rsp+arg_18], rbx
0x1400044e9  push    rbp
0x1400044ea  push    rsi
0x1400044eb  push    rdi
0x1400044ec  push    r14
0x1400044ee  push    r15
0x1400044f0  sub     rsp, 250h
0x1400044f7  mov     rax, cs:__security_cookie
0x1400044fe  xor     rax, rsp
0x140004501  mov     [rsp+278h+var_38], rax
0x140004509  mov     rbx, r8
0x14000450c  mov     rsi, rdx
0x14000450f  mov     r14, rcx
0x140004512  xor     r15d, r15d
0x140004515  test    rdx, rdx
0x140004518  jz      loc_14000477D
0x14000451e  test    rcx, rcx
0x140004521  jz      loc_14000477D
0x140004527  mov     [rcx], r15w
0x14000452b  mov     rax, cs:g_pfnResultLoggingCallback
0x140004532  test    rax, rax
0x140004535  jz      short loc_140004558
0x140004537  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000453e  jz      short loc_140004558
0x140004540  mov     r8, rdx
0x140004543  mov     rdx, rcx
0x140004546  mov     rcx, rbx
0x140004549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000454e  cmp     [r14], r15w
0x140004552  jnz     loc_14000477D
0x140004558  mov     ecx, [rbx]
0x14000455a  mov     bpl, 8
0x14000455d  test    ecx, ecx
0x14000455f  jz      short loc_1400045AA
0x140004561  sub     ecx, 1
0x140004564  jz      short loc_140004592
0x140004566  sub     ecx, 1
0x140004569  jz      short loc_140004582
0x14000456b  cmp     ecx, 1
0x14000456e  jz      short loc_140004579
0x140004570  lea     rdi, dword_14000DC44
0x140004577  jmp     short loc_1400045B1
0x140004579  lea     rdi, aFailfast; "FailFast"
0x140004580  jmp     short loc_1400045B1
0x140004582  lea     rax, aLoghr; "LogHr"
0x140004589  lea     rdi, aLognt; "LogNt"
0x140004590  jmp     short loc_1400045A0
0x140004592  lea     rax, aReturnhr; "ReturnHr"
0x140004599  lea     rdi, aReturnnt; "ReturnNt"
0x1400045a0  test    [rbx+4], bpl
0x1400045a4  cmovz   rdi, rax
0x1400045a8  jmp     short loc_1400045B1
0x1400045aa  lea     rdi, aException; "Exception"
0x1400045b1  xor     edx, edx; Val
0x1400045b3  mov     r8d, 200h; Size
0x1400045b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400045be  call    memset_0
0x1400045c3  test    [rbx+4], bpl
0x1400045c7  jz      short loc_1400045EC
0x1400045c9  mov     ebp, [rbx+0Ch]
0x1400045cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400045d3  test    rax, rax
0x1400045d6  jz      short loc_140004622
0x1400045d8  mov     r8d, 100h
0x1400045de  lea     rdx, [rsp+278h+Buffer]
0x1400045e3  mov     ecx, ebp
0x1400045e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045ea  jmp     short loc_140004622
0x1400045ec  mov     ebp, [rbx+8]
0x1400045ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1400045f4  mov     [rsp+278h+nSize], 100h; nSize
0x1400045fc  lea     rax, [rsp+278h+Buffer]
0x140004601  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004606  mov     r9d, 400h; dwLanguageId
0x14000460c  mov     r8d, ebp; dwMessageId
0x14000460f  xor     edx, edx; lpSource
0x140004611  mov     ecx, 1200h; dwFlags
0x140004616  call    cs:__imp_FormatMessageW
0x14000461d  nop     dword ptr [rax+rax+00h]
0x140004622  lea     rsi, [r14+rsi*2]
0x140004626  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000462a  mov     rax, [rbx+88h]
0x140004631  mov     rcx, [rbx+80h]
0x140004638  mov     rdx, rsi; unsigned __int16 *
0x14000463b  test    r9, r9
0x14000463e  jz      short loc_140004662
0x140004640  mov     [rsp+278h+Arguments], rax
0x140004645  mov     qword ptr [rsp+278h+nSize], rcx
0x14000464a  mov     eax, [rbx+40h]
0x14000464d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004651  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004658  mov     rcx, r14; this
0x14000465b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004660  jmp     short loc_140004679
0x140004662  mov     [rsp+278h+lpBuffer], rax
0x140004667  mov     r9, rcx; unsigned __int16 *
0x14000466a  lea     r8, aHsP; "%hs!%p: "
0x140004671  mov     rcx, r14; this
0x140004674  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004679  mov     r14, rax
0x14000467c  mov     r9, [rbx+90h]; unsigned __int16 *
0x140004683  test    r9, r9
0x140004686  jz      short loc_14000469D
0x140004688  lea     r8, aCallerP; "(caller: %p) "
0x14000468f  mov     rdx, rsi; unsigned __int16 *
0x140004692  mov     rcx, rax; this
0x140004695  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000469a  mov     r14, rax
0x14000469d  call    cs:__imp_GetCurrentThreadId
0x1400046a4  nop     dword ptr [rax+rax+00h]
0x1400046a9  lea     rcx, [rsp+278h+Buffer]
0x1400046ae  mov     [rsp+278h+var_240], rcx
0x1400046b3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400046b7  mov     [rsp+278h+nSize], eax
0x1400046bb  mov     eax, [rbx+44h]
0x1400046be  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400046c2  mov     r9, rdi; unsigned __int16 *
0x1400046c5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400046cc  mov     rdx, rsi; unsigned __int16 *
0x1400046cf  mov     rcx, r14; this
0x1400046d2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400046d7  cmp     [rbx+18h], r15
0x1400046db  jnz     short loc_1400046ED
0x1400046dd  cmp     [rbx+48h], r15
0x1400046e1  jnz     short loc_1400046ED
0x1400046e3  cmp     [rbx+30h], r15
0x1400046e7  jz      loc_14000477D
0x1400046ed  lea     r8, asc_14000DD38; "    "
0x1400046f4  mov     rdx, rsi; unsigned __int16 *
0x1400046f7  mov     rcx, rax; this
0x1400046fa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400046ff  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004703  test    r9, r9
0x140004706  jz      short loc_14000471A
0x140004708  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000470f  mov     rdx, rsi; unsigned __int16 *
0x140004712  mov     rcx, rax; this
0x140004715  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000471a  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000471e  test    r9, r9
0x140004721  jz      short loc_140004735
0x140004723  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000472a  mov     rdx, rsi; unsigned __int16 *
0x14000472d  mov     rcx, rax; this
0x140004730  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004735  mov     rcx, [rbx+28h]
0x140004739  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000473d  mov     rdx, rsi; unsigned __int16 *
0x140004740  test    rcx, rcx
0x140004743  jz      short loc_14000475B
0x140004745  mov     [rsp+278h+lpBuffer], rcx
0x14000474a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004751  mov     rcx, rax; this
0x140004754  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004759  jmp     short loc_14000477D
0x14000475b  mov     rcx, rax; this
0x14000475e  test    r9, r9
0x140004761  jz      short loc_140004771
0x140004763  lea     r8, aHs; "[%hs]\n"
0x14000476a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000476f  jmp     short loc_14000477D
0x140004771  lea     r8, Format; "\n"
0x140004778  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000477d  xor     eax, eax
0x14000477f  mov     rcx, [rsp+278h+var_38]
0x140004787  xor     rcx, rsp; StackCookie
0x14000478a  call    __security_check_cookie
0x14000478f  mov     rbx, [rsp+278h+arg_18]
0x140004797  add     rsp, 250h
0x14000479e  pop     r15
0x1400047a0  pop     r14
0x1400047a2  pop     rdi
0x1400047a3  pop     rsi
0x1400047a4  pop     rbp
0x1400047a5  retn
```
