# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001248`
- end: `0x1400012dd`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@43@Z`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cb40`
- `0x14000cbd0`

## callees

- `0x1400010f4`
- `0x14001adc0`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-39h] BYREF
  __int64 v10; // [rsp+50h] [rbp-19h]
  __int64 v11; // [rsp+58h] [rbp-11h]
  __int64 v12; // [rsp+60h] [rbp-9h]
  __int64 v13; // [rsp+68h] [rbp-1h]
  __int64 v14; // [rsp+70h] [rbp+7h]
  __int64 v15; // [rsp+78h] [rbp+Fh]
  __int64 v16; // [rsp+80h] [rbp+17h]
  __int64 v17; // [rsp+88h] [rbp+1Fh]

  v16 = a8;
  v14 = a7;
  v12 = a6;
  v10 = a5;
  v17 = 8;
  v15 = 4;
  v13 = 4;
  v11 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140022000, a2, 0, 0, 6u, &v9);
}

```

## disassembly

```asm
0x140001248  push    rbp
0x14000124a  lea     rbp, [rsp-37h]
0x14000124f  sub     rsp, 0A0h
0x140001256  mov     rax, cs:__security_cookie
0x14000125d  xor     rax, rsp
0x140001260  mov     [rbp+37h+var_10], rax
0x140001264  mov     rax, [rbp+37h+arg_38]
0x140001268  lea     rcx, dword_140022000
0x14000126f  mov     [rbp+37h+var_20], rax
0x140001273  xor     r9d, r9d
0x140001276  mov     rax, [rbp+37h+arg_30]
0x14000127a  xor     r8d, r8d
0x14000127d  mov     [rbp+37h+var_30], rax
0x140001281  mov     rax, [rbp+37h+arg_28]
0x140001285  mov     [rbp+37h+var_40], rax
0x140001289  mov     rax, [rbp+37h+arg_20]
0x14000128d  mov     [rbp+37h+var_50], rax
0x140001291  lea     rax, [rbp+37h+var_70]
0x140001295  mov     [rsp+0A0h+var_78], rax
0x14000129a  mov     [rsp+0A0h+var_80], 6
0x1400012a2  mov     [rbp+37h+var_18], 8
0x1400012aa  mov     [rbp+37h+var_28], 4
0x1400012b2  mov     [rbp+37h+var_38], 4
0x1400012ba  mov     [rbp+37h+var_48], 8
0x1400012c2  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400012c7  mov     rcx, [rbp+37h+var_10]
0x1400012cb  xor     rcx, rsp; StackCookie
0x1400012ce  call    __security_check_cookie
0x1400012d3  add     rsp, 0A0h
0x1400012da  pop     rbp
0x1400012db  retn
```
