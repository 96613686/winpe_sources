# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400046a4`
- end: `0x14000495a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x14000249c`
- `0x1400027a4`
- `0x1400059e8`
- `0x1400078c0`
- `0x140009580`
- `0x1400096b4`

## callees

- `0x140001460`
- `0x140001f5c`
- `0x1400046a4`
- `0x140005ce8`
- `0x14000a010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1400047d6`
- `KERNEL32!FormatMessageW` at `0x1400047d6`
- `KERNEL32!GetCurrentThreadId` at `0x140004857`
- `KERNEL32!GetCurrentThreadId` at `0x140004857`

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
          v7 = (const char *)&qword_14000C950;
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
0x1400046a4  mov     [rsp+arg_18], rbx
0x1400046a9  push    rbp
0x1400046aa  push    rsi
0x1400046ab  push    rdi
0x1400046ac  push    r14
0x1400046ae  push    r15
0x1400046b0  sub     rsp, 250h
0x1400046b7  mov     rax, cs:__security_cookie
0x1400046be  xor     rax, rsp
0x1400046c1  mov     [rsp+278h+var_38], rax
0x1400046c9  mov     rbx, r8
0x1400046cc  mov     rsi, rdx
0x1400046cf  mov     r14, rcx
0x1400046d2  xor     r15d, r15d
0x1400046d5  test    rdx, rdx
0x1400046d8  jz      loc_140004931
0x1400046de  test    rcx, rcx
0x1400046e1  jz      loc_140004931
0x1400046e7  mov     [rcx], r15w
0x1400046eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1400046f2  test    rax, rax
0x1400046f5  jz      short loc_140004718
0x1400046f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400046fe  jz      short loc_140004718
0x140004700  mov     r8, rdx
0x140004703  mov     rdx, rcx
0x140004706  mov     rcx, rbx
0x140004709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000470e  cmp     [r14], r15w
0x140004712  jnz     loc_140004931
0x140004718  mov     ecx, [rbx]
0x14000471a  mov     bpl, 8
0x14000471d  test    ecx, ecx
0x14000471f  jz      short loc_14000476A
0x140004721  sub     ecx, 1
0x140004724  jz      short loc_140004752
0x140004726  sub     ecx, 1
0x140004729  jz      short loc_140004742
0x14000472b  cmp     ecx, 1
0x14000472e  jz      short loc_140004739
0x140004730  lea     rdi, qword_14000C950
0x140004737  jmp     short loc_140004771
0x140004739  lea     rdi, aFailfast; "FailFast"
0x140004740  jmp     short loc_140004771
0x140004742  lea     rax, aLoghr; "LogHr"
0x140004749  lea     rdi, aLognt; "LogNt"
0x140004750  jmp     short loc_140004760
0x140004752  lea     rax, aReturnhr; "ReturnHr"
0x140004759  lea     rdi, aReturnnt; "ReturnNt"
0x140004760  test    [rbx+4], bpl
0x140004764  cmovz   rdi, rax
0x140004768  jmp     short loc_140004771
0x14000476a  lea     rdi, aException; "Exception"
0x140004771  xor     edx, edx; Val
0x140004773  mov     r8d, 200h; Size
0x140004779  lea     rcx, [rsp+278h+Buffer]; void *
0x14000477e  call    memset_0
0x140004783  test    [rbx+4], bpl
0x140004787  jz      short loc_1400047AC
0x140004789  mov     ebp, [rbx+0Ch]
0x14000478c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004793  test    rax, rax
0x140004796  jz      short loc_1400047DC
0x140004798  mov     r8d, 100h
0x14000479e  lea     rdx, [rsp+278h+Buffer]
0x1400047a3  mov     ecx, ebp
0x1400047a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047aa  jmp     short loc_1400047DC
0x1400047ac  mov     ebp, [rbx+8]
0x1400047af  mov     [rsp+278h+Arguments], r15; Arguments
0x1400047b4  mov     [rsp+278h+nSize], 100h; nSize
0x1400047bc  lea     rax, [rsp+278h+Buffer]
0x1400047c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400047c6  mov     r9d, 400h; dwLanguageId
0x1400047cc  mov     r8d, ebp; dwMessageId
0x1400047cf  xor     edx, edx; lpSource
0x1400047d1  mov     ecx, 1200h; dwFlags
0x1400047d6  call    cs:__imp_FormatMessageW
0x1400047dc  lea     rsi, [r14+rsi*2]
0x1400047e0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400047e4  mov     rax, [rbx+88h]
0x1400047eb  mov     rcx, [rbx+80h]
0x1400047f2  mov     rdx, rsi; unsigned __int16 *
0x1400047f5  test    r9, r9
0x1400047f8  jz      short loc_14000481C
0x1400047fa  mov     [rsp+278h+Arguments], rax
0x1400047ff  mov     qword ptr [rsp+278h+nSize], rcx
0x140004804  mov     eax, [rbx+40h]
0x140004807  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000480b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004812  mov     rcx, r14; this
0x140004815  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000481a  jmp     short loc_140004833
0x14000481c  mov     [rsp+278h+lpBuffer], rax
0x140004821  mov     r9, rcx; unsigned __int16 *
0x140004824  lea     r8, aHsP; "%hs!%p: "
0x14000482b  mov     rcx, r14; this
0x14000482e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004833  mov     r14, rax
0x140004836  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000483d  test    r9, r9
0x140004840  jz      short loc_140004857
0x140004842  lea     r8, aCallerP; "(caller: %p) "
0x140004849  mov     rdx, rsi; unsigned __int16 *
0x14000484c  mov     rcx, rax; this
0x14000484f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004854  mov     r14, rax
0x140004857  call    cs:__imp_GetCurrentThreadId
0x14000485d  lea     rcx, [rsp+278h+Buffer]
0x140004862  mov     [rsp+278h+var_240], rcx
0x140004867  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000486b  mov     [rsp+278h+nSize], eax
0x14000486f  mov     eax, [rbx+44h]
0x140004872  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004876  mov     r9, rdi; unsigned __int16 *
0x140004879  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004880  mov     rdx, rsi; unsigned __int16 *
0x140004883  mov     rcx, r14; this
0x140004886  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000488b  cmp     [rbx+18h], r15
0x14000488f  jnz     short loc_1400048A1
0x140004891  cmp     [rbx+48h], r15
0x140004895  jnz     short loc_1400048A1
0x140004897  cmp     [rbx+30h], r15
0x14000489b  jz      loc_140004931
0x1400048a1  lea     r8, asc_14000CA70; "    "
0x1400048a8  mov     rdx, rsi; unsigned __int16 *
0x1400048ab  mov     rcx, rax; this
0x1400048ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400048b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400048b7  test    r9, r9
0x1400048ba  jz      short loc_1400048CE
0x1400048bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400048c3  mov     rdx, rsi; unsigned __int16 *
0x1400048c6  mov     rcx, rax; this
0x1400048c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400048ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400048d2  test    r9, r9
0x1400048d5  jz      short loc_1400048E9
0x1400048d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400048de  mov     rdx, rsi; unsigned __int16 *
0x1400048e1  mov     rcx, rax; this
0x1400048e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400048e9  mov     rcx, [rbx+28h]
0x1400048ed  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400048f1  mov     rdx, rsi; unsigned __int16 *
0x1400048f4  test    rcx, rcx
0x1400048f7  jz      short loc_14000490F
0x1400048f9  mov     [rsp+278h+lpBuffer], rcx
0x1400048fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004905  mov     rcx, rax; this
0x140004908  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000490d  jmp     short loc_140004931
0x14000490f  mov     rcx, rax; this
0x140004912  test    r9, r9
0x140004915  jz      short loc_140004925
0x140004917  lea     r8, aHs; "[%hs]\n"
0x14000491e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004923  jmp     short loc_140004931
0x140004925  lea     r8, asc_14000CAE8; "\n"
0x14000492c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004931  xor     eax, eax
0x140004933  mov     rcx, [rsp+278h+var_38]
0x14000493b  xor     rcx, rsp; StackCookie
0x14000493e  call    __security_check_cookie
0x140004943  mov     rbx, [rsp+278h+arg_18]
0x14000494b  add     rsp, 250h
0x140004952  pop     r15
0x140004954  pop     r14
0x140004956  pop     rdi
0x140004957  pop     rsi
0x140004958  pop     rbp
0x140004959  retn
```
