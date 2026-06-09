# HidForceFeedbackScheduler::SignalThread(void)

- ea: `0x18001dfdc`
- end: `0x18001e095`
- name: `?SignalThread@HidForceFeedbackScheduler@@AEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(HidForceFeedbackScheduler *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ac68`
- `0x18001c924`
- `0x18001d7e4`
- `0x18001e5b0`

## callees

- `0x180001304`
- `0x18001dfdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001dfe6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001dfe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dffa`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackScheduler::SignalThread(HANDLE *this)
{
  signed int LastError; // ebx
  __int64 v2; // r8
  __int64 v3; // r9
  signed int v5; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+58h] [rbp+10h] BYREF
  const char *v7; // [rsp+60h] [rbp+18h] BYREF

  if ( SetEvent(this[2]) )
    return 0;
  LastError = GetLastError();
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v5 = LastError;
    v7 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackScheduler.cpp";
    v6 = 77;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned __int8 *)&unk_18005D7E8,
      v2,
      v3,
      (__int64 **)&v7,
      (__int64)&v6,
      (__int64)&v5);
  }
  if ( LastError )
  {
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001dfdc  push    rbx
0x18001dfde  sub     rsp, 40h
0x18001dfe2  mov     rcx, [rcx+10h]; hEvent
0x18001dfe6  call    cs:__imp_SetEvent
0x18001dfed  nop     dword ptr [rax+rax+00h]
0x18001dff2  test    eax, eax
0x18001dff4  jnz     loc_18001E08C
0x18001dffa  call    cs:__imp_GetLastError
0x18001e001  nop     dword ptr [rax+rax+00h]
0x18001e006  mov     ebx, eax
0x18001e008  mov     eax, cs:dword_180069000
0x18001e00e  cmp     eax, 2
0x18001e011  jbe     short loc_18001E072
0x18001e013  mov     rcx, cs:qword_180069018
0x18001e01a  mov     rax, cs:qword_180069010
0x18001e021  test    al, 8
0x18001e023  jz      short loc_18001E072
0x18001e025  mov     rax, rcx
0x18001e028  and     eax, 8
0x18001e02b  cmp     rax, rcx
0x18001e02e  jnz     short loc_18001E072
0x18001e030  lea     rax, aOnecoreXboxGam_18; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x18001e037  mov     [rsp+48h+arg_0], ebx
0x18001e03b  mov     [rsp+48h+arg_10], rax
0x18001e040  lea     rdx, unk_18005D7E8
0x18001e047  lea     rax, [rsp+48h+arg_0]
0x18001e04c  mov     [rsp+48h+arg_8], 4Dh ; 'M'
0x18001e054  mov     [rsp+48h+var_18], rax
0x18001e059  lea     rax, [rsp+48h+arg_8]
0x18001e05e  mov     [rsp+48h+var_20], rax
0x18001e063  lea     rax, [rsp+48h+arg_10]
0x18001e068  mov     [rsp+48h+var_28], rax
0x18001e06d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e072  test    ebx, ebx
0x18001e074  jnz     short loc_18001E07D
0x18001e076  mov     ebx, 8000FFFFh
0x18001e07b  jmp     short loc_18001E088
0x18001e07d  jle     short loc_18001E088
0x18001e07f  movzx   ebx, bx
0x18001e082  or      ebx, 80070000h
0x18001e088  mov     eax, ebx
0x18001e08a  jmp     short loc_18001E08E
0x18001e08c  xor     eax, eax
0x18001e08e  add     rsp, 40h
0x18001e092  pop     rbx
0x18001e093  retn
```
