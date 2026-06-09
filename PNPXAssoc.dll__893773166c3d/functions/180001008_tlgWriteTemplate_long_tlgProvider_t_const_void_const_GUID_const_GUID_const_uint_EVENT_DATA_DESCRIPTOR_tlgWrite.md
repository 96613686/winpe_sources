# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x1800012b3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b014`

## callees

- `0x180001008`
- `0x18000163c`
- `0x180012e00`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
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
        __int64 **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  __int64 *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  __int64 *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  __int64 *v40; // rdx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
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
  __int64 *v64; // [rsp+C0h] [rbp-40h]
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
  __int64 *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v85; // [rsp+140h] [rbp+40h]
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
    v24 = &qword_1800166A0;
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
    v28 = &word_180016326;
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
    v31 = &qword_1800166A0;
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
    v34 = &word_180016326;
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
    v37 = &word_180016326;
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
    v40 = &qword_1800166A0;
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
    v42 = &word_180016326;
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
    v45 = &word_180016326;
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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x12u, &v47);
}

```

## disassembly

```asm
0x180001008  mov     [rsp-8+arg_10], rbx
0x18000100d  push    rbp
0x18000100e  push    rsi
0x18000100f  push    rdi
0x180001010  lea     rbp, [rsp-60h]
0x180001015  sub     rsp, 160h
0x18000101c  mov     rax, cs:__security_cookie
0x180001023  xor     rax, rsp
0x180001026  mov     [rbp+70h+var_20], rax
0x18000102a  mov     rax, [rbp+70h+arg_98]
0x180001031  mov     r11, rdx
0x180001034  mov     r10, rcx
0x180001037  xor     ebx, ebx
0x180001039  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000103d  mov     r9d, 2
0x180001043  mov     rdx, [rax]
0x180001046  test    rdx, rdx
0x180001049  jz      short loc_180001060
0x18000104b  mov     rax, rcx
0x18000104e  inc     rax
0x180001051  cmp     [rdx+rax*2], bx
0x180001055  jnz     short loc_18000104E
0x180001057  lea     eax, ds:2[rax*2]
0x18000105e  jmp     short loc_18000106A
0x180001060  lea     rdx, qword_1800166A0
0x180001067  mov     eax, r9d
0x18000106a  mov     [rbp+70h+var_28], eax
0x18000106d  lea     rdi, word_180016326
0x180001074  mov     rax, [rbp+70h+arg_90]
0x18000107b  mov     r8d, 1
0x180001081  mov     [rbp+70h+var_30], rdx
0x180001085  mov     [rbp+70h+var_24], ebx
0x180001088  mov     rdx, [rax]
0x18000108b  test    rdx, rdx
0x18000108e  jz      short loc_18000109F
0x180001090  mov     rax, rcx
0x180001093  inc     rax
0x180001096  cmp     [rdx+rax], bl
0x180001099  jnz     short loc_180001093
0x18000109b  inc     eax
0x18000109d  jmp     short loc_1800010A5
0x18000109f  mov     rdx, rdi
0x1800010a2  mov     eax, r8d
0x1800010a5  mov     [rbp+70h+var_38], eax
0x1800010a8  mov     rax, [rbp+70h+arg_88]
0x1800010af  mov     [rbp+70h+var_50], rax
0x1800010b3  mov     rax, [rbp+70h+arg_80]
0x1800010ba  mov     [rbp+70h+var_40], rdx
0x1800010be  mov     [rbp+70h+var_34], ebx
0x1800010c1  mov     [rbp+70h+var_48], 4
0x1800010c9  mov     rdx, [rax]
0x1800010cc  test    rdx, rdx
0x1800010cf  jz      short loc_1800010E6
0x1800010d1  mov     rax, rcx
0x1800010d4  inc     rax
0x1800010d7  cmp     [rdx+rax*2], bx
0x1800010db  jnz     short loc_1800010D4
0x1800010dd  lea     eax, ds:2[rax*2]
0x1800010e4  jmp     short loc_1800010F0
0x1800010e6  lea     rdx, qword_1800166A0
0x1800010ed  mov     eax, r9d
0x1800010f0  mov     [rbp+70h+var_58], eax
0x1800010f3  mov     rax, [rbp+70h+arg_78]
0x1800010fa  mov     [rbp+70h+var_60], rdx
0x1800010fe  mov     [rbp+70h+var_54], ebx
0x180001101  mov     rdx, [rax]
0x180001104  test    rdx, rdx
0x180001107  jz      short loc_180001118
0x180001109  mov     rax, rcx
0x18000110c  inc     rax
0x18000110f  cmp     [rdx+rax], bl
0x180001112  jnz     short loc_18000110C
0x180001114  inc     eax
0x180001116  jmp     short loc_18000111E
0x180001118  mov     rdx, rdi
0x18000111b  mov     eax, r8d
0x18000111e  mov     [rbp+70h+var_68], eax
0x180001121  mov     rax, [rbp+70h+arg_70]
0x180001128  mov     [rbp+70h+var_80], rax
0x18000112c  mov     rax, [rbp+70h+arg_68]
0x180001133  mov     [rbp+70h+var_70], rdx
0x180001137  mov     [rbp+70h+var_64], ebx
0x18000113a  mov     [rbp+70h+var_78], 4
0x180001142  mov     rdx, [rax]
0x180001145  test    rdx, rdx
0x180001148  jz      short loc_180001159
0x18000114a  mov     rax, rcx
0x18000114d  inc     rax
0x180001150  cmp     [rdx+rax], bl
0x180001153  jnz     short loc_18000114D
0x180001155  inc     eax
0x180001157  jmp     short loc_18000115F
0x180001159  mov     rdx, rdi
0x18000115c  mov     eax, r8d
0x18000115f  mov     [rbp+70h+var_88], eax
0x180001162  mov     rax, [rbp+70h+arg_60]
0x180001169  mov     [rbp+70h+var_A0], rax
0x18000116d  mov     rax, [rbp+70h+arg_58]
0x180001174  mov     [rbp+70h+var_90], rdx
0x180001178  mov     [rbp+70h+var_84], ebx
0x18000117b  mov     [rbp+70h+var_98], 4
0x180001183  mov     rdx, [rax]
0x180001186  test    rdx, rdx
0x180001189  jz      short loc_1800011A1
0x18000118b  mov     rax, rcx
0x18000118e  inc     rax
0x180001191  cmp     [rdx+rax*2], bx
0x180001195  jnz     short loc_18000118E
0x180001197  lea     r9d, ds:2[rax*2]
0x18000119f  jmp     short loc_1800011A8
0x1800011a1  lea     rdx, qword_1800166A0
0x1800011a8  mov     rax, [rbp+70h+arg_50]
0x1800011af  mov     [rbp+70h+var_C0], rax
0x1800011b3  mov     rax, [rbp+70h+arg_48]
0x1800011ba  mov     [rbp+70h+var_B0], rdx
0x1800011be  mov     [rbp+70h+var_A8], r9d
0x1800011c2  mov     [rbp+70h+var_A4], ebx
0x1800011c5  mov     rdx, [rax]
0x1800011c8  mov     [rbp+70h+var_B8], 4
0x1800011d0  test    rdx, rdx
0x1800011d3  jz      short loc_1800011E4
0x1800011d5  mov     rax, rcx
0x1800011d8  inc     rax
0x1800011db  cmp     [rdx+rax], bl
0x1800011de  jnz     short loc_1800011D8
0x1800011e0  inc     eax
0x1800011e2  jmp     short loc_1800011EA
0x1800011e4  mov     rdx, rdi
0x1800011e7  mov     eax, r8d
0x1800011ea  mov     [rbp+70h+var_C8], eax
0x1800011ed  mov     rax, [rbp+70h+arg_40]
0x1800011f4  mov     [rbp+70h+var_E0], rax
0x1800011f8  mov     rax, [rbp+70h+arg_38]
0x1800011ff  mov     [rbp+70h+var_D0], rdx
0x180001203  mov     [rbp+70h+var_C4], ebx
0x180001206  mov     [rbp+70h+var_D8], 4
0x18000120e  mov     rdx, [rax]
0x180001211  test    rdx, rdx
0x180001214  jz      short loc_180001224
0x180001216  inc     rcx
0x180001219  cmp     [rdx+rcx], bl
0x18000121c  jnz     short loc_180001216
0x18000121e  lea     r8d, [rcx+1]
0x180001222  jmp     short loc_180001227
0x180001224  mov     rdx, rdi
0x180001227  mov     rax, [rbp+70h+arg_30]
0x18000122e  xor     r9d, r9d
0x180001231  mov     [rsp+170h+var_100], rax
0x180001236  mov     rcx, r10
0x180001239  mov     rax, [rbp+70h+arg_28]
0x180001240  mov     [rsp+170h+var_110], rax
0x180001245  mov     rax, [rbp+70h+arg_20]
0x18000124c  mov     [rsp+170h+var_120], rax
0x180001251  lea     rax, [rsp+170h+var_140]
0x180001256  mov     [rbp+70h+var_F0], rdx
0x18000125a  mov     rdx, r11
0x18000125d  mov     [rbp+70h+var_E8], r8d
0x180001261  xor     r8d, r8d
0x180001264  mov     [rsp+170h+var_148], rax
0x180001269  mov     [rsp+170h+var_150], 12h
0x180001271  mov     [rbp+70h+var_E4], ebx
0x180001274  mov     [rsp+170h+var_F8], 4
0x18000127d  mov     [rsp+170h+var_108], 8
0x180001286  mov     [rsp+170h+var_118], 8
0x18000128f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001294  mov     rcx, [rbp+70h+var_20]
0x180001298  xor     rcx, rsp; StackCookie
0x18000129b  call    __security_check_cookie
0x1800012a0  mov     rbx, [rsp+170h+arg_10]
0x1800012a8  add     rsp, 160h
0x1800012af  pop     rdi
0x1800012b0  pop     rsi
0x1800012b1  pop     rbp
0x1800012b2  retn
```
