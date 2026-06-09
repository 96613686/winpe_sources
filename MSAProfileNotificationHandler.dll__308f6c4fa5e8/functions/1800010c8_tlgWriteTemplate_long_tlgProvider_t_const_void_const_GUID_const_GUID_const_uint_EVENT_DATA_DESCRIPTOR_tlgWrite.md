# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800010c8`
- end: `0x180001373`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005ad4`

## callees

- `0x1800010c8`
- `0x1800016fc`
- `0x180001cb0`

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
    v24 = &dword_18000DE4C;
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
    v28 = &byte_18000DE48;
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
    v31 = &dword_18000DE4C;
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
    v34 = &byte_18000DE48;
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
    v37 = &byte_18000DE48;
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
    v40 = &dword_18000DE4C;
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
    v42 = &byte_18000DE48;
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
    v45 = &byte_18000DE48;
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
0x1800010c8  mov     [rsp-8+arg_10], rbx
0x1800010cd  push    rbp
0x1800010ce  push    rsi
0x1800010cf  push    rdi
0x1800010d0  lea     rbp, [rsp-60h]
0x1800010d5  sub     rsp, 160h
0x1800010dc  mov     rax, cs:__security_cookie
0x1800010e3  xor     rax, rsp
0x1800010e6  mov     [rbp+70h+var_20], rax
0x1800010ea  mov     rax, [rbp+70h+arg_98]
0x1800010f1  mov     r11, rdx
0x1800010f4  mov     r10, rcx
0x1800010f7  xor     ebx, ebx
0x1800010f9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800010fd  mov     r9d, 2
0x180001103  mov     rdx, [rax]
0x180001106  test    rdx, rdx
0x180001109  jz      short loc_180001120
0x18000110b  mov     rax, rcx
0x18000110e  inc     rax
0x180001111  cmp     [rdx+rax*2], bx
0x180001115  jnz     short loc_18000110E
0x180001117  lea     eax, ds:2[rax*2]
0x18000111e  jmp     short loc_18000112A
0x180001120  lea     rdx, dword_18000DE4C
0x180001127  mov     eax, r9d
0x18000112a  mov     [rbp+70h+var_28], eax
0x18000112d  lea     rdi, byte_18000DE48
0x180001134  mov     rax, [rbp+70h+arg_90]
0x18000113b  mov     r8d, 1
0x180001141  mov     [rbp+70h+var_30], rdx
0x180001145  mov     [rbp+70h+var_24], ebx
0x180001148  mov     rdx, [rax]
0x18000114b  test    rdx, rdx
0x18000114e  jz      short loc_18000115F
0x180001150  mov     rax, rcx
0x180001153  inc     rax
0x180001156  cmp     [rdx+rax], bl
0x180001159  jnz     short loc_180001153
0x18000115b  inc     eax
0x18000115d  jmp     short loc_180001165
0x18000115f  mov     rdx, rdi
0x180001162  mov     eax, r8d
0x180001165  mov     [rbp+70h+var_38], eax
0x180001168  mov     rax, [rbp+70h+arg_88]
0x18000116f  mov     [rbp+70h+var_50], rax
0x180001173  mov     rax, [rbp+70h+arg_80]
0x18000117a  mov     [rbp+70h+var_40], rdx
0x18000117e  mov     [rbp+70h+var_34], ebx
0x180001181  mov     [rbp+70h+var_48], 4
0x180001189  mov     rdx, [rax]
0x18000118c  test    rdx, rdx
0x18000118f  jz      short loc_1800011A6
0x180001191  mov     rax, rcx
0x180001194  inc     rax
0x180001197  cmp     [rdx+rax*2], bx
0x18000119b  jnz     short loc_180001194
0x18000119d  lea     eax, ds:2[rax*2]
0x1800011a4  jmp     short loc_1800011B0
0x1800011a6  lea     rdx, dword_18000DE4C
0x1800011ad  mov     eax, r9d
0x1800011b0  mov     [rbp+70h+var_58], eax
0x1800011b3  mov     rax, [rbp+70h+arg_78]
0x1800011ba  mov     [rbp+70h+var_60], rdx
0x1800011be  mov     [rbp+70h+var_54], ebx
0x1800011c1  mov     rdx, [rax]
0x1800011c4  test    rdx, rdx
0x1800011c7  jz      short loc_1800011D8
0x1800011c9  mov     rax, rcx
0x1800011cc  inc     rax
0x1800011cf  cmp     [rdx+rax], bl
0x1800011d2  jnz     short loc_1800011CC
0x1800011d4  inc     eax
0x1800011d6  jmp     short loc_1800011DE
0x1800011d8  mov     rdx, rdi
0x1800011db  mov     eax, r8d
0x1800011de  mov     [rbp+70h+var_68], eax
0x1800011e1  mov     rax, [rbp+70h+arg_70]
0x1800011e8  mov     [rbp+70h+var_80], rax
0x1800011ec  mov     rax, [rbp+70h+arg_68]
0x1800011f3  mov     [rbp+70h+var_70], rdx
0x1800011f7  mov     [rbp+70h+var_64], ebx
0x1800011fa  mov     [rbp+70h+var_78], 4
0x180001202  mov     rdx, [rax]
0x180001205  test    rdx, rdx
0x180001208  jz      short loc_180001219
0x18000120a  mov     rax, rcx
0x18000120d  inc     rax
0x180001210  cmp     [rdx+rax], bl
0x180001213  jnz     short loc_18000120D
0x180001215  inc     eax
0x180001217  jmp     short loc_18000121F
0x180001219  mov     rdx, rdi
0x18000121c  mov     eax, r8d
0x18000121f  mov     [rbp+70h+var_88], eax
0x180001222  mov     rax, [rbp+70h+arg_60]
0x180001229  mov     [rbp+70h+var_A0], rax
0x18000122d  mov     rax, [rbp+70h+arg_58]
0x180001234  mov     [rbp+70h+var_90], rdx
0x180001238  mov     [rbp+70h+var_84], ebx
0x18000123b  mov     [rbp+70h+var_98], 4
0x180001243  mov     rdx, [rax]
0x180001246  test    rdx, rdx
0x180001249  jz      short loc_180001261
0x18000124b  mov     rax, rcx
0x18000124e  inc     rax
0x180001251  cmp     [rdx+rax*2], bx
0x180001255  jnz     short loc_18000124E
0x180001257  lea     r9d, ds:2[rax*2]
0x18000125f  jmp     short loc_180001268
0x180001261  lea     rdx, dword_18000DE4C
0x180001268  mov     rax, [rbp+70h+arg_50]
0x18000126f  mov     [rbp+70h+var_C0], rax
0x180001273  mov     rax, [rbp+70h+arg_48]
0x18000127a  mov     [rbp+70h+var_B0], rdx
0x18000127e  mov     [rbp+70h+var_A8], r9d
0x180001282  mov     [rbp+70h+var_A4], ebx
0x180001285  mov     rdx, [rax]
0x180001288  mov     [rbp+70h+var_B8], 4
0x180001290  test    rdx, rdx
0x180001293  jz      short loc_1800012A4
0x180001295  mov     rax, rcx
0x180001298  inc     rax
0x18000129b  cmp     [rdx+rax], bl
0x18000129e  jnz     short loc_180001298
0x1800012a0  inc     eax
0x1800012a2  jmp     short loc_1800012AA
0x1800012a4  mov     rdx, rdi
0x1800012a7  mov     eax, r8d
0x1800012aa  mov     [rbp+70h+var_C8], eax
0x1800012ad  mov     rax, [rbp+70h+arg_40]
0x1800012b4  mov     [rbp+70h+var_E0], rax
0x1800012b8  mov     rax, [rbp+70h+arg_38]
0x1800012bf  mov     [rbp+70h+var_D0], rdx
0x1800012c3  mov     [rbp+70h+var_C4], ebx
0x1800012c6  mov     [rbp+70h+var_D8], 4
0x1800012ce  mov     rdx, [rax]
0x1800012d1  test    rdx, rdx
0x1800012d4  jz      short loc_1800012E4
0x1800012d6  inc     rcx
0x1800012d9  cmp     [rdx+rcx], bl
0x1800012dc  jnz     short loc_1800012D6
0x1800012de  lea     r8d, [rcx+1]
0x1800012e2  jmp     short loc_1800012E7
0x1800012e4  mov     rdx, rdi
0x1800012e7  mov     rax, [rbp+70h+arg_30]
0x1800012ee  xor     r9d, r9d
0x1800012f1  mov     [rsp+170h+var_100], rax
0x1800012f6  mov     rcx, r10
0x1800012f9  mov     rax, [rbp+70h+arg_28]
0x180001300  mov     [rsp+170h+var_110], rax
0x180001305  mov     rax, [rbp+70h+arg_20]
0x18000130c  mov     [rsp+170h+var_120], rax
0x180001311  lea     rax, [rsp+170h+var_140]
0x180001316  mov     [rbp+70h+var_F0], rdx
0x18000131a  mov     rdx, r11
0x18000131d  mov     [rbp+70h+var_E8], r8d
0x180001321  xor     r8d, r8d
0x180001324  mov     [rsp+170h+var_148], rax
0x180001329  mov     [rsp+170h+var_150], 12h
0x180001331  mov     [rbp+70h+var_E4], ebx
0x180001334  mov     [rsp+170h+var_F8], 4
0x18000133d  mov     [rsp+170h+var_108], 8
0x180001346  mov     [rsp+170h+var_118], 8
0x18000134f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001354  mov     rcx, [rbp+70h+var_20]
0x180001358  xor     rcx, rsp; StackCookie
0x18000135b  call    __security_check_cookie
0x180001360  mov     rbx, [rsp+170h+arg_10]
0x180001368  add     rsp, 160h
0x18000136f  pop     rdi
0x180001370  pop     rsi
0x180001371  pop     rbp
0x180001372  retn
```
