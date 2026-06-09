# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006674`
- end: `0x18000692a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800073a0`
- `0x180007a30`
- `0x18000b490`

## callees

- `0x1800021d0`
- `0x180002c18`
- `0x180006674`
- `0x18000769c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800067a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800067a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006827`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006827`

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
          v7 = (const char *)&word_180026662;
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
0x180006674  mov     [rsp+arg_18], rbx
0x180006679  push    rbp
0x18000667a  push    rsi
0x18000667b  push    rdi
0x18000667c  push    r14
0x18000667e  push    r15
0x180006680  sub     rsp, 250h
0x180006687  mov     rax, cs:__security_cookie
0x18000668e  xor     rax, rsp
0x180006691  mov     [rsp+278h+var_38], rax
0x180006699  mov     rbx, r8
0x18000669c  mov     rsi, rdx
0x18000669f  mov     r14, rcx
0x1800066a2  xor     r15d, r15d
0x1800066a5  test    rdx, rdx
0x1800066a8  jz      loc_180006901
0x1800066ae  test    rcx, rcx
0x1800066b1  jz      loc_180006901
0x1800066b7  mov     [rcx], r15w
0x1800066bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800066c2  test    rax, rax
0x1800066c5  jz      short loc_1800066E8
0x1800066c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800066ce  jz      short loc_1800066E8
0x1800066d0  mov     r8, rdx
0x1800066d3  mov     rdx, rcx
0x1800066d6  mov     rcx, rbx
0x1800066d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066de  cmp     [r14], r15w
0x1800066e2  jnz     loc_180006901
0x1800066e8  mov     ecx, [rbx]
0x1800066ea  mov     bpl, 8
0x1800066ed  test    ecx, ecx
0x1800066ef  jz      short loc_18000673A
0x1800066f1  sub     ecx, 1
0x1800066f4  jz      short loc_180006722
0x1800066f6  sub     ecx, 1
0x1800066f9  jz      short loc_180006712
0x1800066fb  cmp     ecx, 1
0x1800066fe  jz      short loc_180006709
0x180006700  lea     rdi, word_180026662
0x180006707  jmp     short loc_180006741
0x180006709  lea     rdi, aFailfast; "FailFast"
0x180006710  jmp     short loc_180006741
0x180006712  lea     rax, aLoghr; "LogHr"
0x180006719  lea     rdi, aLognt; "LogNt"
0x180006720  jmp     short loc_180006730
0x180006722  lea     rax, aReturnhr; "ReturnHr"
0x180006729  lea     rdi, aReturnnt; "ReturnNt"
0x180006730  test    [rbx+4], bpl
0x180006734  cmovz   rdi, rax
0x180006738  jmp     short loc_180006741
0x18000673a  lea     rdi, aException; "Exception"
0x180006741  xor     edx, edx; Val
0x180006743  mov     r8d, 200h; Size
0x180006749  lea     rcx, [rsp+278h+Buffer]; void *
0x18000674e  call    memset_0
0x180006753  test    [rbx+4], bpl
0x180006757  jz      short loc_18000677C
0x180006759  mov     ebp, [rbx+0Ch]
0x18000675c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006763  test    rax, rax
0x180006766  jz      short loc_1800067AC
0x180006768  mov     r8d, 100h
0x18000676e  lea     rdx, [rsp+278h+Buffer]
0x180006773  mov     ecx, ebp
0x180006775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000677a  jmp     short loc_1800067AC
0x18000677c  mov     ebp, [rbx+8]
0x18000677f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006784  mov     [rsp+278h+nSize], 100h; nSize
0x18000678c  lea     rax, [rsp+278h+Buffer]
0x180006791  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006796  mov     r9d, 400h; dwLanguageId
0x18000679c  mov     r8d, ebp; dwMessageId
0x18000679f  xor     edx, edx; lpSource
0x1800067a1  mov     ecx, 1200h; dwFlags
0x1800067a6  call    cs:__imp_FormatMessageW
0x1800067ac  lea     rsi, [r14+rsi*2]
0x1800067b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800067b4  mov     rax, [rbx+88h]
0x1800067bb  mov     rcx, [rbx+80h]
0x1800067c2  mov     rdx, rsi; unsigned __int16 *
0x1800067c5  test    r9, r9
0x1800067c8  jz      short loc_1800067EC
0x1800067ca  mov     [rsp+278h+Arguments], rax
0x1800067cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800067d4  mov     eax, [rbx+40h]
0x1800067d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800067db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800067e2  mov     rcx, r14; this
0x1800067e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800067ea  jmp     short loc_180006803
0x1800067ec  mov     [rsp+278h+lpBuffer], rax
0x1800067f1  mov     r9, rcx; unsigned __int16 *
0x1800067f4  lea     r8, aHsP; "%hs!%p: "
0x1800067fb  mov     rcx, r14; this
0x1800067fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006803  mov     r14, rax
0x180006806  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000680d  test    r9, r9
0x180006810  jz      short loc_180006827
0x180006812  lea     r8, aCallerP; "(caller: %p) "
0x180006819  mov     rdx, rsi; unsigned __int16 *
0x18000681c  mov     rcx, rax; this
0x18000681f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006824  mov     r14, rax
0x180006827  call    cs:__imp_GetCurrentThreadId
0x18000682d  lea     rcx, [rsp+278h+Buffer]
0x180006832  mov     [rsp+278h+var_240], rcx
0x180006837  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000683b  mov     [rsp+278h+nSize], eax
0x18000683f  mov     eax, [rbx+44h]
0x180006842  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006846  mov     r9, rdi; unsigned __int16 *
0x180006849  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006850  mov     rdx, rsi; unsigned __int16 *
0x180006853  mov     rcx, r14; this
0x180006856  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000685b  cmp     [rbx+18h], r15
0x18000685f  jnz     short loc_180006871
0x180006861  cmp     [rbx+48h], r15
0x180006865  jnz     short loc_180006871
0x180006867  cmp     [rbx+30h], r15
0x18000686b  jz      loc_180006901
0x180006871  lea     r8, asc_180026198; "    "
0x180006878  mov     rdx, rsi; unsigned __int16 *
0x18000687b  mov     rcx, rax; this
0x18000687e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006883  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006887  test    r9, r9
0x18000688a  jz      short loc_18000689E
0x18000688c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006893  mov     rdx, rsi; unsigned __int16 *
0x180006896  mov     rcx, rax; this
0x180006899  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000689e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800068a2  test    r9, r9
0x1800068a5  jz      short loc_1800068B9
0x1800068a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800068ae  mov     rdx, rsi; unsigned __int16 *
0x1800068b1  mov     rcx, rax; this
0x1800068b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800068b9  mov     rcx, [rbx+28h]
0x1800068bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800068c1  mov     rdx, rsi; unsigned __int16 *
0x1800068c4  test    rcx, rcx
0x1800068c7  jz      short loc_1800068DF
0x1800068c9  mov     [rsp+278h+lpBuffer], rcx
0x1800068ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800068d5  mov     rcx, rax; this
0x1800068d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800068dd  jmp     short loc_180006901
0x1800068df  mov     rcx, rax; this
0x1800068e2  test    r9, r9
0x1800068e5  jz      short loc_1800068F5
0x1800068e7  lea     r8, aHs; "[%hs]\n"
0x1800068ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800068f3  jmp     short loc_180006901
0x1800068f5  lea     r8, asc_180026210; "\n"
0x1800068fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006901  xor     eax, eax
0x180006903  mov     rcx, [rsp+278h+var_38]
0x18000690b  xor     rcx, rsp; StackCookie
0x18000690e  call    __security_check_cookie
0x180006913  mov     rbx, [rsp+278h+arg_18]
0x18000691b  add     rsp, 250h
0x180006922  pop     r15
0x180006924  pop     r14
0x180006926  pop     rdi
0x180006927  pop     rsi
0x180006928  pop     rbp
0x180006929  retn
```
