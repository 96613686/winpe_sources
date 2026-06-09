# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004714`
- end: `0x1800049ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800032fc`
- `0x18000357c`
- `0x180005080`
- `0x1800068d0`
- `0x18000750c`
- `0x18000bf4f`
- `0x18000c083`

## callees

- `0x180002200`
- `0x180002f7c`
- `0x180004714`
- `0x180005380`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004846`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004846`

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
          v7 = (const char *)&byte_18000EB27;
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
0x180004714  mov     [rsp+arg_18], rbx
0x180004719  push    rbp
0x18000471a  push    rsi
0x18000471b  push    rdi
0x18000471c  push    r14
0x18000471e  push    r15
0x180004720  sub     rsp, 250h
0x180004727  mov     rax, cs:__security_cookie
0x18000472e  xor     rax, rsp
0x180004731  mov     [rsp+278h+var_38], rax
0x180004739  mov     rbx, r8
0x18000473c  mov     rsi, rdx
0x18000473f  mov     r14, rcx
0x180004742  xor     r15d, r15d
0x180004745  test    rdx, rdx
0x180004748  jz      loc_1800049A1
0x18000474e  test    rcx, rcx
0x180004751  jz      loc_1800049A1
0x180004757  mov     [rcx], r15w
0x18000475b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004762  test    rax, rax
0x180004765  jz      short loc_180004788
0x180004767  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000476e  jz      short loc_180004788
0x180004770  mov     r8, rdx
0x180004773  mov     rdx, rcx
0x180004776  mov     rcx, rbx
0x180004779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000477e  cmp     [r14], r15w
0x180004782  jnz     loc_1800049A1
0x180004788  mov     ecx, [rbx]
0x18000478a  mov     bpl, 8
0x18000478d  test    ecx, ecx
0x18000478f  jz      short loc_1800047DA
0x180004791  sub     ecx, 1
0x180004794  jz      short loc_1800047C2
0x180004796  sub     ecx, 1
0x180004799  jz      short loc_1800047B2
0x18000479b  cmp     ecx, 1
0x18000479e  jz      short loc_1800047A9
0x1800047a0  lea     rdi, byte_18000EB27
0x1800047a7  jmp     short loc_1800047E1
0x1800047a9  lea     rdi, aFailfast; "FailFast"
0x1800047b0  jmp     short loc_1800047E1
0x1800047b2  lea     rax, aLoghr; "LogHr"
0x1800047b9  lea     rdi, aLognt; "LogNt"
0x1800047c0  jmp     short loc_1800047D0
0x1800047c2  lea     rax, aReturnhr; "ReturnHr"
0x1800047c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800047d0  test    [rbx+4], bpl
0x1800047d4  cmovz   rdi, rax
0x1800047d8  jmp     short loc_1800047E1
0x1800047da  lea     rdi, aException; "Exception"
0x1800047e1  xor     edx, edx; Val
0x1800047e3  mov     r8d, 200h; Size
0x1800047e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800047ee  call    memset_0
0x1800047f3  test    [rbx+4], bpl
0x1800047f7  jz      short loc_18000481C
0x1800047f9  mov     ebp, [rbx+0Ch]
0x1800047fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004803  test    rax, rax
0x180004806  jz      short loc_18000484C
0x180004808  mov     r8d, 100h
0x18000480e  lea     rdx, [rsp+278h+Buffer]
0x180004813  mov     ecx, ebp
0x180004815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481a  jmp     short loc_18000484C
0x18000481c  mov     ebp, [rbx+8]
0x18000481f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004824  mov     [rsp+278h+nSize], 100h; nSize
0x18000482c  lea     rax, [rsp+278h+Buffer]
0x180004831  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004836  mov     r9d, 400h; dwLanguageId
0x18000483c  mov     r8d, ebp; dwMessageId
0x18000483f  xor     edx, edx; lpSource
0x180004841  mov     ecx, 1200h; dwFlags
0x180004846  call    cs:__imp_FormatMessageW
0x18000484c  lea     rsi, [r14+rsi*2]
0x180004850  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004854  mov     rax, [rbx+88h]
0x18000485b  mov     rcx, [rbx+80h]
0x180004862  mov     rdx, rsi; unsigned __int16 *
0x180004865  test    r9, r9
0x180004868  jz      short loc_18000488C
0x18000486a  mov     [rsp+278h+Arguments], rax
0x18000486f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004874  mov     eax, [rbx+40h]
0x180004877  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000487b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004882  mov     rcx, r14; this
0x180004885  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000488a  jmp     short loc_1800048A3
0x18000488c  mov     [rsp+278h+lpBuffer], rax
0x180004891  mov     r9, rcx; unsigned __int16 *
0x180004894  lea     r8, aHsP; "%hs!%p: "
0x18000489b  mov     rcx, r14; this
0x18000489e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048a3  mov     r14, rax
0x1800048a6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800048ad  test    r9, r9
0x1800048b0  jz      short loc_1800048C7
0x1800048b2  lea     r8, aCallerP; "(caller: %p) "
0x1800048b9  mov     rdx, rsi; unsigned __int16 *
0x1800048bc  mov     rcx, rax; this
0x1800048bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048c4  mov     r14, rax
0x1800048c7  call    cs:__imp_GetCurrentThreadId
0x1800048cd  lea     rcx, [rsp+278h+Buffer]
0x1800048d2  mov     [rsp+278h+var_240], rcx
0x1800048d7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800048db  mov     [rsp+278h+nSize], eax
0x1800048df  mov     eax, [rbx+44h]
0x1800048e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800048e6  mov     r9, rdi; unsigned __int16 *
0x1800048e9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800048f0  mov     rdx, rsi; unsigned __int16 *
0x1800048f3  mov     rcx, r14; this
0x1800048f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048fb  cmp     [rbx+18h], r15
0x1800048ff  jnz     short loc_180004911
0x180004901  cmp     [rbx+48h], r15
0x180004905  jnz     short loc_180004911
0x180004907  cmp     [rbx+30h], r15
0x18000490b  jz      loc_1800049A1
0x180004911  lea     r8, asc_18000EC28; "    "
0x180004918  mov     rdx, rsi; unsigned __int16 *
0x18000491b  mov     rcx, rax; this
0x18000491e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004923  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004927  test    r9, r9
0x18000492a  jz      short loc_18000493E
0x18000492c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004933  mov     rdx, rsi; unsigned __int16 *
0x180004936  mov     rcx, rax; this
0x180004939  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000493e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004942  test    r9, r9
0x180004945  jz      short loc_180004959
0x180004947  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000494e  mov     rdx, rsi; unsigned __int16 *
0x180004951  mov     rcx, rax; this
0x180004954  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004959  mov     rcx, [rbx+28h]
0x18000495d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004961  mov     rdx, rsi; unsigned __int16 *
0x180004964  test    rcx, rcx
0x180004967  jz      short loc_18000497F
0x180004969  mov     [rsp+278h+lpBuffer], rcx
0x18000496e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004975  mov     rcx, rax; this
0x180004978  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000497d  jmp     short loc_1800049A1
0x18000497f  mov     rcx, rax; this
0x180004982  test    r9, r9
0x180004985  jz      short loc_180004995
0x180004987  lea     r8, aHs; "[%hs]\n"
0x18000498e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004993  jmp     short loc_1800049A1
0x180004995  lea     r8, asc_18000ECA0; "\n"
0x18000499c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800049a1  xor     eax, eax
0x1800049a3  mov     rcx, [rsp+278h+var_38]
0x1800049ab  xor     rcx, rsp; StackCookie
0x1800049ae  call    __security_check_cookie
0x1800049b3  mov     rbx, [rsp+278h+arg_18]
0x1800049bb  add     rsp, 250h
0x1800049c2  pop     r15
0x1800049c4  pop     r14
0x1800049c6  pop     rdi
0x1800049c7  pop     rsi
0x1800049c8  pop     rbp
0x1800049c9  retn
```
