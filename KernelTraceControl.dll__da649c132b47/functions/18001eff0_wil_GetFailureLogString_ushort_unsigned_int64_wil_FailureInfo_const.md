# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001eff0`
- end: `0x18001f23c`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `588`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f8f0`
- `0x18001fba0`

## callees

- `0x18001ef70`
- `0x18001eff0`
- `0x180026e30`
- `0x180027910`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18001f0c3`
- `KERNEL32!FormatMessageW` at `0x18001f0c3`
- `KERNEL32!GetCurrentThreadId` at `0x18001f13f`
- `KERNEL32!GetCurrentThreadId` at `0x18001f13f`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rbp
  DWORD v9; // r8d
  const unsigned __int16 *v10; // r9
  unsigned __int16 *v11; // rdi
  __int64 v12; // rax
  unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // r9
  wil::details *v15; // rsi
  DWORD CurrentThreadId; // eax
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

  if ( this )
  {
    v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
    *(_WORD *)this = 0;
    if ( !v7 || !wil::details::g_resultMessageCallbackSet || (v7(a3, this, a2, a4), !*(_WORD *)this) )
    {
      v8 = (const char *)&qword_18002D6D0;
      if ( *(_DWORD *)a3 )
      {
        switch ( *(_DWORD *)a3 )
        {
          case 1:
            v8 = "ReturnHr";
            break;
          case 2:
            v8 = "LogHr";
            break;
          case 3:
            v8 = "FailFast";
            break;
        }
      }
      else
      {
        v8 = "Exception";
      }
      v9 = *(_DWORD *)(a3 + 4);
      Buffer[0] = 0;
      FormatMessageW(0x1200u, 0, v9, 0x400u, Buffer, 0x100u, 0);
      v10 = *(const unsigned __int16 **)(a3 + 48);
      v11 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
      v12 = *(_QWORD *)(a3 + 128);
      if ( v10 )
      {
        LODWORD(lpBuffer) = *(_DWORD *)(a3 + 56);
        v13 = wil::details::LogStringPrintf(this, v11, L"%hs(%d)\\%hs!%p: ", v10, lpBuffer, *(_QWORD *)(a3 + 120), v12);
      }
      else
      {
        v13 = wil::details::LogStringPrintf(this, v11, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 120), v12);
      }
      v14 = *(const unsigned __int16 **)(a3 + 136);
      v15 = (wil::details *)v13;
      if ( v14 )
        v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v13, v11, L"(caller: %p) ", v14);
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(Arguments) = *(_DWORD *)(a3 + 4);
      nSize[0] = CurrentThreadId;
      LODWORD(lpBuffera) = *(_DWORD *)(a3 + 60);
      v17 = (wil::details *)wil::details::LogStringPrintf(
                              v15,
                              v11,
                              L"%hs(%d) tid(%x) %08X %ws",
                              (const unsigned __int16 *)v8,
                              lpBuffera,
                              *(_QWORD *)nSize,
                              Arguments,
                              Buffer);
      if ( *(_QWORD *)(a3 + 16) || *(_QWORD *)(a3 + 64) || *(_QWORD *)(a3 + 40) )
      {
        v19 = wil::details::LogStringPrintf(v17, v11, L"    ", v18);
        v20 = *(const unsigned __int16 **)(a3 + 16);
        if ( v20 )
          v19 = wil::details::LogStringPrintf((wil::details *)v19, v11, L"Msg:[%ws] ", v20);
        v21 = *(const unsigned __int16 **)(a3 + 64);
        if ( v21 )
          v19 = wil::details::LogStringPrintf((wil::details *)v19, v11, L"CallContext:[%hs] ", v21);
        v22 = *(const unsigned __int16 **)(a3 + 40);
        if ( *(_QWORD *)(a3 + 32) )
        {
          wil::details::LogStringPrintf((wil::details *)v19, v11, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 32));
        }
        else if ( v22 )
        {
          wil::details::LogStringPrintf((wil::details *)v19, v11, L"[%hs]\n", v22);
        }
        else
        {
          wil::details::LogStringPrintf((wil::details *)v19, v11, L"\n", 0);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001eff0  push    rbx
0x18001eff2  push    rbp
0x18001eff3  push    rsi
0x18001eff4  push    rdi
0x18001eff5  push    r14
0x18001eff7  sub     rsp, 250h
0x18001effe  mov     rax, cs:__security_cookie
0x18001f005  xor     rax, rsp
0x18001f008  mov     [rsp+278h+var_38], rax
0x18001f010  xor     r14d, r14d
0x18001f013  mov     rbx, r8
0x18001f016  mov     rdi, rdx
0x18001f019  mov     rsi, rcx
0x18001f01c  test    rcx, rcx
0x18001f01f  jz      loc_18001F21C
0x18001f025  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f02c  mov     [rcx], r14w
0x18001f030  test    rax, rax
0x18001f033  jz      short loc_18001F057
0x18001f035  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x18001f03c  jz      short loc_18001F057
0x18001f03e  mov     r8, rdx
0x18001f041  mov     rdx, rcx
0x18001f044  mov     rcx, rbx
0x18001f047  call    cs:__guard_dispatch_icall_fptr
0x18001f04d  cmp     [rsi], r14w
0x18001f051  jnz     loc_18001F21C
0x18001f057  mov     ecx, [rbx]
0x18001f059  lea     rbp, qword_18002D6D0
0x18001f060  test    ecx, ecx
0x18001f062  jz      short loc_18001F08E
0x18001f064  sub     ecx, 1
0x18001f067  jz      short loc_18001F085
0x18001f069  sub     ecx, 1
0x18001f06c  jz      short loc_18001F07C
0x18001f06e  cmp     ecx, 1
0x18001f071  jnz     short loc_18001F095
0x18001f073  lea     rbp, aFailfast; "FailFast"
0x18001f07a  jmp     short loc_18001F095
0x18001f07c  lea     rbp, aLoghr; "LogHr"
0x18001f083  jmp     short loc_18001F095
0x18001f085  lea     rbp, aReturnhr; "ReturnHr"
0x18001f08c  jmp     short loc_18001F095
0x18001f08e  lea     rbp, aException; "Exception"
0x18001f095  mov     r8d, [rbx+4]; dwMessageId
0x18001f099  lea     rax, [rsp+278h+Buffer]
0x18001f09e  mov     [rsp+278h+Arguments], r14; Arguments
0x18001f0a3  mov     r9d, 400h; dwLanguageId
0x18001f0a9  mov     [rsp+278h+nSize], 100h; nSize
0x18001f0b1  xor     edx, edx; lpSource
0x18001f0b3  mov     ecx, 1200h; dwFlags
0x18001f0b8  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001f0bd  mov     [rsp+278h+Buffer], r14w
0x18001f0c3  call    cs:__imp_FormatMessageW
0x18001f0c9  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001f0cd  lea     rdi, [rsi+rdi*2]
0x18001f0d1  mov     rax, [rbx+80h]
0x18001f0d8  mov     rdx, rdi; unsigned __int16 *
0x18001f0db  mov     rcx, rsi; this
0x18001f0de  test    r9, r9
0x18001f0e1  jz      short loc_18001F106
0x18001f0e3  mov     [rsp+278h+Arguments], rax
0x18001f0e8  lea     r8, aHsDHsP; "%hs(%d)\\%hs!%p: "
0x18001f0ef  mov     rax, [rbx+78h]
0x18001f0f3  mov     qword ptr [rsp+278h+nSize], rax
0x18001f0f8  mov     eax, [rbx+38h]
0x18001f0fb  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001f0ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f104  jmp     short loc_18001F11B
0x18001f106  mov     r9, [rbx+78h]; unsigned __int16 *
0x18001f10a  lea     r8, aHsP; "%hs!%p: "
0x18001f111  mov     [rsp+278h+lpBuffer], rax
0x18001f116  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f11b  mov     r9, [rbx+88h]; unsigned __int16 *
0x18001f122  mov     rsi, rax
0x18001f125  test    r9, r9
0x18001f128  jz      short loc_18001F13F
0x18001f12a  lea     r8, aCallerP; "(caller: %p) "
0x18001f131  mov     rdx, rdi; unsigned __int16 *
0x18001f134  mov     rcx, rax; this
0x18001f137  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f13c  mov     rsi, rax
0x18001f13f  call    cs:__imp_GetCurrentThreadId
0x18001f145  lea     rcx, [rsp+278h+Buffer]
0x18001f14a  mov     r9, rbp; unsigned __int16 *
0x18001f14d  mov     [rsp+278h+var_240], rcx
0x18001f152  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001f159  mov     ecx, [rbx+4]
0x18001f15c  mov     rdx, rdi; unsigned __int16 *
0x18001f15f  mov     dword ptr [rsp+278h+Arguments], ecx
0x18001f163  mov     rcx, rsi; this
0x18001f166  mov     [rsp+278h+nSize], eax
0x18001f16a  mov     eax, [rbx+3Ch]
0x18001f16d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001f171  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f176  cmp     [rbx+10h], r14
0x18001f17a  jnz     short loc_18001F18C
0x18001f17c  cmp     [rbx+40h], r14
0x18001f180  jnz     short loc_18001F18C
0x18001f182  cmp     [rbx+28h], r14
0x18001f186  jz      loc_18001F21C
0x18001f18c  lea     r8, asc_18002D550; "    "
0x18001f193  mov     rdx, rdi; unsigned __int16 *
0x18001f196  mov     rcx, rax; this
0x18001f199  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f19e  mov     r9, [rbx+10h]; unsigned __int16 *
0x18001f1a2  test    r9, r9
0x18001f1a5  jz      short loc_18001F1B9
0x18001f1a7  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001f1ae  mov     rdx, rdi; unsigned __int16 *
0x18001f1b1  mov     rcx, rax; this
0x18001f1b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f1b9  mov     r9, [rbx+40h]; unsigned __int16 *
0x18001f1bd  test    r9, r9
0x18001f1c0  jz      short loc_18001F1D4
0x18001f1c2  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001f1c9  mov     rdx, rdi; unsigned __int16 *
0x18001f1cc  mov     rcx, rax; this
0x18001f1cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f1d4  mov     rcx, [rbx+20h]
0x18001f1d8  mov     rdx, rdi; unsigned __int16 *
0x18001f1db  mov     r9, [rbx+28h]; unsigned __int16 *
0x18001f1df  test    rcx, rcx
0x18001f1e2  jz      short loc_18001F1FA
0x18001f1e4  mov     [rsp+278h+lpBuffer], rcx
0x18001f1e9  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001f1f0  mov     rcx, rax; this
0x18001f1f3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f1f8  jmp     short loc_18001F21C
0x18001f1fa  mov     rcx, rax; this
0x18001f1fd  test    r9, r9
0x18001f200  jz      short loc_18001F210
0x18001f202  lea     r8, aHs; "[%hs]\n"
0x18001f209  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f20e  jmp     short loc_18001F21C
0x18001f210  lea     r8, asc_18002D5C8; "\n"
0x18001f217  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001f21c  xor     eax, eax
0x18001f21e  mov     rcx, [rsp+278h+var_38]
0x18001f226  xor     rcx, rsp; StackCookie
0x18001f229  call    __security_check_cookie
0x18001f22e  add     rsp, 250h
0x18001f235  pop     r14
0x18001f237  pop     rdi
0x18001f238  pop     rsi
0x18001f239  pop     rbp
0x18001f23a  pop     rbx
0x18001f23b  retn
```
