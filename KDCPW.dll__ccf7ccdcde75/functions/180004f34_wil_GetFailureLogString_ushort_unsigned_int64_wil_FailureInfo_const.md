# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004f34`
- end: `0x1800051ea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002b14`
- `0x180002d7c`
- `0x180005bec`

## callees

- `0x180001630`
- `0x180001f88`
- `0x180004f34`
- `0x180005eec`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050e7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005066`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005066`

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
          v8 = (const char *)&byte_18000E92D;
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
0x180004f34  mov     [rsp+arg_18], rbx
0x180004f39  push    rbp
0x180004f3a  push    rsi
0x180004f3b  push    rdi
0x180004f3c  push    r14
0x180004f3e  push    r15
0x180004f40  sub     rsp, 250h
0x180004f47  mov     rax, cs:__security_cookie
0x180004f4e  xor     rax, rsp
0x180004f51  mov     [rsp+278h+var_38], rax
0x180004f59  xor     r15d, r15d
0x180004f5c  mov     rbx, r8
0x180004f5f  mov     rsi, rdx
0x180004f62  mov     r14, rcx
0x180004f65  test    rdx, rdx
0x180004f68  jz      loc_1800051C1
0x180004f6e  test    rcx, rcx
0x180004f71  jz      loc_1800051C1
0x180004f77  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f7e  mov     [rcx], r15w
0x180004f82  test    rax, rax
0x180004f85  jz      short loc_180004FA8
0x180004f87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004f8e  jz      short loc_180004FA8
0x180004f90  mov     r8, rdx
0x180004f93  mov     rdx, rcx
0x180004f96  mov     rcx, rbx
0x180004f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9e  cmp     [r14], r15w
0x180004fa2  jnz     loc_1800051C1
0x180004fa8  mov     ecx, [rbx]
0x180004faa  mov     bpl, 8
0x180004fad  test    ecx, ecx
0x180004faf  jz      short loc_180004FFA
0x180004fb1  sub     ecx, 1
0x180004fb4  jz      short loc_180004FE2
0x180004fb6  sub     ecx, 1
0x180004fb9  jz      short loc_180004FD2
0x180004fbb  cmp     ecx, 1
0x180004fbe  jz      short loc_180004FC9
0x180004fc0  lea     rdi, byte_18000E92D
0x180004fc7  jmp     short loc_180005001
0x180004fc9  lea     rdi, aFailfast; "FailFast"
0x180004fd0  jmp     short loc_180005001
0x180004fd2  lea     rax, aLoghr; "LogHr"
0x180004fd9  lea     rdi, aLognt; "LogNt"
0x180004fe0  jmp     short loc_180004FF0
0x180004fe2  lea     rax, aReturnhr; "ReturnHr"
0x180004fe9  lea     rdi, aReturnnt; "ReturnNt"
0x180004ff0  test    [rbx+4], bpl
0x180004ff4  cmovz   rdi, rax
0x180004ff8  jmp     short loc_180005001
0x180004ffa  lea     rdi, aException; "Exception"
0x180005001  xor     edx, edx; Val
0x180005003  lea     rcx, [rsp+278h+Buffer]; void *
0x180005008  mov     r8d, 200h; Size
0x18000500e  call    memset_0
0x180005013  test    [rbx+4], bpl
0x180005017  jz      short loc_18000503C
0x180005019  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005020  mov     ebp, [rbx+0Ch]
0x180005023  test    rax, rax
0x180005026  jz      short loc_18000506C
0x180005028  mov     r8d, 100h
0x18000502e  lea     rdx, [rsp+278h+Buffer]
0x180005033  mov     ecx, ebp
0x180005035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000503a  jmp     short loc_18000506C
0x18000503c  mov     ebp, [rbx+8]
0x18000503f  lea     rax, [rsp+278h+Buffer]
0x180005044  mov     [rsp+278h+Arguments], r15; Arguments
0x180005049  mov     r8d, ebp; dwMessageId
0x18000504c  mov     [rsp+278h+nSize], 100h; nSize
0x180005054  mov     r9d, 400h; dwLanguageId
0x18000505a  xor     edx, edx; lpSource
0x18000505c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005061  mov     ecx, 1200h; dwFlags
0x180005066  call    cs:__imp_FormatMessageW
0x18000506c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005070  lea     rsi, [r14+rsi*2]
0x180005074  mov     rax, [rbx+88h]
0x18000507b  mov     rdx, rsi; unsigned __int16 *
0x18000507e  mov     rcx, [rbx+80h]
0x180005085  test    r9, r9
0x180005088  jz      short loc_1800050AC
0x18000508a  mov     [rsp+278h+Arguments], rax
0x18000508f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005096  mov     eax, [rbx+40h]
0x180005099  mov     qword ptr [rsp+278h+nSize], rcx
0x18000509e  mov     rcx, r14; this
0x1800050a1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800050a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050aa  jmp     short loc_1800050C3
0x1800050ac  mov     r9, rcx; unsigned __int16 *
0x1800050af  mov     [rsp+278h+lpBuffer], rax
0x1800050b4  mov     rcx, r14; this
0x1800050b7  lea     r8, aHsP; "%hs!%p: "
0x1800050be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050c3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800050ca  mov     r14, rax
0x1800050cd  test    r9, r9
0x1800050d0  jz      short loc_1800050E7
0x1800050d2  lea     r8, aCallerP; "(caller: %p) "
0x1800050d9  mov     rdx, rsi; unsigned __int16 *
0x1800050dc  mov     rcx, rax; this
0x1800050df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800050e4  mov     r14, rax
0x1800050e7  call    cs:__imp_GetCurrentThreadId
0x1800050ed  lea     rcx, [rsp+278h+Buffer]
0x1800050f2  mov     r9, rdi; unsigned __int16 *
0x1800050f5  mov     [rsp+278h+var_240], rcx
0x1800050fa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005101  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005105  mov     rdx, rsi; unsigned __int16 *
0x180005108  mov     [rsp+278h+nSize], eax
0x18000510c  mov     rcx, r14; this
0x18000510f  mov     eax, [rbx+44h]
0x180005112  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005116  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000511b  cmp     [rbx+18h], r15
0x18000511f  jnz     short loc_180005131
0x180005121  cmp     [rbx+48h], r15
0x180005125  jnz     short loc_180005131
0x180005127  cmp     [rbx+30h], r15
0x18000512b  jz      loc_1800051C1
0x180005131  lea     r8, asc_18000EA18; "    "
0x180005138  mov     rdx, rsi; unsigned __int16 *
0x18000513b  mov     rcx, rax; this
0x18000513e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005143  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005147  test    r9, r9
0x18000514a  jz      short loc_18000515E
0x18000514c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005153  mov     rdx, rsi; unsigned __int16 *
0x180005156  mov     rcx, rax; this
0x180005159  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000515e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005162  test    r9, r9
0x180005165  jz      short loc_180005179
0x180005167  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000516e  mov     rdx, rsi; unsigned __int16 *
0x180005171  mov     rcx, rax; this
0x180005174  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005179  mov     rcx, [rbx+28h]
0x18000517d  mov     rdx, rsi; unsigned __int16 *
0x180005180  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005184  test    rcx, rcx
0x180005187  jz      short loc_18000519F
0x180005189  mov     [rsp+278h+lpBuffer], rcx
0x18000518e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005195  mov     rcx, rax; this
0x180005198  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000519d  jmp     short loc_1800051C1
0x18000519f  mov     rcx, rax; this
0x1800051a2  test    r9, r9
0x1800051a5  jz      short loc_1800051B5
0x1800051a7  lea     r8, aHs; "[%hs]\n"
0x1800051ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051b3  jmp     short loc_1800051C1
0x1800051b5  lea     r8, asc_18000EA90; "\n"
0x1800051bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051c1  xor     eax, eax
0x1800051c3  mov     rcx, [rsp+278h+var_38]
0x1800051cb  xor     rcx, rsp; StackCookie
0x1800051ce  call    __security_check_cookie
0x1800051d3  mov     rbx, [rsp+278h+arg_18]
0x1800051db  add     rsp, 250h
0x1800051e2  pop     r15
0x1800051e4  pop     r14
0x1800051e6  pop     rdi
0x1800051e7  pop     rsi
0x1800051e8  pop     rbp
0x1800051e9  retn
```
