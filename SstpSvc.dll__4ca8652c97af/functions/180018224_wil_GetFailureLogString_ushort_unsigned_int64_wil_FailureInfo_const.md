# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180018224`
- end: `0x1800184da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001699c`
- `0x180016c04`
- `0x180018d94`

## callees

- `0x180018224`
- `0x180019094`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018356`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018356`

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
          v8 = (const char *)&word_18002781E;
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
0x180018224  mov     [rsp+arg_18], rbx
0x180018229  push    rbp
0x18001822a  push    rsi
0x18001822b  push    rdi
0x18001822c  push    r14
0x18001822e  push    r15
0x180018230  sub     rsp, 250h
0x180018237  mov     rax, cs:__security_cookie
0x18001823e  xor     rax, rsp
0x180018241  mov     [rsp+278h+var_38], rax
0x180018249  xor     r15d, r15d
0x18001824c  mov     rbx, r8
0x18001824f  mov     rsi, rdx
0x180018252  mov     r14, rcx
0x180018255  test    rdx, rdx
0x180018258  jz      loc_1800184B1
0x18001825e  test    rcx, rcx
0x180018261  jz      loc_1800184B1
0x180018267  mov     rax, cs:g_pfnResultLoggingCallback
0x18001826e  mov     [rcx], r15w
0x180018272  test    rax, rax
0x180018275  jz      short loc_180018298
0x180018277  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001827e  jz      short loc_180018298
0x180018280  mov     r8, rdx
0x180018283  mov     rdx, rcx
0x180018286  mov     rcx, rbx
0x180018289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001828e  cmp     [r14], r15w
0x180018292  jnz     loc_1800184B1
0x180018298  mov     ecx, [rbx]
0x18001829a  mov     bpl, 8
0x18001829d  test    ecx, ecx
0x18001829f  jz      short loc_1800182EA
0x1800182a1  sub     ecx, 1
0x1800182a4  jz      short loc_1800182D2
0x1800182a6  sub     ecx, 1
0x1800182a9  jz      short loc_1800182C2
0x1800182ab  cmp     ecx, 1
0x1800182ae  jz      short loc_1800182B9
0x1800182b0  lea     rdi, word_18002781E
0x1800182b7  jmp     short loc_1800182F1
0x1800182b9  lea     rdi, aFailfast; "FailFast"
0x1800182c0  jmp     short loc_1800182F1
0x1800182c2  lea     rax, aLoghr; "LogHr"
0x1800182c9  lea     rdi, aLognt; "LogNt"
0x1800182d0  jmp     short loc_1800182E0
0x1800182d2  lea     rax, aReturnhr; "ReturnHr"
0x1800182d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800182e0  test    [rbx+4], bpl
0x1800182e4  cmovz   rdi, rax
0x1800182e8  jmp     short loc_1800182F1
0x1800182ea  lea     rdi, aException; "Exception"
0x1800182f1  xor     edx, edx; Val
0x1800182f3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800182f8  mov     r8d, 200h; Size
0x1800182fe  call    memset_0
0x180018303  test    [rbx+4], bpl
0x180018307  jz      short loc_18001832C
0x180018309  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180018310  mov     ebp, [rbx+0Ch]
0x180018313  test    rax, rax
0x180018316  jz      short loc_18001835C
0x180018318  mov     r8d, 100h
0x18001831e  lea     rdx, [rsp+278h+Buffer]
0x180018323  mov     ecx, ebp
0x180018325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001832a  jmp     short loc_18001835C
0x18001832c  mov     ebp, [rbx+8]
0x18001832f  lea     rax, [rsp+278h+Buffer]
0x180018334  mov     [rsp+278h+Arguments], r15; Arguments
0x180018339  mov     r8d, ebp; dwMessageId
0x18001833c  mov     [rsp+278h+nSize], 100h; nSize
0x180018344  mov     r9d, 400h; dwLanguageId
0x18001834a  xor     edx, edx; lpSource
0x18001834c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180018351  mov     ecx, 1200h; dwFlags
0x180018356  call    cs:__imp_FormatMessageW
0x18001835c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180018360  lea     rsi, [r14+rsi*2]
0x180018364  mov     rax, [rbx+88h]
0x18001836b  mov     rdx, rsi; unsigned __int16 *
0x18001836e  mov     rcx, [rbx+80h]
0x180018375  test    r9, r9
0x180018378  jz      short loc_18001839C
0x18001837a  mov     [rsp+278h+Arguments], rax
0x18001837f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180018386  mov     eax, [rbx+40h]
0x180018389  mov     qword ptr [rsp+278h+nSize], rcx
0x18001838e  mov     rcx, r14; this
0x180018391  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180018395  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001839a  jmp     short loc_1800183B3
0x18001839c  mov     r9, rcx; unsigned __int16 *
0x18001839f  mov     [rsp+278h+lpBuffer], rax
0x1800183a4  mov     rcx, r14; this
0x1800183a7  lea     r8, aHsP; "%hs!%p: "
0x1800183ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800183b3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800183ba  mov     r14, rax
0x1800183bd  test    r9, r9
0x1800183c0  jz      short loc_1800183D7
0x1800183c2  lea     r8, aCallerP; "(caller: %p) "
0x1800183c9  mov     rdx, rsi; unsigned __int16 *
0x1800183cc  mov     rcx, rax; this
0x1800183cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800183d4  mov     r14, rax
0x1800183d7  call    cs:__imp_GetCurrentThreadId
0x1800183dd  lea     rcx, [rsp+278h+Buffer]
0x1800183e2  mov     r9, rdi; unsigned __int16 *
0x1800183e5  mov     [rsp+278h+var_240], rcx
0x1800183ea  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800183f1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800183f5  mov     rdx, rsi; unsigned __int16 *
0x1800183f8  mov     [rsp+278h+nSize], eax
0x1800183fc  mov     rcx, r14; this
0x1800183ff  mov     eax, [rbx+44h]
0x180018402  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180018406  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001840b  cmp     [rbx+18h], r15
0x18001840f  jnz     short loc_180018421
0x180018411  cmp     [rbx+48h], r15
0x180018415  jnz     short loc_180018421
0x180018417  cmp     [rbx+30h], r15
0x18001841b  jz      loc_1800184B1
0x180018421  lea     r8, asc_180027908; "    "
0x180018428  mov     rdx, rsi; unsigned __int16 *
0x18001842b  mov     rcx, rax; this
0x18001842e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018433  mov     r9, [rbx+18h]; unsigned __int16 *
0x180018437  test    r9, r9
0x18001843a  jz      short loc_18001844E
0x18001843c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180018443  mov     rdx, rsi; unsigned __int16 *
0x180018446  mov     rcx, rax; this
0x180018449  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001844e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180018452  test    r9, r9
0x180018455  jz      short loc_180018469
0x180018457  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001845e  mov     rdx, rsi; unsigned __int16 *
0x180018461  mov     rcx, rax; this
0x180018464  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180018469  mov     rcx, [rbx+28h]
0x18001846d  mov     rdx, rsi; unsigned __int16 *
0x180018470  mov     r9, [rbx+30h]; unsigned __int16 *
0x180018474  test    rcx, rcx
0x180018477  jz      short loc_18001848F
0x180018479  mov     [rsp+278h+lpBuffer], rcx
0x18001847e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180018485  mov     rcx, rax; this
0x180018488  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001848d  jmp     short loc_1800184B1
0x18001848f  mov     rcx, rax; this
0x180018492  test    r9, r9
0x180018495  jz      short loc_1800184A5
0x180018497  lea     r8, aHs; "[%hs]\n"
0x18001849e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800184a3  jmp     short loc_1800184B1
0x1800184a5  lea     r8, asc_180027980; "\n"
0x1800184ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800184b1  xor     eax, eax
0x1800184b3  mov     rcx, [rsp+278h+var_38]
0x1800184bb  xor     rcx, rsp; StackCookie
0x1800184be  call    __security_check_cookie
0x1800184c3  mov     rbx, [rsp+278h+arg_18]
0x1800184cb  add     rsp, 250h
0x1800184d2  pop     r15
0x1800184d4  pop     r14
0x1800184d6  pop     rdi
0x1800184d7  pop     rsi
0x1800184d8  pop     rbp
0x1800184d9  retn
```
