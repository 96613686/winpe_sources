# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003df4`
- end: `0x1800040b7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003468`
- `0x1800036fc`
- `0x1800039bc`
- `0x18001112c`
- `0x180021d20`
- `0x180036a42`
- `0x180036b76`

## callees

- `0x180002140`
- `0x180002c48`
- `0x180003df4`
- `0x1800043bc`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fad`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003f26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003f26`

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
          v7 = (const char *)&qword_18003F440;
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
0x180003df4  mov     [rsp+arg_18], rbx
0x180003df9  push    rbp
0x180003dfa  push    rsi
0x180003dfb  push    rdi
0x180003dfc  push    r14
0x180003dfe  push    r15
0x180003e00  sub     rsp, 250h
0x180003e07  mov     rax, cs:__security_cookie
0x180003e0e  xor     rax, rsp
0x180003e11  mov     [rsp+278h+var_38], rax
0x180003e19  mov     rbx, r8
0x180003e1c  mov     rsi, rdx
0x180003e1f  mov     r14, rcx
0x180003e22  xor     r15d, r15d
0x180003e25  test    rdx, rdx
0x180003e28  jz      loc_18000408D
0x180003e2e  test    rcx, rcx
0x180003e31  jz      loc_18000408D
0x180003e37  mov     [rcx], r15w
0x180003e3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003e42  test    rax, rax
0x180003e45  jz      short loc_180003E68
0x180003e47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003e4e  jz      short loc_180003E68
0x180003e50  mov     r8, rdx
0x180003e53  mov     rdx, rcx
0x180003e56  mov     rcx, rbx
0x180003e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e5e  cmp     [r14], r15w
0x180003e62  jnz     loc_18000408D
0x180003e68  mov     ecx, [rbx]
0x180003e6a  mov     bpl, 8
0x180003e6d  test    ecx, ecx
0x180003e6f  jz      short loc_180003EBA
0x180003e71  sub     ecx, 1
0x180003e74  jz      short loc_180003EA2
0x180003e76  sub     ecx, 1
0x180003e79  jz      short loc_180003E92
0x180003e7b  cmp     ecx, 1
0x180003e7e  jz      short loc_180003E89
0x180003e80  lea     rdi, qword_18003F440
0x180003e87  jmp     short loc_180003EC1
0x180003e89  lea     rdi, aFailfast; "FailFast"
0x180003e90  jmp     short loc_180003EC1
0x180003e92  lea     rax, aLoghr; "LogHr"
0x180003e99  lea     rdi, aLognt; "LogNt"
0x180003ea0  jmp     short loc_180003EB0
0x180003ea2  lea     rax, aReturnhr; "ReturnHr"
0x180003ea9  lea     rdi, aReturnnt; "ReturnNt"
0x180003eb0  test    [rbx+4], bpl
0x180003eb4  cmovz   rdi, rax
0x180003eb8  jmp     short loc_180003EC1
0x180003eba  lea     rdi, aException; "Exception"
0x180003ec1  xor     edx, edx; Val
0x180003ec3  mov     r8d, 200h; Size
0x180003ec9  lea     rcx, [rsp+278h+Buffer]; void *
0x180003ece  call    memset_0
0x180003ed3  test    [rbx+4], bpl
0x180003ed7  jz      short loc_180003EFC
0x180003ed9  mov     ebp, [rbx+0Ch]
0x180003edc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003ee3  test    rax, rax
0x180003ee6  jz      short loc_180003F32
0x180003ee8  mov     r8d, 100h
0x180003eee  lea     rdx, [rsp+278h+Buffer]
0x180003ef3  mov     ecx, ebp
0x180003ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003efa  jmp     short loc_180003F32
0x180003efc  mov     ebp, [rbx+8]
0x180003eff  mov     [rsp+278h+Arguments], r15; Arguments
0x180003f04  mov     [rsp+278h+nSize], 100h; nSize
0x180003f0c  lea     rax, [rsp+278h+Buffer]
0x180003f11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003f16  mov     r9d, 400h; dwLanguageId
0x180003f1c  mov     r8d, ebp; dwMessageId
0x180003f1f  xor     edx, edx; lpSource
0x180003f21  mov     ecx, 1200h; dwFlags
0x180003f26  call    cs:__imp_FormatMessageW
0x180003f2d  nop     dword ptr [rax+rax+00h]
0x180003f32  lea     rsi, [r14+rsi*2]
0x180003f36  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003f3a  mov     rax, [rbx+88h]
0x180003f41  mov     rcx, [rbx+80h]
0x180003f48  mov     rdx, rsi; unsigned __int16 *
0x180003f4b  test    r9, r9
0x180003f4e  jz      short loc_180003F72
0x180003f50  mov     [rsp+278h+Arguments], rax
0x180003f55  mov     qword ptr [rsp+278h+nSize], rcx
0x180003f5a  mov     eax, [rbx+40h]
0x180003f5d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003f61  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003f68  mov     rcx, r14; this
0x180003f6b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f70  jmp     short loc_180003F89
0x180003f72  mov     [rsp+278h+lpBuffer], rax
0x180003f77  mov     r9, rcx; unsigned __int16 *
0x180003f7a  lea     r8, aHsP; "%hs!%p: "
0x180003f81  mov     rcx, r14; this
0x180003f84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003f89  mov     r14, rax
0x180003f8c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003f93  test    r9, r9
0x180003f96  jz      short loc_180003FAD
0x180003f98  lea     r8, aCallerP; "(caller: %p) "
0x180003f9f  mov     rdx, rsi; unsigned __int16 *
0x180003fa2  mov     rcx, rax; this
0x180003fa5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003faa  mov     r14, rax
0x180003fad  call    cs:__imp_GetCurrentThreadId
0x180003fb4  nop     dword ptr [rax+rax+00h]
0x180003fb9  lea     rcx, [rsp+278h+Buffer]
0x180003fbe  mov     [rsp+278h+var_240], rcx
0x180003fc3  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003fc7  mov     [rsp+278h+nSize], eax
0x180003fcb  mov     eax, [rbx+44h]
0x180003fce  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003fd2  mov     r9, rdi; unsigned __int16 *
0x180003fd5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003fdc  mov     rdx, rsi; unsigned __int16 *
0x180003fdf  mov     rcx, r14; this
0x180003fe2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003fe7  cmp     [rbx+18h], r15
0x180003feb  jnz     short loc_180003FFD
0x180003fed  cmp     [rbx+48h], r15
0x180003ff1  jnz     short loc_180003FFD
0x180003ff3  cmp     [rbx+30h], r15
0x180003ff7  jz      loc_18000408D
0x180003ffd  lea     r8, asc_18003F530; "    "
0x180004004  mov     rdx, rsi; unsigned __int16 *
0x180004007  mov     rcx, rax; this
0x18000400a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000400f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004013  test    r9, r9
0x180004016  jz      short loc_18000402A
0x180004018  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000401f  mov     rdx, rsi; unsigned __int16 *
0x180004022  mov     rcx, rax; this
0x180004025  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000402a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000402e  test    r9, r9
0x180004031  jz      short loc_180004045
0x180004033  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000403a  mov     rdx, rsi; unsigned __int16 *
0x18000403d  mov     rcx, rax; this
0x180004040  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004045  mov     rcx, [rbx+28h]
0x180004049  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000404d  mov     rdx, rsi; unsigned __int16 *
0x180004050  test    rcx, rcx
0x180004053  jz      short loc_18000406B
0x180004055  mov     [rsp+278h+lpBuffer], rcx
0x18000405a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004061  mov     rcx, rax; this
0x180004064  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004069  jmp     short loc_18000408D
0x18000406b  mov     rcx, rax; this
0x18000406e  test    r9, r9
0x180004071  jz      short loc_180004081
0x180004073  lea     r8, aHs; "[%hs]\n"
0x18000407a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000407f  jmp     short loc_18000408D
0x180004081  lea     r8, asc_18003F5A8; "\n"
0x180004088  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000408d  xor     eax, eax
0x18000408f  mov     rcx, [rsp+278h+var_38]
0x180004097  xor     rcx, rsp; StackCookie
0x18000409a  call    __security_check_cookie
0x18000409f  mov     rbx, [rsp+278h+arg_18]
0x1800040a7  add     rsp, 250h
0x1800040ae  pop     r15
0x1800040b0  pop     r14
0x1800040b2  pop     rdi
0x1800040b3  pop     rsi
0x1800040b4  pop     rbp
0x1800040b5  retn
```
