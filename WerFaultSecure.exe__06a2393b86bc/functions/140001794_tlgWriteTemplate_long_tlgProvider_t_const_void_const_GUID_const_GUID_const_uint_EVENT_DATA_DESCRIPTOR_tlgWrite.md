# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x140001794`
- end: `0x140001a3f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, int **, __int64, const wchar_t **, __int64, const wchar_t **, int **, __int64, const wchar_t **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000be98`

## callees

- `0x14000113c`
- `0x140001794`
- `0x1400023d0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t **a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        int **a12,
        __int64 a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        int **a17,
        __int64 a18,
        const wchar_t **a19,
        int **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  int *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const wchar_t *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const wchar_t *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const wchar_t *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rdx
  __int64 v41; // rax
  const wchar_t *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const wchar_t *v45; // rdx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const wchar_t *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const wchar_t *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  int *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const wchar_t *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const wchar_t *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  int *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const wchar_t *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  int *v85; // [rsp+140h] [rbp+40h]
  int v86; // [rsp+148h] [rbp+48h]
  int v87; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v23 = 2;
  v24 = *a20;
  if ( *a20 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &dword_140014A6C;
    v26 = 2;
  }
  v86 = v26;
  v27 = 1;
  v85 = v24;
  v87 = 0;
  v28 = *a19;
  if ( *a19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &byte_140013F31;
    v30 = 1;
  }
  v83 = v30;
  v80 = a18;
  v82 = v28;
  v84 = 0;
  v81 = 4;
  v31 = *a17;
  if ( *a17 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_140014A6C;
    v33 = 2;
  }
  v78 = v33;
  v77 = v31;
  v79 = 0;
  v34 = *a16;
  if ( *a16 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &byte_140013F31;
    v36 = 1;
  }
  v75 = v36;
  v72 = a15;
  v74 = v34;
  v76 = 0;
  v73 = 4;
  v37 = *a14;
  if ( *a14 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &byte_140013F31;
    v39 = 1;
  }
  v70 = v39;
  v67 = a13;
  v69 = v37;
  v71 = 0;
  v68 = 4;
  v40 = *a12;
  if ( *a12 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &dword_140014A6C;
  }
  v62 = a11;
  v64 = v40;
  v65 = v23;
  v66 = 0;
  v42 = *a10;
  v63 = 4;
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &byte_140013F31;
    v44 = 1;
  }
  v60 = v44;
  v57 = a9;
  v59 = v42;
  v61 = 0;
  v58 = 4;
  v45 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v45 + v22) );
    v27 = v22 + 1;
  }
  else
  {
    v45 = &byte_140013F31;
  }
  v52 = a7;
  v50 = a6;
  v48 = a5;
  v54 = v45;
  v55 = v27;
  v56 = 0;
  v53 = 4;
  v51 = 8;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 18, v47);
}

```

## disassembly

