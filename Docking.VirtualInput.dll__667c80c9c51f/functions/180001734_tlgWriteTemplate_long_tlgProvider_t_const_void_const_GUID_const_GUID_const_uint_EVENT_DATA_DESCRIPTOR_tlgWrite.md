# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001734`
- end: `0x180001a2e`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `762`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009fc8`
- `0x18000f350`

## callees

- `0x180001734`
- `0x180001c98`
- `0x1800036a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        __int64 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        __int64 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        __int64 **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  const unsigned __int16 *v27; // rcx
  int v28; // r8d
  __int64 v29; // rax
  int v30; // eax
  int v31; // r9d
  __int64 *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  __int64 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  __int64 *v47; // rcx
  __int64 v48; // rax
  const unsigned __int16 *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  const unsigned __int16 *v52; // rcx
  struct _EVENT_DATA_DESCRIPTOR v54; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v59; // [rsp+70h] [rbp-90h]
  int v60; // [rsp+78h] [rbp-88h]
  int v61; // [rsp+7Ch] [rbp-84h]
  __int64 v62; // [rsp+80h] [rbp-80h]
  __int64 v63; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v64; // [rsp+90h] [rbp-70h]
  int v65; // [rsp+98h] [rbp-68h]
  int v66; // [rsp+9Ch] [rbp-64h]
  __int64 v67; // [rsp+A0h] [rbp-60h]
  __int64 v68; // [rsp+A8h] [rbp-58h]
  __int64 *v69; // [rsp+B0h] [rbp-50h]
  int v70; // [rsp+B8h] [rbp-48h]
  int v71; // [rsp+BCh] [rbp-44h]
  __int64 v72; // [rsp+C0h] [rbp-40h]
  __int64 v73; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v74; // [rsp+D0h] [rbp-30h]
  int v75; // [rsp+D8h] [rbp-28h]
  int v76; // [rsp+DCh] [rbp-24h]
  __int64 v77; // [rsp+E0h] [rbp-20h]
  __int64 v78; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v79; // [rsp+F0h] [rbp-10h]
  int v80; // [rsp+F8h] [rbp-8h]
  int v81; // [rsp+FCh] [rbp-4h]
  __int64 *v82; // [rsp+100h] [rbp+0h]
  int v83; // [rsp+108h] [rbp+8h]
  int v84; // [rsp+10Ch] [rbp+Ch]
  __int64 v85; // [rsp+110h] [rbp+10h]
  __int64 v86; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v87; // [rsp+120h] [rbp+20h]
  int v88; // [rsp+128h] [rbp+28h]
  int v89; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v90; // [rsp+130h] [rbp+30h]
  int v91; // [rsp+138h] [rbp+38h]
  int v92; // [rsp+13Ch] [rbp+3Ch]
  __int64 v93; // [rsp+140h] [rbp+40h]
  __int64 v94; // [rsp+148h] [rbp+48h]
  __int64 v95; // [rsp+150h] [rbp+50h]
  __int64 v96; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v97; // [rsp+160h] [rbp+60h]
  int v98; // [rsp+168h] [rbp+68h]
  int v99; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v27 = *a22;
  v28 = 1;
  if ( *a22 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v27 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v27 = &word_18001EE3A;
    v30 = 1;
  }
  v98 = v30;
  v31 = 2;
  v95 = a21;
  v93 = a20;
  v97 = v27;
  v99 = 0;
  v96 = 4;
  v32 = *a19;
  v94 = 4;
  if ( v32 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &qword_18001F2D0;
    v34 = 2;
  }
  v91 = v34;
  v90 = v32;
  v92 = 0;
  v35 = *a18;
  if ( *a18 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &word_18001EE3A;
    v37 = 1;
  }
  v88 = v37;
  v85 = a17;
  v87 = v35;
  v89 = 0;
  v86 = 4;
  v38 = *a16;
  if ( *a16 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_WORD *)v38 + v39) );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = &qword_18001F2D0;
    v40 = 2;
  }
  v83 = v40;
  v82 = v38;
  v84 = 0;
  v41 = *a15;
  if ( *a15 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &word_18001EE3A;
    v43 = 1;
  }
  v80 = v43;
  v77 = a14;
  v79 = v41;
  v81 = 0;
  v78 = 4;
  v44 = *a13;
  if ( *a13 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &word_18001EE3A;
    v46 = 1;
  }
  v75 = v46;
  v72 = a12;
  v74 = v44;
  v76 = 0;
  v73 = 4;
  v47 = *a11;
  if ( *a11 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_WORD *)v47 + v48) );
    v31 = 2 * v48 + 2;
  }
  else
  {
    v47 = &qword_18001F2D0;
  }
  v67 = a10;
  v69 = v47;
  v70 = v31;
  v71 = 0;
  v49 = *a9;
  v68 = 4;
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
    v49 = &word_18001EE3A;
    v51 = 1;
  }
  v65 = v51;
  v62 = a8;
  v64 = v49;
  v66 = 0;
  v63 = 4;
  v52 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v52 + v24) );
    v28 = v24 + 1;
  }
  else
  {
    v52 = &word_18001EE3A;
  }
  v57 = a6;
  v55 = a5;
  v59 = v52;
  v60 = v28;
  v61 = 0;
  v58 = 4;
  v56 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 0x14u, &v54);
}

