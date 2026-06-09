# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800012bc`
- end: `0x1800015c7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `779`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const WCHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const WCHAR **, __int64, const unsigned __int16 **, const WCHAR **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180013140`
- `0x1800133c0`
- `0x180013640`
- `0x1800138c0`
- `0x180020a70`

## callees

- `0x1800012bc`
- `0x180001d7c`
- `0x1800032a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        const WCHAR **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const WCHAR **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const WCHAR **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23)
{
  __int64 v25; // rdx
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int v31; // r9d
  const WCHAR *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const WCHAR *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  const WCHAR *v47; // rcx
  __int64 v48; // rax
  const unsigned __int16 *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  const unsigned __int16 *v52; // rcx
  _BYTE v54[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+68h] [rbp-98h]
  __int64 v59; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v61; // [rsp+80h] [rbp-80h]
  int v62; // [rsp+88h] [rbp-78h]
  int v63; // [rsp+8Ch] [rbp-74h]
  __int64 v64; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v66; // [rsp+A0h] [rbp-60h]
  int v67; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+ACh] [rbp-54h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h]
  const WCHAR *v71; // [rsp+C0h] [rbp-40h]
  int v72; // [rsp+C8h] [rbp-38h]
  int v73; // [rsp+CCh] [rbp-34h]
  __int64 v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E8h] [rbp-18h]
  int v78; // [rsp+ECh] [rbp-14h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  const WCHAR *v84; // [rsp+110h] [rbp+10h]
  int v85; // [rsp+118h] [rbp+18h]
  int v86; // [rsp+11Ch] [rbp+1Ch]
  __int64 v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v92; // [rsp+140h] [rbp+40h]
  int v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+14Ch] [rbp+4Ch]
  __int64 v95; // [rsp+150h] [rbp+50h]
  __int64 v96; // [rsp+158h] [rbp+58h]
  __int64 v97; // [rsp+160h] [rbp+60h]
  __int64 v98; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v99; // [rsp+170h] [rbp+70h]
  int v100; // [rsp+178h] [rbp+78h]
  int v101; // [rsp+17Ch] [rbp+7Ch]

  v25 = -1;
  v27 = 1;
  v28 = *a23;
  if ( *a23 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &dword_1800320C4;
    v30 = 1;
  }
  v100 = v30;
  v31 = 2;
  v97 = a22;
  v95 = a21;
  v99 = v28;
  v101 = 0;
  v98 = 4;
  v32 = *a20;
  v96 = 4;
  if ( v32 )
  {
    v33 = -1;
    do
      ++v33;
    while ( v32[v33] );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &SubKey;
    v34 = 2;
  }
  v93 = v34;
  v92 = v32;
  v94 = 0;
  v35 = *a19;
  if ( *a19 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &dword_1800320C4;
    v37 = 1;
  }
  v90 = v37;
  v87 = a18;
  v89 = v35;
  v91 = 0;
  v88 = 4;
  v38 = *a17;
  if ( *a17 )
  {
    v39 = -1;
    do
      ++v39;
    while ( v38[v39] );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = &SubKey;
    v40 = 2;
  }
  v85 = v40;
  v84 = v38;
  v86 = 0;
  v41 = *a16;
  if ( *a16 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &dword_1800320C4;
    v43 = 1;
  }
  v82 = v43;
  v79 = a15;
  v81 = v41;
  v83 = 0;
  v80 = 4;
  v44 = *a14;
  if ( *a14 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &dword_1800320C4;
    v46 = 1;
  }
  v77 = v46;
  v74 = a13;
  v76 = v44;
  v78 = 0;
  v75 = 4;
  v47 = *a12;
  if ( *a12 )
  {
    v48 = -1;
    do
      ++v48;
    while ( v47[v48] );
    v31 = 2 * v48 + 2;
  }
  else
  {
    v47 = &SubKey;
  }
  v69 = a11;
  v71 = v47;
  v72 = v31;
  v73 = 0;
  v49 = *a10;
  v70 = 4;
  if ( v49 )
  {
    v50 = -1;
    do
      ++v50;
    while ( *((_BYTE *)v49 + v50) );
    v51 = v50 + 1;
  }
  else
  {
    v49 = &dword_1800320C4;
    v51 = 1;
  }
  v67 = v51;
  v64 = a9;
  v66 = v49;
  v68 = 0;
  v65 = 4;
  v52 = *a8;
  if ( *a8 )
  {
    do
      ++v25;
    while ( *((_BYTE *)v52 + v25) );
    v27 = v25 + 1;
  }
  else
  {
    v52 = &dword_1800320C4;
  }
  v59 = a7;
  v57 = a6;
  v55 = a5;
  v61 = v52;
  v62 = v27;
  v63 = 0;
  v60 = 4;
  v58 = 8;
  v56 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 21, v54);
}

```

