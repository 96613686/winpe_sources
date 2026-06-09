# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001658`
- end: `0x180001947`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800153d4`

## callees

- `0x180001658`
- `0x180001a8c`
- `0x180019760`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
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
  int v25; // r8d
  const unsigned __int16 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  int *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  int *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  int *v45; // rcx
  __int64 v46; // rax
  const unsigned __int16 *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rcx
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  int *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  int *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  int *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v95; // [rsp+160h] [rbp+60h]
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
    v26 = &word_18001F07E;
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
    v30 = &dword_18001D62C;
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
    v33 = &word_18001F07E;
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
    v36 = &dword_18001D62C;
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
    v39 = &word_18001F07E;
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
    v42 = &word_18001F07E;
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
    v45 = &dword_18001D62C;
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
    v47 = &word_18001F07E;
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
    v50 = &word_18001F07E;
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
0x180001658  mov     [rsp-8+arg_10], rbx
0x18000165d  push    rbp
0x18000165e  push    rdi
0x18000165f  push    r14
0x180001661  lea     rbp, [rsp-80h]
0x180001666  sub     rsp, 180h
0x18000166d  mov     rax, cs:__security_cookie
0x180001674  xor     rax, rsp
0x180001677  mov     [rbp+90h+var_20], rax
0x18000167b  mov     rax, [rbp+90h+arg_A8]
0x180001682  lea     rdi, word_18001F07E
0x180001689  mov     r11, rdx
0x18000168c  mov     r10, rcx
0x18000168f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001693  xor     ebx, ebx
0x180001695  mov     r8d, 1
0x18000169b  mov     rcx, [rax]
0x18000169e  test    rcx, rcx
0x1800016a1  jz      short loc_1800016B2
0x1800016a3  mov     rax, rdx
0x1800016a6  inc     rax
0x1800016a9  cmp     [rcx+rax], bl
0x1800016ac  jnz     short loc_1800016A6
0x1800016ae  inc     eax
0x1800016b0  jmp     short loc_1800016B8
0x1800016b2  mov     rcx, rdi
0x1800016b5  mov     eax, r8d
0x1800016b8  mov     [rbp+90h+var_28], eax
0x1800016bb  mov     r9d, 2
0x1800016c1  mov     rax, [rbp+90h+arg_A0]
0x1800016c8  mov     [rbp+90h+var_40], rax
0x1800016cc  mov     rax, [rbp+90h+arg_98]
0x1800016d3  mov     [rbp+90h+var_50], rax
0x1800016d7  mov     rax, [rbp+90h+arg_90]
0x1800016de  mov     [rbp+90h+var_30], rcx
0x1800016e2  mov     [rbp+90h+var_24], ebx
0x1800016e5  mov     [rbp+90h+var_38], 4
0x1800016ed  mov     rcx, [rax]
0x1800016f0  mov     [rbp+90h+var_48], 4
0x1800016f8  test    rcx, rcx
0x1800016fb  jz      short loc_180001712
0x1800016fd  mov     rax, rdx
0x180001700  inc     rax
0x180001703  cmp     [rcx+rax*2], bx
0x180001707  jnz     short loc_180001700
0x180001709  lea     eax, ds:2[rax*2]
0x180001710  jmp     short loc_18000171C
0x180001712  lea     rcx, dword_18001D62C
0x180001719  mov     eax, r9d
0x18000171c  mov     [rbp+90h+var_58], eax
0x18000171f  mov     rax, [rbp+90h+arg_88]
0x180001726  mov     [rbp+90h+var_60], rcx
0x18000172a  mov     [rbp+90h+var_54], ebx
0x18000172d  mov     rcx, [rax]
0x180001730  test    rcx, rcx
0x180001733  jz      short loc_180001744
0x180001735  mov     rax, rdx
0x180001738  inc     rax
0x18000173b  cmp     [rcx+rax], bl
0x18000173e  jnz     short loc_180001738
0x180001740  inc     eax
0x180001742  jmp     short loc_18000174A
0x180001744  mov     rcx, rdi
0x180001747  mov     eax, r8d
0x18000174a  mov     [rbp+90h+var_68], eax
0x18000174d  mov     rax, [rbp+90h+arg_80]
0x180001754  mov     [rbp+90h+var_80], rax
0x180001758  mov     rax, [rbp+90h+arg_78]
0x18000175f  mov     [rbp+90h+var_70], rcx
0x180001763  mov     [rbp+90h+var_64], ebx
0x180001766  mov     [rbp+90h+var_78], 4
0x18000176e  mov     rcx, [rax]
0x180001771  test    rcx, rcx
0x180001774  jz      short loc_18000178B
0x180001776  mov     rax, rdx
0x180001779  inc     rax
0x18000177c  cmp     [rcx+rax*2], bx
0x180001780  jnz     short loc_180001779
0x180001782  lea     eax, ds:2[rax*2]
0x180001789  jmp     short loc_180001795
0x18000178b  lea     rcx, dword_18001D62C
0x180001792  mov     eax, r9d
0x180001795  mov     [rbp+90h+var_88], eax
0x180001798  mov     rax, [rbp+90h+arg_70]
0x18000179f  mov     [rbp+90h+var_90], rcx
0x1800017a3  mov     [rbp+90h+var_84], ebx
0x1800017a6  mov     rcx, [rax]
0x1800017a9  test    rcx, rcx
0x1800017ac  jz      short loc_1800017BD
0x1800017ae  mov     rax, rdx
0x1800017b1  inc     rax
0x1800017b4  cmp     [rcx+rax], bl
0x1800017b7  jnz     short loc_1800017B1
0x1800017b9  inc     eax
0x1800017bb  jmp     short loc_1800017C3
0x1800017bd  mov     rcx, rdi
0x1800017c0  mov     eax, r8d
0x1800017c3  mov     [rbp+90h+var_98], eax
0x1800017c6  mov     rax, [rbp+90h+arg_68]
0x1800017cd  mov     [rbp+90h+var_B0], rax
0x1800017d1  mov     rax, [rbp+90h+arg_60]
0x1800017d8  mov     [rbp+90h+var_A0], rcx
0x1800017dc  mov     [rbp+90h+var_94], ebx
0x1800017df  mov     [rbp+90h+var_A8], 4
0x1800017e7  mov     rcx, [rax]
0x1800017ea  test    rcx, rcx
0x1800017ed  jz      short loc_1800017FE
0x1800017ef  mov     rax, rdx
0x1800017f2  inc     rax
0x1800017f5  cmp     [rcx+rax], bl
0x1800017f8  jnz     short loc_1800017F2
0x1800017fa  inc     eax
0x1800017fc  jmp     short loc_180001804
0x1800017fe  mov     rcx, rdi
0x180001801  mov     eax, r8d
0x180001804  mov     [rbp+90h+var_B8], eax
0x180001807  mov     rax, [rbp+90h+arg_58]
0x18000180e  mov     [rbp+90h+var_D0], rax
0x180001812  mov     rax, [rbp+90h+arg_50]
0x180001819  mov     [rbp+90h+var_C0], rcx
0x18000181d  mov     [rbp+90h+var_B4], ebx
0x180001820  mov     [rbp+90h+var_C8], 4
0x180001828  mov     rcx, [rax]
0x18000182b  test    rcx, rcx
0x18000182e  jz      short loc_180001846
0x180001830  mov     rax, rdx
0x180001833  inc     rax
0x180001836  cmp     [rcx+rax*2], bx
0x18000183a  jnz     short loc_180001833
0x18000183c  lea     r9d, ds:2[rax*2]
0x180001844  jmp     short loc_18000184D
0x180001846  lea     rcx, dword_18001D62C
0x18000184d  mov     rax, [rbp+90h+arg_48]
0x180001854  mov     [rbp+90h+var_F0], rax
0x180001858  mov     rax, [rbp+90h+arg_40]
0x18000185f  mov     [rbp+90h+var_E0], rcx
0x180001863  mov     [rbp+90h+var_D8], r9d
0x180001867  mov     [rbp+90h+var_D4], ebx
0x18000186a  mov     rcx, [rax]
0x18000186d  mov     [rbp+90h+var_E8], 4
0x180001875  test    rcx, rcx
0x180001878  jz      short loc_180001889
0x18000187a  mov     rax, rdx
0x18000187d  inc     rax
0x180001880  cmp     [rcx+rax], bl
0x180001883  jnz     short loc_18000187D
0x180001885  inc     eax
0x180001887  jmp     short loc_18000188F
0x180001889  mov     rcx, rdi
0x18000188c  mov     eax, r8d
0x18000188f  mov     [rbp+90h+var_F8], eax
0x180001892  mov     rax, [rbp+90h+arg_38]
0x180001899  mov     [rbp+90h+var_110], rax
0x18000189d  mov     rax, [rbp+90h+arg_30]
0x1800018a4  mov     [rbp+90h+var_100], rcx
0x1800018a8  mov     [rbp+90h+var_F4], ebx
0x1800018ab  mov     [rbp+90h+var_108], 4
0x1800018b3  mov     rcx, [rax]
0x1800018b6  test    rcx, rcx
0x1800018b9  jz      short loc_1800018C9
0x1800018bb  inc     rdx
0x1800018be  cmp     [rcx+rdx], bl
0x1800018c1  jnz     short loc_1800018BB
0x1800018c3  lea     r8d, [rdx+1]
0x1800018c7  jmp     short loc_1800018CC
0x1800018c9  mov     rcx, rdi
0x1800018cc  mov     rax, [rbp+90h+arg_28]
0x1800018d3  xor     r9d, r9d
0x1800018d6  mov     [rsp+190h+var_130], rax
0x1800018db  mov     rdx, r11
0x1800018de  mov     rax, [rbp+90h+arg_20]
0x1800018e5  mov     [rsp+190h+var_140], rax
0x1800018ea  lea     rax, [rsp+190h+var_160]
0x1800018ef  mov     [rsp+190h+var_120], rcx
0x1800018f4  mov     rcx, r10
0x1800018f7  mov     [rsp+190h+var_118], r8d
0x1800018fc  xor     r8d, r8d
0x1800018ff  mov     [rsp+190h+var_168], rax
0x180001904  mov     [rsp+190h+var_170], 14h
0x18000190c  mov     [rsp+190h+var_114], ebx
0x180001910  mov     [rsp+190h+var_128], 4
0x180001919  mov     [rsp+190h+var_138], 8
0x180001922  call    _tlgWriteTransfer_EventWriteTransfer
0x180001927  mov     rcx, [rbp+90h+var_20]
0x18000192b  xor     rcx, rsp; StackCookie
0x18000192e  call    __security_check_cookie
0x180001933  mov     rbx, [rsp+190h+arg_10]
0x18000193b  add     rsp, 180h
0x180001942  pop     r14
0x180001944  pop     rdi
0x180001945  pop     rbp
0x180001946  retn
```
