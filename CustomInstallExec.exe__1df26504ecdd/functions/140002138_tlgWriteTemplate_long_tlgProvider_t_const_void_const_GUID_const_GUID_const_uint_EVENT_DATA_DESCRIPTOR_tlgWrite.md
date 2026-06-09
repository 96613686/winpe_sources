# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140002138`
- end: `0x140002428`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a070`
- `0x14000a73c`

## callees

- `0x140002138`
- `0x1400025b8`
- `0x1400033b0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        const unsigned __int16 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const unsigned __int16 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const unsigned __int16 **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v26; // r8d
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  const unsigned __int16 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  _BYTE v53[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  const unsigned __int16 *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  const unsigned __int16 *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v96; // [rsp+160h] [rbp+60h]
  int v97; // [rsp+168h] [rbp+68h]
  int v98; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v26 = 1;
  v27 = *a22;
  if ( *a22 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &dword_140010DA4;
    v29 = 1;
  }
  v97 = v29;
  v30 = 2;
  v94 = a21;
  v92 = a20;
  v96 = v27;
  v98 = 0;
  v95 = 4;
  v31 = *a19;
  v93 = 4;
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &qword_140010DA8;
    v33 = 2;
  }
  v90 = v33;
  v89 = v31;
  v91 = 0;
  v34 = *a18;
  if ( *a18 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &dword_140010DA4;
    v36 = 1;
  }
  v87 = v36;
  v84 = a17;
  v86 = v34;
  v88 = 0;
  v85 = 4;
  v37 = *a16;
  if ( *a16 )
  {
    v38 = -1;
    do
      ++v38;
    while ( v37[v38] );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &qword_140010DA8;
    v39 = 2;
  }
  v82 = v39;
  v81 = v37;
  v83 = 0;
  v40 = *a15;
  if ( *a15 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &dword_140010DA4;
    v42 = 1;
  }
  v79 = v42;
  v76 = a14;
  v78 = v40;
  v80 = 0;
  v77 = 4;
  v43 = *a13;
  if ( *a13 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &dword_140010DA4;
    v45 = 1;
  }
  v74 = v45;
  v71 = a12;
  v73 = v43;
  v75 = 0;
  v72 = 4;
  v46 = *a11;
  if ( *a11 )
  {
    v47 = -1;
    do
      ++v47;
    while ( v46[v47] );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &qword_140010DA8;
  }
  v66 = a10;
  v68 = v46;
  v69 = v30;
  v70 = 0;
  v48 = *a9;
  v67 = 4;
  if ( v48 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &dword_140010DA4;
    v50 = 1;
  }
  v64 = v50;
  v61 = a8;
  v63 = v48;
  v65 = 0;
  v62 = 4;
  v51 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v51 + v24) );
    v26 = v24 + 1;
  }
  else
  {
    v51 = &dword_140010DA4;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 20, v53);
}

