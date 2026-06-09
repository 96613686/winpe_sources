# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800049a4`
- end: `0x180004c5a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800033e4`
- `0x180003664`
- `0x180005480`
- `0x180007590`
- `0x180013d08`
- `0x18002c11f`
- `0x18002c253`

## callees

- `0x1800049a4`
- `0x180005780`
- `0x18002bc62`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b57`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ad6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ad6`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&byte_180033D2B;
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
0x1800049a4  mov     [rsp+arg_18], rbx
0x1800049a9  push    rbp
0x1800049aa  push    rsi
0x1800049ab  push    rdi
0x1800049ac  push    r14
0x1800049ae  push    r15
0x1800049b0  sub     rsp, 250h
0x1800049b7  mov     rax, cs:__security_cookie
0x1800049be  xor     rax, rsp
0x1800049c1  mov     [rsp+278h+var_38], rax
0x1800049c9  mov     rbx, r8
0x1800049cc  mov     rsi, rdx
0x1800049cf  mov     r14, rcx
0x1800049d2  xor     r15d, r15d
0x1800049d5  test    rdx, rdx
0x1800049d8  jz      loc_180004C31
0x1800049de  test    rcx, rcx
0x1800049e1  jz      loc_180004C31
0x1800049e7  mov     [rcx], r15w
0x1800049eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800049f2  test    rax, rax
0x1800049f5  jz      short loc_180004A18
0x1800049f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800049fe  jz      short loc_180004A18
0x180004a00  mov     r8, rdx
0x180004a03  mov     rdx, rcx
0x180004a06  mov     rcx, rbx
0x180004a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0e  cmp     [r14], r15w
0x180004a12  jnz     loc_180004C31
0x180004a18  mov     ecx, [rbx]
0x180004a1a  mov     bpl, 8
0x180004a1d  test    ecx, ecx
0x180004a1f  jz      short loc_180004A6A
0x180004a21  sub     ecx, 1
0x180004a24  jz      short loc_180004A52
0x180004a26  sub     ecx, 1
0x180004a29  jz      short loc_180004A42
0x180004a2b  cmp     ecx, 1
0x180004a2e  jz      short loc_180004A39
0x180004a30  lea     rdi, byte_180033D2B
0x180004a37  jmp     short loc_180004A71
0x180004a39  lea     rdi, aFailfast; "FailFast"
0x180004a40  jmp     short loc_180004A71
0x180004a42  lea     rax, aLoghr; "LogHr"
0x180004a49  lea     rdi, aLognt; "LogNt"
0x180004a50  jmp     short loc_180004A60
0x180004a52  lea     rax, aReturnhr; "ReturnHr"
0x180004a59  lea     rdi, aReturnnt; "ReturnNt"
0x180004a60  test    [rbx+4], bpl
0x180004a64  cmovz   rdi, rax
0x180004a68  jmp     short loc_180004A71
0x180004a6a  lea     rdi, aException; "Exception"
0x180004a71  xor     edx, edx; Val
0x180004a73  mov     r8d, 200h; Size
0x180004a79  lea     rcx, [rsp+278h+Buffer]; void *
0x180004a7e  call    memset_0
0x180004a83  test    [rbx+4], bpl
0x180004a87  jz      short loc_180004AAC
0x180004a89  mov     ebp, [rbx+0Ch]
0x180004a8c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004a93  test    rax, rax
0x180004a96  jz      short loc_180004ADC
0x180004a98  mov     r8d, 100h
0x180004a9e  lea     rdx, [rsp+278h+Buffer]
0x180004aa3  mov     ecx, ebp
0x180004aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aaa  jmp     short loc_180004ADC
0x180004aac  mov     ebp, [rbx+8]
0x180004aaf  mov     [rsp+278h+Arguments], r15; Arguments
0x180004ab4  mov     [rsp+278h+nSize], 100h; nSize
0x180004abc  lea     rax, [rsp+278h+Buffer]
0x180004ac1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004ac6  mov     r9d, 400h; dwLanguageId
0x180004acc  mov     r8d, ebp; dwMessageId
0x180004acf  xor     edx, edx; lpSource
0x180004ad1  mov     ecx, 1200h; dwFlags
0x180004ad6  call    cs:__imp_FormatMessageW
0x180004adc  lea     rsi, [r14+rsi*2]
0x180004ae0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004ae4  mov     rax, [rbx+88h]
0x180004aeb  mov     rcx, [rbx+80h]
0x180004af2  mov     rdx, rsi; unsigned __int16 *
0x180004af5  test    r9, r9
0x180004af8  jz      short loc_180004B1C
0x180004afa  mov     [rsp+278h+Arguments], rax
0x180004aff  mov     qword ptr [rsp+278h+nSize], rcx
0x180004b04  mov     eax, [rbx+40h]
0x180004b07  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004b0b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004b12  mov     rcx, r14; this
0x180004b15  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b1a  jmp     short loc_180004B33
0x180004b1c  mov     [rsp+278h+lpBuffer], rax
0x180004b21  mov     r9, rcx; unsigned __int16 *
0x180004b24  lea     r8, aHsP; "%hs!%p: "
0x180004b2b  mov     rcx, r14; this
0x180004b2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b33  mov     r14, rax
0x180004b36  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004b3d  test    r9, r9
0x180004b40  jz      short loc_180004B57
0x180004b42  lea     r8, aCallerP; "(caller: %p) "
0x180004b49  mov     rdx, rsi; unsigned __int16 *
0x180004b4c  mov     rcx, rax; this
0x180004b4f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b54  mov     r14, rax
0x180004b57  call    cs:__imp_GetCurrentThreadId
0x180004b5d  lea     rcx, [rsp+278h+Buffer]
0x180004b62  mov     [rsp+278h+var_240], rcx
0x180004b67  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004b6b  mov     [rsp+278h+nSize], eax
0x180004b6f  mov     eax, [rbx+44h]
0x180004b72  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004b76  mov     r9, rdi; unsigned __int16 *
0x180004b79  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004b80  mov     rdx, rsi; unsigned __int16 *
0x180004b83  mov     rcx, r14; this
0x180004b86  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b8b  cmp     [rbx+18h], r15
0x180004b8f  jnz     short loc_180004BA1
0x180004b91  cmp     [rbx+48h], r15
0x180004b95  jnz     short loc_180004BA1
0x180004b97  cmp     [rbx+30h], r15
0x180004b9b  jz      loc_180004C31
0x180004ba1  lea     r8, asc_180033E18; "    "
0x180004ba8  mov     rdx, rsi; unsigned __int16 *
0x180004bab  mov     rcx, rax; this
0x180004bae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bb3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004bb7  test    r9, r9
0x180004bba  jz      short loc_180004BCE
0x180004bbc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004bc3  mov     rdx, rsi; unsigned __int16 *
0x180004bc6  mov     rcx, rax; this
0x180004bc9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bce  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004bd2  test    r9, r9
0x180004bd5  jz      short loc_180004BE9
0x180004bd7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004bde  mov     rdx, rsi; unsigned __int16 *
0x180004be1  mov     rcx, rax; this
0x180004be4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004be9  mov     rcx, [rbx+28h]
0x180004bed  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004bf1  mov     rdx, rsi; unsigned __int16 *
0x180004bf4  test    rcx, rcx
0x180004bf7  jz      short loc_180004C0F
0x180004bf9  mov     [rsp+278h+lpBuffer], rcx
0x180004bfe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004c05  mov     rcx, rax; this
0x180004c08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c0d  jmp     short loc_180004C31
0x180004c0f  mov     rcx, rax; this
0x180004c12  test    r9, r9
0x180004c15  jz      short loc_180004C25
0x180004c17  lea     r8, aHs; "[%hs]\n"
0x180004c1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c23  jmp     short loc_180004C31
0x180004c25  lea     r8, asc_180033E90; "\n"
0x180004c2c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c31  xor     eax, eax
0x180004c33  mov     rcx, [rsp+278h+var_38]
0x180004c3b  xor     rcx, rsp; StackCookie
0x180004c3e  call    __security_check_cookie
0x180004c43  mov     rbx, [rsp+278h+arg_18]
0x180004c4b  add     rsp, 250h
0x180004c52  pop     r15
0x180004c54  pop     r14
0x180004c56  pop     rdi
0x180004c57  pop     rsi
0x180004c58  pop     rbp
0x180004c59  retn
```
