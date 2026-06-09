# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000115c`
- end: `0x1400012fe`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@U3@U3@U3@U?$_tlgWrapperByVal@$03@@U3@U4@U4@U4@U4@U4@U4@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@555AEBU?$_tlgWrapperByVal@$03@@5666666566@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400030e0`

## callees

- `0x1400010b8`
- `0x14000ddc0`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21)
{
  __int64 v21; // rcx
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  __int64 v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  __int64 v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  __int64 v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  __int64 v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  __int64 v50; // [rsp+120h] [rbp+20h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  __int64 v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  __int64 v54; // [rsp+140h] [rbp+40h]
  __int64 v55; // [rsp+148h] [rbp+48h]
  __int64 v56; // [rsp+150h] [rbp+50h]
  __int64 v57; // [rsp+158h] [rbp+58h]

  v56 = a21;
  v54 = a20;
  v52 = a19;
  v50 = a18;
  v48 = a17;
  v46 = a16;
  v44 = a15;
  v42 = a14;
  v40 = a13;
  v38 = a12;
  v36 = a11;
  v34 = a10;
  v32 = a9;
  v30 = a8;
  v28 = a7;
  v57 = 4;
  v55 = 4;
  v53 = 2;
  v21 = *a6;
  v24 = a5;
  v26 = v21;
  v51 = 4;
  v49 = 4;
  v47 = 4;
  v45 = 4;
  v43 = 4;
  v41 = 4;
  v39 = 2;
  v37 = 4;
  v35 = 2;
  v33 = 2;
  v31 = 2;
  v29 = 2;
  v27 = 16;
  v25 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140013000, a2, 0, 0, 0x13u, &v23);
}

```

## disassembly

```asm
0x14000115c  push    rbp
0x14000115e  lea     rbp, [rsp-70h]
0x140001163  sub     rsp, 170h
0x14000116a  mov     rax, cs:__security_cookie
0x140001171  xor     rax, rsp
0x140001174  mov     [rbp+70h+var_10], rax
0x140001178  mov     rax, [rbp+70h+arg_A0]
0x14000117f  xor     r9d, r9d
0x140001182  mov     [rbp+70h+var_20], rax
0x140001186  xor     r8d, r8d
0x140001189  mov     rax, [rbp+70h+arg_98]
0x140001190  mov     [rbp+70h+var_30], rax
0x140001194  mov     rax, [rbp+70h+arg_90]
0x14000119b  mov     [rbp+70h+var_40], rax
0x14000119f  mov     rax, [rbp+70h+arg_88]
0x1400011a6  mov     [rbp+70h+var_50], rax
0x1400011aa  mov     rax, [rbp+70h+arg_80]
0x1400011b1  mov     [rbp+70h+var_60], rax
0x1400011b5  mov     rax, [rbp+70h+arg_78]
0x1400011bc  mov     [rbp+70h+var_70], rax
0x1400011c0  mov     rax, [rbp+70h+arg_70]
0x1400011c7  mov     [rbp+70h+var_80], rax
0x1400011cb  mov     rax, [rbp+70h+arg_68]
0x1400011d2  mov     [rbp+70h+var_90], rax
0x1400011d6  mov     rax, [rbp+70h+arg_60]
0x1400011dd  mov     [rbp+70h+var_A0], rax
0x1400011e1  mov     rax, [rbp+70h+arg_58]
0x1400011e8  mov     [rbp+70h+var_B0], rax
0x1400011ec  mov     rax, [rbp+70h+arg_50]
0x1400011f3  mov     [rbp+70h+var_C0], rax
0x1400011f7  mov     rax, [rbp+70h+arg_48]
0x1400011fe  mov     [rbp+70h+var_D0], rax
0x140001202  mov     rax, [rbp+70h+arg_40]
0x140001209  mov     [rbp+70h+var_E0], rax
0x14000120d  mov     rax, [rbp+70h+arg_38]
0x140001214  mov     [rbp+70h+var_F0], rax
0x140001218  mov     rax, [rbp+70h+arg_30]
0x14000121f  mov     [rsp+170h+var_100], rax
0x140001224  mov     rax, [rbp+70h+arg_28]
0x14000122b  mov     [rbp+70h+var_18], 4
0x140001233  mov     [rbp+70h+var_28], 4
0x14000123b  mov     [rbp+70h+var_38], 2
0x140001243  mov     rcx, [rax]
0x140001246  mov     rax, [rbp+70h+arg_20]
0x14000124d  mov     [rsp+170h+var_120], rax
0x140001252  lea     rax, [rsp+170h+var_140]
0x140001257  mov     [rsp+170h+var_110], rcx
0x14000125c  lea     rcx, dword_140013000
0x140001263  mov     [rsp+170h+var_148], rax
0x140001268  mov     [rsp+170h+var_150], 13h
0x140001270  mov     [rbp+70h+var_48], 4
0x140001278  mov     [rbp+70h+var_58], 4
0x140001280  mov     [rbp+70h+var_68], 4
0x140001288  mov     [rbp+70h+var_78], 4
0x140001290  mov     [rbp+70h+var_88], 4
0x140001298  mov     [rbp+70h+var_98], 4
0x1400012a0  mov     [rbp+70h+var_A8], 2
0x1400012a8  mov     [rbp+70h+var_B8], 4
0x1400012b0  mov     [rbp+70h+var_C8], 2
0x1400012b8  mov     [rbp+70h+var_D8], 2
0x1400012c0  mov     [rbp+70h+var_E8], 2
0x1400012c8  mov     [rsp+170h+var_F8], 2
0x1400012d1  mov     [rsp+170h+var_108], 10h
0x1400012da  mov     [rsp+170h+var_118], 8
0x1400012e3  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400012e8  mov     rcx, [rbp+70h+var_10]
0x1400012ec  xor     rcx, rsp; StackCookie
0x1400012ef  call    __security_check_cookie
0x1400012f4  add     rsp, 170h
0x1400012fb  pop     rbp
0x1400012fc  retn
```
