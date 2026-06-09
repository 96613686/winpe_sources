# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800010c4`
- end: `0x180001156`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `146`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ee38`
- `0x18000eec8`

## callees

- `0x180001008`
- `0x1800107c0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        int a2,
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
  v14 = 4;
  v12 = 4;
  v10 = 8;
  return tlgWriteTransfer_EventWriteTransfer((int)&dword_18001B000, a2, 0, 0, 5u, &v8);
}

```

## disassembly

```asm
0x1800010c4  mov     r11, rsp
0x1800010c7  sub     rsp, 98h
0x1800010ce  mov     rax, cs:__security_cookie
0x1800010d5  xor     rax, rsp
0x1800010d8  mov     [rsp+98h+var_18], rax
0x1800010e0  mov     rax, [rsp+98h+arg_30]
0x1800010e8  lea     rcx, dword_18001B000; int
0x1800010ef  mov     [r11-28h], rax
0x1800010f3  xor     r9d, r9d; int
0x1800010f6  mov     rax, [rsp+98h+arg_28]
0x1800010fe  xor     r8d, r8d; int
0x180001101  mov     [r11-38h], rax
0x180001105  mov     rax, [rsp+98h+arg_20]
0x18000110d  mov     [r11-48h], rax
0x180001111  lea     rax, [r11-68h]
0x180001115  mov     [r11-70h], rax
0x180001119  mov     [rsp+98h+var_78], 5; ULONG
0x180001121  mov     qword ptr [r11-20h], 4
0x180001129  mov     qword ptr [r11-30h], 4
0x180001131  mov     qword ptr [r11-40h], 8
0x180001139  call    _tlgWriteTransfer_EventWriteTransfer
0x18000113e  mov     rcx, [rsp+98h+var_18]
0x180001146  xor     rcx, rsp; StackCookie
0x180001149  call    __security_check_cookie
0x18000114e  add     rsp, 98h
0x180001155  retn
```
