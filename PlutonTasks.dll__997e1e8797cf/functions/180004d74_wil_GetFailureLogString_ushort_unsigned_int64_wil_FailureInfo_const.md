# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004d74`
- end: `0x18000502a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180005940`
- `0x180008ef0`

## callees

- `0x180001e00`
- `0x180002858`
- `0x180004d74`
- `0x180005c3c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f27`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ea6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ea6`

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
          v7 = (const char *)&byte_18000B8A0;
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
0x180004d74  mov     [rsp+arg_18], rbx
0x180004d79  push    rbp
0x180004d7a  push    rsi
0x180004d7b  push    rdi
0x180004d7c  push    r14
0x180004d7e  push    r15
0x180004d80  sub     rsp, 250h
0x180004d87  mov     rax, cs:__security_cookie
0x180004d8e  xor     rax, rsp
0x180004d91  mov     [rsp+278h+var_38], rax
0x180004d99  mov     rbx, r8
0x180004d9c  mov     rsi, rdx
0x180004d9f  mov     r14, rcx
0x180004da2  xor     r15d, r15d
0x180004da5  test    rdx, rdx
0x180004da8  jz      loc_180005001
0x180004dae  test    rcx, rcx
0x180004db1  jz      loc_180005001
0x180004db7  mov     [rcx], r15w
0x180004dbb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004dc2  test    rax, rax
0x180004dc5  jz      short loc_180004DE8
0x180004dc7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004dce  jz      short loc_180004DE8
0x180004dd0  mov     r8, rdx
0x180004dd3  mov     rdx, rcx
0x180004dd6  mov     rcx, rbx
0x180004dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dde  cmp     [r14], r15w
0x180004de2  jnz     loc_180005001
0x180004de8  mov     ecx, [rbx]
0x180004dea  mov     bpl, 8
0x180004ded  test    ecx, ecx
0x180004def  jz      short loc_180004E3A
0x180004df1  sub     ecx, 1
0x180004df4  jz      short loc_180004E22
0x180004df6  sub     ecx, 1
0x180004df9  jz      short loc_180004E12
0x180004dfb  cmp     ecx, 1
0x180004dfe  jz      short loc_180004E09
0x180004e00  lea     rdi, byte_18000B8A0
0x180004e07  jmp     short loc_180004E41
0x180004e09  lea     rdi, aFailfast; "FailFast"
0x180004e10  jmp     short loc_180004E41
0x180004e12  lea     rax, aLoghr; "LogHr"
0x180004e19  lea     rdi, aLognt; "LogNt"
0x180004e20  jmp     short loc_180004E30
0x180004e22  lea     rax, aReturnhr; "ReturnHr"
0x180004e29  lea     rdi, aReturnnt; "ReturnNt"
0x180004e30  test    [rbx+4], bpl
0x180004e34  cmovz   rdi, rax
0x180004e38  jmp     short loc_180004E41
0x180004e3a  lea     rdi, aException; "Exception"
0x180004e41  xor     edx, edx; Val
0x180004e43  mov     r8d, 200h; Size
0x180004e49  lea     rcx, [rsp+278h+Buffer]; void *
0x180004e4e  call    memset_0
0x180004e53  test    [rbx+4], bpl
0x180004e57  jz      short loc_180004E7C
0x180004e59  mov     ebp, [rbx+0Ch]
0x180004e5c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004e63  test    rax, rax
0x180004e66  jz      short loc_180004EAC
0x180004e68  mov     r8d, 100h
0x180004e6e  lea     rdx, [rsp+278h+Buffer]
0x180004e73  mov     ecx, ebp
0x180004e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e7a  jmp     short loc_180004EAC
0x180004e7c  mov     ebp, [rbx+8]
0x180004e7f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004e84  mov     [rsp+278h+nSize], 100h; nSize
0x180004e8c  lea     rax, [rsp+278h+Buffer]
0x180004e91  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004e96  mov     r9d, 400h; dwLanguageId
0x180004e9c  mov     r8d, ebp; dwMessageId
0x180004e9f  xor     edx, edx; lpSource
0x180004ea1  mov     ecx, 1200h; dwFlags
0x180004ea6  call    cs:__imp_FormatMessageW
0x180004eac  lea     rsi, [r14+rsi*2]
0x180004eb0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004eb4  mov     rax, [rbx+88h]
0x180004ebb  mov     rcx, [rbx+80h]
0x180004ec2  mov     rdx, rsi; unsigned __int16 *
0x180004ec5  test    r9, r9
0x180004ec8  jz      short loc_180004EEC
0x180004eca  mov     [rsp+278h+Arguments], rax
0x180004ecf  mov     qword ptr [rsp+278h+nSize], rcx
0x180004ed4  mov     eax, [rbx+40h]
0x180004ed7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004edb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004ee2  mov     rcx, r14; this
0x180004ee5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004eea  jmp     short loc_180004F03
0x180004eec  mov     [rsp+278h+lpBuffer], rax
0x180004ef1  mov     r9, rcx; unsigned __int16 *
0x180004ef4  lea     r8, aHsP; "%hs!%p: "
0x180004efb  mov     rcx, r14; this
0x180004efe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f03  mov     r14, rax
0x180004f06  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004f0d  test    r9, r9
0x180004f10  jz      short loc_180004F27
0x180004f12  lea     r8, aCallerP; "(caller: %p) "
0x180004f19  mov     rdx, rsi; unsigned __int16 *
0x180004f1c  mov     rcx, rax; this
0x180004f1f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f24  mov     r14, rax
0x180004f27  call    cs:__imp_GetCurrentThreadId
0x180004f2d  lea     rcx, [rsp+278h+Buffer]
0x180004f32  mov     [rsp+278h+var_240], rcx
0x180004f37  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004f3b  mov     [rsp+278h+nSize], eax
0x180004f3f  mov     eax, [rbx+44h]
0x180004f42  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004f46  mov     r9, rdi; unsigned __int16 *
0x180004f49  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004f50  mov     rdx, rsi; unsigned __int16 *
0x180004f53  mov     rcx, r14; this
0x180004f56  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f5b  cmp     [rbx+18h], r15
0x180004f5f  jnz     short loc_180004F71
0x180004f61  cmp     [rbx+48h], r15
0x180004f65  jnz     short loc_180004F71
0x180004f67  cmp     [rbx+30h], r15
0x180004f6b  jz      loc_180005001
0x180004f71  lea     r8, asc_18000B9A8; "    "
0x180004f78  mov     rdx, rsi; unsigned __int16 *
0x180004f7b  mov     rcx, rax; this
0x180004f7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f83  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004f87  test    r9, r9
0x180004f8a  jz      short loc_180004F9E
0x180004f8c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004f93  mov     rdx, rsi; unsigned __int16 *
0x180004f96  mov     rcx, rax; this
0x180004f99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f9e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004fa2  test    r9, r9
0x180004fa5  jz      short loc_180004FB9
0x180004fa7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004fae  mov     rdx, rsi; unsigned __int16 *
0x180004fb1  mov     rcx, rax; this
0x180004fb4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fb9  mov     rcx, [rbx+28h]
0x180004fbd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004fc1  mov     rdx, rsi; unsigned __int16 *
0x180004fc4  test    rcx, rcx
0x180004fc7  jz      short loc_180004FDF
0x180004fc9  mov     [rsp+278h+lpBuffer], rcx
0x180004fce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004fd5  mov     rcx, rax; this
0x180004fd8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fdd  jmp     short loc_180005001
0x180004fdf  mov     rcx, rax; this
0x180004fe2  test    r9, r9
0x180004fe5  jz      short loc_180004FF5
0x180004fe7  lea     r8, aHs; "[%hs]\n"
0x180004fee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ff3  jmp     short loc_180005001
0x180004ff5  lea     r8, asc_18000BA20; "\n"
0x180004ffc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005001  xor     eax, eax
0x180005003  mov     rcx, [rsp+278h+var_38]
0x18000500b  xor     rcx, rsp; StackCookie
0x18000500e  call    __security_check_cookie
0x180005013  mov     rbx, [rsp+278h+arg_18]
0x18000501b  add     rsp, 250h
0x180005022  pop     r15
0x180005024  pop     r14
0x180005026  pop     rdi
0x180005027  pop     rsi
0x180005028  pop     rbp
0x180005029  retn
```
