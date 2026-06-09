# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800016dc`
- end: `0x1800019e7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `779`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, char **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, char **, __int64, const unsigned __int16 **, char **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b5c0`

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x180002550`

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
        char **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        char **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        char **a20,
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
  char *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  char *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  char *v47; // rcx
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
  char *v71; // [rsp+C0h] [rbp-40h]
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
  char *v84; // [rsp+110h] [rbp+10h]
  int v85; // [rsp+118h] [rbp+18h]
  int v86; // [rsp+11Ch] [rbp+1Ch]
  __int64 v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  char *v92; // [rsp+140h] [rbp+40h]
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
    v28 = &word_1800159FE;
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
    while ( *(_WORD *)&v32[2 * v33] );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = byte_1800159FC;
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
    v35 = &word_1800159FE;
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
    while ( *(_WORD *)&v38[2 * v39] );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = byte_1800159FC;
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
    v41 = &word_1800159FE;
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
    v44 = &word_1800159FE;
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
    while ( *(_WORD *)&v47[2 * v48] );
    v31 = 2 * v48 + 2;
  }
  else
  {
    v47 = byte_1800159FC;
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
    v49 = &word_1800159FE;
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
    v52 = &word_1800159FE;
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
0x1800016dc  push    rbp
0x1800016de  push    rbx
0x1800016df  push    rsi
0x1800016e0  push    rdi
0x1800016e1  push    r14
0x1800016e3  lea     rbp, [rsp-90h]
0x1800016eb  sub     rsp, 190h
0x1800016f2  mov     rax, cs:__security_cookie
0x1800016f9  xor     rax, rsp
0x1800016fc  mov     [rbp+0B0h+var_30], rax
0x180001703  mov     rax, [rbp+0B0h+arg_B0]
0x18000170a  lea     rsi, word_1800159FE
0x180001711  mov     r11, rdx
0x180001714  mov     r10, rcx
0x180001717  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000171b  xor     edi, edi
0x18000171d  mov     rbx, r8
0x180001720  mov     r8d, 1
0x180001726  mov     rcx, [rax]
0x180001729  test    rcx, rcx
0x18000172c  jz      short loc_18000173E
0x18000172e  mov     rax, rdx
0x180001731  inc     rax
0x180001734  cmp     [rcx+rax], dil
0x180001738  jnz     short loc_180001731
0x18000173a  inc     eax
0x18000173c  jmp     short loc_180001744
0x18000173e  mov     rcx, rsi
0x180001741  mov     eax, r8d
0x180001744  mov     [rbp+0B0h+var_38], eax
0x180001747  mov     r9d, 2
0x18000174d  mov     rax, [rbp+0B0h+arg_A8]
0x180001754  mov     [rbp+0B0h+var_50], rax
0x180001758  mov     rax, [rbp+0B0h+arg_A0]
0x18000175f  mov     [rbp+0B0h+var_60], rax
0x180001763  mov     rax, [rbp+0B0h+arg_98]
0x18000176a  mov     [rbp+0B0h+var_40], rcx
0x18000176e  mov     [rbp+0B0h+var_34], edi
0x180001771  mov     [rbp+0B0h+var_48], 4
0x180001779  mov     rcx, [rax]
0x18000177c  mov     [rbp+0B0h+var_58], 4
0x180001784  test    rcx, rcx
0x180001787  jz      short loc_18000179E
0x180001789  mov     rax, rdx
0x18000178c  inc     rax
0x18000178f  cmp     [rcx+rax*2], di
0x180001793  jnz     short loc_18000178C
0x180001795  lea     eax, ds:2[rax*2]
0x18000179c  jmp     short loc_1800017A8
0x18000179e  lea     rcx, byte_1800159FC
0x1800017a5  mov     eax, r9d
0x1800017a8  mov     [rbp+0B0h+var_68], eax
0x1800017ab  mov     rax, [rbp+0B0h+arg_90]
0x1800017b2  mov     [rbp+0B0h+var_70], rcx
0x1800017b6  mov     [rbp+0B0h+var_64], edi
0x1800017b9  mov     rcx, [rax]
0x1800017bc  test    rcx, rcx
0x1800017bf  jz      short loc_1800017D1
0x1800017c1  mov     rax, rdx
0x1800017c4  inc     rax
0x1800017c7  cmp     [rcx+rax], dil
0x1800017cb  jnz     short loc_1800017C4
0x1800017cd  inc     eax
0x1800017cf  jmp     short loc_1800017D7
0x1800017d1  mov     rcx, rsi
0x1800017d4  mov     eax, r8d
0x1800017d7  mov     [rbp+0B0h+var_78], eax
0x1800017da  mov     rax, [rbp+0B0h+arg_88]
0x1800017e1  mov     [rbp+0B0h+var_90], rax
0x1800017e5  mov     rax, [rbp+0B0h+arg_80]
0x1800017ec  mov     [rbp+0B0h+var_80], rcx
0x1800017f0  mov     [rbp+0B0h+var_74], edi
0x1800017f3  mov     [rbp+0B0h+var_88], 4
0x1800017fb  mov     rcx, [rax]
0x1800017fe  test    rcx, rcx
0x180001801  jz      short loc_180001818
0x180001803  mov     rax, rdx
0x180001806  inc     rax
0x180001809  cmp     [rcx+rax*2], di
0x18000180d  jnz     short loc_180001806
0x18000180f  lea     eax, ds:2[rax*2]
0x180001816  jmp     short loc_180001822
0x180001818  lea     rcx, byte_1800159FC
0x18000181f  mov     eax, r9d
0x180001822  mov     [rbp+0B0h+var_98], eax
0x180001825  mov     rax, [rbp+0B0h+arg_78]
0x18000182c  mov     [rbp+0B0h+var_A0], rcx
0x180001830  mov     [rbp+0B0h+var_94], edi
0x180001833  mov     rcx, [rax]
0x180001836  test    rcx, rcx
0x180001839  jz      short loc_18000184B
0x18000183b  mov     rax, rdx
0x18000183e  inc     rax
0x180001841  cmp     [rcx+rax], dil
0x180001845  jnz     short loc_18000183E
0x180001847  inc     eax
0x180001849  jmp     short loc_180001851
0x18000184b  mov     rcx, rsi
0x18000184e  mov     eax, r8d
0x180001851  mov     [rbp+0B0h+var_A8], eax
0x180001854  mov     rax, [rbp+0B0h+arg_70]
0x18000185b  mov     [rbp+0B0h+var_C0], rax
0x18000185f  mov     rax, [rbp+0B0h+arg_68]
0x180001866  mov     [rbp+0B0h+var_B0], rcx
0x18000186a  mov     [rbp+0B0h+var_A4], edi
0x18000186d  mov     [rbp+0B0h+var_B8], 4
0x180001875  mov     rcx, [rax]
0x180001878  test    rcx, rcx
0x18000187b  jz      short loc_18000188D
0x18000187d  mov     rax, rdx
0x180001880  inc     rax
0x180001883  cmp     [rcx+rax], dil
0x180001887  jnz     short loc_180001880
0x180001889  inc     eax
0x18000188b  jmp     short loc_180001893
0x18000188d  mov     rcx, rsi
0x180001890  mov     eax, r8d
0x180001893  mov     [rbp+0B0h+var_C8], eax
0x180001896  mov     rax, [rbp+0B0h+arg_60]
0x18000189d  mov     [rbp+0B0h+var_E0], rax
0x1800018a1  mov     rax, [rbp+0B0h+arg_58]
0x1800018a8  mov     [rbp+0B0h+var_D0], rcx
0x1800018ac  mov     [rbp+0B0h+var_C4], edi
0x1800018af  mov     [rbp+0B0h+var_D8], 4
0x1800018b7  mov     rcx, [rax]
0x1800018ba  test    rcx, rcx
0x1800018bd  jz      short loc_1800018D5
0x1800018bf  mov     rax, rdx
0x1800018c2  inc     rax
0x1800018c5  cmp     [rcx+rax*2], di
0x1800018c9  jnz     short loc_1800018C2
0x1800018cb  lea     r9d, ds:2[rax*2]
0x1800018d3  jmp     short loc_1800018DC
0x1800018d5  lea     rcx, byte_1800159FC
0x1800018dc  mov     rax, [rbp+0B0h+arg_50]
0x1800018e3  mov     [rbp+0B0h+var_100], rax
0x1800018e7  mov     rax, [rbp+0B0h+arg_48]
0x1800018ee  mov     [rbp+0B0h+var_F0], rcx
0x1800018f2  mov     [rbp+0B0h+var_E8], r9d
0x1800018f6  mov     [rbp+0B0h+var_E4], edi
0x1800018f9  mov     rcx, [rax]
0x1800018fc  mov     [rbp+0B0h+var_F8], 4
0x180001904  test    rcx, rcx
0x180001907  jz      short loc_180001919
0x180001909  mov     rax, rdx
0x18000190c  inc     rax
0x18000190f  cmp     [rcx+rax], dil
0x180001913  jnz     short loc_18000190C
0x180001915  inc     eax
0x180001917  jmp     short loc_18000191F
0x180001919  mov     rcx, rsi
0x18000191c  mov     eax, r8d
0x18000191f  mov     [rbp+0B0h+var_108], eax
0x180001922  mov     rax, [rbp+0B0h+arg_40]
0x180001929  mov     [rbp+0B0h+var_120], rax
0x18000192d  mov     rax, [rbp+0B0h+arg_38]
0x180001934  mov     [rbp+0B0h+var_110], rcx
0x180001938  mov     [rbp+0B0h+var_104], edi
0x18000193b  mov     [rbp+0B0h+var_118], 4
0x180001943  mov     rcx, [rax]
0x180001946  test    rcx, rcx
0x180001949  jz      short loc_18000195A
0x18000194b  inc     rdx
0x18000194e  cmp     [rcx+rdx], dil
0x180001952  jnz     short loc_18000194B
0x180001954  lea     r8d, [rdx+1]
0x180001958  jmp     short loc_18000195D
0x18000195a  mov     rcx, rsi
0x18000195d  mov     rax, [rbp+0B0h+arg_30]
0x180001964  xor     r9d, r9d
0x180001967  mov     [rsp+1B0h+var_140], rax
0x18000196c  mov     rdx, r11
0x18000196f  mov     rax, [rbp+0B0h+arg_28]
0x180001976  mov     [rsp+1B0h+var_150], rax
0x18000197b  mov     rax, [rbp+0B0h+arg_20]
0x180001982  mov     [rsp+1B0h+var_160], rax
0x180001987  lea     rax, [rsp+1B0h+var_180]
0x18000198c  mov     [rbp+0B0h+var_130], rcx
0x180001990  mov     rcx, r10
0x180001993  mov     [rbp+0B0h+var_128], r8d
0x180001997  mov     r8, rbx
0x18000199a  mov     [rsp+1B0h+var_188], rax
0x18000199f  mov     [rsp+1B0h+var_190], 15h
0x1800019a7  mov     [rbp+0B0h+var_124], edi
0x1800019aa  mov     [rsp+1B0h+var_138], 4
0x1800019b3  mov     [rsp+1B0h+var_148], 8
0x1800019bc  mov     [rsp+1B0h+var_158], 8
0x1800019c5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800019ca  mov     rcx, [rbp+0B0h+var_30]
0x1800019d1  xor     rcx, rsp; StackCookie
0x1800019d4  call    __security_check_cookie
0x1800019d9  add     rsp, 190h
0x1800019e0  pop     r14
0x1800019e2  pop     rdi
0x1800019e3  pop     rsi
0x1800019e4  pop     rbx
0x1800019e5  pop     rbp
0x1800019e6  retn
```
