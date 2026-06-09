# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001198`
- end: `0x140001242`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3344@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400114e0`

## callees

- `0x1400010f4`
- `0x14001adc0`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-69h] BYREF
  __int64 v12; // [rsp+50h] [rbp-49h]
  __int64 v13; // [rsp+58h] [rbp-41h]
  __int64 v14; // [rsp+60h] [rbp-39h]
  __int64 v15; // [rsp+68h] [rbp-31h]
  __int64 v16; // [rsp+70h] [rbp-29h]
  __int64 v17; // [rsp+78h] [rbp-21h]
  __int64 v18; // [rsp+80h] [rbp-19h]
  __int64 v19; // [rsp+88h] [rbp-11h]
  __int64 v20; // [rsp+90h] [rbp-9h]
  __int64 v21; // [rsp+98h] [rbp-1h]
  __int64 v22; // [rsp+A0h] [rbp+7h]
  __int64 v23; // [rsp+A8h] [rbp+Fh]

  v22 = a10;
  v20 = a9;
  v18 = a8;
  v16 = a7;
  v14 = a6;
  v12 = a5;
  v19 = 8;
  v17 = 8;
  v13 = 8;
  v23 = 4;
  v21 = 4;
  v15 = 4;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140022000, a2, 0, 0, 8u, &v11);
}

```

## disassembly

```asm
0x140001198  push    rbp
0x14000119a  lea     rbp, [rsp-27h]
0x14000119f  sub     rsp, 0C0h
0x1400011a6  mov     rax, cs:__security_cookie
0x1400011ad  xor     rax, rsp
0x1400011b0  mov     [rbp+27h+var_10], rax
0x1400011b4  mov     rax, [rbp+27h+arg_48]
0x1400011b8  mov     ecx, 8
0x1400011bd  mov     [rbp+27h+var_20], rax
0x1400011c1  xor     r9d, r9d
0x1400011c4  mov     rax, [rbp+27h+arg_40]
0x1400011c8  xor     r8d, r8d
0x1400011cb  mov     [rbp+27h+var_30], rax
0x1400011cf  mov     rax, [rbp+27h+arg_38]
0x1400011d3  mov     [rbp+27h+var_40], rax
0x1400011d7  mov     rax, [rbp+27h+arg_30]
0x1400011db  mov     [rbp+27h+var_50], rax
0x1400011df  mov     rax, [rbp+27h+arg_28]
0x1400011e3  mov     [rbp+27h+var_60], rax
0x1400011e7  mov     rax, [rbp+27h+arg_20]
0x1400011eb  mov     [rbp+27h+var_70], rax
0x1400011ef  lea     rax, [rbp+27h+var_90]
0x1400011f3  mov     [rsp+0C0h+var_98], rax
0x1400011f8  mov     [rsp+0C0h+var_A0], ecx
0x1400011fc  mov     [rbp+27h+var_38], rcx
0x140001200  mov     [rbp+27h+var_48], rcx
0x140001204  mov     [rbp+27h+var_68], rcx
0x140001208  lea     rcx, dword_140022000
0x14000120f  mov     [rbp+27h+var_18], 4
0x140001217  mov     [rbp+27h+var_28], 4
0x14000121f  mov     [rbp+27h+var_58], 4
0x140001227  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000122c  mov     rcx, [rbp+27h+var_10]
0x140001230  xor     rcx, rsp; StackCookie
0x140001233  call    __security_check_cookie
0x140001238  add     rsp, 0C0h
0x14000123f  pop     rbp
0x140001240  retn
```
