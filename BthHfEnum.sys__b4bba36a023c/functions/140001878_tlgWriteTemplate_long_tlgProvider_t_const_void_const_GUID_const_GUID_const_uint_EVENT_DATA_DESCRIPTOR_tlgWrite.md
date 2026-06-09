# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001878`
- end: `0x1400018ee`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002db70`
- `0x14002de78`

## callees

- `0x1400010f4`
- `0x14001adc0`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-58h] BYREF
  __int64 v8; // [rsp+50h] [rbp-38h]
  __int64 v9; // [rsp+58h] [rbp-30h]
  __int64 v10; // [rsp+60h] [rbp-28h]
  __int64 v11; // [rsp+68h] [rbp-20h]

  v10 = a6;
  v8 = a5;
  v11 = 4;
  v9 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140022000, a2, 0, 0, 4u, &v7);
}

```

## disassembly

```asm
0x140001878  mov     r11, rsp
0x14000187b  sub     rsp, 88h
0x140001882  mov     rax, cs:__security_cookie
0x140001889  xor     rax, rsp
0x14000188c  mov     [rsp+88h+var_18], rax
0x140001891  mov     rax, [rsp+88h+arg_28]
0x140001899  mov     ecx, 4
0x14000189e  mov     [r11-28h], rax
0x1400018a2  xor     r9d, r9d
0x1400018a5  mov     rax, [rsp+88h+arg_20]
0x1400018ad  xor     r8d, r8d
0x1400018b0  mov     [r11-38h], rax
0x1400018b4  lea     rax, [r11-58h]
0x1400018b8  mov     [r11-60h], rax
0x1400018bc  mov     [rsp+88h+var_68], ecx
0x1400018c0  mov     [r11-20h], rcx
0x1400018c4  lea     rcx, dword_140022000
0x1400018cb  mov     qword ptr [r11-30h], 8
0x1400018d3  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400018d8  mov     rcx, [rsp+88h+var_18]
0x1400018dd  xor     rcx, rsp; StackCookie
0x1400018e0  call    __security_check_cookie
0x1400018e5  add     rsp, 88h
0x1400018ec  retn
```