```

## disassembly

```asm
0x180001734  push    rbp
0x180001736  push    rbx
0x180001737  push    rsi
0x180001738  push    rdi
0x180001739  push    r12
0x18000173b  push    r14
0x18000173d  lea     rbp, [rsp-88h]
0x180001745  sub     rsp, 188h
0x18000174c  mov     rax, cs:__security_cookie
0x180001753  xor     rax, rsp
0x180001756  mov     [rbp+0B0h+var_40], rax
0x18000175a  mov     rax, [rbp+0B0h+arg_A8]
0x180001761  lea     r14, word_18001EE3A
0x180001768  mov     r11, rdx
0x18000176b  mov     r10, rcx
0x18000176e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001772  xor     esi, esi
0x180001774  mov     rbx, r8
0x180001777  mov     rdi, r9
0x18000177a  mov     rcx, [rax]
0x18000177d  mov     r8d, 1
0x180001783  test    rcx, rcx
0x180001786  jz      short loc_180001798
0x180001788  mov     rax, rdx
0x18000178b  inc     rax
0x18000178e  cmp     [rcx+rax], sil
0x180001792  jnz     short loc_18000178B
0x180001794  inc     eax
0x180001796  jmp     short loc_18000179E
0x180001798  mov     rcx, r14
0x18000179b  mov     eax, r8d
0x18000179e  mov     [rbp+0B0h+var_48], eax
0x1800017a1  mov     r9d, 2
0x1800017a7  mov     rax, [rbp+0B0h+arg_A0]
0x1800017ae  mov     [rbp+0B0h+var_60], rax
0x1800017b2  mov     rax, [rbp+0B0h+arg_98]
0x1800017b9  mov     [rbp+0B0h+var_70], rax
0x1800017bd  mov     rax, [rbp+0B0h+arg_90]
0x1800017c4  mov     [rbp+0B0h+var_50], rcx
0x1800017c8  mov     [rbp+0B0h+var_44], esi
0x1800017cb  mov     [rbp+0B0h+var_58], 4
0x1800017d3  mov     rcx, [rax]
0x1800017d6  mov     [rbp+0B0h+var_68], 4
0x1800017de  test    rcx, rcx
0x1800017e1  jz      short loc_1800017F8
0x1800017e3  mov     rax, rdx
0x1800017e6  inc     rax
0x1800017e9  cmp     [rcx+rax*2], si
0x1800017ed  jnz     short loc_1800017E6
0x1800017ef  lea     eax, ds:2[rax*2]
0x1800017f6  jmp     short loc_180001802
0x1800017f8  lea     rcx, qword_18001F2D0
0x1800017ff  mov     eax, r9d
0x180001802  mov     [rbp+0B0h+var_78], eax
0x180001805  mov     rax, [rbp+0B0h+arg_88]
0x18000180c  mov     [rbp+0B0h+var_80], rcx
0x180001810  mov     [rbp+0B0h+var_74], esi
0x180001813  mov     rcx, [rax]
0x180001816  test    rcx, rcx
0x180001819  jz      short loc_18000182B
0x18000181b  mov     rax, rdx
0x18000181e  inc     rax
0x180001821  cmp     [rcx+rax], sil
0x180001825  jnz     short loc_18000181E
0x180001827  inc     eax
0x180001829  jmp     short loc_180001831
0x18000182b  mov     rcx, r14
0x18000182e  mov     eax, r8d
0x180001831  mov     [rbp+0B0h+var_88], eax
0x180001834  mov     rax, [rbp+0B0h+arg_80]
0x18000183b  mov     [rbp+0B0h+var_A0], rax
0x18000183f  mov     rax, [rbp+0B0h+arg_78]
0x180001846  mov     [rbp+0B0h+var_90], rcx
0x18000184a  mov     [rbp+0B0h+var_84], esi
0x18000184d  mov     [rbp+0B0h+var_98], 4
0x180001855  mov     rcx, [rax]
0x180001858  test    rcx, rcx
0x18000185b  jz      short loc_180001872
0x18000185d  mov     rax, rdx
0x180001860  inc     rax
0x180001863  cmp     [rcx+rax*2], si
0x180001867  jnz     short loc_180001860
0x180001869  lea     eax, ds:2[rax*2]
0x180001870  jmp     short loc_18000187C
0x180001872  lea     rcx, qword_18001F2D0
0x180001879  mov     eax, r9d
0x18000187c  mov     [rbp+0B0h+var_A8], eax
0x18000187f  mov     rax, [rbp+0B0h+arg_70]
0x180001886  mov     [rbp+0B0h+var_B0], rcx
0x18000188a  mov     [rbp+0B0h+var_A4], esi
0x18000188d  mov     rcx, [rax]
0x180001890  test    rcx, rcx
0x180001893  jz      short loc_1800018A5
0x180001895  mov     rax, rdx
0x180001898  inc     rax
0x18000189b  cmp     [rcx+rax], sil
0x18000189f  jnz     short loc_180001898
0x1800018a1  inc     eax
0x1800018a3  jmp     short loc_1800018AB
0x1800018a5  mov     rcx, r14
0x1800018a8  mov     eax, r8d
0x1800018ab  mov     [rbp+0B0h+var_B8], eax
0x1800018ae  mov     rax, [rbp+0B0h+arg_68]
0x1800018b5  mov     [rbp+0B0h+var_D0], rax
0x1800018b9  mov     rax, [rbp+0B0h+arg_60]
0x1800018c0  mov     [rbp+0B0h+var_C0], rcx
0x1800018c4  mov     [rbp+0B0h+var_B4], esi
0x1800018c7  mov     [rbp+0B0h+var_C8], 4
0x1800018cf  mov     rcx, [rax]
0x1800018d2  test    rcx, rcx
0x1800018d5  jz      short loc_1800018E7
0x1800018d7  mov     rax, rdx
0x1800018da  inc     rax
0x1800018dd  cmp     [rcx+rax], sil
0x1800018e1  jnz     short loc_1800018DA
0x1800018e3  inc     eax
0x1800018e5  jmp     short loc_1800018ED
0x1800018e7  mov     rcx, r14
0x1800018ea  mov     eax, r8d
0x1800018ed  mov     [rbp+0B0h+var_D8], eax
0x1800018f0  mov     rax, [rbp+0B0h+arg_58]
0x1800018f7  mov     [rbp+0B0h+var_F0], rax
0x1800018fb  mov     rax, [rbp+0B0h+arg_50]
0x180001902  mov     [rbp+0B0h+var_E0], rcx
0x180001906  mov     [rbp+0B0h+var_D4], esi
0x180001909  mov     [rbp+0B0h+var_E8], 4
0x180001911  mov     rcx, [rax]
0x180001914  test    rcx, rcx
0x180001917  jz      short loc_18000192F
0x180001919  mov     rax, rdx
0x18000191c  inc     rax
0x18000191f  cmp     [rcx+rax*2], si
0x180001923  jnz     short loc_18000191C
0x180001925  lea     r9d, ds:2[rax*2]
0x18000192d  jmp     short loc_180001936
0x18000192f  lea     rcx, qword_18001F2D0
0x180001936  mov     rax, [rbp+0B0h+arg_48]
0x18000193d  mov     [rbp+0B0h+var_110], rax
0x180001941  mov     rax, [rbp+0B0h+arg_40]
0x180001948  mov     [rbp+0B0h+var_100], rcx
0x18000194c  mov     [rbp+0B0h+var_F8], r9d
0x180001950  mov     [rbp+0B0h+var_F4], esi
0x180001953  mov     rcx, [rax]
0x180001956  mov     [rbp+0B0h+var_108], 4
0x18000195e  test    rcx, rcx
0x180001961  jz      short loc_180001973
0x180001963  mov     rax, rdx
0x180001966  inc     rax
0x180001969  cmp     [rcx+rax], sil
0x18000196d  jnz     short loc_180001966
0x18000196f  inc     eax
0x180001971  jmp     short loc_180001979
0x180001973  mov     rcx, r14
0x180001976  mov     eax, r8d
0x180001979  mov     [rbp+0B0h+var_118], eax
0x18000197c  mov     rax, [rbp+0B0h+arg_38]
0x180001983  mov     [rbp+0B0h+var_130], rax
0x180001987  mov     rax, [rbp+0B0h+arg_30]
0x18000198e  mov     [rbp+0B0h+var_120], rcx
0x180001992  mov     [rbp+0B0h+var_114], esi
0x180001995  mov     [rbp+0B0h+var_128], 4
0x18000199d  mov     rcx, [rax]
0x1800019a0  test    rcx, rcx
0x1800019a3  jz      short loc_1800019B4
0x1800019a5  inc     rdx
0x1800019a8  cmp     [rcx+rdx], sil
0x1800019ac  jnz     short loc_1800019A5
0x1800019ae  lea     r8d, [rdx+1]
0x1800019b2  jmp     short loc_1800019B7
0x1800019b4  mov     rcx, r14
0x1800019b7  mov     rax, [rbp+0B0h+arg_28]
0x1800019be  mov     r9, rdi
0x1800019c1  mov     [rsp+1B0h+var_150], rax
0x1800019c6  mov     rdx, r11
0x1800019c9  mov     rax, [rbp+0B0h+arg_20]
0x1800019d0  mov     [rsp+1B0h+var_160], rax
0x1800019d5  lea     rax, [rsp+1B0h+var_180]
0x1800019da  mov     [rsp+1B0h+var_140], rcx
0x1800019df  mov     rcx, r10
0x1800019e2  mov     [rsp+1B0h+var_138], r8d
0x1800019e7  mov     r8, rbx
0x1800019ea  mov     [rsp+1B0h+var_188], rax
0x1800019ef  mov     [rsp+1B0h+var_190], 14h
0x1800019f7  mov     [rsp+1B0h+var_134], esi
0x1800019fb  mov     [rsp+1B0h+var_148], 4
0x180001a04  mov     [rsp+1B0h+var_158], 8
0x180001a0d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001a12  mov     rcx, [rbp+0B0h+var_40]
0x180001a16  xor     rcx, rsp; StackCookie
0x180001a19  call    __security_check_cookie
0x180001a1e  add     rsp, 188h
0x180001a25  pop     r14
0x180001a27  pop     r12
0x180001a29  pop     rdi
0x180001a2a  pop     rsi
0x180001a2b  pop     rbx
0x180001a2c  pop     rbp
0x180001a2d  retn
```
