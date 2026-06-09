# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180011b64`
- end: `0x180011e1a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e488`
- `0x180013c38`
- `0x180014144`
- `0x180016ae0`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x180011b64`
- `0x180013f18`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011d17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011d17`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180011c96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180011c96`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
          v7 = (const char *)&byte_180031EE0;
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
0x180011b64  mov     [rsp+arg_18], rbx
0x180011b69  push    rbp
0x180011b6a  push    rsi
0x180011b6b  push    rdi
0x180011b6c  push    r14
0x180011b6e  push    r15
0x180011b70  sub     rsp, 250h
0x180011b77  mov     rax, cs:__security_cookie
0x180011b7e  xor     rax, rsp
0x180011b81  mov     [rsp+278h+var_38], rax
0x180011b89  mov     rbx, r8
0x180011b8c  mov     rsi, rdx
0x180011b8f  mov     r14, rcx
0x180011b92  xor     r15d, r15d
0x180011b95  test    rdx, rdx
0x180011b98  jz      loc_180011DF1
0x180011b9e  test    rcx, rcx
0x180011ba1  jz      loc_180011DF1
0x180011ba7  mov     [rcx], r15w
0x180011bab  mov     rax, cs:g_pfnResultLoggingCallback
0x180011bb2  test    rax, rax
0x180011bb5  jz      short loc_180011BD8
0x180011bb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180011bbe  jz      short loc_180011BD8
0x180011bc0  mov     r8, rdx
0x180011bc3  mov     rdx, rcx
0x180011bc6  mov     rcx, rbx
0x180011bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bce  cmp     [r14], r15w
0x180011bd2  jnz     loc_180011DF1
0x180011bd8  mov     ecx, [rbx]
0x180011bda  mov     bpl, 8
0x180011bdd  test    ecx, ecx
0x180011bdf  jz      short loc_180011C2A
0x180011be1  sub     ecx, 1
0x180011be4  jz      short loc_180011C12
0x180011be6  sub     ecx, 1
0x180011be9  jz      short loc_180011C02
0x180011beb  cmp     ecx, 1
0x180011bee  jz      short loc_180011BF9
0x180011bf0  lea     rdi, byte_180031EE0
0x180011bf7  jmp     short loc_180011C31
0x180011bf9  lea     rdi, aFailfast; "FailFast"
0x180011c00  jmp     short loc_180011C31
0x180011c02  lea     rax, aLoghr; "LogHr"
0x180011c09  lea     rdi, aLognt; "LogNt"
0x180011c10  jmp     short loc_180011C20
0x180011c12  lea     rax, aReturnhr; "ReturnHr"
0x180011c19  lea     rdi, aReturnnt; "ReturnNt"
0x180011c20  test    [rbx+4], bpl
0x180011c24  cmovz   rdi, rax
0x180011c28  jmp     short loc_180011C31
0x180011c2a  lea     rdi, aException; "Exception"
0x180011c31  xor     edx, edx; Val
0x180011c33  mov     r8d, 200h; Size
0x180011c39  lea     rcx, [rsp+278h+Buffer]; void *
0x180011c3e  call    memset_0
0x180011c43  test    [rbx+4], bpl
0x180011c47  jz      short loc_180011C6C
0x180011c49  mov     ebp, [rbx+0Ch]
0x180011c4c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180011c53  test    rax, rax
0x180011c56  jz      short loc_180011C9C
0x180011c58  mov     r8d, 100h
0x180011c5e  lea     rdx, [rsp+278h+Buffer]
0x180011c63  mov     ecx, ebp
0x180011c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c6a  jmp     short loc_180011C9C
0x180011c6c  mov     ebp, [rbx+8]
0x180011c6f  mov     [rsp+278h+Arguments], r15; Arguments
0x180011c74  mov     [rsp+278h+nSize], 100h; nSize
0x180011c7c  lea     rax, [rsp+278h+Buffer]
0x180011c81  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180011c86  mov     r9d, 400h; dwLanguageId
0x180011c8c  mov     r8d, ebp; dwMessageId
0x180011c8f  xor     edx, edx; lpSource
0x180011c91  mov     ecx, 1200h; dwFlags
0x180011c96  call    cs:__imp_FormatMessageW
0x180011c9c  lea     rsi, [r14+rsi*2]
0x180011ca0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180011ca4  mov     rax, [rbx+88h]
0x180011cab  mov     rcx, [rbx+80h]
0x180011cb2  mov     rdx, rsi; unsigned __int16 *
0x180011cb5  test    r9, r9
0x180011cb8  jz      short loc_180011CDC
0x180011cba  mov     [rsp+278h+Arguments], rax
0x180011cbf  mov     qword ptr [rsp+278h+nSize], rcx
0x180011cc4  mov     eax, [rbx+40h]
0x180011cc7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011ccb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180011cd2  mov     rcx, r14; this
0x180011cd5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011cda  jmp     short loc_180011CF3
0x180011cdc  mov     [rsp+278h+lpBuffer], rax
0x180011ce1  mov     r9, rcx; unsigned __int16 *
0x180011ce4  lea     r8, aHsP; "%hs!%p: "
0x180011ceb  mov     rcx, r14; this
0x180011cee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011cf3  mov     r14, rax
0x180011cf6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180011cfd  test    r9, r9
0x180011d00  jz      short loc_180011D17
0x180011d02  lea     r8, aCallerP; "(caller: %p) "
0x180011d09  mov     rdx, rsi; unsigned __int16 *
0x180011d0c  mov     rcx, rax; this
0x180011d0f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011d14  mov     r14, rax
0x180011d17  call    cs:__imp_GetCurrentThreadId
0x180011d1d  lea     rcx, [rsp+278h+Buffer]
0x180011d22  mov     [rsp+278h+var_240], rcx
0x180011d27  mov     dword ptr [rsp+278h+Arguments], ebp
0x180011d2b  mov     [rsp+278h+nSize], eax
0x180011d2f  mov     eax, [rbx+44h]
0x180011d32  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011d36  mov     r9, rdi; unsigned __int16 *
0x180011d39  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180011d40  mov     rdx, rsi; unsigned __int16 *
0x180011d43  mov     rcx, r14; this
0x180011d46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011d4b  cmp     [rbx+18h], r15
0x180011d4f  jnz     short loc_180011D61
0x180011d51  cmp     [rbx+48h], r15
0x180011d55  jnz     short loc_180011D61
0x180011d57  cmp     [rbx+30h], r15
0x180011d5b  jz      loc_180011DF1
0x180011d61  lea     r8, asc_180032000; "    "
0x180011d68  mov     rdx, rsi; unsigned __int16 *
0x180011d6b  mov     rcx, rax; this
0x180011d6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011d73  mov     r9, [rbx+18h]; unsigned __int16 *
0x180011d77  test    r9, r9
0x180011d7a  jz      short loc_180011D8E
0x180011d7c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180011d83  mov     rdx, rsi; unsigned __int16 *
0x180011d86  mov     rcx, rax; this
0x180011d89  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011d8e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180011d92  test    r9, r9
0x180011d95  jz      short loc_180011DA9
0x180011d97  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180011d9e  mov     rdx, rsi; unsigned __int16 *
0x180011da1  mov     rcx, rax; this
0x180011da4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011da9  mov     rcx, [rbx+28h]
0x180011dad  mov     r9, [rbx+30h]; unsigned __int16 *
0x180011db1  mov     rdx, rsi; unsigned __int16 *
0x180011db4  test    rcx, rcx
0x180011db7  jz      short loc_180011DCF
0x180011db9  mov     [rsp+278h+lpBuffer], rcx
0x180011dbe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180011dc5  mov     rcx, rax; this
0x180011dc8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011dcd  jmp     short loc_180011DF1
0x180011dcf  mov     rcx, rax; this
0x180011dd2  test    r9, r9
0x180011dd5  jz      short loc_180011DE5
0x180011dd7  lea     r8, aHs; "[%hs]\n"
0x180011dde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011de3  jmp     short loc_180011DF1
0x180011de5  lea     r8, asc_180032078; "\n"
0x180011dec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011df1  xor     eax, eax
0x180011df3  mov     rcx, [rsp+278h+var_38]
0x180011dfb  xor     rcx, rsp; StackCookie
0x180011dfe  call    __security_check_cookie
0x180011e03  mov     rbx, [rsp+278h+arg_18]
0x180011e0b  add     rsp, 250h
0x180011e12  pop     r15
0x180011e14  pop     r14
0x180011e16  pop     rdi
0x180011e17  pop     rsi
0x180011e18  pop     rbp
0x180011e19  retn
```
