# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180002050`
- end: `0x18000239d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564456@Z`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b26c`

## callees

- `0x180001640`
- `0x180002050`
- `0x180002910`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        __int64 **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        __int64 **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        __int64 **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23,
        __int64 **a24)
{
  __int64 v26; // rdx
  int v28; // r9d
  __int64 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int v32; // r8d
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  __int64 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  __int64 *v51; // rcx
  __int64 v52; // rax
  const unsigned __int16 *v53; // rcx
  __int64 v54; // rax
  int v55; // eax
  const unsigned __int16 *v56; // rcx
  struct _EVENT_DATA_DESCRIPTOR v58; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v59; // [rsp+50h] [rbp-B0h]
  __int64 v60; // [rsp+58h] [rbp-A8h]
  __int64 v61; // [rsp+60h] [rbp-A0h]
  __int64 v62; // [rsp+68h] [rbp-98h]
  __int64 v63; // [rsp+70h] [rbp-90h]
  __int64 v64; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v65; // [rsp+80h] [rbp-80h]
  int v66; // [rsp+88h] [rbp-78h]
  int v67; // [rsp+8Ch] [rbp-74h]
  __int64 v68; // [rsp+90h] [rbp-70h]
  __int64 v69; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v70; // [rsp+A0h] [rbp-60h]
  int v71; // [rsp+A8h] [rbp-58h]
  int v72; // [rsp+ACh] [rbp-54h]
  __int64 v73; // [rsp+B0h] [rbp-50h]
  __int64 v74; // [rsp+B8h] [rbp-48h]
  __int64 *v75; // [rsp+C0h] [rbp-40h]
  int v76; // [rsp+C8h] [rbp-38h]
  int v77; // [rsp+CCh] [rbp-34h]
  __int64 v78; // [rsp+D0h] [rbp-30h]
  __int64 v79; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v80; // [rsp+E0h] [rbp-20h]
  int v81; // [rsp+E8h] [rbp-18h]
  int v82; // [rsp+ECh] [rbp-14h]
  __int64 v83; // [rsp+F0h] [rbp-10h]
  __int64 v84; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v85; // [rsp+100h] [rbp+0h]
  int v86; // [rsp+108h] [rbp+8h]
  int v87; // [rsp+10Ch] [rbp+Ch]
  __int64 *v88; // [rsp+110h] [rbp+10h]
  int v89; // [rsp+118h] [rbp+18h]
  int v90; // [rsp+11Ch] [rbp+1Ch]
  __int64 v91; // [rsp+120h] [rbp+20h]
  __int64 v92; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v93; // [rsp+130h] [rbp+30h]
  int v94; // [rsp+138h] [rbp+38h]
  int v95; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v96; // [rsp+140h] [rbp+40h]
  int v97; // [rsp+148h] [rbp+48h]
  int v98; // [rsp+14Ch] [rbp+4Ch]
  __int64 v99; // [rsp+150h] [rbp+50h]
  __int64 v100; // [rsp+158h] [rbp+58h]
  __int64 v101; // [rsp+160h] [rbp+60h]
  __int64 v102; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v103; // [rsp+170h] [rbp+70h]
  int v104; // [rsp+178h] [rbp+78h]
  int v105; // [rsp+17Ch] [rbp+7Ch]
  __int64 *v106; // [rsp+180h] [rbp+80h]
  int v107; // [rsp+188h] [rbp+88h]
  int v108; // [rsp+18Ch] [rbp+8Ch]

  v26 = -1;
  v28 = 2;
  v29 = *a24;
  if ( *a24 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)v29 + v30) );
    v31 = 2 * v30 + 2;
  }
  else
  {
    v29 = qword_180012C50;
    v31 = 2;
  }
  v107 = v31;
  v32 = 1;
  v106 = v29;
  v108 = 0;
  v33 = *a23;
  if ( *a23 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &qword_180012910;
    v35 = 1;
  }
  v104 = v35;
  v101 = a22;
  v99 = a21;
  v103 = v33;
  v105 = 0;
  v102 = 4;
  v36 = *a20;
  v100 = 4;
  if ( v36 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = qword_180012C50;
    v38 = 2;
  }
  v97 = v38;
  v96 = v36;
  v98 = 0;
  v39 = *a19;
  if ( *a19 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &qword_180012910;
    v41 = 1;
  }
  v94 = v41;
  v91 = a18;
  v93 = v39;
  v95 = 0;
  v92 = 4;
  v42 = *a17;
  if ( *a17 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)v42 + v43) );
    v44 = 2 * v43 + 2;
  }
  else
  {
    v42 = qword_180012C50;
    v44 = 2;
  }
  v89 = v44;
  v88 = v42;
  v90 = 0;
  v45 = *a16;
  if ( *a16 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_BYTE *)v45 + v46) );
    v47 = v46 + 1;
  }
  else
  {
    v45 = &qword_180012910;
    v47 = 1;
  }
  v86 = v47;
  v83 = a15;
  v85 = v45;
  v87 = 0;
  v84 = 4;
  v48 = *a14;
  if ( *a14 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &qword_180012910;
    v50 = 1;
  }
  v81 = v50;
  v78 = a13;
  v80 = v48;
  v82 = 0;
  v79 = 4;
  v51 = *a12;
  if ( *a12 )
  {
    v52 = -1;
    do
      ++v52;
    while ( *((_WORD *)v51 + v52) );
    v28 = 2 * v52 + 2;
  }
  else
  {
    v51 = qword_180012C50;
  }
  v73 = a11;
  v75 = v51;
  v76 = v28;
  v77 = 0;
  v53 = *a10;
  v74 = 4;
  if ( v53 )
  {
    v54 = -1;
    do
      ++v54;
    while ( *((_BYTE *)v53 + v54) );
    v55 = v54 + 1;
  }
  else
  {
    v53 = &qword_180012910;
    v55 = 1;
  }
  v71 = v55;
  v68 = a9;
  v70 = v53;
  v72 = 0;
  v69 = 4;
  v56 = *a8;
  if ( *a8 )
  {
    do
      ++v26;
    while ( *((_BYTE *)v56 + v26) );
    v32 = v26 + 1;
  }
  else
  {
    v56 = &qword_180012910;
  }
  v63 = a7;
  v61 = a6;
  v59 = a5;
  v65 = v56;
  v66 = v32;
  v67 = 0;
  v64 = 4;
  v62 = 8;
  v60 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x16u, &v58);
}

```

