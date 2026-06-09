# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005f94`
- end: `0x18000624a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004314`
- `0x180006b94`
- `0x180007210`
- `0x18000a180`

## callees

- `0x1800020c0`
- `0x180002b28`
- `0x180005f94`
- `0x180006e94`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006147`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006147`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800060c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800060c6`

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
          v7 = (const char *)&byte_180019E80;
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
0x180005f94  mov     [rsp+arg_18], rbx
0x180005f99  push    rbp
0x180005f9a  push    rsi
0x180005f9b  push    rdi
0x180005f9c  push    r14
0x180005f9e  push    r15
0x180005fa0  sub     rsp, 250h
0x180005fa7  mov     rax, cs:__security_cookie
0x180005fae  xor     rax, rsp
0x180005fb1  mov     [rsp+278h+var_38], rax
0x180005fb9  mov     rbx, r8
0x180005fbc  mov     rsi, rdx
0x180005fbf  mov     r14, rcx
0x180005fc2  xor     r15d, r15d
0x180005fc5  test    rdx, rdx
0x180005fc8  jz      loc_180006221
0x180005fce  test    rcx, rcx
0x180005fd1  jz      loc_180006221
0x180005fd7  mov     [rcx], r15w
0x180005fdb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005fe2  test    rax, rax
0x180005fe5  jz      short loc_180006008
0x180005fe7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005fee  jz      short loc_180006008
0x180005ff0  mov     r8, rdx
0x180005ff3  mov     rdx, rcx
0x180005ff6  mov     rcx, rbx
0x180005ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ffe  cmp     [r14], r15w
0x180006002  jnz     loc_180006221
0x180006008  mov     ecx, [rbx]
0x18000600a  mov     bpl, 8
0x18000600d  test    ecx, ecx
0x18000600f  jz      short loc_18000605A
0x180006011  sub     ecx, 1
0x180006014  jz      short loc_180006042
0x180006016  sub     ecx, 1
0x180006019  jz      short loc_180006032
0x18000601b  cmp     ecx, 1
0x18000601e  jz      short loc_180006029
0x180006020  lea     rdi, byte_180019E80
0x180006027  jmp     short loc_180006061
0x180006029  lea     rdi, aFailfast; "FailFast"
0x180006030  jmp     short loc_180006061
0x180006032  lea     rax, aLoghr; "LogHr"
0x180006039  lea     rdi, aLognt; "LogNt"
0x180006040  jmp     short loc_180006050
0x180006042  lea     rax, aReturnhr; "ReturnHr"
0x180006049  lea     rdi, aReturnnt; "ReturnNt"
0x180006050  test    [rbx+4], bpl
0x180006054  cmovz   rdi, rax
0x180006058  jmp     short loc_180006061
0x18000605a  lea     rdi, aException; "Exception"
0x180006061  xor     edx, edx; Val
0x180006063  mov     r8d, 200h; Size
0x180006069  lea     rcx, [rsp+278h+Buffer]; void *
0x18000606e  call    memset_0
0x180006073  test    [rbx+4], bpl
0x180006077  jz      short loc_18000609C
0x180006079  mov     ebp, [rbx+0Ch]
0x18000607c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006083  test    rax, rax
0x180006086  jz      short loc_1800060CC
0x180006088  mov     r8d, 100h
0x18000608e  lea     rdx, [rsp+278h+Buffer]
0x180006093  mov     ecx, ebp
0x180006095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000609a  jmp     short loc_1800060CC
0x18000609c  mov     ebp, [rbx+8]
0x18000609f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800060a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800060ac  lea     rax, [rsp+278h+Buffer]
0x1800060b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800060b6  mov     r9d, 400h; dwLanguageId
0x1800060bc  mov     r8d, ebp; dwMessageId
0x1800060bf  xor     edx, edx; lpSource
0x1800060c1  mov     ecx, 1200h; dwFlags
0x1800060c6  call    cs:__imp_FormatMessageW
0x1800060cc  lea     rsi, [r14+rsi*2]
0x1800060d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800060d4  mov     rax, [rbx+88h]
0x1800060db  mov     rcx, [rbx+80h]
0x1800060e2  mov     rdx, rsi; unsigned __int16 *
0x1800060e5  test    r9, r9
0x1800060e8  jz      short loc_18000610C
0x1800060ea  mov     [rsp+278h+Arguments], rax
0x1800060ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800060f4  mov     eax, [rbx+40h]
0x1800060f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800060fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006102  mov     rcx, r14; this
0x180006105  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000610a  jmp     short loc_180006123
0x18000610c  mov     [rsp+278h+lpBuffer], rax
0x180006111  mov     r9, rcx; unsigned __int16 *
0x180006114  lea     r8, aHsP; "%hs!%p: "
0x18000611b  mov     rcx, r14; this
0x18000611e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006123  mov     r14, rax
0x180006126  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000612d  test    r9, r9
0x180006130  jz      short loc_180006147
0x180006132  lea     r8, aCallerP; "(caller: %p) "
0x180006139  mov     rdx, rsi; unsigned __int16 *
0x18000613c  mov     rcx, rax; this
0x18000613f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006144  mov     r14, rax
0x180006147  call    cs:__imp_GetCurrentThreadId
0x18000614d  lea     rcx, [rsp+278h+Buffer]
0x180006152  mov     [rsp+278h+var_240], rcx
0x180006157  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000615b  mov     [rsp+278h+nSize], eax
0x18000615f  mov     eax, [rbx+44h]
0x180006162  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006166  mov     r9, rdi; unsigned __int16 *
0x180006169  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006170  mov     rdx, rsi; unsigned __int16 *
0x180006173  mov     rcx, r14; this
0x180006176  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000617b  cmp     [rbx+18h], r15
0x18000617f  jnz     short loc_180006191
0x180006181  cmp     [rbx+48h], r15
0x180006185  jnz     short loc_180006191
0x180006187  cmp     [rbx+30h], r15
0x18000618b  jz      loc_180006221
0x180006191  lea     r8, asc_180019F88; "    "
0x180006198  mov     rdx, rsi; unsigned __int16 *
0x18000619b  mov     rcx, rax; this
0x18000619e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800061a7  test    r9, r9
0x1800061aa  jz      short loc_1800061BE
0x1800061ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800061b3  mov     rdx, rsi; unsigned __int16 *
0x1800061b6  mov     rcx, rax; this
0x1800061b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800061c2  test    r9, r9
0x1800061c5  jz      short loc_1800061D9
0x1800061c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800061ce  mov     rdx, rsi; unsigned __int16 *
0x1800061d1  mov     rcx, rax; this
0x1800061d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061d9  mov     rcx, [rbx+28h]
0x1800061dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800061e1  mov     rdx, rsi; unsigned __int16 *
0x1800061e4  test    rcx, rcx
0x1800061e7  jz      short loc_1800061FF
0x1800061e9  mov     [rsp+278h+lpBuffer], rcx
0x1800061ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800061f5  mov     rcx, rax; this
0x1800061f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800061fd  jmp     short loc_180006221
0x1800061ff  mov     rcx, rax; this
0x180006202  test    r9, r9
0x180006205  jz      short loc_180006215
0x180006207  lea     r8, aHs; "[%hs]\n"
0x18000620e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006213  jmp     short loc_180006221
0x180006215  lea     r8, asc_18001A000; "\n"
0x18000621c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006221  xor     eax, eax
0x180006223  mov     rcx, [rsp+278h+var_38]
0x18000622b  xor     rcx, rsp; StackCookie
0x18000622e  call    __security_check_cookie
0x180006233  mov     rbx, [rsp+278h+arg_18]
0x18000623b  add     rsp, 250h
0x180006242  pop     r15
0x180006244  pop     r14
0x180006246  pop     rdi
0x180006247  pop     rsi
0x180006248  pop     rbp
0x180006249  retn
```
