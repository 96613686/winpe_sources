# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1400013c0`
- end: `0x1400014bc`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44444443@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cc60`

## callees

- `0x1400010f4`
- `0x14001adc0`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14)
{
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-C9h] BYREF
  __int64 v16; // [rsp+50h] [rbp-A9h]
  __int64 v17; // [rsp+58h] [rbp-A1h]
  __int64 v18; // [rsp+60h] [rbp-99h]
  __int64 v19; // [rsp+68h] [rbp-91h]
  __int64 v20; // [rsp+70h] [rbp-89h]
  __int64 v21; // [rsp+78h] [rbp-81h]
  __int64 v22; // [rsp+80h] [rbp-79h]
  __int64 v23; // [rsp+88h] [rbp-71h]
  __int64 v24; // [rsp+90h] [rbp-69h]
  __int64 v25; // [rsp+98h] [rbp-61h]
  __int64 v26; // [rsp+A0h] [rbp-59h]
  __int64 v27; // [rsp+A8h] [rbp-51h]
  __int64 v28; // [rsp+B0h] [rbp-49h]
  __int64 v29; // [rsp+B8h] [rbp-41h]
  __int64 v30; // [rsp+C0h] [rbp-39h]
  __int64 v31; // [rsp+C8h] [rbp-31h]
  __int64 v32; // [rsp+D0h] [rbp-29h]
  __int64 v33; // [rsp+D8h] [rbp-21h]
  __int64 v34; // [rsp+E0h] [rbp-19h]
  __int64 v35; // [rsp+E8h] [rbp-11h]

  v34 = a14;
  v32 = a13;
  v30 = a12;
  v28 = a11;
  v26 = a10;
  v24 = a9;
  v22 = a8;
  v20 = a7;
  v18 = a6;
  v16 = a5;
  v35 = 8;
  v33 = 4;
  v31 = 4;
  v29 = 4;
  v27 = 4;
  v25 = 4;
  v23 = 4;
  v21 = 4;
  v19 = 4;
  v17 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140022000, a2, 0, 0, 0xCu, &v15);
}

```

## disassembly

```asm
0x1400013c0  push    rbp
0x1400013c2  lea     rbp, [rsp-7]
0x1400013c7  sub     rsp, 100h
0x1400013ce  mov     rax, cs:__security_cookie
0x1400013d5  xor     rax, rsp
0x1400013d8  mov     [rbp+7+var_10], rax
0x1400013dc  mov     rax, [rbp+7+arg_68]
0x1400013e0  lea     rcx, dword_140022000
0x1400013e7  mov     [rbp+7+var_20], rax
0x1400013eb  xor     r9d, r9d
0x1400013ee  mov     rax, [rbp+7+arg_60]
0x1400013f2  xor     r8d, r8d
0x1400013f5  mov     [rbp+7+var_30], rax
0x1400013f9  mov     rax, [rbp+7+arg_58]
0x1400013fd  mov     [rbp+7+var_40], rax
0x140001401  mov     rax, [rbp+7+arg_50]
0x140001405  mov     [rbp+7+var_50], rax
0x140001409  mov     rax, [rbp+7+arg_48]
0x14000140d  mov     [rbp+7+var_60], rax
0x140001411  mov     rax, [rbp+7+arg_40]
0x140001415  mov     [rbp+7+var_70], rax
0x140001419  mov     rax, [rbp+7+arg_38]
0x14000141d  mov     [rbp+7+var_80], rax
0x140001421  mov     rax, [rbp+7+arg_30]
0x140001425  mov     [rsp+100h+var_90], rax
0x14000142a  mov     rax, [rbp+7+arg_28]
0x14000142e  mov     [rsp+100h+var_A0], rax
0x140001433  mov     rax, [rbp+7+arg_20]
0x140001437  mov     [rsp+100h+var_B0], rax
0x14000143c  lea     rax, [rsp+100h+var_D0]
0x140001441  mov     [rsp+100h+var_D8], rax
0x140001446  mov     [rsp+100h+var_E0], 0Ch
0x14000144e  mov     [rbp+7+var_18], 8
0x140001456  mov     [rbp+7+var_28], 4
0x14000145e  mov     [rbp+7+var_38], 4
0x140001466  mov     [rbp+7+var_48], 4
0x14000146e  mov     [rbp+7+var_58], 4
0x140001476  mov     [rbp+7+var_68], 4
0x14000147e  mov     [rbp+7+var_78], 4
0x140001486  mov     [rsp+100h+var_88], 4
0x14000148f  mov     [rsp+100h+var_98], 4
0x140001498  mov     [rsp+100h+var_A8], 8
0x1400014a1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400014a6  mov     rcx, [rbp+7+var_10]
0x1400014aa  xor     rcx, rsp; StackCookie
0x1400014ad  call    __security_check_cookie
0x1400014b2  add     rsp, 100h
0x1400014b9  pop     rbp
0x1400014ba  retn
```
