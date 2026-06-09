# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001658`
- end: `0x180001963`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `779`
- prototype: `__int64 __fastcall(int, int, int, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180025660`
- `0x1800258e0`

## callees

- `0x180001658`
- `0x1800020dc`
- `0x180003520`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        int a1,
        int a2,
        int a3,
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
        const unsigned __int16 **a23)
{
  __int64 v25; // rdx
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
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
  __int64 *v71; // [rsp+C0h] [rbp-40h]
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
  __int64 *v84; // [rsp+110h] [rbp+10h]
  int v85; // [rsp+118h] [rbp+18h]
  int v86; // [rsp+11Ch] [rbp+1Ch]
  __int64 v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v92; // [rsp+140h] [rbp+40h]
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
    v28 = &dword_18002C87C;
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
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &qword_18002D2C0;
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
    v35 = &dword_18002C87C;
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
    while ( *((_WORD *)v38 + v39) );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = &qword_18002D2C0;
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
    v41 = &dword_18002C87C;
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
    v44 = &dword_18002C87C;
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
    while ( *((_WORD *)v47 + v48) );
    v31 = 2 * v48 + 2;
  }
  else
  {
    v47 = &qword_18002D2C0;
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
    v49 = &dword_18002C87C;
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
    v52 = &dword_18002C87C;
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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x15u, &v54);
}

