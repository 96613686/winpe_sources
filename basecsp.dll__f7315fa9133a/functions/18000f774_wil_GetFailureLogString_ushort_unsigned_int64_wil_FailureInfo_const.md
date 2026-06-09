# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000f774`
- end: `0x18000fa2a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800141e0`
- `0x180014870`
- `0x180019070`

## callees

- `0x18000a772`
- `0x18000f774`
- `0x1800144dc`
- `0x18002cfa0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f927`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f927`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f8a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f8a6`

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
          v7 = (const char *)&byte_180034110;
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
0x18000f774  mov     [rsp+arg_18], rbx
0x18000f779  push    rbp
0x18000f77a  push    rsi
0x18000f77b  push    rdi
0x18000f77c  push    r14
0x18000f77e  push    r15
0x18000f780  sub     rsp, 250h
0x18000f787  mov     rax, cs:__security_cookie
0x18000f78e  xor     rax, rsp
0x18000f791  mov     [rsp+278h+var_38], rax
0x18000f799  mov     rbx, r8
0x18000f79c  mov     rsi, rdx
0x18000f79f  mov     r14, rcx
0x18000f7a2  xor     r15d, r15d
0x18000f7a5  test    rdx, rdx
0x18000f7a8  jz      loc_18000FA01
0x18000f7ae  test    rcx, rcx
0x18000f7b1  jz      loc_18000FA01
0x18000f7b7  mov     [rcx], r15w
0x18000f7bb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f7c2  test    rax, rax
0x18000f7c5  jz      short loc_18000F7E8
0x18000f7c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000f7ce  jz      short loc_18000F7E8
0x18000f7d0  mov     r8, rdx
0x18000f7d3  mov     rdx, rcx
0x18000f7d6  mov     rcx, rbx
0x18000f7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7de  cmp     [r14], r15w
0x18000f7e2  jnz     loc_18000FA01
0x18000f7e8  mov     ecx, [rbx]
0x18000f7ea  mov     bpl, 8
0x18000f7ed  test    ecx, ecx
0x18000f7ef  jz      short loc_18000F83A
0x18000f7f1  sub     ecx, 1
0x18000f7f4  jz      short loc_18000F822
0x18000f7f6  sub     ecx, 1
0x18000f7f9  jz      short loc_18000F812
0x18000f7fb  cmp     ecx, 1
0x18000f7fe  jz      short loc_18000F809
0x18000f800  lea     rdi, byte_180034110
0x18000f807  jmp     short loc_18000F841
0x18000f809  lea     rdi, aFailfast; "FailFast"
0x18000f810  jmp     short loc_18000F841
0x18000f812  lea     rax, aLoghr; "LogHr"
0x18000f819  lea     rdi, aLognt; "LogNt"
0x18000f820  jmp     short loc_18000F830
0x18000f822  lea     rax, aReturnhr; "ReturnHr"
0x18000f829  lea     rdi, aReturnnt; "ReturnNt"
0x18000f830  test    [rbx+4], bpl
0x18000f834  cmovz   rdi, rax
0x18000f838  jmp     short loc_18000F841
0x18000f83a  lea     rdi, aException; "Exception"
0x18000f841  xor     edx, edx; Val
0x18000f843  mov     r8d, 200h; Size
0x18000f849  lea     rcx, [rsp+278h+Buffer]; void *
0x18000f84e  call    memset_0
0x18000f853  test    [rbx+4], bpl
0x18000f857  jz      short loc_18000F87C
0x18000f859  mov     ebp, [rbx+0Ch]
0x18000f85c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000f863  test    rax, rax
0x18000f866  jz      short loc_18000F8AC
0x18000f868  mov     r8d, 100h
0x18000f86e  lea     rdx, [rsp+278h+Buffer]
0x18000f873  mov     ecx, ebp
0x18000f875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f87a  jmp     short loc_18000F8AC
0x18000f87c  mov     ebp, [rbx+8]
0x18000f87f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000f884  mov     [rsp+278h+nSize], 100h; nSize
0x18000f88c  lea     rax, [rsp+278h+Buffer]
0x18000f891  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000f896  mov     r9d, 400h; dwLanguageId
0x18000f89c  mov     r8d, ebp; dwMessageId
0x18000f89f  xor     edx, edx; lpSource
0x18000f8a1  mov     ecx, 1200h; dwFlags
0x18000f8a6  call    cs:__imp_FormatMessageW
0x18000f8ac  lea     rsi, [r14+rsi*2]
0x18000f8b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000f8b4  mov     rax, [rbx+88h]
0x18000f8bb  mov     rcx, [rbx+80h]
0x18000f8c2  mov     rdx, rsi; unsigned __int16 *
0x18000f8c5  test    r9, r9
0x18000f8c8  jz      short loc_18000F8EC
0x18000f8ca  mov     [rsp+278h+Arguments], rax
0x18000f8cf  mov     qword ptr [rsp+278h+nSize], rcx
0x18000f8d4  mov     eax, [rbx+40h]
0x18000f8d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f8db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000f8e2  mov     rcx, r14; this
0x18000f8e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f8ea  jmp     short loc_18000F903
0x18000f8ec  mov     [rsp+278h+lpBuffer], rax
0x18000f8f1  mov     r9, rcx; unsigned __int16 *
0x18000f8f4  lea     r8, aHsP; "%hs!%p: "
0x18000f8fb  mov     rcx, r14; this
0x18000f8fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f903  mov     r14, rax
0x18000f906  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000f90d  test    r9, r9
0x18000f910  jz      short loc_18000F927
0x18000f912  lea     r8, aCallerP; "(caller: %p) "
0x18000f919  mov     rdx, rsi; unsigned __int16 *
0x18000f91c  mov     rcx, rax; this
0x18000f91f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f924  mov     r14, rax
0x18000f927  call    cs:__imp_GetCurrentThreadId
0x18000f92d  lea     rcx, [rsp+278h+Buffer]
0x18000f932  mov     [rsp+278h+var_240], rcx
0x18000f937  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000f93b  mov     [rsp+278h+nSize], eax
0x18000f93f  mov     eax, [rbx+44h]
0x18000f942  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f946  mov     r9, rdi; unsigned __int16 *
0x18000f949  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000f950  mov     rdx, rsi; unsigned __int16 *
0x18000f953  mov     rcx, r14; this
0x18000f956  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f95b  cmp     [rbx+18h], r15
0x18000f95f  jnz     short loc_18000F971
0x18000f961  cmp     [rbx+48h], r15
0x18000f965  jnz     short loc_18000F971
0x18000f967  cmp     [rbx+30h], r15
0x18000f96b  jz      loc_18000FA01
0x18000f971  lea     r8, asc_180034360; "    "
0x18000f978  mov     rdx, rsi; unsigned __int16 *
0x18000f97b  mov     rcx, rax; this
0x18000f97e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f983  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000f987  test    r9, r9
0x18000f98a  jz      short loc_18000F99E
0x18000f98c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000f993  mov     rdx, rsi; unsigned __int16 *
0x18000f996  mov     rcx, rax; this
0x18000f999  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f99e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000f9a2  test    r9, r9
0x18000f9a5  jz      short loc_18000F9B9
0x18000f9a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000f9ae  mov     rdx, rsi; unsigned __int16 *
0x18000f9b1  mov     rcx, rax; this
0x18000f9b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f9b9  mov     rcx, [rbx+28h]
0x18000f9bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000f9c1  mov     rdx, rsi; unsigned __int16 *
0x18000f9c4  test    rcx, rcx
0x18000f9c7  jz      short loc_18000F9DF
0x18000f9c9  mov     [rsp+278h+lpBuffer], rcx
0x18000f9ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000f9d5  mov     rcx, rax; this
0x18000f9d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f9dd  jmp     short loc_18000FA01
0x18000f9df  mov     rcx, rax; this
0x18000f9e2  test    r9, r9
0x18000f9e5  jz      short loc_18000F9F5
0x18000f9e7  lea     r8, aHs; "[%hs]\n"
0x18000f9ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f9f3  jmp     short loc_18000FA01
0x18000f9f5  lea     r8, asc_1800343D8; "\n"
0x18000f9fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fa01  xor     eax, eax
0x18000fa03  mov     rcx, [rsp+278h+var_38]
0x18000fa0b  xor     rcx, rsp; StackCookie
0x18000fa0e  call    __security_check_cookie
0x18000fa13  mov     rbx, [rsp+278h+arg_18]
0x18000fa1b  add     rsp, 250h
0x18000fa22  pop     r15
0x18000fa24  pop     r14
0x18000fa26  pop     rdi
0x18000fa27  pop     rsi
0x18000fa28  pop     rbp
0x18000fa29  retn
```
