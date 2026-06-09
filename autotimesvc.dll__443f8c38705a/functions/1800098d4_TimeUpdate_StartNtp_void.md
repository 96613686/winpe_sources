# TimeUpdate::StartNtp(void)

- ea: `0x1800098d4`
- end: `0x18000992c`
- name: `?StartNtp@TimeUpdate@@AEAAXXZ`
- size: `88`
- prototype: `void __fastcall(TimeUpdate *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800061ac`
- `0x1800084c4`

## callees

- `0x180001010`
- `0x1800012f0`
- `0x1800098d4`
- `0x18000b98c`

## pseudocode

```c
void __fastcall TimeUpdate::StartNtp(TimeUpdate *this)
{
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)word_1800167DA,
      0,
      0);
  _InterlockedExchange((volatile __int32 *)this + 15, 0);
  WNFNotificationDispatcher::Start((TimeUpdate *)((char *)this + 144));
}

```

## disassembly

```asm
0x1800098d4  push    rbx
0x1800098d6  sub     rsp, 20h
0x1800098da  mov     eax, cs:dword_18001C010
0x1800098e0  mov     rbx, rcx
0x1800098e3  cmp     eax, 4
0x1800098e6  jbe     short loc_180009916
0x1800098e8  mov     edx, 1
0x1800098ed  lea     rcx, dword_18001C010
0x1800098f4  call    _tlgKeywordOn
0x1800098f9  test    al, al
0x1800098fb  jz      short loc_180009916
0x1800098fd  xor     r9d, r9d
0x180009900  lea     rdx, word_1800167DA
0x180009907  xor     r8d, r8d
0x18000990a  lea     rcx, dword_18001C010
0x180009911  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180009916  xor     eax, eax
0x180009918  lea     rcx, [rbx+90h]; this
0x18000991f  xchg    eax, [rbx+3Ch]
0x180009922  add     rsp, 20h
0x180009926  pop     rbx
0x180009927  jmp     ?Start@WNFNotificationDispatcher@@QEAAXXZ; WNFNotificationDispatcher::Start(void)
```
