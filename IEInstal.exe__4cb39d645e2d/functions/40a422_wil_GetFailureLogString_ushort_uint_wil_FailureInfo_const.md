# wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)

- ea: `0x40a422`
- end: `0x40a68c`
- name: `?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z`
- size: `618`
- prototype: `int __userpurge@<eax>(int@<edx>, wchar_t *@<ecx>, const unsigned __int16 *@<ebx>, wil *this, unsigned __int16 *, unsigned int, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x40aa18`
- `0x40bc9a`
- `0x40c146`

## callees

- `0x40a3b4`
- `0x40a422`
- `0x40cb60`
- `0x40d1d0`
- `0x40eb27`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x40a544`
- `KERNEL32!FormatMessageW` at `0x40a544`
- `KERNEL32!GetCurrentThreadId` at `0x40a5b3`
- `KERNEL32!GetCurrentThreadId` at `0x40a5b3`

## pseudocode

```c
int __userpurge wil::GetFailureLogString@<eax>(
        int a1@<edx>,
        wchar_t *a2@<ecx>,
        const unsigned __int16 *a3@<ebx>,
        wil *this,
        unsigned __int16 *a5,
        unsigned int a6,
        const struct wil::FailureInfo *a7)
{
  void (__thiscall *v8)(_DWORD, wil *, wchar_t *, int); // ebx
  const char *v9; // ebx
  const char *v10; // eax
  unsigned __int16 *v11; // edi
  wchar_t *v12; // eax
  DWORD CurrentThreadId; // eax
  wchar_t *v14; // eax
  wchar_t *v15; // eax
  const unsigned __int16 *v17; // [esp-Ch] [ebp-228h]
  int v18; // [esp-8h] [ebp-224h]
  const unsigned __int16 *v20; // [esp-4h] [ebp-220h]
  DWORD v22; // [esp+10h] [ebp-20Ch]
  unsigned __int16 *v24; // [esp+14h] [ebp-208h]
  WCHAR Buffer[256]; // [esp+18h] [ebp-204h] BYREF

  if ( !a1 )
    return 0;
  if ( !a2 )
    return 0;
  v8 = (void (__thiscall *)(_DWORD, wil *, wchar_t *, int))g_pfnResultLoggingCallback;
  *a2 = 0;
  if ( v8 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v8(v8, this, a2, a1);
      if ( *a2 )
        return 0;
    }
  }
  v9 = (const char *)&Args;
  if ( *(_DWORD *)this )
  {
    if ( *(_DWORD *)this == 1 )
    {
      v9 = "ReturnHr";
      v10 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)this != 2 )
      {
        if ( *(_DWORD *)this == 3 )
          v9 = "FailFast";
        goto LABEL_17;
      }
      v9 = "LogHr";
      v10 = "LogNt";
    }
    if ( (*((_BYTE *)this + 4) & 8) != 0 )
      v9 = v10;
    goto LABEL_17;
  }
  v9 = "Exception";
