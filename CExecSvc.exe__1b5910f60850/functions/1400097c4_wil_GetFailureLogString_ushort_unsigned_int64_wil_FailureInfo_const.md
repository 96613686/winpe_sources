# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400097c4`
- end: `0x140009a7a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x140005770`
- `0x1400059f0`
- `0x140005cbc`
- `0x14000a23c`
- `0x14000d900`
- `0x14000ec60`
- `0x140022679`
- `0x1400227ad`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x1400097c4`
- `0x14000a53c`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009977`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009977`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400098f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400098f6`

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
          v7 = (const char *)&byte_1400273CD;
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
0x1400097c4  mov     [rsp+arg_18], rbx
0x1400097c9  push    rbp
0x1400097ca  push    rsi
0x1400097cb  push    rdi
0x1400097cc  push    r14
0x1400097ce  push    r15
0x1400097d0  sub     rsp, 250h
0x1400097d7  mov     rax, cs:__security_cookie
0x1400097de  xor     rax, rsp
0x1400097e1  mov     [rsp+278h+var_38], rax
0x1400097e9  mov     rbx, r8
0x1400097ec  mov     rsi, rdx
0x1400097ef  mov     r14, rcx
0x1400097f2  xor     r15d, r15d
0x1400097f5  test    rdx, rdx
0x1400097f8  jz      loc_140009A51
0x1400097fe  test    rcx, rcx
0x140009801  jz      loc_140009A51
0x140009807  mov     [rcx], r15w
0x14000980b  mov     rax, cs:g_pfnResultLoggingCallback
0x140009812  test    rax, rax
0x140009815  jz      short loc_140009838
0x140009817  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000981e  jz      short loc_140009838
0x140009820  mov     r8, rdx
0x140009823  mov     rdx, rcx
0x140009826  mov     rcx, rbx
0x140009829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000982e  cmp     [r14], r15w
0x140009832  jnz     loc_140009A51
0x140009838  mov     ecx, [rbx]
0x14000983a  mov     bpl, 8
0x14000983d  test    ecx, ecx
0x14000983f  jz      short loc_14000988A
0x140009841  sub     ecx, 1
0x140009844  jz      short loc_140009872
0x140009846  sub     ecx, 1
0x140009849  jz      short loc_140009862
0x14000984b  cmp     ecx, 1
0x14000984e  jz      short loc_140009859
0x140009850  lea     rdi, byte_1400273CD
0x140009857  jmp     short loc_140009891
0x140009859  lea     rdi, aFailfast; "FailFast"
0x140009860  jmp     short loc_140009891
0x140009862  lea     rax, aLoghr; "LogHr"
0x140009869  lea     rdi, aLognt; "LogNt"
0x140009870  jmp     short loc_140009880
0x140009872  lea     rax, aReturnhr; "ReturnHr"
0x140009879  lea     rdi, aReturnnt; "ReturnNt"
0x140009880  test    [rbx+4], bpl
0x140009884  cmovz   rdi, rax
0x140009888  jmp     short loc_140009891
0x14000988a  lea     rdi, aException; "Exception"
0x140009891  xor     edx, edx; Val
0x140009893  mov     r8d, 200h; Size
0x140009899  lea     rcx, [rsp+278h+Buffer]; void *
0x14000989e  call    memset_0
0x1400098a3  test    [rbx+4], bpl
0x1400098a7  jz      short loc_1400098CC
0x1400098a9  mov     ebp, [rbx+0Ch]
0x1400098ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400098b3  test    rax, rax
0x1400098b6  jz      short loc_1400098FC
0x1400098b8  mov     r8d, 100h
0x1400098be  lea     rdx, [rsp+278h+Buffer]
0x1400098c3  mov     ecx, ebp
0x1400098c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098ca  jmp     short loc_1400098FC
0x1400098cc  mov     ebp, [rbx+8]
0x1400098cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1400098d4  mov     [rsp+278h+nSize], 100h; nSize
0x1400098dc  lea     rax, [rsp+278h+Buffer]
0x1400098e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400098e6  mov     r9d, 400h; dwLanguageId
0x1400098ec  mov     r8d, ebp; dwMessageId
0x1400098ef  xor     edx, edx; lpSource
0x1400098f1  mov     ecx, 1200h; dwFlags
0x1400098f6  call    cs:__imp_FormatMessageW
0x1400098fc  lea     rsi, [r14+rsi*2]
0x140009900  mov     r9, [rbx+38h]; unsigned __int16 *
0x140009904  mov     rax, [rbx+88h]
0x14000990b  mov     rcx, [rbx+80h]
0x140009912  mov     rdx, rsi; unsigned __int16 *
0x140009915  test    r9, r9
0x140009918  jz      short loc_14000993C
0x14000991a  mov     [rsp+278h+Arguments], rax
0x14000991f  mov     qword ptr [rsp+278h+nSize], rcx
0x140009924  mov     eax, [rbx+40h]
0x140009927  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000992b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140009932  mov     rcx, r14; this
0x140009935  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000993a  jmp     short loc_140009953
0x14000993c  mov     [rsp+278h+lpBuffer], rax
0x140009941  mov     r9, rcx; unsigned __int16 *
0x140009944  lea     r8, aHsP; "%hs!%p: "
0x14000994b  mov     rcx, r14; this
0x14000994e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009953  mov     r14, rax
0x140009956  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000995d  test    r9, r9
0x140009960  jz      short loc_140009977
0x140009962  lea     r8, aCallerP; "(caller: %p) "
0x140009969  mov     rdx, rsi; unsigned __int16 *
0x14000996c  mov     rcx, rax; this
0x14000996f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009974  mov     r14, rax
0x140009977  call    cs:__imp_GetCurrentThreadId
0x14000997d  lea     rcx, [rsp+278h+Buffer]
0x140009982  mov     [rsp+278h+var_240], rcx
0x140009987  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000998b  mov     [rsp+278h+nSize], eax
0x14000998f  mov     eax, [rbx+44h]
0x140009992  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140009996  mov     r9, rdi; unsigned __int16 *
0x140009999  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400099a0  mov     rdx, rsi; unsigned __int16 *
0x1400099a3  mov     rcx, r14; this
0x1400099a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400099ab  cmp     [rbx+18h], r15
0x1400099af  jnz     short loc_1400099C1
0x1400099b1  cmp     [rbx+48h], r15
0x1400099b5  jnz     short loc_1400099C1
0x1400099b7  cmp     [rbx+30h], r15
0x1400099bb  jz      loc_140009A51
0x1400099c1  lea     r8, asc_140027508; "    "
0x1400099c8  mov     rdx, rsi; unsigned __int16 *
0x1400099cb  mov     rcx, rax; this
0x1400099ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400099d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400099d7  test    r9, r9
0x1400099da  jz      short loc_1400099EE
0x1400099dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400099e3  mov     rdx, rsi; unsigned __int16 *
0x1400099e6  mov     rcx, rax; this
0x1400099e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400099ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400099f2  test    r9, r9
0x1400099f5  jz      short loc_140009A09
0x1400099f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400099fe  mov     rdx, rsi; unsigned __int16 *
0x140009a01  mov     rcx, rax; this
0x140009a04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009a09  mov     rcx, [rbx+28h]
0x140009a0d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140009a11  mov     rdx, rsi; unsigned __int16 *
0x140009a14  test    rcx, rcx
0x140009a17  jz      short loc_140009A2F
0x140009a19  mov     [rsp+278h+lpBuffer], rcx
0x140009a1e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140009a25  mov     rcx, rax; this
0x140009a28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009a2d  jmp     short loc_140009A51
0x140009a2f  mov     rcx, rax; this
0x140009a32  test    r9, r9
0x140009a35  jz      short loc_140009A45
0x140009a37  lea     r8, aHs; "[%hs]\n"
0x140009a3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009a43  jmp     short loc_140009A51
0x140009a45  lea     r8, asc_140027580; "\n"
0x140009a4c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009a51  xor     eax, eax
0x140009a53  mov     rcx, [rsp+278h+var_38]
0x140009a5b  xor     rcx, rsp; StackCookie
0x140009a5e  call    __security_check_cookie
0x140009a63  mov     rbx, [rsp+278h+arg_18]
0x140009a6b  add     rsp, 250h
0x140009a72  pop     r15
0x140009a74  pop     r14
0x140009a76  pop     rdi
0x140009a77  pop     rsi
0x140009a78  pop     rbp
0x140009a79  retn
```
