# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180011ce4`
- end: `0x180011f9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180010c58`
- `0x180010ec8`
- `0x180012640`

## callees

- `0x180011ce4`
- `0x180012940`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180011e97`
- `KERNEL32!GetCurrentThreadId` at `0x180011e97`
- `KERNEL32!FormatMessageW` at `0x180011e16`
- `KERNEL32!FormatMessageW` at `0x180011e16`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&dword_180017D6C;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011ce4  mov     [rsp+arg_18], rbx
0x180011ce9  push    rbp
0x180011cea  push    rsi
0x180011ceb  push    rdi
0x180011cec  push    r14
0x180011cee  push    r15
0x180011cf0  sub     rsp, 250h
0x180011cf7  mov     rax, cs:__security_cookie
0x180011cfe  xor     rax, rsp
0x180011d01  mov     [rsp+278h+var_38], rax
0x180011d09  xor     r15d, r15d
0x180011d0c  mov     rbx, r8
0x180011d0f  mov     rsi, rdx
0x180011d12  mov     r14, rcx
0x180011d15  test    rdx, rdx
0x180011d18  jz      loc_180011F71
0x180011d1e  test    rcx, rcx
0x180011d21  jz      loc_180011F71
0x180011d27  mov     rax, cs:g_pfnResultLoggingCallback
0x180011d2e  mov     [rcx], r15w
0x180011d32  test    rax, rax
0x180011d35  jz      short loc_180011D58
0x180011d37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180011d3e  jz      short loc_180011D58
0x180011d40  mov     r8, rdx
0x180011d43  mov     rdx, rcx
0x180011d46  mov     rcx, rbx
0x180011d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d4e  cmp     [r14], r15w
0x180011d52  jnz     loc_180011F71
0x180011d58  mov     ecx, [rbx]
0x180011d5a  mov     bpl, 8
0x180011d5d  test    ecx, ecx
0x180011d5f  jz      short loc_180011DAA
0x180011d61  sub     ecx, 1
0x180011d64  jz      short loc_180011D92
0x180011d66  sub     ecx, 1
0x180011d69  jz      short loc_180011D82
0x180011d6b  cmp     ecx, 1
0x180011d6e  jz      short loc_180011D79
0x180011d70  lea     rdi, dword_180017D6C
0x180011d77  jmp     short loc_180011DB1
0x180011d79  lea     rdi, aFailfast; "FailFast"
0x180011d80  jmp     short loc_180011DB1
0x180011d82  lea     rax, aLoghr; "LogHr"
0x180011d89  lea     rdi, aLognt; "LogNt"
0x180011d90  jmp     short loc_180011DA0
0x180011d92  lea     rax, aReturnhr; "ReturnHr"
0x180011d99  lea     rdi, aReturnnt; "ReturnNt"
0x180011da0  test    [rbx+4], bpl
0x180011da4  cmovz   rdi, rax
0x180011da8  jmp     short loc_180011DB1
0x180011daa  lea     rdi, aException; "Exception"
0x180011db1  xor     edx, edx; Val
0x180011db3  lea     rcx, [rsp+278h+Buffer]; void *
0x180011db8  mov     r8d, 200h; Size
0x180011dbe  call    memset_0
0x180011dc3  test    [rbx+4], bpl
0x180011dc7  jz      short loc_180011DEC
0x180011dc9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180011dd0  mov     ebp, [rbx+0Ch]
0x180011dd3  test    rax, rax
0x180011dd6  jz      short loc_180011E1C
0x180011dd8  mov     r8d, 100h
0x180011dde  lea     rdx, [rsp+278h+Buffer]
0x180011de3  mov     ecx, ebp
0x180011de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dea  jmp     short loc_180011E1C
0x180011dec  mov     ebp, [rbx+8]
0x180011def  lea     rax, [rsp+278h+Buffer]
0x180011df4  mov     [rsp+278h+Arguments], r15; Arguments
0x180011df9  mov     r8d, ebp; dwMessageId
0x180011dfc  mov     [rsp+278h+nSize], 100h; nSize
0x180011e04  mov     r9d, 400h; dwLanguageId
0x180011e0a  xor     edx, edx; lpSource
0x180011e0c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180011e11  mov     ecx, 1200h; dwFlags
0x180011e16  call    cs:__imp_FormatMessageW
0x180011e1c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180011e20  lea     rsi, [r14+rsi*2]
0x180011e24  mov     rax, [rbx+88h]
0x180011e2b  mov     rdx, rsi; unsigned __int16 *
0x180011e2e  mov     rcx, [rbx+80h]
0x180011e35  test    r9, r9
0x180011e38  jz      short loc_180011E5C
0x180011e3a  mov     [rsp+278h+Arguments], rax
0x180011e3f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180011e46  mov     eax, [rbx+40h]
0x180011e49  mov     qword ptr [rsp+278h+nSize], rcx
0x180011e4e  mov     rcx, r14; this
0x180011e51  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011e55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011e5a  jmp     short loc_180011E73
0x180011e5c  mov     r9, rcx; unsigned __int16 *
0x180011e5f  mov     [rsp+278h+lpBuffer], rax
0x180011e64  mov     rcx, r14; this
0x180011e67  lea     r8, aHsP; "%hs!%p: "
0x180011e6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011e73  mov     r9, [rbx+90h]; unsigned __int16 *
0x180011e7a  mov     r14, rax
0x180011e7d  test    r9, r9
0x180011e80  jz      short loc_180011E97
0x180011e82  lea     r8, aCallerP; "(caller: %p) "
0x180011e89  mov     rdx, rsi; unsigned __int16 *
0x180011e8c  mov     rcx, rax; this
0x180011e8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011e94  mov     r14, rax
0x180011e97  call    cs:__imp_GetCurrentThreadId
0x180011e9d  lea     rcx, [rsp+278h+Buffer]
0x180011ea2  mov     r9, rdi; unsigned __int16 *
0x180011ea5  mov     [rsp+278h+var_240], rcx
0x180011eaa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180011eb1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180011eb5  mov     rdx, rsi; unsigned __int16 *
0x180011eb8  mov     [rsp+278h+nSize], eax
0x180011ebc  mov     rcx, r14; this
0x180011ebf  mov     eax, [rbx+44h]
0x180011ec2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011ec6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011ecb  cmp     [rbx+18h], r15
0x180011ecf  jnz     short loc_180011EE1
0x180011ed1  cmp     [rbx+48h], r15
0x180011ed5  jnz     short loc_180011EE1
0x180011ed7  cmp     [rbx+30h], r15
0x180011edb  jz      loc_180011F71
0x180011ee1  lea     r8, asc_180017BB0; "    "
0x180011ee8  mov     rdx, rsi; unsigned __int16 *
0x180011eeb  mov     rcx, rax; this
0x180011eee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011ef3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180011ef7  test    r9, r9
0x180011efa  jz      short loc_180011F0E
0x180011efc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180011f03  mov     rdx, rsi; unsigned __int16 *
0x180011f06  mov     rcx, rax; this
0x180011f09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011f0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180011f12  test    r9, r9
0x180011f15  jz      short loc_180011F29
0x180011f17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180011f1e  mov     rdx, rsi; unsigned __int16 *
0x180011f21  mov     rcx, rax; this
0x180011f24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011f29  mov     rcx, [rbx+28h]
0x180011f2d  mov     rdx, rsi; unsigned __int16 *
0x180011f30  mov     r9, [rbx+30h]; unsigned __int16 *
0x180011f34  test    rcx, rcx
0x180011f37  jz      short loc_180011F4F
0x180011f39  mov     [rsp+278h+lpBuffer], rcx
0x180011f3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180011f45  mov     rcx, rax; this
0x180011f48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011f4d  jmp     short loc_180011F71
0x180011f4f  mov     rcx, rax; this
0x180011f52  test    r9, r9
0x180011f55  jz      short loc_180011F65
0x180011f57  lea     r8, aHs; "[%hs]\n"
0x180011f5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011f63  jmp     short loc_180011F71
0x180011f65  lea     r8, asc_180017C28; "\n"
0x180011f6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011f71  xor     eax, eax
0x180011f73  mov     rcx, [rsp+278h+var_38]
0x180011f7b  xor     rcx, rsp; StackCookie
0x180011f7e  call    __security_check_cookie
0x180011f83  mov     rbx, [rsp+278h+arg_18]
0x180011f8b  add     rsp, 250h
0x180011f92  pop     r15
0x180011f94  pop     r14
0x180011f96  pop     rdi
0x180011f97  pop     rsi
0x180011f98  pop     rbp
0x180011f99  retn
```
