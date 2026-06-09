# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004ed4`
- end: `0x18000518a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002cfc`
- `0x180002f64`
- `0x18000591c`

## callees

- `0x180001ac0`
- `0x1800026b4`
- `0x180004ed4`
- `0x180005c1c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005087`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005006`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005006`

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
          v8 = (const char *)&qword_180026A58;
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
0x180004ed4  mov     [rsp+arg_18], rbx
0x180004ed9  push    rbp
0x180004eda  push    rsi
0x180004edb  push    rdi
0x180004edc  push    r14
0x180004ede  push    r15
0x180004ee0  sub     rsp, 250h
0x180004ee7  mov     rax, cs:__security_cookie
0x180004eee  xor     rax, rsp
0x180004ef1  mov     [rsp+278h+var_38], rax
0x180004ef9  xor     r15d, r15d
0x180004efc  mov     rbx, r8
0x180004eff  mov     rsi, rdx
0x180004f02  mov     r14, rcx
0x180004f05  test    rdx, rdx
0x180004f08  jz      loc_180005161
0x180004f0e  test    rcx, rcx
0x180004f11  jz      loc_180005161
0x180004f17  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f1e  mov     [rcx], r15w
0x180004f22  test    rax, rax
0x180004f25  jz      short loc_180004F48
0x180004f27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004f2e  jz      short loc_180004F48
0x180004f30  mov     r8, rdx
0x180004f33  mov     rdx, rcx
0x180004f36  mov     rcx, rbx
0x180004f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f3e  cmp     [r14], r15w
0x180004f42  jnz     loc_180005161
0x180004f48  mov     ecx, [rbx]
0x180004f4a  mov     bpl, 8
0x180004f4d  test    ecx, ecx
0x180004f4f  jz      short loc_180004F9A
0x180004f51  sub     ecx, 1
0x180004f54  jz      short loc_180004F82
0x180004f56  sub     ecx, 1
0x180004f59  jz      short loc_180004F72
0x180004f5b  cmp     ecx, 1
0x180004f5e  jz      short loc_180004F69
0x180004f60  lea     rdi, qword_180026A58
0x180004f67  jmp     short loc_180004FA1
0x180004f69  lea     rdi, aFailfast; "FailFast"
0x180004f70  jmp     short loc_180004FA1
0x180004f72  lea     rax, aLoghr; "LogHr"
0x180004f79  lea     rdi, aLognt; "LogNt"
0x180004f80  jmp     short loc_180004F90
0x180004f82  lea     rax, aReturnhr; "ReturnHr"
0x180004f89  lea     rdi, aReturnnt; "ReturnNt"
0x180004f90  test    [rbx+4], bpl
0x180004f94  cmovz   rdi, rax
0x180004f98  jmp     short loc_180004FA1
0x180004f9a  lea     rdi, aException; "Exception"
0x180004fa1  xor     edx, edx; Val
0x180004fa3  lea     rcx, [rsp+278h+Buffer]; void *
0x180004fa8  mov     r8d, 200h; Size
0x180004fae  call    memset_0
0x180004fb3  test    [rbx+4], bpl
0x180004fb7  jz      short loc_180004FDC
0x180004fb9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004fc0  mov     ebp, [rbx+0Ch]
0x180004fc3  test    rax, rax
0x180004fc6  jz      short loc_18000500C
0x180004fc8  mov     r8d, 100h
0x180004fce  lea     rdx, [rsp+278h+Buffer]
0x180004fd3  mov     ecx, ebp
0x180004fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fda  jmp     short loc_18000500C
0x180004fdc  mov     ebp, [rbx+8]
0x180004fdf  lea     rax, [rsp+278h+Buffer]
0x180004fe4  mov     [rsp+278h+Arguments], r15; Arguments
0x180004fe9  mov     r8d, ebp; dwMessageId
0x180004fec  mov     [rsp+278h+nSize], 100h; nSize
0x180004ff4  mov     r9d, 400h; dwLanguageId
0x180004ffa  xor     edx, edx; lpSource
0x180004ffc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005001  mov     ecx, 1200h; dwFlags
0x180005006  call    cs:__imp_FormatMessageW
0x18000500c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005010  lea     rsi, [r14+rsi*2]
0x180005014  mov     rax, [rbx+88h]
0x18000501b  mov     rdx, rsi; unsigned __int16 *
0x18000501e  mov     rcx, [rbx+80h]
0x180005025  test    r9, r9
0x180005028  jz      short loc_18000504C
0x18000502a  mov     [rsp+278h+Arguments], rax
0x18000502f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005036  mov     eax, [rbx+40h]
0x180005039  mov     qword ptr [rsp+278h+nSize], rcx
0x18000503e  mov     rcx, r14; this
0x180005041  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005045  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000504a  jmp     short loc_180005063
0x18000504c  mov     r9, rcx; unsigned __int16 *
0x18000504f  mov     [rsp+278h+lpBuffer], rax
0x180005054  mov     rcx, r14; this
0x180005057  lea     r8, aHsP; "%hs!%p: "
0x18000505e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005063  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000506a  mov     r14, rax
0x18000506d  test    r9, r9
0x180005070  jz      short loc_180005087
0x180005072  lea     r8, aCallerP; "(caller: %p) "
0x180005079  mov     rdx, rsi; unsigned __int16 *
0x18000507c  mov     rcx, rax; this
0x18000507f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005084  mov     r14, rax
0x180005087  call    cs:__imp_GetCurrentThreadId
0x18000508d  lea     rcx, [rsp+278h+Buffer]
0x180005092  mov     r9, rdi; unsigned __int16 *
0x180005095  mov     [rsp+278h+var_240], rcx
0x18000509a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800050a1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800050a5  mov     rdx, rsi; unsigned __int16 *
0x1800050a8  mov     [rsp+278h+nSize], eax
0x1800050ac  mov     rcx, r14; this
0x1800050af  mov     eax, [rbx+44h]
0x1800050b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800050b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050bb  cmp     [rbx+18h], r15
0x1800050bf  jnz     short loc_1800050D1
0x1800050c1  cmp     [rbx+48h], r15
0x1800050c5  jnz     short loc_1800050D1
0x1800050c7  cmp     [rbx+30h], r15
0x1800050cb  jz      loc_180005161
0x1800050d1  lea     r8, asc_180026B48; "    "
0x1800050d8  mov     rdx, rsi; unsigned __int16 *
0x1800050db  mov     rcx, rax; this
0x1800050de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800050e7  test    r9, r9
0x1800050ea  jz      short loc_1800050FE
0x1800050ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800050f3  mov     rdx, rsi; unsigned __int16 *
0x1800050f6  mov     rcx, rax; this
0x1800050f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005102  test    r9, r9
0x180005105  jz      short loc_180005119
0x180005107  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000510e  mov     rdx, rsi; unsigned __int16 *
0x180005111  mov     rcx, rax; this
0x180005114  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005119  mov     rcx, [rbx+28h]
0x18000511d  mov     rdx, rsi; unsigned __int16 *
0x180005120  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005124  test    rcx, rcx
0x180005127  jz      short loc_18000513F
0x180005129  mov     [rsp+278h+lpBuffer], rcx
0x18000512e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005135  mov     rcx, rax; this
0x180005138  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000513d  jmp     short loc_180005161
0x18000513f  mov     rcx, rax; this
0x180005142  test    r9, r9
0x180005145  jz      short loc_180005155
0x180005147  lea     r8, aHs; "[%hs]\n"
0x18000514e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005153  jmp     short loc_180005161
0x180005155  lea     r8, asc_180026BC0; "\n"
0x18000515c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005161  xor     eax, eax
0x180005163  mov     rcx, [rsp+278h+var_38]
0x18000516b  xor     rcx, rsp; StackCookie
0x18000516e  call    __security_check_cookie
0x180005173  mov     rbx, [rsp+278h+arg_18]
0x18000517b  add     rsp, 250h
0x180005182  pop     r15
0x180005184  pop     r14
0x180005186  pop     rdi
0x180005187  pop     rsi
0x180005188  pop     rbp
0x180005189  retn
```