```

## disassembly

```asm
0x180001658  push    rbp
0x18000165a  push    rbx
0x18000165b  push    rsi
0x18000165c  push    rdi
0x18000165d  push    r14
0x18000165f  lea     rbp, [rsp-90h]
0x180001667  sub     rsp, 190h
0x18000166e  mov     rax, cs:__security_cookie
0x180001675  xor     rax, rsp
0x180001678  mov     [rbp+0B0h+var_30], rax
0x18000167f  mov     rax, [rbp+0B0h+arg_B0]
0x180001686  lea     rsi, dword_18002C87C
0x18000168d  mov     r11, rdx
0x180001690  mov     r10, rcx
0x180001693  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001697  xor     edi, edi
0x180001699  mov     rbx, r8
0x18000169c  mov     r8d, 1
0x1800016a2  mov     rcx, [rax]
0x1800016a5  test    rcx, rcx
0x1800016a8  jz      short loc_1800016BA
0x1800016aa  mov     rax, rdx
0x1800016ad  inc     rax
0x1800016b0  cmp     [rcx+rax], dil
0x1800016b4  jnz     short loc_1800016AD
0x1800016b6  inc     eax
0x1800016b8  jmp     short loc_1800016C0
0x1800016ba  mov     rcx, rsi
0x1800016bd  mov     eax, r8d
0x1800016c0  mov     [rbp+0B0h+var_38], eax
0x1800016c3  mov     r9d, 2
0x1800016c9  mov     rax, [rbp+0B0h+arg_A8]
0x1800016d0  mov     [rbp+0B0h+var_50], rax
0x1800016d4  mov     rax, [rbp+0B0h+arg_A0]
0x1800016db  mov     [rbp+0B0h+var_60], rax
0x1800016df  mov     rax, [rbp+0B0h+arg_98]
0x1800016e6  mov     [rbp+0B0h+var_40], rcx
0x1800016ea  mov     [rbp+0B0h+var_34], edi
0x1800016ed  mov     [rbp+0B0h+var_48], 4
0x1800016f5  mov     rcx, [rax]
0x1800016f8  mov     [rbp+0B0h+var_58], 4
0x180001700  test    rcx, rcx
0x180001703  jz      short loc_18000171A
0x180001705  mov     rax, rdx
0x180001708  inc     rax
0x18000170b  cmp     [rcx+rax*2], di
0x18000170f  jnz     short loc_180001708
0x180001711  lea     eax, ds:2[rax*2]
0x180001718  jmp     short loc_180001724
0x18000171a  lea     rcx, qword_18002D2C0
0x180001721  mov     eax, r9d
0x180001724  mov     [rbp+0B0h+var_68], eax
0x180001727  mov     rax, [rbp+0B0h+arg_90]
0x18000172e  mov     [rbp+0B0h+var_70], rcx
0x180001732  mov     [rbp+0B0h+var_64], edi
0x180001735  mov     rcx, [rax]
0x180001738  test    rcx, rcx
0x18000173b  jz      short loc_18000174D
0x18000173d  mov     rax, rdx
0x180001740  inc     rax
0x180001743  cmp     [rcx+rax], dil
0x180001747  jnz     short loc_180001740
0x180001749  inc     eax
0x18000174b  jmp     short loc_180001753
0x18000174d  mov     rcx, rsi
0x180001750  mov     eax, r8d
0x180001753  mov     [rbp+0B0h+var_78], eax
0x180001756  mov     rax, [rbp+0B0h+arg_88]
0x18000175d  mov     [rbp+0B0h+var_90], rax
0x180001761  mov     rax, [rbp+0B0h+arg_80]
0x180001768  mov     [rbp+0B0h+var_80], rcx
0x18000176c  mov     [rbp+0B0h+var_74], edi
0x18000176f  mov     [rbp+0B0h+var_88], 4
0x180001777  mov     rcx, [rax]
0x18000177a  test    rcx, rcx
0x18000177d  jz      short loc_180001794
0x18000177f  mov     rax, rdx
0x180001782  inc     rax
0x180001785  cmp     [rcx+rax*2], di
0x180001789  jnz     short loc_180001782
0x18000178b  lea     eax, ds:2[rax*2]
0x180001792  jmp     short loc_18000179E
0x180001794  lea     rcx, qword_18002D2C0
0x18000179b  mov     eax, r9d
0x18000179e  mov     [rbp+0B0h+var_98], eax
0x1800017a1  mov     rax, [rbp+0B0h+arg_78]
0x1800017a8  mov     [rbp+0B0h+var_A0], rcx
0x1800017ac  mov     [rbp+0B0h+var_94], edi
0x1800017af  mov     rcx, [rax]
0x1800017b2  test    rcx, rcx
0x1800017b5  jz      short loc_1800017C7
0x1800017b7  mov     rax, rdx
0x1800017ba  inc     rax
0x1800017bd  cmp     [rcx+rax], dil
0x1800017c1  jnz     short loc_1800017BA
0x1800017c3  inc     eax
0x1800017c5  jmp     short loc_1800017CD
0x1800017c7  mov     rcx, rsi
0x1800017ca  mov     eax, r8d
0x1800017cd  mov     [rbp+0B0h+var_A8], eax
0x1800017d0  mov     rax, [rbp+0B0h+arg_70]
0x1800017d7  mov     [rbp+0B0h+var_C0], rax
0x1800017db  mov     rax, [rbp+0B0h+arg_68]
0x1800017e2  mov     [rbp+0B0h+var_B0], rcx
0x1800017e6  mov     [rbp+0B0h+var_A4], edi
0x1800017e9  mov     [rbp+0B0h+var_B8], 4
0x1800017f1  mov     rcx, [rax]
0x1800017f4  test    rcx, rcx
0x1800017f7  jz      short loc_180001809
0x1800017f9  mov     rax, rdx
0x1800017fc  inc     rax
0x1800017ff  cmp     [rcx+rax], dil
0x180001803  jnz     short loc_1800017FC
0x180001805  inc     eax
0x180001807  jmp     short loc_18000180F
0x180001809  mov     rcx, rsi
0x18000180c  mov     eax, r8d
0x18000180f  mov     [rbp+0B0h+var_C8], eax
0x180001812  mov     rax, [rbp+0B0h+arg_60]
0x180001819  mov     [rbp+0B0h+var_E0], rax
0x18000181d  mov     rax, [rbp+0B0h+arg_58]
0x180001824  mov     [rbp+0B0h+var_D0], rcx
0x180001828  mov     [rbp+0B0h+var_C4], edi
0x18000182b  mov     [rbp+0B0h+var_D8], 4
0x180001833  mov     rcx, [rax]
0x180001836  test    rcx, rcx
0x180001839  jz      short loc_180001851
0x18000183b  mov     rax, rdx
0x18000183e  inc     rax
0x180001841  cmp     [rcx+rax*2], di
0x180001845  jnz     short loc_18000183E
0x180001847  lea     r9d, ds:2[rax*2]
0x18000184f  jmp     short loc_180001858
0x180001851  lea     rcx, qword_18002D2C0
0x180001858  mov     rax, [rbp+0B0h+arg_50]
0x18000185f  mov     [rbp+0B0h+var_100], rax
0x180001863  mov     rax, [rbp+0B0h+arg_48]
0x18000186a  mov     [rbp+0B0h+var_F0], rcx
0x18000186e  mov     [rbp+0B0h+var_E8], r9d
0x180001872  mov     [rbp+0B0h+var_E4], edi
0x180001875  mov     rcx, [rax]
0x180001878  mov     [rbp+0B0h+var_F8], 4
0x180001880  test    rcx, rcx
0x180001883  jz      short loc_180001895
0x180001885  mov     rax, rdx
0x180001888  inc     rax
0x18000188b  cmp     [rcx+rax], dil
0x18000188f  jnz     short loc_180001888
0x180001891  inc     eax
0x180001893  jmp     short loc_18000189B
0x180001895  mov     rcx, rsi
0x180001898  mov     eax, r8d
0x18000189b  mov     [rbp+0B0h+var_108], eax
0x18000189e  mov     rax, [rbp+0B0h+arg_40]
0x1800018a5  mov     [rbp+0B0h+var_120], rax
0x1800018a9  mov     rax, [rbp+0B0h+arg_38]
0x1800018b0  mov     [rbp+0B0h+var_110], rcx
0x1800018b4  mov     [rbp+0B0h+var_104], edi
0x1800018b7  mov     [rbp+0B0h+var_118], 4
0x1800018bf  mov     rcx, [rax]
0x1800018c2  test    rcx, rcx
0x1800018c5  jz      short loc_1800018D6
0x1800018c7  inc     rdx
0x1800018ca  cmp     [rcx+rdx], dil
0x1800018ce  jnz     short loc_1800018C7
0x1800018d0  lea     r8d, [rdx+1]
0x1800018d4  jmp     short loc_1800018D9
0x1800018d6  mov     rcx, rsi
0x1800018d9  mov     rax, [rbp+0B0h+arg_30]
0x1800018e0  xor     r9d, r9d; int
0x1800018e3  mov     [rsp+1B0h+var_140], rax
0x1800018e8  mov     rdx, r11; int
0x1800018eb  mov     rax, [rbp+0B0h+arg_28]
0x1800018f2  mov     [rsp+1B0h+var_150], rax
0x1800018f7  mov     rax, [rbp+0B0h+arg_20]
0x1800018fe  mov     [rsp+1B0h+var_160], rax
0x180001903  lea     rax, [rsp+1B0h+var_180]
0x180001908  mov     [rbp+0B0h+var_130], rcx
0x18000190c  mov     rcx, r10; int
0x18000190f  mov     [rbp+0B0h+var_128], r8d
0x180001913  mov     r8, rbx; int
0x180001916  mov     [rsp+1B0h+var_188], rax; PEVENT_DATA_DESCRIPTOR
0x18000191b  mov     [rsp+1B0h+var_190], 15h; ULONG
0x180001923  mov     [rbp+0B0h+var_124], edi
0x180001926  mov     [rsp+1B0h+var_138], 4
0x18000192f  mov     [rsp+1B0h+var_148], 8
0x180001938  mov     [rsp+1B0h+var_158], 8
0x180001941  call    _tlgWriteTransfer_EventWriteTransfer
0x180001946  mov     rcx, [rbp+0B0h+var_30]
0x18000194d  xor     rcx, rsp; StackCookie
0x180001950  call    __security_check_cookie
0x180001955  add     rsp, 190h
0x18000195c  pop     r14
0x18000195e  pop     rdi
0x18000195f  pop     rsi
0x180001960  pop     rbx
0x180001961  pop     rbp
0x180001962  retn
```
