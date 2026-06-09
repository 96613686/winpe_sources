# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400010ac`
- end: `0x14000143e`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U2@U2@U2@U2@U3@U?$_tlgWrapperByVal@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@44444AEBU?$_tlgWrapperByVal@$03@@555555544445AEBU?$_tlgWrapperByVal@$00@@5@Z`
- size: `914`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001f304`

## callees

- `0x1400010ac`
- `0x140001ad4`
- `0x140005c20`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int **a6,
        int **a7,
        int **a8,
        int **a9,
        int **a10,
        int **a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        int **a20,
        int **a21,
        int **a22,
        int **a23,
        __int64 a24,
        __int64 a25,
        __int64 a26)
{
  __int64 v27; // rcx
  int v29; // edx
  int *v30; // r8
  __int64 v31; // rax
  int v32; // eax
  int *v33; // r8
  __int64 v34; // rax
  int v35; // eax
  int *v36; // r8
  __int64 v37; // rax
  int v38; // eax
  int *v39; // r8
  __int64 v40; // rax
  int v41; // eax
  int *v42; // r8
  __int64 v43; // rax
  int v44; // eax
  int *v45; // r8
  __int64 v46; // rax
  int v47; // eax
  int *v48; // r8
  __int64 v49; // rax
  int v50; // eax
  int *v51; // r8
  __int64 v52; // rax
  int v53; // eax
  int *v54; // r8
  __int64 v55; // rax
  int v56; // eax
  int *v57; // r8
  struct _EVENT_DATA_DESCRIPTOR v59; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h]
  __int64 v61; // [rsp+58h] [rbp-A8h]
  int *v62; // [rsp+60h] [rbp-A0h]
  int v63; // [rsp+68h] [rbp-98h]
  int v64; // [rsp+6Ch] [rbp-94h]
  int *v65; // [rsp+70h] [rbp-90h]
  int v66; // [rsp+78h] [rbp-88h]
  int v67; // [rsp+7Ch] [rbp-84h]
  int *v68; // [rsp+80h] [rbp-80h]
  int v69; // [rsp+88h] [rbp-78h]
  int v70; // [rsp+8Ch] [rbp-74h]
  int *v71; // [rsp+90h] [rbp-70h]
  int v72; // [rsp+98h] [rbp-68h]
  int v73; // [rsp+9Ch] [rbp-64h]
  int *v74; // [rsp+A0h] [rbp-60h]
  int v75; // [rsp+A8h] [rbp-58h]
  int v76; // [rsp+ACh] [rbp-54h]
  int *v77; // [rsp+B0h] [rbp-50h]
  int v78; // [rsp+B8h] [rbp-48h]
  int v79; // [rsp+BCh] [rbp-44h]
  __int64 v80; // [rsp+C0h] [rbp-40h]
  __int64 v81; // [rsp+C8h] [rbp-38h]
  __int64 v82; // [rsp+D0h] [rbp-30h]
  __int64 v83; // [rsp+D8h] [rbp-28h]
  __int64 v84; // [rsp+E0h] [rbp-20h]
  __int64 v85; // [rsp+E8h] [rbp-18h]
  __int64 v86; // [rsp+F0h] [rbp-10h]
  __int64 v87; // [rsp+F8h] [rbp-8h]
  __int64 v88; // [rsp+100h] [rbp+0h]
  __int64 v89; // [rsp+108h] [rbp+8h]
  __int64 v90; // [rsp+110h] [rbp+10h]
  __int64 v91; // [rsp+118h] [rbp+18h]
  __int64 v92; // [rsp+120h] [rbp+20h]
  __int64 v93; // [rsp+128h] [rbp+28h]
  __int64 v94; // [rsp+130h] [rbp+30h]
  __int64 v95; // [rsp+138h] [rbp+38h]
  int *v96; // [rsp+140h] [rbp+40h]
  int v97; // [rsp+148h] [rbp+48h]
  int v98; // [rsp+14Ch] [rbp+4Ch]
  int *v99; // [rsp+150h] [rbp+50h]
  int v100; // [rsp+158h] [rbp+58h]
  int v101; // [rsp+15Ch] [rbp+5Ch]
  int *v102; // [rsp+160h] [rbp+60h]
  int v103; // [rsp+168h] [rbp+68h]
  int v104; // [rsp+16Ch] [rbp+6Ch]
  int *v105; // [rsp+170h] [rbp+70h]
  int v106; // [rsp+178h] [rbp+78h]
  int v107; // [rsp+17Ch] [rbp+7Ch]
  __int64 v108; // [rsp+180h] [rbp+80h]
  __int64 v109; // [rsp+188h] [rbp+88h]
  __int64 v110; // [rsp+190h] [rbp+90h]
  __int64 v111; // [rsp+198h] [rbp+98h]
  __int64 v112; // [rsp+1A0h] [rbp+A0h]
  __int64 v113; // [rsp+1A8h] [rbp+A8h]

  v112 = a26;
  v110 = a25;
  v27 = -1;
  v108 = a24;
  v29 = 2;
  v113 = 4;
  v111 = 1;
  v109 = 4;
  v30 = *a23;
  if ( *a23 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &dword_140033A5C;
    v32 = 2;
  }
  v106 = v32;
  v105 = v30;
  v107 = 0;
  v33 = *a22;
  if ( *a22 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = &dword_140033A5C;
    v35 = 2;
  }
  v103 = v35;
  v102 = v33;
  v104 = 0;
  v36 = *a21;
  if ( *a21 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &dword_140033A5C;
    v38 = 2;
  }
  v100 = v38;
  v99 = v36;
  v101 = 0;
  v39 = *a20;
  if ( *a20 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_WORD *)v39 + v40) );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = &dword_140033A5C;
    v41 = 2;
  }
  v97 = v41;
  v94 = a19;
  v92 = a18;
  v90 = a17;
  v88 = a16;
  v86 = a15;
  v84 = a14;
  v82 = a13;
  v80 = a12;
  v96 = v39;
  v98 = 0;
  v95 = 4;
  v42 = *a11;
  v93 = 4;
  v91 = 4;
  v89 = 4;
  v87 = 4;
  v85 = 4;
  v83 = 4;
  v81 = 4;
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)v42 + v43) );
    v44 = 2 * v43 + 2;
  }
  else
  {
    v42 = &dword_140033A5C;
    v44 = 2;
  }
  v78 = v44;
  v77 = v42;
  v79 = 0;
  v45 = *a10;
  if ( *a10 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_WORD *)v45 + v46) );
    v47 = 2 * v46 + 2;
  }
  else
  {
    v45 = &dword_140033A5C;
    v47 = 2;
  }
  v75 = v47;
  v74 = v45;
  v76 = 0;
  v48 = *a9;
  if ( *a9 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_WORD *)v48 + v49) );
    v50 = 2 * v49 + 2;
  }
  else
  {
    v48 = &dword_140033A5C;
    v50 = 2;
  }
  v72 = v50;
  v71 = v48;
  v73 = 0;
  v51 = *a8;
  if ( *a8 )
  {
    v52 = -1;
    do
      ++v52;
    while ( *((_WORD *)v51 + v52) );
    v53 = 2 * v52 + 2;
  }
  else
  {
    v51 = &dword_140033A5C;
    v53 = 2;
  }
  v69 = v53;
  v68 = v51;
  v70 = 0;
  v54 = *a7;
  if ( *a7 )
  {
    v55 = -1;
    do
      ++v55;
    while ( *((_WORD *)v54 + v55) );
    v56 = 2 * v55 + 2;
  }
  else
  {
    v54 = &dword_140033A5C;
    v56 = 2;
  }
  v66 = v56;
  v65 = v54;
  v67 = 0;
  v57 = *a6;
  if ( *a6 )
  {
    do
      ++v27;
    while ( *((_WORD *)v57 + v27) );
    v29 = 2 * v27 + 2;
  }
  else
  {
    v57 = &dword_140033A5C;
  }
  v60 = a5;
  v62 = v57;
  v63 = v29;
  v64 = 0;
  v61 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x18u, &v59);
}

