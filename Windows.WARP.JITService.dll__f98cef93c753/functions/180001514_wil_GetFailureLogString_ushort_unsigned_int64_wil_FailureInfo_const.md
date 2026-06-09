# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180001514`
- end: `0x1800017ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002580`
- `0x180002920`
- `0x180006cb8`
- `0x180007830`

## callees

- `0x180001498`
- `0x180001514`
- `0x180008a80`
- `0x18000941c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800016c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800016c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180001646`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180001646`

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
          v7 = (const char *)&byte_18000B8C1;
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
0x180001514  mov     [rsp+arg_18], rbx
0x180001519  push    rbp
0x18000151a  push    rsi
0x18000151b  push    rdi
0x18000151c  push    r14
0x18000151e  push    r15
0x180001520  sub     rsp, 250h
0x180001527  mov     rax, cs:__security_cookie
0x18000152e  xor     rax, rsp
0x180001531  mov     [rsp+278h+var_38], rax
0x180001539  mov     rbx, r8
0x18000153c  mov     rsi, rdx
0x18000153f  mov     r14, rcx
0x180001542  xor     r15d, r15d
0x180001545  test    rdx, rdx
0x180001548  jz      loc_1800017A1
0x18000154e  test    rcx, rcx
0x180001551  jz      loc_1800017A1
0x180001557  mov     [rcx], r15w
0x18000155b  mov     rax, cs:g_pfnResultLoggingCallback
0x180001562  test    rax, rax
0x180001565  jz      short loc_180001588
0x180001567  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000156e  jz      short loc_180001588
0x180001570  mov     r8, rdx
0x180001573  mov     rdx, rcx
0x180001576  mov     rcx, rbx
0x180001579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000157e  cmp     [r14], r15w
0x180001582  jnz     loc_1800017A1
0x180001588  mov     ecx, [rbx]
0x18000158a  mov     bpl, 8
0x18000158d  test    ecx, ecx
0x18000158f  jz      short loc_1800015DA
0x180001591  sub     ecx, 1
0x180001594  jz      short loc_1800015C2
0x180001596  sub     ecx, 1
0x180001599  jz      short loc_1800015B2
0x18000159b  cmp     ecx, 1
0x18000159e  jz      short loc_1800015A9
0x1800015a0  lea     rdi, byte_18000B8C1
0x1800015a7  jmp     short loc_1800015E1
0x1800015a9  lea     rdi, aFailfast; "FailFast"
0x1800015b0  jmp     short loc_1800015E1
0x1800015b2  lea     rax, aLoghr; "LogHr"
0x1800015b9  lea     rdi, aLognt; "LogNt"
0x1800015c0  jmp     short loc_1800015D0
0x1800015c2  lea     rax, aReturnhr; "ReturnHr"
0x1800015c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800015d0  test    [rbx+4], bpl
0x1800015d4  cmovz   rdi, rax
0x1800015d8  jmp     short loc_1800015E1
0x1800015da  lea     rdi, aException; "Exception"
0x1800015e1  xor     edx, edx; Val
0x1800015e3  mov     r8d, 200h; Size
0x1800015e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800015ee  call    memset_0
0x1800015f3  test    [rbx+4], bpl
0x1800015f7  jz      short loc_18000161C
0x1800015f9  mov     ebp, [rbx+0Ch]
0x1800015fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180001603  test    rax, rax
0x180001606  jz      short loc_18000164C
0x180001608  mov     r8d, 100h
0x18000160e  lea     rdx, [rsp+278h+Buffer]
0x180001613  mov     ecx, ebp
0x180001615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000161a  jmp     short loc_18000164C
0x18000161c  mov     ebp, [rbx+8]
0x18000161f  mov     [rsp+278h+Arguments], r15; Arguments
0x180001624  mov     [rsp+278h+nSize], 100h; nSize
0x18000162c  lea     rax, [rsp+278h+Buffer]
0x180001631  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180001636  mov     r9d, 400h; dwLanguageId
0x18000163c  mov     r8d, ebp; dwMessageId
0x18000163f  xor     edx, edx; lpSource
0x180001641  mov     ecx, 1200h; dwFlags
0x180001646  call    cs:__imp_FormatMessageW
0x18000164c  lea     rsi, [r14+rsi*2]
0x180001650  mov     r9, [rbx+38h]; unsigned __int16 *
0x180001654  mov     rax, [rbx+88h]
0x18000165b  mov     rcx, [rbx+80h]
0x180001662  mov     rdx, rsi; unsigned __int16 *
0x180001665  test    r9, r9
0x180001668  jz      short loc_18000168C
0x18000166a  mov     [rsp+278h+Arguments], rax
0x18000166f  mov     qword ptr [rsp+278h+nSize], rcx
0x180001674  mov     eax, [rbx+40h]
0x180001677  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000167b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180001682  mov     rcx, r14; this
0x180001685  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000168a  jmp     short loc_1800016A3
0x18000168c  mov     [rsp+278h+lpBuffer], rax
0x180001691  mov     r9, rcx; unsigned __int16 *
0x180001694  lea     r8, aHsP; "%hs!%p: "
0x18000169b  mov     rcx, r14; this
0x18000169e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800016a3  mov     r14, rax
0x1800016a6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800016ad  test    r9, r9
0x1800016b0  jz      short loc_1800016C7
0x1800016b2  lea     r8, aCallerP; "(caller: %p) "
0x1800016b9  mov     rdx, rsi; unsigned __int16 *
0x1800016bc  mov     rcx, rax; this
0x1800016bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800016c4  mov     r14, rax
0x1800016c7  call    cs:__imp_GetCurrentThreadId
0x1800016cd  lea     rcx, [rsp+278h+Buffer]
0x1800016d2  mov     [rsp+278h+var_240], rcx
0x1800016d7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800016db  mov     [rsp+278h+nSize], eax
0x1800016df  mov     eax, [rbx+44h]
0x1800016e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800016e6  mov     r9, rdi; unsigned __int16 *
0x1800016e9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800016f0  mov     rdx, rsi; unsigned __int16 *
0x1800016f3  mov     rcx, r14; this
0x1800016f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800016fb  cmp     [rbx+18h], r15
0x1800016ff  jnz     short loc_180001711
0x180001701  cmp     [rbx+48h], r15
0x180001705  jnz     short loc_180001711
0x180001707  cmp     [rbx+30h], r15
0x18000170b  jz      loc_1800017A1
0x180001711  lea     r8, asc_18000B9C8; "    "
0x180001718  mov     rdx, rsi; unsigned __int16 *
0x18000171b  mov     rcx, rax; this
0x18000171e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180001723  mov     r9, [rbx+18h]; unsigned __int16 *
0x180001727  test    r9, r9
0x18000172a  jz      short loc_18000173E
0x18000172c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180001733  mov     rdx, rsi; unsigned __int16 *
0x180001736  mov     rcx, rax; this
0x180001739  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000173e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180001742  test    r9, r9
0x180001745  jz      short loc_180001759
0x180001747  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000174e  mov     rdx, rsi; unsigned __int16 *
0x180001751  mov     rcx, rax; this
0x180001754  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180001759  mov     rcx, [rbx+28h]
0x18000175d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180001761  mov     rdx, rsi; unsigned __int16 *
0x180001764  test    rcx, rcx
0x180001767  jz      short loc_18000177F
0x180001769  mov     [rsp+278h+lpBuffer], rcx
0x18000176e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180001775  mov     rcx, rax; this
0x180001778  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000177d  jmp     short loc_1800017A1
0x18000177f  mov     rcx, rax; this
0x180001782  test    r9, r9
0x180001785  jz      short loc_180001795
0x180001787  lea     r8, aHs; "[%hs]\n"
0x18000178e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180001793  jmp     short loc_1800017A1
0x180001795  lea     r8, asc_18000BA40; "\n"
0x18000179c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800017a1  xor     eax, eax
0x1800017a3  mov     rcx, [rsp+278h+var_38]
0x1800017ab  xor     rcx, rsp; StackCookie
0x1800017ae  call    __security_check_cookie
0x1800017b3  mov     rbx, [rsp+278h+arg_18]
0x1800017bb  add     rsp, 250h
0x1800017c2  pop     r15
0x1800017c4  pop     r14
0x1800017c6  pop     rdi
0x1800017c7  pop     rsi
0x1800017c8  pop     rbp
0x1800017c9  retn
```
