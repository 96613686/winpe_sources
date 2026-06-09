# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006054`
- end: `0x18000630a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002914`
- `0x180002b7c`
- `0x180006ae0`
- `0x18000c2f0`

## callees

- `0x180006054`
- `0x180006de0`
- `0x180010792`
- `0x1800107c0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006207`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006207`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006186`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006186`

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
          v7 = (const char *)&dword_180014F84;
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
0x180006054  mov     [rsp+arg_18], rbx
0x180006059  push    rbp
0x18000605a  push    rsi
0x18000605b  push    rdi
0x18000605c  push    r14
0x18000605e  push    r15
0x180006060  sub     rsp, 250h
0x180006067  mov     rax, cs:__security_cookie
0x18000606e  xor     rax, rsp
0x180006071  mov     [rsp+278h+var_38], rax
0x180006079  mov     rbx, r8
0x18000607c  mov     rsi, rdx
0x18000607f  mov     r14, rcx
0x180006082  xor     r15d, r15d
0x180006085  test    rdx, rdx
0x180006088  jz      loc_1800062E1
0x18000608e  test    rcx, rcx
0x180006091  jz      loc_1800062E1
0x180006097  mov     [rcx], r15w
0x18000609b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800060a2  test    rax, rax
0x1800060a5  jz      short loc_1800060C8
0x1800060a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800060ae  jz      short loc_1800060C8
0x1800060b0  mov     r8, rdx
0x1800060b3  mov     rdx, rcx
0x1800060b6  mov     rcx, rbx
0x1800060b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060be  cmp     [r14], r15w
0x1800060c2  jnz     loc_1800062E1
0x1800060c8  mov     ecx, [rbx]
0x1800060ca  mov     bpl, 8
0x1800060cd  test    ecx, ecx
0x1800060cf  jz      short loc_18000611A
0x1800060d1  sub     ecx, 1
0x1800060d4  jz      short loc_180006102
0x1800060d6  sub     ecx, 1
0x1800060d9  jz      short loc_1800060F2
0x1800060db  cmp     ecx, 1
0x1800060de  jz      short loc_1800060E9
0x1800060e0  lea     rdi, dword_180014F84
0x1800060e7  jmp     short loc_180006121
0x1800060e9  lea     rdi, aFailfast; "FailFast"
0x1800060f0  jmp     short loc_180006121
0x1800060f2  lea     rax, aLoghr; "LogHr"
0x1800060f9  lea     rdi, aLognt; "LogNt"
0x180006100  jmp     short loc_180006110
0x180006102  lea     rax, aReturnhr; "ReturnHr"
0x180006109  lea     rdi, aReturnnt; "ReturnNt"
0x180006110  test    [rbx+4], bpl
0x180006114  cmovz   rdi, rax
0x180006118  jmp     short loc_180006121
0x18000611a  lea     rdi, aException; "Exception"
0x180006121  xor     edx, edx; Val
0x180006123  mov     r8d, 200h; Size
0x180006129  lea     rcx, [rsp+278h+Buffer]; void *
0x18000612e  call    memset_0
0x180006133  test    [rbx+4], bpl
0x180006137  jz      short loc_18000615C
0x180006139  mov     ebp, [rbx+0Ch]
0x18000613c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006143  test    rax, rax
0x180006146  jz      short loc_18000618C
0x180006148  mov     r8d, 100h
0x18000614e  lea     rdx, [rsp+278h+Buffer]
0x180006153  mov     ecx, ebp
0x180006155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000615a  jmp     short loc_18000618C
0x18000615c  mov     ebp, [rbx+8]
0x18000615f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006164  mov     [rsp+278h+nSize], 100h; nSize
0x18000616c  lea     rax, [rsp+278h+Buffer]
0x180006171  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006176  mov     r9d, 400h; dwLanguageId
0x18000617c  mov     r8d, ebp; dwMessageId
0x18000617f  xor     edx, edx; lpSource
0x180006181  mov     ecx, 1200h; dwFlags
0x180006186  call    cs:__imp_FormatMessageW
0x18000618c  lea     rsi, [r14+rsi*2]
0x180006190  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006194  mov     rax, [rbx+88h]
0x18000619b  mov     rcx, [rbx+80h]
0x1800061a2  mov     rdx, rsi; unsigned __int16 *
0x1800061a5  test    r9, r9
0x1800061a8  jz      short loc_1800061CC
0x1800061aa  mov     [rsp+278h+Arguments], rax
0x1800061af  mov     qword ptr [rsp+278h+nSize], rcx
0x1800061b4  mov     eax, [rbx+40h]
0x1800061b7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800061bb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800061c2  mov     rcx, r14; this
0x1800061c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061ca  jmp     short loc_1800061E3
0x1800061cc  mov     [rsp+278h+lpBuffer], rax
0x1800061d1  mov     r9, rcx; unsigned __int16 *
0x1800061d4  lea     r8, aHsP; "%hs!%p: "
0x1800061db  mov     rcx, r14; this
0x1800061de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061e3  mov     r14, rax
0x1800061e6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800061ed  test    r9, r9
0x1800061f0  jz      short loc_180006207
0x1800061f2  lea     r8, aCallerP; "(caller: %p) "
0x1800061f9  mov     rdx, rsi; unsigned __int16 *
0x1800061fc  mov     rcx, rax; this
0x1800061ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006204  mov     r14, rax
0x180006207  call    cs:__imp_GetCurrentThreadId
0x18000620d  lea     rcx, [rsp+278h+Buffer]
0x180006212  mov     [rsp+278h+var_240], rcx
0x180006217  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000621b  mov     [rsp+278h+nSize], eax
0x18000621f  mov     eax, [rbx+44h]
0x180006222  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006226  mov     r9, rdi; unsigned __int16 *
0x180006229  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006230  mov     rdx, rsi; unsigned __int16 *
0x180006233  mov     rcx, r14; this
0x180006236  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000623b  cmp     [rbx+18h], r15
0x18000623f  jnz     short loc_180006251
0x180006241  cmp     [rbx+48h], r15
0x180006245  jnz     short loc_180006251
0x180006247  cmp     [rbx+30h], r15
0x18000624b  jz      loc_1800062E1
0x180006251  lea     r8, asc_1800150C8; "    "
0x180006258  mov     rdx, rsi; unsigned __int16 *
0x18000625b  mov     rcx, rax; this
0x18000625e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006263  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006267  test    r9, r9
0x18000626a  jz      short loc_18000627E
0x18000626c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006273  mov     rdx, rsi; unsigned __int16 *
0x180006276  mov     rcx, rax; this
0x180006279  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000627e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006282  test    r9, r9
0x180006285  jz      short loc_180006299
0x180006287  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000628e  mov     rdx, rsi; unsigned __int16 *
0x180006291  mov     rcx, rax; this
0x180006294  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006299  mov     rcx, [rbx+28h]
0x18000629d  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800062a1  mov     rdx, rsi; unsigned __int16 *
0x1800062a4  test    rcx, rcx
0x1800062a7  jz      short loc_1800062BF
0x1800062a9  mov     [rsp+278h+lpBuffer], rcx
0x1800062ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800062b5  mov     rcx, rax; this
0x1800062b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800062bd  jmp     short loc_1800062E1
0x1800062bf  mov     rcx, rax; this
0x1800062c2  test    r9, r9
0x1800062c5  jz      short loc_1800062D5
0x1800062c7  lea     r8, aHs; "[%hs]\n"
0x1800062ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800062d3  jmp     short loc_1800062E1
0x1800062d5  lea     r8, asc_180015140; "\n"
0x1800062dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800062e1  xor     eax, eax
0x1800062e3  mov     rcx, [rsp+278h+var_38]
0x1800062eb  xor     rcx, rsp; StackCookie
0x1800062ee  call    __security_check_cookie
0x1800062f3  mov     rbx, [rsp+278h+arg_18]
0x1800062fb  add     rsp, 250h
0x180006302  pop     r15
0x180006304  pop     r14
0x180006306  pop     rdi
0x180006307  pop     rsi
0x180006308  pop     rbp
0x180006309  retn
```
