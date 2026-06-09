# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18000263c`
- end: `0x18000283b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3333333333333333333@Z`
- size: `511`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001dfc4`

## callees

- `0x180001010`
- `0x1800050f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
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
        __int64 a22,
        __int64 a23,
        __int64 a24,
        __int64 a25)
{
  _BYTE v26[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+90h] [rbp-70h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 v37; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  __int64 v40; // [rsp+B8h] [rbp-48h]
  __int64 v41; // [rsp+C0h] [rbp-40h]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  __int64 v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E0h] [rbp-20h]
  __int64 v46; // [rsp+E8h] [rbp-18h]
  __int64 v47; // [rsp+F0h] [rbp-10h]
  __int64 v48; // [rsp+F8h] [rbp-8h]
  __int64 v49; // [rsp+100h] [rbp+0h]
  __int64 v50; // [rsp+108h] [rbp+8h]
  __int64 v51; // [rsp+110h] [rbp+10h]
  __int64 v52; // [rsp+118h] [rbp+18h]
  __int64 v53; // [rsp+120h] [rbp+20h]
  __int64 v54; // [rsp+128h] [rbp+28h]
  __int64 v55; // [rsp+130h] [rbp+30h]
  __int64 v56; // [rsp+138h] [rbp+38h]
  __int64 v57; // [rsp+140h] [rbp+40h]
  __int64 v58; // [rsp+148h] [rbp+48h]
  __int64 v59; // [rsp+150h] [rbp+50h]
  __int64 v60; // [rsp+158h] [rbp+58h]
  __int64 v61; // [rsp+160h] [rbp+60h]
  __int64 v62; // [rsp+168h] [rbp+68h]
  __int64 v63; // [rsp+170h] [rbp+70h]
  __int64 v64; // [rsp+178h] [rbp+78h]
  __int64 v65; // [rsp+180h] [rbp+80h]
  __int64 v66; // [rsp+188h] [rbp+88h]
  __int64 v67; // [rsp+190h] [rbp+90h]
  __int64 v68; // [rsp+198h] [rbp+98h]

  v67 = a25;
  v65 = a24;
  v63 = a23;
  v61 = a22;
  v59 = a21;
  v57 = a20;
  v55 = a19;
  v53 = a18;
  v51 = a17;
  v49 = a16;
  v47 = a15;
  v45 = a14;
  v43 = a13;
  v41 = a12;
  v39 = a11;
  v37 = a10;
  v35 = a9;
  v33 = a8;
  v31 = a7;
  v29 = a6;
  v27 = a5;
  v68 = 8;
  v66 = 8;
  v64 = 8;
  v62 = 8;
  v60 = 8;
  v58 = 8;
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
  v30 = 4;
  v28 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180040010, a2, 0, 0, 23, v26);
}

