# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006c14`
- end: `0x180006eca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000516c`
- `0x1800078dc`
- `0x180007fbc`
- `0x18000abd0`

## callees

- `0x180003ab0`
- `0x1800047f0`
- `0x180006c14`
- `0x180007bdc`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dc7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006d46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006d46`

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
          v7 = qword_180033B60;
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
0x180006c14  mov     [rsp+arg_18], rbx
0x180006c19  push    rbp
0x180006c1a  push    rsi
0x180006c1b  push    rdi
0x180006c1c  push    r14
0x180006c1e  push    r15
0x180006c20  sub     rsp, 250h
0x180006c27  mov     rax, cs:__security_cookie
0x180006c2e  xor     rax, rsp
0x180006c31  mov     [rsp+278h+var_38], rax
0x180006c39  mov     rbx, r8
0x180006c3c  mov     rsi, rdx
0x180006c3f  mov     r14, rcx
0x180006c42  xor     r15d, r15d
0x180006c45  test    rdx, rdx
0x180006c48  jz      loc_180006EA1
0x180006c4e  test    rcx, rcx
0x180006c51  jz      loc_180006EA1
0x180006c57  mov     [rcx], r15w
0x180006c5b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006c62  test    rax, rax
0x180006c65  jz      short loc_180006C88
0x180006c67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006c6e  jz      short loc_180006C88
0x180006c70  mov     r8, rdx
0x180006c73  mov     rdx, rcx
0x180006c76  mov     rcx, rbx
0x180006c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7e  cmp     [r14], r15w
0x180006c82  jnz     loc_180006EA1
0x180006c88  mov     ecx, [rbx]
0x180006c8a  mov     bpl, 8
0x180006c8d  test    ecx, ecx
0x180006c8f  jz      short loc_180006CDA
0x180006c91  sub     ecx, 1
0x180006c94  jz      short loc_180006CC2
0x180006c96  sub     ecx, 1
0x180006c99  jz      short loc_180006CB2
0x180006c9b  cmp     ecx, 1
0x180006c9e  jz      short loc_180006CA9
0x180006ca0  lea     rdi, qword_180033B60
0x180006ca7  jmp     short loc_180006CE1
0x180006ca9  lea     rdi, aFailfast; "FailFast"
0x180006cb0  jmp     short loc_180006CE1
0x180006cb2  lea     rax, aLoghr; "LogHr"
0x180006cb9  lea     rdi, aLognt; "LogNt"
0x180006cc0  jmp     short loc_180006CD0
0x180006cc2  lea     rax, aReturnhr; "ReturnHr"
0x180006cc9  lea     rdi, aReturnnt; "ReturnNt"
0x180006cd0  test    [rbx+4], bpl
0x180006cd4  cmovz   rdi, rax
0x180006cd8  jmp     short loc_180006CE1
0x180006cda  lea     rdi, aException; "Exception"
0x180006ce1  xor     edx, edx; Val
0x180006ce3  mov     r8d, 200h; Size
0x180006ce9  lea     rcx, [rsp+278h+Buffer]; void *
0x180006cee  call    memset_0
0x180006cf3  test    [rbx+4], bpl
0x180006cf7  jz      short loc_180006D1C
0x180006cf9  mov     ebp, [rbx+0Ch]
0x180006cfc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006d03  test    rax, rax
0x180006d06  jz      short loc_180006D4C
0x180006d08  mov     r8d, 100h
0x180006d0e  lea     rdx, [rsp+278h+Buffer]
0x180006d13  mov     ecx, ebp
0x180006d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1a  jmp     short loc_180006D4C
0x180006d1c  mov     ebp, [rbx+8]
0x180006d1f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006d24  mov     [rsp+278h+nSize], 100h; nSize
0x180006d2c  lea     rax, [rsp+278h+Buffer]
0x180006d31  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006d36  mov     r9d, 400h; dwLanguageId
0x180006d3c  mov     r8d, ebp; dwMessageId
0x180006d3f  xor     edx, edx; lpSource
0x180006d41  mov     ecx, 1200h; dwFlags
0x180006d46  call    cs:__imp_FormatMessageW
0x180006d4c  lea     rsi, [r14+rsi*2]
0x180006d50  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006d54  mov     rax, [rbx+88h]
0x180006d5b  mov     rcx, [rbx+80h]
0x180006d62  mov     rdx, rsi; unsigned __int16 *
0x180006d65  test    r9, r9
0x180006d68  jz      short loc_180006D8C
0x180006d6a  mov     [rsp+278h+Arguments], rax
0x180006d6f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006d74  mov     eax, [rbx+40h]
0x180006d77  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006d7b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006d82  mov     rcx, r14; this
0x180006d85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d8a  jmp     short loc_180006DA3
0x180006d8c  mov     [rsp+278h+lpBuffer], rax
0x180006d91  mov     r9, rcx; unsigned __int16 *
0x180006d94  lea     r8, aHsP; "%hs!%p: "
0x180006d9b  mov     rcx, r14; this
0x180006d9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006da3  mov     r14, rax
0x180006da6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006dad  test    r9, r9
0x180006db0  jz      short loc_180006DC7
0x180006db2  lea     r8, aCallerP; "(caller: %p) "
0x180006db9  mov     rdx, rsi; unsigned __int16 *
0x180006dbc  mov     rcx, rax; this
0x180006dbf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006dc4  mov     r14, rax
0x180006dc7  call    cs:__imp_GetCurrentThreadId
0x180006dcd  lea     rcx, [rsp+278h+Buffer]
0x180006dd2  mov     [rsp+278h+var_240], rcx
0x180006dd7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006ddb  mov     [rsp+278h+nSize], eax
0x180006ddf  mov     eax, [rbx+44h]
0x180006de2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006de6  mov     r9, rdi; unsigned __int16 *
0x180006de9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006df0  mov     rdx, rsi; unsigned __int16 *
0x180006df3  mov     rcx, r14; this
0x180006df6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006dfb  cmp     [rbx+18h], r15
0x180006dff  jnz     short loc_180006E11
0x180006e01  cmp     [rbx+48h], r15
0x180006e05  jnz     short loc_180006E11
0x180006e07  cmp     [rbx+30h], r15
0x180006e0b  jz      loc_180006EA1
0x180006e11  lea     r8, asc_180033C68; "    "
0x180006e18  mov     rdx, rsi; unsigned __int16 *
0x180006e1b  mov     rcx, rax; this
0x180006e1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e23  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006e27  test    r9, r9
0x180006e2a  jz      short loc_180006E3E
0x180006e2c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006e33  mov     rdx, rsi; unsigned __int16 *
0x180006e36  mov     rcx, rax; this
0x180006e39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e3e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006e42  test    r9, r9
0x180006e45  jz      short loc_180006E59
0x180006e47  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006e4e  mov     rdx, rsi; unsigned __int16 *
0x180006e51  mov     rcx, rax; this
0x180006e54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e59  mov     rcx, [rbx+28h]
0x180006e5d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006e61  mov     rdx, rsi; unsigned __int16 *
0x180006e64  test    rcx, rcx
0x180006e67  jz      short loc_180006E7F
0x180006e69  mov     [rsp+278h+lpBuffer], rcx
0x180006e6e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006e75  mov     rcx, rax; this
0x180006e78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e7d  jmp     short loc_180006EA1
0x180006e7f  mov     rcx, rax; this
0x180006e82  test    r9, r9
0x180006e85  jz      short loc_180006E95
0x180006e87  lea     r8, aHs; "[%hs]\n"
0x180006e8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e93  jmp     short loc_180006EA1
0x180006e95  lea     r8, asc_180033CE0; "\n"
0x180006e9c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006ea1  xor     eax, eax
0x180006ea3  mov     rcx, [rsp+278h+var_38]
0x180006eab  xor     rcx, rsp; StackCookie
0x180006eae  call    __security_check_cookie
0x180006eb3  mov     rbx, [rsp+278h+arg_18]
0x180006ebb  add     rsp, 250h
0x180006ec2  pop     r15
0x180006ec4  pop     r14
0x180006ec6  pop     rdi
0x180006ec7  pop     rsi
0x180006ec8  pop     rbp
0x180006ec9  retn
```