## disassembly

```asm
0x180002050  push    rbp
0x180002052  push    rbx
0x180002053  push    rsi
0x180002054  push    rdi
0x180002055  push    r14
0x180002057  lea     rbp, [rsp-0A0h]
0x18000205f  sub     rsp, 1A0h
0x180002066  mov     rax, cs:__security_cookie
0x18000206d  xor     rax, rsp
0x180002070  mov     [rbp+0C0h+var_30], rax
0x180002077  mov     rax, [rbp+0C0h+arg_B8]
0x18000207e  mov     r11, rdx
0x180002081  mov     r10, rcx
0x180002084  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002088  xor     edi, edi
0x18000208a  mov     rbx, r8
0x18000208d  mov     r9d, 2
0x180002093  mov     rcx, [rax]
0x180002096  test    rcx, rcx
0x180002099  jz      short loc_1800020B0
0x18000209b  mov     rax, rdx
0x18000209e  inc     rax
0x1800020a1  cmp     [rcx+rax*2], di
0x1800020a5  jnz     short loc_18000209E
0x1800020a7  lea     eax, ds:2[rax*2]
0x1800020ae  jmp     short loc_1800020BA
0x1800020b0  lea     rcx, qword_180012C50
0x1800020b7  mov     eax, r9d
0x1800020ba  mov     [rbp+0C0h+var_38], eax
0x1800020c0  lea     rsi, qword_180012910
0x1800020c7  mov     rax, [rbp+0C0h+arg_B0]
0x1800020ce  mov     r8d, 1
0x1800020d4  mov     [rbp+0C0h+var_40], rcx
0x1800020db  mov     [rbp+0C0h+var_34], edi
0x1800020e1  mov     rcx, [rax]
0x1800020e4  test    rcx, rcx
0x1800020e7  jz      short loc_1800020F9
0x1800020e9  mov     rax, rdx
0x1800020ec  inc     rax
0x1800020ef  cmp     [rcx+rax], dil
0x1800020f3  jnz     short loc_1800020EC
0x1800020f5  inc     eax
0x1800020f7  jmp     short loc_1800020FF
0x1800020f9  mov     rcx, rsi
0x1800020fc  mov     eax, r8d
0x1800020ff  mov     [rbp+0C0h+var_48], eax
0x180002102  mov     rax, [rbp+0C0h+arg_A8]
0x180002109  mov     [rbp+0C0h+var_60], rax
0x18000210d  mov     rax, [rbp+0C0h+arg_A0]
0x180002114  mov     [rbp+0C0h+var_70], rax
0x180002118  mov     rax, [rbp+0C0h+arg_98]
0x18000211f  mov     [rbp+0C0h+var_50], rcx
0x180002123  mov     [rbp+0C0h+var_44], edi
0x180002126  mov     [rbp+0C0h+var_58], 4
0x18000212e  mov     rcx, [rax]
0x180002131  mov     [rbp+0C0h+var_68], 4
0x180002139  test    rcx, rcx
0x18000213c  jz      short loc_180002153
0x18000213e  mov     rax, rdx
0x180002141  inc     rax
0x180002144  cmp     [rcx+rax*2], di
0x180002148  jnz     short loc_180002141
0x18000214a  lea     eax, ds:2[rax*2]
0x180002151  jmp     short loc_18000215D
0x180002153  lea     rcx, qword_180012C50
0x18000215a  mov     eax, r9d
0x18000215d  mov     [rbp+0C0h+var_78], eax
0x180002160  mov     rax, [rbp+0C0h+arg_90]
0x180002167  mov     [rbp+0C0h+var_80], rcx
0x18000216b  mov     [rbp+0C0h+var_74], edi
0x18000216e  mov     rcx, [rax]
0x180002171  test    rcx, rcx
0x180002174  jz      short loc_180002186
0x180002176  mov     rax, rdx
0x180002179  inc     rax
0x18000217c  cmp     [rcx+rax], dil
0x180002180  jnz     short loc_180002179
0x180002182  inc     eax
0x180002184  jmp     short loc_18000218C
0x180002186  mov     rcx, rsi
0x180002189  mov     eax, r8d
0x18000218c  mov     [rbp+0C0h+var_88], eax
0x18000218f  mov     rax, [rbp+0C0h+arg_88]
0x180002196  mov     [rbp+0C0h+var_A0], rax
0x18000219a  mov     rax, [rbp+0C0h+arg_80]
0x1800021a1  mov     [rbp+0C0h+var_90], rcx
0x1800021a5  mov     [rbp+0C0h+var_84], edi
0x1800021a8  mov     [rbp+0C0h+var_98], 4
0x1800021b0  mov     rcx, [rax]
0x1800021b3  test    rcx, rcx
0x1800021b6  jz      short loc_1800021CD
0x1800021b8  mov     rax, rdx
0x1800021bb  inc     rax
0x1800021be  cmp     [rcx+rax*2], di
0x1800021c2  jnz     short loc_1800021BB
0x1800021c4  lea     eax, ds:2[rax*2]
0x1800021cb  jmp     short loc_1800021D7
0x1800021cd  lea     rcx, qword_180012C50
0x1800021d4  mov     eax, r9d
0x1800021d7  mov     [rbp+0C0h+var_A8], eax
0x1800021da  mov     rax, [rbp+0C0h+arg_78]
0x1800021e1  mov     [rbp+0C0h+var_B0], rcx
0x1800021e5  mov     [rbp+0C0h+var_A4], edi
0x1800021e8  mov     rcx, [rax]
0x1800021eb  test    rcx, rcx
0x1800021ee  jz      short loc_180002200
0x1800021f0  mov     rax, rdx
0x1800021f3  inc     rax
0x1800021f6  cmp     [rcx+rax], dil
0x1800021fa  jnz     short loc_1800021F3
0x1800021fc  inc     eax
0x1800021fe  jmp     short loc_180002206
0x180002200  mov     rcx, rsi
0x180002203  mov     eax, r8d
0x180002206  mov     [rbp+0C0h+var_B8], eax
0x180002209  mov     rax, [rbp+0C0h+arg_70]
0x180002210  mov     [rbp+0C0h+var_D0], rax
0x180002214  mov     rax, [rbp+0C0h+arg_68]
0x18000221b  mov     [rbp+0C0h+var_C0], rcx
0x18000221f  mov     [rbp+0C0h+var_B4], edi
0x180002222  mov     [rbp+0C0h+var_C8], 4
0x18000222a  mov     rcx, [rax]
0x18000222d  test    rcx, rcx
0x180002230  jz      short loc_180002242
0x180002232  mov     rax, rdx
0x180002235  inc     rax
0x180002238  cmp     [rcx+rax], dil
0x18000223c  jnz     short loc_180002235
0x18000223e  inc     eax
0x180002240  jmp     short loc_180002248
0x180002242  mov     rcx, rsi
0x180002245  mov     eax, r8d
0x180002248  mov     [rbp+0C0h+var_D8], eax
0x18000224b  mov     rax, [rbp+0C0h+arg_60]
0x180002252  mov     [rbp+0C0h+var_F0], rax
0x180002256  mov     rax, [rbp+0C0h+arg_58]
0x18000225d  mov     [rbp+0C0h+var_E0], rcx
0x180002261  mov     [rbp+0C0h+var_D4], edi
0x180002264  mov     [rbp+0C0h+var_E8], 4
0x18000226c  mov     rcx, [rax]
0x18000226f  test    rcx, rcx
0x180002272  jz      short loc_18000228A
0x180002274  mov     rax, rdx
0x180002277  inc     rax
0x18000227a  cmp     [rcx+rax*2], di
0x18000227e  jnz     short loc_180002277
0x180002280  lea     r9d, ds:2[rax*2]
0x180002288  jmp     short loc_180002291
0x18000228a  lea     rcx, qword_180012C50
0x180002291  mov     rax, [rbp+0C0h+arg_50]
0x180002298  mov     [rbp+0C0h+var_110], rax
0x18000229c  mov     rax, [rbp+0C0h+arg_48]
0x1800022a3  mov     [rbp+0C0h+var_100], rcx
0x1800022a7  mov     [rbp+0C0h+var_F8], r9d
0x1800022ab  mov     [rbp+0C0h+var_F4], edi
0x1800022ae  mov     rcx, [rax]
0x1800022b1  mov     [rbp+0C0h+var_108], 4
0x1800022b9  test    rcx, rcx
0x1800022bc  jz      short loc_1800022CE
0x1800022be  mov     rax, rdx
0x1800022c1  inc     rax
0x1800022c4  cmp     [rcx+rax], dil
0x1800022c8  jnz     short loc_1800022C1
0x1800022ca  inc     eax
0x1800022cc  jmp     short loc_1800022D4
0x1800022ce  mov     rcx, rsi
0x1800022d1  mov     eax, r8d
0x1800022d4  mov     [rbp+0C0h+var_118], eax
0x1800022d7  mov     rax, [rbp+0C0h+arg_40]
0x1800022de  mov     [rbp+0C0h+var_130], rax
0x1800022e2  mov     rax, [rbp+0C0h+arg_38]
0x1800022e9  mov     [rbp+0C0h+var_120], rcx
0x1800022ed  mov     [rbp+0C0h+var_114], edi
0x1800022f0  mov     [rbp+0C0h+var_128], 4
0x1800022f8  mov     rcx, [rax]
0x1800022fb  test    rcx, rcx
0x1800022fe  jz      short loc_18000230F
0x180002300  inc     rdx
0x180002303  cmp     [rcx+rdx], dil
0x180002307  jnz     short loc_180002300
0x180002309  lea     r8d, [rdx+1]
0x18000230d  jmp     short loc_180002312
0x18000230f  mov     rcx, rsi
0x180002312  mov     rax, [rbp+0C0h+arg_30]
0x180002319  xor     r9d, r9d
0x18000231c  mov     [rsp+1C0h+var_150], rax
0x180002321  mov     rdx, r11
0x180002324  mov     rax, [rbp+0C0h+arg_28]
0x18000232b  mov     [rsp+1C0h+var_160], rax
0x180002330  mov     rax, [rbp+0C0h+arg_20]
0x180002337  mov     [rsp+1C0h+var_170], rax
0x18000233c  lea     rax, [rsp+1C0h+var_190]
0x180002341  mov     [rbp+0C0h+var_140], rcx
0x180002345  mov     rcx, r10
0x180002348  mov     [rbp+0C0h+var_138], r8d
0x18000234c  mov     r8, rbx
0x18000234f  mov     [rsp+1C0h+var_198], rax
0x180002354  mov     [rsp+1C0h+var_1A0], 16h
0x18000235c  mov     [rbp+0C0h+var_134], edi
0x18000235f  mov     [rsp+1C0h+var_148], 4
0x180002368  mov     [rsp+1C0h+var_158], 8
0x180002371  mov     [rsp+1C0h+var_168], 8
0x18000237a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000237f  mov     rcx, [rbp+0C0h+var_30]
0x180002386  xor     rcx, rsp; StackCookie
0x180002389  call    __security_check_cookie
0x18000238e  add     rsp, 1A0h
0x180002395  pop     r14
0x180002397  pop     rdi
0x180002398  pop     rsi
0x180002399  pop     rbx
0x18000239a  pop     rbp
0x18000239b  retn
```
