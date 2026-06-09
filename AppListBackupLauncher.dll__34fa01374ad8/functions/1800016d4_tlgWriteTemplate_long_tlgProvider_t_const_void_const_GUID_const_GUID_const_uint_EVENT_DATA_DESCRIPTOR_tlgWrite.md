# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800016d4`
- end: `0x1800019c4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800097b0`
- `0x18000b96c`

## callees

- `0x1800016d4`
- `0x180001a4c`
- `0x180002300`

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
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19,
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
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  int *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  int *v46; // rcx
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
  int *v68; // [rsp+B0h] [rbp-50h]
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
  int *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  int *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &byte_180013CC8;
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
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_180013CCC;
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
    v34 = &byte_180013CC8;
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
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &dword_180013CCC;
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
    v40 = &byte_180013CC8;
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
    v43 = &byte_180013CC8;
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
    while ( *((_WORD *)v46 + v47) );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &dword_180013CCC;
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
    v48 = &byte_180013CC8;
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
    v51 = &byte_180013CC8;
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
0x1800016d4  push    rbp
0x1800016d6  push    rbx
0x1800016d7  push    rsi
0x1800016d8  push    rdi
0x1800016d9  push    r15
0x1800016db  lea     rbp, [rsp-80h]
0x1800016e0  sub     rsp, 180h
0x1800016e7  mov     rax, cs:__security_cookie
0x1800016ee  xor     rax, rsp
0x1800016f1  mov     [rbp+0A0h+var_30], rax
0x1800016f5  mov     rax, [rbp+0A0h+arg_A8]
0x1800016fc  lea     rsi, byte_180013CC8
0x180001703  mov     r11, rdx
0x180001706  mov     r10, rcx
0x180001709  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000170d  xor     edi, edi
0x18000170f  mov     rbx, r8
0x180001712  mov     r8d, 1
0x180001718  mov     rcx, [rax]
0x18000171b  test    rcx, rcx
0x18000171e  jz      short loc_180001730
0x180001720  mov     rax, rdx
0x180001723  inc     rax
0x180001726  cmp     [rcx+rax], dil
0x18000172a  jnz     short loc_180001723
0x18000172c  inc     eax
0x18000172e  jmp     short loc_180001736
0x180001730  mov     rcx, rsi
0x180001733  mov     eax, r8d
0x180001736  mov     [rbp+0A0h+var_38], eax
0x180001739  mov     r9d, 2
0x18000173f  mov     rax, [rbp+0A0h+arg_A0]
0x180001746  mov     [rbp+0A0h+var_50], rax
0x18000174a  mov     rax, [rbp+0A0h+arg_98]
0x180001751  mov     [rbp+0A0h+var_60], rax
0x180001755  mov     rax, [rbp+0A0h+arg_90]
0x18000175c  mov     [rbp+0A0h+var_40], rcx
0x180001760  mov     [rbp+0A0h+var_34], edi
0x180001763  mov     [rbp+0A0h+var_48], 4
0x18000176b  mov     rcx, [rax]
0x18000176e  mov     [rbp+0A0h+var_58], 4
0x180001776  test    rcx, rcx
0x180001779  jz      short loc_180001790
0x18000177b  mov     rax, rdx
0x18000177e  inc     rax
0x180001781  cmp     [rcx+rax*2], di
0x180001785  jnz     short loc_18000177E
0x180001787  lea     eax, ds:2[rax*2]
0x18000178e  jmp     short loc_18000179A
0x180001790  lea     rcx, dword_180013CCC
0x180001797  mov     eax, r9d
0x18000179a  mov     [rbp+0A0h+var_68], eax
0x18000179d  mov     rax, [rbp+0A0h+arg_88]
0x1800017a4  mov     [rbp+0A0h+var_70], rcx
0x1800017a8  mov     [rbp+0A0h+var_64], edi
0x1800017ab  mov     rcx, [rax]
0x1800017ae  test    rcx, rcx
0x1800017b1  jz      short loc_1800017C3
0x1800017b3  mov     rax, rdx
0x1800017b6  inc     rax
0x1800017b9  cmp     [rcx+rax], dil
0x1800017bd  jnz     short loc_1800017B6
0x1800017bf  inc     eax
0x1800017c1  jmp     short loc_1800017C9
0x1800017c3  mov     rcx, rsi
0x1800017c6  mov     eax, r8d
0x1800017c9  mov     [rbp+0A0h+var_78], eax
0x1800017cc  mov     rax, [rbp+0A0h+arg_80]
0x1800017d3  mov     [rbp+0A0h+var_90], rax
0x1800017d7  mov     rax, [rbp+0A0h+arg_78]
0x1800017de  mov     [rbp+0A0h+var_80], rcx
0x1800017e2  mov     [rbp+0A0h+var_74], edi
0x1800017e5  mov     [rbp+0A0h+var_88], 4
0x1800017ed  mov     rcx, [rax]
0x1800017f0  test    rcx, rcx
0x1800017f3  jz      short loc_18000180A
0x1800017f5  mov     rax, rdx
0x1800017f8  inc     rax
0x1800017fb  cmp     [rcx+rax*2], di
0x1800017ff  jnz     short loc_1800017F8
0x180001801  lea     eax, ds:2[rax*2]
0x180001808  jmp     short loc_180001814
0x18000180a  lea     rcx, dword_180013CCC
0x180001811  mov     eax, r9d
0x180001814  mov     [rbp+0A0h+var_98], eax
0x180001817  mov     rax, [rbp+0A0h+arg_70]
0x18000181e  mov     [rbp+0A0h+var_A0], rcx
0x180001822  mov     [rbp+0A0h+var_94], edi
0x180001825  mov     rcx, [rax]
0x180001828  test    rcx, rcx
0x18000182b  jz      short loc_18000183D
0x18000182d  mov     rax, rdx
0x180001830  inc     rax
0x180001833  cmp     [rcx+rax], dil
0x180001837  jnz     short loc_180001830
0x180001839  inc     eax
0x18000183b  jmp     short loc_180001843
0x18000183d  mov     rcx, rsi
0x180001840  mov     eax, r8d
0x180001843  mov     [rbp+0A0h+var_A8], eax
0x180001846  mov     rax, [rbp+0A0h+arg_68]
0x18000184d  mov     [rbp+0A0h+var_C0], rax
0x180001851  mov     rax, [rbp+0A0h+arg_60]
0x180001858  mov     [rbp+0A0h+var_B0], rcx
0x18000185c  mov     [rbp+0A0h+var_A4], edi
0x18000185f  mov     [rbp+0A0h+var_B8], 4
0x180001867  mov     rcx, [rax]
0x18000186a  test    rcx, rcx
0x18000186d  jz      short loc_18000187F
0x18000186f  mov     rax, rdx
0x180001872  inc     rax
0x180001875  cmp     [rcx+rax], dil
0x180001879  jnz     short loc_180001872
0x18000187b  inc     eax
0x18000187d  jmp     short loc_180001885
0x18000187f  mov     rcx, rsi
0x180001882  mov     eax, r8d
0x180001885  mov     [rbp+0A0h+var_C8], eax
0x180001888  mov     rax, [rbp+0A0h+arg_58]
0x18000188f  mov     [rbp+0A0h+var_E0], rax
0x180001893  mov     rax, [rbp+0A0h+arg_50]
0x18000189a  mov     [rbp+0A0h+var_D0], rcx
0x18000189e  mov     [rbp+0A0h+var_C4], edi
0x1800018a1  mov     [rbp+0A0h+var_D8], 4
0x1800018a9  mov     rcx, [rax]
0x1800018ac  test    rcx, rcx
0x1800018af  jz      short loc_1800018C7
0x1800018b1  mov     rax, rdx
0x1800018b4  inc     rax
0x1800018b7  cmp     [rcx+rax*2], di
0x1800018bb  jnz     short loc_1800018B4
0x1800018bd  lea     r9d, ds:2[rax*2]
0x1800018c5  jmp     short loc_1800018CE
0x1800018c7  lea     rcx, dword_180013CCC
0x1800018ce  mov     rax, [rbp+0A0h+arg_48]
0x1800018d5  mov     [rbp+0A0h+var_100], rax
0x1800018d9  mov     rax, [rbp+0A0h+arg_40]
0x1800018e0  mov     [rbp+0A0h+var_F0], rcx
0x1800018e4  mov     [rbp+0A0h+var_E8], r9d
0x1800018e8  mov     [rbp+0A0h+var_E4], edi
0x1800018eb  mov     rcx, [rax]
0x1800018ee  mov     [rbp+0A0h+var_F8], 4
0x1800018f6  test    rcx, rcx
0x1800018f9  jz      short loc_18000190B
0x1800018fb  mov     rax, rdx
0x1800018fe  inc     rax
0x180001901  cmp     [rcx+rax], dil
0x180001905  jnz     short loc_1800018FE
0x180001907  inc     eax
0x180001909  jmp     short loc_180001911
0x18000190b  mov     rcx, rsi
0x18000190e  mov     eax, r8d
0x180001911  mov     [rbp+0A0h+var_108], eax
0x180001914  mov     rax, [rbp+0A0h+arg_38]
0x18000191b  mov     [rbp+0A0h+var_120], rax
0x18000191f  mov     rax, [rbp+0A0h+arg_30]
0x180001926  mov     [rbp+0A0h+var_110], rcx
0x18000192a  mov     [rbp+0A0h+var_104], edi
0x18000192d  mov     [rbp+0A0h+var_118], 4
0x180001935  mov     rcx, [rax]
0x180001938  test    rcx, rcx
0x18000193b  jz      short loc_18000194C
0x18000193d  inc     rdx
0x180001940  cmp     [rcx+rdx], dil
0x180001944  jnz     short loc_18000193D
0x180001946  lea     r8d, [rdx+1]
0x18000194a  jmp     short loc_18000194F
0x18000194c  mov     rcx, rsi
0x18000194f  mov     rax, [rbp+0A0h+arg_28]
0x180001956  xor     r9d, r9d
0x180001959  mov     [rsp+1A0h+var_140], rax
0x18000195e  mov     rdx, r11
0x180001961  mov     rax, [rbp+0A0h+arg_20]
0x180001968  mov     [rsp+1A0h+var_150], rax
0x18000196d  lea     rax, [rsp+1A0h+var_170]
0x180001972  mov     [rsp+1A0h+var_130], rcx
0x180001977  mov     rcx, r10
0x18000197a  mov     [rsp+1A0h+var_128], r8d
0x18000197f  mov     r8, rbx
0x180001982  mov     [rsp+1A0h+var_178], rax
0x180001987  mov     [rsp+1A0h+var_180], 14h
0x18000198f  mov     [rsp+1A0h+var_124], edi
0x180001993  mov     [rsp+1A0h+var_138], 4
0x18000199c  mov     [rsp+1A0h+var_148], 8
0x1800019a5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800019aa  mov     rcx, [rbp+0A0h+var_30]
0x1800019ae  xor     rcx, rsp; StackCookie
0x1800019b1  call    __security_check_cookie
0x1800019b6  add     rsp, 180h
0x1800019bd  pop     r15
0x1800019bf  pop     rdi
0x1800019c0  pop     rsi
0x1800019c1  pop     rbx
0x1800019c2  pop     rbp
0x1800019c3  retn
```
