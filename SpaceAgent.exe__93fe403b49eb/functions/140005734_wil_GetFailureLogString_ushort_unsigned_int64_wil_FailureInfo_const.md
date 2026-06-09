# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005734`
- end: `0x1400059ea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140003bdc`
- `0x14000631c`

## callees

- `0x140001caf`
- `0x140005734`
- `0x14000661c`
- `0x14001edc0`
- `0x140020010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400058e7`
- `KERNEL32!GetCurrentThreadId` at `0x1400058e7`
- `KERNEL32!FormatMessageW` at `0x140005866`
- `KERNEL32!FormatMessageW` at `0x140005866`

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
          v8 = (const char *)&qword_140021E00;
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
0x140005734  mov     [rsp+arg_18], rbx
0x140005739  push    rbp
0x14000573a  push    rsi
0x14000573b  push    rdi
0x14000573c  push    r14
0x14000573e  push    r15
0x140005740  sub     rsp, 250h
0x140005747  mov     rax, cs:__security_cookie
0x14000574e  xor     rax, rsp
0x140005751  mov     [rsp+278h+var_38], rax
0x140005759  xor     r15d, r15d
0x14000575c  mov     rbx, r8
0x14000575f  mov     rsi, rdx
0x140005762  mov     r14, rcx
0x140005765  test    rdx, rdx
0x140005768  jz      loc_1400059C1
0x14000576e  test    rcx, rcx
0x140005771  jz      loc_1400059C1
0x140005777  mov     rax, cs:g_pfnResultLoggingCallback
0x14000577e  mov     [rcx], r15w
0x140005782  test    rax, rax
0x140005785  jz      short loc_1400057A8
0x140005787  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000578e  jz      short loc_1400057A8
0x140005790  mov     r8, rdx
0x140005793  mov     rdx, rcx
0x140005796  mov     rcx, rbx
0x140005799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000579e  cmp     [r14], r15w
0x1400057a2  jnz     loc_1400059C1
0x1400057a8  mov     ecx, [rbx]
0x1400057aa  mov     bpl, 8
0x1400057ad  test    ecx, ecx
0x1400057af  jz      short loc_1400057FA
0x1400057b1  sub     ecx, 1
0x1400057b4  jz      short loc_1400057E2
0x1400057b6  sub     ecx, 1
0x1400057b9  jz      short loc_1400057D2
0x1400057bb  cmp     ecx, 1
0x1400057be  jz      short loc_1400057C9
0x1400057c0  lea     rdi, qword_140021E00
0x1400057c7  jmp     short loc_140005801
0x1400057c9  lea     rdi, aFailfast; "FailFast"
0x1400057d0  jmp     short loc_140005801
0x1400057d2  lea     rax, aLoghr; "LogHr"
0x1400057d9  lea     rdi, aLognt; "LogNt"
0x1400057e0  jmp     short loc_1400057F0
0x1400057e2  lea     rax, aReturnhr; "ReturnHr"
0x1400057e9  lea     rdi, aReturnnt; "ReturnNt"
0x1400057f0  test    [rbx+4], bpl
0x1400057f4  cmovz   rdi, rax
0x1400057f8  jmp     short loc_140005801
0x1400057fa  lea     rdi, aException; "Exception"
0x140005801  xor     edx, edx; Val
0x140005803  lea     rcx, [rsp+278h+Buffer]; void *
0x140005808  mov     r8d, 200h; Size
0x14000580e  call    memset_0
0x140005813  test    [rbx+4], bpl
0x140005817  jz      short loc_14000583C
0x140005819  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140005820  mov     ebp, [rbx+0Ch]
0x140005823  test    rax, rax
0x140005826  jz      short loc_14000586C
0x140005828  mov     r8d, 100h
0x14000582e  lea     rdx, [rsp+278h+Buffer]
0x140005833  mov     ecx, ebp
0x140005835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000583a  jmp     short loc_14000586C
0x14000583c  mov     ebp, [rbx+8]
0x14000583f  lea     rax, [rsp+278h+Buffer]
0x140005844  mov     [rsp+278h+Arguments], r15; Arguments
0x140005849  mov     r8d, ebp; dwMessageId
0x14000584c  mov     [rsp+278h+nSize], 100h; nSize
0x140005854  mov     r9d, 400h; dwLanguageId
0x14000585a  xor     edx, edx; lpSource
0x14000585c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140005861  mov     ecx, 1200h; dwFlags
0x140005866  call    cs:__imp_FormatMessageW
0x14000586c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140005870  lea     rsi, [r14+rsi*2]
0x140005874  mov     rax, [rbx+88h]
0x14000587b  mov     rdx, rsi; unsigned __int16 *
0x14000587e  mov     rcx, [rbx+80h]
0x140005885  test    r9, r9
0x140005888  jz      short loc_1400058AC
0x14000588a  mov     [rsp+278h+Arguments], rax
0x14000588f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005896  mov     eax, [rbx+40h]
0x140005899  mov     qword ptr [rsp+278h+nSize], rcx
0x14000589e  mov     rcx, r14; this
0x1400058a1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400058a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400058aa  jmp     short loc_1400058C3
0x1400058ac  mov     r9, rcx; unsigned __int16 *
0x1400058af  mov     [rsp+278h+lpBuffer], rax
0x1400058b4  mov     rcx, r14; this
0x1400058b7  lea     r8, aHsP; "%hs!%p: "
0x1400058be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400058c3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400058ca  mov     r14, rax
0x1400058cd  test    r9, r9
0x1400058d0  jz      short loc_1400058E7
0x1400058d2  lea     r8, aCallerP; "(caller: %p) "
0x1400058d9  mov     rdx, rsi; unsigned __int16 *
0x1400058dc  mov     rcx, rax; this
0x1400058df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400058e4  mov     r14, rax
0x1400058e7  call    cs:__imp_GetCurrentThreadId
0x1400058ed  lea     rcx, [rsp+278h+Buffer]
0x1400058f2  mov     r9, rdi; unsigned __int16 *
0x1400058f5  mov     [rsp+278h+var_240], rcx
0x1400058fa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140005901  mov     dword ptr [rsp+278h+Arguments], ebp
0x140005905  mov     rdx, rsi; unsigned __int16 *
0x140005908  mov     [rsp+278h+nSize], eax
0x14000590c  mov     rcx, r14; this
0x14000590f  mov     eax, [rbx+44h]
0x140005912  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005916  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000591b  cmp     [rbx+18h], r15
0x14000591f  jnz     short loc_140005931
0x140005921  cmp     [rbx+48h], r15
0x140005925  jnz     short loc_140005931
0x140005927  cmp     [rbx+30h], r15
0x14000592b  jz      loc_1400059C1
0x140005931  lea     r8, asc_140021F08; "    "
0x140005938  mov     rdx, rsi; unsigned __int16 *
0x14000593b  mov     rcx, rax; this
0x14000593e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005943  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005947  test    r9, r9
0x14000594a  jz      short loc_14000595E
0x14000594c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140005953  mov     rdx, rsi; unsigned __int16 *
0x140005956  mov     rcx, rax; this
0x140005959  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000595e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140005962  test    r9, r9
0x140005965  jz      short loc_140005979
0x140005967  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000596e  mov     rdx, rsi; unsigned __int16 *
0x140005971  mov     rcx, rax; this
0x140005974  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005979  mov     rcx, [rbx+28h]
0x14000597d  mov     rdx, rsi; unsigned __int16 *
0x140005980  mov     r9, [rbx+30h]; unsigned __int16 *
0x140005984  test    rcx, rcx
0x140005987  jz      short loc_14000599F
0x140005989  mov     [rsp+278h+lpBuffer], rcx
0x14000598e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005995  mov     rcx, rax; this
0x140005998  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000599d  jmp     short loc_1400059C1
0x14000599f  mov     rcx, rax; this
0x1400059a2  test    r9, r9
0x1400059a5  jz      short loc_1400059B5
0x1400059a7  lea     r8, aHs; "[%hs]\n"
0x1400059ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400059b3  jmp     short loc_1400059C1
0x1400059b5  lea     r8, asc_140021F80; "\n"
0x1400059bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400059c1  xor     eax, eax
0x1400059c3  mov     rcx, [rsp+278h+var_38]
0x1400059cb  xor     rcx, rsp; StackCookie
0x1400059ce  call    __security_check_cookie
0x1400059d3  mov     rbx, [rsp+278h+arg_18]
0x1400059db  add     rsp, 250h
0x1400059e2  pop     r15
0x1400059e4  pop     r14
0x1400059e6  pop     rdi
0x1400059e7  pop     rsi
0x1400059e8  pop     rbp
0x1400059e9  retn
```
