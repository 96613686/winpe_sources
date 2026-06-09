# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004f64`
- end: `0x18000521a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002838`
- `0x180002aa0`
- `0x1800059ac`
- `0x18000d6e0`

## callees

- `0x180001670`
- `0x180002034`
- `0x180004f64`
- `0x180005cac`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005096`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005096`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005117`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005117`

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
          v7 = (const char *)&qword_180019238;
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
0x180004f64  mov     [rsp+arg_18], rbx
0x180004f69  push    rbp
0x180004f6a  push    rsi
0x180004f6b  push    rdi
0x180004f6c  push    r14
0x180004f6e  push    r15
0x180004f70  sub     rsp, 250h
0x180004f77  mov     rax, cs:__security_cookie
0x180004f7e  xor     rax, rsp
0x180004f81  mov     [rsp+278h+var_38], rax
0x180004f89  mov     rbx, r8
0x180004f8c  mov     rsi, rdx
0x180004f8f  mov     r14, rcx
0x180004f92  xor     r15d, r15d
0x180004f95  test    rdx, rdx
0x180004f98  jz      loc_1800051F1
0x180004f9e  test    rcx, rcx
0x180004fa1  jz      loc_1800051F1
0x180004fa7  mov     [rcx], r15w
0x180004fab  mov     rax, cs:g_pfnResultLoggingCallback
0x180004fb2  test    rax, rax
0x180004fb5  jz      short loc_180004FD8
0x180004fb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004fbe  jz      short loc_180004FD8
0x180004fc0  mov     r8, rdx
0x180004fc3  mov     rdx, rcx
0x180004fc6  mov     rcx, rbx
0x180004fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fce  cmp     [r14], r15w
0x180004fd2  jnz     loc_1800051F1
0x180004fd8  mov     ecx, [rbx]
0x180004fda  mov     bpl, 8
0x180004fdd  test    ecx, ecx
0x180004fdf  jz      short loc_18000502A
0x180004fe1  sub     ecx, 1
0x180004fe4  jz      short loc_180005012
0x180004fe6  sub     ecx, 1
0x180004fe9  jz      short loc_180005002
0x180004feb  cmp     ecx, 1
0x180004fee  jz      short loc_180004FF9
0x180004ff0  lea     rdi, qword_180019238
0x180004ff7  jmp     short loc_180005031
0x180004ff9  lea     rdi, aFailfast; "FailFast"
0x180005000  jmp     short loc_180005031
0x180005002  lea     rax, aLoghr; "LogHr"
0x180005009  lea     rdi, aLognt; "LogNt"
0x180005010  jmp     short loc_180005020
0x180005012  lea     rax, aReturnhr; "ReturnHr"
0x180005019  lea     rdi, aReturnnt; "ReturnNt"
0x180005020  test    [rbx+4], bpl
0x180005024  cmovz   rdi, rax
0x180005028  jmp     short loc_180005031
0x18000502a  lea     rdi, aException; "Exception"
0x180005031  xor     edx, edx; Val
0x180005033  mov     r8d, 200h; Size
0x180005039  lea     rcx, [rsp+278h+Buffer]; void *
0x18000503e  call    memset_0
0x180005043  test    [rbx+4], bpl
0x180005047  jz      short loc_18000506C
0x180005049  mov     ebp, [rbx+0Ch]
0x18000504c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005053  test    rax, rax
0x180005056  jz      short loc_18000509C
0x180005058  mov     r8d, 100h
0x18000505e  lea     rdx, [rsp+278h+Buffer]
0x180005063  mov     ecx, ebp
0x180005065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000506a  jmp     short loc_18000509C
0x18000506c  mov     ebp, [rbx+8]
0x18000506f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005074  mov     [rsp+278h+nSize], 100h; nSize
0x18000507c  lea     rax, [rsp+278h+Buffer]
0x180005081  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005086  mov     r9d, 400h; dwLanguageId
0x18000508c  mov     r8d, ebp; dwMessageId
0x18000508f  xor     edx, edx; lpSource
0x180005091  mov     ecx, 1200h; dwFlags
0x180005096  call    cs:__imp_FormatMessageW
0x18000509c  lea     rsi, [r14+rsi*2]
0x1800050a0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800050a4  mov     rax, [rbx+88h]
0x1800050ab  mov     rcx, [rbx+80h]
0x1800050b2  mov     rdx, rsi; unsigned __int16 *
0x1800050b5  test    r9, r9
0x1800050b8  jz      short loc_1800050DC
0x1800050ba  mov     [rsp+278h+Arguments], rax
0x1800050bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800050c4  mov     eax, [rbx+40h]
0x1800050c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800050cb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800050d2  mov     rcx, r14; this
0x1800050d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050da  jmp     short loc_1800050F3
0x1800050dc  mov     [rsp+278h+lpBuffer], rax
0x1800050e1  mov     r9, rcx; unsigned __int16 *
0x1800050e4  lea     r8, aHsP; "%hs!%p: "
0x1800050eb  mov     rcx, r14; this
0x1800050ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050f3  mov     r14, rax
0x1800050f6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800050fd  test    r9, r9
0x180005100  jz      short loc_180005117
0x180005102  lea     r8, aCallerP; "(caller: %p) "
0x180005109  mov     rdx, rsi; unsigned __int16 *
0x18000510c  mov     rcx, rax; this
0x18000510f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005114  mov     r14, rax
0x180005117  call    cs:__imp_GetCurrentThreadId
0x18000511d  lea     rcx, [rsp+278h+Buffer]
0x180005122  mov     [rsp+278h+var_240], rcx
0x180005127  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000512b  mov     [rsp+278h+nSize], eax
0x18000512f  mov     eax, [rbx+44h]
0x180005132  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005136  mov     r9, rdi; unsigned __int16 *
0x180005139  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005140  mov     rdx, rsi; unsigned __int16 *
0x180005143  mov     rcx, r14; this
0x180005146  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000514b  cmp     [rbx+18h], r15
0x18000514f  jnz     short loc_180005161
0x180005151  cmp     [rbx+48h], r15
0x180005155  jnz     short loc_180005161
0x180005157  cmp     [rbx+30h], r15
0x18000515b  jz      loc_1800051F1
0x180005161  lea     r8, asc_1800161C0; "    "
0x180005168  mov     rdx, rsi; unsigned __int16 *
0x18000516b  mov     rcx, rax; this
0x18000516e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005173  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005177  test    r9, r9
0x18000517a  jz      short loc_18000518E
0x18000517c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005183  mov     rdx, rsi; unsigned __int16 *
0x180005186  mov     rcx, rax; this
0x180005189  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000518e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005192  test    r9, r9
0x180005195  jz      short loc_1800051A9
0x180005197  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000519e  mov     rdx, rsi; unsigned __int16 *
0x1800051a1  mov     rcx, rax; this
0x1800051a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051a9  mov     rcx, [rbx+28h]
0x1800051ad  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800051b1  mov     rdx, rsi; unsigned __int16 *
0x1800051b4  test    rcx, rcx
0x1800051b7  jz      short loc_1800051CF
0x1800051b9  mov     [rsp+278h+lpBuffer], rcx
0x1800051be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800051c5  mov     rcx, rax; this
0x1800051c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051cd  jmp     short loc_1800051F1
0x1800051cf  mov     rcx, rax; this
0x1800051d2  test    r9, r9
0x1800051d5  jz      short loc_1800051E5
0x1800051d7  lea     r8, aHs; "[%hs]\n"
0x1800051de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051e3  jmp     short loc_1800051F1
0x1800051e5  lea     r8, asc_180016238; "\n"
0x1800051ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051f1  xor     eax, eax
0x1800051f3  mov     rcx, [rsp+278h+var_38]
0x1800051fb  xor     rcx, rsp; StackCookie
0x1800051fe  call    __security_check_cookie
0x180005203  mov     rbx, [rsp+278h+arg_18]
0x18000520b  add     rsp, 250h
0x180005212  pop     r15
0x180005214  pop     r14
0x180005216  pop     rdi
0x180005217  pop     rsi
0x180005218  pop     rbp
0x180005219  retn
```
