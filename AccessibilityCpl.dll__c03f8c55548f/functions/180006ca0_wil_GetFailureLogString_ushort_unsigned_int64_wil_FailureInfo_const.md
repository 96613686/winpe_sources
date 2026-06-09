# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006ca0`
- end: `0x180006f56`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180003dd0`
- `0x180012bbc`

## callees

- `0x180006ca0`
- `0x180012ebc`
- `0x18002d1ee`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e53`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006dd2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006dd2`

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
          v8 = MultiByteStr;
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
0x180006ca0  mov     [rsp+arg_18], rbx
0x180006ca5  push    rbp
0x180006ca6  push    rsi
0x180006ca7  push    rdi
0x180006ca8  push    r14
0x180006caa  push    r15
0x180006cac  sub     rsp, 250h
0x180006cb3  mov     rax, cs:__security_cookie
0x180006cba  xor     rax, rsp
0x180006cbd  mov     [rsp+278h+var_38], rax
0x180006cc5  xor     r15d, r15d
0x180006cc8  mov     rbx, r8
0x180006ccb  mov     rsi, rdx
0x180006cce  mov     r14, rcx
0x180006cd1  test    rdx, rdx
0x180006cd4  jz      loc_180006F2D
0x180006cda  test    rcx, rcx
0x180006cdd  jz      loc_180006F2D
0x180006ce3  mov     rax, cs:g_pfnResultLoggingCallback
0x180006cea  mov     [rcx], r15w
0x180006cee  test    rax, rax
0x180006cf1  jz      short loc_180006D14
0x180006cf3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006cfa  jz      short loc_180006D14
0x180006cfc  mov     r8, rdx
0x180006cff  mov     rdx, rcx
0x180006d02  mov     rcx, rbx
0x180006d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d0a  cmp     [r14], r15w
0x180006d0e  jnz     loc_180006F2D
0x180006d14  mov     ecx, [rbx]
0x180006d16  mov     bpl, 8
0x180006d19  test    ecx, ecx
0x180006d1b  jz      short loc_180006D66
0x180006d1d  sub     ecx, 1
0x180006d20  jz      short loc_180006D4E
0x180006d22  sub     ecx, 1
0x180006d25  jz      short loc_180006D3E
0x180006d27  cmp     ecx, 1
0x180006d2a  jz      short loc_180006D35
0x180006d2c  lea     rdi, MultiByteStr
0x180006d33  jmp     short loc_180006D6D
0x180006d35  lea     rdi, aFailfast; "FailFast"
0x180006d3c  jmp     short loc_180006D6D
0x180006d3e  lea     rax, aLoghr; "LogHr"
0x180006d45  lea     rdi, aLognt; "LogNt"
0x180006d4c  jmp     short loc_180006D5C
0x180006d4e  lea     rax, aReturnhr; "ReturnHr"
0x180006d55  lea     rdi, aReturnnt; "ReturnNt"
0x180006d5c  test    [rbx+4], bpl
0x180006d60  cmovz   rdi, rax
0x180006d64  jmp     short loc_180006D6D
0x180006d66  lea     rdi, aException; "Exception"
0x180006d6d  xor     edx, edx; Val
0x180006d6f  lea     rcx, [rsp+278h+Buffer]; void *
0x180006d74  mov     r8d, 200h; Size
0x180006d7a  call    memset_0
0x180006d7f  test    [rbx+4], bpl
0x180006d83  jz      short loc_180006DA8
0x180006d85  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006d8c  mov     ebp, [rbx+0Ch]
0x180006d8f  test    rax, rax
0x180006d92  jz      short loc_180006DD8
0x180006d94  mov     r8d, 100h
0x180006d9a  lea     rdx, [rsp+278h+Buffer]
0x180006d9f  mov     ecx, ebp
0x180006da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da6  jmp     short loc_180006DD8
0x180006da8  mov     ebp, [rbx+8]
0x180006dab  lea     rax, [rsp+278h+Buffer]
0x180006db0  mov     [rsp+278h+Arguments], r15; Arguments
0x180006db5  mov     r8d, ebp; dwMessageId
0x180006db8  mov     [rsp+278h+nSize], 100h; nSize
0x180006dc0  mov     r9d, 400h; dwLanguageId
0x180006dc6  xor     edx, edx; lpSource
0x180006dc8  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006dcd  mov     ecx, 1200h; dwFlags
0x180006dd2  call    cs:__imp_FormatMessageW
0x180006dd8  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006ddc  lea     rsi, [r14+rsi*2]
0x180006de0  mov     rax, [rbx+88h]
0x180006de7  mov     rdx, rsi; unsigned __int16 *
0x180006dea  mov     rcx, [rbx+80h]
0x180006df1  test    r9, r9
0x180006df4  jz      short loc_180006E18
0x180006df6  mov     [rsp+278h+Arguments], rax
0x180006dfb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006e02  mov     eax, [rbx+40h]
0x180006e05  mov     qword ptr [rsp+278h+nSize], rcx
0x180006e0a  mov     rcx, r14; this
0x180006e0d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006e11  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e16  jmp     short loc_180006E2F
0x180006e18  mov     r9, rcx; unsigned __int16 *
0x180006e1b  mov     [rsp+278h+lpBuffer], rax
0x180006e20  mov     rcx, r14; this
0x180006e23  lea     r8, aHsP; "%hs!%p: "
0x180006e2a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e2f  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006e36  mov     r14, rax
0x180006e39  test    r9, r9
0x180006e3c  jz      short loc_180006E53
0x180006e3e  lea     r8, aCallerP; "(caller: %p) "
0x180006e45  mov     rdx, rsi; unsigned __int16 *
0x180006e48  mov     rcx, rax; this
0x180006e4b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e50  mov     r14, rax
0x180006e53  call    cs:__imp_GetCurrentThreadId
0x180006e59  lea     rcx, [rsp+278h+Buffer]
0x180006e5e  mov     r9, rdi; unsigned __int16 *
0x180006e61  mov     [rsp+278h+var_240], rcx
0x180006e66  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006e6d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006e71  mov     rdx, rsi; unsigned __int16 *
0x180006e74  mov     [rsp+278h+nSize], eax
0x180006e78  mov     rcx, r14; this
0x180006e7b  mov     eax, [rbx+44h]
0x180006e7e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006e82  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e87  cmp     [rbx+18h], r15
0x180006e8b  jnz     short loc_180006E9D
0x180006e8d  cmp     [rbx+48h], r15
0x180006e91  jnz     short loc_180006E9D
0x180006e93  cmp     [rbx+30h], r15
0x180006e97  jz      loc_180006F2D
0x180006e9d  lea     r8, asc_180031E28; "    "
0x180006ea4  mov     rdx, rsi; unsigned __int16 *
0x180006ea7  mov     rcx, rax; this
0x180006eaa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006eaf  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006eb3  test    r9, r9
0x180006eb6  jz      short loc_180006ECA
0x180006eb8  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006ebf  mov     rdx, rsi; unsigned __int16 *
0x180006ec2  mov     rcx, rax; this
0x180006ec5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006eca  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006ece  test    r9, r9
0x180006ed1  jz      short loc_180006EE5
0x180006ed3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006eda  mov     rdx, rsi; unsigned __int16 *
0x180006edd  mov     rcx, rax; this
0x180006ee0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006ee5  mov     rcx, [rbx+28h]
0x180006ee9  mov     rdx, rsi; unsigned __int16 *
0x180006eec  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006ef0  test    rcx, rcx
0x180006ef3  jz      short loc_180006F0B
0x180006ef5  mov     [rsp+278h+lpBuffer], rcx
0x180006efa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006f01  mov     rcx, rax; this
0x180006f04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f09  jmp     short loc_180006F2D
0x180006f0b  mov     rcx, rax; this
0x180006f0e  test    r9, r9
0x180006f11  jz      short loc_180006F21
0x180006f13  lea     r8, aHs; "[%hs]\n"
0x180006f1a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f1f  jmp     short loc_180006F2D
0x180006f21  lea     r8, asc_180031EA0; "\n"
0x180006f28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006f2d  xor     eax, eax
0x180006f2f  mov     rcx, [rsp+278h+var_38]
0x180006f37  xor     rcx, rsp; StackCookie
0x180006f3a  call    __security_check_cookie
0x180006f3f  mov     rbx, [rsp+278h+arg_18]
0x180006f47  add     rsp, 250h
0x180006f4e  pop     r15
0x180006f50  pop     r14
0x180006f52  pop     rdi
0x180006f53  pop     rsi
0x180006f54  pop     rbp
0x180006f55  retn
```
