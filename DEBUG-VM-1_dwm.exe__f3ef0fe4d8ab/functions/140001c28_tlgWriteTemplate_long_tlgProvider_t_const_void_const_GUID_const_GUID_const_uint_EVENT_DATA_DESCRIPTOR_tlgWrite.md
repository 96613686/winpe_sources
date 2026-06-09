# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)

- ea: `0x140001c28`
- end: `0x140001ca3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e994`

## callees

- `0x140001d5c`
- `0x140005530`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6)
{
  __int64 v6; // rcx
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-58h] BYREF
  __int64 v9; // [rsp+50h] [rbp-38h]
  __int64 v10; // [rsp+58h] [rbp-30h]
  __int64 v11; // [rsp+60h] [rbp-28h]
  __int64 v12; // [rsp+68h] [rbp-20h]

  v12 = 16;
  v10 = 8;
  v6 = *a6;
  v9 = a5;
  v11 = v6;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_1400180D8, a2, 0, 0, 4u, &v8);
}

```

## disassembly

```asm
0x140001c28  mov     r11, rsp
0x140001c2b  sub     rsp, 88h
0x140001c32  mov     rax, cs:__security_cookie
0x140001c39  xor     rax, rsp
0x140001c3c  mov     [rsp+88h+var_18], rax
0x140001c41  mov     rax, [rsp+88h+arg_28]
0x140001c49  xor     r9d, r9d
0x140001c4c  xor     r8d, r8d
0x140001c4f  mov     qword ptr [r11-20h], 10h
0x140001c57  mov     qword ptr [r11-30h], 8
0x140001c5f  mov     rcx, [rax]
0x140001c62  mov     rax, [rsp+88h+arg_20]
0x140001c6a  mov     [r11-38h], rax
0x140001c6e  lea     rax, [r11-58h]
0x140001c72  mov     [r11-28h], rcx
0x140001c76  lea     rcx, dword_1400180D8
0x140001c7d  mov     [r11-60h], rax
0x140001c81  mov     [rsp+88h+var_68], 4
0x140001c89  call    _tlgWriteTransfer_EventWriteTransfer
0x140001c8e  mov     rcx, [rsp+88h+var_18]
0x140001c93  xor     rcx, rsp; StackCookie
0x140001c96  call    __security_check_cookie
0x140001c9b  add     rsp, 88h
0x140001ca2  retn
```
