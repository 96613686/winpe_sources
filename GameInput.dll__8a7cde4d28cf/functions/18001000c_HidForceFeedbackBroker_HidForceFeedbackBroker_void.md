# HidForceFeedbackBroker::~HidForceFeedbackBroker(void)

- ea: `0x18001000c`
- end: `0x1800100e5`
- name: `??1HidForceFeedbackBroker@@UEAA@XZ`
- size: `217`
- prototype: `void __fastcall(HidForceFeedbackBroker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010820`

## callees

- `0x180001008`
- `0x18001000c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800100c0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800100c0`

## string_xrefs

- `0x180010062`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`
- `0x180010057`: `HID force feedback broker destroyed`

## pseudocode

```c
void __fastcall HidForceFeedbackBroker::~HidForceFeedbackBroker(
        HidForceFeedbackBroker *this,
        __int64 a2,
        int a3,
        int a4)
{
  __int64 v5; // rcx
  HMODULE v6; // rcx
  int v7; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+58h] [rbp+10h] BYREF
  const char *v9; // [rsp+60h] [rbp+18h] BYREF
  const char *v10; // [rsp+68h] [rbp+20h] BYREF

  *(_QWORD *)this = &HidForceFeedbackBroker::`vftable';
  if ( (unsigned int)dword_180069000 > 4 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v7 = *((_DWORD *)this + 11);
    v9 = "HID force feedback broker destroyed";
    v10 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
    v8 = 15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)qword_18005DA78,
      a3,
      a4,
      (__int64)&v10,
      (__int64)&v8,
      (__int64)&v9,
      (__int64)&v7);
  }
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 3) = 0;
  }
  v6 = (HMODULE)*((_QWORD *)this + 2);
  if ( v6 )
  {
    FreeLibrary(v6);
    *((_QWORD *)this + 2) = 0;
  }
  *(_QWORD *)this = &RefCountedObjectBase<IHidForceFeebackBroker>::`vftable';
}

```

## disassembly

```asm
0x18001000c  mov     r11, rsp
0x18001000f  push    rbx
0x180010010  sub     rsp, 40h
0x180010014  lea     rax, ??_7HidForceFeedbackBroker@@6B@; const HidForceFeedbackBroker::`vftable'
0x18001001b  mov     rbx, rcx
0x18001001e  mov     [rcx], rax
0x180010021  mov     eax, cs:dword_180069000
0x180010027  cmp     eax, 4
0x18001002a  jbe     short loc_18001009A
0x18001002c  mov     rcx, cs:qword_180069018
0x180010033  mov     rax, cs:qword_180069010
0x18001003a  test    al, 8
0x18001003c  jz      short loc_18001009A
0x18001003e  mov     rax, rcx
0x180010041  and     eax, 8
0x180010044  cmp     rax, rcx
0x180010047  jnz     short loc_18001009A
0x180010049  mov     eax, [rbx+2Ch]
0x18001004c  lea     rdx, qword_18005DA78
0x180010053  mov     [rsp+48h+arg_0], eax
0x180010057  lea     rax, aHidForceFeedba_5; "HID force feedback broker destroyed"
0x18001005e  mov     [r11+18h], rax
0x180010062  lea     rax, aOnecoreXboxGam_36; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180010069  mov     [r11+20h], rax
0x18001006d  lea     rax, [r11+8]
0x180010071  mov     [r11-10h], rax
0x180010075  lea     rax, [r11+18h]
0x180010079  mov     [r11-18h], rax
0x18001007d  lea     rax, [r11+10h]
0x180010081  mov     [r11-20h], rax
0x180010085  lea     rax, [r11+20h]
0x180010089  mov     [r11-28h], rax
0x18001008d  mov     [rsp+48h+arg_8], 0Fh
0x180010095  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001009a  mov     rcx, [rbx+18h]
0x18001009e  test    rcx, rcx
0x1800100a1  jz      short loc_1800100B7
0x1800100a3  mov     rax, [rcx]
0x1800100a6  mov     rax, [rax+10h]
0x1800100aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100af  mov     qword ptr [rbx+18h], 0
0x1800100b7  mov     rcx, [rbx+10h]; hLibModule
0x1800100bb  test    rcx, rcx
0x1800100be  jz      short loc_1800100D4
0x1800100c0  call    cs:__imp_FreeLibrary
0x1800100c7  nop     dword ptr [rax+rax+00h]
0x1800100cc  mov     qword ptr [rbx+10h], 0
0x1800100d4  lea     rax, ??_7?$RefCountedObjectBase@UIHidForceFeebackBroker@@@@6B@; const RefCountedObjectBase<IHidForceFeebackBroker>::`vftable'
0x1800100db  mov     [rbx], rax
0x1800100de  add     rsp, 40h
0x1800100e2  pop     rbx
0x1800100e3  retn
```
