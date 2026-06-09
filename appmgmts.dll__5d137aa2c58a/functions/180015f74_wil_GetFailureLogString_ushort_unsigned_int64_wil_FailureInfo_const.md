# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180015f74`
- end: `0x18001622a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180013cf0`
- `0x180013f58`
- `0x1800168d4`
- `0x1800198f0`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180015f74`
- `0x180016bd4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016127`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800160a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800160a6`

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
          v7 = (const char *)&qword_1800307C8;
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
0x180015f74  mov     [rsp+arg_18], rbx
0x180015f79  push    rbp
0x180015f7a  push    rsi
0x180015f7b  push    rdi
0x180015f7c  push    r14
0x180015f7e  push    r15
0x180015f80  sub     rsp, 250h
0x180015f87  mov     rax, cs:__security_cookie
0x180015f8e  xor     rax, rsp
0x180015f91  mov     [rsp+278h+var_38], rax
0x180015f99  mov     rbx, r8
0x180015f9c  mov     rsi, rdx
0x180015f9f  mov     r14, rcx
0x180015fa2  xor     r15d, r15d
0x180015fa5  test    rdx, rdx
0x180015fa8  jz      loc_180016201
0x180015fae  test    rcx, rcx
0x180015fb1  jz      loc_180016201
0x180015fb7  mov     [rcx], r15w
0x180015fbb  mov     rax, cs:g_pfnResultLoggingCallback
0x180015fc2  test    rax, rax
0x180015fc5  jz      short loc_180015FE8
0x180015fc7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180015fce  jz      short loc_180015FE8
0x180015fd0  mov     r8, rdx
0x180015fd3  mov     rdx, rcx
0x180015fd6  mov     rcx, rbx
0x180015fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fde  cmp     [r14], r15w
0x180015fe2  jnz     loc_180016201
0x180015fe8  mov     ecx, [rbx]
0x180015fea  mov     bpl, 8
0x180015fed  test    ecx, ecx
0x180015fef  jz      short loc_18001603A
0x180015ff1  sub     ecx, 1
0x180015ff4  jz      short loc_180016022
0x180015ff6  sub     ecx, 1
0x180015ff9  jz      short loc_180016012
0x180015ffb  cmp     ecx, 1
0x180015ffe  jz      short loc_180016009
0x180016000  lea     rdi, qword_1800307C8
0x180016007  jmp     short loc_180016041
0x180016009  lea     rdi, aFailfast; "FailFast"
0x180016010  jmp     short loc_180016041
0x180016012  lea     rax, aLoghr; "LogHr"
0x180016019  lea     rdi, aLognt; "LogNt"
0x180016020  jmp     short loc_180016030
0x180016022  lea     rax, aReturnhr; "ReturnHr"
0x180016029  lea     rdi, aReturnnt; "ReturnNt"
0x180016030  test    [rbx+4], bpl
0x180016034  cmovz   rdi, rax
0x180016038  jmp     short loc_180016041
0x18001603a  lea     rdi, aException; "Exception"
0x180016041  xor     edx, edx; Val
0x180016043  mov     r8d, 200h; Size
0x180016049  lea     rcx, [rsp+278h+Buffer]; void *
0x18001604e  call    memset_0
0x180016053  test    [rbx+4], bpl
0x180016057  jz      short loc_18001607C
0x180016059  mov     ebp, [rbx+0Ch]
0x18001605c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180016063  test    rax, rax
0x180016066  jz      short loc_1800160AC
0x180016068  mov     r8d, 100h
0x18001606e  lea     rdx, [rsp+278h+Buffer]
0x180016073  mov     ecx, ebp
0x180016075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001607a  jmp     short loc_1800160AC
0x18001607c  mov     ebp, [rbx+8]
0x18001607f  mov     [rsp+278h+Arguments], r15; Arguments
0x180016084  mov     [rsp+278h+nSize], 100h; nSize
0x18001608c  lea     rax, [rsp+278h+Buffer]
0x180016091  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180016096  mov     r9d, 400h; dwLanguageId
0x18001609c  mov     r8d, ebp; dwMessageId
0x18001609f  xor     edx, edx; lpSource
0x1800160a1  mov     ecx, 1200h; dwFlags
0x1800160a6  call    cs:__imp_FormatMessageW
0x1800160ac  lea     rsi, [r14+rsi*2]
0x1800160b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800160b4  mov     rax, [rbx+88h]
0x1800160bb  mov     rcx, [rbx+80h]
0x1800160c2  mov     rdx, rsi; unsigned __int16 *
0x1800160c5  test    r9, r9
0x1800160c8  jz      short loc_1800160EC
0x1800160ca  mov     [rsp+278h+Arguments], rax
0x1800160cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800160d4  mov     eax, [rbx+40h]
0x1800160d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800160db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800160e2  mov     rcx, r14; this
0x1800160e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800160ea  jmp     short loc_180016103
0x1800160ec  mov     [rsp+278h+lpBuffer], rax
0x1800160f1  mov     r9, rcx; unsigned __int16 *
0x1800160f4  lea     r8, aHsP; "%hs!%p: "
0x1800160fb  mov     rcx, r14; this
0x1800160fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016103  mov     r14, rax
0x180016106  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001610d  test    r9, r9
0x180016110  jz      short loc_180016127
0x180016112  lea     r8, aCallerP; "(caller: %p) "
0x180016119  mov     rdx, rsi; unsigned __int16 *
0x18001611c  mov     rcx, rax; this
0x18001611f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016124  mov     r14, rax
0x180016127  call    cs:__imp_GetCurrentThreadId
0x18001612d  lea     rcx, [rsp+278h+Buffer]
0x180016132  mov     [rsp+278h+var_240], rcx
0x180016137  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001613b  mov     [rsp+278h+nSize], eax
0x18001613f  mov     eax, [rbx+44h]
0x180016142  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180016146  mov     r9, rdi; unsigned __int16 *
0x180016149  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180016150  mov     rdx, rsi; unsigned __int16 *
0x180016153  mov     rcx, r14; this
0x180016156  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001615b  cmp     [rbx+18h], r15
0x18001615f  jnz     short loc_180016171
0x180016161  cmp     [rbx+48h], r15
0x180016165  jnz     short loc_180016171
0x180016167  cmp     [rbx+30h], r15
0x18001616b  jz      loc_180016201
0x180016171  lea     r8, asc_180030480; "    "
0x180016178  mov     rdx, rsi; unsigned __int16 *
0x18001617b  mov     rcx, rax; this
0x18001617e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016183  mov     r9, [rbx+18h]; unsigned __int16 *
0x180016187  test    r9, r9
0x18001618a  jz      short loc_18001619E
0x18001618c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180016193  mov     rdx, rsi; unsigned __int16 *
0x180016196  mov     rcx, rax; this
0x180016199  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001619e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800161a2  test    r9, r9
0x1800161a5  jz      short loc_1800161B9
0x1800161a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800161ae  mov     rdx, rsi; unsigned __int16 *
0x1800161b1  mov     rcx, rax; this
0x1800161b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800161b9  mov     rcx, [rbx+28h]
0x1800161bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800161c1  mov     rdx, rsi; unsigned __int16 *
0x1800161c4  test    rcx, rcx
0x1800161c7  jz      short loc_1800161DF
0x1800161c9  mov     [rsp+278h+lpBuffer], rcx
0x1800161ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800161d5  mov     rcx, rax; this
0x1800161d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800161dd  jmp     short loc_180016201
0x1800161df  mov     rcx, rax; this
0x1800161e2  test    r9, r9
0x1800161e5  jz      short loc_1800161F5
0x1800161e7  lea     r8, aHs; "[%hs]\n"
0x1800161ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800161f3  jmp     short loc_180016201
0x1800161f5  lea     r8, asc_1800304F8; "\n"
0x1800161fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016201  xor     eax, eax
0x180016203  mov     rcx, [rsp+278h+var_38]
0x18001620b  xor     rcx, rsp; StackCookie
0x18001620e  call    __security_check_cookie
0x180016213  mov     rbx, [rsp+278h+arg_18]
0x18001621b  add     rsp, 250h
0x180016222  pop     r15
0x180016224  pop     r14
0x180016226  pop     rdi
0x180016227  pop     rsi
0x180016228  pop     rbp
0x180016229  retn
```
