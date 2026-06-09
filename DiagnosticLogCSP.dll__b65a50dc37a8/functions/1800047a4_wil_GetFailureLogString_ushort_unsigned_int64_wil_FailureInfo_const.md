# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800047a4`
- end: `0x180004a67`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800036a8`
- `0x18000392c`
- `0x180005174`
- `0x180006b40`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x1800047a4`
- `0x180005488`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000495d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000495d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800048d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800048d6`

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
          v7 = (const char *)&qword_18003D3B8;
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
0x1800047a4  mov     [rsp+arg_18], rbx
0x1800047a9  push    rbp
0x1800047aa  push    rsi
0x1800047ab  push    rdi
0x1800047ac  push    r14
0x1800047ae  push    r15
0x1800047b0  sub     rsp, 250h
0x1800047b7  mov     rax, cs:__security_cookie
0x1800047be  xor     rax, rsp
0x1800047c1  mov     [rsp+278h+var_38], rax
0x1800047c9  mov     rbx, r8
0x1800047cc  mov     rsi, rdx
0x1800047cf  mov     r14, rcx
0x1800047d2  xor     r15d, r15d
0x1800047d5  test    rdx, rdx
0x1800047d8  jz      loc_180004A3D
0x1800047de  test    rcx, rcx
0x1800047e1  jz      loc_180004A3D
0x1800047e7  mov     [rcx], r15w
0x1800047eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800047f2  test    rax, rax
0x1800047f5  jz      short loc_180004818
0x1800047f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800047fe  jz      short loc_180004818
0x180004800  mov     r8, rdx
0x180004803  mov     rdx, rcx
0x180004806  mov     rcx, rbx
0x180004809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000480e  cmp     [r14], r15w
0x180004812  jnz     loc_180004A3D
0x180004818  mov     ecx, [rbx]
0x18000481a  mov     bpl, 8
0x18000481d  test    ecx, ecx
0x18000481f  jz      short loc_18000486A
0x180004821  sub     ecx, 1
0x180004824  jz      short loc_180004852
0x180004826  sub     ecx, 1
0x180004829  jz      short loc_180004842
0x18000482b  cmp     ecx, 1
0x18000482e  jz      short loc_180004839
0x180004830  lea     rdi, qword_18003D3B8
0x180004837  jmp     short loc_180004871
0x180004839  lea     rdi, aFailfast; "FailFast"
0x180004840  jmp     short loc_180004871
0x180004842  lea     rax, aLoghr; "LogHr"
0x180004849  lea     rdi, aLognt; "LogNt"
0x180004850  jmp     short loc_180004860
0x180004852  lea     rax, aReturnhr; "ReturnHr"
0x180004859  lea     rdi, aReturnnt; "ReturnNt"
0x180004860  test    [rbx+4], bpl
0x180004864  cmovz   rdi, rax
0x180004868  jmp     short loc_180004871
0x18000486a  lea     rdi, aException; "Exception"
0x180004871  xor     edx, edx; Val
0x180004873  mov     r8d, 200h; Size
0x180004879  lea     rcx, [rsp+278h+Buffer]; void *
0x18000487e  call    memset_0
0x180004883  test    [rbx+4], bpl
0x180004887  jz      short loc_1800048AC
0x180004889  mov     ebp, [rbx+0Ch]
0x18000488c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004893  test    rax, rax
0x180004896  jz      short loc_1800048E2
0x180004898  mov     r8d, 100h
0x18000489e  lea     rdx, [rsp+278h+Buffer]
0x1800048a3  mov     ecx, ebp
0x1800048a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048aa  jmp     short loc_1800048E2
0x1800048ac  mov     ebp, [rbx+8]
0x1800048af  mov     [rsp+278h+Arguments], r15; Arguments
0x1800048b4  mov     [rsp+278h+nSize], 100h; nSize
0x1800048bc  lea     rax, [rsp+278h+Buffer]
0x1800048c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800048c6  mov     r9d, 400h; dwLanguageId
0x1800048cc  mov     r8d, ebp; dwMessageId
0x1800048cf  xor     edx, edx; lpSource
0x1800048d1  mov     ecx, 1200h; dwFlags
0x1800048d6  call    cs:__imp_FormatMessageW
0x1800048dd  nop     dword ptr [rax+rax+00h]
0x1800048e2  lea     rsi, [r14+rsi*2]
0x1800048e6  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800048ea  mov     rax, [rbx+88h]
0x1800048f1  mov     rcx, [rbx+80h]
0x1800048f8  mov     rdx, rsi; unsigned __int16 *
0x1800048fb  test    r9, r9
0x1800048fe  jz      short loc_180004922
0x180004900  mov     [rsp+278h+Arguments], rax
0x180004905  mov     qword ptr [rsp+278h+nSize], rcx
0x18000490a  mov     eax, [rbx+40h]
0x18000490d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004911  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004918  mov     rcx, r14; this
0x18000491b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004920  jmp     short loc_180004939
0x180004922  mov     [rsp+278h+lpBuffer], rax
0x180004927  mov     r9, rcx; unsigned __int16 *
0x18000492a  lea     r8, aHsP; "%hs!%p: "
0x180004931  mov     rcx, r14; this
0x180004934  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004939  mov     r14, rax
0x18000493c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004943  test    r9, r9
0x180004946  jz      short loc_18000495D
0x180004948  lea     r8, aCallerP; "(caller: %p) "
0x18000494f  mov     rdx, rsi; unsigned __int16 *
0x180004952  mov     rcx, rax; this
0x180004955  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000495a  mov     r14, rax
0x18000495d  call    cs:__imp_GetCurrentThreadId
0x180004964  nop     dword ptr [rax+rax+00h]
0x180004969  lea     rcx, [rsp+278h+Buffer]
0x18000496e  mov     [rsp+278h+var_240], rcx
0x180004973  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004977  mov     [rsp+278h+nSize], eax
0x18000497b  mov     eax, [rbx+44h]
0x18000497e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004982  mov     r9, rdi; unsigned __int16 *
0x180004985  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000498c  mov     rdx, rsi; unsigned __int16 *
0x18000498f  mov     rcx, r14; this
0x180004992  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004997  cmp     [rbx+18h], r15
0x18000499b  jnz     short loc_1800049AD
0x18000499d  cmp     [rbx+48h], r15
0x1800049a1  jnz     short loc_1800049AD
0x1800049a3  cmp     [rbx+30h], r15
0x1800049a7  jz      loc_180004A3D
0x1800049ad  lea     r8, asc_18003D4C0; "    "
0x1800049b4  mov     rdx, rsi; unsigned __int16 *
0x1800049b7  mov     rcx, rax; this
0x1800049ba  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800049bf  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800049c3  test    r9, r9
0x1800049c6  jz      short loc_1800049DA
0x1800049c8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800049cf  mov     rdx, rsi; unsigned __int16 *
0x1800049d2  mov     rcx, rax; this
0x1800049d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800049da  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800049de  test    r9, r9
0x1800049e1  jz      short loc_1800049F5
0x1800049e3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800049ea  mov     rdx, rsi; unsigned __int16 *
0x1800049ed  mov     rcx, rax; this
0x1800049f0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800049f5  mov     rcx, [rbx+28h]
0x1800049f9  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800049fd  mov     rdx, rsi; unsigned __int16 *
0x180004a00  test    rcx, rcx
0x180004a03  jz      short loc_180004A1B
0x180004a05  mov     [rsp+278h+lpBuffer], rcx
0x180004a0a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004a11  mov     rcx, rax; this
0x180004a14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a19  jmp     short loc_180004A3D
0x180004a1b  mov     rcx, rax; this
0x180004a1e  test    r9, r9
0x180004a21  jz      short loc_180004A31
0x180004a23  lea     r8, aHs; "[%hs]\n"
0x180004a2a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a2f  jmp     short loc_180004A3D
0x180004a31  lea     r8, asc_18003D538; "\n"
0x180004a38  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a3d  xor     eax, eax
0x180004a3f  mov     rcx, [rsp+278h+var_38]
0x180004a47  xor     rcx, rsp; StackCookie
0x180004a4a  call    __security_check_cookie
0x180004a4f  mov     rbx, [rsp+278h+arg_18]
0x180004a57  add     rsp, 250h
0x180004a5e  pop     r15
0x180004a60  pop     r14
0x180004a62  pop     rdi
0x180004a63  pop     rsi
0x180004a64  pop     rbp
0x180004a65  retn
```
