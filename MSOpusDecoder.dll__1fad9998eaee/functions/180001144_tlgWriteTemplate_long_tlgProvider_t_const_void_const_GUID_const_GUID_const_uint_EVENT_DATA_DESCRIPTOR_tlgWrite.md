# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001144`
- end: `0x1800011d6`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bc80`

## callees

- `0x1800011dc`
- `0x1800018f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-68h] BYREF
  __int64 v9; // [rsp+50h] [rbp-48h]
  __int64 v10; // [rsp+58h] [rbp-40h]
  __int64 v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  __int64 v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  v13 = a7;
  v11 = a6;
  v9 = a5;
  v14 = 8;
  v12 = 4;
  v10 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180035090, a2, 0, 0, 5u, &v8);
}

```

## disassembly

```asm
0x180001144  mov     r11, rsp
0x180001147  sub     rsp, 98h
0x18000114e  mov     rax, cs:__security_cookie
0x180001155  xor     rax, rsp
0x180001158  mov     [rsp+98h+var_18], rax
0x180001160  mov     rax, [rsp+98h+arg_30]
0x180001168  lea     rcx, dword_180035090
0x18000116f  mov     [r11-28h], rax
0x180001173  xor     r9d, r9d
0x180001176  mov     rax, [rsp+98h+arg_28]
0x18000117e  xor     r8d, r8d
0x180001181  mov     [r11-38h], rax
0x180001185  mov     rax, [rsp+98h+arg_20]
0x18000118d  mov     [r11-48h], rax
0x180001191  lea     rax, [r11-68h]
0x180001195  mov     [r11-70h], rax
0x180001199  mov     [rsp+98h+var_78], 5
0x1800011a1  mov     qword ptr [r11-20h], 8
0x1800011a9  mov     qword ptr [r11-30h], 4
0x1800011b1  mov     qword ptr [r11-40h], 8
0x1800011b9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011be  mov     rcx, [rsp+98h+var_18]
0x1800011c6  xor     rcx, rsp; StackCookie
0x1800011c9  call    __security_check_cookie
0x1800011ce  add     rsp, 98h
0x1800011d5  retn
```
