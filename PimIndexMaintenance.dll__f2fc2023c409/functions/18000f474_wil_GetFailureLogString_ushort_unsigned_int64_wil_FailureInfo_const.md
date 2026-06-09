# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000f474`
- end: `0x18000f72a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e0a8`
- `0x1800100f8`

## callees

- `0x18000f474`
- `0x1800103f8`
- `0x18002120a`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f627`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f627`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f5a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f5a6`

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
          v8 = (const char *)&dword_1800270F4;
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
0x18000f474  mov     [rsp+arg_18], rbx
0x18000f479  push    rbp
0x18000f47a  push    rsi
0x18000f47b  push    rdi
0x18000f47c  push    r14
0x18000f47e  push    r15
0x18000f480  sub     rsp, 250h
0x18000f487  mov     rax, cs:__security_cookie
0x18000f48e  xor     rax, rsp
0x18000f491  mov     [rsp+278h+var_38], rax
0x18000f499  xor     r15d, r15d
0x18000f49c  mov     rbx, r8
0x18000f49f  mov     rsi, rdx
0x18000f4a2  mov     r14, rcx
0x18000f4a5  test    rdx, rdx
0x18000f4a8  jz      loc_18000F701
0x18000f4ae  test    rcx, rcx
0x18000f4b1  jz      loc_18000F701
0x18000f4b7  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f4be  mov     [rcx], r15w
0x18000f4c2  test    rax, rax
0x18000f4c5  jz      short loc_18000F4E8
0x18000f4c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000f4ce  jz      short loc_18000F4E8
0x18000f4d0  mov     r8, rdx
0x18000f4d3  mov     rdx, rcx
0x18000f4d6  mov     rcx, rbx
0x18000f4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4de  cmp     [r14], r15w
0x18000f4e2  jnz     loc_18000F701
0x18000f4e8  mov     ecx, [rbx]
0x18000f4ea  mov     bpl, 8
0x18000f4ed  test    ecx, ecx
0x18000f4ef  jz      short loc_18000F53A
0x18000f4f1  sub     ecx, 1
0x18000f4f4  jz      short loc_18000F522
0x18000f4f6  sub     ecx, 1
0x18000f4f9  jz      short loc_18000F512
0x18000f4fb  cmp     ecx, 1
0x18000f4fe  jz      short loc_18000F509
0x18000f500  lea     rdi, dword_1800270F4
0x18000f507  jmp     short loc_18000F541
0x18000f509  lea     rdi, aFailfast; "FailFast"
0x18000f510  jmp     short loc_18000F541
0x18000f512  lea     rax, aLoghr; "LogHr"
0x18000f519  lea     rdi, aLognt; "LogNt"
0x18000f520  jmp     short loc_18000F530
0x18000f522  lea     rax, aReturnhr; "ReturnHr"
0x18000f529  lea     rdi, aReturnnt; "ReturnNt"
0x18000f530  test    [rbx+4], bpl
0x18000f534  cmovz   rdi, rax
0x18000f538  jmp     short loc_18000F541
0x18000f53a  lea     rdi, aException; "Exception"
0x18000f541  xor     edx, edx; Val
0x18000f543  lea     rcx, [rsp+278h+Buffer]; void *
0x18000f548  mov     r8d, 200h; Size
0x18000f54e  call    memset_0
0x18000f553  test    [rbx+4], bpl
0x18000f557  jz      short loc_18000F57C
0x18000f559  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000f560  mov     ebp, [rbx+0Ch]
0x18000f563  test    rax, rax
0x18000f566  jz      short loc_18000F5AC
0x18000f568  mov     r8d, 100h
0x18000f56e  lea     rdx, [rsp+278h+Buffer]
0x18000f573  mov     ecx, ebp
0x18000f575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f57a  jmp     short loc_18000F5AC
0x18000f57c  mov     ebp, [rbx+8]
0x18000f57f  lea     rax, [rsp+278h+Buffer]
0x18000f584  mov     [rsp+278h+Arguments], r15; Arguments
0x18000f589  mov     r8d, ebp; dwMessageId
0x18000f58c  mov     [rsp+278h+nSize], 100h; nSize
0x18000f594  mov     r9d, 400h; dwLanguageId
0x18000f59a  xor     edx, edx; lpSource
0x18000f59c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000f5a1  mov     ecx, 1200h; dwFlags
0x18000f5a6  call    cs:__imp_FormatMessageW
0x18000f5ac  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000f5b0  lea     rsi, [r14+rsi*2]
0x18000f5b4  mov     rax, [rbx+88h]
0x18000f5bb  mov     rdx, rsi; unsigned __int16 *
0x18000f5be  mov     rcx, [rbx+80h]
0x18000f5c5  test    r9, r9
0x18000f5c8  jz      short loc_18000F5EC
0x18000f5ca  mov     [rsp+278h+Arguments], rax
0x18000f5cf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000f5d6  mov     eax, [rbx+40h]
0x18000f5d9  mov     qword ptr [rsp+278h+nSize], rcx
0x18000f5de  mov     rcx, r14; this
0x18000f5e1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f5e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f5ea  jmp     short loc_18000F603
0x18000f5ec  mov     r9, rcx; unsigned __int16 *
0x18000f5ef  mov     [rsp+278h+lpBuffer], rax
0x18000f5f4  mov     rcx, r14; this
0x18000f5f7  lea     r8, aHsP; "%hs!%p: "
0x18000f5fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f603  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000f60a  mov     r14, rax
0x18000f60d  test    r9, r9
0x18000f610  jz      short loc_18000F627
0x18000f612  lea     r8, aCallerP; "(caller: %p) "
0x18000f619  mov     rdx, rsi; unsigned __int16 *
0x18000f61c  mov     rcx, rax; this
0x18000f61f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f624  mov     r14, rax
0x18000f627  call    cs:__imp_GetCurrentThreadId
0x18000f62d  lea     rcx, [rsp+278h+Buffer]
0x18000f632  mov     r9, rdi; unsigned __int16 *
0x18000f635  mov     [rsp+278h+var_240], rcx
0x18000f63a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000f641  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000f645  mov     rdx, rsi; unsigned __int16 *
0x18000f648  mov     [rsp+278h+nSize], eax
0x18000f64c  mov     rcx, r14; this
0x18000f64f  mov     eax, [rbx+44h]
0x18000f652  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f656  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f65b  cmp     [rbx+18h], r15
0x18000f65f  jnz     short loc_18000F671
0x18000f661  cmp     [rbx+48h], r15
0x18000f665  jnz     short loc_18000F671
0x18000f667  cmp     [rbx+30h], r15
0x18000f66b  jz      loc_18000F701
0x18000f671  lea     r8, asc_180026D28; "    "
0x18000f678  mov     rdx, rsi; unsigned __int16 *
0x18000f67b  mov     rcx, rax; this
0x18000f67e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f683  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000f687  test    r9, r9
0x18000f68a  jz      short loc_18000F69E
0x18000f68c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000f693  mov     rdx, rsi; unsigned __int16 *
0x18000f696  mov     rcx, rax; this
0x18000f699  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f69e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000f6a2  test    r9, r9
0x18000f6a5  jz      short loc_18000F6B9
0x18000f6a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000f6ae  mov     rdx, rsi; unsigned __int16 *
0x18000f6b1  mov     rcx, rax; this
0x18000f6b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f6b9  mov     rcx, [rbx+28h]
0x18000f6bd  mov     rdx, rsi; unsigned __int16 *
0x18000f6c0  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000f6c4  test    rcx, rcx
0x18000f6c7  jz      short loc_18000F6DF
0x18000f6c9  mov     [rsp+278h+lpBuffer], rcx
0x18000f6ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000f6d5  mov     rcx, rax; this
0x18000f6d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f6dd  jmp     short loc_18000F701
0x18000f6df  mov     rcx, rax; this
0x18000f6e2  test    r9, r9
0x18000f6e5  jz      short loc_18000F6F5
0x18000f6e7  lea     r8, aHs; "[%hs]\n"
0x18000f6ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f6f3  jmp     short loc_18000F701
0x18000f6f5  lea     r8, asc_180026DA0; "\n"
0x18000f6fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f701  xor     eax, eax
0x18000f703  mov     rcx, [rsp+278h+var_38]
0x18000f70b  xor     rcx, rsp; StackCookie
0x18000f70e  call    __security_check_cookie
0x18000f713  mov     rbx, [rsp+278h+arg_18]
0x18000f71b  add     rsp, 250h
0x18000f722  pop     r15
0x18000f724  pop     r14
0x18000f726  pop     rdi
0x18000f727  pop     rsi
0x18000f728  pop     rbp
0x18000f729  retn
```
