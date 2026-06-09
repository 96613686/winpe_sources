# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007144`
- end: `0x1800073fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180004b10`
- `0x180004d90`
- `0x180007c10`
- `0x18000aa20`
- `0x18001fb60`
- `0x18001fc94`

## callees

- `0x1800038f0`
- `0x1800046a0`
- `0x180007144`
- `0x180007f10`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007276`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007276`

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
          v7 = (const char *)&word_18002377A;
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
0x180007144  mov     [rsp+arg_18], rbx
0x180007149  push    rbp
0x18000714a  push    rsi
0x18000714b  push    rdi
0x18000714c  push    r14
0x18000714e  push    r15
0x180007150  sub     rsp, 250h
0x180007157  mov     rax, cs:__security_cookie
0x18000715e  xor     rax, rsp
0x180007161  mov     [rsp+278h+var_38], rax
0x180007169  mov     rbx, r8
0x18000716c  mov     rsi, rdx
0x18000716f  mov     r14, rcx
0x180007172  xor     r15d, r15d
0x180007175  test    rdx, rdx
0x180007178  jz      loc_1800073D1
0x18000717e  test    rcx, rcx
0x180007181  jz      loc_1800073D1
0x180007187  mov     [rcx], r15w
0x18000718b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007192  test    rax, rax
0x180007195  jz      short loc_1800071B8
0x180007197  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000719e  jz      short loc_1800071B8
0x1800071a0  mov     r8, rdx
0x1800071a3  mov     rdx, rcx
0x1800071a6  mov     rcx, rbx
0x1800071a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ae  cmp     [r14], r15w
0x1800071b2  jnz     loc_1800073D1
0x1800071b8  mov     ecx, [rbx]
0x1800071ba  mov     bpl, 8
0x1800071bd  test    ecx, ecx
0x1800071bf  jz      short loc_18000720A
0x1800071c1  sub     ecx, 1
0x1800071c4  jz      short loc_1800071F2
0x1800071c6  sub     ecx, 1
0x1800071c9  jz      short loc_1800071E2
0x1800071cb  cmp     ecx, 1
0x1800071ce  jz      short loc_1800071D9
0x1800071d0  lea     rdi, word_18002377A
0x1800071d7  jmp     short loc_180007211
0x1800071d9  lea     rdi, aFailfast; "FailFast"
0x1800071e0  jmp     short loc_180007211
0x1800071e2  lea     rax, aLoghr; "LogHr"
0x1800071e9  lea     rdi, aLognt; "LogNt"
0x1800071f0  jmp     short loc_180007200
0x1800071f2  lea     rax, aReturnhr; "ReturnHr"
0x1800071f9  lea     rdi, aReturnnt; "ReturnNt"
0x180007200  test    [rbx+4], bpl
0x180007204  cmovz   rdi, rax
0x180007208  jmp     short loc_180007211
0x18000720a  lea     rdi, aException; "Exception"
0x180007211  xor     edx, edx; Val
0x180007213  mov     r8d, 200h; Size
0x180007219  lea     rcx, [rsp+278h+Buffer]; void *
0x18000721e  call    memset_0
0x180007223  test    [rbx+4], bpl
0x180007227  jz      short loc_18000724C
0x180007229  mov     ebp, [rbx+0Ch]
0x18000722c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007233  test    rax, rax
0x180007236  jz      short loc_18000727C
0x180007238  mov     r8d, 100h
0x18000723e  lea     rdx, [rsp+278h+Buffer]
0x180007243  mov     ecx, ebp
0x180007245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000724a  jmp     short loc_18000727C
0x18000724c  mov     ebp, [rbx+8]
0x18000724f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007254  mov     [rsp+278h+nSize], 100h; nSize
0x18000725c  lea     rax, [rsp+278h+Buffer]
0x180007261  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007266  mov     r9d, 400h; dwLanguageId
0x18000726c  mov     r8d, ebp; dwMessageId
0x18000726f  xor     edx, edx; lpSource
0x180007271  mov     ecx, 1200h; dwFlags
0x180007276  call    cs:__imp_FormatMessageW
0x18000727c  lea     rsi, [r14+rsi*2]
0x180007280  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007284  mov     rax, [rbx+88h]
0x18000728b  mov     rcx, [rbx+80h]
0x180007292  mov     rdx, rsi; unsigned __int16 *
0x180007295  test    r9, r9
0x180007298  jz      short loc_1800072BC
0x18000729a  mov     [rsp+278h+Arguments], rax
0x18000729f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800072a4  mov     eax, [rbx+40h]
0x1800072a7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800072ab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800072b2  mov     rcx, r14; this
0x1800072b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800072ba  jmp     short loc_1800072D3
0x1800072bc  mov     [rsp+278h+lpBuffer], rax
0x1800072c1  mov     r9, rcx; unsigned __int16 *
0x1800072c4  lea     r8, aHsP; "%hs!%p: "
0x1800072cb  mov     rcx, r14; this
0x1800072ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800072d3  mov     r14, rax
0x1800072d6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800072dd  test    r9, r9
0x1800072e0  jz      short loc_1800072F7
0x1800072e2  lea     r8, aCallerP; "(caller: %p) "
0x1800072e9  mov     rdx, rsi; unsigned __int16 *
0x1800072ec  mov     rcx, rax; this
0x1800072ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800072f4  mov     r14, rax
0x1800072f7  call    cs:__imp_GetCurrentThreadId
0x1800072fd  lea     rcx, [rsp+278h+Buffer]
0x180007302  mov     [rsp+278h+var_240], rcx
0x180007307  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000730b  mov     [rsp+278h+nSize], eax
0x18000730f  mov     eax, [rbx+44h]
0x180007312  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007316  mov     r9, rdi; unsigned __int16 *
0x180007319  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007320  mov     rdx, rsi; unsigned __int16 *
0x180007323  mov     rcx, r14; this
0x180007326  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000732b  cmp     [rbx+18h], r15
0x18000732f  jnz     short loc_180007341
0x180007331  cmp     [rbx+48h], r15
0x180007335  jnz     short loc_180007341
0x180007337  cmp     [rbx+30h], r15
0x18000733b  jz      loc_1800073D1
0x180007341  lea     r8, asc_180023888; "    "
0x180007348  mov     rdx, rsi; unsigned __int16 *
0x18000734b  mov     rcx, rax; this
0x18000734e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007353  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007357  test    r9, r9
0x18000735a  jz      short loc_18000736E
0x18000735c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007363  mov     rdx, rsi; unsigned __int16 *
0x180007366  mov     rcx, rax; this
0x180007369  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000736e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007372  test    r9, r9
0x180007375  jz      short loc_180007389
0x180007377  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000737e  mov     rdx, rsi; unsigned __int16 *
0x180007381  mov     rcx, rax; this
0x180007384  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007389  mov     rcx, [rbx+28h]
0x18000738d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007391  mov     rdx, rsi; unsigned __int16 *
0x180007394  test    rcx, rcx
0x180007397  jz      short loc_1800073AF
0x180007399  mov     [rsp+278h+lpBuffer], rcx
0x18000739e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800073a5  mov     rcx, rax; this
0x1800073a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800073ad  jmp     short loc_1800073D1
0x1800073af  mov     rcx, rax; this
0x1800073b2  test    r9, r9
0x1800073b5  jz      short loc_1800073C5
0x1800073b7  lea     r8, aHs; "[%hs]\n"
0x1800073be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800073c3  jmp     short loc_1800073D1
0x1800073c5  lea     r8, asc_180023900; "\n"
0x1800073cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800073d1  xor     eax, eax
0x1800073d3  mov     rcx, [rsp+278h+var_38]
0x1800073db  xor     rcx, rsp; StackCookie
0x1800073de  call    __security_check_cookie
0x1800073e3  mov     rbx, [rsp+278h+arg_18]
0x1800073eb  add     rsp, 250h
0x1800073f2  pop     r15
0x1800073f4  pop     r14
0x1800073f6  pop     rdi
0x1800073f7  pop     rsi
0x1800073f8  pop     rbp
0x1800073f9  retn
```
