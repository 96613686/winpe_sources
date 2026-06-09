# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800036b4`
- end: `0x18000396a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000284c`
- `0x18000404c`
- `0x180004504`
- `0x180005cb0`

## callees

- `0x1800036b4`
- `0x18000434c`
- `0x18001dfe2`
- `0x18001e020`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003867`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003867`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800037e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800037e6`

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
          v7 = (const char *)&byte_18002359D;
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
0x1800036b4  mov     [rsp+arg_18], rbx
0x1800036b9  push    rbp
0x1800036ba  push    rsi
0x1800036bb  push    rdi
0x1800036bc  push    r14
0x1800036be  push    r15
0x1800036c0  sub     rsp, 250h
0x1800036c7  mov     rax, cs:__security_cookie
0x1800036ce  xor     rax, rsp
0x1800036d1  mov     [rsp+278h+var_38], rax
0x1800036d9  mov     rbx, r8
0x1800036dc  mov     rsi, rdx
0x1800036df  mov     r14, rcx
0x1800036e2  xor     r15d, r15d
0x1800036e5  test    rdx, rdx
0x1800036e8  jz      loc_180003941
0x1800036ee  test    rcx, rcx
0x1800036f1  jz      loc_180003941
0x1800036f7  mov     [rcx], r15w
0x1800036fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180003702  test    rax, rax
0x180003705  jz      short loc_180003728
0x180003707  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000370e  jz      short loc_180003728
0x180003710  mov     r8, rdx
0x180003713  mov     rdx, rcx
0x180003716  mov     rcx, rbx
0x180003719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000371e  cmp     [r14], r15w
0x180003722  jnz     loc_180003941
0x180003728  mov     ecx, [rbx]
0x18000372a  mov     bpl, 8
0x18000372d  test    ecx, ecx
0x18000372f  jz      short loc_18000377A
0x180003731  sub     ecx, 1
0x180003734  jz      short loc_180003762
0x180003736  sub     ecx, 1
0x180003739  jz      short loc_180003752
0x18000373b  cmp     ecx, 1
0x18000373e  jz      short loc_180003749
0x180003740  lea     rdi, byte_18002359D
0x180003747  jmp     short loc_180003781
0x180003749  lea     rdi, aFailfast; "FailFast"
0x180003750  jmp     short loc_180003781
0x180003752  lea     rax, aLoghr; "LogHr"
0x180003759  lea     rdi, aLognt; "LogNt"
0x180003760  jmp     short loc_180003770
0x180003762  lea     rax, aReturnhr; "ReturnHr"
0x180003769  lea     rdi, aReturnnt; "ReturnNt"
0x180003770  test    [rbx+4], bpl
0x180003774  cmovz   rdi, rax
0x180003778  jmp     short loc_180003781
0x18000377a  lea     rdi, aException; "Exception"
0x180003781  xor     edx, edx; Val
0x180003783  mov     r8d, 200h; Size
0x180003789  lea     rcx, [rsp+278h+Buffer]; void *
0x18000378e  call    memset_0
0x180003793  test    [rbx+4], bpl
0x180003797  jz      short loc_1800037BC
0x180003799  mov     ebp, [rbx+0Ch]
0x18000379c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800037a3  test    rax, rax
0x1800037a6  jz      short loc_1800037EC
0x1800037a8  mov     r8d, 100h
0x1800037ae  lea     rdx, [rsp+278h+Buffer]
0x1800037b3  mov     ecx, ebp
0x1800037b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ba  jmp     short loc_1800037EC
0x1800037bc  mov     ebp, [rbx+8]
0x1800037bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800037c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800037cc  lea     rax, [rsp+278h+Buffer]
0x1800037d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800037d6  mov     r9d, 400h; dwLanguageId
0x1800037dc  mov     r8d, ebp; dwMessageId
0x1800037df  xor     edx, edx; lpSource
0x1800037e1  mov     ecx, 1200h; dwFlags
0x1800037e6  call    cs:__imp_FormatMessageW
0x1800037ec  lea     rsi, [r14+rsi*2]
0x1800037f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800037f4  mov     rax, [rbx+88h]
0x1800037fb  mov     rcx, [rbx+80h]
0x180003802  mov     rdx, rsi; unsigned __int16 *
0x180003805  test    r9, r9
0x180003808  jz      short loc_18000382C
0x18000380a  mov     [rsp+278h+Arguments], rax
0x18000380f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003814  mov     eax, [rbx+40h]
0x180003817  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000381b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003822  mov     rcx, r14; this
0x180003825  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000382a  jmp     short loc_180003843
0x18000382c  mov     [rsp+278h+lpBuffer], rax
0x180003831  mov     r9, rcx; unsigned __int16 *
0x180003834  lea     r8, aHsP; "%hs!%p: "
0x18000383b  mov     rcx, r14; this
0x18000383e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003843  mov     r14, rax
0x180003846  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000384d  test    r9, r9
0x180003850  jz      short loc_180003867
0x180003852  lea     r8, aCallerP; "(caller: %p) "
0x180003859  mov     rdx, rsi; unsigned __int16 *
0x18000385c  mov     rcx, rax; this
0x18000385f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003864  mov     r14, rax
0x180003867  call    cs:__imp_GetCurrentThreadId
0x18000386d  lea     rcx, [rsp+278h+Buffer]
0x180003872  mov     [rsp+278h+var_240], rcx
0x180003877  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000387b  mov     [rsp+278h+nSize], eax
0x18000387f  mov     eax, [rbx+44h]
0x180003882  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003886  mov     r9, rdi; unsigned __int16 *
0x180003889  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003890  mov     rdx, rsi; unsigned __int16 *
0x180003893  mov     rcx, r14; this
0x180003896  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000389b  cmp     [rbx+18h], r15
0x18000389f  jnz     short loc_1800038B1
0x1800038a1  cmp     [rbx+48h], r15
0x1800038a5  jnz     short loc_1800038B1
0x1800038a7  cmp     [rbx+30h], r15
0x1800038ab  jz      loc_180003941
0x1800038b1  lea     r8, asc_180023688; "    "
0x1800038b8  mov     rdx, rsi; unsigned __int16 *
0x1800038bb  mov     rcx, rax; this
0x1800038be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800038c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800038c7  test    r9, r9
0x1800038ca  jz      short loc_1800038DE
0x1800038cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800038d3  mov     rdx, rsi; unsigned __int16 *
0x1800038d6  mov     rcx, rax; this
0x1800038d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800038de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800038e2  test    r9, r9
0x1800038e5  jz      short loc_1800038F9
0x1800038e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800038ee  mov     rdx, rsi; unsigned __int16 *
0x1800038f1  mov     rcx, rax; this
0x1800038f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800038f9  mov     rcx, [rbx+28h]
0x1800038fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003901  mov     rdx, rsi; unsigned __int16 *
0x180003904  test    rcx, rcx
0x180003907  jz      short loc_18000391F
0x180003909  mov     [rsp+278h+lpBuffer], rcx
0x18000390e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003915  mov     rcx, rax; this
0x180003918  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000391d  jmp     short loc_180003941
0x18000391f  mov     rcx, rax; this
0x180003922  test    r9, r9
0x180003925  jz      short loc_180003935
0x180003927  lea     r8, aHs; "[%hs]\n"
0x18000392e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003933  jmp     short loc_180003941
0x180003935  lea     r8, asc_180023700; "\n"
0x18000393c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003941  xor     eax, eax
0x180003943  mov     rcx, [rsp+278h+var_38]
0x18000394b  xor     rcx, rsp; StackCookie
0x18000394e  call    __security_check_cookie
0x180003953  mov     rbx, [rsp+278h+arg_18]
0x18000395b  add     rsp, 250h
0x180003962  pop     r15
0x180003964  pop     r14
0x180003966  pop     rdi
0x180003967  pop     rsi
0x180003968  pop     rbp
0x180003969  retn
```