```

## disassembly

```asm
0x18000263c  push    rbp
0x18000263e  lea     rbp, [rsp-0B0h]
0x180002646  sub     rsp, 1B0h
0x18000264d  mov     rax, cs:__security_cookie
0x180002654  xor     rax, rsp
0x180002657  mov     [rbp+0B0h+var_10], rax
0x18000265e  mov     rax, [rbp+0B0h+arg_C0]
0x180002665  lea     rcx, dword_180040010
0x18000266c  mov     [rbp+0B0h+var_20], rax
0x180002673  xor     r9d, r9d
0x180002676  mov     rax, [rbp+0B0h+arg_B8]
0x18000267d  xor     r8d, r8d
0x180002680  mov     [rbp+0B0h+var_30], rax
0x180002687  mov     rax, [rbp+0B0h+arg_B0]
0x18000268e  mov     [rbp+0B0h+var_40], rax
0x180002692  mov     rax, [rbp+0B0h+arg_A8]
0x180002699  mov     [rbp+0B0h+var_50], rax
0x18000269d  mov     rax, [rbp+0B0h+arg_A0]
0x1800026a4  mov     [rbp+0B0h+var_60], rax
0x1800026a8  mov     rax, [rbp+0B0h+arg_98]
0x1800026af  mov     [rbp+0B0h+var_70], rax
0x1800026b3  mov     rax, [rbp+0B0h+arg_90]
0x1800026ba  mov     [rbp+0B0h+var_80], rax
0x1800026be  mov     rax, [rbp+0B0h+arg_88]
0x1800026c5  mov     [rbp+0B0h+var_90], rax
0x1800026c9  mov     rax, [rbp+0B0h+arg_80]
0x1800026d0  mov     [rbp+0B0h+var_A0], rax
0x1800026d4  mov     rax, [rbp+0B0h+arg_78]
0x1800026db  mov     [rbp+0B0h+var_B0], rax
0x1800026df  mov     rax, [rbp+0B0h+arg_70]
0x1800026e6  mov     [rbp+0B0h+var_C0], rax
0x1800026ea  mov     rax, [rbp+0B0h+arg_68]
0x1800026f1  mov     [rbp+0B0h+var_D0], rax
0x1800026f5  mov     rax, [rbp+0B0h+arg_60]
0x1800026fc  mov     [rbp+0B0h+var_E0], rax
0x180002700  mov     rax, [rbp+0B0h+arg_58]
0x180002707  mov     [rbp+0B0h+var_F0], rax
0x18000270b  mov     rax, [rbp+0B0h+arg_50]
0x180002712  mov     [rbp+0B0h+var_100], rax
0x180002716  mov     rax, [rbp+0B0h+arg_48]
0x18000271d  mov     [rbp+0B0h+var_110], rax
0x180002721  mov     rax, [rbp+0B0h+arg_40]
0x180002728  mov     [rbp+0B0h+var_120], rax
0x18000272c  mov     rax, [rbp+0B0h+arg_38]
0x180002733  mov     [rbp+0B0h+var_130], rax
0x180002737  mov     rax, [rbp+0B0h+arg_30]
0x18000273e  mov     [rsp+1B0h+var_140], rax
0x180002743  mov     rax, [rbp+0B0h+arg_28]
0x18000274a  mov     [rsp+1B0h+var_150], rax
0x18000274f  mov     rax, [rbp+0B0h+arg_20]
0x180002756  mov     [rsp+1B0h+var_160], rax
0x18000275b  lea     rax, [rsp+1B0h+var_180]
0x180002760  mov     [rsp+1B0h+var_188], rax
0x180002765  mov     [rsp+1B0h+var_190], 17h
0x18000276d  mov     [rbp+0B0h+var_18], 8
0x180002778  mov     [rbp+0B0h+var_28], 8
0x180002783  mov     [rbp+0B0h+var_38], 8
0x18000278b  mov     [rbp+0B0h+var_48], 8
0x180002793  mov     [rbp+0B0h+var_58], 8
0x18000279b  mov     [rbp+0B0h+var_68], 8
0x1800027a3  mov     [rbp+0B0h+var_78], 8
0x1800027ab  mov     [rbp+0B0h+var_88], 8
0x1800027b3  mov     [rbp+0B0h+var_98], 8
0x1800027bb  mov     [rbp+0B0h+var_A8], 8
0x1800027c3  mov     [rbp+0B0h+var_B8], 8
0x1800027cb  mov     [rbp+0B0h+var_C8], 8
0x1800027d3  mov     [rbp+0B0h+var_D8], 8
0x1800027db  mov     [rbp+0B0h+var_E8], 8
0x1800027e3  mov     [rbp+0B0h+var_F8], 8
0x1800027eb  mov     [rbp+0B0h+var_108], 8
0x1800027f3  mov     [rbp+0B0h+var_118], 8
0x1800027fb  mov     [rbp+0B0h+var_128], 8
0x180002803  mov     [rsp+1B0h+var_138], 8
0x18000280c  mov     [rsp+1B0h+var_148], 4
0x180002815  mov     [rsp+1B0h+var_158], 8
0x18000281e  call    _tlgWriteTransfer_EventWriteTransfer
0x180002823  mov     rcx, [rbp+0B0h+var_10]
0x18000282a  xor     rcx, rsp; StackCookie
0x18000282d  call    __security_check_cookie
0x180002832  add     rsp, 1B0h
0x180002839  pop     rbp
0x18000283a  retn
```
