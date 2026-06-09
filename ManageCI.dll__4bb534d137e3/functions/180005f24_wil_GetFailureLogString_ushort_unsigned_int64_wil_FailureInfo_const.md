# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005f24`
- end: `0x1800061da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800043f8`
- `0x180006908`
- `0x180006dd0`
- `0x180008810`

## callees

- `0x180002a90`
- `0x180003888`
- `0x180005f24`
- `0x180006c08`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006056`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006056`

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
          v7 = (const char *)&byte_18002EDD0;
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
0x180005f24  mov     [rsp+arg_18], rbx
0x180005f29  push    rbp
0x180005f2a  push    rsi
0x180005f2b  push    rdi
0x180005f2c  push    r14
0x180005f2e  push    r15
0x180005f30  sub     rsp, 250h
0x180005f37  mov     rax, cs:__security_cookie
0x180005f3e  xor     rax, rsp
0x180005f41  mov     [rsp+278h+var_38], rax
0x180005f49  mov     rbx, r8
0x180005f4c  mov     rsi, rdx
0x180005f4f  mov     r14, rcx
0x180005f52  xor     r15d, r15d
0x180005f55  test    rdx, rdx
0x180005f58  jz      loc_1800061B1
0x180005f5e  test    rcx, rcx
0x180005f61  jz      loc_1800061B1
0x180005f67  mov     [rcx], r15w
0x180005f6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005f72  test    rax, rax
0x180005f75  jz      short loc_180005F98
0x180005f77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005f7e  jz      short loc_180005F98
0x180005f80  mov     r8, rdx
0x180005f83  mov     rdx, rcx
0x180005f86  mov     rcx, rbx
0x180005f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f8e  cmp     [r14], r15w
0x180005f92  jnz     loc_1800061B1
0x180005f98  mov     ecx, [rbx]
0x180005f9a  mov     bpl, 8
0x180005f9d  test    ecx, ecx
0x180005f9f  jz      short loc_180005FEA
0x180005fa1  sub     ecx, 1
0x180005fa4  jz      short loc_180005FD2
0x180005fa6  sub     ecx, 1
0x180005fa9  jz      short loc_180005FC2
0x180005fab  cmp     ecx, 1
0x180005fae  jz      short loc_180005FB9
0x180005fb0  lea     rdi, byte_18002EDD0
0x180005fb7  jmp     short loc_180005FF1
0x180005fb9  lea     rdi, aFailfast; "FailFast"
0x180005fc0  jmp     short loc_180005FF1
0x180005fc2  lea     rax, aLoghr; "LogHr"
0x180005fc9  lea     rdi, aLognt; "LogNt"
0x180005fd0  jmp     short loc_180005FE0
0x180005fd2  lea     rax, aReturnhr; "ReturnHr"
0x180005fd9  lea     rdi, aReturnnt; "ReturnNt"
0x180005fe0  test    [rbx+4], bpl
0x180005fe4  cmovz   rdi, rax
0x180005fe8  jmp     short loc_180005FF1
0x180005fea  lea     rdi, aException; "Exception"
0x180005ff1  xor     edx, edx; Val
0x180005ff3  mov     r8d, 200h; Size
0x180005ff9  lea     rcx, [rsp+278h+Buffer]; void *
0x180005ffe  call    memset_0
0x180006003  test    [rbx+4], bpl
0x180006007  jz      short loc_18000602C
0x180006009  mov     ebp, [rbx+0Ch]
0x18000600c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006013  test    rax, rax
0x180006016  jz      short loc_18000605C
0x180006018  mov     r8d, 100h
0x18000601e  lea     rdx, [rsp+278h+Buffer]
0x180006023  mov     ecx, ebp
0x180006025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000602a  jmp     short loc_18000605C
0x18000602c  mov     ebp, [rbx+8]
0x18000602f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006034  mov     [rsp+278h+nSize], 100h; nSize
0x18000603c  lea     rax, [rsp+278h+Buffer]
0x180006041  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006046  mov     r9d, 400h; dwLanguageId
0x18000604c  mov     r8d, ebp; dwMessageId
0x18000604f  xor     edx, edx; lpSource
0x180006051  mov     ecx, 1200h; dwFlags
0x180006056  call    cs:__imp_FormatMessageW
0x18000605c  lea     rsi, [r14+rsi*2]
0x180006060  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006064  mov     rax, [rbx+88h]
0x18000606b  mov     rcx, [rbx+80h]
0x180006072  mov     rdx, rsi; unsigned __int16 *
0x180006075  test    r9, r9
0x180006078  jz      short loc_18000609C
0x18000607a  mov     [rsp+278h+Arguments], rax
0x18000607f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006084  mov     eax, [rbx+40h]
0x180006087  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000608b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006092  mov     rcx, r14; this
0x180006095  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000609a  jmp     short loc_1800060B3
0x18000609c  mov     [rsp+278h+lpBuffer], rax
0x1800060a1  mov     r9, rcx; unsigned __int16 *
0x1800060a4  lea     r8, aHsP; "%hs!%p: "
0x1800060ab  mov     rcx, r14; this
0x1800060ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800060b3  mov     r14, rax
0x1800060b6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800060bd  test    r9, r9
0x1800060c0  jz      short loc_1800060D7
0x1800060c2  lea     r8, aCallerP; "(caller: %p) "
0x1800060c9  mov     rdx, rsi; unsigned __int16 *
0x1800060cc  mov     rcx, rax; this
0x1800060cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800060d4  mov     r14, rax
0x1800060d7  call    cs:__imp_GetCurrentThreadId
0x1800060dd  lea     rcx, [rsp+278h+Buffer]
0x1800060e2  mov     [rsp+278h+var_240], rcx
0x1800060e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800060eb  mov     [rsp+278h+nSize], eax
0x1800060ef  mov     eax, [rbx+44h]
0x1800060f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800060f6  mov     r9, rdi; unsigned __int16 *
0x1800060f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006100  mov     rdx, rsi; unsigned __int16 *
0x180006103  mov     rcx, r14; this
0x180006106  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000610b  cmp     [rbx+18h], r15
0x18000610f  jnz     short loc_180006121
0x180006111  cmp     [rbx+48h], r15
0x180006115  jnz     short loc_180006121
0x180006117  cmp     [rbx+30h], r15
0x18000611b  jz      loc_1800061B1
0x180006121  lea     r8, asc_18002EEC0; "    "
0x180006128  mov     rdx, rsi; unsigned __int16 *
0x18000612b  mov     rcx, rax; this
0x18000612e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006133  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006137  test    r9, r9
0x18000613a  jz      short loc_18000614E
0x18000613c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006143  mov     rdx, rsi; unsigned __int16 *
0x180006146  mov     rcx, rax; this
0x180006149  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000614e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006152  test    r9, r9
0x180006155  jz      short loc_180006169
0x180006157  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000615e  mov     rdx, rsi; unsigned __int16 *
0x180006161  mov     rcx, rax; this
0x180006164  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006169  mov     rcx, [rbx+28h]
0x18000616d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006171  mov     rdx, rsi; unsigned __int16 *
0x180006174  test    rcx, rcx
0x180006177  jz      short loc_18000618F
0x180006179  mov     [rsp+278h+lpBuffer], rcx
0x18000617e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006185  mov     rcx, rax; this
0x180006188  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000618d  jmp     short loc_1800061B1
0x18000618f  mov     rcx, rax; this
0x180006192  test    r9, r9
0x180006195  jz      short loc_1800061A5
0x180006197  lea     r8, aHs; "[%hs]\n"
0x18000619e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061a3  jmp     short loc_1800061B1
0x1800061a5  lea     r8, asc_18002EF38; "\n"
0x1800061ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061b1  xor     eax, eax
0x1800061b3  mov     rcx, [rsp+278h+var_38]
0x1800061bb  xor     rcx, rsp; StackCookie
0x1800061be  call    __security_check_cookie
0x1800061c3  mov     rbx, [rsp+278h+arg_18]
0x1800061cb  add     rsp, 250h
0x1800061d2  pop     r15
0x1800061d4  pop     r14
0x1800061d6  pop     rdi
0x1800061d7  pop     rsi
0x1800061d8  pop     rbp
0x1800061d9  retn
```
