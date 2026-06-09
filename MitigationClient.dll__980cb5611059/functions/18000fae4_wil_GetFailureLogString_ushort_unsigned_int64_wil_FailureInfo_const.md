# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000fae4`
- end: `0x18000fd9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d6cc`
- `0x1800107ac`
- `0x180010e8c`
- `0x180014130`

## callees

- `0x18000a6e0`
- `0x18000b2b4`
- `0x18000fae4`
- `0x180010aac`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fc97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fc97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000fc16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000fc16`

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
          v7 = qword_1800612A8;
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
0x18000fae4  mov     [rsp+arg_18], rbx
0x18000fae9  push    rbp
0x18000faea  push    rsi
0x18000faeb  push    rdi
0x18000faec  push    r14
0x18000faee  push    r15
0x18000faf0  sub     rsp, 250h
0x18000faf7  mov     rax, cs:__security_cookie
0x18000fafe  xor     rax, rsp
0x18000fb01  mov     [rsp+278h+var_38], rax
0x18000fb09  mov     rbx, r8
0x18000fb0c  mov     rsi, rdx
0x18000fb0f  mov     r14, rcx
0x18000fb12  xor     r15d, r15d
0x18000fb15  test    rdx, rdx
0x18000fb18  jz      loc_18000FD71
0x18000fb1e  test    rcx, rcx
0x18000fb21  jz      loc_18000FD71
0x18000fb27  mov     [rcx], r15w
0x18000fb2b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fb32  test    rax, rax
0x18000fb35  jz      short loc_18000FB58
0x18000fb37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000fb3e  jz      short loc_18000FB58
0x18000fb40  mov     r8, rdx
0x18000fb43  mov     rdx, rcx
0x18000fb46  mov     rcx, rbx
0x18000fb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb4e  cmp     [r14], r15w
0x18000fb52  jnz     loc_18000FD71
0x18000fb58  mov     ecx, [rbx]
0x18000fb5a  mov     bpl, 8
0x18000fb5d  test    ecx, ecx
0x18000fb5f  jz      short loc_18000FBAA
0x18000fb61  sub     ecx, 1
0x18000fb64  jz      short loc_18000FB92
0x18000fb66  sub     ecx, 1
0x18000fb69  jz      short loc_18000FB82
0x18000fb6b  cmp     ecx, 1
0x18000fb6e  jz      short loc_18000FB79
0x18000fb70  lea     rdi, qword_1800612A8
0x18000fb77  jmp     short loc_18000FBB1
0x18000fb79  lea     rdi, aFailfast; "FailFast"
0x18000fb80  jmp     short loc_18000FBB1
0x18000fb82  lea     rax, aLoghr; "LogHr"
0x18000fb89  lea     rdi, aLognt; "LogNt"
0x18000fb90  jmp     short loc_18000FBA0
0x18000fb92  lea     rax, aReturnhr; "ReturnHr"
0x18000fb99  lea     rdi, aReturnnt; "ReturnNt"
0x18000fba0  test    [rbx+4], bpl
0x18000fba4  cmovz   rdi, rax
0x18000fba8  jmp     short loc_18000FBB1
0x18000fbaa  lea     rdi, aException; "Exception"
0x18000fbb1  xor     edx, edx; Val
0x18000fbb3  mov     r8d, 200h; Size
0x18000fbb9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000fbbe  call    memset_0
0x18000fbc3  test    [rbx+4], bpl
0x18000fbc7  jz      short loc_18000FBEC
0x18000fbc9  mov     ebp, [rbx+0Ch]
0x18000fbcc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000fbd3  test    rax, rax
0x18000fbd6  jz      short loc_18000FC1C
0x18000fbd8  mov     r8d, 100h
0x18000fbde  lea     rdx, [rsp+278h+Buffer]
0x18000fbe3  mov     ecx, ebp
0x18000fbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbea  jmp     short loc_18000FC1C
0x18000fbec  mov     ebp, [rbx+8]
0x18000fbef  mov     [rsp+278h+Arguments], r15; Arguments
0x18000fbf4  mov     [rsp+278h+nSize], 100h; nSize
0x18000fbfc  lea     rax, [rsp+278h+Buffer]
0x18000fc01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000fc06  mov     r9d, 400h; dwLanguageId
0x18000fc0c  mov     r8d, ebp; dwMessageId
0x18000fc0f  xor     edx, edx; lpSource
0x18000fc11  mov     ecx, 1200h; dwFlags
0x18000fc16  call    cs:__imp_FormatMessageW
0x18000fc1c  lea     rsi, [r14+rsi*2]
0x18000fc20  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000fc24  mov     rax, [rbx+88h]
0x18000fc2b  mov     rcx, [rbx+80h]
0x18000fc32  mov     rdx, rsi; unsigned __int16 *
0x18000fc35  test    r9, r9
0x18000fc38  jz      short loc_18000FC5C
0x18000fc3a  mov     [rsp+278h+Arguments], rax
0x18000fc3f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000fc44  mov     eax, [rbx+40h]
0x18000fc47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000fc4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000fc52  mov     rcx, r14; this
0x18000fc55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fc5a  jmp     short loc_18000FC73
0x18000fc5c  mov     [rsp+278h+lpBuffer], rax
0x18000fc61  mov     r9, rcx; unsigned __int16 *
0x18000fc64  lea     r8, aHsP; "%hs!%p: "
0x18000fc6b  mov     rcx, r14; this
0x18000fc6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fc73  mov     r14, rax
0x18000fc76  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000fc7d  test    r9, r9
0x18000fc80  jz      short loc_18000FC97
0x18000fc82  lea     r8, aCallerP; "(caller: %p) "
0x18000fc89  mov     rdx, rsi; unsigned __int16 *
0x18000fc8c  mov     rcx, rax; this
0x18000fc8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fc94  mov     r14, rax
0x18000fc97  call    cs:__imp_GetCurrentThreadId
0x18000fc9d  lea     rcx, [rsp+278h+Buffer]
0x18000fca2  mov     [rsp+278h+var_240], rcx
0x18000fca7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000fcab  mov     [rsp+278h+nSize], eax
0x18000fcaf  mov     eax, [rbx+44h]
0x18000fcb2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000fcb6  mov     r9, rdi; unsigned __int16 *
0x18000fcb9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000fcc0  mov     rdx, rsi; unsigned __int16 *
0x18000fcc3  mov     rcx, r14; this
0x18000fcc6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fccb  cmp     [rbx+18h], r15
0x18000fccf  jnz     short loc_18000FCE1
0x18000fcd1  cmp     [rbx+48h], r15
0x18000fcd5  jnz     short loc_18000FCE1
0x18000fcd7  cmp     [rbx+30h], r15
0x18000fcdb  jz      loc_18000FD71
0x18000fce1  lea     r8, asc_1800613C8; "    "
0x18000fce8  mov     rdx, rsi; unsigned __int16 *
0x18000fceb  mov     rcx, rax; this
0x18000fcee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fcf3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000fcf7  test    r9, r9
0x18000fcfa  jz      short loc_18000FD0E
0x18000fcfc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000fd03  mov     rdx, rsi; unsigned __int16 *
0x18000fd06  mov     rcx, rax; this
0x18000fd09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fd0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000fd12  test    r9, r9
0x18000fd15  jz      short loc_18000FD29
0x18000fd17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000fd1e  mov     rdx, rsi; unsigned __int16 *
0x18000fd21  mov     rcx, rax; this
0x18000fd24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fd29  mov     rcx, [rbx+28h]
0x18000fd2d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000fd31  mov     rdx, rsi; unsigned __int16 *
0x18000fd34  test    rcx, rcx
0x18000fd37  jz      short loc_18000FD4F
0x18000fd39  mov     [rsp+278h+lpBuffer], rcx
0x18000fd3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000fd45  mov     rcx, rax; this
0x18000fd48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fd4d  jmp     short loc_18000FD71
0x18000fd4f  mov     rcx, rax; this
0x18000fd52  test    r9, r9
0x18000fd55  jz      short loc_18000FD65
0x18000fd57  lea     r8, aHs; "[%hs]\n"
0x18000fd5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fd63  jmp     short loc_18000FD71
0x18000fd65  lea     r8, asc_180061440; "\n"
0x18000fd6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000fd71  xor     eax, eax
0x18000fd73  mov     rcx, [rsp+278h+var_38]
0x18000fd7b  xor     rcx, rsp; StackCookie
0x18000fd7e  call    __security_check_cookie
0x18000fd83  mov     rbx, [rsp+278h+arg_18]
0x18000fd8b  add     rsp, 250h
0x18000fd92  pop     r15
0x18000fd94  pop     r14
0x18000fd96  pop     rdi
0x18000fd97  pop     rsi
0x18000fd98  pop     rbp
0x18000fd99  retn
```
