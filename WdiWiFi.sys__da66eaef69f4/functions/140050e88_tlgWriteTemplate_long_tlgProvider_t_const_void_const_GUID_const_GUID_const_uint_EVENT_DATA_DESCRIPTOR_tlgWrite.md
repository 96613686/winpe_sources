# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140050e88`
- end: `0x1400512d3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U?$_tlgWrapperByVal@$00@@U3@U3@U3@U3@U4@U4@U4@U3@U3@U3@U3@U3@U3@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@5555555555AEBU?$_tlgWrapperByVal@$00@@55556665555553333333333333@Z`
- size: `1099`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400b6014`

## callees

- `0x1400da4f0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400512ae`
- `ntoskrnl!EtwWriteTransfer` at `0x1400512ae`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
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
        __int64 a22,
        __int64 a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        __int64 a27,
        __int64 a28,
        __int64 a29,
        __int64 a30,
        __int64 a31,
        __int64 a32,
        __int64 a33,
        __int64 a34,
        __int64 a35,
        __int64 a36,
        __int64 a37,
        __int64 a38,
        __int64 a39,
        __int64 a40,
        __int64 a41,
        __int64 a42,
        __int64 a43,
        __int64 a44)
{
  __int64 v44; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v48; // [rsp+60h] [rbp-A0h]
  int v49; // [rsp+68h] [rbp-98h]
  int v50; // [rsp+6Ch] [rbp-94h]
  __int64 v51; // [rsp+70h] [rbp-90h]
  __int64 v52; // [rsp+78h] [rbp-88h]
  __int64 v53; // [rsp+80h] [rbp-80h]
  __int64 v54; // [rsp+88h] [rbp-78h]
  __int64 v55; // [rsp+90h] [rbp-70h]
  __int64 v56; // [rsp+98h] [rbp-68h]
  __int64 v57; // [rsp+A0h] [rbp-60h]
  __int64 v58; // [rsp+A8h] [rbp-58h]
  __int64 v59; // [rsp+B0h] [rbp-50h]
  __int64 v60; // [rsp+B8h] [rbp-48h]
  __int64 v61; // [rsp+C0h] [rbp-40h]
  __int64 v62; // [rsp+C8h] [rbp-38h]
  __int64 v63; // [rsp+D0h] [rbp-30h]
  __int64 v64; // [rsp+D8h] [rbp-28h]
  __int64 v65; // [rsp+E0h] [rbp-20h]
  __int64 v66; // [rsp+E8h] [rbp-18h]
  __int64 v67; // [rsp+F0h] [rbp-10h]
  __int64 v68; // [rsp+F8h] [rbp-8h]
  __int64 v69; // [rsp+100h] [rbp+0h]
  __int64 v70; // [rsp+108h] [rbp+8h]
  __int64 v71; // [rsp+110h] [rbp+10h]
  __int64 v72; // [rsp+118h] [rbp+18h]
  __int64 v73; // [rsp+120h] [rbp+20h]
  __int64 v74; // [rsp+128h] [rbp+28h]
  __int64 v75; // [rsp+130h] [rbp+30h]
  __int64 v76; // [rsp+138h] [rbp+38h]
  __int64 v77; // [rsp+140h] [rbp+40h]
  __int64 v78; // [rsp+148h] [rbp+48h]
  __int64 v79; // [rsp+150h] [rbp+50h]
  __int64 v80; // [rsp+158h] [rbp+58h]
  __int64 v81; // [rsp+160h] [rbp+60h]
  __int64 v82; // [rsp+168h] [rbp+68h]
  __int64 v83; // [rsp+170h] [rbp+70h]
  __int64 v84; // [rsp+178h] [rbp+78h]
  __int64 v85; // [rsp+180h] [rbp+80h]
  __int64 v86; // [rsp+188h] [rbp+88h]
  __int64 v87; // [rsp+190h] [rbp+90h]
  __int64 v88; // [rsp+198h] [rbp+98h]
  __int64 v89; // [rsp+1A0h] [rbp+A0h]
  __int64 v90; // [rsp+1A8h] [rbp+A8h]
  __int64 v91; // [rsp+1B0h] [rbp+B0h]
  __int64 v92; // [rsp+1B8h] [rbp+B8h]
  __int64 v93; // [rsp+1C0h] [rbp+C0h]
  __int64 v94; // [rsp+1C8h] [rbp+C8h]
  __int64 v95; // [rsp+1D0h] [rbp+D0h]
  __int64 v96; // [rsp+1D8h] [rbp+D8h]
  __int64 v97; // [rsp+1E0h] [rbp+E0h]
  __int64 v98; // [rsp+1E8h] [rbp+E8h]
  __int64 v99; // [rsp+1F0h] [rbp+F0h]
  __int64 v100; // [rsp+1F8h] [rbp+F8h]
  __int64 v101; // [rsp+200h] [rbp+100h]
  __int64 v102; // [rsp+208h] [rbp+108h]
  __int64 v103; // [rsp+210h] [rbp+110h]
  __int64 v104; // [rsp+218h] [rbp+118h]
  __int64 v105; // [rsp+220h] [rbp+120h]
  __int64 v106; // [rsp+228h] [rbp+128h]
  __int64 v107; // [rsp+230h] [rbp+130h]
  __int64 v108; // [rsp+238h] [rbp+138h]
  __int64 v109; // [rsp+240h] [rbp+140h]
  __int64 v110; // [rsp+248h] [rbp+148h]
  __int64 v111; // [rsp+250h] [rbp+150h]
  __int64 v112; // [rsp+258h] [rbp+158h]
  __int64 v113; // [rsp+260h] [rbp+160h]
  __int64 v114; // [rsp+268h] [rbp+168h]
  __int64 v115; // [rsp+270h] [rbp+170h]
  __int64 v116; // [rsp+278h] [rbp+178h]
  __int64 v117; // [rsp+280h] [rbp+180h]
  __int64 v118; // [rsp+288h] [rbp+188h]
  __int64 v119; // [rsp+290h] [rbp+190h]
  __int64 v120; // [rsp+298h] [rbp+198h]
  __int64 v121; // [rsp+2A0h] [rbp+1A0h]
  __int64 v122; // [rsp+2A8h] [rbp+1A8h]
  __int64 v123; // [rsp+2B0h] [rbp+1B0h]
  __int64 v124; // [rsp+2B8h] [rbp+1B8h]
  __int64 v125; // [rsp+2C0h] [rbp+1C0h]
  __int64 v126; // [rsp+2C8h] [rbp+1C8h]
  __int64 v127; // [rsp+2D0h] [rbp+1D0h]
  __int64 v128; // [rsp+2D8h] [rbp+1D8h]
  __int64 v129; // [rsp+2E0h] [rbp+1E0h]
  __int64 v130; // [rsp+2E8h] [rbp+1E8h]

  v129 = a44;
  v127 = a43;
  v125 = a42;
  v123 = a41;
  v121 = a40;
  v119 = a39;
  v117 = a38;
  v115 = a37;
  v113 = a36;
  v111 = a35;
  v109 = a34;
  v107 = a33;
  v105 = a32;
  v103 = a31;
  v101 = a30;
  v99 = a29;
  v97 = a28;
  v95 = a27;
  v93 = a26;
  v91 = a25;
  v89 = a24;
  v87 = a23;
  v85 = a22;
  v83 = a21;
  v81 = a20;
  v79 = a19;
  v77 = a18;
  v130 = 8;
  v128 = 8;
  v126 = 8;
  v124 = 8;
  v122 = 8;
  v120 = 8;
  v118 = 8;
  v116 = 8;
  v114 = 8;
  v112 = 8;
  v110 = 8;
  v108 = 8;
  v106 = 8;
  v104 = 4;
  v102 = 4;
  v100 = 4;
  v98 = 4;
  v96 = 4;
  v94 = 4;
  v92 = 1;
  v90 = 1;
  v88 = 1;
  v86 = 4;
  v84 = 4;
  v82 = 4;
  v80 = 4;
  v75 = a17;
  v73 = a16;
  v71 = a15;
  v69 = a14;
  v67 = a13;
  v65 = a12;
  v63 = a11;
  v61 = a10;
  v59 = a9;
  v57 = a8;
  v55 = a7;
  v78 = 1;
  v76 = 4;
  v74 = 4;
  v44 = *a6;
  v51 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (unsigned __int64)off_1400F8760;
  v53 = v44;
  v72 = 4;
  v70 = 4;
  v68 = 4;
  v66 = 4;
  v64 = 4;
  v62 = 4;
  v60 = 4;
  v58 = 4;
  v56 = 4;
  v54 = 16;
  v52 = 8;
  UserData.Size = *(unsigned __int16 *)off_1400F8760;
  v49 = *(unsigned __int16 *)(a2 + 11);
  v48 = a2 + 11;
  v50 = 1;
  UserData.Reserved = 2;
  return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0x2Au, &UserData);
}

```