```asm
0x140001794  mov     [rsp-8+arg_10], rbx
0x140001799  push    rbp
0x14000179a  push    rsi
0x14000179b  push    rdi
0x14000179c  lea     rbp, [rsp-60h]
0x1400017a1  sub     rsp, 160h
0x1400017a8  mov     rax, cs:__security_cookie
0x1400017af  xor     rax, rsp
0x1400017b2  mov     [rbp+70h+var_20], rax
0x1400017b6  mov     rax, [rbp+70h+arg_98]
0x1400017bd  mov     r11, rdx
0x1400017c0  mov     r10, rcx
0x1400017c3  xor     ebx, ebx
0x1400017c5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400017c9  mov     r9d, 2
0x1400017cf  mov     rdx, [rax]
0x1400017d2  test    rdx, rdx
0x1400017d5  jz      short loc_1400017EC
0x1400017d7  mov     rax, rcx
0x1400017da  inc     rax
0x1400017dd  cmp     [rdx+rax*2], bx
0x1400017e1  jnz     short loc_1400017DA
0x1400017e3  lea     eax, ds:2[rax*2]
0x1400017ea  jmp     short loc_1400017F6
0x1400017ec  lea     rdx, dword_140014A6C
0x1400017f3  mov     eax, r9d
0x1400017f6  mov     [rbp+70h+var_28], eax
0x1400017f9  lea     rdi, byte_140013F31
0x140001800  mov     rax, [rbp+70h+arg_90]
0x140001807  mov     r8d, 1
0x14000180d  mov     [rbp+70h+var_30], rdx
0x140001811  mov     [rbp+70h+var_24], ebx
0x140001814  mov     rdx, [rax]
0x140001817  test    rdx, rdx
0x14000181a  jz      short loc_14000182B
0x14000181c  mov     rax, rcx
0x14000181f  inc     rax
0x140001822  cmp     [rdx+rax], bl
0x140001825  jnz     short loc_14000181F
0x140001827  inc     eax
0x140001829  jmp     short loc_140001831
0x14000182b  mov     rdx, rdi
0x14000182e  mov     eax, r8d
0x140001831  mov     [rbp+70h+var_38], eax
0x140001834  mov     rax, [rbp+70h+arg_88]
0x14000183b  mov     [rbp+70h+var_50], rax
0x14000183f  mov     rax, [rbp+70h+arg_80]
0x140001846  mov     [rbp+70h+var_40], rdx
0x14000184a  mov     [rbp+70h+var_34], ebx
0x14000184d  mov     [rbp+70h+var_48], 4
0x140001855  mov     rdx, [rax]
0x140001858  test    rdx, rdx
0x14000185b  jz      short loc_140001872
0x14000185d  mov     rax, rcx
0x140001860  inc     rax
0x140001863  cmp     [rdx+rax*2], bx
0x140001867  jnz     short loc_140001860
0x140001869  lea     eax, ds:2[rax*2]
0x140001870  jmp     short loc_14000187C
0x140001872  lea     rdx, dword_140014A6C
0x140001879  mov     eax, r9d
0x14000187c  mov     [rbp+70h+var_58], eax
0x14000187f  mov     rax, [rbp+70h+arg_78]
0x140001886  mov     [rbp+70h+var_60], rdx
0x14000188a  mov     [rbp+70h+var_54], ebx
0x14000188d  mov     rdx, [rax]
0x140001890  test    rdx, rdx
0x140001893  jz      short loc_1400018A4
0x140001895  mov     rax, rcx
0x140001898  inc     rax
0x14000189b  cmp     [rdx+rax], bl
0x14000189e  jnz     short loc_140001898
0x1400018a0  inc     eax
0x1400018a2  jmp     short loc_1400018AA
0x1400018a4  mov     rdx, rdi
0x1400018a7  mov     eax, r8d
0x1400018aa  mov     [rbp+70h+var_68], eax
0x1400018ad  mov     rax, [rbp+70h+arg_70]
0x1400018b4  mov     [rbp+70h+var_80], rax
0x1400018b8  mov     rax, [rbp+70h+arg_68]
0x1400018bf  mov     [rbp+70h+var_70], rdx
0x1400018c3  mov     [rbp+70h+var_64], ebx
0x1400018c6  mov     [rbp+70h+var_78], 4
0x1400018ce  mov     rdx, [rax]
0x1400018d1  test    rdx, rdx
0x1400018d4  jz      short loc_1400018E5
0x1400018d6  mov     rax, rcx
0x1400018d9  inc     rax
0x1400018dc  cmp     [rdx+rax], bl
0x1400018df  jnz     short loc_1400018D9
0x1400018e1  inc     eax
0x1400018e3  jmp     short loc_1400018EB
0x1400018e5  mov     rdx, rdi
0x1400018e8  mov     eax, r8d
0x1400018eb  mov     [rbp+70h+var_88], eax
0x1400018ee  mov     rax, [rbp+70h+arg_60]
0x1400018f5  mov     [rbp+70h+var_A0], rax
0x1400018f9  mov     rax, [rbp+70h+arg_58]
0x140001900  mov     [rbp+70h+var_90], rdx
0x140001904  mov     [rbp+70h+var_84], ebx
0x140001907  mov     [rbp+70h+var_98], 4
0x14000190f  mov     rdx, [rax]
0x140001912  test    rdx, rdx
0x140001915  jz      short loc_14000192D
0x140001917  mov     rax, rcx
0x14000191a  inc     rax
0x14000191d  cmp     [rdx+rax*2], bx
0x140001921  jnz     short loc_14000191A
0x140001923  lea     r9d, ds:2[rax*2]
0x14000192b  jmp     short loc_140001934
0x14000192d  lea     rdx, dword_140014A6C
0x140001934  mov     rax, [rbp+70h+arg_50]
0x14000193b  mov     [rbp+70h+var_C0], rax
0x14000193f  mov     rax, [rbp+70h+arg_48]
0x140001946  mov     [rbp+70h+var_B0], rdx
0x14000194a  mov     [rbp+70h+var_A8], r9d
0x14000194e  mov     [rbp+70h+var_A4], ebx
0x140001951  mov     rdx, [rax]
0x140001954  mov     [rbp+70h+var_B8], 4
0x14000195c  test    rdx, rdx
0x14000195f  jz      short loc_140001970
0x140001961  mov     rax, rcx
0x140001964  inc     rax
0x140001967  cmp     [rdx+rax], bl
0x14000196a  jnz     short loc_140001964
0x14000196c  inc     eax
0x14000196e  jmp     short loc_140001976
0x140001970  mov     rdx, rdi
0x140001973  mov     eax, r8d
0x140001976  mov     [rbp+70h+var_C8], eax
0x140001979  mov     rax, [rbp+70h+arg_40]
0x140001980  mov     [rbp+70h+var_E0], rax
0x140001984  mov     rax, [rbp+70h+arg_38]
0x14000198b  mov     [rbp+70h+var_D0], rdx
0x14000198f  mov     [rbp+70h+var_C4], ebx
0x140001992  mov     [rbp+70h+var_D8], 4
0x14000199a  mov     rdx, [rax]
0x14000199d  test    rdx, rdx
0x1400019a0  jz      short loc_1400019B0
0x1400019a2  inc     rcx
0x1400019a5  cmp     [rdx+rcx], bl
0x1400019a8  jnz     short loc_1400019A2
0x1400019aa  lea     r8d, [rcx+1]
0x1400019ae  jmp     short loc_1400019B3
0x1400019b0  mov     rdx, rdi
0x1400019b3  mov     rax, [rbp+70h+arg_30]
0x1400019ba  xor     r9d, r9d
0x1400019bd  mov     [rsp+170h+var_100], rax
0x1400019c2  mov     rcx, r10
0x1400019c5  mov     rax, [rbp+70h+arg_28]
0x1400019cc  mov     [rsp+170h+var_110], rax
0x1400019d1  mov     rax, [rbp+70h+arg_20]
0x1400019d8  mov     [rsp+170h+var_120], rax
0x1400019dd  lea     rax, [rsp+170h+var_140]
0x1400019e2  mov     [rbp+70h+var_F0], rdx
0x1400019e6  mov     rdx, r11
0x1400019e9  mov     [rbp+70h+var_E8], r8d
0x1400019ed  xor     r8d, r8d
0x1400019f0  mov     [rsp+170h+var_148], rax
0x1400019f5  mov     [rsp+170h+var_150], 12h
0x1400019fd  mov     [rbp+70h+var_E4], ebx
0x140001a00  mov     [rsp+170h+var_F8], 4
0x140001a09  mov     [rsp+170h+var_108], 8
0x140001a12  mov     [rsp+170h+var_118], 8
0x140001a1b  call    _tlgWriteTransfer_EventWriteTransfer
0x140001a20  mov     rcx, [rbp+70h+var_20]
0x140001a24  xor     rcx, rsp; StackCookie
0x140001a27  call    __security_check_cookie
0x140001a2c  mov     rbx, [rsp+170h+arg_10]
0x140001a34  add     rsp, 160h
0x140001a3b  pop     rdi
0x140001a3c  pop     rsi
0x140001a3d  pop     rbp
0x140001a3e  retn
```
