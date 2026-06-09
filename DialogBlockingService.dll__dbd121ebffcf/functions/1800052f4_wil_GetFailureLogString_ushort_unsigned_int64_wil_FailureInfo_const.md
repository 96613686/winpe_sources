# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800052f4`
- end: `0x1800055aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003318`
- `0x180003598`
- `0x180005db0`
- `0x180007e70`
- `0x180008278`
- `0x18000ca05`
- `0x18000cb39`

## callees

- `0x180001620`
- `0x1800020d0`
- `0x1800052f4`
- `0x1800060b0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005426`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005426`

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
          v7 = (const char *)&qword_18000FE80;
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
0x1800052f4  mov     [rsp+arg_18], rbx
0x1800052f9  push    rbp
0x1800052fa  push    rsi
0x1800052fb  push    rdi
0x1800052fc  push    r14
0x1800052fe  push    r15
0x180005300  sub     rsp, 250h
0x180005307  mov     rax, cs:__security_cookie
0x18000530e  xor     rax, rsp
0x180005311  mov     [rsp+278h+var_38], rax
0x180005319  mov     rbx, r8
0x18000531c  mov     rsi, rdx
0x18000531f  mov     r14, rcx
0x180005322  xor     r15d, r15d
0x180005325  test    rdx, rdx
0x180005328  jz      loc_180005581
0x18000532e  test    rcx, rcx
0x180005331  jz      loc_180005581
0x180005337  mov     [rcx], r15w
0x18000533b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005342  test    rax, rax
0x180005345  jz      short loc_180005368
0x180005347  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000534e  jz      short loc_180005368
0x180005350  mov     r8, rdx
0x180005353  mov     rdx, rcx
0x180005356  mov     rcx, rbx
0x180005359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000535e  cmp     [r14], r15w
0x180005362  jnz     loc_180005581
0x180005368  mov     ecx, [rbx]
0x18000536a  mov     bpl, 8
0x18000536d  test    ecx, ecx
0x18000536f  jz      short loc_1800053BA
0x180005371  sub     ecx, 1
0x180005374  jz      short loc_1800053A2
0x180005376  sub     ecx, 1
0x180005379  jz      short loc_180005392
0x18000537b  cmp     ecx, 1
0x18000537e  jz      short loc_180005389
0x180005380  lea     rdi, qword_18000FE80
0x180005387  jmp     short loc_1800053C1
0x180005389  lea     rdi, aFailfast; "FailFast"
0x180005390  jmp     short loc_1800053C1
0x180005392  lea     rax, aLoghr; "LogHr"
0x180005399  lea     rdi, aLognt; "LogNt"
0x1800053a0  jmp     short loc_1800053B0
0x1800053a2  lea     rax, aReturnhr; "ReturnHr"
0x1800053a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800053b0  test    [rbx+4], bpl
0x1800053b4  cmovz   rdi, rax
0x1800053b8  jmp     short loc_1800053C1
0x1800053ba  lea     rdi, aException; "Exception"
0x1800053c1  xor     edx, edx; Val
0x1800053c3  mov     r8d, 200h; Size
0x1800053c9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800053ce  call    memset_0
0x1800053d3  test    [rbx+4], bpl
0x1800053d7  jz      short loc_1800053FC
0x1800053d9  mov     ebp, [rbx+0Ch]
0x1800053dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800053e3  test    rax, rax
0x1800053e6  jz      short loc_18000542C
0x1800053e8  mov     r8d, 100h
0x1800053ee  lea     rdx, [rsp+278h+Buffer]
0x1800053f3  mov     ecx, ebp
0x1800053f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053fa  jmp     short loc_18000542C
0x1800053fc  mov     ebp, [rbx+8]
0x1800053ff  mov     [rsp+278h+Arguments], r15; Arguments
0x180005404  mov     [rsp+278h+nSize], 100h; nSize
0x18000540c  lea     rax, [rsp+278h+Buffer]
0x180005411  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005416  mov     r9d, 400h; dwLanguageId
0x18000541c  mov     r8d, ebp; dwMessageId
0x18000541f  xor     edx, edx; lpSource
0x180005421  mov     ecx, 1200h; dwFlags
0x180005426  call    cs:__imp_FormatMessageW
0x18000542c  lea     rsi, [r14+rsi*2]
0x180005430  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005434  mov     rax, [rbx+88h]
0x18000543b  mov     rcx, [rbx+80h]
0x180005442  mov     rdx, rsi; unsigned __int16 *
0x180005445  test    r9, r9
0x180005448  jz      short loc_18000546C
0x18000544a  mov     [rsp+278h+Arguments], rax
0x18000544f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005454  mov     eax, [rbx+40h]
0x180005457  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000545b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005462  mov     rcx, r14; this
0x180005465  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000546a  jmp     short loc_180005483
0x18000546c  mov     [rsp+278h+lpBuffer], rax
0x180005471  mov     r9, rcx; unsigned __int16 *
0x180005474  lea     r8, aHsP; "%hs!%p: "
0x18000547b  mov     rcx, r14; this
0x18000547e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005483  mov     r14, rax
0x180005486  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000548d  test    r9, r9
0x180005490  jz      short loc_1800054A7
0x180005492  lea     r8, aCallerP; "(caller: %p) "
0x180005499  mov     rdx, rsi; unsigned __int16 *
0x18000549c  mov     rcx, rax; this
0x18000549f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054a4  mov     r14, rax
0x1800054a7  call    cs:__imp_GetCurrentThreadId
0x1800054ad  lea     rcx, [rsp+278h+Buffer]
0x1800054b2  mov     [rsp+278h+var_240], rcx
0x1800054b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800054bb  mov     [rsp+278h+nSize], eax
0x1800054bf  mov     eax, [rbx+44h]
0x1800054c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800054c6  mov     r9, rdi; unsigned __int16 *
0x1800054c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800054d0  mov     rdx, rsi; unsigned __int16 *
0x1800054d3  mov     rcx, r14; this
0x1800054d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054db  cmp     [rbx+18h], r15
0x1800054df  jnz     short loc_1800054F1
0x1800054e1  cmp     [rbx+48h], r15
0x1800054e5  jnz     short loc_1800054F1
0x1800054e7  cmp     [rbx+30h], r15
0x1800054eb  jz      loc_180005581
0x1800054f1  lea     r8, asc_18000FFA0; "    "
0x1800054f8  mov     rdx, rsi; unsigned __int16 *
0x1800054fb  mov     rcx, rax; this
0x1800054fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005503  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005507  test    r9, r9
0x18000550a  jz      short loc_18000551E
0x18000550c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005513  mov     rdx, rsi; unsigned __int16 *
0x180005516  mov     rcx, rax; this
0x180005519  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000551e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005522  test    r9, r9
0x180005525  jz      short loc_180005539
0x180005527  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000552e  mov     rdx, rsi; unsigned __int16 *
0x180005531  mov     rcx, rax; this
0x180005534  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005539  mov     rcx, [rbx+28h]
0x18000553d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005541  mov     rdx, rsi; unsigned __int16 *
0x180005544  test    rcx, rcx
0x180005547  jz      short loc_18000555F
0x180005549  mov     [rsp+278h+lpBuffer], rcx
0x18000554e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005555  mov     rcx, rax; this
0x180005558  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000555d  jmp     short loc_180005581
0x18000555f  mov     rcx, rax; this
0x180005562  test    r9, r9
0x180005565  jz      short loc_180005575
0x180005567  lea     r8, aHs; "[%hs]\n"
0x18000556e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005573  jmp     short loc_180005581
0x180005575  lea     r8, asc_180010018; "\n"
0x18000557c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005581  xor     eax, eax
0x180005583  mov     rcx, [rsp+278h+var_38]
0x18000558b  xor     rcx, rsp; StackCookie
0x18000558e  call    __security_check_cookie
0x180005593  mov     rbx, [rsp+278h+arg_18]
0x18000559b  add     rsp, 250h
0x1800055a2  pop     r15
0x1800055a4  pop     r14
0x1800055a6  pop     rdi
0x1800055a7  pop     rsi
0x1800055a8  pop     rbp
0x1800055a9  retn
```
