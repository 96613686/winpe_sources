# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001304`
- end: `0x1400014b9`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@U3@U3@U3@U?$_tlgWrapperByVal@$03@@U3@U4@U4@U4@U4@U4@U4@U3@U4@U?$_tlgWrapperByVal@$00@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@555AEBU?$_tlgWrapperByVal@$03@@566666656AEBU?$_tlgWrapperByVal@$00@@6@Z`
- size: `437`
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
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
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
        __int64 a21,
        __int64 a22)
{
  __int64 v22; // rcx
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  __int64 v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  __int64 v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  __int64 v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  __int64 v49; // [rsp+110h] [rbp+10h]
  __int64 v50; // [rsp+118h] [rbp+18h]
  __int64 v51; // [rsp+120h] [rbp+20h]
  __int64 v52; // [rsp+128h] [rbp+28h]
  __int64 v53; // [rsp+130h] [rbp+30h]
  __int64 v54; // [rsp+138h] [rbp+38h]
  __int64 v55; // [rsp+140h] [rbp+40h]
  __int64 v56; // [rsp+148h] [rbp+48h]
  __int64 v57; // [rsp+150h] [rbp+50h]
  __int64 v58; // [rsp+158h] [rbp+58h]
  __int64 v59; // [rsp+160h] [rbp+60h]
  __int64 v60; // [rsp+168h] [rbp+68h]

  v59 = a22;
  v57 = a21;
  v55 = a20;
  v53 = a19;
  v51 = a18;
  v49 = a17;
  v47 = a16;
  v45 = a15;
  v43 = a14;
  v41 = a13;
  v39 = a12;
  v37 = a11;
  v35 = a10;
  v33 = a9;
  v31 = a8;
  v29 = a7;
  v60 = 4;
  v58 = 1;
  v56 = 4;
  v22 = *a6;
  v25 = a5;
  v27 = v22;
  v54 = 2;
  v52 = 4;
  v50 = 4;
  v48 = 4;
  v46 = 4;
  v44 = 4;
  v42 = 4;
  v40 = 2;
  v38 = 4;
  v36 = 2;
  v34 = 2;
  v32 = 2;
  v30 = 2;
  v28 = 16;
  v26 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140013000, a2, 0, 0, 0x14u, &v24);
}

```

## disassembly

```asm
0x140001304  push    rbp
0x140001306  lea     rbp, [rsp-80h]
0x14000130b  sub     rsp, 180h
0x140001312  mov     rax, cs:__security_cookie
0x140001319  xor     rax, rsp
0x14000131c  mov     [rbp+80h+var_10], rax
0x140001320  mov     rax, [rbp+80h+arg_A8]
0x140001327  xor     r9d, r9d
0x14000132a  mov     [rbp+80h+var_20], rax
0x14000132e  xor     r8d, r8d
0x140001331  mov     rax, [rbp+80h+arg_A0]
0x140001338  mov     [rbp+80h+var_30], rax
0x14000133c  mov     rax, [rbp+80h+arg_98]
0x140001343  mov     [rbp+80h+var_40], rax
0x140001347  mov     rax, [rbp+80h+arg_90]
0x14000134e  mov     [rbp+80h+var_50], rax
0x140001352  mov     rax, [rbp+80h+arg_88]
0x140001359  mov     [rbp+80h+var_60], rax
0x14000135d  mov     rax, [rbp+80h+arg_80]
0x140001364  mov     [rbp+80h+var_70], rax
0x140001368  mov     rax, [rbp+80h+arg_78]
0x14000136f  mov     [rbp+80h+var_80], rax
0x140001373  mov     rax, [rbp+80h+arg_70]
0x14000137a  mov     [rbp+80h+var_90], rax
0x14000137e  mov     rax, [rbp+80h+arg_68]
0x140001385  mov     [rbp+80h+var_A0], rax
0x140001389  mov     rax, [rbp+80h+arg_60]
0x140001390  mov     [rbp+80h+var_B0], rax
0x140001394  mov     rax, [rbp+80h+arg_58]
0x14000139b  mov     [rbp+80h+var_C0], rax
0x14000139f  mov     rax, [rbp+80h+arg_50]
0x1400013a6  mov     [rbp+80h+var_D0], rax
0x1400013aa  mov     rax, [rbp+80h+arg_48]
0x1400013b1  mov     [rbp+80h+var_E0], rax
0x1400013b5  mov     rax, [rbp+80h+arg_40]
0x1400013bc  mov     [rbp+80h+var_F0], rax
0x1400013c0  mov     rax, [rbp+80h+arg_38]
0x1400013c7  mov     [rbp+80h+var_100], rax
0x1400013cb  mov     rax, [rbp+80h+arg_30]
0x1400013d2  mov     [rsp+180h+var_110], rax
0x1400013d7  mov     rax, [rbp+80h+arg_28]
0x1400013de  mov     [rbp+80h+var_18], 4
0x1400013e6  mov     [rbp+80h+var_28], 1
0x1400013ee  mov     [rbp+80h+var_38], 4
0x1400013f6  mov     rcx, [rax]
0x1400013f9  mov     rax, [rbp+80h+arg_20]
0x140001400  mov     [rsp+180h+var_130], rax
0x140001405  lea     rax, [rsp+180h+var_150]
0x14000140a  mov     [rsp+180h+var_120], rcx
0x14000140f  lea     rcx, dword_140013000
0x140001416  mov     [rsp+180h+var_158], rax
0x14000141b  mov     [rsp+180h+var_160], 14h
0x140001423  mov     [rbp+80h+var_48], 2
0x14000142b  mov     [rbp+80h+var_58], 4
0x140001433  mov     [rbp+80h+var_68], 4
0x14000143b  mov     [rbp+80h+var_78], 4
0x140001443  mov     [rbp+80h+var_88], 4
0x14000144b  mov     [rbp+80h+var_98], 4
0x140001453  mov     [rbp+80h+var_A8], 4
0x14000145b  mov     [rbp+80h+var_B8], 2
0x140001463  mov     [rbp+80h+var_C8], 4
0x14000146b  mov     [rbp+80h+var_D8], 2
0x140001473  mov     [rbp+80h+var_E8], 2
0x14000147b  mov     [rbp+80h+var_F8], 2
0x140001483  mov     [rsp+180h+var_108], 2
0x14000148c  mov     [rsp+180h+var_118], 10h
0x140001495  mov     [rsp+180h+var_128], 8
0x14000149e  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400014a3  mov     rcx, [rbp+80h+var_10]
0x1400014a7  xor     rcx, rsp; StackCookie
0x1400014aa  call    __security_check_cookie
0x1400014af  add     rsp, 180h
0x1400014b6  pop     rbp
0x1400014b7  retn
```
