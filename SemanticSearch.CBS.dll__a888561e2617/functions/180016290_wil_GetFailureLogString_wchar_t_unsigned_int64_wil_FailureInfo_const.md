# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180016290`
- end: `0x180016550`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `704`
- prototype: `__int64 __fastcall(wchar_t *Buffer, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180015c60`
- `0x180016550`
- `0x1800169a0`
- `0x1800416e0`
- `0x180043330`
- `0x1800632d0`
- `0x1800633f8`
- `0x180063560`
- `0x180063751`

## callees

- `0x1800161d0`
- `0x180016290`
- `0x18004c070`
- `0x18005e260`
- `0x18005e2c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180016449`
- `KERNEL32!GetCurrentThreadId` at `0x180016449`
- `KERNEL32!FormatMessageW` at `0x1800163c8`
- `KERNEL32!FormatMessageW` at `0x1800163c8`

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
        || (g_pfnResultLoggingCallback(a3, Buffer, a2), !*Buffer) )
      {
        v7 = (const char *)&qword_18006F810;
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
0x180016290  mov     [rsp+arg_18], rbx
0x180016295  push    rbp
0x180016296  push    rsi
0x180016297  push    rdi
0x180016298  push    r14
0x18001629a  push    r15
0x18001629c  sub     rsp, 250h
0x1800162a3  mov     rax, cs:__security_cookie
0x1800162aa  xor     rax, rsp
0x1800162ad  mov     [rsp+278h+var_38], rax
0x1800162b5  mov     rbx, r8
0x1800162b8  mov     rsi, rdx
0x1800162bb  mov     r14, rcx
0x1800162be  test    rdx, rdx
0x1800162c1  jz      loc_180016527
0x1800162c7  test    rcx, rcx
0x1800162ca  jz      loc_180016527
0x1800162d0  xor     ebp, ebp
0x1800162d2  mov     [rcx], bp
0x1800162d5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800162dc  test    rax, rax
0x1800162df  jz      short loc_180016303
0x1800162e1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bpl; bool wil::details::g_resultMessageCallbackSet
0x1800162e8  jz      short loc_180016303
0x1800162ea  mov     r8, rdx
0x1800162ed  mov     rdx, rcx
0x1800162f0  mov     rcx, rbx
0x1800162f3  call    cs:__guard_dispatch_icall_fptr
0x1800162f9  cmp     [r14], bp
0x1800162fd  jnz     loc_180016527
0x180016303  lea     rdi, qword_18006F810
0x18001630a  mov     ecx, [rbx]
0x18001630c  test    ecx, ecx
0x18001630e  jz      short loc_180016358
0x180016310  sub     ecx, 1
0x180016313  jz      short loc_180016340
0x180016315  sub     ecx, 1
0x180016318  jz      short loc_180016328
0x18001631a  cmp     ecx, 1
0x18001631d  jnz     short loc_18001635F
0x18001631f  lea     rdi, aFailfast; "FailFast"
0x180016326  jmp     short loc_18001635F
0x180016328  test    byte ptr [rbx+4], 8
0x18001632c  lea     rax, aLoghr; "LogHr"
0x180016333  lea     rdi, aLognt; "LogNt"
0x18001633a  cmovz   rdi, rax
0x18001633e  jmp     short loc_18001635F
0x180016340  test    byte ptr [rbx+4], 8
0x180016344  lea     rax, aReturnhr; "ReturnHr"
0x18001634b  lea     rdi, aReturnnt; "ReturnNt"
0x180016352  cmovz   rdi, rax
0x180016356  jmp     short loc_18001635F
0x180016358  lea     rdi, aException; "Exception"
0x18001635f  xor     edx, edx; Val
0x180016361  mov     r8d, 200h; Size
0x180016367  lea     rcx, [rsp+278h+Buffer]; void *
0x18001636c  call    memset
0x180016371  test    byte ptr [rbx+4], 8
0x180016375  jz      short loc_18001639D
0x180016377  mov     r15d, [rbx+0Ch]
0x18001637b  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180016382  test    rax, rax
0x180016385  jz      short loc_1800163CE
0x180016387  mov     r8d, 100h
0x18001638d  lea     rdx, [rsp+278h+Buffer]
0x180016392  mov     ecx, r15d
0x180016395  call    cs:__guard_dispatch_icall_fptr
0x18001639b  jmp     short loc_1800163CE
0x18001639d  mov     r15d, [rbx+8]
0x1800163a1  mov     [rsp+278h+Arguments], rbp; Arguments
0x1800163a6  mov     [rsp+278h+nSize], 100h; nSize
0x1800163ae  lea     rax, [rsp+278h+Buffer]
0x1800163b3  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800163b8  mov     r9d, 400h; dwLanguageId
0x1800163be  mov     r8d, r15d; dwMessageId
0x1800163c1  xor     edx, edx; lpSource
0x1800163c3  mov     ecx, 1200h; dwFlags
0x1800163c8  call    cs:__imp_FormatMessageW
0x1800163ce  lea     rsi, [r14+rsi*2]
0x1800163d2  mov     r9, [rbx+38h]; wchar_t *
0x1800163d6  mov     rax, [rbx+88h]
0x1800163dd  mov     rcx, [rbx+80h]
0x1800163e4  mov     rdx, rsi; wchar_t *
0x1800163e7  test    r9, r9
0x1800163ea  jz      short loc_18001640E
0x1800163ec  mov     [rsp+278h+Arguments], rax
0x1800163f1  mov     qword ptr [rsp+278h+nSize], rcx
0x1800163f6  mov     eax, [rbx+40h]
0x1800163f9  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800163fd  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180016404  mov     rcx, r14; Buffer
0x180016407  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18001640c  jmp     short loc_180016425
0x18001640e  mov     [rsp+278h+lpBuffer], rax
0x180016413  mov     r9, rcx; wchar_t *
0x180016416  lea     r8, aHsP; "%hs!%p: "
0x18001641d  mov     rcx, r14; Buffer
0x180016420  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180016425  mov     rbp, rax
0x180016428  mov     r9, [rbx+90h]; wchar_t *
0x18001642f  test    r9, r9
0x180016432  jz      short loc_180016449
0x180016434  lea     r8, aCallerP; "(caller: %p) "
0x18001643b  mov     rdx, rsi; wchar_t *
0x18001643e  mov     rcx, rax; Buffer
0x180016441  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180016446  mov     rbp, rax
0x180016449  call    cs:__imp_GetCurrentThreadId
0x18001644f  lea     rcx, [rsp+278h+Buffer]
0x180016454  mov     [rsp+278h+var_240], rcx
0x180016459  mov     dword ptr [rsp+278h+Arguments], r15d
0x18001645e  mov     [rsp+278h+nSize], eax
0x180016462  mov     eax, [rbx+44h]
0x180016465  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180016469  mov     r9, rdi; wchar_t *
0x18001646c  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180016473  mov     rdx, rsi; wchar_t *
0x180016476  mov     rcx, rbp; Buffer
0x180016479  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18001647e  cmp     qword ptr [rbx+18h], 0
0x180016483  jnz     short loc_180016497
0x180016485  cmp     qword ptr [rbx+48h], 0
0x18001648a  jnz     short loc_180016497
0x18001648c  cmp     qword ptr [rbx+30h], 0
0x180016491  jz      loc_180016527
0x180016497  lea     r8, asc_18006F900; "    "
0x18001649e  mov     rdx, rsi; wchar_t *
0x1800164a1  mov     rcx, rax; Buffer
0x1800164a4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800164a9  mov     r9, [rbx+18h]; wchar_t *
0x1800164ad  test    r9, r9
0x1800164b0  jz      short loc_1800164C4
0x1800164b2  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800164b9  mov     rdx, rsi; wchar_t *
0x1800164bc  mov     rcx, rax; Buffer
0x1800164bf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800164c4  mov     r9, [rbx+48h]; wchar_t *
0x1800164c8  test    r9, r9
0x1800164cb  jz      short loc_1800164DF
0x1800164cd  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800164d4  mov     rdx, rsi; wchar_t *
0x1800164d7  mov     rcx, rax; Buffer
0x1800164da  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800164df  mov     rcx, [rbx+28h]
0x1800164e3  mov     r9, [rbx+30h]; wchar_t *
0x1800164e7  mov     rdx, rsi; wchar_t *
0x1800164ea  test    rcx, rcx
0x1800164ed  jz      short loc_180016505
0x1800164ef  mov     [rsp+278h+lpBuffer], rcx
0x1800164f4  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800164fb  mov     rcx, rax; Buffer
0x1800164fe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180016503  jmp     short loc_180016527
0x180016505  mov     rcx, rax; Buffer
0x180016508  test    r9, r9
0x18001650b  jz      short loc_18001651B
0x18001650d  lea     r8, aHs; "[%hs]\n"
0x180016514  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180016519  jmp     short loc_180016527
0x18001651b  lea     r8, asc_18006F978; "\n"
0x180016522  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180016527  xor     eax, eax
0x180016529  mov     rcx, [rsp+278h+var_38]
0x180016531  xor     rcx, rsp; StackCookie
0x180016534  call    __security_check_cookie
0x180016539  mov     rbx, [rsp+278h+arg_18]
0x180016541  add     rsp, 250h
0x180016548  pop     r15
0x18001654a  pop     r14
0x18001654c  pop     rdi
0x18001654d  pop     rsi
0x18001654e  pop     rbp
0x18001654f  retn
```