LABEL_17:
  memset(Buffer, 0, sizeof(Buffer));
  if ( (*((_BYTE *)this + 4) & 8) != 0 )
  {
    v22 = *((_DWORD *)this + 3);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(*((_DWORD *)this + 3), Buffer, 256u);
  }
  else
  {
    v22 = *((_DWORD *)this + 2);
    FormatMessageW(0x1200u, 0, v22, 0x400u, Buffer, 0x100u, 0);
  }
  v18 = *((_DWORD *)this + 20);
  v17 = (const unsigned __int16 *)*((_DWORD *)this + 19);
  v11 = &a2[a1];
  if ( *((_DWORD *)this + 9) )
    v12 = wil::details::LogStringPrintf(
            a2,
            v11,
            (wchar_t *)L"%hs(%u)\\%hs!%p: ",
            *((const unsigned __int16 **)this + 9),
            *((_DWORD *)this + 10),
            v17,
            v18);
  else
    v12 = wil::details::LogStringPrintf(a2, v11, (wchar_t *)L"%hs!%p: ", v17, v18);
  v24 = v12;
  if ( *((_DWORD *)this + 21) )
    v24 = wil::details::LogStringPrintf(v12, v11, (wchar_t *)L"(caller: %p) ", *((const unsigned __int16 **)this + 21));
  CurrentThreadId = GetCurrentThreadId();
  v14 = wil::details::LogStringPrintf(
          v24,
          v11,
          (wchar_t *)L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v9,
          *((_DWORD *)this + 11),
          CurrentThreadId,
          v22,
          Buffer);
  if ( *((_DWORD *)this + 5) || *((_DWORD *)this + 12) || *((_DWORD *)this + 8) )
  {
    v15 = wil::details::LogStringPrintf(v14, v11, (wchar_t *)L"    ", a3);
    if ( *((_DWORD *)this + 5) )
      v15 = wil::details::LogStringPrintf(v15, v11, (wchar_t *)L"Msg:[%ws] ", *((const unsigned __int16 **)this + 5));
    if ( *((_DWORD *)this + 12) )
      v15 = wil::details::LogStringPrintf(
              v15,
              v11,
              (wchar_t *)L"CallContext:[%hs] ",
              *((const unsigned __int16 **)this + 12));
    if ( *((_DWORD *)this + 7) )
    {
      wil::details::LogStringPrintf(
        v15,
        v11,
        (wchar_t *)L"[%hs(%hs)]\n",
        *((const unsigned __int16 **)this + 8),
        *((_DWORD *)this + 7));
    }
    else if ( *((_DWORD *)this + 8) )
    {
      wil::details::LogStringPrintf(v15, v11, (wchar_t *)L"[%hs]\n", *((const unsigned __int16 **)this + 8));
    }
    else
    {
      wil::details::LogStringPrintf(v15, v11, (wchar_t *)L"\n", v20);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x40a422  mov     edi, edi
0x40a424  push    ebp
0x40a425  mov     ebp, esp
0x40a427  sub     esp, 214h
0x40a42d  mov     eax, ___security_cookie
0x40a432  xor     eax, ebp
0x40a434  mov     [ebp+var_4], eax
0x40a437  push    esi
0x40a438  mov     esi, [ebp+this]
0x40a43b  mov     eax, edx
0x40a43d  mov     [ebp+var_214], eax
0x40a443  push    edi
0x40a444  mov     edi, ecx
0x40a446  mov     [ebp+var_208], edi
0x40a44c  test    eax, eax
0x40a44e  jz      loc_40A67A
0x40a454  test    edi, edi
0x40a456  jz      loc_40A67A
0x40a45c  push    ebx; Args
0x40a45d  mov     ebx, _g_pfnResultLoggingCallback
0x40a463  xor     ecx, ecx
0x40a465  mov     [edi], cx
0x40a468  test    ebx, ebx
0x40a46a  jz      short loc_40A48C
0x40a46c  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, cl; bool wil::details::g_resultMessageCallbackSet
0x40a472  jz      short loc_40A48C
0x40a474  push    eax
0x40a475  push    edi
0x40a476  push    esi
0x40a477  mov     ecx, ebx
0x40a479  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40a47f  call    ebx ; _g_pfnResultLoggingCallback
0x40a481  xor     ecx, ecx
0x40a483  cmp     [edi], cx
0x40a486  jnz     loc_40A679
0x40a48c  mov     eax, [esi]
0x40a48e  mov     ebx, offset Args
0x40a493  sub     eax, ecx
0x40a495  jz      short loc_40A4CC
0x40a497  sub     eax, 1
0x40a49a  jz      short loc_40A4B9
0x40a49c  sub     eax, 1
0x40a49f  jz      short loc_40A4AD
0x40a4a1  sub     eax, 1
0x40a4a4  jnz     short loc_40A4D1
0x40a4a6  mov     ebx, offset aFailfast; "FailFast"
0x40a4ab  jmp     short loc_40A4D1
0x40a4ad  mov     ebx, offset aLoghr; "LogHr"
0x40a4b2  mov     eax, offset aLognt; "LogNt"
0x40a4b7  jmp     short loc_40A4C3
0x40a4b9  mov     ebx, offset aReturnhr; "ReturnHr"
0x40a4be  mov     eax, offset aReturnnt; "ReturnNt"
0x40a4c3  test    byte ptr [esi+4], 8
0x40a4c7  cmovnz  ebx, eax
0x40a4ca  jmp     short loc_40A4D1
0x40a4cc  mov     ebx, offset aException; "Exception"
0x40a4d1  push    200h; Size
0x40a4d6  push    ecx; Val
0x40a4d7  lea     eax, [ebp+Buffer]
0x40a4dd  push    eax; void *
0x40a4de  call    _memset
0x40a4e3  add     esp, 0Ch
0x40a4e6  test    byte ptr [esi+4], 8
0x40a4ea  jz      short loc_40A520
0x40a4ec  mov     ecx, ?g_pfnFormatNtStatusMsg@details@wil@@3P6GXJPAGK@ZA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x40a4f2  mov     eax, [esi+0Ch]
0x40a4f5  mov     [ebp+var_20C], eax
0x40a4fb  mov     [ebp+var_210], ecx
0x40a501  test    ecx, ecx
0x40a503  jz      short loc_40A54A
0x40a505  push    100h
0x40a50a  lea     edx, [ebp+Buffer]
0x40a510  push    edx
0x40a511  push    eax
0x40a512  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40a518  call    [ebp+var_210]
0x40a51e  jmp     short loc_40A54A
0x40a520  mov     eax, [esi+8]
0x40a523  lea     ecx, [ebp+Buffer]
0x40a529  push    0; Arguments
0x40a52b  push    100h; nSize
0x40a530  push    ecx; lpBuffer
0x40a531  push    400h; dwLanguageId
0x40a536  push    eax; dwMessageId
0x40a537  push    0; lpSource
0x40a539  push    1200h; dwFlags
0x40a53e  mov     [ebp+var_20C], eax
0x40a544  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x40a54a  cmp     dword ptr [esi+24h], 0
0x40a54e  mov     eax, [ebp+var_214]
0x40a554  push    dword ptr [esi+50h]
0x40a557  push    dword ptr [esi+4Ch]; Args
0x40a55a  lea     edi, [edi+eax*2]
0x40a55d  jz      short loc_40A57B
0x40a55f  push    dword ptr [esi+28h]
0x40a562  push    dword ptr [esi+24h]; Args
0x40a565  push    offset aHsUHsP; "%hs(%u)\\%hs!%p: "
0x40a56a  push    edi; unsigned __int16 *
0x40a56b  push    [ebp+var_208]; Buffer
0x40a571  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x40a576  add     esp, 1Ch
0x40a579  jmp     short loc_40A58F
0x40a57b  push    offset aHsP; "%hs!%p: "
0x40a580  push    edi; unsigned __int16 *
0x40a581  push    [ebp+var_208]; Buffer
0x40a587  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x40a58c  add     esp, 14h
0x40a58f  cmp     dword ptr [esi+54h], 0
0x40a593  mov     [ebp+var_208], eax
0x40a599  jz      short loc_40A5B3
0x40a59b  push    dword ptr [esi+54h]; Args
0x40a59e  push    offset aCallerP; "(caller: %p) "
0x40a5a3  push    edi; unsigned __int16 *
0x40a5a4  push    eax; Buffer
0x40a5a5  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x40a5aa  add     esp, 10h
0x40a5ad  mov     [ebp+var_208], eax
0x40a5b3  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40a5b9  lea     ecx, [ebp+Buffer]
0x40a5bf  push    ecx
0x40a5c0  push    [ebp+var_20C]
0x40a5c6  push    eax
0x40a5c7  push    dword ptr [esi+2Ch]
0x40a5ca  push    ebx; Args
0x40a5cb  push    offset aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x40a5d0  push    edi; unsigned __int16 *
0x40a5d1  push    [ebp+var_208]; Buffer
0x40a5d7  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x40a5dc  xor     ecx, ecx
0x40a5de  add     esp, 20h
0x40a5e1  cmp     [esi+14h], ecx
0x40a5e4  jnz     short loc_40A5F4
0x40a5e6  cmp     [esi+30h], ecx
0x40a5e9  jnz     short loc_40A5F4
0x40a5eb  cmp     [esi+20h], ecx
0x40a5ee  jz      loc_40A679
0x40a5f4  push    offset asc_401F0C; "    "
0x40a5f9  push    edi; unsigned __int16 *
0x40a5fa  push    eax; Buffer
0x40a5fb  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x40a600  add     esp, 0Ch
0x40a603  cmp     dword ptr [esi+14h], 0
0x40a607  jz      short loc_40A61B
0x40a609  push    dword ptr [esi+14h]; Args
0x40a60c  push    offset aMsgWs; "Msg:[%ws] "
0x40a611  push    edi; unsigned __int16 *
0x40a612  push    eax; Buffer
0x40a613  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x40a618  add     esp, 10h
0x40a61b  cmp     dword ptr [esi+30h], 0
0x40a61f  jz      short loc_40A633
0x40a621  push    dword ptr [esi+30h]; Args
0x40a624  push    offset aCallcontextHs; "CallContext:[%hs] "
0x40a629  push    edi; unsigned __int16 *
0x40a62a  push    eax; Buffer
0x40a62b  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x40a630  add     esp, 10h
0x40a633  cmp     dword ptr [esi+1Ch], 0
0x40a637  jz      short loc_40A650
0x40a639  push    dword ptr [esi+1Ch]
0x40a63c  push    dword ptr [esi+20h]; Args
0x40a63f  push    offset aHsHs; "[%hs(%hs)]\n"
0x40a644  push    edi; unsigned __int16 *
0x40a645  push    eax; Buffer
0x40a646  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x40a64b  add     esp, 14h
0x40a64e  jmp     short loc_40A679
0x40a650  cmp     dword ptr [esi+20h], 0
0x40a654  jz      short loc_40A66A
0x40a656  push    dword ptr [esi+20h]; Args
0x40a659  push    offset aHs; "[%hs]\n"
0x40a65e  push    edi; unsigned __int16 *
0x40a65f  push    eax; Buffer
0x40a660  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x40a665  add     esp, 10h
0x40a668  jmp     short loc_40A679
0x40a66a  push    offset asc_401F80; "\n"
0x40a66f  push    edi; unsigned __int16 *
0x40a670  push    eax; Buffer
0x40a671  call    ?LogStringPrintf@details@wil@@YAPAGPAGPBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x40a676  add     esp, 0Ch
0x40a679  pop     ebx
0x40a67a  mov     ecx, [ebp+var_4]
0x40a67d  xor     eax, eax
0x40a67f  pop     edi
0x40a680  xor     ecx, ebp; StackCookie
0x40a682  pop     esi
0x40a683  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40a688  leave
0x40a689  retn    4
```
