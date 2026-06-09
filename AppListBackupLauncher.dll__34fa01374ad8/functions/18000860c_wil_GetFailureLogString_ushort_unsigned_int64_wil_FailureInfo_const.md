# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000860c`
- end: `0x1800088c2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180003a3c`
- `0x180003cbc`
- `0x180003f78`
- `0x1800092b0`
- `0x18000f570`
- `0x180010562`
- `0x180010696`
- `0x1800107ff`
- `0x180010a7c`

## callees

- `0x180002300`
- `0x180002de0`
- `0x18000860c`
- `0x1800095b0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800087bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800087bf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000873e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000873e`

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
          v7 = (const char *)&byte_180013CC8;
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
0x18000860c  mov     [rsp+arg_18], rbx
0x180008611  push    rbp
0x180008612  push    rsi
0x180008613  push    rdi
0x180008614  push    r14
0x180008616  push    r15
0x180008618  sub     rsp, 250h
0x18000861f  mov     rax, cs:__security_cookie
0x180008626  xor     rax, rsp
0x180008629  mov     [rsp+278h+var_38], rax
0x180008631  mov     rbx, r8
0x180008634  mov     rsi, rdx
0x180008637  mov     r14, rcx
0x18000863a  xor     r15d, r15d
0x18000863d  test    rdx, rdx
0x180008640  jz      loc_180008899
0x180008646  test    rcx, rcx
0x180008649  jz      loc_180008899
0x18000864f  mov     [rcx], r15w
0x180008653  mov     rax, cs:g_pfnResultLoggingCallback
0x18000865a  test    rax, rax
0x18000865d  jz      short loc_180008680
0x18000865f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008666  jz      short loc_180008680
0x180008668  mov     r8, rdx
0x18000866b  mov     rdx, rcx
0x18000866e  mov     rcx, rbx
0x180008671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008676  cmp     [r14], r15w
0x18000867a  jnz     loc_180008899
0x180008680  mov     ecx, [rbx]
0x180008682  mov     bpl, 8
0x180008685  test    ecx, ecx
0x180008687  jz      short loc_1800086D2
0x180008689  sub     ecx, 1
0x18000868c  jz      short loc_1800086BA
0x18000868e  sub     ecx, 1
0x180008691  jz      short loc_1800086AA
0x180008693  cmp     ecx, 1
0x180008696  jz      short loc_1800086A1
0x180008698  lea     rdi, byte_180013CC8
0x18000869f  jmp     short loc_1800086D9
0x1800086a1  lea     rdi, aFailfast; "FailFast"
0x1800086a8  jmp     short loc_1800086D9
0x1800086aa  lea     rax, aLoghr; "LogHr"
0x1800086b1  lea     rdi, aLognt; "LogNt"
0x1800086b8  jmp     short loc_1800086C8
0x1800086ba  lea     rax, aReturnhr; "ReturnHr"
0x1800086c1  lea     rdi, aReturnnt; "ReturnNt"
0x1800086c8  test    [rbx+4], bpl
0x1800086cc  cmovz   rdi, rax
0x1800086d0  jmp     short loc_1800086D9
0x1800086d2  lea     rdi, aException; "Exception"
0x1800086d9  xor     edx, edx; Val
0x1800086db  mov     r8d, 200h; Size
0x1800086e1  lea     rcx, [rsp+278h+Buffer]; void *
0x1800086e6  call    memset_0
0x1800086eb  test    [rbx+4], bpl
0x1800086ef  jz      short loc_180008714
0x1800086f1  mov     ebp, [rbx+0Ch]
0x1800086f4  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800086fb  test    rax, rax
0x1800086fe  jz      short loc_180008744
0x180008700  mov     r8d, 100h
0x180008706  lea     rdx, [rsp+278h+Buffer]
0x18000870b  mov     ecx, ebp
0x18000870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008712  jmp     short loc_180008744
0x180008714  mov     ebp, [rbx+8]
0x180008717  mov     [rsp+278h+Arguments], r15; Arguments
0x18000871c  mov     [rsp+278h+nSize], 100h; nSize
0x180008724  lea     rax, [rsp+278h+Buffer]
0x180008729  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000872e  mov     r9d, 400h; dwLanguageId
0x180008734  mov     r8d, ebp; dwMessageId
0x180008737  xor     edx, edx; lpSource
0x180008739  mov     ecx, 1200h; dwFlags
0x18000873e  call    cs:__imp_FormatMessageW
0x180008744  lea     rsi, [r14+rsi*2]
0x180008748  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000874c  mov     rax, [rbx+88h]
0x180008753  mov     rcx, [rbx+80h]
0x18000875a  mov     rdx, rsi; unsigned __int16 *
0x18000875d  test    r9, r9
0x180008760  jz      short loc_180008784
0x180008762  mov     [rsp+278h+Arguments], rax
0x180008767  mov     qword ptr [rsp+278h+nSize], rcx
0x18000876c  mov     eax, [rbx+40h]
0x18000876f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008773  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000877a  mov     rcx, r14; this
0x18000877d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008782  jmp     short loc_18000879B
0x180008784  mov     [rsp+278h+lpBuffer], rax
0x180008789  mov     r9, rcx; unsigned __int16 *
0x18000878c  lea     r8, aHsP; "%hs!%p: "
0x180008793  mov     rcx, r14; this
0x180008796  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000879b  mov     r14, rax
0x18000879e  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800087a5  test    r9, r9
0x1800087a8  jz      short loc_1800087BF
0x1800087aa  lea     r8, aCallerP; "(caller: %p) "
0x1800087b1  mov     rdx, rsi; unsigned __int16 *
0x1800087b4  mov     rcx, rax; this
0x1800087b7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800087bc  mov     r14, rax
0x1800087bf  call    cs:__imp_GetCurrentThreadId
0x1800087c5  lea     rcx, [rsp+278h+Buffer]
0x1800087ca  mov     [rsp+278h+var_240], rcx
0x1800087cf  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800087d3  mov     [rsp+278h+nSize], eax
0x1800087d7  mov     eax, [rbx+44h]
0x1800087da  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800087de  mov     r9, rdi; unsigned __int16 *
0x1800087e1  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800087e8  mov     rdx, rsi; unsigned __int16 *
0x1800087eb  mov     rcx, r14; this
0x1800087ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800087f3  cmp     [rbx+18h], r15
0x1800087f7  jnz     short loc_180008809
0x1800087f9  cmp     [rbx+48h], r15
0x1800087fd  jnz     short loc_180008809
0x1800087ff  cmp     [rbx+30h], r15
0x180008803  jz      loc_180008899
0x180008809  lea     r8, asc_180013DF8; "    "
0x180008810  mov     rdx, rsi; unsigned __int16 *
0x180008813  mov     rcx, rax; this
0x180008816  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000881b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000881f  test    r9, r9
0x180008822  jz      short loc_180008836
0x180008824  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000882b  mov     rdx, rsi; unsigned __int16 *
0x18000882e  mov     rcx, rax; this
0x180008831  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008836  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000883a  test    r9, r9
0x18000883d  jz      short loc_180008851
0x18000883f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180008846  mov     rdx, rsi; unsigned __int16 *
0x180008849  mov     rcx, rax; this
0x18000884c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008851  mov     rcx, [rbx+28h]
0x180008855  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008859  mov     rdx, rsi; unsigned __int16 *
0x18000885c  test    rcx, rcx
0x18000885f  jz      short loc_180008877
0x180008861  mov     [rsp+278h+lpBuffer], rcx
0x180008866  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000886d  mov     rcx, rax; this
0x180008870  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008875  jmp     short loc_180008899
0x180008877  mov     rcx, rax; this
0x18000887a  test    r9, r9
0x18000887d  jz      short loc_18000888D
0x18000887f  lea     r8, aHs; "[%hs]\n"
0x180008886  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000888b  jmp     short loc_180008899
0x18000888d  lea     r8, asc_180013E70; "\n"
0x180008894  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008899  xor     eax, eax
0x18000889b  mov     rcx, [rsp+278h+var_38]
0x1800088a3  xor     rcx, rsp; StackCookie
0x1800088a6  call    __security_check_cookie
0x1800088ab  mov     rbx, [rsp+278h+arg_18]
0x1800088b3  add     rsp, 250h
0x1800088ba  pop     r15
0x1800088bc  pop     r14
0x1800088be  pop     rdi
0x1800088bf  pop     rsi
0x1800088c0  pop     rbp
0x1800088c1  retn
```
