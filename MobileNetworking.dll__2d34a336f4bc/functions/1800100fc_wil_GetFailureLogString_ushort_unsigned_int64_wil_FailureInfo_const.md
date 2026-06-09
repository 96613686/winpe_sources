# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800100fc`
- end: `0x1800103b2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f5d0`
- `0x1800107d0`

## callees

- `0x180009850`
- `0x18000a19a`
- `0x1800100fc`
- `0x180010ad0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800102af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800102af`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001022e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001022e`

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
          v8 = (const char *)&qword_1800158E8;
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
0x1800100fc  mov     [rsp+arg_18], rbx
0x180010101  push    rbp
0x180010102  push    rsi
0x180010103  push    rdi
0x180010104  push    r14
0x180010106  push    r15
0x180010108  sub     rsp, 250h
0x18001010f  mov     rax, cs:__security_cookie
0x180010116  xor     rax, rsp
0x180010119  mov     [rsp+278h+var_38], rax
0x180010121  xor     r15d, r15d
0x180010124  mov     rbx, r8
0x180010127  mov     rsi, rdx
0x18001012a  mov     r14, rcx
0x18001012d  test    rdx, rdx
0x180010130  jz      loc_180010389
0x180010136  test    rcx, rcx
0x180010139  jz      loc_180010389
0x18001013f  mov     rax, cs:g_pfnResultLoggingCallback
0x180010146  mov     [rcx], r15w
0x18001014a  test    rax, rax
0x18001014d  jz      short loc_180010170
0x18001014f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180010156  jz      short loc_180010170
0x180010158  mov     r8, rdx
0x18001015b  mov     rdx, rcx
0x18001015e  mov     rcx, rbx
0x180010161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010166  cmp     [r14], r15w
0x18001016a  jnz     loc_180010389
0x180010170  mov     ecx, [rbx]
0x180010172  mov     bpl, 8
0x180010175  test    ecx, ecx
0x180010177  jz      short loc_1800101C2
0x180010179  sub     ecx, 1
0x18001017c  jz      short loc_1800101AA
0x18001017e  sub     ecx, 1
0x180010181  jz      short loc_18001019A
0x180010183  cmp     ecx, 1
0x180010186  jz      short loc_180010191
0x180010188  lea     rdi, qword_1800158E8
0x18001018f  jmp     short loc_1800101C9
0x180010191  lea     rdi, aFailfast; "FailFast"
0x180010198  jmp     short loc_1800101C9
0x18001019a  lea     rax, aLoghr; "LogHr"
0x1800101a1  lea     rdi, aLognt; "LogNt"
0x1800101a8  jmp     short loc_1800101B8
0x1800101aa  lea     rax, aReturnhr; "ReturnHr"
0x1800101b1  lea     rdi, aReturnnt; "ReturnNt"
0x1800101b8  test    [rbx+4], bpl
0x1800101bc  cmovz   rdi, rax
0x1800101c0  jmp     short loc_1800101C9
0x1800101c2  lea     rdi, aException; "Exception"
0x1800101c9  xor     edx, edx; Val
0x1800101cb  lea     rcx, [rsp+278h+Buffer]; void *
0x1800101d0  mov     r8d, 200h; Size
0x1800101d6  call    memset_0
0x1800101db  test    [rbx+4], bpl
0x1800101df  jz      short loc_180010204
0x1800101e1  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800101e8  mov     ebp, [rbx+0Ch]
0x1800101eb  test    rax, rax
0x1800101ee  jz      short loc_180010234
0x1800101f0  mov     r8d, 100h
0x1800101f6  lea     rdx, [rsp+278h+Buffer]
0x1800101fb  mov     ecx, ebp
0x1800101fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010202  jmp     short loc_180010234
0x180010204  mov     ebp, [rbx+8]
0x180010207  lea     rax, [rsp+278h+Buffer]
0x18001020c  mov     [rsp+278h+Arguments], r15; Arguments
0x180010211  mov     r8d, ebp; dwMessageId
0x180010214  mov     [rsp+278h+nSize], 100h; nSize
0x18001021c  mov     r9d, 400h; dwLanguageId
0x180010222  xor     edx, edx; lpSource
0x180010224  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180010229  mov     ecx, 1200h; dwFlags
0x18001022e  call    cs:__imp_FormatMessageW
0x180010234  mov     r9, [rbx+38h]; unsigned __int16 *
0x180010238  lea     rsi, [r14+rsi*2]
0x18001023c  mov     rax, [rbx+88h]
0x180010243  mov     rdx, rsi; unsigned __int16 *
0x180010246  mov     rcx, [rbx+80h]
0x18001024d  test    r9, r9
0x180010250  jz      short loc_180010274
0x180010252  mov     [rsp+278h+Arguments], rax
0x180010257  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001025e  mov     eax, [rbx+40h]
0x180010261  mov     qword ptr [rsp+278h+nSize], rcx
0x180010266  mov     rcx, r14; this
0x180010269  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001026d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010272  jmp     short loc_18001028B
0x180010274  mov     r9, rcx; unsigned __int16 *
0x180010277  mov     [rsp+278h+lpBuffer], rax
0x18001027c  mov     rcx, r14; this
0x18001027f  lea     r8, aHsP; "%hs!%p: "
0x180010286  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001028b  mov     r9, [rbx+90h]; unsigned __int16 *
0x180010292  mov     r14, rax
0x180010295  test    r9, r9
0x180010298  jz      short loc_1800102AF
0x18001029a  lea     r8, aCallerP; "(caller: %p) "
0x1800102a1  mov     rdx, rsi; unsigned __int16 *
0x1800102a4  mov     rcx, rax; this
0x1800102a7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800102ac  mov     r14, rax
0x1800102af  call    cs:__imp_GetCurrentThreadId
0x1800102b5  lea     rcx, [rsp+278h+Buffer]
0x1800102ba  mov     r9, rdi; unsigned __int16 *
0x1800102bd  mov     [rsp+278h+var_240], rcx
0x1800102c2  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800102c9  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800102cd  mov     rdx, rsi; unsigned __int16 *
0x1800102d0  mov     [rsp+278h+nSize], eax
0x1800102d4  mov     rcx, r14; this
0x1800102d7  mov     eax, [rbx+44h]
0x1800102da  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800102de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800102e3  cmp     [rbx+18h], r15
0x1800102e7  jnz     short loc_1800102F9
0x1800102e9  cmp     [rbx+48h], r15
0x1800102ed  jnz     short loc_1800102F9
0x1800102ef  cmp     [rbx+30h], r15
0x1800102f3  jz      loc_180010389
0x1800102f9  lea     r8, asc_1800159D8; "    "
0x180010300  mov     rdx, rsi; unsigned __int16 *
0x180010303  mov     rcx, rax; this
0x180010306  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001030b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001030f  test    r9, r9
0x180010312  jz      short loc_180010326
0x180010314  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001031b  mov     rdx, rsi; unsigned __int16 *
0x18001031e  mov     rcx, rax; this
0x180010321  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010326  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001032a  test    r9, r9
0x18001032d  jz      short loc_180010341
0x18001032f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180010336  mov     rdx, rsi; unsigned __int16 *
0x180010339  mov     rcx, rax; this
0x18001033c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010341  mov     rcx, [rbx+28h]
0x180010345  mov     rdx, rsi; unsigned __int16 *
0x180010348  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001034c  test    rcx, rcx
0x18001034f  jz      short loc_180010367
0x180010351  mov     [rsp+278h+lpBuffer], rcx
0x180010356  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001035d  mov     rcx, rax; this
0x180010360  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010365  jmp     short loc_180010389
0x180010367  mov     rcx, rax; this
0x18001036a  test    r9, r9
0x18001036d  jz      short loc_18001037D
0x18001036f  lea     r8, aHs; "[%hs]\n"
0x180010376  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001037b  jmp     short loc_180010389
0x18001037d  lea     r8, asc_180015A50; "\n"
0x180010384  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010389  xor     eax, eax
0x18001038b  mov     rcx, [rsp+278h+var_38]
0x180010393  xor     rcx, rsp; StackCookie
0x180010396  call    __security_check_cookie
0x18001039b  mov     rbx, [rsp+278h+arg_18]
0x1800103a3  add     rsp, 250h
0x1800103aa  pop     r15
0x1800103ac  pop     r14
0x1800103ae  pop     rdi
0x1800103af  pop     rsi
0x1800103b0  pop     rbp
0x1800103b1  retn
```
