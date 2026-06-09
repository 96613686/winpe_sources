# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001750`
- end: `0x140001a3f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, __int64 **, __int64, const wchar_t **, __int64, const wchar_t **, __int64 **, __int64, const wchar_t **, __int64 **, __int64, __int64, const wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140024a8c`

## callees

- `0x140001750`
- `0x140001c88`
- `0x140002310`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const wchar_t **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        __int64 **a11,
        __int64 a12,
        const wchar_t **a13,
        __int64 a14,
        const wchar_t **a15,
        __int64 **a16,
        __int64 a17,
        const wchar_t **a18,
        __int64 **a19,
        __int64 a20,
        __int64 a21,
        const wchar_t **a22)
{
  __int64 v24; // rdx
  int v25; // r8d
  const wchar_t *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const wchar_t *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const wchar_t *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const wchar_t *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  __int64 *v45; // rcx
  __int64 v46; // rax
  const wchar_t *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const wchar_t *v50; // rcx
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const wchar_t *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const wchar_t *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  __int64 *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const wchar_t *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const wchar_t *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  __int64 *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const wchar_t *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const wchar_t *v95; // [rsp+160h] [rbp+60h]
  int v96; // [rsp+168h] [rbp+68h]
  int v97; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v25 = 1;
  v26 = *a22;
  if ( *a22 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &qword_14002E968;
    v28 = 1;
  }
  v96 = v28;
  v29 = 2;
  v93 = a21;
  v91 = a20;
  v95 = v26;
  v97 = 0;
  v94 = 4;
  v30 = *a19;
  v92 = 4;
  if ( v30 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &qword_1400320D8;
    v32 = 2;
  }
  v89 = v32;
  v88 = v30;
  v90 = 0;
  v33 = *a18;
  if ( *a18 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &qword_14002E968;
    v35 = 1;
  }
  v86 = v35;
  v83 = a17;
  v85 = v33;
  v87 = 0;
  v84 = 4;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &qword_1400320D8;
    v38 = 2;
  }
  v81 = v38;
  v80 = v36;
  v82 = 0;
  v39 = *a15;
  if ( *a15 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &qword_14002E968;
    v41 = 1;
  }
  v78 = v41;
  v75 = a14;
  v77 = v39;
  v79 = 0;
  v76 = 4;
  v42 = *a13;
  if ( *a13 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &qword_14002E968;
    v44 = 1;
  }
  v73 = v44;
  v70 = a12;
  v72 = v42;
  v74 = 0;
  v71 = 4;
  v45 = *a11;
  if ( *a11 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_WORD *)v45 + v46) );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = &qword_1400320D8;
  }
  v65 = a10;
  v67 = v45;
  v68 = v29;
  v69 = 0;
  v47 = *a9;
  v66 = 4;
  if ( v47 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &qword_14002E968;
    v49 = 1;
  }
  v63 = v49;
  v60 = a8;
  v62 = v47;
  v64 = 0;
  v61 = 4;
  v50 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v50 + v24) );
    v25 = v24 + 1;
  }
  else
  {
    v50 = &qword_14002E968;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x14u, &v52);
}