## disassembly

```asm
0x1800012bc  push    rbp
0x1800012be  push    rbx
0x1800012bf  push    rsi
0x1800012c0  push    rdi
0x1800012c1  push    r14
0x1800012c3  lea     rbp, [rsp-90h]
0x1800012cb  sub     rsp, 190h
0x1800012d2  mov     rax, cs:__security_cookie
0x1800012d9  xor     rax, rsp
0x1800012dc  mov     [rbp+0B0h+var_30], rax
0x1800012e3  mov     rax, [rbp+0B0h+arg_B0]
0x1800012ea  lea     rsi, dword_1800320C4
0x1800012f1  mov     r11, rdx
0x1800012f4  mov     r10, rcx
0x1800012f7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800012fb  xor     edi, edi
0x1800012fd  mov     rbx, r8
0x180001300  mov     r8d, 1
0x180001306  mov     rcx, [rax]
0x180001309  test    rcx, rcx
0x18000130c  jz      short loc_18000131E
0x18000130e  mov     rax, rdx
0x180001311  inc     rax
0x180001314  cmp     [rcx+rax], dil
0x180001318  jnz     short loc_180001311
0x18000131a  inc     eax
0x18000131c  jmp     short loc_180001324
0x18000131e  mov     rcx, rsi
0x180001321  mov     eax, r8d
0x180001324  mov     [rbp+0B0h+var_38], eax
0x180001327  mov     r9d, 2
0x18000132d  mov     rax, [rbp+0B0h+arg_A8]
0x180001334  mov     [rbp+0B0h+var_50], rax
0x180001338  mov     rax, [rbp+0B0h+arg_A0]
0x18000133f  mov     [rbp+0B0h+var_60], rax
0x180001343  mov     rax, [rbp+0B0h+arg_98]
0x18000134a  mov     [rbp+0B0h+var_40], rcx
0x18000134e  mov     [rbp+0B0h+var_34], edi
0x180001351  mov     [rbp+0B0h+var_48], 4
0x180001359  mov     rcx, [rax]
0x18000135c  mov     [rbp+0B0h+var_58], 4
0x180001364  test    rcx, rcx
0x180001367  jz      short loc_18000137E
0x180001369  mov     rax, rdx
0x18000136c  inc     rax
0x18000136f  cmp     [rcx+rax*2], di
0x180001373  jnz     short loc_18000136C
0x180001375  lea     eax, ds:2[rax*2]
0x18000137c  jmp     short loc_180001388
0x18000137e  lea     rcx, SubKey
0x180001385  mov     eax, r9d
0x180001388  mov     [rbp+0B0h+var_68], eax
0x18000138b  mov     rax, [rbp+0B0h+arg_90]
0x180001392  mov     [rbp+0B0h+var_70], rcx
0x180001396  mov     [rbp+0B0h+var_64], edi
0x180001399  mov     rcx, [rax]
0x18000139c  test    rcx, rcx
0x18000139f  jz      short loc_1800013B1
0x1800013a1  mov     rax, rdx
0x1800013a4  inc     rax
0x1800013a7  cmp     [rcx+rax], dil
0x1800013ab  jnz     short loc_1800013A4
0x1800013ad  inc     eax
0x1800013af  jmp     short loc_1800013B7
0x1800013b1  mov     rcx, rsi
0x1800013b4  mov     eax, r8d
0x1800013b7  mov     [rbp+0B0h+var_78], eax
0x1800013ba  mov     rax, [rbp+0B0h+arg_88]
0x1800013c1  mov     [rbp+0B0h+var_90], rax
0x1800013c5  mov     rax, [rbp+0B0h+arg_80]
0x1800013cc  mov     [rbp+0B0h+var_80], rcx
0x1800013d0  mov     [rbp+0B0h+var_74], edi
0x1800013d3  mov     [rbp+0B0h+var_88], 4
0x1800013db  mov     rcx, [rax]
0x1800013de  test    rcx, rcx
0x1800013e1  jz      short loc_1800013F8
0x1800013e3  mov     rax, rdx
0x1800013e6  inc     rax
0x1800013e9  cmp     [rcx+rax*2], di
0x1800013ed  jnz     short loc_1800013E6
0x1800013ef  lea     eax, ds:2[rax*2]
0x1800013f6  jmp     short loc_180001402
0x1800013f8  lea     rcx, SubKey
0x1800013ff  mov     eax, r9d
0x180001402  mov     [rbp+0B0h+var_98], eax
0x180001405  mov     rax, [rbp+0B0h+arg_78]
0x18000140c  mov     [rbp+0B0h+var_A0], rcx
0x180001410  mov     [rbp+0B0h+var_94], edi
0x180001413  mov     rcx, [rax]
0x180001416  test    rcx, rcx
0x180001419  jz      short loc_18000142B
0x18000141b  mov     rax, rdx
0x18000141e  inc     rax
0x180001421  cmp     [rcx+rax], dil
0x180001425  jnz     short loc_18000141E
0x180001427  inc     eax
0x180001429  jmp     short loc_180001431
0x18000142b  mov     rcx, rsi
0x18000142e  mov     eax, r8d
0x180001431  mov     [rbp+0B0h+var_A8], eax
0x180001434  mov     rax, [rbp+0B0h+arg_70]
0x18000143b  mov     [rbp+0B0h+var_C0], rax
0x18000143f  mov     rax, [rbp+0B0h+arg_68]
0x180001446  mov     [rbp+0B0h+var_B0], rcx
0x18000144a  mov     [rbp+0B0h+var_A4], edi
0x18000144d  mov     [rbp+0B0h+var_B8], 4
0x180001455  mov     rcx, [rax]
0x180001458  test    rcx, rcx
0x18000145b  jz      short loc_18000146D
0x18000145d  mov     rax, rdx
0x180001460  inc     rax
0x180001463  cmp     [rcx+rax], dil
0x180001467  jnz     short loc_180001460
0x180001469  inc     eax
0x18000146b  jmp     short loc_180001473
0x18000146d  mov     rcx, rsi
0x180001470  mov     eax, r8d
0x180001473  mov     [rbp+0B0h+var_C8], eax
0x180001476  mov     rax, [rbp+0B0h+arg_60]
0x18000147d  mov     [rbp+0B0h+var_E0], rax
0x180001481  mov     rax, [rbp+0B0h+arg_58]
0x180001488  mov     [rbp+0B0h+var_D0], rcx
0x18000148c  mov     [rbp+0B0h+var_C4], edi
0x18000148f  mov     [rbp+0B0h+var_D8], 4
0x180001497  mov     rcx, [rax]
0x18000149a  test    rcx, rcx
0x18000149d  jz      short loc_1800014B5
0x18000149f  mov     rax, rdx
0x1800014a2  inc     rax
0x1800014a5  cmp     [rcx+rax*2], di
0x1800014a9  jnz     short loc_1800014A2
0x1800014ab  lea     r9d, ds:2[rax*2]
0x1800014b3  jmp     short loc_1800014BC
0x1800014b5  lea     rcx, SubKey
0x1800014bc  mov     rax, [rbp+0B0h+arg_50]
0x1800014c3  mov     [rbp+0B0h+var_100], rax
0x1800014c7  mov     rax, [rbp+0B0h+arg_48]
0x1800014ce  mov     [rbp+0B0h+var_F0], rcx
0x1800014d2  mov     [rbp+0B0h+var_E8], r9d
0x1800014d6  mov     [rbp+0B0h+var_E4], edi
0x1800014d9  mov     rcx, [rax]
0x1800014dc  mov     [rbp+0B0h+var_F8], 4
0x1800014e4  test    rcx, rcx
0x1800014e7  jz      short loc_1800014F9
0x1800014e9  mov     rax, rdx
0x1800014ec  inc     rax
0x1800014ef  cmp     [rcx+rax], dil
0x1800014f3  jnz     short loc_1800014EC
0x1800014f5  inc     eax
0x1800014f7  jmp     short loc_1800014FF
0x1800014f9  mov     rcx, rsi
0x1800014fc  mov     eax, r8d
0x1800014ff  mov     [rbp+0B0h+var_108], eax
0x180001502  mov     rax, [rbp+0B0h+arg_40]
0x180001509  mov     [rbp+0B0h+var_120], rax
0x18000150d  mov     rax, [rbp+0B0h+arg_38]
0x180001514  mov     [rbp+0B0h+var_110], rcx
0x180001518  mov     [rbp+0B0h+var_104], edi
0x18000151b  mov     [rbp+0B0h+var_118], 4
0x180001523  mov     rcx, [rax]
0x180001526  test    rcx, rcx
0x180001529  jz      short loc_18000153A
0x18000152b  inc     rdx
0x18000152e  cmp     [rcx+rdx], dil
0x180001532  jnz     short loc_18000152B
0x180001534  lea     r8d, [rdx+1]
0x180001538  jmp     short loc_18000153D
0x18000153a  mov     rcx, rsi
0x18000153d  mov     rax, [rbp+0B0h+arg_30]
0x180001544  xor     r9d, r9d
0x180001547  mov     [rsp+1B0h+var_140], rax
0x18000154c  mov     rdx, r11
0x18000154f  mov     rax, [rbp+0B0h+arg_28]
0x180001556  mov     [rsp+1B0h+var_150], rax
0x18000155b  mov     rax, [rbp+0B0h+arg_20]
0x180001562  mov     [rsp+1B0h+var_160], rax
0x180001567  lea     rax, [rsp+1B0h+var_180]
0x18000156c  mov     [rbp+0B0h+var_130], rcx
0x180001570  mov     rcx, r10
0x180001573  mov     [rbp+0B0h+var_128], r8d
0x180001577  mov     r8, rbx
0x18000157a  mov     [rsp+1B0h+var_188], rax
0x18000157f  mov     [rsp+1B0h+var_190], 15h
0x180001587  mov     [rbp+0B0h+var_124], edi
0x18000158a  mov     [rsp+1B0h+var_138], 4
0x180001593  mov     [rsp+1B0h+var_148], 8
0x18000159c  mov     [rsp+1B0h+var_158], 8
0x1800015a5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800015aa  mov     rcx, [rbp+0B0h+var_30]
0x1800015b1  xor     rcx, rsp; StackCookie
0x1800015b4  call    __security_check_cookie
0x1800015b9  add     rsp, 190h
0x1800015c0  pop     r14
0x1800015c2  pop     rdi
0x1800015c3  pop     rsi
0x1800015c4  pop     rbx
0x1800015c5  pop     rbp
0x1800015c6  retn
```
