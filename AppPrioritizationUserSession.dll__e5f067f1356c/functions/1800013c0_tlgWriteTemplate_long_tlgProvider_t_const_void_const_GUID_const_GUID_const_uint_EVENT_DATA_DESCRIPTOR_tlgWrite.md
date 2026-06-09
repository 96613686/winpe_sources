# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)

- ea: `0x1800013c0`
- end: `0x1800017dc`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z`
- size: `1052`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b5b0`

## callees

- `0x180001304`
- `0x180002650`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 *a9,
        __int64 *a10,
        __int64 a11,
        __int64 a12,
        __int64 *a13,
        __int64 a14,
        __int64 a15,
        __int64 *a16,
        __int64 a17,
        __int64 a18,
        __int64 *a19,
        __int64 a20,
        __int64 a21,
        __int64 *a22,
        __int64 a23,
        __int64 a24,
        __int64 *a25,
        __int64 a26,
        __int64 a27,
        __int64 *a28,
        __int64 a29,
        __int64 a30,
        __int64 *a31,
        __int64 a32,
        __int64 a33,
        __int64 *a34,
        __int64 a35,
        __int64 a36)
{
  __int64 v36; // rcx
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h]
  __int64 v40; // [rsp+58h] [rbp-A8h]
  __int64 v41; // [rsp+60h] [rbp-A0h]
  __int64 v42; // [rsp+68h] [rbp-98h]
  __int64 v43; // [rsp+70h] [rbp-90h]
  __int64 v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h]
  __int64 v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h]
  __int64 *v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h]
  __int64 v51; // [rsp+B0h] [rbp-50h]
  int v52; // [rsp+B8h] [rbp-48h]
  int v53; // [rsp+BCh] [rbp-44h]
  __int64 v54; // [rsp+C0h] [rbp-40h]
  __int64 v55; // [rsp+C8h] [rbp-38h]
  __int64 v56; // [rsp+D0h] [rbp-30h]
  __int64 v57; // [rsp+D8h] [rbp-28h]
  __int64 *v58; // [rsp+E0h] [rbp-20h]
  __int64 v59; // [rsp+E8h] [rbp-18h]
  __int64 v60; // [rsp+F0h] [rbp-10h]
  int v61; // [rsp+F8h] [rbp-8h]
  int v62; // [rsp+FCh] [rbp-4h]
  __int64 v63; // [rsp+100h] [rbp+0h]
  __int64 v64; // [rsp+108h] [rbp+8h]
  __int64 v65; // [rsp+110h] [rbp+10h]
  __int64 v66; // [rsp+118h] [rbp+18h]
  __int64 *v67; // [rsp+120h] [rbp+20h]
  __int64 v68; // [rsp+128h] [rbp+28h]
  __int64 v69; // [rsp+130h] [rbp+30h]
  int v70; // [rsp+138h] [rbp+38h]
  int v71; // [rsp+13Ch] [rbp+3Ch]
  __int64 v72; // [rsp+140h] [rbp+40h]
  __int64 v73; // [rsp+148h] [rbp+48h]
  __int64 v74; // [rsp+150h] [rbp+50h]
  __int64 v75; // [rsp+158h] [rbp+58h]
  __int64 *v76; // [rsp+160h] [rbp+60h]
  __int64 v77; // [rsp+168h] [rbp+68h]
  __int64 v78; // [rsp+170h] [rbp+70h]
  int v79; // [rsp+178h] [rbp+78h]
  int v80; // [rsp+17Ch] [rbp+7Ch]
  __int64 v81; // [rsp+180h] [rbp+80h]
  __int64 v82; // [rsp+188h] [rbp+88h]
  __int64 v83; // [rsp+190h] [rbp+90h]
  __int64 v84; // [rsp+198h] [rbp+98h]
  __int64 *v85; // [rsp+1A0h] [rbp+A0h]
  __int64 v86; // [rsp+1A8h] [rbp+A8h]
  __int64 v87; // [rsp+1B0h] [rbp+B0h]
  int v88; // [rsp+1B8h] [rbp+B8h]
  int v89; // [rsp+1BCh] [rbp+BCh]
  __int64 v90; // [rsp+1C0h] [rbp+C0h]
  __int64 v91; // [rsp+1C8h] [rbp+C8h]
  __int64 v92; // [rsp+1D0h] [rbp+D0h]
  __int64 v93; // [rsp+1D8h] [rbp+D8h]
  __int64 *v94; // [rsp+1E0h] [rbp+E0h]
  __int64 v95; // [rsp+1E8h] [rbp+E8h]
  __int64 v96; // [rsp+1F0h] [rbp+F0h]
  int v97; // [rsp+1F8h] [rbp+F8h]
  int v98; // [rsp+1FCh] [rbp+FCh]
  __int64 v99; // [rsp+200h] [rbp+100h]
  __int64 v100; // [rsp+208h] [rbp+108h]
  __int64 v101; // [rsp+210h] [rbp+110h]
  __int64 v102; // [rsp+218h] [rbp+118h]
  __int64 *v103; // [rsp+220h] [rbp+120h]
  __int64 v104; // [rsp+228h] [rbp+128h]
  __int64 v105; // [rsp+230h] [rbp+130h]
  int v106; // [rsp+238h] [rbp+138h]
  int v107; // [rsp+23Ch] [rbp+13Ch]
  __int64 v108; // [rsp+240h] [rbp+140h]
  __int64 v109; // [rsp+248h] [rbp+148h]
  __int64 v110; // [rsp+250h] [rbp+150h]
  __int64 v111; // [rsp+258h] [rbp+158h]
  __int64 *v112; // [rsp+260h] [rbp+160h]
  __int64 v113; // [rsp+268h] [rbp+168h]
  __int64 v114; // [rsp+270h] [rbp+170h]
  int v115; // [rsp+278h] [rbp+178h]
  int v116; // [rsp+27Ch] [rbp+17Ch]
  __int64 v117; // [rsp+280h] [rbp+180h]
  __int64 v118; // [rsp+288h] [rbp+188h]
  __int64 v119; // [rsp+290h] [rbp+190h]
  __int64 v120; // [rsp+298h] [rbp+198h]
  __int64 *v121; // [rsp+2A0h] [rbp+1A0h]
  __int64 v122; // [rsp+2A8h] [rbp+1A8h]
  __int64 v123; // [rsp+2B0h] [rbp+1B0h]
  int v124; // [rsp+2B8h] [rbp+1B8h]
  int v125; // [rsp+2BCh] [rbp+1BCh]
  __int64 v126; // [rsp+2C0h] [rbp+1C0h]
  __int64 v127; // [rsp+2C8h] [rbp+1C8h]
  __int64 v128; // [rsp+2D0h] [rbp+1D0h]
  __int64 v129; // [rsp+2D8h] [rbp+1D8h]

  v128 = a36;
  v126 = a35;
  v129 = 1;
  v127 = 4;
  v122 = 2;
  v125 = 0;
  v123 = *a34;
  v124 = *((unsigned __int16 *)a34 + 4);
  v119 = a33;
  v117 = a32;
  v121 = a34 + 1;
  v120 = 1;
  v118 = 8;
  v113 = 2;
  v114 = *a31;
  v115 = *((unsigned __int16 *)a31 + 4);
  v110 = a30;
  v108 = a29;
  v112 = a31 + 1;
  v116 = 0;
  v111 = 1;
  v109 = 8;
  v105 = *a28;
  v106 = *((unsigned __int16 *)a28 + 4);
  v101 = a27;
  v99 = a26;
  v103 = a28 + 1;
  v104 = 2;
  v107 = 0;
  v102 = 1;
  v96 = *a25;
  v97 = *((unsigned __int16 *)a25 + 4);
  v92 = a24;
  v90 = a23;
  v94 = a25 + 1;
  v100 = 8;
  v95 = 2;
  v98 = 0;
  v87 = *a22;
  v88 = *((unsigned __int16 *)a22 + 4);
  v83 = a21;
  v81 = a20;
  v93 = 1;
  v91 = 8;
  v85 = a22 + 1;
  v86 = 2;
  v89 = 0;
  v84 = 1;
  v82 = 8;
  v77 = 2;
  v80 = 0;
  v75 = 1;
  v78 = *a19;
  v79 = *((unsigned __int16 *)a19 + 4);
  v74 = a18;
  v72 = a17;
  v76 = a19 + 1;
  v73 = 8;
  v68 = 2;
  v71 = 0;
  v69 = *a16;
  v70 = *((unsigned __int16 *)a16 + 4);
  v65 = a15;
  v63 = a14;
  v67 = a16 + 1;
  v66 = 1;
  v64 = 8;
  v59 = 2;
  v60 = *a13;
  v61 = *((unsigned __int16 *)a13 + 4);
  v56 = a12;
  v54 = a11;
  v58 = a13 + 1;
  v62 = 0;
  v57 = 1;
  v55 = 8;
  v51 = *a10;
  v52 = *((unsigned __int16 *)a10 + 4);
  v49 = a10 + 1;
  v50 = 2;
  v53 = 0;
  v36 = *a9;
  v45 = a8;
  v43 = a7;
  v41 = a6;
  v39 = a5;
  v47 = v36;
  v48 = 16;
  v46 = 1;
  v44 = 4;
  v42 = 4;
  v40 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014038, a2, 0, 0, 0x2Bu, &v38);
}

