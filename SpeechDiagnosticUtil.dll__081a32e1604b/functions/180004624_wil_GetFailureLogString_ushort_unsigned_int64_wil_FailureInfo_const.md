# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004624`
- end: `0x1800048e7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003860`
- `0x180003ae0`
- `0x1800050a0`

## callees

- `0x180002910`
- `0x180003290`
- `0x180004624`
- `0x1800053b4`
- `0x180011010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180004756`
- `KERNEL32!FormatMessageW` at `0x180004756`
- `KERNEL32!GetCurrentThreadId` at `0x1800047dd`
- `KERNEL32!GetCurrentThreadId` at `0x1800047dd`

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
          v8 = (const char *)&qword_180012910;
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
0x180004624  mov     [rsp+arg_18], rbx
0x180004629  push    rbp
0x18000462a  push    rsi
0x18000462b  push    rdi
0x18000462c  push    r14
0x18000462e  push    r15
0x180004630  sub     rsp, 250h
0x180004637  mov     rax, cs:__security_cookie
0x18000463e  xor     rax, rsp
0x180004641  mov     [rsp+278h+var_38], rax
0x180004649  xor     r15d, r15d
0x18000464c  mov     rbx, r8
0x18000464f  mov     rsi, rdx
0x180004652  mov     r14, rcx
0x180004655  test    rdx, rdx
0x180004658  jz      loc_1800048BD
0x18000465e  test    rcx, rcx
0x180004661  jz      loc_1800048BD
0x180004667  mov     rax, cs:g_pfnResultLoggingCallback
0x18000466e  mov     [rcx], r15w
0x180004672  test    rax, rax
0x180004675  jz      short loc_180004698
0x180004677  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000467e  jz      short loc_180004698
0x180004680  mov     r8, rdx
0x180004683  mov     rdx, rcx
0x180004686  mov     rcx, rbx
0x180004689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000468e  cmp     [r14], r15w
0x180004692  jnz     loc_1800048BD
0x180004698  mov     ecx, [rbx]
0x18000469a  mov     bpl, 8
0x18000469d  test    ecx, ecx
0x18000469f  jz      short loc_1800046EA
0x1800046a1  sub     ecx, 1
0x1800046a4  jz      short loc_1800046D2
0x1800046a6  sub     ecx, 1
0x1800046a9  jz      short loc_1800046C2
0x1800046ab  cmp     ecx, 1
0x1800046ae  jz      short loc_1800046B9
0x1800046b0  lea     rdi, qword_180012910
0x1800046b7  jmp     short loc_1800046F1
0x1800046b9  lea     rdi, aFailfast; "FailFast"
0x1800046c0  jmp     short loc_1800046F1
0x1800046c2  lea     rax, aLoghr; "LogHr"
0x1800046c9  lea     rdi, aLognt; "LogNt"
0x1800046d0  jmp     short loc_1800046E0
0x1800046d2  lea     rax, aReturnhr; "ReturnHr"
0x1800046d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800046e0  test    [rbx+4], bpl
0x1800046e4  cmovz   rdi, rax
0x1800046e8  jmp     short loc_1800046F1
0x1800046ea  lea     rdi, aException; "Exception"
0x1800046f1  xor     edx, edx; Val
0x1800046f3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800046f8  mov     r8d, 200h; Size
0x1800046fe  call    memset_0
0x180004703  test    [rbx+4], bpl
0x180004707  jz      short loc_18000472C
0x180004709  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004710  mov     ebp, [rbx+0Ch]
0x180004713  test    rax, rax
0x180004716  jz      short loc_180004762
0x180004718  mov     r8d, 100h
0x18000471e  lea     rdx, [rsp+278h+Buffer]
0x180004723  mov     ecx, ebp
0x180004725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000472a  jmp     short loc_180004762
0x18000472c  mov     ebp, [rbx+8]
0x18000472f  lea     rax, [rsp+278h+Buffer]
0x180004734  mov     [rsp+278h+Arguments], r15; Arguments
0x180004739  mov     r8d, ebp; dwMessageId
0x18000473c  mov     [rsp+278h+nSize], 100h; nSize
0x180004744  mov     r9d, 400h; dwLanguageId
0x18000474a  xor     edx, edx; lpSource
0x18000474c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004751  mov     ecx, 1200h; dwFlags
0x180004756  call    cs:__imp_FormatMessageW
0x18000475d  nop     dword ptr [rax+rax+00h]
0x180004762  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004766  lea     rsi, [r14+rsi*2]
0x18000476a  mov     rax, [rbx+88h]
0x180004771  mov     rdx, rsi; unsigned __int16 *
0x180004774  mov     rcx, [rbx+80h]
0x18000477b  test    r9, r9
0x18000477e  jz      short loc_1800047A2
0x180004780  mov     [rsp+278h+Arguments], rax
0x180004785  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000478c  mov     eax, [rbx+40h]
0x18000478f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004794  mov     rcx, r14; this
0x180004797  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000479b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047a0  jmp     short loc_1800047B9
0x1800047a2  mov     r9, rcx; unsigned __int16 *
0x1800047a5  mov     [rsp+278h+lpBuffer], rax
0x1800047aa  mov     rcx, r14; this
0x1800047ad  lea     r8, aHsP; "%hs!%p: "
0x1800047b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047b9  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800047c0  mov     r14, rax
0x1800047c3  test    r9, r9
0x1800047c6  jz      short loc_1800047DD
0x1800047c8  lea     r8, aCallerP; "(caller: %p) "
0x1800047cf  mov     rdx, rsi; unsigned __int16 *
0x1800047d2  mov     rcx, rax; this
0x1800047d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800047da  mov     r14, rax
0x1800047dd  call    cs:__imp_GetCurrentThreadId
0x1800047e4  nop     dword ptr [rax+rax+00h]
0x1800047e9  lea     rcx, [rsp+278h+Buffer]
0x1800047ee  mov     r9, rdi; unsigned __int16 *
0x1800047f1  mov     [rsp+278h+var_240], rcx
0x1800047f6  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800047fd  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004801  mov     rdx, rsi; unsigned __int16 *
0x180004804  mov     [rsp+278h+nSize], eax
0x180004808  mov     rcx, r14; this
0x18000480b  mov     eax, [rbx+44h]
0x18000480e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004812  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004817  cmp     [rbx+18h], r15
0x18000481b  jnz     short loc_18000482D
0x18000481d  cmp     [rbx+48h], r15
0x180004821  jnz     short loc_18000482D
0x180004823  cmp     [rbx+30h], r15
0x180004827  jz      loc_1800048BD
0x18000482d  lea     r8, asc_180012A00; "    "
0x180004834  mov     rdx, rsi; unsigned __int16 *
0x180004837  mov     rcx, rax; this
0x18000483a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000483f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004843  test    r9, r9
0x180004846  jz      short loc_18000485A
0x180004848  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000484f  mov     rdx, rsi; unsigned __int16 *
0x180004852  mov     rcx, rax; this
0x180004855  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000485a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000485e  test    r9, r9
0x180004861  jz      short loc_180004875
0x180004863  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000486a  mov     rdx, rsi; unsigned __int16 *
0x18000486d  mov     rcx, rax; this
0x180004870  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004875  mov     rcx, [rbx+28h]
0x180004879  mov     rdx, rsi; unsigned __int16 *
0x18000487c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004880  test    rcx, rcx
0x180004883  jz      short loc_18000489B
0x180004885  mov     [rsp+278h+lpBuffer], rcx
0x18000488a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004891  mov     rcx, rax; this
0x180004894  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004899  jmp     short loc_1800048BD
0x18000489b  mov     rcx, rax; this
0x18000489e  test    r9, r9
0x1800048a1  jz      short loc_1800048B1
0x1800048a3  lea     r8, aHs; "[%hs]\n"
0x1800048aa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048af  jmp     short loc_1800048BD
0x1800048b1  lea     r8, asc_180012A78; "\n"
0x1800048b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800048bd  xor     eax, eax
0x1800048bf  mov     rcx, [rsp+278h+var_38]
0x1800048c7  xor     rcx, rsp; StackCookie
0x1800048ca  call    __security_check_cookie
0x1800048cf  mov     rbx, [rsp+278h+arg_18]
0x1800048d7  add     rsp, 250h
0x1800048de  pop     r15
0x1800048e0  pop     r14
0x1800048e2  pop     rdi
0x1800048e3  pop     rsi
0x1800048e4  pop     rbp
0x1800048e5  retn
```
