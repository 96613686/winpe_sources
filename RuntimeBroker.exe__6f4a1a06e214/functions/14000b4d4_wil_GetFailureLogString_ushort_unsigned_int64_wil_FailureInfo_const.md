# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000b4d4`
- end: `0x14000b78a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a648`
- `0x14000bcfc`

## callees

- `0x140008c80`
- `0x140009640`
- `0x14000b4d4`
- `0x14000bffc`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b687`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b687`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000b606`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000b606`

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
          v8 = (const char *)&dword_1400135E4;
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
0x14000b4d4  mov     [rsp+arg_18], rbx
0x14000b4d9  push    rbp
0x14000b4da  push    rsi
0x14000b4db  push    rdi
0x14000b4dc  push    r14
0x14000b4de  push    r15
0x14000b4e0  sub     rsp, 250h
0x14000b4e7  mov     rax, cs:__security_cookie
0x14000b4ee  xor     rax, rsp
0x14000b4f1  mov     [rsp+278h+var_38], rax
0x14000b4f9  xor     r15d, r15d
0x14000b4fc  mov     rbx, r8
0x14000b4ff  mov     rsi, rdx
0x14000b502  mov     r14, rcx
0x14000b505  test    rdx, rdx
0x14000b508  jz      loc_14000B761
0x14000b50e  test    rcx, rcx
0x14000b511  jz      loc_14000B761
0x14000b517  mov     rax, cs:g_pfnResultLoggingCallback
0x14000b51e  mov     [rcx], r15w
0x14000b522  test    rax, rax
0x14000b525  jz      short loc_14000B548
0x14000b527  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000b52e  jz      short loc_14000B548
0x14000b530  mov     r8, rdx
0x14000b533  mov     rdx, rcx
0x14000b536  mov     rcx, rbx
0x14000b539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b53e  cmp     [r14], r15w
0x14000b542  jnz     loc_14000B761
0x14000b548  mov     ecx, [rbx]
0x14000b54a  mov     bpl, 8
0x14000b54d  test    ecx, ecx
0x14000b54f  jz      short loc_14000B59A
0x14000b551  sub     ecx, 1
0x14000b554  jz      short loc_14000B582
0x14000b556  sub     ecx, 1
0x14000b559  jz      short loc_14000B572
0x14000b55b  cmp     ecx, 1
0x14000b55e  jz      short loc_14000B569
0x14000b560  lea     rdi, dword_1400135E4
0x14000b567  jmp     short loc_14000B5A1
0x14000b569  lea     rdi, aFailfast; "FailFast"
0x14000b570  jmp     short loc_14000B5A1
0x14000b572  lea     rax, aLoghr; "LogHr"
0x14000b579  lea     rdi, aLognt; "LogNt"
0x14000b580  jmp     short loc_14000B590
0x14000b582  lea     rax, aReturnhr; "ReturnHr"
0x14000b589  lea     rdi, aReturnnt; "ReturnNt"
0x14000b590  test    [rbx+4], bpl
0x14000b594  cmovz   rdi, rax
0x14000b598  jmp     short loc_14000B5A1
0x14000b59a  lea     rdi, aException; "Exception"
0x14000b5a1  xor     edx, edx; Val
0x14000b5a3  lea     rcx, [rsp+278h+Buffer]; void *
0x14000b5a8  mov     r8d, 200h; Size
0x14000b5ae  call    memset_0
0x14000b5b3  test    [rbx+4], bpl
0x14000b5b7  jz      short loc_14000B5DC
0x14000b5b9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000b5c0  mov     ebp, [rbx+0Ch]
0x14000b5c3  test    rax, rax
0x14000b5c6  jz      short loc_14000B60C
0x14000b5c8  mov     r8d, 100h
0x14000b5ce  lea     rdx, [rsp+278h+Buffer]
0x14000b5d3  mov     ecx, ebp
0x14000b5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b5da  jmp     short loc_14000B60C
0x14000b5dc  mov     ebp, [rbx+8]
0x14000b5df  lea     rax, [rsp+278h+Buffer]
0x14000b5e4  mov     [rsp+278h+Arguments], r15; Arguments
0x14000b5e9  mov     r8d, ebp; dwMessageId
0x14000b5ec  mov     [rsp+278h+nSize], 100h; nSize
0x14000b5f4  mov     r9d, 400h; dwLanguageId
0x14000b5fa  xor     edx, edx; lpSource
0x14000b5fc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000b601  mov     ecx, 1200h; dwFlags
0x14000b606  call    cs:__imp_FormatMessageW
0x14000b60c  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000b610  lea     rsi, [r14+rsi*2]
0x14000b614  mov     rax, [rbx+88h]
0x14000b61b  mov     rdx, rsi; unsigned __int16 *
0x14000b61e  mov     rcx, [rbx+80h]
0x14000b625  test    r9, r9
0x14000b628  jz      short loc_14000B64C
0x14000b62a  mov     [rsp+278h+Arguments], rax
0x14000b62f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000b636  mov     eax, [rbx+40h]
0x14000b639  mov     qword ptr [rsp+278h+nSize], rcx
0x14000b63e  mov     rcx, r14; this
0x14000b641  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000b645  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b64a  jmp     short loc_14000B663
0x14000b64c  mov     r9, rcx; unsigned __int16 *
0x14000b64f  mov     [rsp+278h+lpBuffer], rax
0x14000b654  mov     rcx, r14; this
0x14000b657  lea     r8, aHsP; "%hs!%p: "
0x14000b65e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b663  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000b66a  mov     r14, rax
0x14000b66d  test    r9, r9
0x14000b670  jz      short loc_14000B687
0x14000b672  lea     r8, aCallerP; "(caller: %p) "
0x14000b679  mov     rdx, rsi; unsigned __int16 *
0x14000b67c  mov     rcx, rax; this
0x14000b67f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b684  mov     r14, rax
0x14000b687  call    cs:__imp_GetCurrentThreadId
0x14000b68d  lea     rcx, [rsp+278h+Buffer]
0x14000b692  mov     r9, rdi; unsigned __int16 *
0x14000b695  mov     [rsp+278h+var_240], rcx
0x14000b69a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000b6a1  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000b6a5  mov     rdx, rsi; unsigned __int16 *
0x14000b6a8  mov     [rsp+278h+nSize], eax
0x14000b6ac  mov     rcx, r14; this
0x14000b6af  mov     eax, [rbx+44h]
0x14000b6b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000b6b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b6bb  cmp     [rbx+18h], r15
0x14000b6bf  jnz     short loc_14000B6D1
0x14000b6c1  cmp     [rbx+48h], r15
0x14000b6c5  jnz     short loc_14000B6D1
0x14000b6c7  cmp     [rbx+30h], r15
0x14000b6cb  jz      loc_14000B761
0x14000b6d1  lea     r8, asc_1400136D8; "    "
0x14000b6d8  mov     rdx, rsi; unsigned __int16 *
0x14000b6db  mov     rcx, rax; this
0x14000b6de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b6e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000b6e7  test    r9, r9
0x14000b6ea  jz      short loc_14000B6FE
0x14000b6ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000b6f3  mov     rdx, rsi; unsigned __int16 *
0x14000b6f6  mov     rcx, rax; this
0x14000b6f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b6fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000b702  test    r9, r9
0x14000b705  jz      short loc_14000B719
0x14000b707  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000b70e  mov     rdx, rsi; unsigned __int16 *
0x14000b711  mov     rcx, rax; this
0x14000b714  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b719  mov     rcx, [rbx+28h]
0x14000b71d  mov     rdx, rsi; unsigned __int16 *
0x14000b720  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000b724  test    rcx, rcx
0x14000b727  jz      short loc_14000B73F
0x14000b729  mov     [rsp+278h+lpBuffer], rcx
0x14000b72e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000b735  mov     rcx, rax; this
0x14000b738  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b73d  jmp     short loc_14000B761
0x14000b73f  mov     rcx, rax; this
0x14000b742  test    r9, r9
0x14000b745  jz      short loc_14000B755
0x14000b747  lea     r8, aHs; "[%hs]\n"
0x14000b74e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b753  jmp     short loc_14000B761
0x14000b755  lea     r8, asc_140013750; "\n"
0x14000b75c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b761  xor     eax, eax
0x14000b763  mov     rcx, [rsp+278h+var_38]
0x14000b76b  xor     rcx, rsp; StackCookie
0x14000b76e  call    __security_check_cookie
0x14000b773  mov     rbx, [rsp+278h+arg_18]
0x14000b77b  add     rsp, 250h
0x14000b782  pop     r15
0x14000b784  pop     r14
0x14000b786  pop     rdi
0x14000b787  pop     rsi
0x14000b788  pop     rbp
0x14000b789  retn
```
