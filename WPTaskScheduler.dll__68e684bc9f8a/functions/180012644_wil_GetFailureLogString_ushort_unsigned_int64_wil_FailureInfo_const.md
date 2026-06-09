# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180012644`
- end: `0x1800128fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180010b1c`
- `0x180010d84`
- `0x1800131b0`
- `0x180016e10`

## callees

- `0x180012644`
- `0x1800134b0`
- `0x180020c02`
- `0x180020c30`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800127f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800127f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180012776`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180012776`

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
          v7 = (const char *)&qword_180028628;
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
0x180012644  mov     [rsp+arg_18], rbx
0x180012649  push    rbp
0x18001264a  push    rsi
0x18001264b  push    rdi
0x18001264c  push    r14
0x18001264e  push    r15
0x180012650  sub     rsp, 250h
0x180012657  mov     rax, cs:__security_cookie
0x18001265e  xor     rax, rsp
0x180012661  mov     [rsp+278h+var_38], rax
0x180012669  mov     rbx, r8
0x18001266c  mov     rsi, rdx
0x18001266f  mov     r14, rcx
0x180012672  xor     r15d, r15d
0x180012675  test    rdx, rdx
0x180012678  jz      loc_1800128D1
0x18001267e  test    rcx, rcx
0x180012681  jz      loc_1800128D1
0x180012687  mov     [rcx], r15w
0x18001268b  mov     rax, cs:g_pfnResultLoggingCallback
0x180012692  test    rax, rax
0x180012695  jz      short loc_1800126B8
0x180012697  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001269e  jz      short loc_1800126B8
0x1800126a0  mov     r8, rdx
0x1800126a3  mov     rdx, rcx
0x1800126a6  mov     rcx, rbx
0x1800126a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126ae  cmp     [r14], r15w
0x1800126b2  jnz     loc_1800128D1
0x1800126b8  mov     ecx, [rbx]
0x1800126ba  mov     bpl, 8
0x1800126bd  test    ecx, ecx
0x1800126bf  jz      short loc_18001270A
0x1800126c1  sub     ecx, 1
0x1800126c4  jz      short loc_1800126F2
0x1800126c6  sub     ecx, 1
0x1800126c9  jz      short loc_1800126E2
0x1800126cb  cmp     ecx, 1
0x1800126ce  jz      short loc_1800126D9
0x1800126d0  lea     rdi, qword_180028628
0x1800126d7  jmp     short loc_180012711
0x1800126d9  lea     rdi, aFailfast; "FailFast"
0x1800126e0  jmp     short loc_180012711
0x1800126e2  lea     rax, aLoghr; "LogHr"
0x1800126e9  lea     rdi, aLognt; "LogNt"
0x1800126f0  jmp     short loc_180012700
0x1800126f2  lea     rax, aReturnhr; "ReturnHr"
0x1800126f9  lea     rdi, aReturnnt; "ReturnNt"
0x180012700  test    [rbx+4], bpl
0x180012704  cmovz   rdi, rax
0x180012708  jmp     short loc_180012711
0x18001270a  lea     rdi, aException; "Exception"
0x180012711  xor     edx, edx; Val
0x180012713  mov     r8d, 200h; Size
0x180012719  lea     rcx, [rsp+278h+Buffer]; void *
0x18001271e  call    memset_0
0x180012723  test    [rbx+4], bpl
0x180012727  jz      short loc_18001274C
0x180012729  mov     ebp, [rbx+0Ch]
0x18001272c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180012733  test    rax, rax
0x180012736  jz      short loc_18001277C
0x180012738  mov     r8d, 100h
0x18001273e  lea     rdx, [rsp+278h+Buffer]
0x180012743  mov     ecx, ebp
0x180012745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001274a  jmp     short loc_18001277C
0x18001274c  mov     ebp, [rbx+8]
0x18001274f  mov     [rsp+278h+Arguments], r15; Arguments
0x180012754  mov     [rsp+278h+nSize], 100h; nSize
0x18001275c  lea     rax, [rsp+278h+Buffer]
0x180012761  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180012766  mov     r9d, 400h; dwLanguageId
0x18001276c  mov     r8d, ebp; dwMessageId
0x18001276f  xor     edx, edx; lpSource
0x180012771  mov     ecx, 1200h; dwFlags
0x180012776  call    cs:__imp_FormatMessageW
0x18001277c  lea     rsi, [r14+rsi*2]
0x180012780  mov     r9, [rbx+38h]; unsigned __int16 *
0x180012784  mov     rax, [rbx+88h]
0x18001278b  mov     rcx, [rbx+80h]
0x180012792  mov     rdx, rsi; unsigned __int16 *
0x180012795  test    r9, r9
0x180012798  jz      short loc_1800127BC
0x18001279a  mov     [rsp+278h+Arguments], rax
0x18001279f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800127a4  mov     eax, [rbx+40h]
0x1800127a7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800127ab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800127b2  mov     rcx, r14; this
0x1800127b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800127ba  jmp     short loc_1800127D3
0x1800127bc  mov     [rsp+278h+lpBuffer], rax
0x1800127c1  mov     r9, rcx; unsigned __int16 *
0x1800127c4  lea     r8, aHsP; "%hs!%p: "
0x1800127cb  mov     rcx, r14; this
0x1800127ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800127d3  mov     r14, rax
0x1800127d6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800127dd  test    r9, r9
0x1800127e0  jz      short loc_1800127F7
0x1800127e2  lea     r8, aCallerP; "(caller: %p) "
0x1800127e9  mov     rdx, rsi; unsigned __int16 *
0x1800127ec  mov     rcx, rax; this
0x1800127ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800127f4  mov     r14, rax
0x1800127f7  call    cs:__imp_GetCurrentThreadId
0x1800127fd  lea     rcx, [rsp+278h+Buffer]
0x180012802  mov     [rsp+278h+var_240], rcx
0x180012807  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001280b  mov     [rsp+278h+nSize], eax
0x18001280f  mov     eax, [rbx+44h]
0x180012812  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180012816  mov     r9, rdi; unsigned __int16 *
0x180012819  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180012820  mov     rdx, rsi; unsigned __int16 *
0x180012823  mov     rcx, r14; this
0x180012826  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001282b  cmp     [rbx+18h], r15
0x18001282f  jnz     short loc_180012841
0x180012831  cmp     [rbx+48h], r15
0x180012835  jnz     short loc_180012841
0x180012837  cmp     [rbx+30h], r15
0x18001283b  jz      loc_1800128D1
0x180012841  lea     r8, asc_180028718; "    "
0x180012848  mov     rdx, rsi; unsigned __int16 *
0x18001284b  mov     rcx, rax; this
0x18001284e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012853  mov     r9, [rbx+18h]; unsigned __int16 *
0x180012857  test    r9, r9
0x18001285a  jz      short loc_18001286E
0x18001285c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180012863  mov     rdx, rsi; unsigned __int16 *
0x180012866  mov     rcx, rax; this
0x180012869  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001286e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180012872  test    r9, r9
0x180012875  jz      short loc_180012889
0x180012877  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001287e  mov     rdx, rsi; unsigned __int16 *
0x180012881  mov     rcx, rax; this
0x180012884  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180012889  mov     rcx, [rbx+28h]
0x18001288d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180012891  mov     rdx, rsi; unsigned __int16 *
0x180012894  test    rcx, rcx
0x180012897  jz      short loc_1800128AF
0x180012899  mov     [rsp+278h+lpBuffer], rcx
0x18001289e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800128a5  mov     rcx, rax; this
0x1800128a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800128ad  jmp     short loc_1800128D1
0x1800128af  mov     rcx, rax; this
0x1800128b2  test    r9, r9
0x1800128b5  jz      short loc_1800128C5
0x1800128b7  lea     r8, aHs; "[%hs]\n"
0x1800128be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800128c3  jmp     short loc_1800128D1
0x1800128c5  lea     r8, asc_180028790; "\n"
0x1800128cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800128d1  xor     eax, eax
0x1800128d3  mov     rcx, [rsp+278h+var_38]
0x1800128db  xor     rcx, rsp; StackCookie
0x1800128de  call    __security_check_cookie
0x1800128e3  mov     rbx, [rsp+278h+arg_18]
0x1800128eb  add     rsp, 250h
0x1800128f2  pop     r15
0x1800128f4  pop     r14
0x1800128f6  pop     rdi
0x1800128f7  pop     rsi
0x1800128f8  pop     rbp
0x1800128f9  retn
```
