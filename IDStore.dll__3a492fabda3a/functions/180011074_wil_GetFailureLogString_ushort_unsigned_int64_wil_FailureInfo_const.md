# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180011074`
- end: `0x18001132a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180012610`
- `0x180016ea0`

## callees

- `0x180011074`
- `0x1800116d0`
- `0x180019722`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800111a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800111a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011227`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&word_18001F5B2;
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
0x180011074  mov     [rsp+arg_18], rbx
0x180011079  push    rbp
0x18001107a  push    rsi
0x18001107b  push    rdi
0x18001107c  push    r14
0x18001107e  push    r15
0x180011080  sub     rsp, 250h
0x180011087  mov     rax, cs:__security_cookie
0x18001108e  xor     rax, rsp
0x180011091  mov     [rsp+278h+var_38], rax
0x180011099  mov     rbx, r8
0x18001109c  mov     rsi, rdx
0x18001109f  mov     r14, rcx
0x1800110a2  xor     r15d, r15d
0x1800110a5  test    rdx, rdx
0x1800110a8  jz      loc_180011301
0x1800110ae  test    rcx, rcx
0x1800110b1  jz      loc_180011301
0x1800110b7  mov     [rcx], r15w
0x1800110bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800110c2  test    rax, rax
0x1800110c5  jz      short loc_1800110E8
0x1800110c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800110ce  jz      short loc_1800110E8
0x1800110d0  mov     r8, rdx
0x1800110d3  mov     rdx, rcx
0x1800110d6  mov     rcx, rbx
0x1800110d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110de  cmp     [r14], r15w
0x1800110e2  jnz     loc_180011301
0x1800110e8  mov     ecx, [rbx]
0x1800110ea  mov     bpl, 8
0x1800110ed  test    ecx, ecx
0x1800110ef  jz      short loc_18001113A
0x1800110f1  sub     ecx, 1
0x1800110f4  jz      short loc_180011122
0x1800110f6  sub     ecx, 1
0x1800110f9  jz      short loc_180011112
0x1800110fb  cmp     ecx, 1
0x1800110fe  jz      short loc_180011109
0x180011100  lea     rdi, word_18001F5B2
0x180011107  jmp     short loc_180011141
0x180011109  lea     rdi, aFailfast; "FailFast"
0x180011110  jmp     short loc_180011141
0x180011112  lea     rax, aLoghr; "LogHr"
0x180011119  lea     rdi, aLognt; "LogNt"
0x180011120  jmp     short loc_180011130
0x180011122  lea     rax, aReturnhr; "ReturnHr"
0x180011129  lea     rdi, aReturnnt; "ReturnNt"
0x180011130  test    [rbx+4], bpl
0x180011134  cmovz   rdi, rax
0x180011138  jmp     short loc_180011141
0x18001113a  lea     rdi, aException; "Exception"
0x180011141  xor     edx, edx; Val
0x180011143  mov     r8d, 200h; Size
0x180011149  lea     rcx, [rsp+278h+Buffer]; void *
0x18001114e  call    memset_0
0x180011153  test    [rbx+4], bpl
0x180011157  jz      short loc_18001117C
0x180011159  mov     ebp, [rbx+0Ch]
0x18001115c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180011163  test    rax, rax
0x180011166  jz      short loc_1800111AC
0x180011168  mov     r8d, 100h
0x18001116e  lea     rdx, [rsp+278h+Buffer]
0x180011173  mov     ecx, ebp
0x180011175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001117a  jmp     short loc_1800111AC
0x18001117c  mov     ebp, [rbx+8]
0x18001117f  mov     [rsp+278h+Arguments], r15; Arguments
0x180011184  mov     [rsp+278h+nSize], 100h; nSize
0x18001118c  lea     rax, [rsp+278h+Buffer]
0x180011191  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180011196  mov     r9d, 400h; dwLanguageId
0x18001119c  mov     r8d, ebp; dwMessageId
0x18001119f  xor     edx, edx; lpSource
0x1800111a1  mov     ecx, 1200h; dwFlags
0x1800111a6  call    cs:__imp_FormatMessageW
0x1800111ac  lea     rsi, [r14+rsi*2]
0x1800111b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800111b4  mov     rax, [rbx+88h]
0x1800111bb  mov     rcx, [rbx+80h]
0x1800111c2  mov     rdx, rsi; unsigned __int16 *
0x1800111c5  test    r9, r9
0x1800111c8  jz      short loc_1800111EC
0x1800111ca  mov     [rsp+278h+Arguments], rax
0x1800111cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800111d4  mov     eax, [rbx+40h]
0x1800111d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800111db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800111e2  mov     rcx, r14; this
0x1800111e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800111ea  jmp     short loc_180011203
0x1800111ec  mov     [rsp+278h+lpBuffer], rax
0x1800111f1  mov     r9, rcx; unsigned __int16 *
0x1800111f4  lea     r8, aHsP; "%hs!%p: "
0x1800111fb  mov     rcx, r14; this
0x1800111fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011203  mov     r14, rax
0x180011206  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001120d  test    r9, r9
0x180011210  jz      short loc_180011227
0x180011212  lea     r8, aCallerP; "(caller: %p) "
0x180011219  mov     rdx, rsi; unsigned __int16 *
0x18001121c  mov     rcx, rax; this
0x18001121f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011224  mov     r14, rax
0x180011227  call    cs:__imp_GetCurrentThreadId
0x18001122d  lea     rcx, [rsp+278h+Buffer]
0x180011232  mov     [rsp+278h+var_240], rcx
0x180011237  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001123b  mov     [rsp+278h+nSize], eax
0x18001123f  mov     eax, [rbx+44h]
0x180011242  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011246  mov     r9, rdi; unsigned __int16 *
0x180011249  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180011250  mov     rdx, rsi; unsigned __int16 *
0x180011253  mov     rcx, r14; this
0x180011256  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001125b  cmp     [rbx+18h], r15
0x18001125f  jnz     short loc_180011271
0x180011261  cmp     [rbx+48h], r15
0x180011265  jnz     short loc_180011271
0x180011267  cmp     [rbx+30h], r15
0x18001126b  jz      loc_180011301
0x180011271  lea     r8, asc_18001F6B8; "    "
0x180011278  mov     rdx, rsi; unsigned __int16 *
0x18001127b  mov     rcx, rax; this
0x18001127e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011283  mov     r9, [rbx+18h]; unsigned __int16 *
0x180011287  test    r9, r9
0x18001128a  jz      short loc_18001129E
0x18001128c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180011293  mov     rdx, rsi; unsigned __int16 *
0x180011296  mov     rcx, rax; this
0x180011299  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001129e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800112a2  test    r9, r9
0x1800112a5  jz      short loc_1800112B9
0x1800112a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800112ae  mov     rdx, rsi; unsigned __int16 *
0x1800112b1  mov     rcx, rax; this
0x1800112b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800112b9  mov     rcx, [rbx+28h]
0x1800112bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800112c1  mov     rdx, rsi; unsigned __int16 *
0x1800112c4  test    rcx, rcx
0x1800112c7  jz      short loc_1800112DF
0x1800112c9  mov     [rsp+278h+lpBuffer], rcx
0x1800112ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800112d5  mov     rcx, rax; this
0x1800112d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800112dd  jmp     short loc_180011301
0x1800112df  mov     rcx, rax; this
0x1800112e2  test    r9, r9
0x1800112e5  jz      short loc_1800112F5
0x1800112e7  lea     r8, aHs; "[%hs]\n"
0x1800112ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800112f3  jmp     short loc_180011301
0x1800112f5  lea     r8, asc_18001F730; "\n"
0x1800112fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011301  xor     eax, eax
0x180011303  mov     rcx, [rsp+278h+var_38]
0x18001130b  xor     rcx, rsp; StackCookie
0x18001130e  call    __security_check_cookie
0x180011313  mov     rbx, [rsp+278h+arg_18]
0x18001131b  add     rsp, 250h
0x180011322  pop     r15
0x180011324  pop     r14
0x180011326  pop     rdi
0x180011327  pop     rsi
0x180011328  pop     rbp
0x180011329  retn
```
