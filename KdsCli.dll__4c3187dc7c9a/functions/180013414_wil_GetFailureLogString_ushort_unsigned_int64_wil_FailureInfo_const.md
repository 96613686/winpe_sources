# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180013414`
- end: `0x1800136ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180011500`
- `0x180011768`
- `0x180013e58`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x180013414`
- `0x180014158`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800135c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800135c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013546`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013546`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&dword_18001E044;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013414  mov     [rsp+arg_18], rbx
0x180013419  push    rbp
0x18001341a  push    rsi
0x18001341b  push    rdi
0x18001341c  push    r14
0x18001341e  push    r15
0x180013420  sub     rsp, 250h
0x180013427  mov     rax, cs:__security_cookie
0x18001342e  xor     rax, rsp
0x180013431  mov     [rsp+278h+var_38], rax
0x180013439  xor     r15d, r15d
0x18001343c  mov     rbx, r8
0x18001343f  mov     rsi, rdx
0x180013442  mov     r14, rcx
0x180013445  test    rdx, rdx
0x180013448  jz      loc_1800136A1
0x18001344e  test    rcx, rcx
0x180013451  jz      loc_1800136A1
0x180013457  mov     rax, cs:g_pfnResultLoggingCallback
0x18001345e  mov     [rcx], r15w
0x180013462  test    rax, rax
0x180013465  jz      short loc_180013488
0x180013467  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001346e  jz      short loc_180013488
0x180013470  mov     r8, rdx
0x180013473  mov     rdx, rcx
0x180013476  mov     rcx, rbx
0x180013479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001347e  cmp     [r14], r15w
0x180013482  jnz     loc_1800136A1
0x180013488  mov     ecx, [rbx]
0x18001348a  mov     bpl, 8
0x18001348d  test    ecx, ecx
0x18001348f  jz      short loc_1800134DA
0x180013491  sub     ecx, 1
0x180013494  jz      short loc_1800134C2
0x180013496  sub     ecx, 1
0x180013499  jz      short loc_1800134B2
0x18001349b  cmp     ecx, 1
0x18001349e  jz      short loc_1800134A9
0x1800134a0  lea     rdi, dword_18001E044
0x1800134a7  jmp     short loc_1800134E1
0x1800134a9  lea     rdi, aFailfast; "FailFast"
0x1800134b0  jmp     short loc_1800134E1
0x1800134b2  lea     rax, aLoghr; "LogHr"
0x1800134b9  lea     rdi, aLognt; "LogNt"
0x1800134c0  jmp     short loc_1800134D0
0x1800134c2  lea     rax, aReturnhr; "ReturnHr"
0x1800134c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800134d0  test    [rbx+4], bpl
0x1800134d4  cmovz   rdi, rax
0x1800134d8  jmp     short loc_1800134E1
0x1800134da  lea     rdi, aException; "Exception"
0x1800134e1  xor     edx, edx; Val
0x1800134e3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800134e8  mov     r8d, 200h; Size
0x1800134ee  call    memset_0
0x1800134f3  test    [rbx+4], bpl
0x1800134f7  jz      short loc_18001351C
0x1800134f9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180013500  mov     ebp, [rbx+0Ch]
0x180013503  test    rax, rax
0x180013506  jz      short loc_18001354C
0x180013508  mov     r8d, 100h
0x18001350e  lea     rdx, [rsp+278h+Buffer]
0x180013513  mov     ecx, ebp
0x180013515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001351a  jmp     short loc_18001354C
0x18001351c  mov     ebp, [rbx+8]
0x18001351f  lea     rax, [rsp+278h+Buffer]
0x180013524  mov     [rsp+278h+Arguments], r15; Arguments
0x180013529  mov     r8d, ebp; dwMessageId
0x18001352c  mov     [rsp+278h+nSize], 100h; nSize
0x180013534  mov     r9d, 400h; dwLanguageId
0x18001353a  xor     edx, edx; lpSource
0x18001353c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180013541  mov     ecx, 1200h; dwFlags
0x180013546  call    cs:__imp_FormatMessageW
0x18001354c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180013550  lea     rsi, [r14+rsi*2]
0x180013554  mov     rax, [rbx+88h]
0x18001355b  mov     rdx, rsi; unsigned __int16 *
0x18001355e  mov     rcx, [rbx+80h]
0x180013565  test    r9, r9
0x180013568  jz      short loc_18001358C
0x18001356a  mov     [rsp+278h+Arguments], rax
0x18001356f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180013576  mov     eax, [rbx+40h]
0x180013579  mov     qword ptr [rsp+278h+nSize], rcx
0x18001357e  mov     rcx, r14; this
0x180013581  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180013585  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001358a  jmp     short loc_1800135A3
0x18001358c  mov     r9, rcx; unsigned __int16 *
0x18001358f  mov     [rsp+278h+lpBuffer], rax
0x180013594  mov     rcx, r14; this
0x180013597  lea     r8, aHsP; "%hs!%p: "
0x18001359e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800135a3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800135aa  mov     r14, rax
0x1800135ad  test    r9, r9
0x1800135b0  jz      short loc_1800135C7
0x1800135b2  lea     r8, aCallerP; "(caller: %p) "
0x1800135b9  mov     rdx, rsi; unsigned __int16 *
0x1800135bc  mov     rcx, rax; this
0x1800135bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800135c4  mov     r14, rax
0x1800135c7  call    cs:__imp_GetCurrentThreadId
0x1800135cd  lea     rcx, [rsp+278h+Buffer]
0x1800135d2  mov     r9, rdi; unsigned __int16 *
0x1800135d5  mov     [rsp+278h+var_240], rcx
0x1800135da  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800135e1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800135e5  mov     rdx, rsi; unsigned __int16 *
0x1800135e8  mov     [rsp+278h+nSize], eax
0x1800135ec  mov     rcx, r14; this
0x1800135ef  mov     eax, [rbx+44h]
0x1800135f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800135f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800135fb  cmp     [rbx+18h], r15
0x1800135ff  jnz     short loc_180013611
0x180013601  cmp     [rbx+48h], r15
0x180013605  jnz     short loc_180013611
0x180013607  cmp     [rbx+30h], r15
0x18001360b  jz      loc_1800136A1
0x180013611  lea     r8, asc_18001E130; "    "
0x180013618  mov     rdx, rsi; unsigned __int16 *
0x18001361b  mov     rcx, rax; this
0x18001361e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013623  mov     r9, [rbx+18h]; unsigned __int16 *
0x180013627  test    r9, r9
0x18001362a  jz      short loc_18001363E
0x18001362c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180013633  mov     rdx, rsi; unsigned __int16 *
0x180013636  mov     rcx, rax; this
0x180013639  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001363e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180013642  test    r9, r9
0x180013645  jz      short loc_180013659
0x180013647  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001364e  mov     rdx, rsi; unsigned __int16 *
0x180013651  mov     rcx, rax; this
0x180013654  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013659  mov     rcx, [rbx+28h]
0x18001365d  mov     rdx, rsi; unsigned __int16 *
0x180013660  mov     r9, [rbx+30h]; unsigned __int16 *
0x180013664  test    rcx, rcx
0x180013667  jz      short loc_18001367F
0x180013669  mov     [rsp+278h+lpBuffer], rcx
0x18001366e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180013675  mov     rcx, rax; this
0x180013678  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001367d  jmp     short loc_1800136A1
0x18001367f  mov     rcx, rax; this
0x180013682  test    r9, r9
0x180013685  jz      short loc_180013695
0x180013687  lea     r8, aHs; "[%hs]\n"
0x18001368e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013693  jmp     short loc_1800136A1
0x180013695  lea     r8, asc_18001E1A8; "\n"
0x18001369c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800136a1  xor     eax, eax
0x1800136a3  mov     rcx, [rsp+278h+var_38]
0x1800136ab  xor     rcx, rsp; StackCookie
0x1800136ae  call    __security_check_cookie
0x1800136b3  mov     rbx, [rsp+278h+arg_18]
0x1800136bb  add     rsp, 250h
0x1800136c2  pop     r15
0x1800136c4  pop     r14
0x1800136c6  pop     rdi
0x1800136c7  pop     rsi
0x1800136c8  pop     rbp
0x1800136c9  retn
```
