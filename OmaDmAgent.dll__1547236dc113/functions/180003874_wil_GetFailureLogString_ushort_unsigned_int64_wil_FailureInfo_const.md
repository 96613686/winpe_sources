# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003874`
- end: `0x180003b37`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000253c`
- `0x18000427c`
- `0x18000474c`
- `0x180006bb0`

## callees

- `0x180003874`
- `0x180004590`
- `0x18001f3da`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800039a6`
- `KERNEL32!FormatMessageW` at `0x1800039a6`
- `KERNEL32!GetCurrentThreadId` at `0x180003a2d`
- `KERNEL32!GetCurrentThreadId` at `0x180003a2d`

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
          v7 = (const char *)&byte_180022F68;
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
0x180003874  mov     [rsp+arg_18], rbx
0x180003879  push    rbp
0x18000387a  push    rsi
0x18000387b  push    rdi
0x18000387c  push    r14
0x18000387e  push    r15
0x180003880  sub     rsp, 250h
0x180003887  mov     rax, cs:__security_cookie
0x18000388e  xor     rax, rsp
0x180003891  mov     [rsp+278h+var_38], rax
0x180003899  mov     rbx, r8
0x18000389c  mov     rsi, rdx
0x18000389f  mov     r14, rcx
0x1800038a2  xor     r15d, r15d
0x1800038a5  test    rdx, rdx
0x1800038a8  jz      loc_180003B0D
0x1800038ae  test    rcx, rcx
0x1800038b1  jz      loc_180003B0D
0x1800038b7  mov     [rcx], r15w
0x1800038bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800038c2  test    rax, rax
0x1800038c5  jz      short loc_1800038E8
0x1800038c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800038ce  jz      short loc_1800038E8
0x1800038d0  mov     r8, rdx
0x1800038d3  mov     rdx, rcx
0x1800038d6  mov     rcx, rbx
0x1800038d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038de  cmp     [r14], r15w
0x1800038e2  jnz     loc_180003B0D
0x1800038e8  mov     ecx, [rbx]
0x1800038ea  mov     bpl, 8
0x1800038ed  test    ecx, ecx
0x1800038ef  jz      short loc_18000393A
0x1800038f1  sub     ecx, 1
0x1800038f4  jz      short loc_180003922
0x1800038f6  sub     ecx, 1
0x1800038f9  jz      short loc_180003912
0x1800038fb  cmp     ecx, 1
0x1800038fe  jz      short loc_180003909
0x180003900  lea     rdi, byte_180022F68
0x180003907  jmp     short loc_180003941
0x180003909  lea     rdi, aFailfast; "FailFast"
0x180003910  jmp     short loc_180003941
0x180003912  lea     rax, aLoghr; "LogHr"
0x180003919  lea     rdi, aLognt; "LogNt"
0x180003920  jmp     short loc_180003930
0x180003922  lea     rax, aReturnhr; "ReturnHr"
0x180003929  lea     rdi, aReturnnt; "ReturnNt"
0x180003930  test    [rbx+4], bpl
0x180003934  cmovz   rdi, rax
0x180003938  jmp     short loc_180003941
0x18000393a  lea     rdi, aException; "Exception"
0x180003941  xor     edx, edx; Val
0x180003943  mov     r8d, 200h; Size
0x180003949  lea     rcx, [rsp+278h+Buffer]; void *
0x18000394e  call    memset_0
0x180003953  test    [rbx+4], bpl
0x180003957  jz      short loc_18000397C
0x180003959  mov     ebp, [rbx+0Ch]
0x18000395c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003963  test    rax, rax
0x180003966  jz      short loc_1800039B2
0x180003968  mov     r8d, 100h
0x18000396e  lea     rdx, [rsp+278h+Buffer]
0x180003973  mov     ecx, ebp
0x180003975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000397a  jmp     short loc_1800039B2
0x18000397c  mov     ebp, [rbx+8]
0x18000397f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003984  mov     [rsp+278h+nSize], 100h; nSize
0x18000398c  lea     rax, [rsp+278h+Buffer]
0x180003991  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003996  mov     r9d, 400h; dwLanguageId
0x18000399c  mov     r8d, ebp; dwMessageId
0x18000399f  xor     edx, edx; lpSource
0x1800039a1  mov     ecx, 1200h; dwFlags
0x1800039a6  call    cs:__imp_FormatMessageW
0x1800039ad  nop     dword ptr [rax+rax+00h]
0x1800039b2  lea     rsi, [r14+rsi*2]
0x1800039b6  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800039ba  mov     rax, [rbx+88h]
0x1800039c1  mov     rcx, [rbx+80h]
0x1800039c8  mov     rdx, rsi; unsigned __int16 *
0x1800039cb  test    r9, r9
0x1800039ce  jz      short loc_1800039F2
0x1800039d0  mov     [rsp+278h+Arguments], rax
0x1800039d5  mov     qword ptr [rsp+278h+nSize], rcx
0x1800039da  mov     eax, [rbx+40h]
0x1800039dd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800039e1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800039e8  mov     rcx, r14; this
0x1800039eb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800039f0  jmp     short loc_180003A09
0x1800039f2  mov     [rsp+278h+lpBuffer], rax
0x1800039f7  mov     r9, rcx; unsigned __int16 *
0x1800039fa  lea     r8, aHsP; "%hs!%p: "
0x180003a01  mov     rcx, r14; this
0x180003a04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a09  mov     r14, rax
0x180003a0c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003a13  test    r9, r9
0x180003a16  jz      short loc_180003A2D
0x180003a18  lea     r8, aCallerP; "(caller: %p) "
0x180003a1f  mov     rdx, rsi; unsigned __int16 *
0x180003a22  mov     rcx, rax; this
0x180003a25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a2a  mov     r14, rax
0x180003a2d  call    cs:__imp_GetCurrentThreadId
0x180003a34  nop     dword ptr [rax+rax+00h]
0x180003a39  lea     rcx, [rsp+278h+Buffer]
0x180003a3e  mov     [rsp+278h+var_240], rcx
0x180003a43  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003a47  mov     [rsp+278h+nSize], eax
0x180003a4b  mov     eax, [rbx+44h]
0x180003a4e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003a52  mov     r9, rdi; unsigned __int16 *
0x180003a55  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003a5c  mov     rdx, rsi; unsigned __int16 *
0x180003a5f  mov     rcx, r14; this
0x180003a62  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a67  cmp     [rbx+18h], r15
0x180003a6b  jnz     short loc_180003A7D
0x180003a6d  cmp     [rbx+48h], r15
0x180003a71  jnz     short loc_180003A7D
0x180003a73  cmp     [rbx+30h], r15
0x180003a77  jz      loc_180003B0D
0x180003a7d  lea     r8, asc_1800230A8; "    "
0x180003a84  mov     rdx, rsi; unsigned __int16 *
0x180003a87  mov     rcx, rax; this
0x180003a8a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a8f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003a93  test    r9, r9
0x180003a96  jz      short loc_180003AAA
0x180003a98  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003a9f  mov     rdx, rsi; unsigned __int16 *
0x180003aa2  mov     rcx, rax; this
0x180003aa5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003aaa  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003aae  test    r9, r9
0x180003ab1  jz      short loc_180003AC5
0x180003ab3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003aba  mov     rdx, rsi; unsigned __int16 *
0x180003abd  mov     rcx, rax; this
0x180003ac0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ac5  mov     rcx, [rbx+28h]
0x180003ac9  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003acd  mov     rdx, rsi; unsigned __int16 *
0x180003ad0  test    rcx, rcx
0x180003ad3  jz      short loc_180003AEB
0x180003ad5  mov     [rsp+278h+lpBuffer], rcx
0x180003ada  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003ae1  mov     rcx, rax; this
0x180003ae4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ae9  jmp     short loc_180003B0D
0x180003aeb  mov     rcx, rax; this
0x180003aee  test    r9, r9
0x180003af1  jz      short loc_180003B01
0x180003af3  lea     r8, aHs; "[%hs]\n"
0x180003afa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003aff  jmp     short loc_180003B0D
0x180003b01  lea     r8, asc_180023120; "\n"
0x180003b08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b0d  xor     eax, eax
0x180003b0f  mov     rcx, [rsp+278h+var_38]
0x180003b17  xor     rcx, rsp; StackCookie
0x180003b1a  call    __security_check_cookie
0x180003b1f  mov     rbx, [rsp+278h+arg_18]
0x180003b27  add     rsp, 250h
0x180003b2e  pop     r15
0x180003b30  pop     r14
0x180003b32  pop     rdi
0x180003b33  pop     rsi
0x180003b34  pop     rbp
0x180003b35  retn
```
