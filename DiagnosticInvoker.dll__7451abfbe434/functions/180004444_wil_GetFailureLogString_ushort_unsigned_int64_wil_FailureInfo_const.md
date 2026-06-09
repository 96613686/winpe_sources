# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004444`
- end: `0x1800046fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003060`
- `0x1800032d0`
- `0x180004da8`
- `0x180006490`

## callees

- `0x180001e20`
- `0x180002ac8`
- `0x180004444`
- `0x1800050a8`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004576`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004576`

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
          v7 = (const char *)&qword_1800150F8;
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
0x180004444  mov     [rsp+arg_18], rbx
0x180004449  push    rbp
0x18000444a  push    rsi
0x18000444b  push    rdi
0x18000444c  push    r14
0x18000444e  push    r15
0x180004450  sub     rsp, 250h
0x180004457  mov     rax, cs:__security_cookie
0x18000445e  xor     rax, rsp
0x180004461  mov     [rsp+278h+var_38], rax
0x180004469  mov     rbx, r8
0x18000446c  mov     rsi, rdx
0x18000446f  mov     r14, rcx
0x180004472  xor     r15d, r15d
0x180004475  test    rdx, rdx
0x180004478  jz      loc_1800046D1
0x18000447e  test    rcx, rcx
0x180004481  jz      loc_1800046D1
0x180004487  mov     [rcx], r15w
0x18000448b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004492  test    rax, rax
0x180004495  jz      short loc_1800044B8
0x180004497  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000449e  jz      short loc_1800044B8
0x1800044a0  mov     r8, rdx
0x1800044a3  mov     rdx, rcx
0x1800044a6  mov     rcx, rbx
0x1800044a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ae  cmp     [r14], r15w
0x1800044b2  jnz     loc_1800046D1
0x1800044b8  mov     ecx, [rbx]
0x1800044ba  mov     bpl, 8
0x1800044bd  test    ecx, ecx
0x1800044bf  jz      short loc_18000450A
0x1800044c1  sub     ecx, 1
0x1800044c4  jz      short loc_1800044F2
0x1800044c6  sub     ecx, 1
0x1800044c9  jz      short loc_1800044E2
0x1800044cb  cmp     ecx, 1
0x1800044ce  jz      short loc_1800044D9
0x1800044d0  lea     rdi, qword_1800150F8
0x1800044d7  jmp     short loc_180004511
0x1800044d9  lea     rdi, aFailfast; "FailFast"
0x1800044e0  jmp     short loc_180004511
0x1800044e2  lea     rax, aLoghr; "LogHr"
0x1800044e9  lea     rdi, aLognt; "LogNt"
0x1800044f0  jmp     short loc_180004500
0x1800044f2  lea     rax, aReturnhr; "ReturnHr"
0x1800044f9  lea     rdi, aReturnnt; "ReturnNt"
0x180004500  test    [rbx+4], bpl
0x180004504  cmovz   rdi, rax
0x180004508  jmp     short loc_180004511
0x18000450a  lea     rdi, aException; "Exception"
0x180004511  xor     edx, edx; Val
0x180004513  mov     r8d, 200h; Size
0x180004519  lea     rcx, [rsp+278h+Buffer]; void *
0x18000451e  call    memset_0
0x180004523  test    [rbx+4], bpl
0x180004527  jz      short loc_18000454C
0x180004529  mov     ebp, [rbx+0Ch]
0x18000452c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004533  test    rax, rax
0x180004536  jz      short loc_18000457C
0x180004538  mov     r8d, 100h
0x18000453e  lea     rdx, [rsp+278h+Buffer]
0x180004543  mov     ecx, ebp
0x180004545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000454a  jmp     short loc_18000457C
0x18000454c  mov     ebp, [rbx+8]
0x18000454f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004554  mov     [rsp+278h+nSize], 100h; nSize
0x18000455c  lea     rax, [rsp+278h+Buffer]
0x180004561  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004566  mov     r9d, 400h; dwLanguageId
0x18000456c  mov     r8d, ebp; dwMessageId
0x18000456f  xor     edx, edx; lpSource
0x180004571  mov     ecx, 1200h; dwFlags
0x180004576  call    cs:__imp_FormatMessageW
0x18000457c  lea     rsi, [r14+rsi*2]
0x180004580  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004584  mov     rax, [rbx+88h]
0x18000458b  mov     rcx, [rbx+80h]
0x180004592  mov     rdx, rsi; unsigned __int16 *
0x180004595  test    r9, r9
0x180004598  jz      short loc_1800045BC
0x18000459a  mov     [rsp+278h+Arguments], rax
0x18000459f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800045a4  mov     eax, [rbx+40h]
0x1800045a7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800045ab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800045b2  mov     rcx, r14; this
0x1800045b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045ba  jmp     short loc_1800045D3
0x1800045bc  mov     [rsp+278h+lpBuffer], rax
0x1800045c1  mov     r9, rcx; unsigned __int16 *
0x1800045c4  lea     r8, aHsP; "%hs!%p: "
0x1800045cb  mov     rcx, r14; this
0x1800045ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045d3  mov     r14, rax
0x1800045d6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800045dd  test    r9, r9
0x1800045e0  jz      short loc_1800045F7
0x1800045e2  lea     r8, aCallerP; "(caller: %p) "
0x1800045e9  mov     rdx, rsi; unsigned __int16 *
0x1800045ec  mov     rcx, rax; this
0x1800045ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045f4  mov     r14, rax
0x1800045f7  call    cs:__imp_GetCurrentThreadId
0x1800045fd  lea     rcx, [rsp+278h+Buffer]
0x180004602  mov     [rsp+278h+var_240], rcx
0x180004607  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000460b  mov     [rsp+278h+nSize], eax
0x18000460f  mov     eax, [rbx+44h]
0x180004612  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004616  mov     r9, rdi; unsigned __int16 *
0x180004619  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004620  mov     rdx, rsi; unsigned __int16 *
0x180004623  mov     rcx, r14; this
0x180004626  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000462b  cmp     [rbx+18h], r15
0x18000462f  jnz     short loc_180004641
0x180004631  cmp     [rbx+48h], r15
0x180004635  jnz     short loc_180004641
0x180004637  cmp     [rbx+30h], r15
0x18000463b  jz      loc_1800046D1
0x180004641  lea     r8, asc_180015200; "    "
0x180004648  mov     rdx, rsi; unsigned __int16 *
0x18000464b  mov     rcx, rax; this
0x18000464e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004653  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004657  test    r9, r9
0x18000465a  jz      short loc_18000466E
0x18000465c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004663  mov     rdx, rsi; unsigned __int16 *
0x180004666  mov     rcx, rax; this
0x180004669  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000466e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004672  test    r9, r9
0x180004675  jz      short loc_180004689
0x180004677  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000467e  mov     rdx, rsi; unsigned __int16 *
0x180004681  mov     rcx, rax; this
0x180004684  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004689  mov     rcx, [rbx+28h]
0x18000468d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004691  mov     rdx, rsi; unsigned __int16 *
0x180004694  test    rcx, rcx
0x180004697  jz      short loc_1800046AF
0x180004699  mov     [rsp+278h+lpBuffer], rcx
0x18000469e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800046a5  mov     rcx, rax; this
0x1800046a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046ad  jmp     short loc_1800046D1
0x1800046af  mov     rcx, rax; this
0x1800046b2  test    r9, r9
0x1800046b5  jz      short loc_1800046C5
0x1800046b7  lea     r8, aHs; "[%hs]\n"
0x1800046be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046c3  jmp     short loc_1800046D1
0x1800046c5  lea     r8, asc_180015278; "\n"
0x1800046cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046d1  xor     eax, eax
0x1800046d3  mov     rcx, [rsp+278h+var_38]
0x1800046db  xor     rcx, rsp; StackCookie
0x1800046de  call    __security_check_cookie
0x1800046e3  mov     rbx, [rsp+278h+arg_18]
0x1800046eb  add     rsp, 250h
0x1800046f2  pop     r15
0x1800046f4  pop     r14
0x1800046f6  pop     rdi
0x1800046f7  pop     rsi
0x1800046f8  pop     rbp
0x1800046f9  retn
```
