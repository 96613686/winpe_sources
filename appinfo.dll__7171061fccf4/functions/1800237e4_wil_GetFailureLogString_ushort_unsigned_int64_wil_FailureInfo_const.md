# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800237e4`
- end: `0x180023a9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001944c`

## callees

- `0x1800237e4`
- `0x180023dd8`
- `0x180046e1a`
- `0x180046e50`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023997`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023997`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180023916`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180023916`

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
          v8 = (const char *)&dword_18004D4B4;
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
0x1800237e4  mov     [rsp+arg_18], rbx
0x1800237e9  push    rbp
0x1800237ea  push    rsi
0x1800237eb  push    rdi
0x1800237ec  push    r14
0x1800237ee  push    r15
0x1800237f0  sub     rsp, 250h
0x1800237f7  mov     rax, cs:__security_cookie
0x1800237fe  xor     rax, rsp
0x180023801  mov     [rsp+278h+var_38], rax
0x180023809  xor     r15d, r15d
0x18002380c  mov     rbx, r8
0x18002380f  mov     rsi, rdx
0x180023812  mov     r14, rcx
0x180023815  test    rdx, rdx
0x180023818  jz      loc_180023A71
0x18002381e  test    rcx, rcx
0x180023821  jz      loc_180023A71
0x180023827  mov     rax, cs:g_pfnResultLoggingCallback
0x18002382e  mov     [rcx], r15w
0x180023832  test    rax, rax
0x180023835  jz      short loc_180023858
0x180023837  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002383e  jz      short loc_180023858
0x180023840  mov     r8, rdx
0x180023843  mov     rdx, rcx
0x180023846  mov     rcx, rbx
0x180023849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002384e  cmp     [r14], r15w
0x180023852  jnz     loc_180023A71
0x180023858  mov     ecx, [rbx]
0x18002385a  mov     bpl, 8
0x18002385d  test    ecx, ecx
0x18002385f  jz      short loc_1800238AA
0x180023861  sub     ecx, 1
0x180023864  jz      short loc_180023892
0x180023866  sub     ecx, 1
0x180023869  jz      short loc_180023882
0x18002386b  cmp     ecx, 1
0x18002386e  jz      short loc_180023879
0x180023870  lea     rdi, dword_18004D4B4
0x180023877  jmp     short loc_1800238B1
0x180023879  lea     rdi, aFailfast; "FailFast"
0x180023880  jmp     short loc_1800238B1
0x180023882  lea     rax, aLoghr; "LogHr"
0x180023889  lea     rdi, aLognt; "LogNt"
0x180023890  jmp     short loc_1800238A0
0x180023892  lea     rax, aReturnhr; "ReturnHr"
0x180023899  lea     rdi, aReturnnt; "ReturnNt"
0x1800238a0  test    [rbx+4], bpl
0x1800238a4  cmovz   rdi, rax
0x1800238a8  jmp     short loc_1800238B1
0x1800238aa  lea     rdi, aException; "Exception"
0x1800238b1  xor     edx, edx; Val
0x1800238b3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800238b8  mov     r8d, 200h; Size
0x1800238be  call    memset_0
0x1800238c3  test    [rbx+4], bpl
0x1800238c7  jz      short loc_1800238EC
0x1800238c9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800238d0  mov     ebp, [rbx+0Ch]
0x1800238d3  test    rax, rax
0x1800238d6  jz      short loc_18002391C
0x1800238d8  mov     r8d, 100h
0x1800238de  lea     rdx, [rsp+278h+Buffer]
0x1800238e3  mov     ecx, ebp
0x1800238e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238ea  jmp     short loc_18002391C
0x1800238ec  mov     ebp, [rbx+8]
0x1800238ef  lea     rax, [rsp+278h+Buffer]
0x1800238f4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800238f9  mov     r8d, ebp; dwMessageId
0x1800238fc  mov     [rsp+278h+nSize], 100h; nSize
0x180023904  mov     r9d, 400h; dwLanguageId
0x18002390a  xor     edx, edx; lpSource
0x18002390c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180023911  mov     ecx, 1200h; dwFlags
0x180023916  call    cs:__imp_FormatMessageW
0x18002391c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180023920  lea     rsi, [r14+rsi*2]
0x180023924  mov     rax, [rbx+88h]
0x18002392b  mov     rdx, rsi; unsigned __int16 *
0x18002392e  mov     rcx, [rbx+80h]
0x180023935  test    r9, r9
0x180023938  jz      short loc_18002395C
0x18002393a  mov     [rsp+278h+Arguments], rax
0x18002393f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180023946  mov     eax, [rbx+40h]
0x180023949  mov     qword ptr [rsp+278h+nSize], rcx
0x18002394e  mov     rcx, r14; this
0x180023951  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180023955  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002395a  jmp     short loc_180023973
0x18002395c  mov     r9, rcx; unsigned __int16 *
0x18002395f  mov     [rsp+278h+lpBuffer], rax
0x180023964  mov     rcx, r14; this
0x180023967  lea     r8, aHsP; "%hs!%p: "
0x18002396e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023973  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002397a  mov     r14, rax
0x18002397d  test    r9, r9
0x180023980  jz      short loc_180023997
0x180023982  lea     r8, aCallerP; "(caller: %p) "
0x180023989  mov     rdx, rsi; unsigned __int16 *
0x18002398c  mov     rcx, rax; this
0x18002398f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023994  mov     r14, rax
0x180023997  call    cs:__imp_GetCurrentThreadId
0x18002399d  lea     rcx, [rsp+278h+Buffer]
0x1800239a2  mov     r9, rdi; unsigned __int16 *
0x1800239a5  mov     [rsp+278h+var_240], rcx
0x1800239aa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800239b1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800239b5  mov     rdx, rsi; unsigned __int16 *
0x1800239b8  mov     [rsp+278h+nSize], eax
0x1800239bc  mov     rcx, r14; this
0x1800239bf  mov     eax, [rbx+44h]
0x1800239c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800239c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800239cb  cmp     [rbx+18h], r15
0x1800239cf  jnz     short loc_1800239E1
0x1800239d1  cmp     [rbx+48h], r15
0x1800239d5  jnz     short loc_1800239E1
0x1800239d7  cmp     [rbx+30h], r15
0x1800239db  jz      loc_180023A71
0x1800239e1  lea     r8, asc_18004F7F0; "    "
0x1800239e8  mov     rdx, rsi; unsigned __int16 *
0x1800239eb  mov     rcx, rax; this
0x1800239ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800239f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800239f7  test    r9, r9
0x1800239fa  jz      short loc_180023A0E
0x1800239fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180023a03  mov     rdx, rsi; unsigned __int16 *
0x180023a06  mov     rcx, rax; this
0x180023a09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023a0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180023a12  test    r9, r9
0x180023a15  jz      short loc_180023A29
0x180023a17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180023a1e  mov     rdx, rsi; unsigned __int16 *
0x180023a21  mov     rcx, rax; this
0x180023a24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023a29  mov     rcx, [rbx+28h]
0x180023a2d  mov     rdx, rsi; unsigned __int16 *
0x180023a30  mov     r9, [rbx+30h]; unsigned __int16 *
0x180023a34  test    rcx, rcx
0x180023a37  jz      short loc_180023A4F
0x180023a39  mov     [rsp+278h+lpBuffer], rcx
0x180023a3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180023a45  mov     rcx, rax; this
0x180023a48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023a4d  jmp     short loc_180023A71
0x180023a4f  mov     rcx, rax; this
0x180023a52  test    r9, r9
0x180023a55  jz      short loc_180023A65
0x180023a57  lea     r8, aHs; "[%hs]\n"
0x180023a5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023a63  jmp     short loc_180023A71
0x180023a65  lea     r8, asc_18004F868; "\n"
0x180023a6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180023a71  xor     eax, eax
0x180023a73  mov     rcx, [rsp+278h+var_38]
0x180023a7b  xor     rcx, rsp; StackCookie
0x180023a7e  call    __security_check_cookie
0x180023a83  mov     rbx, [rsp+278h+arg_18]
0x180023a8b  add     rsp, 250h
0x180023a92  pop     r15
0x180023a94  pop     r14
0x180023a96  pop     rdi
0x180023a97  pop     rsi
0x180023a98  pop     rbp
0x180023a99  retn
```
