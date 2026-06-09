# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800010c8`
- end: `0x18000113d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `117`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b838`
- `0x18001b994`
- `0x18001bc80`
- `0x18001bf50`
- `0x18001c3c0`
- `0x18001cc40`
- `0x18001cce0`
- `0x18001ce80`
- `0x18001d738`
- `0x18001d860`
- `0x18001dd40`
- `0x18001dda0`
- `0x18001dfc0`
- `0x18001e360`
- `0x18001e808`

## callees

- `0x1800011dc`
- `0x1800018f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
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
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180035090, a2, 0, 0, 4u, &v7);
}

```

## disassembly

```asm
0x1800010c8  mov     r11, rsp
0x1800010cb  sub     rsp, 88h
0x1800010d2  mov     rax, cs:__security_cookie
0x1800010d9  xor     rax, rsp
0x1800010dc  mov     [rsp+88h+var_18], rax
0x1800010e1  mov     rax, [rsp+88h+arg_28]
0x1800010e9  mov     ecx, 4
0x1800010ee  mov     [r11-28h], rax
0x1800010f2  xor     r9d, r9d
0x1800010f5  mov     rax, [rsp+88h+arg_20]
0x1800010fd  xor     r8d, r8d
0x180001100  mov     [r11-38h], rax
0x180001104  lea     rax, [r11-58h]
0x180001108  mov     [r11-60h], rax
0x18000110c  mov     [rsp+88h+var_68], ecx
0x180001110  mov     [r11-20h], rcx
0x180001114  lea     rcx, dword_180035090
0x18000111b  mov     qword ptr [r11-30h], 8
0x180001123  call    _tlgWriteTransfer_EventWriteTransfer
0x180001128  mov     rcx, [rsp+88h+var_18]
0x18000112d  xor     rcx, rsp; StackCookie
0x180001130  call    __security_check_cookie
0x180001135  add     rsp, 88h
0x18000113c  retn
```
