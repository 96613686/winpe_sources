# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180024144`
- end: `0x1800243fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800236a0`
- `0x180024730`
- `0x18004b9c0`

## callees

- `0x180024144`
- `0x180024a34`
- `0x18004c98a`
- `0x18004c9d0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800242f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800242f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180024276`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180024276`

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
          v8 = (const char *)&byte_18005188D;
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
0x180024144  mov     [rsp+arg_18], rbx
0x180024149  push    rbp
0x18002414a  push    rsi
0x18002414b  push    rdi
0x18002414c  push    r14
0x18002414e  push    r15
0x180024150  sub     rsp, 250h
0x180024157  mov     rax, cs:__security_cookie
0x18002415e  xor     rax, rsp
0x180024161  mov     [rsp+278h+var_38], rax
0x180024169  xor     r15d, r15d
0x18002416c  mov     rbx, r8
0x18002416f  mov     rsi, rdx
0x180024172  mov     r14, rcx
0x180024175  test    rdx, rdx
0x180024178  jz      loc_1800243D1
0x18002417e  test    rcx, rcx
0x180024181  jz      loc_1800243D1
0x180024187  mov     rax, cs:g_pfnResultLoggingCallback
0x18002418e  mov     [rcx], r15w
0x180024192  test    rax, rax
0x180024195  jz      short loc_1800241B8
0x180024197  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002419e  jz      short loc_1800241B8
0x1800241a0  mov     r8, rdx
0x1800241a3  mov     rdx, rcx
0x1800241a6  mov     rcx, rbx
0x1800241a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241ae  cmp     [r14], r15w
0x1800241b2  jnz     loc_1800243D1
0x1800241b8  mov     ecx, [rbx]
0x1800241ba  mov     bpl, 8
0x1800241bd  test    ecx, ecx
0x1800241bf  jz      short loc_18002420A
0x1800241c1  sub     ecx, 1
0x1800241c4  jz      short loc_1800241F2
0x1800241c6  sub     ecx, 1
0x1800241c9  jz      short loc_1800241E2
0x1800241cb  cmp     ecx, 1
0x1800241ce  jz      short loc_1800241D9
0x1800241d0  lea     rdi, byte_18005188D
0x1800241d7  jmp     short loc_180024211
0x1800241d9  lea     rdi, aFailfast; "FailFast"
0x1800241e0  jmp     short loc_180024211
0x1800241e2  lea     rax, aLoghr; "LogHr"
0x1800241e9  lea     rdi, aLognt; "LogNt"
0x1800241f0  jmp     short loc_180024200
0x1800241f2  lea     rax, aReturnhr; "ReturnHr"
0x1800241f9  lea     rdi, aReturnnt; "ReturnNt"
0x180024200  test    [rbx+4], bpl
0x180024204  cmovz   rdi, rax
0x180024208  jmp     short loc_180024211
0x18002420a  lea     rdi, aException; "Exception"
0x180024211  xor     edx, edx; Val
0x180024213  lea     rcx, [rsp+278h+Buffer]; void *
0x180024218  mov     r8d, 200h; Size
0x18002421e  call    memset_0
0x180024223  test    [rbx+4], bpl
0x180024227  jz      short loc_18002424C
0x180024229  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180024230  mov     ebp, [rbx+0Ch]
0x180024233  test    rax, rax
0x180024236  jz      short loc_18002427C
0x180024238  mov     r8d, 100h
0x18002423e  lea     rdx, [rsp+278h+Buffer]
0x180024243  mov     ecx, ebp
0x180024245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002424a  jmp     short loc_18002427C
0x18002424c  mov     ebp, [rbx+8]
0x18002424f  lea     rax, [rsp+278h+Buffer]
0x180024254  mov     [rsp+278h+Arguments], r15; Arguments
0x180024259  mov     r8d, ebp; dwMessageId
0x18002425c  mov     [rsp+278h+nSize], 100h; nSize
0x180024264  mov     r9d, 400h; dwLanguageId
0x18002426a  xor     edx, edx; lpSource
0x18002426c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180024271  mov     ecx, 1200h; dwFlags
0x180024276  call    cs:__imp_FormatMessageW
0x18002427c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180024280  lea     rsi, [r14+rsi*2]
0x180024284  mov     rax, [rbx+88h]
0x18002428b  mov     rdx, rsi; unsigned __int16 *
0x18002428e  mov     rcx, [rbx+80h]
0x180024295  test    r9, r9
0x180024298  jz      short loc_1800242BC
0x18002429a  mov     [rsp+278h+Arguments], rax
0x18002429f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800242a6  mov     eax, [rbx+40h]
0x1800242a9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800242ae  mov     rcx, r14; this
0x1800242b1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800242b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800242ba  jmp     short loc_1800242D3
0x1800242bc  mov     r9, rcx; unsigned __int16 *
0x1800242bf  mov     [rsp+278h+lpBuffer], rax
0x1800242c4  mov     rcx, r14; this
0x1800242c7  lea     r8, aHsP; "%hs!%p: "
0x1800242ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800242d3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800242da  mov     r14, rax
0x1800242dd  test    r9, r9
0x1800242e0  jz      short loc_1800242F7
0x1800242e2  lea     r8, aCallerP; "(caller: %p) "
0x1800242e9  mov     rdx, rsi; unsigned __int16 *
0x1800242ec  mov     rcx, rax; this
0x1800242ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800242f4  mov     r14, rax
0x1800242f7  call    cs:__imp_GetCurrentThreadId
0x1800242fd  lea     rcx, [rsp+278h+Buffer]
0x180024302  mov     r9, rdi; unsigned __int16 *
0x180024305  mov     [rsp+278h+var_240], rcx
0x18002430a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180024311  mov     dword ptr [rsp+278h+Arguments], ebp
0x180024315  mov     rdx, rsi; unsigned __int16 *
0x180024318  mov     [rsp+278h+nSize], eax
0x18002431c  mov     rcx, r14; this
0x18002431f  mov     eax, [rbx+44h]
0x180024322  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180024326  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002432b  cmp     [rbx+18h], r15
0x18002432f  jnz     short loc_180024341
0x180024331  cmp     [rbx+48h], r15
0x180024335  jnz     short loc_180024341
0x180024337  cmp     [rbx+30h], r15
0x18002433b  jz      loc_1800243D1
0x180024341  lea     r8, asc_180051978; "    "
0x180024348  mov     rdx, rsi; unsigned __int16 *
0x18002434b  mov     rcx, rax; this
0x18002434e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024353  mov     r9, [rbx+18h]; unsigned __int16 *
0x180024357  test    r9, r9
0x18002435a  jz      short loc_18002436E
0x18002435c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180024363  mov     rdx, rsi; unsigned __int16 *
0x180024366  mov     rcx, rax; this
0x180024369  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002436e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180024372  test    r9, r9
0x180024375  jz      short loc_180024389
0x180024377  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002437e  mov     rdx, rsi; unsigned __int16 *
0x180024381  mov     rcx, rax; this
0x180024384  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024389  mov     rcx, [rbx+28h]
0x18002438d  mov     rdx, rsi; unsigned __int16 *
0x180024390  mov     r9, [rbx+30h]; unsigned __int16 *
0x180024394  test    rcx, rcx
0x180024397  jz      short loc_1800243AF
0x180024399  mov     [rsp+278h+lpBuffer], rcx
0x18002439e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800243a5  mov     rcx, rax; this
0x1800243a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800243ad  jmp     short loc_1800243D1
0x1800243af  mov     rcx, rax; this
0x1800243b2  test    r9, r9
0x1800243b5  jz      short loc_1800243C5
0x1800243b7  lea     r8, aHs; "[%hs]\n"
0x1800243be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800243c3  jmp     short loc_1800243D1
0x1800243c5  lea     r8, asc_1800519F0; "\n"
0x1800243cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800243d1  xor     eax, eax
0x1800243d3  mov     rcx, [rsp+278h+var_38]
0x1800243db  xor     rcx, rsp; StackCookie
0x1800243de  call    __security_check_cookie
0x1800243e3  mov     rbx, [rsp+278h+arg_18]
0x1800243eb  add     rsp, 250h
0x1800243f2  pop     r15
0x1800243f4  pop     r14
0x1800243f6  pop     rdi
0x1800243f7  pop     rsi
0x1800243f8  pop     rbp
0x1800243f9  retn
```
