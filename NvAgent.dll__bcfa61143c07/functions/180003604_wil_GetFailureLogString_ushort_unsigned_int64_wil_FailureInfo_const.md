# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003604`
- end: `0x1800038ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000226c`
- `0x1800024dc`
- `0x180003f64`
- `0x1800055f0`
- `0x180005824`

## callees

- `0x180001590`
- `0x180001f4a`
- `0x180003604`
- `0x180004264`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003736`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003736`

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
          v7 = (const char *)&qword_180008660;
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
0x180003604  mov     [rsp+arg_18], rbx
0x180003609  push    rbp
0x18000360a  push    rsi
0x18000360b  push    rdi
0x18000360c  push    r14
0x18000360e  push    r15
0x180003610  sub     rsp, 250h
0x180003617  mov     rax, cs:__security_cookie
0x18000361e  xor     rax, rsp
0x180003621  mov     [rsp+278h+var_38], rax
0x180003629  mov     rbx, r8
0x18000362c  mov     rsi, rdx
0x18000362f  mov     r14, rcx
0x180003632  xor     r15d, r15d
0x180003635  test    rdx, rdx
0x180003638  jz      loc_180003891
0x18000363e  test    rcx, rcx
0x180003641  jz      loc_180003891
0x180003647  mov     [rcx], r15w
0x18000364b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003652  test    rax, rax
0x180003655  jz      short loc_180003678
0x180003657  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000365e  jz      short loc_180003678
0x180003660  mov     r8, rdx
0x180003663  mov     rdx, rcx
0x180003666  mov     rcx, rbx
0x180003669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000366e  cmp     [r14], r15w
0x180003672  jnz     loc_180003891
0x180003678  mov     ecx, [rbx]
0x18000367a  mov     bpl, 8
0x18000367d  test    ecx, ecx
0x18000367f  jz      short loc_1800036CA
0x180003681  sub     ecx, 1
0x180003684  jz      short loc_1800036B2
0x180003686  sub     ecx, 1
0x180003689  jz      short loc_1800036A2
0x18000368b  cmp     ecx, 1
0x18000368e  jz      short loc_180003699
0x180003690  lea     rdi, qword_180008660
0x180003697  jmp     short loc_1800036D1
0x180003699  lea     rdi, aFailfast; "FailFast"
0x1800036a0  jmp     short loc_1800036D1
0x1800036a2  lea     rax, aLoghr; "LogHr"
0x1800036a9  lea     rdi, aLognt; "LogNt"
0x1800036b0  jmp     short loc_1800036C0
0x1800036b2  lea     rax, aReturnhr; "ReturnHr"
0x1800036b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800036c0  test    [rbx+4], bpl
0x1800036c4  cmovz   rdi, rax
0x1800036c8  jmp     short loc_1800036D1
0x1800036ca  lea     rdi, aException; "Exception"
0x1800036d1  xor     edx, edx; Val
0x1800036d3  mov     r8d, 200h; Size
0x1800036d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800036de  call    memset_0
0x1800036e3  test    [rbx+4], bpl
0x1800036e7  jz      short loc_18000370C
0x1800036e9  mov     ebp, [rbx+0Ch]
0x1800036ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800036f3  test    rax, rax
0x1800036f6  jz      short loc_18000373C
0x1800036f8  mov     r8d, 100h
0x1800036fe  lea     rdx, [rsp+278h+Buffer]
0x180003703  mov     ecx, ebp
0x180003705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370a  jmp     short loc_18000373C
0x18000370c  mov     ebp, [rbx+8]
0x18000370f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003714  mov     [rsp+278h+nSize], 100h; nSize
0x18000371c  lea     rax, [rsp+278h+Buffer]
0x180003721  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003726  mov     r9d, 400h; dwLanguageId
0x18000372c  mov     r8d, ebp; dwMessageId
0x18000372f  xor     edx, edx; lpSource
0x180003731  mov     ecx, 1200h; dwFlags
0x180003736  call    cs:__imp_FormatMessageW
0x18000373c  lea     rsi, [r14+rsi*2]
0x180003740  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003744  mov     rax, [rbx+88h]
0x18000374b  mov     rcx, [rbx+80h]
0x180003752  mov     rdx, rsi; unsigned __int16 *
0x180003755  test    r9, r9
0x180003758  jz      short loc_18000377C
0x18000375a  mov     [rsp+278h+Arguments], rax
0x18000375f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003764  mov     eax, [rbx+40h]
0x180003767  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000376b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003772  mov     rcx, r14; this
0x180003775  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000377a  jmp     short loc_180003793
0x18000377c  mov     [rsp+278h+lpBuffer], rax
0x180003781  mov     r9, rcx; unsigned __int16 *
0x180003784  lea     r8, aHsP; "%hs!%p: "
0x18000378b  mov     rcx, r14; this
0x18000378e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003793  mov     r14, rax
0x180003796  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000379d  test    r9, r9
0x1800037a0  jz      short loc_1800037B7
0x1800037a2  lea     r8, aCallerP; "(caller: %p) "
0x1800037a9  mov     rdx, rsi; unsigned __int16 *
0x1800037ac  mov     rcx, rax; this
0x1800037af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800037b4  mov     r14, rax
0x1800037b7  call    cs:__imp_GetCurrentThreadId
0x1800037bd  lea     rcx, [rsp+278h+Buffer]
0x1800037c2  mov     [rsp+278h+var_240], rcx
0x1800037c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800037cb  mov     [rsp+278h+nSize], eax
0x1800037cf  mov     eax, [rbx+44h]
0x1800037d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800037d6  mov     r9, rdi; unsigned __int16 *
0x1800037d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800037e0  mov     rdx, rsi; unsigned __int16 *
0x1800037e3  mov     rcx, r14; this
0x1800037e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800037eb  cmp     [rbx+18h], r15
0x1800037ef  jnz     short loc_180003801
0x1800037f1  cmp     [rbx+48h], r15
0x1800037f5  jnz     short loc_180003801
0x1800037f7  cmp     [rbx+30h], r15
0x1800037fb  jz      loc_180003891
0x180003801  lea     r8, asc_180008768; "    "
0x180003808  mov     rdx, rsi; unsigned __int16 *
0x18000380b  mov     rcx, rax; this
0x18000380e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003813  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003817  test    r9, r9
0x18000381a  jz      short loc_18000382E
0x18000381c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003823  mov     rdx, rsi; unsigned __int16 *
0x180003826  mov     rcx, rax; this
0x180003829  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000382e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003832  test    r9, r9
0x180003835  jz      short loc_180003849
0x180003837  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000383e  mov     rdx, rsi; unsigned __int16 *
0x180003841  mov     rcx, rax; this
0x180003844  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003849  mov     rcx, [rbx+28h]
0x18000384d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003851  mov     rdx, rsi; unsigned __int16 *
0x180003854  test    rcx, rcx
0x180003857  jz      short loc_18000386F
0x180003859  mov     [rsp+278h+lpBuffer], rcx
0x18000385e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003865  mov     rcx, rax; this
0x180003868  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000386d  jmp     short loc_180003891
0x18000386f  mov     rcx, rax; this
0x180003872  test    r9, r9
0x180003875  jz      short loc_180003885
0x180003877  lea     r8, aHs; "[%hs]\n"
0x18000387e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003883  jmp     short loc_180003891
0x180003885  lea     r8, asc_1800087E0; "\n"
0x18000388c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003891  xor     eax, eax
0x180003893  mov     rcx, [rsp+278h+var_38]
0x18000389b  xor     rcx, rsp; StackCookie
0x18000389e  call    __security_check_cookie
0x1800038a3  mov     rbx, [rsp+278h+arg_18]
0x1800038ab  add     rsp, 250h
0x1800038b2  pop     r15
0x1800038b4  pop     r14
0x1800038b6  pop     rdi
0x1800038b7  pop     rsi
0x1800038b8  pop     rbp
0x1800038b9  retn
```
