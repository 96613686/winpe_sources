# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180041670`
- end: `0x180041926`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800259f0`
- `0x180041e14`
- `0x180042a00`

## callees

- `0x18003e920`
- `0x18003f7a4`
- `0x180041670`
- `0x180041c94`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041823`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041823`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800417a2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800417a2`

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
          v7 = (const char *)&qword_18006DC08;
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
0x180041670  mov     [rsp+arg_18], rbx
0x180041675  push    rbp
0x180041676  push    rsi
0x180041677  push    rdi
0x180041678  push    r14
0x18004167a  push    r15
0x18004167c  sub     rsp, 250h
0x180041683  mov     rax, cs:__security_cookie
0x18004168a  xor     rax, rsp
0x18004168d  mov     [rsp+278h+var_38], rax
0x180041695  mov     rbx, r8
0x180041698  mov     rsi, rdx
0x18004169b  mov     r14, rcx
0x18004169e  xor     r15d, r15d
0x1800416a1  test    rdx, rdx
0x1800416a4  jz      loc_1800418FD
0x1800416aa  test    rcx, rcx
0x1800416ad  jz      loc_1800418FD
0x1800416b3  mov     [rcx], r15w
0x1800416b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800416be  test    rax, rax
0x1800416c1  jz      short loc_1800416E4
0x1800416c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800416ca  jz      short loc_1800416E4
0x1800416cc  mov     r8, rdx
0x1800416cf  mov     rdx, rcx
0x1800416d2  mov     rcx, rbx
0x1800416d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416da  cmp     [r14], r15w
0x1800416de  jnz     loc_1800418FD
0x1800416e4  mov     ecx, [rbx]
0x1800416e6  mov     bpl, 8
0x1800416e9  test    ecx, ecx
0x1800416eb  jz      short loc_180041736
0x1800416ed  sub     ecx, 1
0x1800416f0  jz      short loc_18004171E
0x1800416f2  sub     ecx, 1
0x1800416f5  jz      short loc_18004170E
0x1800416f7  cmp     ecx, 1
0x1800416fa  jz      short loc_180041705
0x1800416fc  lea     rdi, qword_18006DC08
0x180041703  jmp     short loc_18004173D
0x180041705  lea     rdi, aFailfast; "FailFast"
0x18004170c  jmp     short loc_18004173D
0x18004170e  lea     rax, aLoghr; "LogHr"
0x180041715  lea     rdi, aLognt; "LogNt"
0x18004171c  jmp     short loc_18004172C
0x18004171e  lea     rax, aReturnhr; "ReturnHr"
0x180041725  lea     rdi, aReturnnt; "ReturnNt"
0x18004172c  test    [rbx+4], bpl
0x180041730  cmovz   rdi, rax
0x180041734  jmp     short loc_18004173D
0x180041736  lea     rdi, aException; "Exception"
0x18004173d  xor     edx, edx; Val
0x18004173f  mov     r8d, 200h; Size
0x180041745  lea     rcx, [rsp+278h+Buffer]; void *
0x18004174a  call    memset_0
0x18004174f  test    [rbx+4], bpl
0x180041753  jz      short loc_180041778
0x180041755  mov     ebp, [rbx+0Ch]
0x180041758  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18004175f  test    rax, rax
0x180041762  jz      short loc_1800417A8
0x180041764  mov     r8d, 100h
0x18004176a  lea     rdx, [rsp+278h+Buffer]
0x18004176f  mov     ecx, ebp
0x180041771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041776  jmp     short loc_1800417A8
0x180041778  mov     ebp, [rbx+8]
0x18004177b  mov     [rsp+278h+Arguments], r15; Arguments
0x180041780  mov     [rsp+278h+nSize], 100h; nSize
0x180041788  lea     rax, [rsp+278h+Buffer]
0x18004178d  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180041792  mov     r9d, 400h; dwLanguageId
0x180041798  mov     r8d, ebp; dwMessageId
0x18004179b  xor     edx, edx; lpSource
0x18004179d  mov     ecx, 1200h; dwFlags
0x1800417a2  call    cs:__imp_FormatMessageW
0x1800417a8  lea     rsi, [r14+rsi*2]
0x1800417ac  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800417b0  mov     rax, [rbx+88h]
0x1800417b7  mov     rcx, [rbx+80h]
0x1800417be  mov     rdx, rsi; unsigned __int16 *
0x1800417c1  test    r9, r9
0x1800417c4  jz      short loc_1800417E8
0x1800417c6  mov     [rsp+278h+Arguments], rax
0x1800417cb  mov     qword ptr [rsp+278h+nSize], rcx
0x1800417d0  mov     eax, [rbx+40h]
0x1800417d3  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800417d7  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800417de  mov     rcx, r14; this
0x1800417e1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800417e6  jmp     short loc_1800417FF
0x1800417e8  mov     [rsp+278h+lpBuffer], rax
0x1800417ed  mov     r9, rcx; unsigned __int16 *
0x1800417f0  lea     r8, aHsP; "%hs!%p: "
0x1800417f7  mov     rcx, r14; this
0x1800417fa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800417ff  mov     r14, rax
0x180041802  mov     r9, [rbx+90h]; unsigned __int16 *
0x180041809  test    r9, r9
0x18004180c  jz      short loc_180041823
0x18004180e  lea     r8, aCallerP; "(caller: %p) "
0x180041815  mov     rdx, rsi; unsigned __int16 *
0x180041818  mov     rcx, rax; this
0x18004181b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041820  mov     r14, rax
0x180041823  call    cs:__imp_GetCurrentThreadId
0x180041829  lea     rcx, [rsp+278h+Buffer]
0x18004182e  mov     [rsp+278h+var_240], rcx
0x180041833  mov     dword ptr [rsp+278h+Arguments], ebp
0x180041837  mov     [rsp+278h+nSize], eax
0x18004183b  mov     eax, [rbx+44h]
0x18004183e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180041842  mov     r9, rdi; unsigned __int16 *
0x180041845  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18004184c  mov     rdx, rsi; unsigned __int16 *
0x18004184f  mov     rcx, r14; this
0x180041852  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180041857  cmp     [rbx+18h], r15
0x18004185b  jnz     short loc_18004186D
0x18004185d  cmp     [rbx+48h], r15
0x180041861  jnz     short loc_18004186D
0x180041863  cmp     [rbx+30h], r15
0x180041867  jz      loc_1800418FD
0x18004186d  lea     r8, asc_18006F400; "    "
0x180041874  mov     rdx, rsi; unsigned __int16 *
0x180041877  mov     rcx, rax; this
0x18004187a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004187f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180041883  test    r9, r9
0x180041886  jz      short loc_18004189A
0x180041888  lea     r8, aMsgWs; "Msg:[%ws] "
0x18004188f  mov     rdx, rsi; unsigned __int16 *
0x180041892  mov     rcx, rax; this
0x180041895  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004189a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18004189e  test    r9, r9
0x1800418a1  jz      short loc_1800418B5
0x1800418a3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800418aa  mov     rdx, rsi; unsigned __int16 *
0x1800418ad  mov     rcx, rax; this
0x1800418b0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800418b5  mov     rcx, [rbx+28h]
0x1800418b9  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800418bd  mov     rdx, rsi; unsigned __int16 *
0x1800418c0  test    rcx, rcx
0x1800418c3  jz      short loc_1800418DB
0x1800418c5  mov     [rsp+278h+lpBuffer], rcx
0x1800418ca  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800418d1  mov     rcx, rax; this
0x1800418d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800418d9  jmp     short loc_1800418FD
0x1800418db  mov     rcx, rax; this
0x1800418de  test    r9, r9
0x1800418e1  jz      short loc_1800418F1
0x1800418e3  lea     r8, aHs; "[%hs]\n"
0x1800418ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800418ef  jmp     short loc_1800418FD
0x1800418f1  lea     r8, asc_18006F478; "\n"
0x1800418f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800418fd  xor     eax, eax
0x1800418ff  mov     rcx, [rsp+278h+var_38]
0x180041907  xor     rcx, rsp; StackCookie
0x18004190a  call    __security_check_cookie
0x18004190f  mov     rbx, [rsp+278h+arg_18]
0x180041917  add     rsp, 250h
0x18004191e  pop     r15
0x180041920  pop     r14
0x180041922  pop     rdi
0x180041923  pop     rsi
0x180041924  pop     rbp
0x180041925  retn
```