```

## disassembly

```asm
0x1400010ac  mov     [rsp-8+arg_10], rbx
0x1400010b1  mov     [rsp-8+arg_18], rdi
0x1400010b6  push    rbp
0x1400010b7  lea     rbp, [rsp-0C0h]
0x1400010bf  sub     rsp, 1C0h
0x1400010c6  mov     rax, cs:__security_cookie
0x1400010cd  xor     rax, rsp
0x1400010d0  mov     [rbp+0C0h+var_10], rax
0x1400010d7  mov     rax, [rbp+0C0h+arg_C8]
0x1400010de  lea     rbx, dword_140033A5C
0x1400010e5  mov     [rbp+0C0h+var_20], rax
0x1400010ec  xor     r9d, r9d; int
0x1400010ef  mov     rax, [rbp+0C0h+arg_C0]
0x1400010f6  mov     r10, rcx
0x1400010f9  mov     [rbp+0C0h+var_30], rax
0x140001100  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001104  mov     rax, [rbp+0C0h+arg_B8]
0x14000110b  mov     r11, rdx
0x14000110e  mov     [rbp+0C0h+var_40], rax
0x140001115  lea     edx, [r9+2]
0x140001119  mov     rax, [rbp+0C0h+arg_B0]
0x140001120  mov     [rbp+0C0h+var_18], 4
0x14000112b  mov     [rbp+0C0h+var_28], 1
0x140001136  mov     [rbp+0C0h+var_38], 4
0x140001141  mov     r8, [rax]
0x140001144  test    r8, r8
0x140001147  jz      short loc_14000115F
0x140001149  mov     rax, rcx
0x14000114c  inc     rax
0x14000114f  cmp     [r8+rax*2], r9w
0x140001154  jnz     short loc_14000114C
0x140001156  lea     eax, ds:2[rax*2]
0x14000115d  jmp     short loc_140001164
0x14000115f  mov     r8, rbx
0x140001162  mov     eax, edx
0x140001164  mov     [rbp+0C0h+var_48], eax
0x140001167  mov     rax, [rbp+0C0h+arg_A8]
0x14000116e  mov     [rbp+0C0h+var_50], r8
0x140001172  mov     [rbp+0C0h+var_44], r9d
0x140001176  mov     r8, [rax]
0x140001179  test    r8, r8
0x14000117c  jz      short loc_140001194
0x14000117e  mov     rax, rcx
0x140001181  inc     rax
0x140001184  cmp     [r8+rax*2], r9w
0x140001189  jnz     short loc_140001181
0x14000118b  lea     eax, ds:2[rax*2]
0x140001192  jmp     short loc_140001199
0x140001194  mov     r8, rbx
0x140001197  mov     eax, edx
0x140001199  mov     [rbp+0C0h+var_58], eax
0x14000119c  mov     rax, [rbp+0C0h+arg_A0]
0x1400011a3  mov     [rbp+0C0h+var_60], r8
0x1400011a7  mov     [rbp+0C0h+var_54], r9d
0x1400011ab  mov     r8, [rax]
0x1400011ae  test    r8, r8
0x1400011b1  jz      short loc_1400011C9
0x1400011b3  mov     rax, rcx
0x1400011b6  inc     rax
0x1400011b9  cmp     [r8+rax*2], r9w
0x1400011be  jnz     short loc_1400011B6
0x1400011c0  lea     eax, ds:2[rax*2]
0x1400011c7  jmp     short loc_1400011CE
0x1400011c9  mov     r8, rbx
0x1400011cc  mov     eax, edx
0x1400011ce  mov     [rbp+0C0h+var_68], eax
0x1400011d1  mov     rax, [rbp+0C0h+arg_98]
0x1400011d8  mov     [rbp+0C0h+var_70], r8
0x1400011dc  mov     [rbp+0C0h+var_64], r9d
0x1400011e0  mov     r8, [rax]
0x1400011e3  test    r8, r8
0x1400011e6  jz      short loc_1400011FE
0x1400011e8  mov     rax, rcx
0x1400011eb  inc     rax
0x1400011ee  cmp     [r8+rax*2], r9w
0x1400011f3  jnz     short loc_1400011EB
0x1400011f5  lea     eax, ds:2[rax*2]
0x1400011fc  jmp     short loc_140001203
0x1400011fe  mov     r8, rbx
0x140001201  mov     eax, edx
0x140001203  mov     [rbp+0C0h+var_78], eax
0x140001206  mov     rax, [rbp+0C0h+arg_90]
0x14000120d  mov     [rbp+0C0h+var_90], rax
0x140001211  mov     rax, [rbp+0C0h+arg_88]
0x140001218  mov     [rbp+0C0h+var_A0], rax
0x14000121c  mov     rax, [rbp+0C0h+arg_80]
0x140001223  mov     [rbp+0C0h+var_B0], rax
0x140001227  mov     rax, [rbp+0C0h+arg_78]
0x14000122e  mov     [rbp+0C0h+var_C0], rax
0x140001232  mov     rax, [rbp+0C0h+arg_70]
0x140001239  mov     [rbp+0C0h+var_D0], rax
0x14000123d  mov     rax, [rbp+0C0h+arg_68]
0x140001244  mov     [rbp+0C0h+var_E0], rax
0x140001248  mov     rax, [rbp+0C0h+arg_60]
0x14000124f  mov     [rbp+0C0h+var_F0], rax
0x140001253  mov     rax, [rbp+0C0h+arg_58]
0x14000125a  mov     [rbp+0C0h+var_100], rax
0x14000125e  mov     rax, [rbp+0C0h+arg_50]
0x140001265  mov     [rbp+0C0h+var_80], r8
0x140001269  mov     [rbp+0C0h+var_74], r9d
0x14000126d  mov     [rbp+0C0h+var_88], 4
0x140001275  mov     r8, [rax]
0x140001278  mov     [rbp+0C0h+var_98], 4
0x140001280  mov     [rbp+0C0h+var_A8], 4
0x140001288  mov     [rbp+0C0h+var_B8], 4
0x140001290  mov     [rbp+0C0h+var_C8], 4
0x140001298  mov     [rbp+0C0h+var_D8], 4
0x1400012a0  mov     [rbp+0C0h+var_E8], 4
0x1400012a8  mov     [rbp+0C0h+var_F8], 4
0x1400012b0  test    r8, r8
0x1400012b3  jz      short loc_1400012CB
0x1400012b5  mov     rax, rcx
0x1400012b8  inc     rax
0x1400012bb  cmp     [r8+rax*2], r9w
0x1400012c0  jnz     short loc_1400012B8
0x1400012c2  lea     eax, ds:2[rax*2]
0x1400012c9  jmp     short loc_1400012D0
0x1400012cb  mov     r8, rbx
0x1400012ce  mov     eax, edx
0x1400012d0  mov     [rbp+0C0h+var_108], eax
0x1400012d3  mov     rax, [rbp+0C0h+arg_48]
0x1400012da  mov     [rbp+0C0h+var_110], r8
0x1400012de  mov     [rbp+0C0h+var_104], r9d
0x1400012e2  mov     r8, [rax]
0x1400012e5  test    r8, r8
0x1400012e8  jz      short loc_140001300
0x1400012ea  mov     rax, rcx
0x1400012ed  inc     rax
0x1400012f0  cmp     [r8+rax*2], r9w
0x1400012f5  jnz     short loc_1400012ED
0x1400012f7  lea     eax, ds:2[rax*2]
0x1400012fe  jmp     short loc_140001305
0x140001300  mov     r8, rbx
0x140001303  mov     eax, edx
0x140001305  mov     [rbp+0C0h+var_118], eax
0x140001308  mov     rax, [rbp+0C0h+arg_40]
0x14000130f  mov     [rbp+0C0h+var_120], r8
0x140001313  mov     [rbp+0C0h+var_114], r9d
0x140001317  mov     r8, [rax]
0x14000131a  test    r8, r8
0x14000131d  jz      short loc_140001335
0x14000131f  mov     rax, rcx
0x140001322  inc     rax
0x140001325  cmp     [r8+rax*2], r9w
0x14000132a  jnz     short loc_140001322
0x14000132c  lea     eax, ds:2[rax*2]
0x140001333  jmp     short loc_14000133A
0x140001335  mov     r8, rbx
0x140001338  mov     eax, edx
0x14000133a  mov     [rbp+0C0h+var_128], eax
0x14000133d  mov     rax, [rbp+0C0h+arg_38]
0x140001344  mov     [rbp+0C0h+var_130], r8
0x140001348  mov     [rbp+0C0h+var_124], r9d
0x14000134c  mov     r8, [rax]
0x14000134f  test    r8, r8
0x140001352  jz      short loc_14000136A
0x140001354  mov     rax, rcx
0x140001357  inc     rax
0x14000135a  cmp     [r8+rax*2], r9w
0x14000135f  jnz     short loc_140001357
0x140001361  lea     eax, ds:2[rax*2]
0x140001368  jmp     short loc_14000136F
0x14000136a  mov     r8, rbx
0x14000136d  mov     eax, edx
0x14000136f  mov     [rbp+0C0h+var_138], eax
0x140001372  mov     rax, [rbp+0C0h+arg_30]
0x140001379  mov     [rbp+0C0h+var_140], r8
0x14000137d  mov     [rbp+0C0h+var_134], r9d
0x140001381  mov     r8, [rax]
0x140001384  test    r8, r8
0x140001387  jz      short loc_14000139F
0x140001389  mov     rax, rcx
0x14000138c  inc     rax
0x14000138f  cmp     [r8+rax*2], r9w
0x140001394  jnz     short loc_14000138C
0x140001396  lea     eax, ds:2[rax*2]
0x14000139d  jmp     short loc_1400013A4
0x14000139f  mov     r8, rbx
0x1400013a2  mov     eax, edx
0x1400013a4  mov     [rsp+1C0h+var_148], eax
0x1400013a8  mov     rax, [rbp+0C0h+arg_28]
0x1400013af  mov     [rsp+1C0h+var_150], r8
0x1400013b4  mov     [rsp+1C0h+var_144], r9d
0x1400013b9  mov     r8, [rax]
0x1400013bc  test    r8, r8
0x1400013bf  jz      short loc_1400013D4
0x1400013c1  inc     rcx
0x1400013c4  cmp     [r8+rcx*2], r9w
0x1400013c9  jnz     short loc_1400013C1
0x1400013cb  lea     edx, ds:2[rcx*2]
0x1400013d2  jmp     short loc_1400013D7
0x1400013d4  mov     r8, rbx
0x1400013d7  mov     rax, [rbp+0C0h+arg_20]
0x1400013de  mov     rcx, r10; int
0x1400013e1  mov     [rsp+1C0h+var_170], rax
0x1400013e6  lea     rax, [rsp+1C0h+var_190]
0x1400013eb  mov     [rsp+1C0h+var_160], r8
0x1400013f0  xor     r8d, r8d; int
0x1400013f3  mov     [rsp+1C0h+var_158], edx
0x1400013f7  mov     rdx, r11; int
0x1400013fa  mov     [rsp+1C0h+var_198], rax; PEVENT_DATA_DESCRIPTOR
0x1400013ff  mov     [rsp+1C0h+var_1A0], 18h; ULONG
0x140001407  mov     [rsp+1C0h+var_154], r9d
0x14000140c  mov     [rsp+1C0h+var_168], 8
0x140001415  call    _tlgWriteTransfer_EventWriteTransfer
0x14000141a  mov     rcx, [rbp+0C0h+var_10]
0x140001421  xor     rcx, rsp; StackCookie
0x140001424  call    __security_check_cookie
0x140001429  lea     r11, [rsp+1C0h+var_s0]
0x140001431  mov     rbx, [r11+20h]
0x140001435  mov     rdi, [r11+28h]
0x140001439  mov     rsp, r11
0x14000143c  pop     rbp
0x14000143d  retn
```
