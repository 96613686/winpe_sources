# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800526e4`
- end: `0x18005299a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180050938`
- `0x1800535b4`

## callees

- `0x1800487e0`
- `0x1800491dc`
- `0x1800526e4`
- `0x1800538f8`
- `0x180075010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180052816`
- `KERNEL32!FormatMessageW` at `0x180052816`
- `KERNEL32!GetCurrentThreadId` at `0x180052897`
- `KERNEL32!GetCurrentThreadId` at `0x180052897`

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
          v8 = (const char *)&dword_180080074;
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
0x1800526e4  mov     [rsp+arg_18], rbx
0x1800526e9  push    rbp
0x1800526ea  push    rsi
0x1800526eb  push    rdi
0x1800526ec  push    r14
0x1800526ee  push    r15
0x1800526f0  sub     rsp, 250h
0x1800526f7  mov     rax, cs:__security_cookie
0x1800526fe  xor     rax, rsp
0x180052701  mov     [rsp+278h+var_38], rax
0x180052709  xor     r15d, r15d
0x18005270c  mov     rbx, r8
0x18005270f  mov     rsi, rdx
0x180052712  mov     r14, rcx
0x180052715  test    rdx, rdx
0x180052718  jz      loc_180052971
0x18005271e  test    rcx, rcx
0x180052721  jz      loc_180052971
0x180052727  mov     rax, cs:g_pfnResultLoggingCallback
0x18005272e  mov     [rcx], r15w
0x180052732  test    rax, rax
0x180052735  jz      short loc_180052758
0x180052737  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005273e  jz      short loc_180052758
0x180052740  mov     r8, rdx
0x180052743  mov     rdx, rcx
0x180052746  mov     rcx, rbx
0x180052749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005274e  cmp     [r14], r15w
0x180052752  jnz     loc_180052971
0x180052758  mov     ecx, [rbx]
0x18005275a  mov     bpl, 8
0x18005275d  test    ecx, ecx
0x18005275f  jz      short loc_1800527AA
0x180052761  sub     ecx, 1
0x180052764  jz      short loc_180052792
0x180052766  sub     ecx, 1
0x180052769  jz      short loc_180052782
0x18005276b  cmp     ecx, 1
0x18005276e  jz      short loc_180052779
0x180052770  lea     rdi, dword_180080074
0x180052777  jmp     short loc_1800527B1
0x180052779  lea     rdi, aFailfast; "FailFast"
0x180052780  jmp     short loc_1800527B1
0x180052782  lea     rax, aLoghr; "LogHr"
0x180052789  lea     rdi, aLognt; "LogNt"
0x180052790  jmp     short loc_1800527A0
0x180052792  lea     rax, aReturnhr; "ReturnHr"
0x180052799  lea     rdi, aReturnnt; "ReturnNt"
0x1800527a0  test    [rbx+4], bpl
0x1800527a4  cmovz   rdi, rax
0x1800527a8  jmp     short loc_1800527B1
0x1800527aa  lea     rdi, aException; "Exception"
0x1800527b1  xor     edx, edx; Val
0x1800527b3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800527b8  mov     r8d, 200h; Size
0x1800527be  call    memset_0
0x1800527c3  test    [rbx+4], bpl
0x1800527c7  jz      short loc_1800527EC
0x1800527c9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800527d0  mov     ebp, [rbx+0Ch]
0x1800527d3  test    rax, rax
0x1800527d6  jz      short loc_18005281C
0x1800527d8  mov     r8d, 100h
0x1800527de  lea     rdx, [rsp+278h+Buffer]
0x1800527e3  mov     ecx, ebp
0x1800527e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527ea  jmp     short loc_18005281C
0x1800527ec  mov     ebp, [rbx+8]
0x1800527ef  lea     rax, [rsp+278h+Buffer]
0x1800527f4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800527f9  mov     r8d, ebp; dwMessageId
0x1800527fc  mov     [rsp+278h+nSize], 100h; nSize
0x180052804  mov     r9d, 400h; dwLanguageId
0x18005280a  xor     edx, edx; lpSource
0x18005280c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180052811  mov     ecx, 1200h; dwFlags
0x180052816  call    cs:__imp_FormatMessageW
0x18005281c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180052820  lea     rsi, [r14+rsi*2]
0x180052824  mov     rax, [rbx+88h]
0x18005282b  mov     rdx, rsi; unsigned __int16 *
0x18005282e  mov     rcx, [rbx+80h]
0x180052835  test    r9, r9
0x180052838  jz      short loc_18005285C
0x18005283a  mov     [rsp+278h+Arguments], rax
0x18005283f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180052846  mov     eax, [rbx+40h]
0x180052849  mov     qword ptr [rsp+278h+nSize], rcx
0x18005284e  mov     rcx, r14; this
0x180052851  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180052855  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005285a  jmp     short loc_180052873
0x18005285c  mov     r9, rcx; unsigned __int16 *
0x18005285f  mov     [rsp+278h+lpBuffer], rax
0x180052864  mov     rcx, r14; this
0x180052867  lea     r8, aHsP; "%hs!%p: "
0x18005286e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052873  mov     r9, [rbx+90h]; unsigned __int16 *
0x18005287a  mov     r14, rax
0x18005287d  test    r9, r9
0x180052880  jz      short loc_180052897
0x180052882  lea     r8, aCallerP; "(caller: %p) "
0x180052889  mov     rdx, rsi; unsigned __int16 *
0x18005288c  mov     rcx, rax; this
0x18005288f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052894  mov     r14, rax
0x180052897  call    cs:__imp_GetCurrentThreadId
0x18005289d  lea     rcx, [rsp+278h+Buffer]
0x1800528a2  mov     r9, rdi; unsigned __int16 *
0x1800528a5  mov     [rsp+278h+var_240], rcx
0x1800528aa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800528b1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800528b5  mov     rdx, rsi; unsigned __int16 *
0x1800528b8  mov     [rsp+278h+nSize], eax
0x1800528bc  mov     rcx, r14; this
0x1800528bf  mov     eax, [rbx+44h]
0x1800528c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800528c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800528cb  cmp     [rbx+18h], r15
0x1800528cf  jnz     short loc_1800528E1
0x1800528d1  cmp     [rbx+48h], r15
0x1800528d5  jnz     short loc_1800528E1
0x1800528d7  cmp     [rbx+30h], r15
0x1800528db  jz      loc_180052971
0x1800528e1  lea     r8, asc_180080D78; "    "
0x1800528e8  mov     rdx, rsi; unsigned __int16 *
0x1800528eb  mov     rcx, rax; this
0x1800528ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800528f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800528f7  test    r9, r9
0x1800528fa  jz      short loc_18005290E
0x1800528fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180052903  mov     rdx, rsi; unsigned __int16 *
0x180052906  mov     rcx, rax; this
0x180052909  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005290e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180052912  test    r9, r9
0x180052915  jz      short loc_180052929
0x180052917  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18005291e  mov     rdx, rsi; unsigned __int16 *
0x180052921  mov     rcx, rax; this
0x180052924  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052929  mov     rcx, [rbx+28h]
0x18005292d  mov     rdx, rsi; unsigned __int16 *
0x180052930  mov     r9, [rbx+30h]; unsigned __int16 *
0x180052934  test    rcx, rcx
0x180052937  jz      short loc_18005294F
0x180052939  mov     [rsp+278h+lpBuffer], rcx
0x18005293e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180052945  mov     rcx, rax; this
0x180052948  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005294d  jmp     short loc_180052971
0x18005294f  mov     rcx, rax; this
0x180052952  test    r9, r9
0x180052955  jz      short loc_180052965
0x180052957  lea     r8, aHs; "[%hs]\n"
0x18005295e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052963  jmp     short loc_180052971
0x180052965  lea     r8, asc_180080DF0; "\n"
0x18005296c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052971  xor     eax, eax
0x180052973  mov     rcx, [rsp+278h+var_38]
0x18005297b  xor     rcx, rsp; StackCookie
0x18005297e  call    __security_check_cookie
0x180052983  mov     rbx, [rsp+278h+arg_18]
0x18005298b  add     rsp, 250h
0x180052992  pop     r15
0x180052994  pop     r14
0x180052996  pop     rdi
0x180052997  pop     rsi
0x180052998  pop     rbp
0x180052999  retn
```
