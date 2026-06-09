# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140002de4`
- end: `0x14000309a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140001d70`
- `0x140001fe0`
- `0x140003740`

## callees

- `0x14000187f`
- `0x140002de4`
- `0x140003a40`
- `0x140004ba0`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002f97`
- `KERNEL32!GetCurrentThreadId` at `0x140002f97`
- `KERNEL32!FormatMessageW` at `0x140002f16`
- `KERNEL32!FormatMessageW` at `0x140002f16`

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
          v8 = (const char *)&byte_140006560;
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
0x140002de4  mov     [rsp+arg_18], rbx
0x140002de9  push    rbp
0x140002dea  push    rsi
0x140002deb  push    rdi
0x140002dec  push    r14
0x140002dee  push    r15
0x140002df0  sub     rsp, 250h
0x140002df7  mov     rax, cs:__security_cookie
0x140002dfe  xor     rax, rsp
0x140002e01  mov     [rsp+278h+var_38], rax
0x140002e09  xor     r15d, r15d
0x140002e0c  mov     rbx, r8
0x140002e0f  mov     rsi, rdx
0x140002e12  mov     r14, rcx
0x140002e15  test    rdx, rdx
0x140002e18  jz      loc_140003071
0x140002e1e  test    rcx, rcx
0x140002e21  jz      loc_140003071
0x140002e27  mov     rax, cs:g_pfnResultLoggingCallback
0x140002e2e  mov     [rcx], r15w
0x140002e32  test    rax, rax
0x140002e35  jz      short loc_140002E58
0x140002e37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002e3e  jz      short loc_140002E58
0x140002e40  mov     r8, rdx
0x140002e43  mov     rdx, rcx
0x140002e46  mov     rcx, rbx
0x140002e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e4e  cmp     [r14], r15w
0x140002e52  jnz     loc_140003071
0x140002e58  mov     ecx, [rbx]
0x140002e5a  mov     bpl, 8
0x140002e5d  test    ecx, ecx
0x140002e5f  jz      short loc_140002EAA
0x140002e61  sub     ecx, 1
0x140002e64  jz      short loc_140002E92
0x140002e66  sub     ecx, 1
0x140002e69  jz      short loc_140002E82
0x140002e6b  cmp     ecx, 1
0x140002e6e  jz      short loc_140002E79
0x140002e70  lea     rdi, byte_140006560
0x140002e77  jmp     short loc_140002EB1
0x140002e79  lea     rdi, aFailfast; "FailFast"
0x140002e80  jmp     short loc_140002EB1
0x140002e82  lea     rax, aLoghr; "LogHr"
0x140002e89  lea     rdi, aLognt; "LogNt"
0x140002e90  jmp     short loc_140002EA0
0x140002e92  lea     rax, aReturnhr; "ReturnHr"
0x140002e99  lea     rdi, aReturnnt; "ReturnNt"
0x140002ea0  test    [rbx+4], bpl
0x140002ea4  cmovz   rdi, rax
0x140002ea8  jmp     short loc_140002EB1
0x140002eaa  lea     rdi, aException; "Exception"
0x140002eb1  xor     edx, edx; Val
0x140002eb3  lea     rcx, [rsp+278h+Buffer]; void *
0x140002eb8  mov     r8d, 200h; Size
0x140002ebe  call    memset_0
0x140002ec3  test    [rbx+4], bpl
0x140002ec7  jz      short loc_140002EEC
0x140002ec9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140002ed0  mov     ebp, [rbx+0Ch]
0x140002ed3  test    rax, rax
0x140002ed6  jz      short loc_140002F1C
0x140002ed8  mov     r8d, 100h
0x140002ede  lea     rdx, [rsp+278h+Buffer]
0x140002ee3  mov     ecx, ebp
0x140002ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002eea  jmp     short loc_140002F1C
0x140002eec  mov     ebp, [rbx+8]
0x140002eef  lea     rax, [rsp+278h+Buffer]
0x140002ef4  mov     [rsp+278h+Arguments], r15; Arguments
0x140002ef9  mov     r8d, ebp; dwMessageId
0x140002efc  mov     [rsp+278h+nSize], 100h; nSize
0x140002f04  mov     r9d, 400h; dwLanguageId
0x140002f0a  xor     edx, edx; lpSource
0x140002f0c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140002f11  mov     ecx, 1200h; dwFlags
0x140002f16  call    cs:__imp_FormatMessageW
0x140002f1c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140002f20  lea     rsi, [r14+rsi*2]
0x140002f24  mov     rax, [rbx+88h]
0x140002f2b  mov     rdx, rsi; unsigned __int16 *
0x140002f2e  mov     rcx, [rbx+80h]
0x140002f35  test    r9, r9
0x140002f38  jz      short loc_140002F5C
0x140002f3a  mov     [rsp+278h+Arguments], rax
0x140002f3f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140002f46  mov     eax, [rbx+40h]
0x140002f49  mov     qword ptr [rsp+278h+nSize], rcx
0x140002f4e  mov     rcx, r14; this
0x140002f51  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140002f55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140002f5a  jmp     short loc_140002F73
0x140002f5c  mov     r9, rcx; unsigned __int16 *
0x140002f5f  mov     [rsp+278h+lpBuffer], rax
0x140002f64  mov     rcx, r14; this
0x140002f67  lea     r8, aHsP; "%hs!%p: "
0x140002f6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140002f73  mov     r9, [rbx+90h]; unsigned __int16 *
0x140002f7a  mov     r14, rax
0x140002f7d  test    r9, r9
0x140002f80  jz      short loc_140002F97
0x140002f82  lea     r8, aCallerP; "(caller: %p) "
0x140002f89  mov     rdx, rsi; unsigned __int16 *
0x140002f8c  mov     rcx, rax; this
0x140002f8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140002f94  mov     r14, rax
0x140002f97  call    cs:__imp_GetCurrentThreadId
0x140002f9d  lea     rcx, [rsp+278h+Buffer]
0x140002fa2  mov     r9, rdi; unsigned __int16 *
0x140002fa5  mov     [rsp+278h+var_240], rcx
0x140002faa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140002fb1  mov     dword ptr [rsp+278h+Arguments], ebp
0x140002fb5  mov     rdx, rsi; unsigned __int16 *
0x140002fb8  mov     [rsp+278h+nSize], eax
0x140002fbc  mov     rcx, r14; this
0x140002fbf  mov     eax, [rbx+44h]
0x140002fc2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140002fc6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140002fcb  cmp     [rbx+18h], r15
0x140002fcf  jnz     short loc_140002FE1
0x140002fd1  cmp     [rbx+48h], r15
0x140002fd5  jnz     short loc_140002FE1
0x140002fd7  cmp     [rbx+30h], r15
0x140002fdb  jz      loc_140003071
0x140002fe1  lea     r8, asc_140006650; "    "
0x140002fe8  mov     rdx, rsi; unsigned __int16 *
0x140002feb  mov     rcx, rax; this
0x140002fee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140002ff3  mov     r9, [rbx+18h]; unsigned __int16 *
0x140002ff7  test    r9, r9
0x140002ffa  jz      short loc_14000300E
0x140002ffc  lea     r8, aMsgWs; "Msg:[%ws] "
0x140003003  mov     rdx, rsi; unsigned __int16 *
0x140003006  mov     rcx, rax; this
0x140003009  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000300e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140003012  test    r9, r9
0x140003015  jz      short loc_140003029
0x140003017  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000301e  mov     rdx, rsi; unsigned __int16 *
0x140003021  mov     rcx, rax; this
0x140003024  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003029  mov     rcx, [rbx+28h]
0x14000302d  mov     rdx, rsi; unsigned __int16 *
0x140003030  mov     r9, [rbx+30h]; unsigned __int16 *
0x140003034  test    rcx, rcx
0x140003037  jz      short loc_14000304F
0x140003039  mov     [rsp+278h+lpBuffer], rcx
0x14000303e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003045  mov     rcx, rax; this
0x140003048  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000304d  jmp     short loc_140003071
0x14000304f  mov     rcx, rax; this
0x140003052  test    r9, r9
0x140003055  jz      short loc_140003065
0x140003057  lea     r8, aHs; "[%hs]\n"
0x14000305e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003063  jmp     short loc_140003071
0x140003065  lea     r8, asc_1400066C8; "\n"
0x14000306c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003071  xor     eax, eax
0x140003073  mov     rcx, [rsp+278h+var_38]
0x14000307b  xor     rcx, rsp; StackCookie
0x14000307e  call    __security_check_cookie
0x140003083  mov     rbx, [rsp+278h+arg_18]
0x14000308b  add     rsp, 250h
0x140003092  pop     r15
0x140003094  pop     r14
0x140003096  pop     rdi
0x140003097  pop     rsi
0x140003098  pop     rbp
0x140003099  retn
```
