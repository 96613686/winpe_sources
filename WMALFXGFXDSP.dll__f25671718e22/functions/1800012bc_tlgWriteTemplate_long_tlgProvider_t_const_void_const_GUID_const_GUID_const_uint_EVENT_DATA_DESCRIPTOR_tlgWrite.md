# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)

- ea: `0x1800012bc`
- end: `0x180001352`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180076b98`
- `0x180076f6c`

## callees

- `0x1800017d8`
- `0x180015190`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 *a8)
{
  __int64 v9; // rcx
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-39h] BYREF
  __int64 v12; // [rsp+50h] [rbp-19h]
  __int64 v13; // [rsp+58h] [rbp-11h]
  __int64 v14; // [rsp+60h] [rbp-9h]
  __int64 v15; // [rsp+68h] [rbp-1h]
  __int64 v16; // [rsp+70h] [rbp+7h]
  __int64 v17; // [rsp+78h] [rbp+Fh]
  __int64 v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]

  v19 = 16;
  v17 = 4;
  v15 = 4;
  v9 = *a8;
  v16 = a7;
  v14 = a6;
  v12 = a5;
  v18 = v9;
  v13 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 6u, &v11);
}

```

## disassembly

```asm
0x1800012bc  push    rbp
0x1800012be  lea     rbp, [rsp-37h]
0x1800012c3  sub     rsp, 0A0h
0x1800012ca  mov     rax, cs:__security_cookie
0x1800012d1  xor     rax, rsp
0x1800012d4  mov     [rbp+37h+var_10], rax
0x1800012d8  mov     rax, [rbp+37h+arg_38]
0x1800012dc  mov     r10, rcx
0x1800012df  xor     r9d, r9d
0x1800012e2  mov     [rbp+37h+var_18], 10h
0x1800012ea  xor     r8d, r8d
0x1800012ed  mov     [rbp+37h+var_28], 4
0x1800012f5  mov     [rbp+37h+var_38], 4
0x1800012fd  mov     rcx, [rax]
0x180001300  mov     rax, [rbp+37h+arg_30]
0x180001304  mov     [rbp+37h+var_30], rax
0x180001308  mov     rax, [rbp+37h+arg_28]
0x18000130c  mov     [rbp+37h+var_40], rax
0x180001310  mov     rax, [rbp+37h+arg_20]
0x180001314  mov     [rbp+37h+var_50], rax
0x180001318  lea     rax, [rbp+37h+var_70]
0x18000131c  mov     [rbp+37h+var_20], rcx
0x180001320  mov     rcx, r10
0x180001323  mov     [rsp+0A0h+var_78], rax
0x180001328  mov     [rsp+0A0h+var_80], 6
0x180001330  mov     [rbp+37h+var_48], 8
0x180001338  call    _tlgWriteTransfer_EventWriteTransfer
0x18000133d  mov     rcx, [rbp+37h+var_10]
0x180001341  xor     rcx, rsp; StackCookie
0x180001344  call    __security_check_cookie
0x180001349  add     rsp, 0A0h
0x180001350  pop     rbp
0x180001351  retn
```