```

## disassembly

```asm
0x1800013c0  mov     [rsp-8+arg_0], rbx
0x1800013c5  push    rbp
0x1800013c6  lea     rbp, [rsp-1F0h]
0x1800013ce  sub     rsp, 2F0h
0x1800013d5  mov     rax, cs:__security_cookie
0x1800013dc  xor     rax, rsp
0x1800013df  mov     [rbp+1F0h+var_10], rax
0x1800013e6  mov     rax, [rbp+1F0h+arg_118]
0x1800013ed  xor     ebx, ebx
0x1800013ef  mov     [rbp+1F0h+var_20], rax
0x1800013f6  mov     rax, [rbp+1F0h+arg_110]
0x1800013fd  mov     [rbp+1F0h+var_30], rax
0x180001404  mov     rax, [rbp+1F0h+arg_108]
0x18000140b  mov     [rbp+1F0h+var_18], 1
0x180001416  mov     [rbp+1F0h+var_28], 4
0x180001421  mov     [rbp+1F0h+var_48], 2
0x18000142c  lea     rcx, [rax+8]
0x180001430  mov     [rbp+1F0h+var_34], ebx
0x180001436  mov     rax, [rax]
0x180001439  mov     [rbp+1F0h+var_40], rax
0x180001440  movzx   eax, word ptr [rcx]
0x180001443  mov     [rbp+1F0h+var_38], eax
0x180001449  mov     rax, [rbp+1F0h+arg_100]
0x180001450  mov     [rbp+1F0h+var_60], rax
0x180001457  mov     rax, [rbp+1F0h+arg_F8]
0x18000145e  mov     [rbp+1F0h+var_70], rax
0x180001465  mov     rax, [rbp+1F0h+arg_F0]
0x18000146c  mov     [rbp+1F0h+var_50], rcx
0x180001473  mov     [rbp+1F0h+var_58], 1
0x18000147e  mov     [rbp+1F0h+var_68], 8
0x180001489  lea     rcx, [rax+8]
0x18000148d  mov     [rbp+1F0h+var_88], 2
0x180001498  mov     rax, [rax]
0x18000149b  mov     [rbp+1F0h+var_80], rax
0x1800014a2  movzx   eax, word ptr [rcx]
0x1800014a5  mov     [rbp+1F0h+var_78], eax
0x1800014ab  mov     rax, [rbp+1F0h+arg_E8]
0x1800014b2  mov     [rbp+1F0h+var_A0], rax
0x1800014b9  mov     rax, [rbp+1F0h+arg_E0]
0x1800014c0  mov     [rbp+1F0h+var_B0], rax
0x1800014c7  mov     rax, [rbp+1F0h+arg_D8]
0x1800014ce  mov     [rbp+1F0h+var_90], rcx
0x1800014d5  mov     [rbp+1F0h+var_74], ebx
0x1800014db  mov     [rbp+1F0h+var_98], 1
0x1800014e6  lea     rcx, [rax+8]
0x1800014ea  mov     [rbp+1F0h+var_A8], 8
0x1800014f5  mov     rax, [rax]
0x1800014f8  mov     [rbp+1F0h+var_C0], rax
0x1800014ff  movzx   eax, word ptr [rcx]
0x180001502  mov     [rbp+1F0h+var_B8], eax
0x180001508  mov     rax, [rbp+1F0h+arg_D0]
0x18000150f  mov     [rbp+1F0h+var_E0], rax
0x180001516  mov     rax, [rbp+1F0h+arg_C8]
0x18000151d  mov     [rbp+1F0h+var_F0], rax
0x180001524  mov     rax, [rbp+1F0h+arg_C0]
0x18000152b  mov     [rbp+1F0h+var_D0], rcx
0x180001532  mov     [rbp+1F0h+var_C8], 2
0x18000153d  mov     [rbp+1F0h+var_B4], ebx
0x180001543  lea     rcx, [rax+8]
0x180001547  mov     [rbp+1F0h+var_D8], 1
0x180001552  mov     rax, [rax]
0x180001555  mov     [rbp+1F0h+var_100], rax
0x18000155c  movzx   eax, word ptr [rcx]
0x18000155f  mov     [rbp+1F0h+var_F8], eax
0x180001565  mov     rax, [rbp+1F0h+arg_B8]
0x18000156c  mov     [rbp+1F0h+var_120], rax
0x180001573  mov     rax, [rbp+1F0h+arg_B0]
0x18000157a  mov     [rbp+1F0h+var_130], rax
0x180001581  mov     rax, [rbp+1F0h+arg_A8]
0x180001588  mov     [rbp+1F0h+var_110], rcx
0x18000158f  mov     [rbp+1F0h+var_E8], 8
0x18000159a  mov     [rbp+1F0h+var_108], 2
0x1800015a5  lea     rcx, [rax+8]
0x1800015a9  mov     [rbp+1F0h+var_F4], ebx
0x1800015af  mov     rax, [rax]
0x1800015b2  mov     [rbp+1F0h+var_140], rax
0x1800015b9  movzx   eax, word ptr [rcx]
0x1800015bc  mov     [rbp+1F0h+var_138], eax
0x1800015c2  mov     rax, [rbp+1F0h+arg_A0]
0x1800015c9  mov     [rbp+1F0h+var_160], rax
0x1800015d0  mov     rax, [rbp+1F0h+arg_98]
0x1800015d7  mov     [rbp+1F0h+var_170], rax
0x1800015de  mov     [rbp+1F0h+var_118], 1
0x1800015e9  mov     [rbp+1F0h+var_128], 8
0x1800015f4  mov     [rbp+1F0h+var_150], rcx
0x1800015fb  mov     [rbp+1F0h+var_148], 2
0x180001606  mov     [rbp+1F0h+var_134], ebx
0x18000160c  mov     [rbp+1F0h+var_158], 1
0x180001617  mov     rax, [rbp+1F0h+arg_90]
0x18000161e  xor     r9d, r9d; int
0x180001621  xor     r8d, r8d; int
0x180001624  mov     [rbp+1F0h+var_168], 8
0x18000162f  mov     [rbp+1F0h+var_188], 2
0x180001637  mov     [rbp+1F0h+var_174], ebx
0x18000163a  lea     rcx, [rax+8]
0x18000163e  mov     [rbp+1F0h+var_198], 1
0x180001646  mov     rax, [rax]
0x180001649  mov     [rbp+1F0h+var_180], rax
0x18000164d  movzx   eax, word ptr [rcx]
0x180001650  mov     [rbp+1F0h+var_178], eax
0x180001653  mov     rax, [rbp+1F0h+arg_88]
0x18000165a  mov     [rbp+1F0h+var_1A0], rax
0x18000165e  mov     rax, [rbp+1F0h+arg_80]
0x180001665  mov     [rbp+1F0h+var_1B0], rax
0x180001669  mov     rax, [rbp+1F0h+arg_78]
0x180001670  mov     [rbp+1F0h+var_190], rcx
0x180001674  mov     [rbp+1F0h+var_1A8], 8
0x18000167c  mov     [rbp+1F0h+var_1C8], 2
0x180001684  lea     rcx, [rax+8]
0x180001688  mov     [rbp+1F0h+var_1B4], ebx
0x18000168b  mov     rax, [rax]
0x18000168e  mov     [rbp+1F0h+var_1C0], rax
0x180001692  movzx   eax, word ptr [rcx]
0x180001695  mov     [rbp+1F0h+var_1B8], eax
0x180001698  mov     rax, [rbp+1F0h+arg_70]
0x18000169f  mov     [rbp+1F0h+var_1E0], rax
0x1800016a3  mov     rax, [rbp+1F0h+arg_68]
0x1800016aa  mov     [rbp+1F0h+var_1F0], rax
0x1800016ae  mov     rax, [rbp+1F0h+arg_60]
0x1800016b5  mov     [rbp+1F0h+var_1D0], rcx
0x1800016b9  mov     [rbp+1F0h+var_1D8], 1
0x1800016c1  mov     [rbp+1F0h+var_1E8], 8
0x1800016c9  lea     rcx, [rax+8]
0x1800016cd  mov     [rbp+1F0h+var_208], 2
0x1800016d5  mov     rax, [rax]
0x1800016d8  mov     [rbp+1F0h+var_200], rax
0x1800016dc  movzx   eax, word ptr [rcx]
0x1800016df  mov     [rbp+1F0h+var_1F8], eax
0x1800016e2  mov     rax, [rbp+1F0h+arg_58]
0x1800016e9  mov     [rbp+1F0h+var_220], rax
0x1800016ed  mov     rax, [rbp+1F0h+arg_50]
0x1800016f4  mov     [rbp+1F0h+var_230], rax
0x1800016f8  mov     rax, [rbp+1F0h+arg_48]
0x1800016ff  mov     [rbp+1F0h+var_210], rcx
0x180001703  mov     [rbp+1F0h+var_1F4], ebx
0x180001706  mov     [rbp+1F0h+var_218], 1
0x18000170e  lea     rcx, [rax+8]
0x180001712  mov     [rbp+1F0h+var_228], 8
0x18000171a  mov     rax, [rax]
0x18000171d  mov     [rbp+1F0h+var_240], rax
0x180001721  movzx   eax, word ptr [rcx]
0x180001724  mov     [rbp+1F0h+var_238], eax
0x180001727  mov     rax, [rbp+1F0h+arg_40]
0x18000172e  mov     [rbp+1F0h+var_250], rcx
0x180001732  mov     [rbp+1F0h+var_248], 2
0x18000173a  mov     [rbp+1F0h+var_234], ebx
0x18000173d  mov     rcx, [rax]
0x180001740  mov     rax, [rbp+1F0h+arg_38]
0x180001747  mov     [rbp+1F0h+var_270], rax
0x18000174b  mov     rax, [rbp+1F0h+arg_30]
0x180001752  mov     [rsp+2F0h+var_280], rax
0x180001757  mov     rax, [rbp+1F0h+arg_28]
0x18000175e  mov     [rsp+2F0h+var_290], rax
0x180001763  mov     rax, [rbp+1F0h+arg_20]
0x18000176a  mov     [rsp+2F0h+var_2A0], rax
0x18000176f  lea     rax, [rsp+2F0h+var_2C0]
0x180001774  mov     [rbp+1F0h+var_260], rcx
0x180001778  lea     rcx, dword_180014038; int
0x18000177f  mov     [rsp+2F0h+var_2C8], rax; PEVENT_DATA_DESCRIPTOR
0x180001784  mov     [rsp+2F0h+var_2D0], 2Bh ; '+'; ULONG
0x18000178c  mov     [rbp+1F0h+var_258], 10h
0x180001794  mov     [rbp+1F0h+var_268], 1
0x18000179c  mov     [rsp+2F0h+var_278], 4
0x1800017a5  mov     [rsp+2F0h+var_288], 4
0x1800017ae  mov     [rsp+2F0h+var_298], 8
0x1800017b7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800017bc  mov     rcx, [rbp+1F0h+var_10]
0x1800017c3  xor     rcx, rsp; StackCookie
0x1800017c6  call    __security_check_cookie
0x1800017cb  mov     rbx, [rsp+2F0h+arg_0]
0x1800017d3  add     rsp, 2F0h
0x1800017da  pop     rbp
0x1800017db  retn
```
