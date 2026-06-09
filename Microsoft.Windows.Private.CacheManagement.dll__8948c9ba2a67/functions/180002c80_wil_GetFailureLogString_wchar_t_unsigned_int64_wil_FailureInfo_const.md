# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180002c80`
- end: `0x180002f40`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `704`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800027b0`
- `0x180003070`
- `0x180012b20`
- `0x180013910`
- `0x1800156f0`
- `0x18001e930`
- `0x18001ea58`
- `0x18001ebc0`
- `0x18001edb1`

## callees

- `0x180002c00`
- `0x180002c80`
- `0x1800181b0`
- `0x18001cdf0`
- `0x18001d600`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002e39`
- `KERNEL32!GetCurrentThreadId` at `0x180002e39`
- `KERNEL32!FormatMessageW` at `0x180002db8`
- `KERNEL32!FormatMessageW` at `0x180002db8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  DWORD v8; // r15d
  wchar_t *v9; // rsi
  const wchar_t *v10; // r9
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  wchar_t *v13; // rax
  wil::details *v14; // rbp
  const wchar_t *v15; // r9
  wil::details *v16; // rax
  const wchar_t *v17; // r9
  wchar_t *v18; // rax
  const wchar_t *v19; // r9
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( a2 )
  {
    if ( this )
    {
      *(_WORD *)this = 0;
      if ( !g_pfnResultLoggingCallback
        || !wil::details::g_resultMessageCallbackSet
        || (g_pfnResultLoggingCallback(a3, this, a2), !*(_WORD *)this) )
      {
        v7 = (const char *)&qword_1800250A8;
        if ( *(_DWORD *)a3 )
        {
          switch ( *(_DWORD *)a3 )
          {
            case 1:
              v7 = "ReturnNt";
              if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
                v7 = "ReturnHr";
              break;
            case 2:
              v7 = "LogNt";
              if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
                v7 = "LogHr";
              break;
            case 3:
              v7 = "FailFast";
              break;
          }
        }
        else
        {
          v7 = "Exception";
        }
        memset(Buffer, 0, sizeof(Buffer));
        if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
        {
          v8 = *(_DWORD *)(a3 + 12);
          if ( wil::details::g_pfnFormatNtStatusMsg )
            wil::details::g_pfnFormatNtStatusMsg(v8, Buffer, 0x100u);
        }
        else
        {
          v8 = *(_DWORD *)(a3 + 8);
          FormatMessageW(0x1200u, 0, v8, 0x400u, Buffer, 0x100u, 0);
        }
        v9 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
        v10 = *(const wchar_t **)(a3 + 56);
        v11 = *(_QWORD *)(a3 + 136);
        v12 = *(const wchar_t **)(a3 + 128);
        if ( v10 )
        {
          LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
          v13 = wil::details::LogStringPrintf(this, v9, L"%hs(%u)\\%hs!%p: ", v10, lpBuffer, v12, v11);
        }
        else
        {
          v13 = wil::details::LogStringPrintf(this, v9, L"%hs!%p: ", v12, v11);
        }
        v14 = (wil::details *)v13;
        v15 = *(const wchar_t **)(a3 + 144);
        if ( v15 )
          v14 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v13, v9, L"(caller: %p) ", v15);
        LODWORD(Arguments) = v8;
        nSize[0] = GetCurrentThreadId();
        LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
        v16 = (wil::details *)wil::details::LogStringPrintf(
                                v14,
                                v9,
                                L"%hs(%d) tid(%x) %08X %ws",
                                (const wchar_t *)v7,
                                lpBuffera,
                                *(_QWORD *)nSize,
                                Arguments,
                                Buffer);
        if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
        {
          v18 = wil::details::LogStringPrintf(v16, v9, L"    ", v17);
          v19 = *(const wchar_t **)(a3 + 24);
          if ( v19 )
            v18 = wil::details::LogStringPrintf((wil::details *)v18, v9, L"Msg:[%ws] ", v19);
          v20 = *(const wchar_t **)(a3 + 72);
          if ( v20 )
            v18 = wil::details::LogStringPrintf((wil::details *)v18, v9, L"CallContext:[%hs] ", v20);
          v21 = *(const wchar_t **)(a3 + 48);
          if ( *(_QWORD *)(a3 + 40) )
          {
            wil::details::LogStringPrintf((wil::details *)v18, v9, L"[%hs(%hs)]\n", v21, *(_QWORD *)(a3 + 40));
          }
          else if ( v21 )
          {
            wil::details::LogStringPrintf((wil::details *)v18, v9, L"[%hs]\n", v21);
          }
          else
          {
            wil::details::LogStringPrintf((wil::details *)v18, v9, L"\n", 0);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002c80  mov     [rsp+arg_18], rbx
0x180002c85  push    rbp
0x180002c86  push    rsi
0x180002c87  push    rdi
0x180002c88  push    r14
0x180002c8a  push    r15
0x180002c8c  sub     rsp, 250h
0x180002c93  mov     rax, cs:__security_cookie
0x180002c9a  xor     rax, rsp
0x180002c9d  mov     [rsp+278h+var_38], rax
0x180002ca5  mov     rbx, r8
0x180002ca8  mov     rsi, rdx
0x180002cab  mov     r14, rcx
0x180002cae  test    rdx, rdx
0x180002cb1  jz      loc_180002F17
0x180002cb7  test    rcx, rcx
0x180002cba  jz      loc_180002F17
0x180002cc0  xor     ebp, ebp
0x180002cc2  mov     [rcx], bp
0x180002cc5  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ccc  test    rax, rax
0x180002ccf  jz      short loc_180002CF3
0x180002cd1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bpl; bool wil::details::g_resultMessageCallbackSet
0x180002cd8  jz      short loc_180002CF3
0x180002cda  mov     r8, rdx
0x180002cdd  mov     rdx, rcx
0x180002ce0  mov     rcx, rbx
0x180002ce3  call    cs:__guard_dispatch_icall_fptr
0x180002ce9  cmp     [r14], bp
0x180002ced  jnz     loc_180002F17
0x180002cf3  lea     rdi, qword_1800250A8
0x180002cfa  mov     ecx, [rbx]
0x180002cfc  test    ecx, ecx
0x180002cfe  jz      short loc_180002D48
0x180002d00  sub     ecx, 1
0x180002d03  jz      short loc_180002D30
0x180002d05  sub     ecx, 1
0x180002d08  jz      short loc_180002D18
0x180002d0a  cmp     ecx, 1
0x180002d0d  jnz     short loc_180002D4F
0x180002d0f  lea     rdi, aFailfast; "FailFast"
0x180002d16  jmp     short loc_180002D4F
0x180002d18  test    byte ptr [rbx+4], 8
0x180002d1c  lea     rax, aLoghr; "LogHr"
0x180002d23  lea     rdi, aLognt; "LogNt"
0x180002d2a  cmovz   rdi, rax
0x180002d2e  jmp     short loc_180002D4F
0x180002d30  test    byte ptr [rbx+4], 8
0x180002d34  lea     rax, aReturnhr; "ReturnHr"
0x180002d3b  lea     rdi, aReturnnt; "ReturnNt"
0x180002d42  cmovz   rdi, rax
0x180002d46  jmp     short loc_180002D4F
0x180002d48  lea     rdi, aException; "Exception"
0x180002d4f  xor     edx, edx; Val
0x180002d51  mov     r8d, 200h; Size
0x180002d57  lea     rcx, [rsp+278h+Buffer]; void *
0x180002d5c  call    memset
0x180002d61  test    byte ptr [rbx+4], 8
0x180002d65  jz      short loc_180002D8D
0x180002d67  mov     r15d, [rbx+0Ch]
0x180002d6b  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180002d72  test    rax, rax
0x180002d75  jz      short loc_180002DBE
0x180002d77  mov     r8d, 100h
0x180002d7d  lea     rdx, [rsp+278h+Buffer]
0x180002d82  mov     ecx, r15d
0x180002d85  call    cs:__guard_dispatch_icall_fptr
0x180002d8b  jmp     short loc_180002DBE
0x180002d8d  mov     r15d, [rbx+8]
0x180002d91  mov     [rsp+278h+Arguments], rbp; Arguments
0x180002d96  mov     [rsp+278h+nSize], 100h; nSize
0x180002d9e  lea     rax, [rsp+278h+Buffer]
0x180002da3  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180002da8  mov     r9d, 400h; dwLanguageId
0x180002dae  mov     r8d, r15d; dwMessageId
0x180002db1  xor     edx, edx; lpSource
0x180002db3  mov     ecx, 1200h; dwFlags
0x180002db8  call    cs:__imp_FormatMessageW
0x180002dbe  lea     rsi, [r14+rsi*2]
0x180002dc2  mov     r9, [rbx+38h]; wchar_t *
0x180002dc6  mov     rax, [rbx+88h]
0x180002dcd  mov     rcx, [rbx+80h]
0x180002dd4  mov     rdx, rsi; wchar_t *
0x180002dd7  test    r9, r9
0x180002dda  jz      short loc_180002DFE
0x180002ddc  mov     [rsp+278h+Arguments], rax
0x180002de1  mov     qword ptr [rsp+278h+nSize], rcx
0x180002de6  mov     eax, [rbx+40h]
0x180002de9  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002ded  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180002df4  mov     rcx, r14; this
0x180002df7  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002dfc  jmp     short loc_180002E15
0x180002dfe  mov     [rsp+278h+lpBuffer], rax
0x180002e03  mov     r9, rcx; wchar_t *
0x180002e06  lea     r8, aHsP; "%hs!%p: "
0x180002e0d  mov     rcx, r14; this
0x180002e10  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002e15  mov     rbp, rax
0x180002e18  mov     r9, [rbx+90h]; wchar_t *
0x180002e1f  test    r9, r9
0x180002e22  jz      short loc_180002E39
0x180002e24  lea     r8, aCallerP; "(caller: %p) "
0x180002e2b  mov     rdx, rsi; wchar_t *
0x180002e2e  mov     rcx, rax; this
0x180002e31  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002e36  mov     rbp, rax
0x180002e39  call    cs:__imp_GetCurrentThreadId
0x180002e3f  lea     rcx, [rsp+278h+Buffer]
0x180002e44  mov     [rsp+278h+var_240], rcx
0x180002e49  mov     dword ptr [rsp+278h+Arguments], r15d
0x180002e4e  mov     [rsp+278h+nSize], eax
0x180002e52  mov     eax, [rbx+44h]
0x180002e55  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002e59  mov     r9, rdi; wchar_t *
0x180002e5c  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180002e63  mov     rdx, rsi; wchar_t *
0x180002e66  mov     rcx, rbp; this
0x180002e69  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002e6e  cmp     qword ptr [rbx+18h], 0
0x180002e73  jnz     short loc_180002E87
0x180002e75  cmp     qword ptr [rbx+48h], 0
0x180002e7a  jnz     short loc_180002E87
0x180002e7c  cmp     qword ptr [rbx+30h], 0
0x180002e81  jz      loc_180002F17
0x180002e87  lea     r8, asc_180025198; "    "
0x180002e8e  mov     rdx, rsi; wchar_t *
0x180002e91  mov     rcx, rax; this
0x180002e94  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002e99  mov     r9, [rbx+18h]; wchar_t *
0x180002e9d  test    r9, r9
0x180002ea0  jz      short loc_180002EB4
0x180002ea2  lea     r8, aMsgWs; "Msg:[%ws] "
0x180002ea9  mov     rdx, rsi; wchar_t *
0x180002eac  mov     rcx, rax; this
0x180002eaf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002eb4  mov     r9, [rbx+48h]; wchar_t *
0x180002eb8  test    r9, r9
0x180002ebb  jz      short loc_180002ECF
0x180002ebd  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180002ec4  mov     rdx, rsi; wchar_t *
0x180002ec7  mov     rcx, rax; this
0x180002eca  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002ecf  mov     rcx, [rbx+28h]
0x180002ed3  mov     r9, [rbx+30h]; wchar_t *
0x180002ed7  mov     rdx, rsi; wchar_t *
0x180002eda  test    rcx, rcx
0x180002edd  jz      short loc_180002EF5
0x180002edf  mov     [rsp+278h+lpBuffer], rcx
0x180002ee4  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180002eeb  mov     rcx, rax; this
0x180002eee  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002ef3  jmp     short loc_180002F17
0x180002ef5  mov     rcx, rax; this
0x180002ef8  test    r9, r9
0x180002efb  jz      short loc_180002F0B
0x180002efd  lea     r8, aHs; "[%hs]\n"
0x180002f04  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002f09  jmp     short loc_180002F17
0x180002f0b  lea     r8, asc_180025210; "\n"
0x180002f12  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002f17  xor     eax, eax
0x180002f19  mov     rcx, [rsp+278h+var_38]
0x180002f21  xor     rcx, rsp; StackCookie
0x180002f24  call    __security_check_cookie
0x180002f29  mov     rbx, [rsp+278h+arg_18]
0x180002f31  add     rsp, 250h
0x180002f38  pop     r15
0x180002f3a  pop     r14
0x180002f3c  pop     rdi
0x180002f3d  pop     rsi
0x180002f3e  pop     rbp
0x180002f3f  retn
```
