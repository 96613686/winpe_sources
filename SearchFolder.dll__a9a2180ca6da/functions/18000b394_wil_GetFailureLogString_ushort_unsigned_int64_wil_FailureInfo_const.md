# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b394`
- end: `0x18000b64a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180008b4c`
- `0x18000bf30`
- `0x18000c5ec`
- `0x180010330`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x18000b394`
- `0x18000c230`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b547`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b547`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b4c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b4c6`

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
          v7 = MultiByteStr;
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
0x18000b394  mov     [rsp+arg_18], rbx
0x18000b399  push    rbp
0x18000b39a  push    rsi
0x18000b39b  push    rdi
0x18000b39c  push    r14
0x18000b39e  push    r15
0x18000b3a0  sub     rsp, 250h
0x18000b3a7  mov     rax, cs:__security_cookie
0x18000b3ae  xor     rax, rsp
0x18000b3b1  mov     [rsp+278h+var_38], rax
0x18000b3b9  mov     rbx, r8
0x18000b3bc  mov     rsi, rdx
0x18000b3bf  mov     r14, rcx
0x18000b3c2  xor     r15d, r15d
0x18000b3c5  test    rdx, rdx
0x18000b3c8  jz      loc_18000B621
0x18000b3ce  test    rcx, rcx
0x18000b3d1  jz      loc_18000B621
0x18000b3d7  mov     [rcx], r15w
0x18000b3db  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b3e2  test    rax, rax
0x18000b3e5  jz      short loc_18000B408
0x18000b3e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b3ee  jz      short loc_18000B408
0x18000b3f0  mov     r8, rdx
0x18000b3f3  mov     rdx, rcx
0x18000b3f6  mov     rcx, rbx
0x18000b3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3fe  cmp     [r14], r15w
0x18000b402  jnz     loc_18000B621
0x18000b408  mov     ecx, [rbx]
0x18000b40a  mov     bpl, 8
0x18000b40d  test    ecx, ecx
0x18000b40f  jz      short loc_18000B45A
0x18000b411  sub     ecx, 1
0x18000b414  jz      short loc_18000B442
0x18000b416  sub     ecx, 1
0x18000b419  jz      short loc_18000B432
0x18000b41b  cmp     ecx, 1
0x18000b41e  jz      short loc_18000B429
0x18000b420  lea     rdi, MultiByteStr
0x18000b427  jmp     short loc_18000B461
0x18000b429  lea     rdi, aFailfast; "FailFast"
0x18000b430  jmp     short loc_18000B461
0x18000b432  lea     rax, aLoghr; "LogHr"
0x18000b439  lea     rdi, aLognt; "LogNt"
0x18000b440  jmp     short loc_18000B450
0x18000b442  lea     rax, aReturnhr; "ReturnHr"
0x18000b449  lea     rdi, aReturnnt; "ReturnNt"
0x18000b450  test    [rbx+4], bpl
0x18000b454  cmovz   rdi, rax
0x18000b458  jmp     short loc_18000B461
0x18000b45a  lea     rdi, aException; "Exception"
0x18000b461  xor     edx, edx; Val
0x18000b463  mov     r8d, 200h; Size
0x18000b469  lea     rcx, [rsp+278h+Buffer]; void *
0x18000b46e  call    memset_0
0x18000b473  test    [rbx+4], bpl
0x18000b477  jz      short loc_18000B49C
0x18000b479  mov     ebp, [rbx+0Ch]
0x18000b47c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000b483  test    rax, rax
0x18000b486  jz      short loc_18000B4CC
0x18000b488  mov     r8d, 100h
0x18000b48e  lea     rdx, [rsp+278h+Buffer]
0x18000b493  mov     ecx, ebp
0x18000b495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b49a  jmp     short loc_18000B4CC
0x18000b49c  mov     ebp, [rbx+8]
0x18000b49f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000b4a4  mov     [rsp+278h+nSize], 100h; nSize
0x18000b4ac  lea     rax, [rsp+278h+Buffer]
0x18000b4b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000b4b6  mov     r9d, 400h; dwLanguageId
0x18000b4bc  mov     r8d, ebp; dwMessageId
0x18000b4bf  xor     edx, edx; lpSource
0x18000b4c1  mov     ecx, 1200h; dwFlags
0x18000b4c6  call    cs:__imp_FormatMessageW
0x18000b4cc  lea     rsi, [r14+rsi*2]
0x18000b4d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000b4d4  mov     rax, [rbx+88h]
0x18000b4db  mov     rcx, [rbx+80h]
0x18000b4e2  mov     rdx, rsi; unsigned __int16 *
0x18000b4e5  test    r9, r9
0x18000b4e8  jz      short loc_18000B50C
0x18000b4ea  mov     [rsp+278h+Arguments], rax
0x18000b4ef  mov     qword ptr [rsp+278h+nSize], rcx
0x18000b4f4  mov     eax, [rbx+40h]
0x18000b4f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b4fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000b502  mov     rcx, r14; this
0x18000b505  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b50a  jmp     short loc_18000B523
0x18000b50c  mov     [rsp+278h+lpBuffer], rax
0x18000b511  mov     r9, rcx; unsigned __int16 *
0x18000b514  lea     r8, aHsP; "%hs!%p: "
0x18000b51b  mov     rcx, r14; this
0x18000b51e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b523  mov     r14, rax
0x18000b526  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000b52d  test    r9, r9
0x18000b530  jz      short loc_18000B547
0x18000b532  lea     r8, aCallerP; "(caller: %p) "
0x18000b539  mov     rdx, rsi; unsigned __int16 *
0x18000b53c  mov     rcx, rax; this
0x18000b53f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b544  mov     r14, rax
0x18000b547  call    cs:__imp_GetCurrentThreadId
0x18000b54d  lea     rcx, [rsp+278h+Buffer]
0x18000b552  mov     [rsp+278h+var_240], rcx
0x18000b557  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000b55b  mov     [rsp+278h+nSize], eax
0x18000b55f  mov     eax, [rbx+44h]
0x18000b562  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b566  mov     r9, rdi; unsigned __int16 *
0x18000b569  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b570  mov     rdx, rsi; unsigned __int16 *
0x18000b573  mov     rcx, r14; this
0x18000b576  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b57b  cmp     [rbx+18h], r15
0x18000b57f  jnz     short loc_18000B591
0x18000b581  cmp     [rbx+48h], r15
0x18000b585  jnz     short loc_18000B591
0x18000b587  cmp     [rbx+30h], r15
0x18000b58b  jz      loc_18000B621
0x18000b591  lea     r8, asc_180058B18; "    "
0x18000b598  mov     rdx, rsi; unsigned __int16 *
0x18000b59b  mov     rcx, rax; this
0x18000b59e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b5a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000b5a7  test    r9, r9
0x18000b5aa  jz      short loc_18000B5BE
0x18000b5ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000b5b3  mov     rdx, rsi; unsigned __int16 *
0x18000b5b6  mov     rcx, rax; this
0x18000b5b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b5be  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000b5c2  test    r9, r9
0x18000b5c5  jz      short loc_18000B5D9
0x18000b5c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000b5ce  mov     rdx, rsi; unsigned __int16 *
0x18000b5d1  mov     rcx, rax; this
0x18000b5d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b5d9  mov     rcx, [rbx+28h]
0x18000b5dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000b5e1  mov     rdx, rsi; unsigned __int16 *
0x18000b5e4  test    rcx, rcx
0x18000b5e7  jz      short loc_18000B5FF
0x18000b5e9  mov     [rsp+278h+lpBuffer], rcx
0x18000b5ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000b5f5  mov     rcx, rax; this
0x18000b5f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b5fd  jmp     short loc_18000B621
0x18000b5ff  mov     rcx, rax; this
0x18000b602  test    r9, r9
0x18000b605  jz      short loc_18000B615
0x18000b607  lea     r8, aHs; "[%hs]\n"
0x18000b60e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b613  jmp     short loc_18000B621
0x18000b615  lea     r8, asc_180058B90; "\n"
0x18000b61c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b621  xor     eax, eax
0x18000b623  mov     rcx, [rsp+278h+var_38]
0x18000b62b  xor     rcx, rsp; StackCookie
0x18000b62e  call    __security_check_cookie
0x18000b633  mov     rbx, [rsp+278h+arg_18]
0x18000b63b  add     rsp, 250h
0x18000b642  pop     r15
0x18000b644  pop     r14
0x18000b646  pop     rdi
0x18000b647  pop     rsi
0x18000b648  pop     rbp
0x18000b649  retn
```
