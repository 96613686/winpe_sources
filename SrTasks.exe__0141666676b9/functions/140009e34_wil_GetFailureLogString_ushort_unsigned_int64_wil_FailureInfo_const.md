# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140009e34`
- end: `0x14000a0ea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140007f20`
- `0x140008188`
- `0x14000a790`

## callees

- `0x140009e34`
- `0x14000aa90`
- `0x14001094e`
- `0x140010980`
- `0x140011010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140009f66`
- `KERNEL32!FormatMessageW` at `0x140009f66`
- `KERNEL32!GetCurrentThreadId` at `0x140009fe7`
- `KERNEL32!GetCurrentThreadId` at `0x140009fe7`

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
          v8 = (const char *)&qword_140013320;
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
0x140009e34  mov     [rsp+arg_18], rbx
0x140009e39  push    rbp
0x140009e3a  push    rsi
0x140009e3b  push    rdi
0x140009e3c  push    r14
0x140009e3e  push    r15
0x140009e40  sub     rsp, 250h
0x140009e47  mov     rax, cs:__security_cookie
0x140009e4e  xor     rax, rsp
0x140009e51  mov     [rsp+278h+var_38], rax
0x140009e59  xor     r15d, r15d
0x140009e5c  mov     rbx, r8
0x140009e5f  mov     rsi, rdx
0x140009e62  mov     r14, rcx
0x140009e65  test    rdx, rdx
0x140009e68  jz      loc_14000A0C1
0x140009e6e  test    rcx, rcx
0x140009e71  jz      loc_14000A0C1
0x140009e77  mov     rax, cs:g_pfnResultLoggingCallback
0x140009e7e  mov     [rcx], r15w
0x140009e82  test    rax, rax
0x140009e85  jz      short loc_140009EA8
0x140009e87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140009e8e  jz      short loc_140009EA8
0x140009e90  mov     r8, rdx
0x140009e93  mov     rdx, rcx
0x140009e96  mov     rcx, rbx
0x140009e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e9e  cmp     [r14], r15w
0x140009ea2  jnz     loc_14000A0C1
0x140009ea8  mov     ecx, [rbx]
0x140009eaa  mov     bpl, 8
0x140009ead  test    ecx, ecx
0x140009eaf  jz      short loc_140009EFA
0x140009eb1  sub     ecx, 1
0x140009eb4  jz      short loc_140009EE2
0x140009eb6  sub     ecx, 1
0x140009eb9  jz      short loc_140009ED2
0x140009ebb  cmp     ecx, 1
0x140009ebe  jz      short loc_140009EC9
0x140009ec0  lea     rdi, qword_140013320
0x140009ec7  jmp     short loc_140009F01
0x140009ec9  lea     rdi, aFailfast; "FailFast"
0x140009ed0  jmp     short loc_140009F01
0x140009ed2  lea     rax, aLoghr; "LogHr"
0x140009ed9  lea     rdi, aLognt; "LogNt"
0x140009ee0  jmp     short loc_140009EF0
0x140009ee2  lea     rax, aReturnhr; "ReturnHr"
0x140009ee9  lea     rdi, aReturnnt; "ReturnNt"
0x140009ef0  test    [rbx+4], bpl
0x140009ef4  cmovz   rdi, rax
0x140009ef8  jmp     short loc_140009F01
0x140009efa  lea     rdi, aException; "Exception"
0x140009f01  xor     edx, edx; Val
0x140009f03  lea     rcx, [rsp+278h+Buffer]; void *
0x140009f08  mov     r8d, 200h; Size
0x140009f0e  call    memset_0
0x140009f13  test    [rbx+4], bpl
0x140009f17  jz      short loc_140009F3C
0x140009f19  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140009f20  mov     ebp, [rbx+0Ch]
0x140009f23  test    rax, rax
0x140009f26  jz      short loc_140009F6C
0x140009f28  mov     r8d, 100h
0x140009f2e  lea     rdx, [rsp+278h+Buffer]
0x140009f33  mov     ecx, ebp
0x140009f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f3a  jmp     short loc_140009F6C
0x140009f3c  mov     ebp, [rbx+8]
0x140009f3f  lea     rax, [rsp+278h+Buffer]
0x140009f44  mov     [rsp+278h+Arguments], r15; Arguments
0x140009f49  mov     r8d, ebp; dwMessageId
0x140009f4c  mov     [rsp+278h+nSize], 100h; nSize
0x140009f54  mov     r9d, 400h; dwLanguageId
0x140009f5a  xor     edx, edx; lpSource
0x140009f5c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140009f61  mov     ecx, 1200h; dwFlags
0x140009f66  call    cs:__imp_FormatMessageW
0x140009f6c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140009f70  lea     rsi, [r14+rsi*2]
0x140009f74  mov     rax, [rbx+88h]
0x140009f7b  mov     rdx, rsi; unsigned __int16 *
0x140009f7e  mov     rcx, [rbx+80h]
0x140009f85  test    r9, r9
0x140009f88  jz      short loc_140009FAC
0x140009f8a  mov     [rsp+278h+Arguments], rax
0x140009f8f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140009f96  mov     eax, [rbx+40h]
0x140009f99  mov     qword ptr [rsp+278h+nSize], rcx
0x140009f9e  mov     rcx, r14; this
0x140009fa1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140009fa5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009faa  jmp     short loc_140009FC3
0x140009fac  mov     r9, rcx; unsigned __int16 *
0x140009faf  mov     [rsp+278h+lpBuffer], rax
0x140009fb4  mov     rcx, r14; this
0x140009fb7  lea     r8, aHsP; "%hs!%p: "
0x140009fbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009fc3  mov     r9, [rbx+90h]; unsigned __int16 *
0x140009fca  mov     r14, rax
0x140009fcd  test    r9, r9
0x140009fd0  jz      short loc_140009FE7
0x140009fd2  lea     r8, aCallerP; "(caller: %p) "
0x140009fd9  mov     rdx, rsi; unsigned __int16 *
0x140009fdc  mov     rcx, rax; this
0x140009fdf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140009fe4  mov     r14, rax
0x140009fe7  call    cs:__imp_GetCurrentThreadId
0x140009fed  lea     rcx, [rsp+278h+Buffer]
0x140009ff2  mov     r9, rdi; unsigned __int16 *
0x140009ff5  mov     [rsp+278h+var_240], rcx
0x140009ffa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000a001  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000a005  mov     rdx, rsi; unsigned __int16 *
0x14000a008  mov     [rsp+278h+nSize], eax
0x14000a00c  mov     rcx, r14; this
0x14000a00f  mov     eax, [rbx+44h]
0x14000a012  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000a016  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a01b  cmp     [rbx+18h], r15
0x14000a01f  jnz     short loc_14000A031
0x14000a021  cmp     [rbx+48h], r15
0x14000a025  jnz     short loc_14000A031
0x14000a027  cmp     [rbx+30h], r15
0x14000a02b  jz      loc_14000A0C1
0x14000a031  lea     r8, asc_140013410; "    "
0x14000a038  mov     rdx, rsi; unsigned __int16 *
0x14000a03b  mov     rcx, rax; this
0x14000a03e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a043  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000a047  test    r9, r9
0x14000a04a  jz      short loc_14000A05E
0x14000a04c  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000a053  mov     rdx, rsi; unsigned __int16 *
0x14000a056  mov     rcx, rax; this
0x14000a059  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a05e  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000a062  test    r9, r9
0x14000a065  jz      short loc_14000A079
0x14000a067  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000a06e  mov     rdx, rsi; unsigned __int16 *
0x14000a071  mov     rcx, rax; this
0x14000a074  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a079  mov     rcx, [rbx+28h]
0x14000a07d  mov     rdx, rsi; unsigned __int16 *
0x14000a080  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000a084  test    rcx, rcx
0x14000a087  jz      short loc_14000A09F
0x14000a089  mov     [rsp+278h+lpBuffer], rcx
0x14000a08e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000a095  mov     rcx, rax; this
0x14000a098  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a09d  jmp     short loc_14000A0C1
0x14000a09f  mov     rcx, rax; this
0x14000a0a2  test    r9, r9
0x14000a0a5  jz      short loc_14000A0B5
0x14000a0a7  lea     r8, aHs; "[%hs]\n"
0x14000a0ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a0b3  jmp     short loc_14000A0C1
0x14000a0b5  lea     r8, asc_140013488; "\n"
0x14000a0bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a0c1  xor     eax, eax
0x14000a0c3  mov     rcx, [rsp+278h+var_38]
0x14000a0cb  xor     rcx, rsp; StackCookie
0x14000a0ce  call    __security_check_cookie
0x14000a0d3  mov     rbx, [rsp+278h+arg_18]
0x14000a0db  add     rsp, 250h
0x14000a0e2  pop     r15
0x14000a0e4  pop     r14
0x14000a0e6  pop     rdi
0x14000a0e7  pop     rsi
0x14000a0e8  pop     rbp
0x14000a0e9  retn
```
