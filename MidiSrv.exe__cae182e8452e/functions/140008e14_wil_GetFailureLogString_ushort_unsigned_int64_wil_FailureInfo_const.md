# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140008e14`
- end: `0x1400090ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x140006a30`
- `0x140006cb0`
- `0x140006f5c`
- `0x14000cc50`
- `0x14002194c`
- `0x14005654c`
- `0x140056680`

## callees

- `0x1400054c0`
- `0x1400060f8`
- `0x140008e14`
- `0x140009908`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008fc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008fc7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140008f46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140008f46`

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
          v7 = (const char *)&Src;
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
0x140008e14  mov     [rsp+arg_18], rbx
0x140008e19  push    rbp
0x140008e1a  push    rsi
0x140008e1b  push    rdi
0x140008e1c  push    r14
0x140008e1e  push    r15
0x140008e20  sub     rsp, 250h
0x140008e27  mov     rax, cs:__security_cookie
0x140008e2e  xor     rax, rsp
0x140008e31  mov     [rsp+278h+var_38], rax
0x140008e39  mov     rbx, r8
0x140008e3c  mov     rsi, rdx
0x140008e3f  mov     r14, rcx
0x140008e42  xor     r15d, r15d
0x140008e45  test    rdx, rdx
0x140008e48  jz      loc_1400090A1
0x140008e4e  test    rcx, rcx
0x140008e51  jz      loc_1400090A1
0x140008e57  mov     [rcx], r15w
0x140008e5b  mov     rax, cs:g_pfnResultLoggingCallback
0x140008e62  test    rax, rax
0x140008e65  jz      short loc_140008E88
0x140008e67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140008e6e  jz      short loc_140008E88
0x140008e70  mov     r8, rdx
0x140008e73  mov     rdx, rcx
0x140008e76  mov     rcx, rbx
0x140008e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e7e  cmp     [r14], r15w
0x140008e82  jnz     loc_1400090A1
0x140008e88  mov     ecx, [rbx]
0x140008e8a  mov     bpl, 8
0x140008e8d  test    ecx, ecx
0x140008e8f  jz      short loc_140008EDA
0x140008e91  sub     ecx, 1
0x140008e94  jz      short loc_140008EC2
0x140008e96  sub     ecx, 1
0x140008e99  jz      short loc_140008EB2
0x140008e9b  cmp     ecx, 1
0x140008e9e  jz      short loc_140008EA9
0x140008ea0  lea     rdi, Src
0x140008ea7  jmp     short loc_140008EE1
0x140008ea9  lea     rdi, aFailfast; "FailFast"
0x140008eb0  jmp     short loc_140008EE1
0x140008eb2  lea     rax, aLoghr; "LogHr"
0x140008eb9  lea     rdi, aLognt; "LogNt"
0x140008ec0  jmp     short loc_140008ED0
0x140008ec2  lea     rax, aReturnhr; "ReturnHr"
0x140008ec9  lea     rdi, aReturnnt; "ReturnNt"
0x140008ed0  test    [rbx+4], bpl
0x140008ed4  cmovz   rdi, rax
0x140008ed8  jmp     short loc_140008EE1
0x140008eda  lea     rdi, aException; "Exception"
0x140008ee1  xor     edx, edx; Val
0x140008ee3  mov     r8d, 200h; Size
0x140008ee9  lea     rcx, [rsp+278h+Buffer]; void *
0x140008eee  call    memset_0
0x140008ef3  test    [rbx+4], bpl
0x140008ef7  jz      short loc_140008F1C
0x140008ef9  mov     ebp, [rbx+0Ch]
0x140008efc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140008f03  test    rax, rax
0x140008f06  jz      short loc_140008F4C
0x140008f08  mov     r8d, 100h
0x140008f0e  lea     rdx, [rsp+278h+Buffer]
0x140008f13  mov     ecx, ebp
0x140008f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f1a  jmp     short loc_140008F4C
0x140008f1c  mov     ebp, [rbx+8]
0x140008f1f  mov     [rsp+278h+Arguments], r15; Arguments
0x140008f24  mov     [rsp+278h+nSize], 100h; nSize
0x140008f2c  lea     rax, [rsp+278h+Buffer]
0x140008f31  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140008f36  mov     r9d, 400h; dwLanguageId
0x140008f3c  mov     r8d, ebp; dwMessageId
0x140008f3f  xor     edx, edx; lpSource
0x140008f41  mov     ecx, 1200h; dwFlags
0x140008f46  call    cs:__imp_FormatMessageW
0x140008f4c  lea     rsi, [r14+rsi*2]
0x140008f50  mov     r9, [rbx+38h]; unsigned __int16 *
0x140008f54  mov     rax, [rbx+88h]
0x140008f5b  mov     rcx, [rbx+80h]
0x140008f62  mov     rdx, rsi; unsigned __int16 *
0x140008f65  test    r9, r9
0x140008f68  jz      short loc_140008F8C
0x140008f6a  mov     [rsp+278h+Arguments], rax
0x140008f6f  mov     qword ptr [rsp+278h+nSize], rcx
0x140008f74  mov     eax, [rbx+40h]
0x140008f77  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140008f7b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140008f82  mov     rcx, r14; this
0x140008f85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008f8a  jmp     short loc_140008FA3
0x140008f8c  mov     [rsp+278h+lpBuffer], rax
0x140008f91  mov     r9, rcx; unsigned __int16 *
0x140008f94  lea     r8, aHsP; "%hs!%p: "
0x140008f9b  mov     rcx, r14; this
0x140008f9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008fa3  mov     r14, rax
0x140008fa6  mov     r9, [rbx+90h]; unsigned __int16 *
0x140008fad  test    r9, r9
0x140008fb0  jz      short loc_140008FC7
0x140008fb2  lea     r8, aCallerP; "(caller: %p) "
0x140008fb9  mov     rdx, rsi; unsigned __int16 *
0x140008fbc  mov     rcx, rax; this
0x140008fbf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008fc4  mov     r14, rax
0x140008fc7  call    cs:__imp_GetCurrentThreadId
0x140008fcd  lea     rcx, [rsp+278h+Buffer]
0x140008fd2  mov     [rsp+278h+var_240], rcx
0x140008fd7  mov     dword ptr [rsp+278h+Arguments], ebp
0x140008fdb  mov     [rsp+278h+nSize], eax
0x140008fdf  mov     eax, [rbx+44h]
0x140008fe2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140008fe6  mov     r9, rdi; unsigned __int16 *
0x140008fe9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140008ff0  mov     rdx, rsi; unsigned __int16 *
0x140008ff3  mov     rcx, r14; this
0x140008ff6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140008ffb  cmp     [rbx+18h], r15
0x140008fff  jnz     short loc_140009011
0x140009001  cmp     [rbx+48h], r15
0x140009005  jnz     short loc_140009011
0x140009007  cmp     [rbx+30h], r15
0x14000900b  jz      loc_1400090A1
0x140009011  lea     r8, asc_14007AB30; "    "
0x140009018  mov     rdx, rsi; unsigned __int16 *
0x14000901b  mov     rcx, rax; this
0x14000901e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009023  mov     r9, [rbx+18h]; unsigned __int16 *
0x140009027  test    r9, r9
0x14000902a  jz      short loc_14000903E
0x14000902c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140009033  mov     rdx, rsi; unsigned __int16 *
0x140009036  mov     rcx, rax; this
0x140009039  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000903e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140009042  test    r9, r9
0x140009045  jz      short loc_140009059
0x140009047  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000904e  mov     rdx, rsi; unsigned __int16 *
0x140009051  mov     rcx, rax; this
0x140009054  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009059  mov     rcx, [rbx+28h]
0x14000905d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140009061  mov     rdx, rsi; unsigned __int16 *
0x140009064  test    rcx, rcx
0x140009067  jz      short loc_14000907F
0x140009069  mov     [rsp+278h+lpBuffer], rcx
0x14000906e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140009075  mov     rcx, rax; this
0x140009078  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000907d  jmp     short loc_1400090A1
0x14000907f  mov     rcx, rax; this
0x140009082  test    r9, r9
0x140009085  jz      short loc_140009095
0x140009087  lea     r8, aHs; "[%hs]\n"
0x14000908e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009093  jmp     short loc_1400090A1
0x140009095  lea     r8, asc_14007ABA8; "\n"
0x14000909c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400090a1  xor     eax, eax
0x1400090a3  mov     rcx, [rsp+278h+var_38]
0x1400090ab  xor     rcx, rsp; StackCookie
0x1400090ae  call    __security_check_cookie
0x1400090b3  mov     rbx, [rsp+278h+arg_18]
0x1400090bb  add     rsp, 250h
0x1400090c2  pop     r15
0x1400090c4  pop     r14
0x1400090c6  pop     rdi
0x1400090c7  pop     rsi
0x1400090c8  pop     rbp
0x1400090c9  retn
```