```

## disassembly

```asm
0x140001750  mov     [rsp-8+arg_10], rbx
0x140001755  push    rbp
0x140001756  push    rdi
0x140001757  push    r14
0x140001759  lea     rbp, [rsp-80h]
0x14000175e  sub     rsp, 180h
0x140001765  mov     rax, cs:__security_cookie
0x14000176c  xor     rax, rsp
0x14000176f  mov     [rbp+90h+var_20], rax
0x140001773  mov     rax, [rbp+90h+arg_A8]
0x14000177a  lea     rdi, qword_14002E968
0x140001781  mov     r11, rdx
0x140001784  mov     r10, rcx
0x140001787  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000178b  xor     ebx, ebx
0x14000178d  mov     r8d, 1
0x140001793  mov     rcx, [rax]
0x140001796  test    rcx, rcx
0x140001799  jz      short loc_1400017AA
0x14000179b  mov     rax, rdx
0x14000179e  inc     rax
0x1400017a1  cmp     [rcx+rax], bl
0x1400017a4  jnz     short loc_14000179E
0x1400017a6  inc     eax
0x1400017a8  jmp     short loc_1400017B0
0x1400017aa  mov     rcx, rdi
0x1400017ad  mov     eax, r8d
0x1400017b0  mov     [rbp+90h+var_28], eax
0x1400017b3  mov     r9d, 2
0x1400017b9  mov     rax, [rbp+90h+arg_A0]
0x1400017c0  mov     [rbp+90h+var_40], rax
0x1400017c4  mov     rax, [rbp+90h+arg_98]
0x1400017cb  mov     [rbp+90h+var_50], rax
0x1400017cf  mov     rax, [rbp+90h+arg_90]
0x1400017d6  mov     [rbp+90h+var_30], rcx
0x1400017da  mov     [rbp+90h+var_24], ebx
0x1400017dd  mov     [rbp+90h+var_38], 4
0x1400017e5  mov     rcx, [rax]
0x1400017e8  mov     [rbp+90h+var_48], 4
0x1400017f0  test    rcx, rcx
0x1400017f3  jz      short loc_14000180A
0x1400017f5  mov     rax, rdx
0x1400017f8  inc     rax
0x1400017fb  cmp     [rcx+rax*2], bx
0x1400017ff  jnz     short loc_1400017F8
0x140001801  lea     eax, ds:2[rax*2]
0x140001808  jmp     short loc_140001814
0x14000180a  lea     rcx, qword_1400320D8
0x140001811  mov     eax, r9d
0x140001814  mov     [rbp+90h+var_58], eax
0x140001817  mov     rax, [rbp+90h+arg_88]
0x14000181e  mov     [rbp+90h+var_60], rcx
0x140001822  mov     [rbp+90h+var_54], ebx
0x140001825  mov     rcx, [rax]
0x140001828  test    rcx, rcx
0x14000182b  jz      short loc_14000183C
0x14000182d  mov     rax, rdx
0x140001830  inc     rax
0x140001833  cmp     [rcx+rax], bl
0x140001836  jnz     short loc_140001830
0x140001838  inc     eax
0x14000183a  jmp     short loc_140001842
0x14000183c  mov     rcx, rdi
0x14000183f  mov     eax, r8d
0x140001842  mov     [rbp+90h+var_68], eax
0x140001845  mov     rax, [rbp+90h+arg_80]
0x14000184c  mov     [rbp+90h+var_80], rax
0x140001850  mov     rax, [rbp+90h+arg_78]
0x140001857  mov     [rbp+90h+var_70], rcx
0x14000185b  mov     [rbp+90h+var_64], ebx
0x14000185e  mov     [rbp+90h+var_78], 4
0x140001866  mov     rcx, [rax]
0x140001869  test    rcx, rcx
0x14000186c  jz      short loc_140001883
0x14000186e  mov     rax, rdx
0x140001871  inc     rax
0x140001874  cmp     [rcx+rax*2], bx
0x140001878  jnz     short loc_140001871
0x14000187a  lea     eax, ds:2[rax*2]
0x140001881  jmp     short loc_14000188D
0x140001883  lea     rcx, qword_1400320D8
0x14000188a  mov     eax, r9d
0x14000188d  mov     [rbp+90h+var_88], eax
0x140001890  mov     rax, [rbp+90h+arg_70]
0x140001897  mov     [rbp+90h+var_90], rcx
0x14000189b  mov     [rbp+90h+var_84], ebx
0x14000189e  mov     rcx, [rax]
0x1400018a1  test    rcx, rcx
0x1400018a4  jz      short loc_1400018B5
0x1400018a6  mov     rax, rdx
0x1400018a9  inc     rax
0x1400018ac  cmp     [rcx+rax], bl
0x1400018af  jnz     short loc_1400018A9
0x1400018b1  inc     eax
0x1400018b3  jmp     short loc_1400018BB
0x1400018b5  mov     rcx, rdi
0x1400018b8  mov     eax, r8d
0x1400018bb  mov     [rbp+90h+var_98], eax
0x1400018be  mov     rax, [rbp+90h+arg_68]
0x1400018c5  mov     [rbp+90h+var_B0], rax
0x1400018c9  mov     rax, [rbp+90h+arg_60]
0x1400018d0  mov     [rbp+90h+var_A0], rcx
0x1400018d4  mov     [rbp+90h+var_94], ebx
0x1400018d7  mov     [rbp+90h+var_A8], 4
0x1400018df  mov     rcx, [rax]
0x1400018e2  test    rcx, rcx
0x1400018e5  jz      short loc_1400018F6
0x1400018e7  mov     rax, rdx
0x1400018ea  inc     rax
0x1400018ed  cmp     [rcx+rax], bl
0x1400018f0  jnz     short loc_1400018EA
0x1400018f2  inc     eax
0x1400018f4  jmp     short loc_1400018FC
0x1400018f6  mov     rcx, rdi
0x1400018f9  mov     eax, r8d
0x1400018fc  mov     [rbp+90h+var_B8], eax
0x1400018ff  mov     rax, [rbp+90h+arg_58]
0x140001906  mov     [rbp+90h+var_D0], rax
0x14000190a  mov     rax, [rbp+90h+arg_50]
0x140001911  mov     [rbp+90h+var_C0], rcx
0x140001915  mov     [rbp+90h+var_B4], ebx
0x140001918  mov     [rbp+90h+var_C8], 4
0x140001920  mov     rcx, [rax]
0x140001923  test    rcx, rcx
0x140001926  jz      short loc_14000193E
0x140001928  mov     rax, rdx
0x14000192b  inc     rax
0x14000192e  cmp     [rcx+rax*2], bx
0x140001932  jnz     short loc_14000192B
0x140001934  lea     r9d, ds:2[rax*2]
0x14000193c  jmp     short loc_140001945
0x14000193e  lea     rcx, qword_1400320D8
0x140001945  mov     rax, [rbp+90h+arg_48]
0x14000194c  mov     [rbp+90h+var_F0], rax
0x140001950  mov     rax, [rbp+90h+arg_40]
0x140001957  mov     [rbp+90h+var_E0], rcx
0x14000195b  mov     [rbp+90h+var_D8], r9d
0x14000195f  mov     [rbp+90h+var_D4], ebx
0x140001962  mov     rcx, [rax]
0x140001965  mov     [rbp+90h+var_E8], 4
0x14000196d  test    rcx, rcx
0x140001970  jz      short loc_140001981
0x140001972  mov     rax, rdx
0x140001975  inc     rax
0x140001978  cmp     [rcx+rax], bl
0x14000197b  jnz     short loc_140001975
0x14000197d  inc     eax
0x14000197f  jmp     short loc_140001987
0x140001981  mov     rcx, rdi
0x140001984  mov     eax, r8d
0x140001987  mov     [rbp+90h+var_F8], eax
0x14000198a  mov     rax, [rbp+90h+arg_38]
0x140001991  mov     [rbp+90h+var_110], rax
0x140001995  mov     rax, [rbp+90h+arg_30]
0x14000199c  mov     [rbp+90h+var_100], rcx
0x1400019a0  mov     [rbp+90h+var_F4], ebx
0x1400019a3  mov     [rbp+90h+var_108], 4
0x1400019ab  mov     rcx, [rax]
0x1400019ae  test    rcx, rcx
0x1400019b1  jz      short loc_1400019C1
0x1400019b3  inc     rdx
0x1400019b6  cmp     [rcx+rdx], bl
0x1400019b9  jnz     short loc_1400019B3
0x1400019bb  lea     r8d, [rdx+1]
0x1400019bf  jmp     short loc_1400019C4
0x1400019c1  mov     rcx, rdi
0x1400019c4  mov     rax, [rbp+90h+arg_28]
0x1400019cb  xor     r9d, r9d; int
0x1400019ce  mov     [rsp+190h+var_130], rax
0x1400019d3  mov     rdx, r11; int
0x1400019d6  mov     rax, [rbp+90h+arg_20]
0x1400019dd  mov     [rsp+190h+var_140], rax
0x1400019e2  lea     rax, [rsp+190h+var_160]
0x1400019e7  mov     [rsp+190h+var_120], rcx
0x1400019ec  mov     rcx, r10; int
0x1400019ef  mov     [rsp+190h+var_118], r8d
0x1400019f4  xor     r8d, r8d; int
0x1400019f7  mov     [rsp+190h+var_168], rax; PEVENT_DATA_DESCRIPTOR
0x1400019fc  mov     [rsp+190h+var_170], 14h; ULONG
0x140001a04  mov     [rsp+190h+var_114], ebx
0x140001a08  mov     [rsp+190h+var_128], 4
0x140001a11  mov     [rsp+190h+var_138], 8
0x140001a1a  call    _tlgWriteTransfer_EventWriteTransfer
0x140001a1f  mov     rcx, [rbp+90h+var_20]
0x140001a23  xor     rcx, rsp; StackCookie
0x140001a26  call    __security_check_cookie
0x140001a2b  mov     rbx, [rsp+190h+arg_10]
0x140001a33  add     rsp, 180h
0x140001a3a  pop     r14
0x140001a3c  pop     rdi
0x140001a3d  pop     rbp
0x140001a3e  retn
```
