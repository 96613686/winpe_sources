# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001724`
- end: `0x140001ad4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@44444AEBU?$_tlgWrapperByVal@$03@@555555555555555555555@Z`
- size: `944`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001efa4`

## callees

- `0x140001724`
- `0x140001ad4`
- `0x140005c20`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
        __int64 a33)
{
  __int64 v34; // rcx
  int v36; // edx
  int *v37; // r8
  __int64 v38; // rax
  int v39; // eax
  int *v40; // r8
  __int64 v41; // rax
  int v42; // eax
  int *v43; // r8
  __int64 v44; // rax
  int v45; // eax
  int *v46; // r8
  __int64 v47; // rax
  int v48; // eax
  int *v49; // r8
  __int64 v50; // rax
  int v51; // eax
  int *v52; // r8
  struct _EVENT_DATA_DESCRIPTOR v54; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h]
  int *v57; // [rsp+60h] [rbp-A0h]
  int v58; // [rsp+68h] [rbp-98h]
  int v59; // [rsp+6Ch] [rbp-94h]
  int *v60; // [rsp+70h] [rbp-90h]
  int v61; // [rsp+78h] [rbp-88h]
  int v62; // [rsp+7Ch] [rbp-84h]
  int *v63; // [rsp+80h] [rbp-80h]
  int v64; // [rsp+88h] [rbp-78h]
  int v65; // [rsp+8Ch] [rbp-74h]
  int *v66; // [rsp+90h] [rbp-70h]
  int v67; // [rsp+98h] [rbp-68h]
  int v68; // [rsp+9Ch] [rbp-64h]
  int *v69; // [rsp+A0h] [rbp-60h]
  int v70; // [rsp+A8h] [rbp-58h]
  int v71; // [rsp+ACh] [rbp-54h]
  int *v72; // [rsp+B0h] [rbp-50h]
  int v73; // [rsp+B8h] [rbp-48h]
  int v74; // [rsp+BCh] [rbp-44h]
  __int64 v75; // [rsp+C0h] [rbp-40h]
  __int64 v76; // [rsp+C8h] [rbp-38h]
  __int64 v77; // [rsp+D0h] [rbp-30h]
  __int64 v78; // [rsp+D8h] [rbp-28h]
  __int64 v79; // [rsp+E0h] [rbp-20h]
  __int64 v80; // [rsp+E8h] [rbp-18h]
  __int64 v81; // [rsp+F0h] [rbp-10h]
  __int64 v82; // [rsp+F8h] [rbp-8h]
  __int64 v83; // [rsp+100h] [rbp+0h]
  __int64 v84; // [rsp+108h] [rbp+8h]
  __int64 v85; // [rsp+110h] [rbp+10h]
  __int64 v86; // [rsp+118h] [rbp+18h]
  __int64 v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  __int64 v89; // [rsp+130h] [rbp+30h]
  __int64 v90; // [rsp+138h] [rbp+38h]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  __int64 v95; // [rsp+160h] [rbp+60h]
  __int64 v96; // [rsp+168h] [rbp+68h]
  __int64 v97; // [rsp+170h] [rbp+70h]
  __int64 v98; // [rsp+178h] [rbp+78h]
  __int64 v99; // [rsp+180h] [rbp+80h]
  __int64 v100; // [rsp+188h] [rbp+88h]
  __int64 v101; // [rsp+190h] [rbp+90h]
  __int64 v102; // [rsp+198h] [rbp+98h]
  __int64 v103; // [rsp+1A0h] [rbp+A0h]
  __int64 v104; // [rsp+1A8h] [rbp+A8h]
  __int64 v105; // [rsp+1B0h] [rbp+B0h]
  __int64 v106; // [rsp+1B8h] [rbp+B8h]
  __int64 v107; // [rsp+1C0h] [rbp+C0h]
  __int64 v108; // [rsp+1C8h] [rbp+C8h]
  __int64 v109; // [rsp+1D0h] [rbp+D0h]
  __int64 v110; // [rsp+1D8h] [rbp+D8h]
  __int64 v111; // [rsp+1E0h] [rbp+E0h]
  __int64 v112; // [rsp+1E8h] [rbp+E8h]
  __int64 v113; // [rsp+1F0h] [rbp+F0h]
  __int64 v114; // [rsp+1F8h] [rbp+F8h]
  __int64 v115; // [rsp+200h] [rbp+100h]
  __int64 v116; // [rsp+208h] [rbp+108h]
  __int64 v117; // [rsp+210h] [rbp+110h]
  __int64 v118; // [rsp+218h] [rbp+118h]

  v117 = a33;
  v115 = a32;
  v34 = -1;
  v113 = a31;
  v36 = 2;
  v111 = a30;
  v109 = a29;
  v107 = a28;
  v105 = a27;
  v103 = a26;
  v101 = a25;
  v99 = a24;
  v97 = a23;
  v95 = a22;
  v93 = a21;
  v91 = a20;
  v89 = a19;
  v87 = a18;
  v85 = a17;
  v83 = a16;
  v81 = a15;
  v79 = a14;
  v77 = a13;
  v75 = a12;
  v118 = 4;
  v116 = 4;
  v114 = 4;
  v37 = *a11;
  v112 = 4;
  v110 = 4;
  v108 = 4;
  v106 = 4;
  v104 = 4;
  v102 = 4;
  v100 = 4;
  v98 = 4;
  v96 = 4;
  v94 = 4;
  v92 = 4;
  v90 = 4;
  v88 = 4;
  v86 = 4;
  v84 = 4;
  v82 = 4;
  v80 = 4;
  v78 = 4;
  v76 = 4;
  if ( v37 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &dword_140033A5C;
    v39 = 2;
  }
  v73 = v39;
  v72 = v37;
  v74 = 0;
  v40 = *a10;
  if ( *a10 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    v42 = 2 * v41 + 2;
  }
  else
  {
    v40 = &dword_140033A5C;
    v42 = 2;
  }
  v70 = v42;
  v69 = v40;
  v71 = 0;
  v43 = *a9;
  if ( *a9 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_WORD *)v43 + v44) );
    v45 = 2 * v44 + 2;
  }
  else
  {
    v43 = &dword_140033A5C;
    v45 = 2;
  }
  v67 = v45;
  v66 = v43;
  v68 = 0;
  v46 = *a8;
  if ( *a8 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_WORD *)v46 + v47) );
    v48 = 2 * v47 + 2;
  }
  else
  {
    v46 = &dword_140033A5C;
    v48 = 2;
  }
  v64 = v48;
  v63 = v46;
  v65 = 0;
  v49 = *a7;
  if ( *a7 )
  {
    v50 = -1;
    do
      ++v50;
    while ( *((_WORD *)v49 + v50) );
    v51 = 2 * v50 + 2;
  }
  else
  {
    v49 = &dword_140033A5C;
    v51 = 2;
  }
  v61 = v51;
  v60 = v49;
  v62 = 0;
  v52 = *a6;
  if ( *a6 )
  {
    do
      ++v34;
    while ( *((_WORD *)v52 + v34) );
    v36 = 2 * v34 + 2;
  }
  else
  {
    v52 = &dword_140033A5C;
  }
  v55 = a5;
  v57 = v52;
  v58 = v36;
  v59 = 0;
  v56 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x1Fu, &v54);
}

```

