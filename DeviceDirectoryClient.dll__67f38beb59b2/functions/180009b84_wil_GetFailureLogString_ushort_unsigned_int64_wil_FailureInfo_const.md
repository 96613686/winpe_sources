# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009b84`
- end: `0x180009e3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180007f3c`
- `0x18000a9e4`
- `0x18000b050`
- `0x18000e960`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x180009b84`
- `0x18000ace4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009cb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009cb6`

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
          v7 = (const char *)&qword_18002F618;
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
0x180009b84  mov     [rsp+arg_18], rbx
0x180009b89  push    rbp
0x180009b8a  push    rsi
0x180009b8b  push    rdi
0x180009b8c  push    r14
0x180009b8e  push    r15
0x180009b90  sub     rsp, 250h
0x180009b97  mov     rax, cs:__security_cookie
0x180009b9e  xor     rax, rsp
0x180009ba1  mov     [rsp+278h+var_38], rax
0x180009ba9  mov     rbx, r8
0x180009bac  mov     rsi, rdx
0x180009baf  mov     r14, rcx
0x180009bb2  xor     r15d, r15d
0x180009bb5  test    rdx, rdx
0x180009bb8  jz      loc_180009E11
0x180009bbe  test    rcx, rcx
0x180009bc1  jz      loc_180009E11
0x180009bc7  mov     [rcx], r15w
0x180009bcb  mov     rax, cs:g_pfnResultLoggingCallback
0x180009bd2  test    rax, rax
0x180009bd5  jz      short loc_180009BF8
0x180009bd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009bde  jz      short loc_180009BF8
0x180009be0  mov     r8, rdx
0x180009be3  mov     rdx, rcx
0x180009be6  mov     rcx, rbx
0x180009be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bee  cmp     [r14], r15w
0x180009bf2  jnz     loc_180009E11
0x180009bf8  mov     ecx, [rbx]
0x180009bfa  mov     bpl, 8
0x180009bfd  test    ecx, ecx
0x180009bff  jz      short loc_180009C4A
0x180009c01  sub     ecx, 1
0x180009c04  jz      short loc_180009C32
0x180009c06  sub     ecx, 1
0x180009c09  jz      short loc_180009C22
0x180009c0b  cmp     ecx, 1
0x180009c0e  jz      short loc_180009C19
0x180009c10  lea     rdi, qword_18002F618
0x180009c17  jmp     short loc_180009C51
0x180009c19  lea     rdi, aFailfast; "FailFast"
0x180009c20  jmp     short loc_180009C51
0x180009c22  lea     rax, aLoghr; "LogHr"
0x180009c29  lea     rdi, aLognt; "LogNt"
0x180009c30  jmp     short loc_180009C40
0x180009c32  lea     rax, aReturnhr; "ReturnHr"
0x180009c39  lea     rdi, aReturnnt; "ReturnNt"
0x180009c40  test    [rbx+4], bpl
0x180009c44  cmovz   rdi, rax
0x180009c48  jmp     short loc_180009C51
0x180009c4a  lea     rdi, aException; "Exception"
0x180009c51  xor     edx, edx; Val
0x180009c53  mov     r8d, 200h; Size
0x180009c59  lea     rcx, [rsp+278h+Buffer]; void *
0x180009c5e  call    memset_0
0x180009c63  test    [rbx+4], bpl
0x180009c67  jz      short loc_180009C8C
0x180009c69  mov     ebp, [rbx+0Ch]
0x180009c6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009c73  test    rax, rax
0x180009c76  jz      short loc_180009CBC
0x180009c78  mov     r8d, 100h
0x180009c7e  lea     rdx, [rsp+278h+Buffer]
0x180009c83  mov     ecx, ebp
0x180009c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c8a  jmp     short loc_180009CBC
0x180009c8c  mov     ebp, [rbx+8]
0x180009c8f  mov     [rsp+278h+Arguments], r15; Arguments
0x180009c94  mov     [rsp+278h+nSize], 100h; nSize
0x180009c9c  lea     rax, [rsp+278h+Buffer]
0x180009ca1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009ca6  mov     r9d, 400h; dwLanguageId
0x180009cac  mov     r8d, ebp; dwMessageId
0x180009caf  xor     edx, edx; lpSource
0x180009cb1  mov     ecx, 1200h; dwFlags
0x180009cb6  call    cs:__imp_FormatMessageW
0x180009cbc  lea     rsi, [r14+rsi*2]
0x180009cc0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009cc4  mov     rax, [rbx+88h]
0x180009ccb  mov     rcx, [rbx+80h]
0x180009cd2  mov     rdx, rsi; unsigned __int16 *
0x180009cd5  test    r9, r9
0x180009cd8  jz      short loc_180009CFC
0x180009cda  mov     [rsp+278h+Arguments], rax
0x180009cdf  mov     qword ptr [rsp+278h+nSize], rcx
0x180009ce4  mov     eax, [rbx+40h]
0x180009ce7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009ceb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009cf2  mov     rcx, r14; this
0x180009cf5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cfa  jmp     short loc_180009D13
0x180009cfc  mov     [rsp+278h+lpBuffer], rax
0x180009d01  mov     r9, rcx; unsigned __int16 *
0x180009d04  lea     r8, aHsP; "%hs!%p: "
0x180009d0b  mov     rcx, r14; this
0x180009d0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d13  mov     r14, rax
0x180009d16  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009d1d  test    r9, r9
0x180009d20  jz      short loc_180009D37
0x180009d22  lea     r8, aCallerP; "(caller: %p) "
0x180009d29  mov     rdx, rsi; unsigned __int16 *
0x180009d2c  mov     rcx, rax; this
0x180009d2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d34  mov     r14, rax
0x180009d37  call    cs:__imp_GetCurrentThreadId
0x180009d3d  lea     rcx, [rsp+278h+Buffer]
0x180009d42  mov     [rsp+278h+var_240], rcx
0x180009d47  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009d4b  mov     [rsp+278h+nSize], eax
0x180009d4f  mov     eax, [rbx+44h]
0x180009d52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009d56  mov     r9, rdi; unsigned __int16 *
0x180009d59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009d60  mov     rdx, rsi; unsigned __int16 *
0x180009d63  mov     rcx, r14; this
0x180009d66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d6b  cmp     [rbx+18h], r15
0x180009d6f  jnz     short loc_180009D81
0x180009d71  cmp     [rbx+48h], r15
0x180009d75  jnz     short loc_180009D81
0x180009d77  cmp     [rbx+30h], r15
0x180009d7b  jz      loc_180009E11
0x180009d81  lea     r8, asc_18002E7C8; "    "
0x180009d88  mov     rdx, rsi; unsigned __int16 *
0x180009d8b  mov     rcx, rax; this
0x180009d8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d93  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009d97  test    r9, r9
0x180009d9a  jz      short loc_180009DAE
0x180009d9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009da3  mov     rdx, rsi; unsigned __int16 *
0x180009da6  mov     rcx, rax; this
0x180009da9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009dae  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009db2  test    r9, r9
0x180009db5  jz      short loc_180009DC9
0x180009db7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009dbe  mov     rdx, rsi; unsigned __int16 *
0x180009dc1  mov     rcx, rax; this
0x180009dc4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009dc9  mov     rcx, [rbx+28h]
0x180009dcd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009dd1  mov     rdx, rsi; unsigned __int16 *
0x180009dd4  test    rcx, rcx
0x180009dd7  jz      short loc_180009DEF
0x180009dd9  mov     [rsp+278h+lpBuffer], rcx
0x180009dde  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009de5  mov     rcx, rax; this
0x180009de8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009ded  jmp     short loc_180009E11
0x180009def  mov     rcx, rax; this
0x180009df2  test    r9, r9
0x180009df5  jz      short loc_180009E05
0x180009df7  lea     r8, aHs; "[%hs]\n"
0x180009dfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009e03  jmp     short loc_180009E11
0x180009e05  lea     r8, asc_18002E840; "\n"
0x180009e0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009e11  xor     eax, eax
0x180009e13  mov     rcx, [rsp+278h+var_38]
0x180009e1b  xor     rcx, rsp; StackCookie
0x180009e1e  call    __security_check_cookie
0x180009e23  mov     rbx, [rsp+278h+arg_18]
0x180009e2b  add     rsp, 250h
0x180009e32  pop     r15
0x180009e34  pop     r14
0x180009e36  pop     rdi
0x180009e37  pop     rsi
0x180009e38  pop     rbp
0x180009e39  retn
```