```

## disassembly

```asm
0x140002138  push    rbp
0x14000213a  push    rbx
0x14000213b  push    rsi
0x14000213c  push    rdi
0x14000213d  push    r15
0x14000213f  lea     rbp, [rsp-80h]
0x140002144  sub     rsp, 180h
0x14000214b  mov     rax, cs:__security_cookie
0x140002152  xor     rax, rsp
0x140002155  mov     [rbp+0A0h+var_30], rax
0x140002159  mov     rax, [rbp+0A0h+arg_A8]
0x140002160  lea     rsi, dword_140010DA4
0x140002167  mov     r11, rdx
0x14000216a  mov     r10, rcx
0x14000216d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140002171  xor     edi, edi
0x140002173  mov     rbx, r8
0x140002176  mov     r8d, 1
0x14000217c  mov     rcx, [rax]
0x14000217f  test    rcx, rcx
0x140002182  jz      short loc_140002194
0x140002184  mov     rax, rdx
0x140002187  inc     rax
0x14000218a  cmp     [rcx+rax], dil
0x14000218e  jnz     short loc_140002187
0x140002190  inc     eax
0x140002192  jmp     short loc_14000219A
0x140002194  mov     rcx, rsi
0x140002197  mov     eax, r8d
0x14000219a  mov     [rbp+0A0h+var_38], eax
0x14000219d  mov     r9d, 2
0x1400021a3  mov     rax, [rbp+0A0h+arg_A0]
0x1400021aa  mov     [rbp+0A0h+var_50], rax
0x1400021ae  mov     rax, [rbp+0A0h+arg_98]
0x1400021b5  mov     [rbp+0A0h+var_60], rax
0x1400021b9  mov     rax, [rbp+0A0h+arg_90]
0x1400021c0  mov     [rbp+0A0h+var_40], rcx
0x1400021c4  mov     [rbp+0A0h+var_34], edi
0x1400021c7  mov     [rbp+0A0h+var_48], 4
0x1400021cf  mov     rcx, [rax]
0x1400021d2  mov     [rbp+0A0h+var_58], 4
0x1400021da  test    rcx, rcx
0x1400021dd  jz      short loc_1400021F4
0x1400021df  mov     rax, rdx
0x1400021e2  inc     rax
0x1400021e5  cmp     [rcx+rax*2], di
0x1400021e9  jnz     short loc_1400021E2
0x1400021eb  lea     eax, ds:2[rax*2]
0x1400021f2  jmp     short loc_1400021FE
0x1400021f4  lea     rcx, qword_140010DA8
0x1400021fb  mov     eax, r9d
0x1400021fe  mov     [rbp+0A0h+var_68], eax
0x140002201  mov     rax, [rbp+0A0h+arg_88]
0x140002208  mov     [rbp+0A0h+var_70], rcx
0x14000220c  mov     [rbp+0A0h+var_64], edi
0x14000220f  mov     rcx, [rax]
0x140002212  test    rcx, rcx
0x140002215  jz      short loc_140002227
0x140002217  mov     rax, rdx
0x14000221a  inc     rax
0x14000221d  cmp     [rcx+rax], dil
0x140002221  jnz     short loc_14000221A
0x140002223  inc     eax
0x140002225  jmp     short loc_14000222D
0x140002227  mov     rcx, rsi
0x14000222a  mov     eax, r8d
0x14000222d  mov     [rbp+0A0h+var_78], eax
0x140002230  mov     rax, [rbp+0A0h+arg_80]
0x140002237  mov     [rbp+0A0h+var_90], rax
0x14000223b  mov     rax, [rbp+0A0h+arg_78]
0x140002242  mov     [rbp+0A0h+var_80], rcx
0x140002246  mov     [rbp+0A0h+var_74], edi
0x140002249  mov     [rbp+0A0h+var_88], 4
0x140002251  mov     rcx, [rax]
0x140002254  test    rcx, rcx
0x140002257  jz      short loc_14000226E
0x140002259  mov     rax, rdx
0x14000225c  inc     rax
0x14000225f  cmp     [rcx+rax*2], di
0x140002263  jnz     short loc_14000225C
0x140002265  lea     eax, ds:2[rax*2]
0x14000226c  jmp     short loc_140002278
0x14000226e  lea     rcx, qword_140010DA8
0x140002275  mov     eax, r9d
0x140002278  mov     [rbp+0A0h+var_98], eax
0x14000227b  mov     rax, [rbp+0A0h+arg_70]
0x140002282  mov     [rbp+0A0h+var_A0], rcx
0x140002286  mov     [rbp+0A0h+var_94], edi
0x140002289  mov     rcx, [rax]
0x14000228c  test    rcx, rcx
0x14000228f  jz      short loc_1400022A1
0x140002291  mov     rax, rdx
0x140002294  inc     rax
0x140002297  cmp     [rcx+rax], dil
0x14000229b  jnz     short loc_140002294
0x14000229d  inc     eax
0x14000229f  jmp     short loc_1400022A7
0x1400022a1  mov     rcx, rsi
0x1400022a4  mov     eax, r8d
0x1400022a7  mov     [rbp+0A0h+var_A8], eax
0x1400022aa  mov     rax, [rbp+0A0h+arg_68]
0x1400022b1  mov     [rbp+0A0h+var_C0], rax
0x1400022b5  mov     rax, [rbp+0A0h+arg_60]
0x1400022bc  mov     [rbp+0A0h+var_B0], rcx
0x1400022c0  mov     [rbp+0A0h+var_A4], edi
0x1400022c3  mov     [rbp+0A0h+var_B8], 4
0x1400022cb  mov     rcx, [rax]
0x1400022ce  test    rcx, rcx
0x1400022d1  jz      short loc_1400022E3
0x1400022d3  mov     rax, rdx
0x1400022d6  inc     rax
0x1400022d9  cmp     [rcx+rax], dil
0x1400022dd  jnz     short loc_1400022D6
0x1400022df  inc     eax
0x1400022e1  jmp     short loc_1400022E9
0x1400022e3  mov     rcx, rsi
0x1400022e6  mov     eax, r8d
0x1400022e9  mov     [rbp+0A0h+var_C8], eax
0x1400022ec  mov     rax, [rbp+0A0h+arg_58]
0x1400022f3  mov     [rbp+0A0h+var_E0], rax
0x1400022f7  mov     rax, [rbp+0A0h+arg_50]
0x1400022fe  mov     [rbp+0A0h+var_D0], rcx
0x140002302  mov     [rbp+0A0h+var_C4], edi
0x140002305  mov     [rbp+0A0h+var_D8], 4
0x14000230d  mov     rcx, [rax]
0x140002310  test    rcx, rcx
0x140002313  jz      short loc_14000232B
0x140002315  mov     rax, rdx
0x140002318  inc     rax
0x14000231b  cmp     [rcx+rax*2], di
0x14000231f  jnz     short loc_140002318
0x140002321  lea     r9d, ds:2[rax*2]
0x140002329  jmp     short loc_140002332
0x14000232b  lea     rcx, qword_140010DA8
0x140002332  mov     rax, [rbp+0A0h+arg_48]
0x140002339  mov     [rbp+0A0h+var_100], rax
0x14000233d  mov     rax, [rbp+0A0h+arg_40]
0x140002344  mov     [rbp+0A0h+var_F0], rcx
0x140002348  mov     [rbp+0A0h+var_E8], r9d
0x14000234c  mov     [rbp+0A0h+var_E4], edi
0x14000234f  mov     rcx, [rax]
0x140002352  mov     [rbp+0A0h+var_F8], 4
0x14000235a  test    rcx, rcx
0x14000235d  jz      short loc_14000236F
0x14000235f  mov     rax, rdx
0x140002362  inc     rax
0x140002365  cmp     [rcx+rax], dil
0x140002369  jnz     short loc_140002362
0x14000236b  inc     eax
0x14000236d  jmp     short loc_140002375
0x14000236f  mov     rcx, rsi
0x140002372  mov     eax, r8d
0x140002375  mov     [rbp+0A0h+var_108], eax
0x140002378  mov     rax, [rbp+0A0h+arg_38]
0x14000237f  mov     [rbp+0A0h+var_120], rax
0x140002383  mov     rax, [rbp+0A0h+arg_30]
0x14000238a  mov     [rbp+0A0h+var_110], rcx
0x14000238e  mov     [rbp+0A0h+var_104], edi
0x140002391  mov     [rbp+0A0h+var_118], 4
0x140002399  mov     rcx, [rax]
0x14000239c  test    rcx, rcx
0x14000239f  jz      short loc_1400023B0
0x1400023a1  inc     rdx
0x1400023a4  cmp     [rcx+rdx], dil
0x1400023a8  jnz     short loc_1400023A1
0x1400023aa  lea     r8d, [rdx+1]
0x1400023ae  jmp     short loc_1400023B3
0x1400023b0  mov     rcx, rsi
0x1400023b3  mov     rax, [rbp+0A0h+arg_28]
0x1400023ba  xor     r9d, r9d
0x1400023bd  mov     [rsp+1A0h+var_140], rax
0x1400023c2  mov     rdx, r11
0x1400023c5  mov     rax, [rbp+0A0h+arg_20]
0x1400023cc  mov     [rsp+1A0h+var_150], rax
0x1400023d1  lea     rax, [rsp+1A0h+var_170]
0x1400023d6  mov     [rsp+1A0h+var_130], rcx
0x1400023db  mov     rcx, r10
0x1400023de  mov     [rsp+1A0h+var_128], r8d
0x1400023e3  mov     r8, rbx
0x1400023e6  mov     [rsp+1A0h+var_178], rax
0x1400023eb  mov     [rsp+1A0h+var_180], 14h
0x1400023f3  mov     [rsp+1A0h+var_124], edi
0x1400023f7  mov     [rsp+1A0h+var_138], 4
0x140002400  mov     [rsp+1A0h+var_148], 8
0x140002409  call    _tlgWriteTransfer_EventWriteTransfer
0x14000240e  mov     rcx, [rbp+0A0h+var_30]
0x140002412  xor     rcx, rsp; StackCookie
0x140002415  call    __security_check_cookie
0x14000241a  add     rsp, 180h
0x140002421  pop     r15
0x140002423  pop     rdi
0x140002424  pop     rsi
0x140002425  pop     rbx
0x140002426  pop     rbp
0x140002427  retn
```
