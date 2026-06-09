# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800043bc`
- end: `0x18000467f`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800026b4`
- `0x18000292c`
- `0x180004c50`

## callees

- `0x1800043bc`
- `0x180004f64`
- `0x18000967e`
- `0x1800096b0`
- `0x18000a010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800044ee`
- `KERNEL32!FormatMessageW` at `0x1800044ee`
- `KERNEL32!GetCurrentThreadId` at `0x180004575`
- `KERNEL32!GetCurrentThreadId` at `0x180004575`

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
          v8 = (const char *)&dword_18000C894;
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
0x1800043bc  mov     [rsp+arg_18], rbx
0x1800043c1  push    rbp
0x1800043c2  push    rsi
0x1800043c3  push    rdi
0x1800043c4  push    r14
0x1800043c6  push    r15
0x1800043c8  sub     rsp, 250h
0x1800043cf  mov     rax, cs:__security_cookie
0x1800043d6  xor     rax, rsp
0x1800043d9  mov     [rsp+278h+var_38], rax
0x1800043e1  xor     r15d, r15d
0x1800043e4  mov     rbx, r8
0x1800043e7  mov     rsi, rdx
0x1800043ea  mov     r14, rcx
0x1800043ed  test    rdx, rdx
0x1800043f0  jz      loc_180004655
0x1800043f6  test    rcx, rcx
0x1800043f9  jz      loc_180004655
0x1800043ff  mov     rax, cs:g_pfnResultLoggingCallback
0x180004406  mov     [rcx], r15w
0x18000440a  test    rax, rax
0x18000440d  jz      short loc_180004430
0x18000440f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004416  jz      short loc_180004430
0x180004418  mov     r8, rdx
0x18000441b  mov     rdx, rcx
0x18000441e  mov     rcx, rbx
0x180004421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004426  cmp     [r14], r15w
0x18000442a  jnz     loc_180004655
0x180004430  mov     ecx, [rbx]
0x180004432  mov     bpl, 8
0x180004435  test    ecx, ecx
0x180004437  jz      short loc_180004482
0x180004439  sub     ecx, 1
0x18000443c  jz      short loc_18000446A
0x18000443e  sub     ecx, 1
0x180004441  jz      short loc_18000445A
0x180004443  cmp     ecx, 1
0x180004446  jz      short loc_180004451
0x180004448  lea     rdi, dword_18000C894
0x18000444f  jmp     short loc_180004489
0x180004451  lea     rdi, aFailfast; "FailFast"
0x180004458  jmp     short loc_180004489
0x18000445a  lea     rax, aLoghr; "LogHr"
0x180004461  lea     rdi, aLognt; "LogNt"
0x180004468  jmp     short loc_180004478
0x18000446a  lea     rax, aReturnhr; "ReturnHr"
0x180004471  lea     rdi, aReturnnt; "ReturnNt"
0x180004478  test    [rbx+4], bpl
0x18000447c  cmovz   rdi, rax
0x180004480  jmp     short loc_180004489
0x180004482  lea     rdi, aException; "Exception"
0x180004489  xor     edx, edx; Val
0x18000448b  lea     rcx, [rsp+278h+Buffer]; void *
0x180004490  mov     r8d, 200h; Size
0x180004496  call    memset_0
0x18000449b  test    [rbx+4], bpl
0x18000449f  jz      short loc_1800044C4
0x1800044a1  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800044a8  mov     ebp, [rbx+0Ch]
0x1800044ab  test    rax, rax
0x1800044ae  jz      short loc_1800044FA
0x1800044b0  mov     r8d, 100h
0x1800044b6  lea     rdx, [rsp+278h+Buffer]
0x1800044bb  mov     ecx, ebp
0x1800044bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044c2  jmp     short loc_1800044FA
0x1800044c4  mov     ebp, [rbx+8]
0x1800044c7  lea     rax, [rsp+278h+Buffer]
0x1800044cc  mov     [rsp+278h+Arguments], r15; Arguments
0x1800044d1  mov     r8d, ebp; dwMessageId
0x1800044d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800044dc  mov     r9d, 400h; dwLanguageId
0x1800044e2  xor     edx, edx; lpSource
0x1800044e4  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800044e9  mov     ecx, 1200h; dwFlags
0x1800044ee  call    cs:__imp_FormatMessageW
0x1800044f5  nop     dword ptr [rax+rax+00h]
0x1800044fa  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800044fe  lea     rsi, [r14+rsi*2]
0x180004502  mov     rax, [rbx+88h]
0x180004509  mov     rdx, rsi; unsigned __int16 *
0x18000450c  mov     rcx, [rbx+80h]
0x180004513  test    r9, r9
0x180004516  jz      short loc_18000453A
0x180004518  mov     [rsp+278h+Arguments], rax
0x18000451d  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004524  mov     eax, [rbx+40h]
0x180004527  mov     qword ptr [rsp+278h+nSize], rcx
0x18000452c  mov     rcx, r14; this
0x18000452f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004533  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004538  jmp     short loc_180004551
0x18000453a  mov     r9, rcx; unsigned __int16 *
0x18000453d  mov     [rsp+278h+lpBuffer], rax
0x180004542  mov     rcx, r14; this
0x180004545  lea     r8, aHsP; "%hs!%p: "
0x18000454c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004551  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004558  mov     r14, rax
0x18000455b  test    r9, r9
0x18000455e  jz      short loc_180004575
0x180004560  lea     r8, aCallerP; "(caller: %p) "
0x180004567  mov     rdx, rsi; unsigned __int16 *
0x18000456a  mov     rcx, rax; this
0x18000456d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004572  mov     r14, rax
0x180004575  call    cs:__imp_GetCurrentThreadId
0x18000457c  nop     dword ptr [rax+rax+00h]
0x180004581  lea     rcx, [rsp+278h+Buffer]
0x180004586  mov     r9, rdi; unsigned __int16 *
0x180004589  mov     [rsp+278h+var_240], rcx
0x18000458e  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004595  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004599  mov     rdx, rsi; unsigned __int16 *
0x18000459c  mov     [rsp+278h+nSize], eax
0x1800045a0  mov     rcx, r14; this
0x1800045a3  mov     eax, [rbx+44h]
0x1800045a6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800045aa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045af  cmp     [rbx+18h], r15
0x1800045b3  jnz     short loc_1800045C5
0x1800045b5  cmp     [rbx+48h], r15
0x1800045b9  jnz     short loc_1800045C5
0x1800045bb  cmp     [rbx+30h], r15
0x1800045bf  jz      loc_180004655
0x1800045c5  lea     r8, asc_18000C980; "    "
0x1800045cc  mov     rdx, rsi; unsigned __int16 *
0x1800045cf  mov     rcx, rax; this
0x1800045d2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045d7  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800045db  test    r9, r9
0x1800045de  jz      short loc_1800045F2
0x1800045e0  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800045e7  mov     rdx, rsi; unsigned __int16 *
0x1800045ea  mov     rcx, rax; this
0x1800045ed  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045f2  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800045f6  test    r9, r9
0x1800045f9  jz      short loc_18000460D
0x1800045fb  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004602  mov     rdx, rsi; unsigned __int16 *
0x180004605  mov     rcx, rax; this
0x180004608  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000460d  mov     rcx, [rbx+28h]
0x180004611  mov     rdx, rsi; unsigned __int16 *
0x180004614  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004618  test    rcx, rcx
0x18000461b  jz      short loc_180004633
0x18000461d  mov     [rsp+278h+lpBuffer], rcx
0x180004622  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004629  mov     rcx, rax; this
0x18000462c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004631  jmp     short loc_180004655
0x180004633  mov     rcx, rax; this
0x180004636  test    r9, r9
0x180004639  jz      short loc_180004649
0x18000463b  lea     r8, aHs; "[%hs]\n"
0x180004642  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004647  jmp     short loc_180004655
0x180004649  lea     r8, asc_18000C9F8; "\n"
0x180004650  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004655  xor     eax, eax
0x180004657  mov     rcx, [rsp+278h+var_38]
0x18000465f  xor     rcx, rsp; StackCookie
0x180004662  call    __security_check_cookie
0x180004667  mov     rbx, [rsp+278h+arg_18]
0x18000466f  add     rsp, 250h
0x180004676  pop     r15
0x180004678  pop     r14
0x18000467a  pop     rdi
0x18000467b  pop     rsi
0x18000467c  pop     rbp
0x18000467d  retn
```
