# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004694`
- end: `0x18000494a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002e48`
- `0x1800030c8`
- `0x18000508c`
- `0x180007260`
- `0x180007b40`
- `0x180021cf8`
- `0x180021e2c`

## callees

- `0x180004694`
- `0x18000538c`
- `0x180021822`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004847`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004847`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800047c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800047c6`

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
          v7 = (const char *)&byte_180028200;
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
0x180004694  mov     [rsp+arg_18], rbx
0x180004699  push    rbp
0x18000469a  push    rsi
0x18000469b  push    rdi
0x18000469c  push    r14
0x18000469e  push    r15
0x1800046a0  sub     rsp, 250h
0x1800046a7  mov     rax, cs:__security_cookie
0x1800046ae  xor     rax, rsp
0x1800046b1  mov     [rsp+278h+var_38], rax
0x1800046b9  mov     rbx, r8
0x1800046bc  mov     rsi, rdx
0x1800046bf  mov     r14, rcx
0x1800046c2  xor     r15d, r15d
0x1800046c5  test    rdx, rdx
0x1800046c8  jz      loc_180004921
0x1800046ce  test    rcx, rcx
0x1800046d1  jz      loc_180004921
0x1800046d7  mov     [rcx], r15w
0x1800046db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046e2  test    rax, rax
0x1800046e5  jz      short loc_180004708
0x1800046e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800046ee  jz      short loc_180004708
0x1800046f0  mov     r8, rdx
0x1800046f3  mov     rdx, rcx
0x1800046f6  mov     rcx, rbx
0x1800046f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fe  cmp     [r14], r15w
0x180004702  jnz     loc_180004921
0x180004708  mov     ecx, [rbx]
0x18000470a  mov     bpl, 8
0x18000470d  test    ecx, ecx
0x18000470f  jz      short loc_18000475A
0x180004711  sub     ecx, 1
0x180004714  jz      short loc_180004742
0x180004716  sub     ecx, 1
0x180004719  jz      short loc_180004732
0x18000471b  cmp     ecx, 1
0x18000471e  jz      short loc_180004729
0x180004720  lea     rdi, byte_180028200
0x180004727  jmp     short loc_180004761
0x180004729  lea     rdi, aFailfast; "FailFast"
0x180004730  jmp     short loc_180004761
0x180004732  lea     rax, aLoghr; "LogHr"
0x180004739  lea     rdi, aLognt; "LogNt"
0x180004740  jmp     short loc_180004750
0x180004742  lea     rax, aReturnhr; "ReturnHr"
0x180004749  lea     rdi, aReturnnt; "ReturnNt"
0x180004750  test    [rbx+4], bpl
0x180004754  cmovz   rdi, rax
0x180004758  jmp     short loc_180004761
0x18000475a  lea     rdi, aException; "Exception"
0x180004761  xor     edx, edx; Val
0x180004763  mov     r8d, 200h; Size
0x180004769  lea     rcx, [rsp+278h+Buffer]; void *
0x18000476e  call    memset_0
0x180004773  test    [rbx+4], bpl
0x180004777  jz      short loc_18000479C
0x180004779  mov     ebp, [rbx+0Ch]
0x18000477c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004783  test    rax, rax
0x180004786  jz      short loc_1800047CC
0x180004788  mov     r8d, 100h
0x18000478e  lea     rdx, [rsp+278h+Buffer]
0x180004793  mov     ecx, ebp
0x180004795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000479a  jmp     short loc_1800047CC
0x18000479c  mov     ebp, [rbx+8]
0x18000479f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800047a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800047ac  lea     rax, [rsp+278h+Buffer]
0x1800047b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800047b6  mov     r9d, 400h; dwLanguageId
0x1800047bc  mov     r8d, ebp; dwMessageId
0x1800047bf  xor     edx, edx; lpSource
0x1800047c1  mov     ecx, 1200h; dwFlags
0x1800047c6  call    cs:__imp_FormatMessageW
0x1800047cc  lea     rsi, [r14+rsi*2]
0x1800047d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800047d4  mov     rax, [rbx+88h]
0x1800047db  mov     rcx, [rbx+80h]
0x1800047e2  mov     rdx, rsi; unsigned __int16 *
0x1800047e5  test    r9, r9
0x1800047e8  jz      short loc_18000480C
0x1800047ea  mov     [rsp+278h+Arguments], rax
0x1800047ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800047f4  mov     eax, [rbx+40h]
0x1800047f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800047fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004802  mov     rcx, r14; this
0x180004805  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000480a  jmp     short loc_180004823
0x18000480c  mov     [rsp+278h+lpBuffer], rax
0x180004811  mov     r9, rcx; unsigned __int16 *
0x180004814  lea     r8, aHsP; "%hs!%p: "
0x18000481b  mov     rcx, r14; this
0x18000481e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004823  mov     r14, rax
0x180004826  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000482d  test    r9, r9
0x180004830  jz      short loc_180004847
0x180004832  lea     r8, aCallerP; "(caller: %p) "
0x180004839  mov     rdx, rsi; unsigned __int16 *
0x18000483c  mov     rcx, rax; this
0x18000483f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004844  mov     r14, rax
0x180004847  call    cs:__imp_GetCurrentThreadId
0x18000484d  lea     rcx, [rsp+278h+Buffer]
0x180004852  mov     [rsp+278h+var_240], rcx
0x180004857  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000485b  mov     [rsp+278h+nSize], eax
0x18000485f  mov     eax, [rbx+44h]
0x180004862  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004866  mov     r9, rdi; unsigned __int16 *
0x180004869  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004870  mov     rdx, rsi; unsigned __int16 *
0x180004873  mov     rcx, r14; this
0x180004876  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000487b  cmp     [rbx+18h], r15
0x18000487f  jnz     short loc_180004891
0x180004881  cmp     [rbx+48h], r15
0x180004885  jnz     short loc_180004891
0x180004887  cmp     [rbx+30h], r15
0x18000488b  jz      loc_180004921
0x180004891  lea     r8, asc_1800282F0; "    "
0x180004898  mov     rdx, rsi; unsigned __int16 *
0x18000489b  mov     rcx, rax; this
0x18000489e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800048a7  test    r9, r9
0x1800048aa  jz      short loc_1800048BE
0x1800048ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800048b3  mov     rdx, rsi; unsigned __int16 *
0x1800048b6  mov     rcx, rax; this
0x1800048b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800048c2  test    r9, r9
0x1800048c5  jz      short loc_1800048D9
0x1800048c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800048ce  mov     rdx, rsi; unsigned __int16 *
0x1800048d1  mov     rcx, rax; this
0x1800048d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048d9  mov     rcx, [rbx+28h]
0x1800048dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800048e1  mov     rdx, rsi; unsigned __int16 *
0x1800048e4  test    rcx, rcx
0x1800048e7  jz      short loc_1800048FF
0x1800048e9  mov     [rsp+278h+lpBuffer], rcx
0x1800048ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800048f5  mov     rcx, rax; this
0x1800048f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048fd  jmp     short loc_180004921
0x1800048ff  mov     rcx, rax; this
0x180004902  test    r9, r9
0x180004905  jz      short loc_180004915
0x180004907  lea     r8, aHs; "[%hs]\n"
0x18000490e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004913  jmp     short loc_180004921
0x180004915  lea     r8, asc_180028368; "\n"
0x18000491c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004921  xor     eax, eax
0x180004923  mov     rcx, [rsp+278h+var_38]
0x18000492b  xor     rcx, rsp; StackCookie
0x18000492e  call    __security_check_cookie
0x180004933  mov     rbx, [rsp+278h+arg_18]
0x18000493b  add     rsp, 250h
0x180004942  pop     r15
0x180004944  pop     r14
0x180004946  pop     rdi
0x180004947  pop     rsi
0x180004948  pop     rbp
0x180004949  retn
```