## disassembly

```asm
0x140001724  mov     [rsp-8+arg_10], rbx
0x140001729  push    rbp
0x14000172a  lea     rbp, [rsp-130h]
0x140001732  sub     rsp, 230h
0x140001739  mov     rax, cs:__security_cookie
0x140001740  xor     rax, rsp
0x140001743  mov     [rbp+130h+var_10], rax
0x14000174a  mov     rax, [rbp+130h+arg_100]
0x140001751  lea     rbx, dword_140033A5C
0x140001758  mov     [rbp+130h+var_20], rax
0x14000175f  xor     r9d, r9d; int
0x140001762  mov     rax, [rbp+130h+arg_F8]
0x140001769  mov     r10, rcx
0x14000176c  mov     [rbp+130h+var_30], rax
0x140001773  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001777  mov     rax, [rbp+130h+arg_F0]
0x14000177e  mov     r11, rdx
0x140001781  mov     [rbp+130h+var_40], rax
0x140001788  lea     edx, [r9+2]
0x14000178c  mov     rax, [rbp+130h+arg_E8]
0x140001793  mov     [rbp+130h+var_50], rax
0x14000179a  mov     rax, [rbp+130h+arg_E0]
0x1400017a1  mov     [rbp+130h+var_60], rax
0x1400017a8  mov     rax, [rbp+130h+arg_D8]
0x1400017af  mov     [rbp+130h+var_70], rax
0x1400017b6  mov     rax, [rbp+130h+arg_D0]
0x1400017bd  mov     [rbp+130h+var_80], rax
0x1400017c4  mov     rax, [rbp+130h+arg_C8]
0x1400017cb  mov     [rbp+130h+var_90], rax
0x1400017d2  mov     rax, [rbp+130h+arg_C0]
0x1400017d9  mov     [rbp+130h+var_A0], rax
0x1400017e0  mov     rax, [rbp+130h+arg_B8]
0x1400017e7  mov     [rbp+130h+var_B0], rax
0x1400017ee  mov     rax, [rbp+130h+arg_B0]
0x1400017f5  mov     [rbp+130h+var_C0], rax
0x1400017f9  mov     rax, [rbp+130h+arg_A8]
0x140001800  mov     [rbp+130h+var_D0], rax
0x140001804  mov     rax, [rbp+130h+arg_A0]
0x14000180b  mov     [rbp+130h+var_E0], rax
0x14000180f  mov     rax, [rbp+130h+arg_98]
0x140001816  mov     [rbp+130h+var_F0], rax
0x14000181a  mov     rax, [rbp+130h+arg_90]
0x140001821  mov     [rbp+130h+var_100], rax
0x140001825  mov     rax, [rbp+130h+arg_88]
0x14000182c  mov     [rbp+130h+var_110], rax
0x140001830  mov     rax, [rbp+130h+arg_80]
0x140001837  mov     [rbp+130h+var_120], rax
0x14000183b  mov     rax, [rbp+130h+arg_78]
0x140001842  mov     [rbp+130h+var_130], rax
0x140001846  mov     rax, [rbp+130h+arg_70]
0x14000184d  mov     [rbp+130h+var_140], rax
0x140001851  mov     rax, [rbp+130h+arg_68]
0x140001858  mov     [rbp+130h+var_150], rax
0x14000185c  mov     rax, [rbp+130h+arg_60]
0x140001863  mov     [rbp+130h+var_160], rax
0x140001867  mov     rax, [rbp+130h+arg_58]
0x14000186e  mov     [rbp+130h+var_170], rax
0x140001872  mov     rax, [rbp+130h+arg_50]
0x140001879  mov     [rbp+130h+var_18], 4
0x140001884  mov     [rbp+130h+var_28], 4
0x14000188f  mov     [rbp+130h+var_38], 4
0x14000189a  mov     r8, [rax]
0x14000189d  mov     [rbp+130h+var_48], 4
0x1400018a8  mov     [rbp+130h+var_58], 4
0x1400018b3  mov     [rbp+130h+var_68], 4
0x1400018be  mov     [rbp+130h+var_78], 4
0x1400018c9  mov     [rbp+130h+var_88], 4
0x1400018d4  mov     [rbp+130h+var_98], 4
0x1400018df  mov     [rbp+130h+var_A8], 4
0x1400018ea  mov     [rbp+130h+var_B8], 4
0x1400018f2  mov     [rbp+130h+var_C8], 4
0x1400018fa  mov     [rbp+130h+var_D8], 4
0x140001902  mov     [rbp+130h+var_E8], 4
0x14000190a  mov     [rbp+130h+var_F8], 4
0x140001912  mov     [rbp+130h+var_108], 4
0x14000191a  mov     [rbp+130h+var_118], 4
0x140001922  mov     [rbp+130h+var_128], 4
0x14000192a  mov     [rbp+130h+var_138], 4
0x140001932  mov     [rbp+130h+var_148], 4
0x14000193a  mov     [rbp+130h+var_158], 4
0x140001942  mov     [rbp+130h+var_168], 4
0x14000194a  test    r8, r8
0x14000194d  jz      short loc_140001965
0x14000194f  mov     rax, rcx
0x140001952  inc     rax
0x140001955  cmp     [r8+rax*2], r9w
0x14000195a  jnz     short loc_140001952
0x14000195c  lea     eax, ds:2[rax*2]
0x140001963  jmp     short loc_14000196A
0x140001965  mov     r8, rbx
0x140001968  mov     eax, edx
0x14000196a  mov     [rbp+130h+var_178], eax
0x14000196d  mov     rax, [rbp+130h+arg_48]
0x140001974  mov     [rbp+130h+var_180], r8
0x140001978  mov     [rbp+130h+var_174], r9d
0x14000197c  mov     r8, [rax]
0x14000197f  test    r8, r8
0x140001982  jz      short loc_14000199A
0x140001984  mov     rax, rcx
0x140001987  inc     rax
0x14000198a  cmp     [r8+rax*2], r9w
0x14000198f  jnz     short loc_140001987
0x140001991  lea     eax, ds:2[rax*2]
0x140001998  jmp     short loc_14000199F
0x14000199a  mov     r8, rbx
0x14000199d  mov     eax, edx
0x14000199f  mov     [rbp+130h+var_188], eax
0x1400019a2  mov     rax, [rbp+130h+arg_40]
0x1400019a9  mov     [rbp+130h+var_190], r8
0x1400019ad  mov     [rbp+130h+var_184], r9d
0x1400019b1  mov     r8, [rax]
0x1400019b4  test    r8, r8
0x1400019b7  jz      short loc_1400019CF
0x1400019b9  mov     rax, rcx
0x1400019bc  inc     rax
0x1400019bf  cmp     [r8+rax*2], r9w
0x1400019c4  jnz     short loc_1400019BC
0x1400019c6  lea     eax, ds:2[rax*2]
0x1400019cd  jmp     short loc_1400019D4
0x1400019cf  mov     r8, rbx
0x1400019d2  mov     eax, edx
0x1400019d4  mov     [rbp+130h+var_198], eax
0x1400019d7  mov     rax, [rbp+130h+arg_38]
0x1400019de  mov     [rbp+130h+var_1A0], r8
0x1400019e2  mov     [rbp+130h+var_194], r9d
0x1400019e6  mov     r8, [rax]
0x1400019e9  test    r8, r8
0x1400019ec  jz      short loc_140001A04
0x1400019ee  mov     rax, rcx
0x1400019f1  inc     rax
0x1400019f4  cmp     [r8+rax*2], r9w
0x1400019f9  jnz     short loc_1400019F1
0x1400019fb  lea     eax, ds:2[rax*2]
0x140001a02  jmp     short loc_140001A09
0x140001a04  mov     r8, rbx
0x140001a07  mov     eax, edx
0x140001a09  mov     [rbp+130h+var_1A8], eax
0x140001a0c  mov     rax, [rbp+130h+arg_30]
0x140001a13  mov     [rbp+130h+var_1B0], r8
0x140001a17  mov     [rbp+130h+var_1A4], r9d
0x140001a1b  mov     r8, [rax]
0x140001a1e  test    r8, r8
0x140001a21  jz      short loc_140001A39
0x140001a23  mov     rax, rcx
0x140001a26  inc     rax
0x140001a29  cmp     [r8+rax*2], r9w
0x140001a2e  jnz     short loc_140001A26
0x140001a30  lea     eax, ds:2[rax*2]
0x140001a37  jmp     short loc_140001A3E
0x140001a39  mov     r8, rbx
0x140001a3c  mov     eax, edx
0x140001a3e  mov     [rsp+230h+var_1B8], eax
0x140001a42  mov     rax, [rbp+130h+arg_28]
0x140001a49  mov     [rsp+230h+var_1C0], r8
0x140001a4e  mov     [rsp+230h+var_1B4], r9d
0x140001a53  mov     r8, [rax]
0x140001a56  test    r8, r8
0x140001a59  jz      short loc_140001A6E
0x140001a5b  inc     rcx
0x140001a5e  cmp     [r8+rcx*2], r9w
0x140001a63  jnz     short loc_140001A5B
0x140001a65  lea     edx, ds:2[rcx*2]
0x140001a6c  jmp     short loc_140001A71
0x140001a6e  mov     r8, rbx
0x140001a71  mov     rax, [rbp+130h+arg_20]
0x140001a78  mov     rcx, r10; int
0x140001a7b  mov     [rsp+230h+var_1E0], rax
0x140001a80  lea     rax, [rsp+230h+var_200]
0x140001a85  mov     [rsp+230h+var_1D0], r8
0x140001a8a  xor     r8d, r8d; int
0x140001a8d  mov     [rsp+230h+var_1C8], edx
0x140001a91  mov     rdx, r11; int
0x140001a94  mov     [rsp+230h+var_208], rax; PEVENT_DATA_DESCRIPTOR
0x140001a99  mov     [rsp+230h+var_210], 1Fh; ULONG
0x140001aa1  mov     [rsp+230h+var_1C4], r9d
0x140001aa6  mov     [rsp+230h+var_1D8], 8
0x140001aaf  call    _tlgWriteTransfer_EventWriteTransfer
0x140001ab4  mov     rcx, [rbp+130h+var_10]
0x140001abb  xor     rcx, rsp; StackCookie
0x140001abe  call    __security_check_cookie
0x140001ac3  mov     rbx, [rsp+230h+arg_10]
0x140001acb  add     rsp, 230h
0x140001ad2  pop     rbp
0x140001ad3  retn
```
