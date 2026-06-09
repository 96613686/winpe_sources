# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180015e04`
- end: `0x1800160ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800134a0`
- `0x180013720`
- `0x1800139cc`
- `0x18001a070`
- `0x18001f524`
- `0x1800689b1`
- `0x180068ae5`
- `0x18006d791`
- `0x18006da0e`

## callees

- `0x180007660`
- `0x18000856c`
- `0x180015e04`
- `0x180016920`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015fb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015fb7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180015f36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180015f36`

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
          v7 = (const char *)&word_180078692;
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
0x180015e04  mov     [rsp+arg_18], rbx
0x180015e09  push    rbp
0x180015e0a  push    rsi
0x180015e0b  push    rdi
0x180015e0c  push    r14
0x180015e0e  push    r15
0x180015e10  sub     rsp, 250h
0x180015e17  mov     rax, cs:__security_cookie
0x180015e1e  xor     rax, rsp
0x180015e21  mov     [rsp+278h+var_38], rax
0x180015e29  mov     rbx, r8
0x180015e2c  mov     rsi, rdx
0x180015e2f  mov     r14, rcx
0x180015e32  xor     r15d, r15d
0x180015e35  test    rdx, rdx
0x180015e38  jz      loc_180016091
0x180015e3e  test    rcx, rcx
0x180015e41  jz      loc_180016091
0x180015e47  mov     [rcx], r15w
0x180015e4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180015e52  test    rax, rax
0x180015e55  jz      short loc_180015E78
0x180015e57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180015e5e  jz      short loc_180015E78
0x180015e60  mov     r8, rdx
0x180015e63  mov     rdx, rcx
0x180015e66  mov     rcx, rbx
0x180015e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e6e  cmp     [r14], r15w
0x180015e72  jnz     loc_180016091
0x180015e78  mov     ecx, [rbx]
0x180015e7a  mov     bpl, 8
0x180015e7d  test    ecx, ecx
0x180015e7f  jz      short loc_180015ECA
0x180015e81  sub     ecx, 1
0x180015e84  jz      short loc_180015EB2
0x180015e86  sub     ecx, 1
0x180015e89  jz      short loc_180015EA2
0x180015e8b  cmp     ecx, 1
0x180015e8e  jz      short loc_180015E99
0x180015e90  lea     rdi, word_180078692
0x180015e97  jmp     short loc_180015ED1
0x180015e99  lea     rdi, aFailfast; "FailFast"
0x180015ea0  jmp     short loc_180015ED1
0x180015ea2  lea     rax, aLoghr; "LogHr"
0x180015ea9  lea     rdi, aLognt; "LogNt"
0x180015eb0  jmp     short loc_180015EC0
0x180015eb2  lea     rax, aReturnhr; "ReturnHr"
0x180015eb9  lea     rdi, aReturnnt; "ReturnNt"
0x180015ec0  test    [rbx+4], bpl
0x180015ec4  cmovz   rdi, rax
0x180015ec8  jmp     short loc_180015ED1
0x180015eca  lea     rdi, aException; "Exception"
0x180015ed1  xor     edx, edx; Val
0x180015ed3  mov     r8d, 200h; Size
0x180015ed9  lea     rcx, [rsp+278h+Buffer]; void *
0x180015ede  call    memset_0
0x180015ee3  test    [rbx+4], bpl
0x180015ee7  jz      short loc_180015F0C
0x180015ee9  mov     ebp, [rbx+0Ch]
0x180015eec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180015ef3  test    rax, rax
0x180015ef6  jz      short loc_180015F3C
0x180015ef8  mov     r8d, 100h
0x180015efe  lea     rdx, [rsp+278h+Buffer]
0x180015f03  mov     ecx, ebp
0x180015f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f0a  jmp     short loc_180015F3C
0x180015f0c  mov     ebp, [rbx+8]
0x180015f0f  mov     [rsp+278h+Arguments], r15; Arguments
0x180015f14  mov     [rsp+278h+nSize], 100h; nSize
0x180015f1c  lea     rax, [rsp+278h+Buffer]
0x180015f21  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180015f26  mov     r9d, 400h; dwLanguageId
0x180015f2c  mov     r8d, ebp; dwMessageId
0x180015f2f  xor     edx, edx; lpSource
0x180015f31  mov     ecx, 1200h; dwFlags
0x180015f36  call    cs:__imp_FormatMessageW
0x180015f3c  lea     rsi, [r14+rsi*2]
0x180015f40  mov     r9, [rbx+38h]; unsigned __int16 *
0x180015f44  mov     rax, [rbx+88h]
0x180015f4b  mov     rcx, [rbx+80h]
0x180015f52  mov     rdx, rsi; unsigned __int16 *
0x180015f55  test    r9, r9
0x180015f58  jz      short loc_180015F7C
0x180015f5a  mov     [rsp+278h+Arguments], rax
0x180015f5f  mov     qword ptr [rsp+278h+nSize], rcx
0x180015f64  mov     eax, [rbx+40h]
0x180015f67  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180015f6b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180015f72  mov     rcx, r14; this
0x180015f75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015f7a  jmp     short loc_180015F93
0x180015f7c  mov     [rsp+278h+lpBuffer], rax
0x180015f81  mov     r9, rcx; unsigned __int16 *
0x180015f84  lea     r8, aHsP; "%hs!%p: "
0x180015f8b  mov     rcx, r14; this
0x180015f8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015f93  mov     r14, rax
0x180015f96  mov     r9, [rbx+90h]; unsigned __int16 *
0x180015f9d  test    r9, r9
0x180015fa0  jz      short loc_180015FB7
0x180015fa2  lea     r8, aCallerP; "(caller: %p) "
0x180015fa9  mov     rdx, rsi; unsigned __int16 *
0x180015fac  mov     rcx, rax; this
0x180015faf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015fb4  mov     r14, rax
0x180015fb7  call    cs:__imp_GetCurrentThreadId
0x180015fbd  lea     rcx, [rsp+278h+Buffer]
0x180015fc2  mov     [rsp+278h+var_240], rcx
0x180015fc7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180015fcb  mov     [rsp+278h+nSize], eax
0x180015fcf  mov     eax, [rbx+44h]
0x180015fd2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180015fd6  mov     r9, rdi; unsigned __int16 *
0x180015fd9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180015fe0  mov     rdx, rsi; unsigned __int16 *
0x180015fe3  mov     rcx, r14; this
0x180015fe6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015feb  cmp     [rbx+18h], r15
0x180015fef  jnz     short loc_180016001
0x180015ff1  cmp     [rbx+48h], r15
0x180015ff5  jnz     short loc_180016001
0x180015ff7  cmp     [rbx+30h], r15
0x180015ffb  jz      loc_180016091
0x180016001  lea     r8, asc_180078780; "    "
0x180016008  mov     rdx, rsi; unsigned __int16 *
0x18001600b  mov     rcx, rax; this
0x18001600e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016013  mov     r9, [rbx+18h]; unsigned __int16 *
0x180016017  test    r9, r9
0x18001601a  jz      short loc_18001602E
0x18001601c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180016023  mov     rdx, rsi; unsigned __int16 *
0x180016026  mov     rcx, rax; this
0x180016029  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001602e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180016032  test    r9, r9
0x180016035  jz      short loc_180016049
0x180016037  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001603e  mov     rdx, rsi; unsigned __int16 *
0x180016041  mov     rcx, rax; this
0x180016044  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016049  mov     rcx, [rbx+28h]
0x18001604d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180016051  mov     rdx, rsi; unsigned __int16 *
0x180016054  test    rcx, rcx
0x180016057  jz      short loc_18001606F
0x180016059  mov     [rsp+278h+lpBuffer], rcx
0x18001605e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180016065  mov     rcx, rax; this
0x180016068  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001606d  jmp     short loc_180016091
0x18001606f  mov     rcx, rax; this
0x180016072  test    r9, r9
0x180016075  jz      short loc_180016085
0x180016077  lea     r8, aHs; "[%hs]\n"
0x18001607e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016083  jmp     short loc_180016091
0x180016085  lea     r8, asc_1800787F8; "\n"
0x18001608c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016091  xor     eax, eax
0x180016093  mov     rcx, [rsp+278h+var_38]
0x18001609b  xor     rcx, rsp; StackCookie
0x18001609e  call    __security_check_cookie
0x1800160a3  mov     rbx, [rsp+278h+arg_18]
0x1800160ab  add     rsp, 250h
0x1800160b2  pop     r15
0x1800160b4  pop     r14
0x1800160b6  pop     rdi
0x1800160b7  pop     rsi
0x1800160b8  pop     rbp
0x1800160b9  retn
```
