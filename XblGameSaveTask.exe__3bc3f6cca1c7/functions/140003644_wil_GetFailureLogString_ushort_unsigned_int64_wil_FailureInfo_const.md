# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140003644`
- end: `0x1400038fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1400022b4`
- `0x140002524`
- `0x140003fa8`
- `0x140005640`

## callees

- `0x140001480`
- `0x140001f36`
- `0x140003644`
- `0x1400042a8`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400037f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400037f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003776`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003776`

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
          v7 = (const char *)&byte_1400088EF;
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
0x140003644  mov     [rsp+arg_18], rbx
0x140003649  push    rbp
0x14000364a  push    rsi
0x14000364b  push    rdi
0x14000364c  push    r14
0x14000364e  push    r15
0x140003650  sub     rsp, 250h
0x140003657  mov     rax, cs:__security_cookie
0x14000365e  xor     rax, rsp
0x140003661  mov     [rsp+278h+var_38], rax
0x140003669  mov     rbx, r8
0x14000366c  mov     rsi, rdx
0x14000366f  mov     r14, rcx
0x140003672  xor     r15d, r15d
0x140003675  test    rdx, rdx
0x140003678  jz      loc_1400038D1
0x14000367e  test    rcx, rcx
0x140003681  jz      loc_1400038D1
0x140003687  mov     [rcx], r15w
0x14000368b  mov     rax, cs:g_pfnResultLoggingCallback
0x140003692  test    rax, rax
0x140003695  jz      short loc_1400036B8
0x140003697  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000369e  jz      short loc_1400036B8
0x1400036a0  mov     r8, rdx
0x1400036a3  mov     rdx, rcx
0x1400036a6  mov     rcx, rbx
0x1400036a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036ae  cmp     [r14], r15w
0x1400036b2  jnz     loc_1400038D1
0x1400036b8  mov     ecx, [rbx]
0x1400036ba  mov     bpl, 8
0x1400036bd  test    ecx, ecx
0x1400036bf  jz      short loc_14000370A
0x1400036c1  sub     ecx, 1
0x1400036c4  jz      short loc_1400036F2
0x1400036c6  sub     ecx, 1
0x1400036c9  jz      short loc_1400036E2
0x1400036cb  cmp     ecx, 1
0x1400036ce  jz      short loc_1400036D9
0x1400036d0  lea     rdi, byte_1400088EF
0x1400036d7  jmp     short loc_140003711
0x1400036d9  lea     rdi, aFailfast; "FailFast"
0x1400036e0  jmp     short loc_140003711
0x1400036e2  lea     rax, aLoghr; "LogHr"
0x1400036e9  lea     rdi, aLognt; "LogNt"
0x1400036f0  jmp     short loc_140003700
0x1400036f2  lea     rax, aReturnhr; "ReturnHr"
0x1400036f9  lea     rdi, aReturnnt; "ReturnNt"
0x140003700  test    [rbx+4], bpl
0x140003704  cmovz   rdi, rax
0x140003708  jmp     short loc_140003711
0x14000370a  lea     rdi, aException; "Exception"
0x140003711  xor     edx, edx; Val
0x140003713  mov     r8d, 200h; Size
0x140003719  lea     rcx, [rsp+278h+Buffer]; void *
0x14000371e  call    memset_0
0x140003723  test    [rbx+4], bpl
0x140003727  jz      short loc_14000374C
0x140003729  mov     ebp, [rbx+0Ch]
0x14000372c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003733  test    rax, rax
0x140003736  jz      short loc_14000377C
0x140003738  mov     r8d, 100h
0x14000373e  lea     rdx, [rsp+278h+Buffer]
0x140003743  mov     ecx, ebp
0x140003745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000374a  jmp     short loc_14000377C
0x14000374c  mov     ebp, [rbx+8]
0x14000374f  mov     [rsp+278h+Arguments], r15; Arguments
0x140003754  mov     [rsp+278h+nSize], 100h; nSize
0x14000375c  lea     rax, [rsp+278h+Buffer]
0x140003761  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003766  mov     r9d, 400h; dwLanguageId
0x14000376c  mov     r8d, ebp; dwMessageId
0x14000376f  xor     edx, edx; lpSource
0x140003771  mov     ecx, 1200h; dwFlags
0x140003776  call    cs:__imp_FormatMessageW
0x14000377c  lea     rsi, [r14+rsi*2]
0x140003780  mov     r9, [rbx+38h]; unsigned __int16 *
0x140003784  mov     rax, [rbx+88h]
0x14000378b  mov     rcx, [rbx+80h]
0x140003792  mov     rdx, rsi; unsigned __int16 *
0x140003795  test    r9, r9
0x140003798  jz      short loc_1400037BC
0x14000379a  mov     [rsp+278h+Arguments], rax
0x14000379f  mov     qword ptr [rsp+278h+nSize], rcx
0x1400037a4  mov     eax, [rbx+40h]
0x1400037a7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400037ab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400037b2  mov     rcx, r14; this
0x1400037b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400037ba  jmp     short loc_1400037D3
0x1400037bc  mov     [rsp+278h+lpBuffer], rax
0x1400037c1  mov     r9, rcx; unsigned __int16 *
0x1400037c4  lea     r8, aHsP; "%hs!%p: "
0x1400037cb  mov     rcx, r14; this
0x1400037ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400037d3  mov     r14, rax
0x1400037d6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400037dd  test    r9, r9
0x1400037e0  jz      short loc_1400037F7
0x1400037e2  lea     r8, aCallerP; "(caller: %p) "
0x1400037e9  mov     rdx, rsi; unsigned __int16 *
0x1400037ec  mov     rcx, rax; this
0x1400037ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400037f4  mov     r14, rax
0x1400037f7  call    cs:__imp_GetCurrentThreadId
0x1400037fd  lea     rcx, [rsp+278h+Buffer]
0x140003802  mov     [rsp+278h+var_240], rcx
0x140003807  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000380b  mov     [rsp+278h+nSize], eax
0x14000380f  mov     eax, [rbx+44h]
0x140003812  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003816  mov     r9, rdi; unsigned __int16 *
0x140003819  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003820  mov     rdx, rsi; unsigned __int16 *
0x140003823  mov     rcx, r14; this
0x140003826  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000382b  cmp     [rbx+18h], r15
0x14000382f  jnz     short loc_140003841
0x140003831  cmp     [rbx+48h], r15
0x140003835  jnz     short loc_140003841
0x140003837  cmp     [rbx+30h], r15
0x14000383b  jz      loc_1400038D1
0x140003841  lea     r8, asc_1400089F0; "    "
0x140003848  mov     rdx, rsi; unsigned __int16 *
0x14000384b  mov     rcx, rax; this
0x14000384e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003853  mov     r9, [rbx+18h]; unsigned __int16 *
0x140003857  test    r9, r9
0x14000385a  jz      short loc_14000386E
0x14000385c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140003863  mov     rdx, rsi; unsigned __int16 *
0x140003866  mov     rcx, rax; this
0x140003869  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000386e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140003872  test    r9, r9
0x140003875  jz      short loc_140003889
0x140003877  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000387e  mov     rdx, rsi; unsigned __int16 *
0x140003881  mov     rcx, rax; this
0x140003884  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003889  mov     rcx, [rbx+28h]
0x14000388d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140003891  mov     rdx, rsi; unsigned __int16 *
0x140003894  test    rcx, rcx
0x140003897  jz      short loc_1400038AF
0x140003899  mov     [rsp+278h+lpBuffer], rcx
0x14000389e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400038a5  mov     rcx, rax; this
0x1400038a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038ad  jmp     short loc_1400038D1
0x1400038af  mov     rcx, rax; this
0x1400038b2  test    r9, r9
0x1400038b5  jz      short loc_1400038C5
0x1400038b7  lea     r8, aHs; "[%hs]\n"
0x1400038be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038c3  jmp     short loc_1400038D1
0x1400038c5  lea     r8, asc_140008A68; "\n"
0x1400038cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038d1  xor     eax, eax
0x1400038d3  mov     rcx, [rsp+278h+var_38]
0x1400038db  xor     rcx, rsp; StackCookie
0x1400038de  call    __security_check_cookie
0x1400038e3  mov     rbx, [rsp+278h+arg_18]
0x1400038eb  add     rsp, 250h
0x1400038f2  pop     r15
0x1400038f4  pop     r14
0x1400038f6  pop     rdi
0x1400038f7  pop     rsi
0x1400038f8  pop     rbp
0x1400038f9  retn
```
