# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800c3fc4`
- end: `0x1800c427a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18008e6cc`
- `0x1800c4fb0`
- `0x1800c7b10`

## callees

- `0x1800bb480`
- `0x1800bc094`
- `0x1800c3fc4`
- `0x1800c4d14`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c4177`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c4177`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800c40f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800c40f6`

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
          v7 = Src;
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
0x1800c3fc4  mov     [rsp+arg_18], rbx
0x1800c3fc9  push    rbp
0x1800c3fca  push    rsi
0x1800c3fcb  push    rdi
0x1800c3fcc  push    r14
0x1800c3fce  push    r15
0x1800c3fd0  sub     rsp, 250h
0x1800c3fd7  mov     rax, cs:__security_cookie
0x1800c3fde  xor     rax, rsp
0x1800c3fe1  mov     [rsp+278h+var_38], rax
0x1800c3fe9  mov     rbx, r8
0x1800c3fec  mov     rsi, rdx
0x1800c3fef  mov     r14, rcx
0x1800c3ff2  xor     r15d, r15d
0x1800c3ff5  test    rdx, rdx
0x1800c3ff8  jz      loc_1800C4251
0x1800c3ffe  test    rcx, rcx
0x1800c4001  jz      loc_1800C4251
0x1800c4007  mov     [rcx], r15w
0x1800c400b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800c4012  test    rax, rax
0x1800c4015  jz      short loc_1800C4038
0x1800c4017  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800c401e  jz      short loc_1800C4038
0x1800c4020  mov     r8, rdx
0x1800c4023  mov     rdx, rcx
0x1800c4026  mov     rcx, rbx
0x1800c4029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c402e  cmp     [r14], r15w
0x1800c4032  jnz     loc_1800C4251
0x1800c4038  mov     ecx, [rbx]
0x1800c403a  mov     bpl, 8
0x1800c403d  test    ecx, ecx
0x1800c403f  jz      short loc_1800C408A
0x1800c4041  sub     ecx, 1
0x1800c4044  jz      short loc_1800C4072
0x1800c4046  sub     ecx, 1
0x1800c4049  jz      short loc_1800C4062
0x1800c404b  cmp     ecx, 1
0x1800c404e  jz      short loc_1800C4059
0x1800c4050  lea     rdi, Src
0x1800c4057  jmp     short loc_1800C4091
0x1800c4059  lea     rdi, aFailfast; "FailFast"
0x1800c4060  jmp     short loc_1800C4091
0x1800c4062  lea     rax, aLoghr; "LogHr"
0x1800c4069  lea     rdi, aLognt; "LogNt"
0x1800c4070  jmp     short loc_1800C4080
0x1800c4072  lea     rax, aReturnhr; "ReturnHr"
0x1800c4079  lea     rdi, aReturnnt; "ReturnNt"
0x1800c4080  test    [rbx+4], bpl
0x1800c4084  cmovz   rdi, rax
0x1800c4088  jmp     short loc_1800C4091
0x1800c408a  lea     rdi, aException; "Exception"
0x1800c4091  xor     edx, edx; Val
0x1800c4093  mov     r8d, 200h; Size
0x1800c4099  lea     rcx, [rsp+278h+Buffer]; void *
0x1800c409e  call    memset_0
0x1800c40a3  test    [rbx+4], bpl
0x1800c40a7  jz      short loc_1800C40CC
0x1800c40a9  mov     ebp, [rbx+0Ch]
0x1800c40ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800c40b3  test    rax, rax
0x1800c40b6  jz      short loc_1800C40FC
0x1800c40b8  mov     r8d, 100h
0x1800c40be  lea     rdx, [rsp+278h+Buffer]
0x1800c40c3  mov     ecx, ebp
0x1800c40c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c40ca  jmp     short loc_1800C40FC
0x1800c40cc  mov     ebp, [rbx+8]
0x1800c40cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800c40d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800c40dc  lea     rax, [rsp+278h+Buffer]
0x1800c40e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800c40e6  mov     r9d, 400h; dwLanguageId
0x1800c40ec  mov     r8d, ebp; dwMessageId
0x1800c40ef  xor     edx, edx; lpSource
0x1800c40f1  mov     ecx, 1200h; dwFlags
0x1800c40f6  call    cs:__imp_FormatMessageW
0x1800c40fc  lea     rsi, [r14+rsi*2]
0x1800c4100  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800c4104  mov     rax, [rbx+88h]
0x1800c410b  mov     rcx, [rbx+80h]
0x1800c4112  mov     rdx, rsi; unsigned __int16 *
0x1800c4115  test    r9, r9
0x1800c4118  jz      short loc_1800C413C
0x1800c411a  mov     [rsp+278h+Arguments], rax
0x1800c411f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800c4124  mov     eax, [rbx+40h]
0x1800c4127  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800c412b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800c4132  mov     rcx, r14; this
0x1800c4135  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800c413a  jmp     short loc_1800C4153
0x1800c413c  mov     [rsp+278h+lpBuffer], rax
0x1800c4141  mov     r9, rcx; unsigned __int16 *
0x1800c4144  lea     r8, aHsP; "%hs!%p: "
0x1800c414b  mov     rcx, r14; this
0x1800c414e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800c4153  mov     r14, rax
0x1800c4156  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800c415d  test    r9, r9
0x1800c4160  jz      short loc_1800C4177
0x1800c4162  lea     r8, aCallerP; "(caller: %p) "
0x1800c4169  mov     rdx, rsi; unsigned __int16 *
0x1800c416c  mov     rcx, rax; this
0x1800c416f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800c4174  mov     r14, rax
0x1800c4177  call    cs:__imp_GetCurrentThreadId
0x1800c417d  lea     rcx, [rsp+278h+Buffer]
0x1800c4182  mov     [rsp+278h+var_240], rcx
0x1800c4187  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800c418b  mov     [rsp+278h+nSize], eax
0x1800c418f  mov     eax, [rbx+44h]
0x1800c4192  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800c4196  mov     r9, rdi; unsigned __int16 *
0x1800c4199  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800c41a0  mov     rdx, rsi; unsigned __int16 *
0x1800c41a3  mov     rcx, r14; this
0x1800c41a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800c41ab  cmp     [rbx+18h], r15
0x1800c41af  jnz     short loc_1800C41C1
0x1800c41b1  cmp     [rbx+48h], r15
0x1800c41b5  jnz     short loc_1800C41C1
0x1800c41b7  cmp     [rbx+30h], r15
0x1800c41bb  jz      loc_1800C4251
0x1800c41c1  lea     r8, asc_1802A6200; "    "
0x1800c41c8  mov     rdx, rsi; unsigned __int16 *
0x1800c41cb  mov     rcx, rax; this
0x1800c41ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800c41d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800c41d7  test    r9, r9
0x1800c41da  jz      short loc_1800C41EE
0x1800c41dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800c41e3  mov     rdx, rsi; unsigned __int16 *
0x1800c41e6  mov     rcx, rax; this
0x1800c41e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800c41ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800c41f2  test    r9, r9
0x1800c41f5  jz      short loc_1800C4209
0x1800c41f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800c41fe  mov     rdx, rsi; unsigned __int16 *
0x1800c4201  mov     rcx, rax; this
0x1800c4204  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800c4209  mov     rcx, [rbx+28h]
0x1800c420d  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800c4211  mov     rdx, rsi; unsigned __int16 *
0x1800c4214  test    rcx, rcx
0x1800c4217  jz      short loc_1800C422F
0x1800c4219  mov     [rsp+278h+lpBuffer], rcx
0x1800c421e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800c4225  mov     rcx, rax; this
0x1800c4228  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800c422d  jmp     short loc_1800C4251
0x1800c422f  mov     rcx, rax; this
0x1800c4232  test    r9, r9
0x1800c4235  jz      short loc_1800C4245
0x1800c4237  lea     r8, aHs_0; "[%hs]\n"
0x1800c423e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800c4243  jmp     short loc_1800C4251
0x1800c4245  lea     r8, asc_1802A6278; "\n"
0x1800c424c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800c4251  xor     eax, eax
0x1800c4253  mov     rcx, [rsp+278h+var_38]
0x1800c425b  xor     rcx, rsp; StackCookie
0x1800c425e  call    __security_check_cookie
0x1800c4263  mov     rbx, [rsp+278h+arg_18]
0x1800c426b  add     rsp, 250h
0x1800c4272  pop     r15
0x1800c4274  pop     r14
0x1800c4276  pop     rdi
0x1800c4277  pop     rsi
0x1800c4278  pop     rbp
0x1800c4279  retn
```
