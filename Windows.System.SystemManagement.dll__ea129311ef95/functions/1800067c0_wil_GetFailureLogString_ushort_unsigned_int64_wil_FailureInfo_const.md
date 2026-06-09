# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800067c0`
- end: `0x180006a76`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000454c`
- `0x1800072a4`
- `0x1800077d4`
- `0x180009940`

## callees

- `0x180002dc0`
- `0x18000399c`
- `0x1800067c0`
- `0x1800075a4`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006973`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006973`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800068f2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800068f2`

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
          v7 = (const char *)&dword_180034A84;
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
0x1800067c0  mov     [rsp+arg_18], rbx
0x1800067c5  push    rbp
0x1800067c6  push    rsi
0x1800067c7  push    rdi
0x1800067c8  push    r14
0x1800067ca  push    r15
0x1800067cc  sub     rsp, 250h
0x1800067d3  mov     rax, cs:__security_cookie
0x1800067da  xor     rax, rsp
0x1800067dd  mov     [rsp+278h+var_38], rax
0x1800067e5  mov     rbx, r8
0x1800067e8  mov     rsi, rdx
0x1800067eb  mov     r14, rcx
0x1800067ee  xor     r15d, r15d
0x1800067f1  test    rdx, rdx
0x1800067f4  jz      loc_180006A4D
0x1800067fa  test    rcx, rcx
0x1800067fd  jz      loc_180006A4D
0x180006803  mov     [rcx], r15w
0x180006807  mov     rax, cs:g_pfnResultLoggingCallback
0x18000680e  test    rax, rax
0x180006811  jz      short loc_180006834
0x180006813  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000681a  jz      short loc_180006834
0x18000681c  mov     r8, rdx
0x18000681f  mov     rdx, rcx
0x180006822  mov     rcx, rbx
0x180006825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000682a  cmp     [r14], r15w
0x18000682e  jnz     loc_180006A4D
0x180006834  mov     ecx, [rbx]
0x180006836  mov     bpl, 8
0x180006839  test    ecx, ecx
0x18000683b  jz      short loc_180006886
0x18000683d  sub     ecx, 1
0x180006840  jz      short loc_18000686E
0x180006842  sub     ecx, 1
0x180006845  jz      short loc_18000685E
0x180006847  cmp     ecx, 1
0x18000684a  jz      short loc_180006855
0x18000684c  lea     rdi, dword_180034A84
0x180006853  jmp     short loc_18000688D
0x180006855  lea     rdi, aFailfast; "FailFast"
0x18000685c  jmp     short loc_18000688D
0x18000685e  lea     rax, aLoghr; "LogHr"
0x180006865  lea     rdi, aLognt; "LogNt"
0x18000686c  jmp     short loc_18000687C
0x18000686e  lea     rax, aReturnhr; "ReturnHr"
0x180006875  lea     rdi, aReturnnt; "ReturnNt"
0x18000687c  test    [rbx+4], bpl
0x180006880  cmovz   rdi, rax
0x180006884  jmp     short loc_18000688D
0x180006886  lea     rdi, aException; "Exception"
0x18000688d  xor     edx, edx; Val
0x18000688f  mov     r8d, 200h; Size
0x180006895  lea     rcx, [rsp+278h+Buffer]; void *
0x18000689a  call    memset_0
0x18000689f  test    [rbx+4], bpl
0x1800068a3  jz      short loc_1800068C8
0x1800068a5  mov     ebp, [rbx+0Ch]
0x1800068a8  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800068af  test    rax, rax
0x1800068b2  jz      short loc_1800068F8
0x1800068b4  mov     r8d, 100h
0x1800068ba  lea     rdx, [rsp+278h+Buffer]
0x1800068bf  mov     ecx, ebp
0x1800068c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068c6  jmp     short loc_1800068F8
0x1800068c8  mov     ebp, [rbx+8]
0x1800068cb  mov     [rsp+278h+Arguments], r15; Arguments
0x1800068d0  mov     [rsp+278h+nSize], 100h; nSize
0x1800068d8  lea     rax, [rsp+278h+Buffer]
0x1800068dd  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800068e2  mov     r9d, 400h; dwLanguageId
0x1800068e8  mov     r8d, ebp; dwMessageId
0x1800068eb  xor     edx, edx; lpSource
0x1800068ed  mov     ecx, 1200h; dwFlags
0x1800068f2  call    cs:__imp_FormatMessageW
0x1800068f8  lea     rsi, [r14+rsi*2]
0x1800068fc  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006900  mov     rax, [rbx+88h]
0x180006907  mov     rcx, [rbx+80h]
0x18000690e  mov     rdx, rsi; unsigned __int16 *
0x180006911  test    r9, r9
0x180006914  jz      short loc_180006938
0x180006916  mov     [rsp+278h+Arguments], rax
0x18000691b  mov     qword ptr [rsp+278h+nSize], rcx
0x180006920  mov     eax, [rbx+40h]
0x180006923  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006927  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000692e  mov     rcx, r14; this
0x180006931  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006936  jmp     short loc_18000694F
0x180006938  mov     [rsp+278h+lpBuffer], rax
0x18000693d  mov     r9, rcx; unsigned __int16 *
0x180006940  lea     r8, aHsP; "%hs!%p: "
0x180006947  mov     rcx, r14; this
0x18000694a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000694f  mov     r14, rax
0x180006952  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006959  test    r9, r9
0x18000695c  jz      short loc_180006973
0x18000695e  lea     r8, aCallerP; "(caller: %p) "
0x180006965  mov     rdx, rsi; unsigned __int16 *
0x180006968  mov     rcx, rax; this
0x18000696b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006970  mov     r14, rax
0x180006973  call    cs:__imp_GetCurrentThreadId
0x180006979  lea     rcx, [rsp+278h+Buffer]
0x18000697e  mov     [rsp+278h+var_240], rcx
0x180006983  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006987  mov     [rsp+278h+nSize], eax
0x18000698b  mov     eax, [rbx+44h]
0x18000698e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006992  mov     r9, rdi; unsigned __int16 *
0x180006995  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000699c  mov     rdx, rsi; unsigned __int16 *
0x18000699f  mov     rcx, r14; this
0x1800069a2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800069a7  cmp     [rbx+18h], r15
0x1800069ab  jnz     short loc_1800069BD
0x1800069ad  cmp     [rbx+48h], r15
0x1800069b1  jnz     short loc_1800069BD
0x1800069b3  cmp     [rbx+30h], r15
0x1800069b7  jz      loc_180006A4D
0x1800069bd  lea     r8, asc_180034BB8; "    "
0x1800069c4  mov     rdx, rsi; unsigned __int16 *
0x1800069c7  mov     rcx, rax; this
0x1800069ca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800069cf  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800069d3  test    r9, r9
0x1800069d6  jz      short loc_1800069EA
0x1800069d8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800069df  mov     rdx, rsi; unsigned __int16 *
0x1800069e2  mov     rcx, rax; this
0x1800069e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800069ea  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800069ee  test    r9, r9
0x1800069f1  jz      short loc_180006A05
0x1800069f3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800069fa  mov     rdx, rsi; unsigned __int16 *
0x1800069fd  mov     rcx, rax; this
0x180006a00  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a05  mov     rcx, [rbx+28h]
0x180006a09  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006a0d  mov     rdx, rsi; unsigned __int16 *
0x180006a10  test    rcx, rcx
0x180006a13  jz      short loc_180006A2B
0x180006a15  mov     [rsp+278h+lpBuffer], rcx
0x180006a1a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006a21  mov     rcx, rax; this
0x180006a24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a29  jmp     short loc_180006A4D
0x180006a2b  mov     rcx, rax; this
0x180006a2e  test    r9, r9
0x180006a31  jz      short loc_180006A41
0x180006a33  lea     r8, aHs; "[%hs]\n"
0x180006a3a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a3f  jmp     short loc_180006A4D
0x180006a41  lea     r8, asc_180034C30; "\n"
0x180006a48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006a4d  xor     eax, eax
0x180006a4f  mov     rcx, [rsp+278h+var_38]
0x180006a57  xor     rcx, rsp; StackCookie
0x180006a5a  call    __security_check_cookie
0x180006a5f  mov     rbx, [rsp+278h+arg_18]
0x180006a67  add     rsp, 250h
0x180006a6e  pop     r15
0x180006a70  pop     r14
0x180006a72  pop     rdi
0x180006a73  pop     rsi
0x180006a74  pop     rbp
0x180006a75  retn
```
