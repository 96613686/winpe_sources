# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18004b3f8`
- end: `0x18004b6ae`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180012d7c`
- `0x1800251a4`
- `0x18004dc30`

## callees

- `0x180043680`
- `0x1800441ac`
- `0x18004b3f8`
- `0x18004bb0c`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b5ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b5ab`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004b52a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004b52a`

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
          v7 = (const char *)&qword_1800A2650;
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
0x18004b3f8  mov     [rsp+arg_18], rbx
0x18004b3fd  push    rbp
0x18004b3fe  push    rsi
0x18004b3ff  push    rdi
0x18004b400  push    r14
0x18004b402  push    r15
0x18004b404  sub     rsp, 250h
0x18004b40b  mov     rax, cs:__security_cookie
0x18004b412  xor     rax, rsp
0x18004b415  mov     [rsp+278h+var_38], rax
0x18004b41d  mov     rbx, r8
0x18004b420  mov     rsi, rdx
0x18004b423  mov     r14, rcx
0x18004b426  xor     r15d, r15d
0x18004b429  test    rdx, rdx
0x18004b42c  jz      loc_18004B685
0x18004b432  test    rcx, rcx
0x18004b435  jz      loc_18004B685
0x18004b43b  mov     [rcx], r15w
0x18004b43f  mov     rax, cs:g_pfnResultLoggingCallback
0x18004b446  test    rax, rax
0x18004b449  jz      short loc_18004B46C
0x18004b44b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18004b452  jz      short loc_18004B46C
0x18004b454  mov     r8, rdx
0x18004b457  mov     rdx, rcx
0x18004b45a  mov     rcx, rbx
0x18004b45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b462  cmp     [r14], r15w
0x18004b466  jnz     loc_18004B685
0x18004b46c  mov     ecx, [rbx]
0x18004b46e  mov     bpl, 8
0x18004b471  test    ecx, ecx
0x18004b473  jz      short loc_18004B4BE
0x18004b475  sub     ecx, 1
0x18004b478  jz      short loc_18004B4A6
0x18004b47a  sub     ecx, 1
0x18004b47d  jz      short loc_18004B496
0x18004b47f  cmp     ecx, 1
0x18004b482  jz      short loc_18004B48D
0x18004b484  lea     rdi, qword_1800A2650
0x18004b48b  jmp     short loc_18004B4C5
0x18004b48d  lea     rdi, aFailfast; "FailFast"
0x18004b494  jmp     short loc_18004B4C5
0x18004b496  lea     rax, aLoghr; "LogHr"
0x18004b49d  lea     rdi, aLognt; "LogNt"
0x18004b4a4  jmp     short loc_18004B4B4
0x18004b4a6  lea     rax, aReturnhr; "ReturnHr"
0x18004b4ad  lea     rdi, aReturnnt; "ReturnNt"
0x18004b4b4  test    [rbx+4], bpl
0x18004b4b8  cmovz   rdi, rax
0x18004b4bc  jmp     short loc_18004B4C5
0x18004b4be  lea     rdi, aException; "Exception"
0x18004b4c5  xor     edx, edx; Val
0x18004b4c7  mov     r8d, 200h; Size
0x18004b4cd  lea     rcx, [rsp+278h+Buffer]; void *
0x18004b4d2  call    memset_0
0x18004b4d7  test    [rbx+4], bpl
0x18004b4db  jz      short loc_18004B500
0x18004b4dd  mov     ebp, [rbx+0Ch]
0x18004b4e0  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18004b4e7  test    rax, rax
0x18004b4ea  jz      short loc_18004B530
0x18004b4ec  mov     r8d, 100h
0x18004b4f2  lea     rdx, [rsp+278h+Buffer]
0x18004b4f7  mov     ecx, ebp
0x18004b4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4fe  jmp     short loc_18004B530
0x18004b500  mov     ebp, [rbx+8]
0x18004b503  mov     [rsp+278h+Arguments], r15; Arguments
0x18004b508  mov     [rsp+278h+nSize], 100h; nSize
0x18004b510  lea     rax, [rsp+278h+Buffer]
0x18004b515  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18004b51a  mov     r9d, 400h; dwLanguageId
0x18004b520  mov     r8d, ebp; dwMessageId
0x18004b523  xor     edx, edx; lpSource
0x18004b525  mov     ecx, 1200h; dwFlags
0x18004b52a  call    cs:__imp_FormatMessageW
0x18004b530  lea     rsi, [r14+rsi*2]
0x18004b534  mov     r9, [rbx+38h]; unsigned __int16 *
0x18004b538  mov     rax, [rbx+88h]
0x18004b53f  mov     rcx, [rbx+80h]
0x18004b546  mov     rdx, rsi; unsigned __int16 *
0x18004b549  test    r9, r9
0x18004b54c  jz      short loc_18004B570
0x18004b54e  mov     [rsp+278h+Arguments], rax
0x18004b553  mov     qword ptr [rsp+278h+nSize], rcx
0x18004b558  mov     eax, [rbx+40h]
0x18004b55b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18004b55f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18004b566  mov     rcx, r14; this
0x18004b569  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004b56e  jmp     short loc_18004B587
0x18004b570  mov     [rsp+278h+lpBuffer], rax
0x18004b575  mov     r9, rcx; unsigned __int16 *
0x18004b578  lea     r8, aHsP; "%hs!%p: "
0x18004b57f  mov     rcx, r14; this
0x18004b582  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004b587  mov     r14, rax
0x18004b58a  mov     r9, [rbx+90h]; unsigned __int16 *
0x18004b591  test    r9, r9
0x18004b594  jz      short loc_18004B5AB
0x18004b596  lea     r8, aCallerP; "(caller: %p) "
0x18004b59d  mov     rdx, rsi; unsigned __int16 *
0x18004b5a0  mov     rcx, rax; this
0x18004b5a3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004b5a8  mov     r14, rax
0x18004b5ab  call    cs:__imp_GetCurrentThreadId
0x18004b5b1  lea     rcx, [rsp+278h+Buffer]
0x18004b5b6  mov     [rsp+278h+var_240], rcx
0x18004b5bb  mov     dword ptr [rsp+278h+Arguments], ebp
0x18004b5bf  mov     [rsp+278h+nSize], eax
0x18004b5c3  mov     eax, [rbx+44h]
0x18004b5c6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18004b5ca  mov     r9, rdi; unsigned __int16 *
0x18004b5cd  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18004b5d4  mov     rdx, rsi; unsigned __int16 *
0x18004b5d7  mov     rcx, r14; this
0x18004b5da  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004b5df  cmp     [rbx+18h], r15
0x18004b5e3  jnz     short loc_18004B5F5
0x18004b5e5  cmp     [rbx+48h], r15
0x18004b5e9  jnz     short loc_18004B5F5
0x18004b5eb  cmp     [rbx+30h], r15
0x18004b5ef  jz      loc_18004B685
0x18004b5f5  lea     r8, asc_1800A4560; "    "
0x18004b5fc  mov     rdx, rsi; unsigned __int16 *
0x18004b5ff  mov     rcx, rax; this
0x18004b602  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004b607  mov     r9, [rbx+18h]; unsigned __int16 *
0x18004b60b  test    r9, r9
0x18004b60e  jz      short loc_18004B622
0x18004b610  lea     r8, aMsgWs; "Msg:[%ws] "
0x18004b617  mov     rdx, rsi; unsigned __int16 *
0x18004b61a  mov     rcx, rax; this
0x18004b61d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004b622  mov     r9, [rbx+48h]; unsigned __int16 *
0x18004b626  test    r9, r9
0x18004b629  jz      short loc_18004B63D
0x18004b62b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18004b632  mov     rdx, rsi; unsigned __int16 *
0x18004b635  mov     rcx, rax; this
0x18004b638  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004b63d  mov     rcx, [rbx+28h]
0x18004b641  mov     r9, [rbx+30h]; unsigned __int16 *
0x18004b645  mov     rdx, rsi; unsigned __int16 *
0x18004b648  test    rcx, rcx
0x18004b64b  jz      short loc_18004B663
0x18004b64d  mov     [rsp+278h+lpBuffer], rcx
0x18004b652  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18004b659  mov     rcx, rax; this
0x18004b65c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004b661  jmp     short loc_18004B685
0x18004b663  mov     rcx, rax; this
0x18004b666  test    r9, r9
0x18004b669  jz      short loc_18004B679
0x18004b66b  lea     r8, aHs; "[%hs]\n"
0x18004b672  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004b677  jmp     short loc_18004B685
0x18004b679  lea     r8, asc_1800A45D8; "\n"
0x18004b680  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004b685  xor     eax, eax
0x18004b687  mov     rcx, [rsp+278h+var_38]
0x18004b68f  xor     rcx, rsp; StackCookie
0x18004b692  call    __security_check_cookie
0x18004b697  mov     rbx, [rsp+278h+arg_18]
0x18004b69f  add     rsp, 250h
0x18004b6a6  pop     r15
0x18004b6a8  pop     r14
0x18004b6aa  pop     rdi
0x18004b6ab  pop     rsi
0x18004b6ac  pop     rbp
0x18004b6ad  retn
```
