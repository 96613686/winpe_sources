# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007684`
- end: `0x18000793a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005580`
- `0x180008378`
- `0x180008a58`
- `0x18000bbc0`

## callees

- `0x1800028d0`
- `0x1800033a0`
- `0x180007684`
- `0x180008678`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800077b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800077b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007837`

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
          v7 = qword_180064FB8;
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
0x180007684  mov     [rsp+arg_18], rbx
0x180007689  push    rbp
0x18000768a  push    rsi
0x18000768b  push    rdi
0x18000768c  push    r14
0x18000768e  push    r15
0x180007690  sub     rsp, 250h
0x180007697  mov     rax, cs:__security_cookie
0x18000769e  xor     rax, rsp
0x1800076a1  mov     [rsp+278h+var_38], rax
0x1800076a9  mov     rbx, r8
0x1800076ac  mov     rsi, rdx
0x1800076af  mov     r14, rcx
0x1800076b2  xor     r15d, r15d
0x1800076b5  test    rdx, rdx
0x1800076b8  jz      loc_180007911
0x1800076be  test    rcx, rcx
0x1800076c1  jz      loc_180007911
0x1800076c7  mov     [rcx], r15w
0x1800076cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800076d2  test    rax, rax
0x1800076d5  jz      short loc_1800076F8
0x1800076d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800076de  jz      short loc_1800076F8
0x1800076e0  mov     r8, rdx
0x1800076e3  mov     rdx, rcx
0x1800076e6  mov     rcx, rbx
0x1800076e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ee  cmp     [r14], r15w
0x1800076f2  jnz     loc_180007911
0x1800076f8  mov     ecx, [rbx]
0x1800076fa  mov     bpl, 8
0x1800076fd  test    ecx, ecx
0x1800076ff  jz      short loc_18000774A
0x180007701  sub     ecx, 1
0x180007704  jz      short loc_180007732
0x180007706  sub     ecx, 1
0x180007709  jz      short loc_180007722
0x18000770b  cmp     ecx, 1
0x18000770e  jz      short loc_180007719
0x180007710  lea     rdi, qword_180064FB8
0x180007717  jmp     short loc_180007751
0x180007719  lea     rdi, aFailfast; "FailFast"
0x180007720  jmp     short loc_180007751
0x180007722  lea     rax, aLoghr; "LogHr"
0x180007729  lea     rdi, aLognt; "LogNt"
0x180007730  jmp     short loc_180007740
0x180007732  lea     rax, aReturnhr; "ReturnHr"
0x180007739  lea     rdi, aReturnnt; "ReturnNt"
0x180007740  test    [rbx+4], bpl
0x180007744  cmovz   rdi, rax
0x180007748  jmp     short loc_180007751
0x18000774a  lea     rdi, aException; "Exception"
0x180007751  xor     edx, edx; Val
0x180007753  mov     r8d, 200h; Size
0x180007759  lea     rcx, [rsp+278h+Buffer]; void *
0x18000775e  call    memset_0
0x180007763  test    [rbx+4], bpl
0x180007767  jz      short loc_18000778C
0x180007769  mov     ebp, [rbx+0Ch]
0x18000776c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007773  test    rax, rax
0x180007776  jz      short loc_1800077BC
0x180007778  mov     r8d, 100h
0x18000777e  lea     rdx, [rsp+278h+Buffer]
0x180007783  mov     ecx, ebp
0x180007785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000778a  jmp     short loc_1800077BC
0x18000778c  mov     ebp, [rbx+8]
0x18000778f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007794  mov     [rsp+278h+nSize], 100h; nSize
0x18000779c  lea     rax, [rsp+278h+Buffer]
0x1800077a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800077a6  mov     r9d, 400h; dwLanguageId
0x1800077ac  mov     r8d, ebp; dwMessageId
0x1800077af  xor     edx, edx; lpSource
0x1800077b1  mov     ecx, 1200h; dwFlags
0x1800077b6  call    cs:__imp_FormatMessageW
0x1800077bc  lea     rsi, [r14+rsi*2]
0x1800077c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800077c4  mov     rax, [rbx+88h]
0x1800077cb  mov     rcx, [rbx+80h]
0x1800077d2  mov     rdx, rsi; unsigned __int16 *
0x1800077d5  test    r9, r9
0x1800077d8  jz      short loc_1800077FC
0x1800077da  mov     [rsp+278h+Arguments], rax
0x1800077df  mov     qword ptr [rsp+278h+nSize], rcx
0x1800077e4  mov     eax, [rbx+40h]
0x1800077e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800077eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800077f2  mov     rcx, r14; this
0x1800077f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800077fa  jmp     short loc_180007813
0x1800077fc  mov     [rsp+278h+lpBuffer], rax
0x180007801  mov     r9, rcx; unsigned __int16 *
0x180007804  lea     r8, aHsP; "%hs!%p: "
0x18000780b  mov     rcx, r14; this
0x18000780e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007813  mov     r14, rax
0x180007816  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000781d  test    r9, r9
0x180007820  jz      short loc_180007837
0x180007822  lea     r8, aCallerP; "(caller: %p) "
0x180007829  mov     rdx, rsi; unsigned __int16 *
0x18000782c  mov     rcx, rax; this
0x18000782f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007834  mov     r14, rax
0x180007837  call    cs:__imp_GetCurrentThreadId
0x18000783d  lea     rcx, [rsp+278h+Buffer]
0x180007842  mov     [rsp+278h+var_240], rcx
0x180007847  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000784b  mov     [rsp+278h+nSize], eax
0x18000784f  mov     eax, [rbx+44h]
0x180007852  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007856  mov     r9, rdi; unsigned __int16 *
0x180007859  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007860  mov     rdx, rsi; unsigned __int16 *
0x180007863  mov     rcx, r14; this
0x180007866  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000786b  cmp     [rbx+18h], r15
0x18000786f  jnz     short loc_180007881
0x180007871  cmp     [rbx+48h], r15
0x180007875  jnz     short loc_180007881
0x180007877  cmp     [rbx+30h], r15
0x18000787b  jz      loc_180007911
0x180007881  lea     r8, asc_180063988; "    "
0x180007888  mov     rdx, rsi; unsigned __int16 *
0x18000788b  mov     rcx, rax; this
0x18000788e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007893  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007897  test    r9, r9
0x18000789a  jz      short loc_1800078AE
0x18000789c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800078a3  mov     rdx, rsi; unsigned __int16 *
0x1800078a6  mov     rcx, rax; this
0x1800078a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800078ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800078b2  test    r9, r9
0x1800078b5  jz      short loc_1800078C9
0x1800078b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800078be  mov     rdx, rsi; unsigned __int16 *
0x1800078c1  mov     rcx, rax; this
0x1800078c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800078c9  mov     rcx, [rbx+28h]
0x1800078cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800078d1  mov     rdx, rsi; unsigned __int16 *
0x1800078d4  test    rcx, rcx
0x1800078d7  jz      short loc_1800078EF
0x1800078d9  mov     [rsp+278h+lpBuffer], rcx
0x1800078de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800078e5  mov     rcx, rax; this
0x1800078e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800078ed  jmp     short loc_180007911
0x1800078ef  mov     rcx, rax; this
0x1800078f2  test    r9, r9
0x1800078f5  jz      short loc_180007905
0x1800078f7  lea     r8, aHs; "[%hs]\n"
0x1800078fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007903  jmp     short loc_180007911
0x180007905  lea     r8, asc_180063A00; "\n"
0x18000790c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007911  xor     eax, eax
0x180007913  mov     rcx, [rsp+278h+var_38]
0x18000791b  xor     rcx, rsp; StackCookie
0x18000791e  call    __security_check_cookie
0x180007923  mov     rbx, [rsp+278h+arg_18]
0x18000792b  add     rsp, 250h
0x180007932  pop     r15
0x180007934  pop     r14
0x180007936  pop     rdi
0x180007937  pop     rsi
0x180007938  pop     rbp
0x180007939  retn
```
