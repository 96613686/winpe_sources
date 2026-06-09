# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180013e18`
- end: `0x1800140ce`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ac3c`
- `0x18001599c`
- `0x1800162c4`
- `0x180024f80`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x180013e18`
- `0x180015eb4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013fcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013fcb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013f4a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013f4a`

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
          v7 = pszCabPath;
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
0x180013e18  mov     [rsp+arg_18], rbx
0x180013e1d  push    rbp
0x180013e1e  push    rsi
0x180013e1f  push    rdi
0x180013e20  push    r14
0x180013e22  push    r15
0x180013e24  sub     rsp, 250h
0x180013e2b  mov     rax, cs:__security_cookie
0x180013e32  xor     rax, rsp
0x180013e35  mov     [rsp+278h+var_38], rax
0x180013e3d  mov     rbx, r8
0x180013e40  mov     rsi, rdx
0x180013e43  mov     r14, rcx
0x180013e46  xor     r15d, r15d
0x180013e49  test    rdx, rdx
0x180013e4c  jz      loc_1800140A5
0x180013e52  test    rcx, rcx
0x180013e55  jz      loc_1800140A5
0x180013e5b  mov     [rcx], r15w
0x180013e5f  mov     rax, cs:g_pfnResultLoggingCallback
0x180013e66  test    rax, rax
0x180013e69  jz      short loc_180013E8C
0x180013e6b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180013e72  jz      short loc_180013E8C
0x180013e74  mov     r8, rdx
0x180013e77  mov     rdx, rcx
0x180013e7a  mov     rcx, rbx
0x180013e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e82  cmp     [r14], r15w
0x180013e86  jnz     loc_1800140A5
0x180013e8c  mov     ecx, [rbx]
0x180013e8e  mov     bpl, 8
0x180013e91  test    ecx, ecx
0x180013e93  jz      short loc_180013EDE
0x180013e95  sub     ecx, 1
0x180013e98  jz      short loc_180013EC6
0x180013e9a  sub     ecx, 1
0x180013e9d  jz      short loc_180013EB6
0x180013e9f  cmp     ecx, 1
0x180013ea2  jz      short loc_180013EAD
0x180013ea4  lea     rdi, pszCabPath
0x180013eab  jmp     short loc_180013EE5
0x180013ead  lea     rdi, aFailfast; "FailFast"
0x180013eb4  jmp     short loc_180013EE5
0x180013eb6  lea     rax, aLoghr; "LogHr"
0x180013ebd  lea     rdi, aLognt; "LogNt"
0x180013ec4  jmp     short loc_180013ED4
0x180013ec6  lea     rax, aReturnhr; "ReturnHr"
0x180013ecd  lea     rdi, aReturnnt; "ReturnNt"
0x180013ed4  test    [rbx+4], bpl
0x180013ed8  cmovz   rdi, rax
0x180013edc  jmp     short loc_180013EE5
0x180013ede  lea     rdi, aException; "Exception"
0x180013ee5  xor     edx, edx; Val
0x180013ee7  mov     r8d, 200h; Size
0x180013eed  lea     rcx, [rsp+278h+Buffer]; void *
0x180013ef2  call    memset_0
0x180013ef7  test    [rbx+4], bpl
0x180013efb  jz      short loc_180013F20
0x180013efd  mov     ebp, [rbx+0Ch]
0x180013f00  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180013f07  test    rax, rax
0x180013f0a  jz      short loc_180013F50
0x180013f0c  mov     r8d, 100h
0x180013f12  lea     rdx, [rsp+278h+Buffer]
0x180013f17  mov     ecx, ebp
0x180013f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f1e  jmp     short loc_180013F50
0x180013f20  mov     ebp, [rbx+8]
0x180013f23  mov     [rsp+278h+Arguments], r15; Arguments
0x180013f28  mov     [rsp+278h+nSize], 100h; nSize
0x180013f30  lea     rax, [rsp+278h+Buffer]
0x180013f35  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180013f3a  mov     r9d, 400h; dwLanguageId
0x180013f40  mov     r8d, ebp; dwMessageId
0x180013f43  xor     edx, edx; lpSource
0x180013f45  mov     ecx, 1200h; dwFlags
0x180013f4a  call    cs:__imp_FormatMessageW
0x180013f50  lea     rsi, [r14+rsi*2]
0x180013f54  mov     r9, [rbx+38h]; unsigned __int16 *
0x180013f58  mov     rax, [rbx+88h]
0x180013f5f  mov     rcx, [rbx+80h]
0x180013f66  mov     rdx, rsi; unsigned __int16 *
0x180013f69  test    r9, r9
0x180013f6c  jz      short loc_180013F90
0x180013f6e  mov     [rsp+278h+Arguments], rax
0x180013f73  mov     qword ptr [rsp+278h+nSize], rcx
0x180013f78  mov     eax, [rbx+40h]
0x180013f7b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180013f7f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180013f86  mov     rcx, r14; this
0x180013f89  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013f8e  jmp     short loc_180013FA7
0x180013f90  mov     [rsp+278h+lpBuffer], rax
0x180013f95  mov     r9, rcx; unsigned __int16 *
0x180013f98  lea     r8, aHsP; "%hs!%p: "
0x180013f9f  mov     rcx, r14; this
0x180013fa2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013fa7  mov     r14, rax
0x180013faa  mov     r9, [rbx+90h]; unsigned __int16 *
0x180013fb1  test    r9, r9
0x180013fb4  jz      short loc_180013FCB
0x180013fb6  lea     r8, aCallerP; "(caller: %p) "
0x180013fbd  mov     rdx, rsi; unsigned __int16 *
0x180013fc0  mov     rcx, rax; this
0x180013fc3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013fc8  mov     r14, rax
0x180013fcb  call    cs:__imp_GetCurrentThreadId
0x180013fd1  lea     rcx, [rsp+278h+Buffer]
0x180013fd6  mov     [rsp+278h+var_240], rcx
0x180013fdb  mov     dword ptr [rsp+278h+Arguments], ebp
0x180013fdf  mov     [rsp+278h+nSize], eax
0x180013fe3  mov     eax, [rbx+44h]
0x180013fe6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180013fea  mov     r9, rdi; unsigned __int16 *
0x180013fed  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180013ff4  mov     rdx, rsi; unsigned __int16 *
0x180013ff7  mov     rcx, r14; this
0x180013ffa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180013fff  cmp     [rbx+18h], r15
0x180014003  jnz     short loc_180014015
0x180014005  cmp     [rbx+48h], r15
0x180014009  jnz     short loc_180014015
0x18001400b  cmp     [rbx+30h], r15
0x18001400f  jz      loc_1800140A5
0x180014015  lea     r8, asc_180067020; "    "
0x18001401c  mov     rdx, rsi; unsigned __int16 *
0x18001401f  mov     rcx, rax; this
0x180014022  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014027  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001402b  test    r9, r9
0x18001402e  jz      short loc_180014042
0x180014030  lea     r8, aMsgWs; "Msg:[%ws] "
0x180014037  mov     rdx, rsi; unsigned __int16 *
0x18001403a  mov     rcx, rax; this
0x18001403d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014042  mov     r9, [rbx+48h]; unsigned __int16 *
0x180014046  test    r9, r9
0x180014049  jz      short loc_18001405D
0x18001404b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180014052  mov     rdx, rsi; unsigned __int16 *
0x180014055  mov     rcx, rax; this
0x180014058  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001405d  mov     rcx, [rbx+28h]
0x180014061  mov     r9, [rbx+30h]; unsigned __int16 *
0x180014065  mov     rdx, rsi; unsigned __int16 *
0x180014068  test    rcx, rcx
0x18001406b  jz      short loc_180014083
0x18001406d  mov     [rsp+278h+lpBuffer], rcx
0x180014072  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180014079  mov     rcx, rax; this
0x18001407c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014081  jmp     short loc_1800140A5
0x180014083  mov     rcx, rax; this
0x180014086  test    r9, r9
0x180014089  jz      short loc_180014099
0x18001408b  lea     r8, aHs; "[%hs]\n"
0x180014092  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014097  jmp     short loc_1800140A5
0x180014099  lea     r8, asc_180067098; "\n"
0x1800140a0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800140a5  xor     eax, eax
0x1800140a7  mov     rcx, [rsp+278h+var_38]
0x1800140af  xor     rcx, rsp; StackCookie
0x1800140b2  call    __security_check_cookie
0x1800140b7  mov     rbx, [rsp+278h+arg_18]
0x1800140bf  add     rsp, 250h
0x1800140c6  pop     r15
0x1800140c8  pop     r14
0x1800140ca  pop     rdi
0x1800140cb  pop     rsi
0x1800140cc  pop     rbp
0x1800140cd  retn
```
