# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000cc28`
- end: `0x18000cede`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180006f08`
- `0x18000e318`
- `0x18000eb2c`
- `0x1800149a0`

## callees

- `0x180003ca0`
- `0x18000495c`
- `0x18000cc28`
- `0x18000e618`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cddb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cddb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cd5a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000cd5a`

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
          v7 = (const char *)&byte_180067200;
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
0x18000cc28  mov     [rsp+arg_18], rbx
0x18000cc2d  push    rbp
0x18000cc2e  push    rsi
0x18000cc2f  push    rdi
0x18000cc30  push    r14
0x18000cc32  push    r15
0x18000cc34  sub     rsp, 250h
0x18000cc3b  mov     rax, cs:__security_cookie
0x18000cc42  xor     rax, rsp
0x18000cc45  mov     [rsp+278h+var_38], rax
0x18000cc4d  mov     rbx, r8
0x18000cc50  mov     rsi, rdx
0x18000cc53  mov     r14, rcx
0x18000cc56  xor     r15d, r15d
0x18000cc59  test    rdx, rdx
0x18000cc5c  jz      loc_18000CEB5
0x18000cc62  test    rcx, rcx
0x18000cc65  jz      loc_18000CEB5
0x18000cc6b  mov     [rcx], r15w
0x18000cc6f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cc76  test    rax, rax
0x18000cc79  jz      short loc_18000CC9C
0x18000cc7b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cc82  jz      short loc_18000CC9C
0x18000cc84  mov     r8, rdx
0x18000cc87  mov     rdx, rcx
0x18000cc8a  mov     rcx, rbx
0x18000cc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc92  cmp     [r14], r15w
0x18000cc96  jnz     loc_18000CEB5
0x18000cc9c  mov     ecx, [rbx]
0x18000cc9e  mov     bpl, 8
0x18000cca1  test    ecx, ecx
0x18000cca3  jz      short loc_18000CCEE
0x18000cca5  sub     ecx, 1
0x18000cca8  jz      short loc_18000CCD6
0x18000ccaa  sub     ecx, 1
0x18000ccad  jz      short loc_18000CCC6
0x18000ccaf  cmp     ecx, 1
0x18000ccb2  jz      short loc_18000CCBD
0x18000ccb4  lea     rdi, byte_180067200
0x18000ccbb  jmp     short loc_18000CCF5
0x18000ccbd  lea     rdi, aFailfast; "FailFast"
0x18000ccc4  jmp     short loc_18000CCF5
0x18000ccc6  lea     rax, aLoghr; "LogHr"
0x18000cccd  lea     rdi, aLognt; "LogNt"
0x18000ccd4  jmp     short loc_18000CCE4
0x18000ccd6  lea     rax, aReturnhr; "ReturnHr"
0x18000ccdd  lea     rdi, aReturnnt; "ReturnNt"
0x18000cce4  test    [rbx+4], bpl
0x18000cce8  cmovz   rdi, rax
0x18000ccec  jmp     short loc_18000CCF5
0x18000ccee  lea     rdi, aException; "Exception"
0x18000ccf5  xor     edx, edx; Val
0x18000ccf7  mov     r8d, 200h; Size
0x18000ccfd  lea     rcx, [rsp+278h+Buffer]; void *
0x18000cd02  call    memset_0
0x18000cd07  test    [rbx+4], bpl
0x18000cd0b  jz      short loc_18000CD30
0x18000cd0d  mov     ebp, [rbx+0Ch]
0x18000cd10  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000cd17  test    rax, rax
0x18000cd1a  jz      short loc_18000CD60
0x18000cd1c  mov     r8d, 100h
0x18000cd22  lea     rdx, [rsp+278h+Buffer]
0x18000cd27  mov     ecx, ebp
0x18000cd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd2e  jmp     short loc_18000CD60
0x18000cd30  mov     ebp, [rbx+8]
0x18000cd33  mov     [rsp+278h+Arguments], r15; Arguments
0x18000cd38  mov     [rsp+278h+nSize], 100h; nSize
0x18000cd40  lea     rax, [rsp+278h+Buffer]
0x18000cd45  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000cd4a  mov     r9d, 400h; dwLanguageId
0x18000cd50  mov     r8d, ebp; dwMessageId
0x18000cd53  xor     edx, edx; lpSource
0x18000cd55  mov     ecx, 1200h; dwFlags
0x18000cd5a  call    cs:__imp_FormatMessageW
0x18000cd60  lea     rsi, [r14+rsi*2]
0x18000cd64  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000cd68  mov     rax, [rbx+88h]
0x18000cd6f  mov     rcx, [rbx+80h]
0x18000cd76  mov     rdx, rsi; unsigned __int16 *
0x18000cd79  test    r9, r9
0x18000cd7c  jz      short loc_18000CDA0
0x18000cd7e  mov     [rsp+278h+Arguments], rax
0x18000cd83  mov     qword ptr [rsp+278h+nSize], rcx
0x18000cd88  mov     eax, [rbx+40h]
0x18000cd8b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000cd8f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000cd96  mov     rcx, r14; this
0x18000cd99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cd9e  jmp     short loc_18000CDB7
0x18000cda0  mov     [rsp+278h+lpBuffer], rax
0x18000cda5  mov     r9, rcx; unsigned __int16 *
0x18000cda8  lea     r8, aHsP; "%hs!%p: "
0x18000cdaf  mov     rcx, r14; this
0x18000cdb2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cdb7  mov     r14, rax
0x18000cdba  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000cdc1  test    r9, r9
0x18000cdc4  jz      short loc_18000CDDB
0x18000cdc6  lea     r8, aCallerP; "(caller: %p) "
0x18000cdcd  mov     rdx, rsi; unsigned __int16 *
0x18000cdd0  mov     rcx, rax; this
0x18000cdd3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cdd8  mov     r14, rax
0x18000cddb  call    cs:__imp_GetCurrentThreadId
0x18000cde1  lea     rcx, [rsp+278h+Buffer]
0x18000cde6  mov     [rsp+278h+var_240], rcx
0x18000cdeb  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000cdef  mov     [rsp+278h+nSize], eax
0x18000cdf3  mov     eax, [rbx+44h]
0x18000cdf6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000cdfa  mov     r9, rdi; unsigned __int16 *
0x18000cdfd  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000ce04  mov     rdx, rsi; unsigned __int16 *
0x18000ce07  mov     rcx, r14; this
0x18000ce0a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ce0f  cmp     [rbx+18h], r15
0x18000ce13  jnz     short loc_18000CE25
0x18000ce15  cmp     [rbx+48h], r15
0x18000ce19  jnz     short loc_18000CE25
0x18000ce1b  cmp     [rbx+30h], r15
0x18000ce1f  jz      loc_18000CEB5
0x18000ce25  lea     r8, asc_180067330; "    "
0x18000ce2c  mov     rdx, rsi; unsigned __int16 *
0x18000ce2f  mov     rcx, rax; this
0x18000ce32  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ce37  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000ce3b  test    r9, r9
0x18000ce3e  jz      short loc_18000CE52
0x18000ce40  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000ce47  mov     rdx, rsi; unsigned __int16 *
0x18000ce4a  mov     rcx, rax; this
0x18000ce4d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ce52  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000ce56  test    r9, r9
0x18000ce59  jz      short loc_18000CE6D
0x18000ce5b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000ce62  mov     rdx, rsi; unsigned __int16 *
0x18000ce65  mov     rcx, rax; this
0x18000ce68  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ce6d  mov     rcx, [rbx+28h]
0x18000ce71  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000ce75  mov     rdx, rsi; unsigned __int16 *
0x18000ce78  test    rcx, rcx
0x18000ce7b  jz      short loc_18000CE93
0x18000ce7d  mov     [rsp+278h+lpBuffer], rcx
0x18000ce82  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000ce89  mov     rcx, rax; this
0x18000ce8c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ce91  jmp     short loc_18000CEB5
0x18000ce93  mov     rcx, rax; this
0x18000ce96  test    r9, r9
0x18000ce99  jz      short loc_18000CEA9
0x18000ce9b  lea     r8, aHs; "[%hs]\n"
0x18000cea2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000cea7  jmp     short loc_18000CEB5
0x18000cea9  lea     r8, asc_1800673A8; "\n"
0x18000ceb0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ceb5  xor     eax, eax
0x18000ceb7  mov     rcx, [rsp+278h+var_38]
0x18000cebf  xor     rcx, rsp; StackCookie
0x18000cec2  call    __security_check_cookie
0x18000cec7  mov     rbx, [rsp+278h+arg_18]
0x18000cecf  add     rsp, 250h
0x18000ced6  pop     r15
0x18000ced8  pop     r14
0x18000ceda  pop     rdi
0x18000cedb  pop     rsi
0x18000cedc  pop     rbp
0x18000cedd  retn
```
