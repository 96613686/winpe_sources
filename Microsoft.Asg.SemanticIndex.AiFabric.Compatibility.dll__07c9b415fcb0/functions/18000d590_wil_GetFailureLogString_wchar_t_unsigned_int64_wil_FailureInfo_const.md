# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000d590`
- end: `0x18000d850`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `704`
- prototype: `__int64 __fastcall(wchar_t *Buffer, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d850`
- `0x18000dce0`
- `0x1800471c0`
- `0x180071480`
- `0x180073520`
- `0x18024e040`
- `0x18024e168`
- `0x18024e310`
- `0x18024e501`

## callees

- `0x18000d4d0`
- `0x18000d590`
- `0x1801f7110`
- `0x180242120`
- `0x180242860`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000d749`
- `KERNEL32!GetCurrentThreadId` at `0x18000d749`
- `KERNEL32!FormatMessageW` at `0x18000d6c8`
- `KERNEL32!FormatMessageW` at `0x18000d6c8`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wchar_t *Buffer,
        wchar_t *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  DWORD v8; // r15d
  wchar_t *v9; // rsi
  const wchar_t *v10; // r9
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  wchar_t *v13; // rax
  wchar_t *v14; // rbp
  const wchar_t *v15; // r9
  wchar_t *v16; // rax
  const wchar_t *v17; // r9
  wchar_t *v18; // rax
  const wchar_t *v19; // r9
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffera[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( a2 )
  {
    if ( Buffer )
    {
      *Buffer = 0;
      if ( !g_pfnResultLoggingCallback
        || !wil::details::g_resultMessageCallbackSet
        || (g_pfnResultLoggingCallback(a3, Buffer, a2, a4), !*Buffer) )
      {
        v7 = (const char *)&byte_1802990D8;
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
        memset(Buffera, 0, sizeof(Buffera));
        if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
        {
          v8 = *(_DWORD *)(a3 + 12);
          if ( wil::details::g_pfnFormatNtStatusMsg )
            wil::details::g_pfnFormatNtStatusMsg(v8, Buffera, 0x100u);
        }
        else
        {
          v8 = *(_DWORD *)(a3 + 8);
          FormatMessageW(0x1200u, 0, v8, 0x400u, Buffera, 0x100u, 0);
        }
        v9 = &Buffer[(_QWORD)a2];
        v10 = *(const wchar_t **)(a3 + 56);
        v11 = *(_QWORD *)(a3 + 136);
        v12 = *(const wchar_t **)(a3 + 128);
        if ( v10 )
        {
          LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
          v13 = wil::details::LogStringPrintf(Buffer, v9, L"%hs(%u)\\%hs!%p: ", v10, lpBuffer, v12, v11);
        }
        else
        {
          v13 = wil::details::LogStringPrintf(Buffer, v9, L"%hs!%p: ", v12, v11);
        }
        v14 = v13;
        v15 = *(const wchar_t **)(a3 + 144);
        if ( v15 )
          v14 = wil::details::LogStringPrintf(v13, v9, L"(caller: %p) ", v15);
        LODWORD(Arguments) = v8;
        nSize[0] = GetCurrentThreadId();
        LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
        v16 = wil::details::LogStringPrintf(
                v14,
                v9,
                L"%hs(%d) tid(%x) %08X %ws",
                (const wchar_t *)v7,
                lpBuffera,
                *(_QWORD *)nSize,
                Arguments,
                Buffera);
        if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
        {
          v18 = wil::details::LogStringPrintf(v16, v9, L"    ", v17);
          v19 = *(const wchar_t **)(a3 + 24);
          if ( v19 )
            v18 = wil::details::LogStringPrintf(v18, v9, L"Msg:[%ws] ", v19);
          v20 = *(const wchar_t **)(a3 + 72);
          if ( v20 )
            v18 = wil::details::LogStringPrintf(v18, v9, L"CallContext:[%hs] ", v20);
          v21 = *(const wchar_t **)(a3 + 48);
          if ( *(_QWORD *)(a3 + 40) )
          {
            wil::details::LogStringPrintf(v18, v9, L"[%hs(%hs)]\n", v21, *(_QWORD *)(a3 + 40));
          }
          else if ( v21 )
          {
            wil::details::LogStringPrintf(v18, v9, L"[%hs]\n", v21);
          }
          else
          {
            wil::details::LogStringPrintf(v18, v9, L"\n", 0);
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
0x18000d590  mov     [rsp+arg_18], rbx
0x18000d595  push    rbp
0x18000d596  push    rsi
0x18000d597  push    rdi
0x18000d598  push    r14
0x18000d59a  push    r15
0x18000d59c  sub     rsp, 250h
0x18000d5a3  mov     rax, cs:__security_cookie
0x18000d5aa  xor     rax, rsp
0x18000d5ad  mov     [rsp+278h+var_38], rax
0x18000d5b5  mov     rbx, r8
0x18000d5b8  mov     rsi, rdx
0x18000d5bb  mov     r14, rcx
0x18000d5be  test    rdx, rdx
0x18000d5c1  jz      loc_18000D827
0x18000d5c7  test    rcx, rcx
0x18000d5ca  jz      loc_18000D827
0x18000d5d0  xor     ebp, ebp
0x18000d5d2  mov     [rcx], bp
0x18000d5d5  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d5dc  test    rax, rax
0x18000d5df  jz      short loc_18000D603
0x18000d5e1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bpl; bool wil::details::g_resultMessageCallbackSet
0x18000d5e8  jz      short loc_18000D603
0x18000d5ea  mov     r8, rdx
0x18000d5ed  mov     rdx, rcx
0x18000d5f0  mov     rcx, rbx
0x18000d5f3  call    cs:__guard_dispatch_icall_fptr
0x18000d5f9  cmp     [r14], bp
0x18000d5fd  jnz     loc_18000D827
0x18000d603  lea     rdi, byte_1802990D8
0x18000d60a  mov     ecx, [rbx]
0x18000d60c  test    ecx, ecx
0x18000d60e  jz      short loc_18000D658
0x18000d610  sub     ecx, 1
0x18000d613  jz      short loc_18000D640
0x18000d615  sub     ecx, 1
0x18000d618  jz      short loc_18000D628
0x18000d61a  cmp     ecx, 1
0x18000d61d  jnz     short loc_18000D65F
0x18000d61f  lea     rdi, aFailfast; "FailFast"
0x18000d626  jmp     short loc_18000D65F
0x18000d628  test    byte ptr [rbx+4], 8
0x18000d62c  lea     rax, aLoghr; "LogHr"
0x18000d633  lea     rdi, aLognt; "LogNt"
0x18000d63a  cmovz   rdi, rax
0x18000d63e  jmp     short loc_18000D65F
0x18000d640  test    byte ptr [rbx+4], 8
0x18000d644  lea     rax, aReturnhr; "ReturnHr"
0x18000d64b  lea     rdi, aReturnnt; "ReturnNt"
0x18000d652  cmovz   rdi, rax
0x18000d656  jmp     short loc_18000D65F
0x18000d658  lea     rdi, aException_1; "Exception"
0x18000d65f  xor     edx, edx; Val
0x18000d661  mov     r8d, 200h; Size
0x18000d667  lea     rcx, [rsp+278h+Buffer]; void *
0x18000d66c  call    memset
0x18000d671  test    byte ptr [rbx+4], 8
0x18000d675  jz      short loc_18000D69D
0x18000d677  mov     r15d, [rbx+0Ch]
0x18000d67b  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18000d682  test    rax, rax
0x18000d685  jz      short loc_18000D6CE
0x18000d687  mov     r8d, 100h
0x18000d68d  lea     rdx, [rsp+278h+Buffer]
0x18000d692  mov     ecx, r15d
0x18000d695  call    cs:__guard_dispatch_icall_fptr
0x18000d69b  jmp     short loc_18000D6CE
0x18000d69d  mov     r15d, [rbx+8]
0x18000d6a1  mov     [rsp+278h+Arguments], rbp; Arguments
0x18000d6a6  mov     [rsp+278h+nSize], 100h; nSize
0x18000d6ae  lea     rax, [rsp+278h+Buffer]
0x18000d6b3  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000d6b8  mov     r9d, 400h; dwLanguageId
0x18000d6be  mov     r8d, r15d; dwMessageId
0x18000d6c1  xor     edx, edx; lpSource
0x18000d6c3  mov     ecx, 1200h; dwFlags
0x18000d6c8  call    cs:__imp_FormatMessageW
0x18000d6ce  lea     rsi, [r14+rsi*2]
0x18000d6d2  mov     r9, [rbx+38h]; wchar_t *
0x18000d6d6  mov     rax, [rbx+88h]
0x18000d6dd  mov     rcx, [rbx+80h]
0x18000d6e4  mov     rdx, rsi; wchar_t *
0x18000d6e7  test    r9, r9
0x18000d6ea  jz      short loc_18000D70E
0x18000d6ec  mov     [rsp+278h+Arguments], rax
0x18000d6f1  mov     qword ptr [rsp+278h+nSize], rcx
0x18000d6f6  mov     eax, [rbx+40h]
0x18000d6f9  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d6fd  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000d704  mov     rcx, r14; Buffer
0x18000d707  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000d70c  jmp     short loc_18000D725
0x18000d70e  mov     [rsp+278h+lpBuffer], rax
0x18000d713  mov     r9, rcx; wchar_t *
0x18000d716  lea     r8, aHsP; "%hs!%p: "
0x18000d71d  mov     rcx, r14; Buffer
0x18000d720  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000d725  mov     rbp, rax
0x18000d728  mov     r9, [rbx+90h]; wchar_t *
0x18000d72f  test    r9, r9
0x18000d732  jz      short loc_18000D749
0x18000d734  lea     r8, aCallerP; "(caller: %p) "
0x18000d73b  mov     rdx, rsi; wchar_t *
0x18000d73e  mov     rcx, rax; Buffer
0x18000d741  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000d746  mov     rbp, rax
0x18000d749  call    cs:__imp_GetCurrentThreadId
0x18000d74f  lea     rcx, [rsp+278h+Buffer]
0x18000d754  mov     [rsp+278h+var_240], rcx
0x18000d759  mov     dword ptr [rsp+278h+Arguments], r15d
0x18000d75e  mov     [rsp+278h+nSize], eax
0x18000d762  mov     eax, [rbx+44h]
0x18000d765  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d769  mov     r9, rdi; wchar_t *
0x18000d76c  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000d773  mov     rdx, rsi; wchar_t *
0x18000d776  mov     rcx, rbp; Buffer
0x18000d779  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000d77e  cmp     qword ptr [rbx+18h], 0
0x18000d783  jnz     short loc_18000D797
0x18000d785  cmp     qword ptr [rbx+48h], 0
0x18000d78a  jnz     short loc_18000D797
0x18000d78c  cmp     qword ptr [rbx+30h], 0
0x18000d791  jz      loc_18000D827
0x18000d797  lea     r8, asc_1802991F0; "    "
0x18000d79e  mov     rdx, rsi; wchar_t *
0x18000d7a1  mov     rcx, rax; Buffer
0x18000d7a4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000d7a9  mov     r9, [rbx+18h]; wchar_t *
0x18000d7ad  test    r9, r9
0x18000d7b0  jz      short loc_18000D7C4
0x18000d7b2  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000d7b9  mov     rdx, rsi; wchar_t *
0x18000d7bc  mov     rcx, rax; Buffer
0x18000d7bf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000d7c4  mov     r9, [rbx+48h]; wchar_t *
0x18000d7c8  test    r9, r9
0x18000d7cb  jz      short loc_18000D7DF
0x18000d7cd  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000d7d4  mov     rdx, rsi; wchar_t *
0x18000d7d7  mov     rcx, rax; Buffer
0x18000d7da  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000d7df  mov     rcx, [rbx+28h]
0x18000d7e3  mov     r9, [rbx+30h]; wchar_t *
0x18000d7e7  mov     rdx, rsi; wchar_t *
0x18000d7ea  test    rcx, rcx
0x18000d7ed  jz      short loc_18000D805
0x18000d7ef  mov     [rsp+278h+lpBuffer], rcx
0x18000d7f4  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000d7fb  mov     rcx, rax; Buffer
0x18000d7fe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000d803  jmp     short loc_18000D827
0x18000d805  mov     rcx, rax; Buffer
0x18000d808  test    r9, r9
0x18000d80b  jz      short loc_18000D81B
0x18000d80d  lea     r8, aHs_1; "[%hs]\n"
0x18000d814  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000d819  jmp     short loc_18000D827
0x18000d81b  lea     r8, Source; "\n"
0x18000d822  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000d827  xor     eax, eax
0x18000d829  mov     rcx, [rsp+278h+var_38]
0x18000d831  xor     rcx, rsp; StackCookie
0x18000d834  call    __security_check_cookie
0x18000d839  mov     rbx, [rsp+278h+arg_18]
0x18000d841  add     rsp, 250h
0x18000d848  pop     r15
0x18000d84a  pop     r14
0x18000d84c  pop     rdi
0x18000d84d  pop     rsi
0x18000d84e  pop     rbp
0x18000d84f  retn
```
