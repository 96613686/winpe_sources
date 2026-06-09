# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140014138`
- end: `0x1400141c9`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `145`
- prototype: `__int64 __fastcall(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001526c`

## callees

- `0x1400041ac`
- `0x1400074e0`
- `0x1400080fc`
- `0x140014138`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400141b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400141b8`

## string_xrefs

- `0x140014149`: `onecore\windows\directx\database\updater\filecompression\filecompression.cpp`
- `0x140014181`: `onecore\windows\directx\database\updater\filecompression\filecompression.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int v7; // esi
  int LastErrorFail; // eax
  DWORD v9; // ebx
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  const char *v13; // [rsp+20h] [rbp-68h]
  void *v14; // [rsp+30h] [rbp-58h]
  _DWORD v15[14]; // [rsp+50h] [rbp-38h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
                    a4,
                    v13,
                    a6,
                    v14);
  v9 = LastErrorFail;
  if ( LastErrorFail > 0 )
    v10 = (unsigned __int16)LastErrorFail | 0x80070000;
  else
    v10 = (unsigned int)LastErrorFail;
  v15[0] = v10;
  v15[1] = wil::details::HrToNtStatus((wil::details *)v10, 0);
  v15[2] = v11;
  wil::details::ReportFailure_Base<2,0>(
    v7,
    v6,
    (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
    0,
    v11,
    (__int64)a6,
    (__int64)v15,
    v11);
  SetLastError(v9);
  return v9;
}

```

## disassembly

```asm
0x140014138  push    rbx
0x14001413a  push    rbp
0x14001413b  push    rsi
0x14001413c  push    rdi
0x14001413d  sub     rsp, 68h
0x140014141  mov     rbp, [rsp+88h+arg_28]
0x140014149  lea     r8, aOnecoreWindows_1; "onecore\\windows\\directx\\database\\up"...
0x140014150  mov     [rsp+88h+var_60], rbp; char *
0x140014155  mov     edi, edx
0x140014157  mov     rsi, rcx
0x14001415a  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x14001415f  xor     edx, edx; int
0x140014161  mov     ebx, eax
0x140014163  test    eax, eax
0x140014165  jg      short loc_14001416B
0x140014167  mov     ecx, eax
0x140014169  jmp     short loc_140014174
0x14001416b  movzx   ecx, bx
0x14001416e  or      ecx, 80070000h; this
0x140014174  mov     [rsp+88h+var_38], ecx
0x140014178  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14001417d  mov     [rsp+88h+var_40], edx
0x140014181  lea     r8, aOnecoreWindows_1; "onecore\\windows\\directx\\database\\up"...
0x140014188  mov     [rsp+88h+var_50], rdx
0x14001418d  xor     r9d, r9d
0x140014190  mov     [rsp+88h+var_34], eax
0x140014194  mov     rcx, rsi
0x140014197  lea     rax, [rsp+88h+var_38]
0x14001419c  mov     [rsp+88h+var_30], edx
0x1400141a0  mov     [rsp+88h+var_58], rax
0x1400141a5  mov     [rsp+88h+var_60], rbp
0x1400141aa  mov     [rsp+88h+var_68], rdx
0x1400141af  mov     edx, edi
0x1400141b1  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1400141b6  mov     ecx, ebx; dwErrCode
0x1400141b8  call    cs:__imp_SetLastError
0x1400141be  mov     eax, ebx
0x1400141c0  add     rsp, 68h
0x1400141c4  pop     rdi
0x1400141c5  pop     rsi
0x1400141c6  pop     rbp
0x1400141c7  pop     rbx
0x1400141c8  retn
```
