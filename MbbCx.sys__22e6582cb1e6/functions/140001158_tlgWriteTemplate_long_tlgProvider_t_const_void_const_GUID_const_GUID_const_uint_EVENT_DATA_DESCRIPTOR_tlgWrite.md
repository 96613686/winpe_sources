# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001158`
- end: `0x1400012f7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3333333333333333@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bb48`

## callees

- `0x1400010b4`
- `0x140047e50`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
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
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21)
{
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  __int64 v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  __int64 v30; // [rsp+88h] [rbp-78h]
  __int64 v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  __int64 v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  __int64 v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  __int64 v43; // [rsp+F0h] [rbp-10h]
  __int64 v44; // [rsp+F8h] [rbp-8h]
  __int64 v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+108h] [rbp+8h]
  __int64 v47; // [rsp+110h] [rbp+10h]
  __int64 v48; // [rsp+118h] [rbp+18h]
  __int64 v49; // [rsp+120h] [rbp+20h]
  __int64 v50; // [rsp+128h] [rbp+28h]
  __int64 v51; // [rsp+130h] [rbp+30h]
  __int64 v52; // [rsp+138h] [rbp+38h]
  __int64 v53; // [rsp+140h] [rbp+40h]
  __int64 v54; // [rsp+148h] [rbp+48h]
  __int64 v55; // [rsp+150h] [rbp+50h]
  __int64 v56; // [rsp+158h] [rbp+58h]

  v55 = a21;
  v53 = a20;
  v51 = a19;
  v49 = a18;
  v47 = a17;
  v45 = a16;
  v43 = a15;
  v41 = a14;
  v39 = a13;
  v37 = a12;
  v35 = a11;
  v33 = a10;
  v31 = a9;
  v29 = a8;
  v27 = a7;
  v25 = a6;
  v23 = a5;
  v56 = 8;
  v54 = 8;
  v52 = 8;
  v50 = 8;
  v48 = 8;
  v46 = 8;
  v44 = 8;
  v42 = 8;
  v40 = 8;
  v38 = 8;
  v36 = 8;
  v34 = 8;
  v32 = 8;
  v30 = 8;
  v28 = 8;
  v26 = 8;
  v24 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14005E0C8, a2, 0, 0, 0x13u, &v22);
}

```

## disassembly

```asm
0x140001158  push    rbp
0x14000115a  lea     rbp, [rsp-70h]
0x14000115f  sub     rsp, 170h
0x140001166  mov     rax, cs:__security_cookie
0x14000116d  xor     rax, rsp
0x140001170  mov     [rbp+70h+var_10], rax
0x140001174  mov     rax, [rbp+70h+arg_A0]
0x14000117b  lea     rcx, dword_14005E0C8
0x140001182  mov     [rbp+70h+var_20], rax
0x140001186  xor     r9d, r9d
0x140001189  mov     rax, [rbp+70h+arg_98]
0x140001190  xor     r8d, r8d
0x140001193  mov     [rbp+70h+var_30], rax
0x140001197  mov     rax, [rbp+70h+arg_90]
0x14000119e  mov     [rbp+70h+var_40], rax
0x1400011a2  mov     rax, [rbp+70h+arg_88]
0x1400011a9  mov     [rbp+70h+var_50], rax
0x1400011ad  mov     rax, [rbp+70h+arg_80]
0x1400011b4  mov     [rbp+70h+var_60], rax
0x1400011b8  mov     rax, [rbp+70h+arg_78]
0x1400011bf  mov     [rbp+70h+var_70], rax
0x1400011c3  mov     rax, [rbp+70h+arg_70]
0x1400011ca  mov     [rbp+70h+var_80], rax
0x1400011ce  mov     rax, [rbp+70h+arg_68]
0x1400011d5  mov     [rbp+70h+var_90], rax
0x1400011d9  mov     rax, [rbp+70h+arg_60]
0x1400011e0  mov     [rbp+70h+var_A0], rax
0x1400011e4  mov     rax, [rbp+70h+arg_58]
0x1400011eb  mov     [rbp+70h+var_B0], rax
0x1400011ef  mov     rax, [rbp+70h+arg_50]
0x1400011f6  mov     [rbp+70h+var_C0], rax
0x1400011fa  mov     rax, [rbp+70h+arg_48]
0x140001201  mov     [rbp+70h+var_D0], rax
0x140001205  mov     rax, [rbp+70h+arg_40]
0x14000120c  mov     [rbp+70h+var_E0], rax
0x140001210  mov     rax, [rbp+70h+arg_38]
0x140001217  mov     [rbp+70h+var_F0], rax
0x14000121b  mov     rax, [rbp+70h+arg_30]
0x140001222  mov     [rsp+170h+var_100], rax
0x140001227  mov     rax, [rbp+70h+arg_28]
0x14000122e  mov     [rsp+170h+var_110], rax
0x140001233  mov     rax, [rbp+70h+arg_20]
0x14000123a  mov     [rsp+170h+var_120], rax
0x14000123f  lea     rax, [rsp+170h+var_140]
0x140001244  mov     [rsp+170h+var_148], rax
0x140001249  mov     [rsp+170h+var_150], 13h
0x140001251  mov     [rbp+70h+var_18], 8
0x140001259  mov     [rbp+70h+var_28], 8
0x140001261  mov     [rbp+70h+var_38], 8
0x140001269  mov     [rbp+70h+var_48], 8
0x140001271  mov     [rbp+70h+var_58], 8
0x140001279  mov     [rbp+70h+var_68], 8
0x140001281  mov     [rbp+70h+var_78], 8
0x140001289  mov     [rbp+70h+var_88], 8
0x140001291  mov     [rbp+70h+var_98], 8
0x140001299  mov     [rbp+70h+var_A8], 8
0x1400012a1  mov     [rbp+70h+var_B8], 8
0x1400012a9  mov     [rbp+70h+var_C8], 8
0x1400012b1  mov     [rbp+70h+var_D8], 8
0x1400012b9  mov     [rbp+70h+var_E8], 8
0x1400012c1  mov     [rsp+170h+var_F8], 8
0x1400012ca  mov     [rsp+170h+var_108], 8
0x1400012d3  mov     [rsp+170h+var_118], 8
0x1400012dc  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400012e1  mov     rcx, [rbp+70h+var_10]
0x1400012e5  xor     rcx, rsp; StackCookie
0x1400012e8  call    __security_check_cookie
0x1400012ed  add     rsp, 170h
0x1400012f4  pop     rbp
0x1400012f5  retn
```
