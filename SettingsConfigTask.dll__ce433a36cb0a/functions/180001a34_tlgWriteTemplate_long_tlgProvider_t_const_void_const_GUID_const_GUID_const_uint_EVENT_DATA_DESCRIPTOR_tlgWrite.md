# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)

- ea: `0x180001a34`
- end: `0x180001a8b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18001845c`
- `0x1800184b4`
- `0x18001850c`
- `0x180018564`
- `0x1800185bc`
- `0x180018614`
- `0x18001866c`
- `0x1800186c4`
- `0x180019758`

## callees

- `0x180001738`
- `0x1800021d0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD v6[6]; // [rsp+30h] [rbp-48h] BYREF

  v6[4] = a5;
  v6[5] = 8;
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, _QWORD *))tlgWriteTransfer_EventWriteTransfer)(
           a1,
           a2,
           0,
           0,
           3,
           v6);
}

```

## disassembly

```asm
0x180001a34  mov     r11, rsp
0x180001a37  sub     rsp, 78h
0x180001a3b  mov     rax, cs:__security_cookie
0x180001a42  xor     rax, rsp
0x180001a45  mov     [rsp+78h+var_18], rax
0x180001a4a  mov     rax, [rsp+78h+arg_20]
0x180001a52  xor     r9d, r9d
0x180001a55  mov     [r11-28h], rax
0x180001a59  xor     r8d, r8d
0x180001a5c  lea     rax, [r11-48h]
0x180001a60  mov     qword ptr [r11-20h], 8
0x180001a68  mov     [r11-50h], rax
0x180001a6c  mov     [rsp+78h+var_58], 3
0x180001a74  call    _tlgWriteTransfer_EventWriteTransfer
0x180001a79  mov     rcx, [rsp+78h+var_18]
0x180001a7e  xor     rcx, rsp; StackCookie
0x180001a81  call    __security_check_cookie
0x180001a86  add     rsp, 78h
0x180001a8a  retn
```