## disassembly

```asm
0x140050e88  push    rbp
0x140050e8a  lea     rbp, [rsp-200h]
0x140050e92  sub     rsp, 300h
0x140050e99  mov     rax, cs:__security_cookie
0x140050ea0  xor     rax, rsp
0x140050ea3  mov     [rbp+200h+var_10], rax
0x140050eaa  mov     rax, [rbp+200h+arg_158]
0x140050eb1  mov     r8d, 1
0x140050eb7  mov     [rbp+200h+var_20], rax
0x140050ebe  mov     rax, [rbp+200h+arg_150]
0x140050ec5  mov     [rbp+200h+var_30], rax
0x140050ecc  mov     rax, [rbp+200h+arg_148]
0x140050ed3  mov     [rbp+200h+var_40], rax
0x140050eda  mov     rax, [rbp+200h+arg_140]
0x140050ee1  mov     [rbp+200h+var_50], rax
0x140050ee8  mov     rax, [rbp+200h+arg_138]
0x140050eef  mov     [rbp+200h+var_60], rax
0x140050ef6  mov     rax, [rbp+200h+arg_130]
0x140050efd  mov     [rbp+200h+var_70], rax
0x140050f04  mov     rax, [rbp+200h+arg_128]
0x140050f0b  mov     [rbp+200h+var_80], rax
0x140050f12  mov     rax, [rbp+200h+arg_120]
0x140050f19  mov     [rbp+200h+var_90], rax
0x140050f20  mov     rax, [rbp+200h+arg_118]
0x140050f27  mov     [rbp+200h+var_A0], rax
0x140050f2e  mov     rax, [rbp+200h+arg_110]
0x140050f35  mov     [rbp+200h+var_B0], rax
0x140050f3c  mov     rax, [rbp+200h+arg_108]
0x140050f43  mov     [rbp+200h+var_C0], rax
0x140050f4a  mov     rax, [rbp+200h+arg_100]
0x140050f51  mov     [rbp+200h+var_D0], rax
0x140050f58  mov     rax, [rbp+200h+arg_F8]
0x140050f5f  mov     [rbp+200h+var_E0], rax
0x140050f66  mov     rax, [rbp+200h+arg_F0]
0x140050f6d  mov     [rbp+200h+var_F0], rax
0x140050f74  mov     rax, [rbp+200h+arg_E8]
0x140050f7b  mov     [rbp+200h+var_100], rax
0x140050f82  mov     rax, [rbp+200h+arg_E0]
0x140050f89  mov     [rbp+200h+var_110], rax
0x140050f90  mov     rax, [rbp+200h+arg_D8]
0x140050f97  mov     [rbp+200h+var_120], rax
0x140050f9e  mov     rax, [rbp+200h+arg_D0]
0x140050fa5  mov     [rbp+200h+var_130], rax
0x140050fac  mov     rax, [rbp+200h+arg_C8]
0x140050fb3  mov     [rbp+200h+var_140], rax
0x140050fba  mov     rax, [rbp+200h+arg_C0]
0x140050fc1  mov     [rbp+200h+var_150], rax
0x140050fc8  mov     rax, [rbp+200h+arg_B8]
0x140050fcf  mov     [rbp+200h+var_160], rax
0x140050fd6  mov     rax, [rbp+200h+arg_B0]
0x140050fdd  mov     [rbp+200h+var_170], rax
0x140050fe4  mov     rax, [rbp+200h+arg_A8]
0x140050feb  mov     [rbp+200h+var_180], rax
0x140050ff2  mov     rax, [rbp+200h+arg_A0]
0x140050ff9  mov     [rbp+200h+var_190], rax
0x140050ffd  mov     rax, [rbp+200h+arg_98]
0x140051004  mov     [rbp+200h+var_1A0], rax
0x140051008  mov     rax, [rbp+200h+arg_90]
0x14005100f  mov     [rbp+200h+var_1B0], rax
0x140051013  mov     rax, [rbp+200h+arg_88]
0x14005101a  mov     [rbp+200h+var_1C0], rax
0x14005101e  mov     [rbp+200h+var_18], 8
0x140051029  mov     [rbp+200h+var_28], 8
0x140051034  mov     [rbp+200h+var_38], 8
0x14005103f  mov     [rbp+200h+var_48], 8
0x14005104a  mov     [rbp+200h+var_58], 8
0x140051055  mov     [rbp+200h+var_68], 8
0x140051060  mov     [rbp+200h+var_78], 8
0x14005106b  mov     [rbp+200h+var_88], 8
0x140051076  mov     [rbp+200h+var_98], 8
0x140051081  mov     [rbp+200h+var_A8], 8
0x14005108c  mov     [rbp+200h+var_B8], 8
0x140051097  mov     [rbp+200h+var_C8], 8
0x1400510a2  mov     [rbp+200h+var_D8], 8
0x1400510ad  mov     [rbp+200h+var_E8], 4
0x1400510b8  mov     [rbp+200h+var_F8], 4
0x1400510c3  mov     [rbp+200h+var_108], 4
0x1400510ce  mov     [rbp+200h+var_118], 4
0x1400510d9  mov     [rbp+200h+var_128], 4
0x1400510e4  mov     [rbp+200h+var_138], 4
0x1400510ef  mov     [rbp+200h+var_148], r8
0x1400510f6  mov     [rbp+200h+var_158], r8
0x1400510fd  mov     [rbp+200h+var_168], r8
0x140051104  mov     [rbp+200h+var_178], 4
0x14005110f  mov     [rbp+200h+var_188], 4
0x140051117  mov     [rbp+200h+var_198], 4
0x14005111f  mov     [rbp+200h+var_1A8], 4
0x140051127  mov     rax, [rbp+200h+arg_80]
0x14005112e  xor     r9d, r9d; RelatedActivityId
0x140051131  mov     [rbp+200h+var_1D0], rax
0x140051135  mov     rax, [rbp+200h+arg_78]
0x14005113c  mov     [rbp+200h+var_1E0], rax
0x140051140  mov     rax, [rbp+200h+arg_70]
0x140051147  mov     [rbp+200h+var_1F0], rax
0x14005114b  mov     rax, [rbp+200h+arg_68]
0x140051152  mov     [rbp+200h+var_200], rax
0x140051156  mov     rax, [rbp+200h+arg_60]
0x14005115d  mov     [rbp+200h+var_210], rax
0x140051161  mov     rax, [rbp+200h+arg_58]
0x140051168  mov     [rbp+200h+var_220], rax
0x14005116c  mov     rax, [rbp+200h+arg_50]
0x140051173  mov     [rbp+200h+var_230], rax
0x140051177  mov     rax, [rbp+200h+arg_48]
0x14005117e  mov     [rbp+200h+var_240], rax
0x140051182  mov     rax, [rbp+200h+arg_40]
0x140051189  mov     [rbp+200h+var_250], rax
0x14005118d  mov     rax, [rbp+200h+arg_38]
0x140051194  mov     [rbp+200h+var_260], rax
0x140051198  mov     rax, [rbp+200h+arg_30]
0x14005119f  mov     [rbp+200h+var_270], rax
0x1400511a3  mov     rax, [rbp+200h+arg_28]
0x1400511aa  mov     [rbp+200h+var_1B8], r8
0x1400511ae  mov     [rbp+200h+var_1C8], 4
0x1400511b6  mov     [rbp+200h+var_1D8], 4
0x1400511be  mov     rcx, [rax]
0x1400511c1  mov     rax, [rbp+200h+arg_20]
0x1400511c8  mov     [rsp+300h+var_290], rax
0x1400511cd  movzx   eax, byte ptr [rdx]
0x1400511d0  shl     eax, 18h
0x1400511d3  mov     dword ptr [rsp+300h+EventDescriptor.Id], eax
0x1400511d7  movzx   eax, word ptr [rdx+1]
0x1400511db  mov     dword ptr [rsp+300h+EventDescriptor.Level], eax
0x1400511df  mov     rax, [rdx+3]
0x1400511e3  mov     [rsp+300h+EventDescriptor.Keyword], rax
0x1400511e8  mov     rax, cs:off_1400F8760
0x1400511ef  mov     [rsp+300h+var_2B0.Ptr], rax
0x1400511f4  mov     [rbp+200h+var_280], rcx
0x1400511f8  lea     rcx, [rdx+0Bh]
0x1400511fc  mov     [rbp+200h+var_1E8], 4
0x140051204  lea     rdx, [rsp+300h+EventDescriptor]; EventDescriptor
0x140051209  mov     [rbp+200h+var_1F8], 4
0x140051211  mov     [rbp+200h+var_208], 4
0x140051219  mov     [rbp+200h+var_218], 4
0x140051221  mov     [rbp+200h+var_228], 4
0x140051229  mov     [rbp+200h+var_238], 4
0x140051231  mov     [rbp+200h+var_248], 4
0x140051239  mov     [rbp+200h+var_258], 4
0x140051241  mov     [rbp+200h+var_268], 4
0x140051249  mov     [rbp+200h+var_278], 10h
0x140051251  mov     [rsp+300h+var_288], 8
0x14005125a  movzx   eax, word ptr [rax]
0x14005125d  mov     [rsp+300h+var_2B0.Size], eax
0x140051261  movzx   eax, word ptr [rcx]
0x140051264  mov     [rsp+300h+var_298], eax
0x140051268  lea     rax, _TraceLoggingMetadataEnd
0x14005126f  mov     [rsp+300h+var_2A0], rcx
0x140051274  lea     rcx, _TraceLoggingMetadata
0x14005127b  sub     eax, ecx
0x14005127d  mov     [rsp+300h+var_294], r8d
0x140051282  mov     dword ptr [rsp+300h+var_2B0.___u2], 2
0x14005128a  xor     r8d, r8d; ActivityId
0x14005128d  mov     [rsp+300h+var_2D0], eax
0x140051291  mov     eax, [rsp+300h+var_2D0]
0x140051295  mov     rcx, cs:RegHandle; RegHandle
0x14005129c  lea     rax, [rsp+300h+var_2B0]
0x1400512a1  mov     [rsp+300h+UserData], rax; UserData
0x1400512a6  mov     [rsp+300h+UserDataCount], 2Ah ; '*'; UserDataCount
0x1400512ae  call    cs:__imp_EtwWriteTransfer
0x1400512b5  nop     dword ptr [rax+rax+00h]
0x1400512ba  mov     rcx, [rbp+200h+var_10]
0x1400512c1  xor     rcx, rsp; StackCookie
0x1400512c4  call    __security_check_cookie
0x1400512c9  add     rsp, 300h
0x1400512d0  pop     rbp
0x1400512d1  retn
```
