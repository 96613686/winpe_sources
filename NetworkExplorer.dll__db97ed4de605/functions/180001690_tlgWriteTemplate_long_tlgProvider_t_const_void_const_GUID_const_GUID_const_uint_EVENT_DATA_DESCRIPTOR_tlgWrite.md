# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001690`
- end: `0x180001980`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a820`
- `0x18000b164`

## callees

- `0x180001008`
- `0x180001690`
- `0x18000f0a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        const wchar_t **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const wchar_t **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const wchar_t **a19,
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
  const wchar_t *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const wchar_t *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const wchar_t *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  struct _EVENT_DATA_DESCRIPTOR v53; // [rsp+30h] [rbp-D0h] BYREF
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
  const wchar_t *v68; // [rsp+B0h] [rbp-50h]
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
  const wchar_t *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &word_18001423A;
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
    v31 = &pszFormat;
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
    v34 = &word_18001423A;
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
    v37 = &pszFormat;
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
    v40 = &word_18001423A;
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
    v43 = &word_18001423A;
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
    v46 = &pszFormat;
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
    v48 = &word_18001423A;
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
    v51 = &word_18001423A;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x14u, &v53);
}

```

## disassembly

```asm
0x180001690  push    rbp
0x180001692  push    rbx
0x180001693  push    rsi
0x180001694  push    rdi
0x180001695  push    r15
0x180001697  lea     rbp, [rsp-80h]
0x18000169c  sub     rsp, 180h
0x1800016a3  mov     rax, cs:__security_cookie
0x1800016aa  xor     rax, rsp
0x1800016ad  mov     [rbp+0A0h+var_30], rax
0x1800016b1  mov     rax, [rbp+0A0h+arg_A8]
0x1800016b8  lea     rsi, word_18001423A
0x1800016bf  mov     r11, rdx
0x1800016c2  mov     r10, rcx
0x1800016c5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800016c9  xor     edi, edi
0x1800016cb  mov     rbx, r8
0x1800016ce  mov     r8d, 1
0x1800016d4  mov     rcx, [rax]
0x1800016d7  test    rcx, rcx
0x1800016da  jz      short loc_1800016EC
0x1800016dc  mov     rax, rdx
0x1800016df  inc     rax
0x1800016e2  cmp     [rcx+rax], dil
0x1800016e6  jnz     short loc_1800016DF
0x1800016e8  inc     eax
0x1800016ea  jmp     short loc_1800016F2
0x1800016ec  mov     rcx, rsi
0x1800016ef  mov     eax, r8d
0x1800016f2  mov     [rbp+0A0h+var_38], eax
0x1800016f5  mov     r9d, 2
0x1800016fb  mov     rax, [rbp+0A0h+arg_A0]
0x180001702  mov     [rbp+0A0h+var_50], rax
0x180001706  mov     rax, [rbp+0A0h+arg_98]
0x18000170d  mov     [rbp+0A0h+var_60], rax
0x180001711  mov     rax, [rbp+0A0h+arg_90]
0x180001718  mov     [rbp+0A0h+var_40], rcx
0x18000171c  mov     [rbp+0A0h+var_34], edi
0x18000171f  mov     [rbp+0A0h+var_48], 4
0x180001727  mov     rcx, [rax]
0x18000172a  mov     [rbp+0A0h+var_58], 4
0x180001732  test    rcx, rcx
0x180001735  jz      short loc_18000174C
0x180001737  mov     rax, rdx
0x18000173a  inc     rax
0x18000173d  cmp     [rcx+rax*2], di
0x180001741  jnz     short loc_18000173A
0x180001743  lea     eax, ds:2[rax*2]
0x18000174a  jmp     short loc_180001756
0x18000174c  lea     rcx, pszFormat
0x180001753  mov     eax, r9d
0x180001756  mov     [rbp+0A0h+var_68], eax
0x180001759  mov     rax, [rbp+0A0h+arg_88]
0x180001760  mov     [rbp+0A0h+var_70], rcx
0x180001764  mov     [rbp+0A0h+var_64], edi
0x180001767  mov     rcx, [rax]
0x18000176a  test    rcx, rcx
0x18000176d  jz      short loc_18000177F
0x18000176f  mov     rax, rdx
0x180001772  inc     rax
0x180001775  cmp     [rcx+rax], dil
0x180001779  jnz     short loc_180001772
0x18000177b  inc     eax
0x18000177d  jmp     short loc_180001785
0x18000177f  mov     rcx, rsi
0x180001782  mov     eax, r8d
0x180001785  mov     [rbp+0A0h+var_78], eax
0x180001788  mov     rax, [rbp+0A0h+arg_80]
0x18000178f  mov     [rbp+0A0h+var_90], rax
0x180001793  mov     rax, [rbp+0A0h+arg_78]
0x18000179a  mov     [rbp+0A0h+var_80], rcx
0x18000179e  mov     [rbp+0A0h+var_74], edi
0x1800017a1  mov     [rbp+0A0h+var_88], 4
0x1800017a9  mov     rcx, [rax]
0x1800017ac  test    rcx, rcx
0x1800017af  jz      short loc_1800017C6
0x1800017b1  mov     rax, rdx
0x1800017b4  inc     rax
0x1800017b7  cmp     [rcx+rax*2], di
0x1800017bb  jnz     short loc_1800017B4
0x1800017bd  lea     eax, ds:2[rax*2]
0x1800017c4  jmp     short loc_1800017D0
0x1800017c6  lea     rcx, pszFormat
0x1800017cd  mov     eax, r9d
0x1800017d0  mov     [rbp+0A0h+var_98], eax
0x1800017d3  mov     rax, [rbp+0A0h+arg_70]
0x1800017da  mov     [rbp+0A0h+var_A0], rcx
0x1800017de  mov     [rbp+0A0h+var_94], edi
0x1800017e1  mov     rcx, [rax]
0x1800017e4  test    rcx, rcx
0x1800017e7  jz      short loc_1800017F9
0x1800017e9  mov     rax, rdx
0x1800017ec  inc     rax
0x1800017ef  cmp     [rcx+rax], dil
0x1800017f3  jnz     short loc_1800017EC
0x1800017f5  inc     eax
0x1800017f7  jmp     short loc_1800017FF
0x1800017f9  mov     rcx, rsi
0x1800017fc  mov     eax, r8d
0x1800017ff  mov     [rbp+0A0h+var_A8], eax
0x180001802  mov     rax, [rbp+0A0h+arg_68]
0x180001809  mov     [rbp+0A0h+var_C0], rax
0x18000180d  mov     rax, [rbp+0A0h+arg_60]
0x180001814  mov     [rbp+0A0h+var_B0], rcx
0x180001818  mov     [rbp+0A0h+var_A4], edi
0x18000181b  mov     [rbp+0A0h+var_B8], 4
0x180001823  mov     rcx, [rax]
0x180001826  test    rcx, rcx
0x180001829  jz      short loc_18000183B
0x18000182b  mov     rax, rdx
0x18000182e  inc     rax
0x180001831  cmp     [rcx+rax], dil
0x180001835  jnz     short loc_18000182E
0x180001837  inc     eax
0x180001839  jmp     short loc_180001841
0x18000183b  mov     rcx, rsi
0x18000183e  mov     eax, r8d
0x180001841  mov     [rbp+0A0h+var_C8], eax
0x180001844  mov     rax, [rbp+0A0h+arg_58]
0x18000184b  mov     [rbp+0A0h+var_E0], rax
0x18000184f  mov     rax, [rbp+0A0h+arg_50]
0x180001856  mov     [rbp+0A0h+var_D0], rcx
0x18000185a  mov     [rbp+0A0h+var_C4], edi
0x18000185d  mov     [rbp+0A0h+var_D8], 4
0x180001865  mov     rcx, [rax]
0x180001868  test    rcx, rcx
0x18000186b  jz      short loc_180001883
0x18000186d  mov     rax, rdx
0x180001870  inc     rax
0x180001873  cmp     [rcx+rax*2], di
0x180001877  jnz     short loc_180001870
0x180001879  lea     r9d, ds:2[rax*2]
0x180001881  jmp     short loc_18000188A
0x180001883  lea     rcx, pszFormat
0x18000188a  mov     rax, [rbp+0A0h+arg_48]
0x180001891  mov     [rbp+0A0h+var_100], rax
0x180001895  mov     rax, [rbp+0A0h+arg_40]
0x18000189c  mov     [rbp+0A0h+var_F0], rcx
0x1800018a0  mov     [rbp+0A0h+var_E8], r9d
0x1800018a4  mov     [rbp+0A0h+var_E4], edi
0x1800018a7  mov     rcx, [rax]
0x1800018aa  mov     [rbp+0A0h+var_F8], 4
0x1800018b2  test    rcx, rcx
0x1800018b5  jz      short loc_1800018C7
0x1800018b7  mov     rax, rdx
0x1800018ba  inc     rax
0x1800018bd  cmp     [rcx+rax], dil
0x1800018c1  jnz     short loc_1800018BA
0x1800018c3  inc     eax
0x1800018c5  jmp     short loc_1800018CD
0x1800018c7  mov     rcx, rsi
0x1800018ca  mov     eax, r8d
0x1800018cd  mov     [rbp+0A0h+var_108], eax
0x1800018d0  mov     rax, [rbp+0A0h+arg_38]
0x1800018d7  mov     [rbp+0A0h+var_120], rax
0x1800018db  mov     rax, [rbp+0A0h+arg_30]
0x1800018e2  mov     [rbp+0A0h+var_110], rcx
0x1800018e6  mov     [rbp+0A0h+var_104], edi
0x1800018e9  mov     [rbp+0A0h+var_118], 4
0x1800018f1  mov     rcx, [rax]
0x1800018f4  test    rcx, rcx
0x1800018f7  jz      short loc_180001908
0x1800018f9  inc     rdx
0x1800018fc  cmp     [rcx+rdx], dil
0x180001900  jnz     short loc_1800018F9
0x180001902  lea     r8d, [rdx+1]
0x180001906  jmp     short loc_18000190B
0x180001908  mov     rcx, rsi
0x18000190b  mov     rax, [rbp+0A0h+arg_28]
0x180001912  xor     r9d, r9d
0x180001915  mov     [rsp+1A0h+var_140], rax
0x18000191a  mov     rdx, r11
0x18000191d  mov     rax, [rbp+0A0h+arg_20]
0x180001924  mov     [rsp+1A0h+var_150], rax
0x180001929  lea     rax, [rsp+1A0h+var_170]
0x18000192e  mov     [rsp+1A0h+var_130], rcx
0x180001933  mov     rcx, r10
0x180001936  mov     [rsp+1A0h+var_128], r8d
0x18000193b  mov     r8, rbx
0x18000193e  mov     [rsp+1A0h+var_178], rax
0x180001943  mov     [rsp+1A0h+var_180], 14h
0x18000194b  mov     [rsp+1A0h+var_124], edi
0x18000194f  mov     [rsp+1A0h+var_138], 4
0x180001958  mov     [rsp+1A0h+var_148], 8
0x180001961  call    _tlgWriteTransfer_EventWriteTransfer
0x180001966  mov     rcx, [rbp+0A0h+var_30]
0x18000196a  xor     rcx, rsp; StackCookie
0x18000196d  call    __security_check_cookie
0x180001972  add     rsp, 180h
0x180001979  pop     r15
0x18000197b  pop     rdi
0x18000197c  pop     rsi
0x18000197d  pop     rbx
0x18000197e  pop     rbp
0x18000197f  retn
```
