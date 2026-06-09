# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800014e4`
- end: `0x1800015a2`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009040`

## callees

- `0x180001bdc`
- `0x180002bc0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  _BYTE v12[32]; // [rsp+30h] [rbp-81h] BYREF
  __int64 v13; // [rsp+50h] [rbp-61h]
  __int64 v14; // [rsp+58h] [rbp-59h]
  __int64 v15; // [rsp+60h] [rbp-51h]
  __int64 v16; // [rsp+68h] [rbp-49h]
  __int64 v17; // [rsp+70h] [rbp-41h]
  __int64 v18; // [rsp+78h] [rbp-39h]
  __int64 v19; // [rsp+80h] [rbp-31h]
  __int64 v20; // [rsp+88h] [rbp-29h]
  __int64 v21; // [rsp+90h] [rbp-21h]
  __int64 v22; // [rsp+98h] [rbp-19h]
  __int64 v23; // [rsp+A0h] [rbp-11h]
  __int64 v24; // [rsp+A8h] [rbp-9h]
  __int64 v25; // [rsp+B0h] [rbp-1h]
  __int64 v26; // [rsp+B8h] [rbp+7h]

  v25 = a11;
  v23 = a10;
  v21 = a9;
  v19 = a8;
  v17 = a7;
  v15 = a6;
  v13 = a5;
  v26 = 8;
  v24 = 4;
  v22 = 1;
  v20 = 2;
  v18 = 4;
  v16 = 4;
  v14 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 9, v12);
}

```

## disassembly

```asm
0x1800014e4  push    rbp
0x1800014e6  lea     rbp, [rsp-1Fh]
0x1800014eb  sub     rsp, 0D0h
0x1800014f2  mov     rax, cs:__security_cookie
0x1800014f9  xor     rax, rsp
0x1800014fc  mov     [rbp+1Fh+var_10], rax
0x180001500  mov     rax, [rbp+1Fh+arg_50]
0x180001504  xor     r9d, r9d
0x180001507  mov     [rbp+1Fh+var_20], rax
0x18000150b  xor     r8d, r8d
0x18000150e  mov     rax, [rbp+1Fh+arg_48]
0x180001512  mov     [rbp+1Fh+var_30], rax
0x180001516  mov     rax, [rbp+1Fh+arg_40]
0x18000151a  mov     [rbp+1Fh+var_40], rax
0x18000151e  mov     rax, [rbp+1Fh+arg_38]
0x180001522  mov     [rbp+1Fh+var_50], rax
0x180001526  mov     rax, [rbp+1Fh+arg_30]
0x18000152a  mov     [rbp+1Fh+var_60], rax
0x18000152e  mov     rax, [rbp+1Fh+arg_28]
0x180001532  mov     [rbp+1Fh+var_70], rax
0x180001536  mov     rax, [rbp+1Fh+arg_20]
0x18000153a  mov     [rbp+1Fh+var_80], rax
0x18000153e  lea     rax, [rsp+0D0h+var_A0]
0x180001543  mov     [rsp+0D0h+var_A8], rax
0x180001548  mov     [rsp+0D0h+var_B0], 9
0x180001550  mov     [rbp+1Fh+var_18], 8
0x180001558  mov     [rbp+1Fh+var_28], 4
0x180001560  mov     [rbp+1Fh+var_38], 1
0x180001568  mov     [rbp+1Fh+var_48], 2
0x180001570  mov     [rbp+1Fh+var_58], 4
0x180001578  mov     [rbp+1Fh+var_68], 4
0x180001580  mov     [rbp+1Fh+var_78], 4
0x180001588  call    _tlgWriteTransfer_EventWriteTransfer
0x18000158d  mov     rcx, [rbp+1Fh+var_10]
0x180001591  xor     rcx, rsp; StackCookie
0x180001594  call    __security_check_cookie
0x180001599  add     rsp, 0D0h
0x1800015a0  pop     rbp
0x1800015a1  retn
```
