# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001008`
- end: `0x1400012b3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009974`

## callees

- `0x140001008`
- `0x14000163c`
- `0x140002120`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        int **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        int **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        int **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  int *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rdx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  int *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  int *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
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
    v24 = &dword_14000DE5C;
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
    v28 = &byte_14000D9BF;
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
    v31 = &dword_14000DE5C;
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
    v34 = &byte_14000D9BF;
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
    v37 = &byte_14000D9BF;
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
    v40 = &dword_14000DE5C;
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
    v42 = &byte_14000D9BF;
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
    v45 = &byte_14000D9BF;
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
0x140001008  mov     [rsp-8+arg_10], rbx
0x14000100d  push    rbp
0x14000100e  push    rsi
0x14000100f  push    rdi
0x140001010  lea     rbp, [rsp-60h]
0x140001015  sub     rsp, 160h
0x14000101c  mov     rax, cs:__security_cookie
0x140001023  xor     rax, rsp
0x140001026  mov     [rbp+70h+var_20], rax
0x14000102a  mov     rax, [rbp+70h+arg_98]
0x140001031  mov     r11, rdx
0x140001034  mov     r10, rcx
0x140001037  xor     ebx, ebx
0x140001039  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000103d  mov     r9d, 2
0x140001043  mov     rdx, [rax]
0x140001046  test    rdx, rdx
0x140001049  jz      short loc_140001060
0x14000104b  mov     rax, rcx
0x14000104e  inc     rax
0x140001051  cmp     [rdx+rax*2], bx
0x140001055  jnz     short loc_14000104E
0x140001057  lea     eax, ds:2[rax*2]
0x14000105e  jmp     short loc_14000106A
0x140001060  lea     rdx, dword_14000DE5C
0x140001067  mov     eax, r9d
0x14000106a  mov     [rbp+70h+var_28], eax
0x14000106d  lea     rdi, byte_14000D9BF
0x140001074  mov     rax, [rbp+70h+arg_90]
0x14000107b  mov     r8d, 1
0x140001081  mov     [rbp+70h+var_30], rdx
0x140001085  mov     [rbp+70h+var_24], ebx
0x140001088  mov     rdx, [rax]
0x14000108b  test    rdx, rdx
0x14000108e  jz      short loc_14000109F
0x140001090  mov     rax, rcx
0x140001093  inc     rax
0x140001096  cmp     [rdx+rax], bl
0x140001099  jnz     short loc_140001093
0x14000109b  inc     eax
0x14000109d  jmp     short loc_1400010A5
0x14000109f  mov     rdx, rdi
0x1400010a2  mov     eax, r8d
0x1400010a5  mov     [rbp+70h+var_38], eax
0x1400010a8  mov     rax, [rbp+70h+arg_88]
0x1400010af  mov     [rbp+70h+var_50], rax
0x1400010b3  mov     rax, [rbp+70h+arg_80]
0x1400010ba  mov     [rbp+70h+var_40], rdx
0x1400010be  mov     [rbp+70h+var_34], ebx
0x1400010c1  mov     [rbp+70h+var_48], 4
0x1400010c9  mov     rdx, [rax]
0x1400010cc  test    rdx, rdx
0x1400010cf  jz      short loc_1400010E6
0x1400010d1  mov     rax, rcx
0x1400010d4  inc     rax
0x1400010d7  cmp     [rdx+rax*2], bx
0x1400010db  jnz     short loc_1400010D4
0x1400010dd  lea     eax, ds:2[rax*2]
0x1400010e4  jmp     short loc_1400010F0
0x1400010e6  lea     rdx, dword_14000DE5C
0x1400010ed  mov     eax, r9d
0x1400010f0  mov     [rbp+70h+var_58], eax
0x1400010f3  mov     rax, [rbp+70h+arg_78]
0x1400010fa  mov     [rbp+70h+var_60], rdx
0x1400010fe  mov     [rbp+70h+var_54], ebx
0x140001101  mov     rdx, [rax]
0x140001104  test    rdx, rdx
0x140001107  jz      short loc_140001118
0x140001109  mov     rax, rcx
0x14000110c  inc     rax
0x14000110f  cmp     [rdx+rax], bl
0x140001112  jnz     short loc_14000110C
0x140001114  inc     eax
0x140001116  jmp     short loc_14000111E
0x140001118  mov     rdx, rdi
0x14000111b  mov     eax, r8d
0x14000111e  mov     [rbp+70h+var_68], eax
0x140001121  mov     rax, [rbp+70h+arg_70]
0x140001128  mov     [rbp+70h+var_80], rax
0x14000112c  mov     rax, [rbp+70h+arg_68]
0x140001133  mov     [rbp+70h+var_70], rdx
0x140001137  mov     [rbp+70h+var_64], ebx
0x14000113a  mov     [rbp+70h+var_78], 4
0x140001142  mov     rdx, [rax]
0x140001145  test    rdx, rdx
0x140001148  jz      short loc_140001159
0x14000114a  mov     rax, rcx
0x14000114d  inc     rax
0x140001150  cmp     [rdx+rax], bl
0x140001153  jnz     short loc_14000114D
0x140001155  inc     eax
0x140001157  jmp     short loc_14000115F
0x140001159  mov     rdx, rdi
0x14000115c  mov     eax, r8d
0x14000115f  mov     [rbp+70h+var_88], eax
0x140001162  mov     rax, [rbp+70h+arg_60]
0x140001169  mov     [rbp+70h+var_A0], rax
0x14000116d  mov     rax, [rbp+70h+arg_58]
0x140001174  mov     [rbp+70h+var_90], rdx
0x140001178  mov     [rbp+70h+var_84], ebx
0x14000117b  mov     [rbp+70h+var_98], 4
0x140001183  mov     rdx, [rax]
0x140001186  test    rdx, rdx
0x140001189  jz      short loc_1400011A1
0x14000118b  mov     rax, rcx
0x14000118e  inc     rax
0x140001191  cmp     [rdx+rax*2], bx
0x140001195  jnz     short loc_14000118E
0x140001197  lea     r9d, ds:2[rax*2]
0x14000119f  jmp     short loc_1400011A8
0x1400011a1  lea     rdx, dword_14000DE5C
0x1400011a8  mov     rax, [rbp+70h+arg_50]
0x1400011af  mov     [rbp+70h+var_C0], rax
0x1400011b3  mov     rax, [rbp+70h+arg_48]
0x1400011ba  mov     [rbp+70h+var_B0], rdx
0x1400011be  mov     [rbp+70h+var_A8], r9d
0x1400011c2  mov     [rbp+70h+var_A4], ebx
0x1400011c5  mov     rdx, [rax]
0x1400011c8  mov     [rbp+70h+var_B8], 4
0x1400011d0  test    rdx, rdx
0x1400011d3  jz      short loc_1400011E4
0x1400011d5  mov     rax, rcx
0x1400011d8  inc     rax
0x1400011db  cmp     [rdx+rax], bl
0x1400011de  jnz     short loc_1400011D8
0x1400011e0  inc     eax
0x1400011e2  jmp     short loc_1400011EA
0x1400011e4  mov     rdx, rdi
0x1400011e7  mov     eax, r8d
0x1400011ea  mov     [rbp+70h+var_C8], eax
0x1400011ed  mov     rax, [rbp+70h+arg_40]
0x1400011f4  mov     [rbp+70h+var_E0], rax
0x1400011f8  mov     rax, [rbp+70h+arg_38]
0x1400011ff  mov     [rbp+70h+var_D0], rdx
0x140001203  mov     [rbp+70h+var_C4], ebx
0x140001206  mov     [rbp+70h+var_D8], 4
0x14000120e  mov     rdx, [rax]
0x140001211  test    rdx, rdx
0x140001214  jz      short loc_140001224
0x140001216  inc     rcx
0x140001219  cmp     [rdx+rcx], bl
0x14000121c  jnz     short loc_140001216
0x14000121e  lea     r8d, [rcx+1]
0x140001222  jmp     short loc_140001227
0x140001224  mov     rdx, rdi
0x140001227  mov     rax, [rbp+70h+arg_30]
0x14000122e  xor     r9d, r9d
0x140001231  mov     [rsp+170h+var_100], rax
0x140001236  mov     rcx, r10
0x140001239  mov     rax, [rbp+70h+arg_28]
0x140001240  mov     [rsp+170h+var_110], rax
0x140001245  mov     rax, [rbp+70h+arg_20]
0x14000124c  mov     [rsp+170h+var_120], rax
0x140001251  lea     rax, [rsp+170h+var_140]
0x140001256  mov     [rbp+70h+var_F0], rdx
0x14000125a  mov     rdx, r11
0x14000125d  mov     [rbp+70h+var_E8], r8d
0x140001261  xor     r8d, r8d
0x140001264  mov     [rsp+170h+var_148], rax
0x140001269  mov     [rsp+170h+var_150], 12h
0x140001271  mov     [rbp+70h+var_E4], ebx
0x140001274  mov     [rsp+170h+var_F8], 4
0x14000127d  mov     [rsp+170h+var_108], 8
0x140001286  mov     [rsp+170h+var_118], 8
0x14000128f  call    _tlgWriteTransfer_EventWriteTransfer
0x140001294  mov     rcx, [rbp+70h+var_20]
0x140001298  xor     rcx, rsp; StackCookie
0x14000129b  call    __security_check_cookie
0x1400012a0  mov     rbx, [rsp+170h+arg_10]
0x1400012a8  add     rsp, 160h
0x1400012af  pop     rdi
0x1400012b0  pop     rsi
0x1400012b1  pop     rbp
0x1400012b2  retn
```
