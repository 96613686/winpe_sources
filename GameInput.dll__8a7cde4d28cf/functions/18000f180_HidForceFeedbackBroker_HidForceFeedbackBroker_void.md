# HidForceFeedbackBroker::HidForceFeedbackBroker(void)

- ea: `0x18000f180`
- end: `0x18000f23d`
- name: `??0HidForceFeedbackBroker@@QEAA@XZ`
- size: `189`
- prototype: `HidForceFeedbackBroker *__fastcall(HidForceFeedbackBroker *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013be0`

## callees

- `0x180001008`
- `0x18000f180`

## string_xrefs

- `0x18000f1f0`: `HID force feedback broker created`
- `0x18000f1fb`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`

## pseudocode

```c
HidForceFeedbackBroker *__fastcall HidForceFeedbackBroker::HidForceFeedbackBroker(
        HidForceFeedbackBroker *this,
        __int64 a2,
        int a3,
        int a4)
{
  int v6; // [rsp+50h] [rbp+8h] BYREF
  int v7; // [rsp+58h] [rbp+10h] BYREF
  const char *v8; // [rsp+60h] [rbp+18h] BYREF
  const char *v9; // [rsp+68h] [rbp+20h] BYREF

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &HidForceFeedbackBroker::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_DWORD *)this + 11) = _InterlockedIncrement((volatile signed __int32 *)this + 10);
  if ( (unsigned int)dword_180069000 > 4 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v6 = *((_DWORD *)this + 11);
    v8 = "HID force feedback broker created";
    v9 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
    v7 = 8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)byte_18005B113,
      a3,
      a4,
      (__int64)&v9,
      (__int64)&v7,
      (__int64)&v8,
      (__int64)&v6);
  }
  return this;
}

```

## disassembly

```asm
0x18000f180  mov     r11, rsp
0x18000f183  push    rbx
0x18000f184  sub     rsp, 40h
0x18000f188  mov     rbx, rcx
0x18000f18b  mov     eax, 1
0x18000f190  mov     [rcx+8], eax
0x18000f193  lea     rcx, ??_7HidForceFeedbackBroker@@6B@; const HidForceFeedbackBroker::`vftable'
0x18000f19a  mov     [rbx], rcx
0x18000f19d  xor     ecx, ecx
0x18000f19f  mov     [rbx+10h], rcx
0x18000f1a3  mov     [rbx+18h], rcx
0x18000f1a7  mov     [rbx+20h], rcx
0x18000f1ab  mov     [rbx+28h], ecx
0x18000f1ae  nop
0x18000f1af  lock xadd [rbx+28h], eax
0x18000f1b4  inc     eax
0x18000f1b6  nop
0x18000f1b7  mov     [rbx+2Ch], eax
0x18000f1ba  mov     eax, cs:dword_180069000
0x18000f1c0  cmp     eax, 4
0x18000f1c3  jbe     short loc_18000F233
0x18000f1c5  mov     rcx, cs:qword_180069018
0x18000f1cc  mov     rax, cs:qword_180069010
0x18000f1d3  test    al, 8
0x18000f1d5  jz      short loc_18000F233
0x18000f1d7  mov     rax, rcx
0x18000f1da  and     eax, 8
0x18000f1dd  cmp     rax, rcx
0x18000f1e0  jnz     short loc_18000F233
0x18000f1e2  mov     eax, [rbx+2Ch]
0x18000f1e5  lea     rdx, byte_18005B113
0x18000f1ec  mov     [rsp+48h+arg_0], eax
0x18000f1f0  lea     rax, aHidForceFeedba_12; "HID force feedback broker created"
0x18000f1f7  mov     [r11+18h], rax
0x18000f1fb  lea     rax, aOnecoreXboxGam_36; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x18000f202  mov     [r11+20h], rax
0x18000f206  lea     rax, [r11+8]
0x18000f20a  mov     [r11-10h], rax
0x18000f20e  lea     rax, [r11+18h]
0x18000f212  mov     [r11-18h], rax
0x18000f216  lea     rax, [r11+10h]
0x18000f21a  mov     [r11-20h], rax
0x18000f21e  lea     rax, [r11+20h]
0x18000f222  mov     [r11-28h], rax
0x18000f226  mov     [rsp+48h+arg_8], 8
0x18000f22e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000f233  mov     rax, rbx
0x18000f236  add     rsp, 40h
0x18000f23a  pop     rbx
0x18000f23b  retn
```
