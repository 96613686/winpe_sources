# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000117c`
- end: `0x180001429`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `685`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b804`
- `0x18000ce20`

## callees

- `0x18000117c`
- `0x180001a4c`
- `0x180002300`

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
  __int64 v22; // rdx
  int v24; // r9d
  int *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // r8d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  int *v41; // rcx
  __int64 v42; // rax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rcx
  _BYTE v48[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h]
  __int64 v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v55; // [rsp+80h] [rbp-80h]
  int v56; // [rsp+88h] [rbp-78h]
  int v57; // [rsp+8Ch] [rbp-74h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  int *v65; // [rsp+C0h] [rbp-40h]
  int v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+CCh] [rbp-34h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  int *v78; // [rsp+110h] [rbp+10h]
  int v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+11Ch] [rbp+1Ch]
  __int64 v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  int *v86; // [rsp+140h] [rbp+40h]
  int v87; // [rsp+148h] [rbp+48h]
  int v88; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v24 = 2;
  v25 = *a20;
  if ( *a20 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *((_WORD *)v25 + v26) );
    v27 = 2 * v26 + 2;
  }
  else
  {
    v25 = &dword_180013CCC;
    v27 = 2;
  }
  v87 = v27;
  v28 = 1;
  v86 = v25;
  v88 = 0;
  v29 = *a19;
  if ( *a19 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &byte_180013CC8;
    v31 = 1;
  }
  v84 = v31;
  v81 = a18;
  v83 = v29;
  v85 = 0;
  v82 = 4;
  v32 = *a17;
  if ( *a17 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &dword_180013CCC;
    v34 = 2;
  }
  v79 = v34;
  v78 = v32;
  v80 = 0;
  v35 = *a16;
  if ( *a16 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &byte_180013CC8;
    v37 = 1;
  }
  v76 = v37;
  v73 = a15;
  v75 = v35;
  v77 = 0;
  v74 = 4;
  v38 = *a14;
  if ( *a14 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &byte_180013CC8;
    v40 = 1;
  }
  v71 = v40;
  v68 = a13;
  v70 = v38;
  v72 = 0;
  v69 = 4;
  v41 = *a12;
  if ( *a12 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_WORD *)v41 + v42) );
    v24 = 2 * v42 + 2;
  }
  else
  {
    v41 = &dword_180013CCC;
  }
  v63 = a11;
  v65 = v41;
  v66 = v24;
  v67 = 0;
  v43 = *a10;
  v64 = 4;
  if ( v43 )
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
  v61 = v45;
  v58 = a9;
  v60 = v43;
  v62 = 0;
  v59 = 4;
  v46 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v46 + v22) );
    v28 = v22 + 1;
  }
  else
  {
    v46 = &byte_180013CC8;
  }
  v53 = a7;
  v51 = a6;
  v49 = a5;
  v55 = v46;
  v56 = v28;
  v57 = 0;
  v54 = 4;
  v52 = 8;
  v50 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 18, v48);
}

```

## disassembly

```asm
0x18000117c  push    rbp
0x18000117e  push    rbx
0x18000117f  push    rsi
0x180001180  push    rdi
0x180001181  push    r14
0x180001183  lea     rbp, [rsp-60h]
0x180001188  sub     rsp, 160h
0x18000118f  mov     rax, cs:__security_cookie
0x180001196  xor     rax, rsp
0x180001199  mov     [rbp+80h+var_30], rax
0x18000119d  mov     rax, [rbp+80h+arg_98]
0x1800011a4  mov     r11, rdx
0x1800011a7  mov     r10, rcx
0x1800011aa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800011ae  xor     edi, edi
0x1800011b0  mov     rbx, r8
0x1800011b3  mov     r9d, 2
0x1800011b9  mov     rcx, [rax]
0x1800011bc  test    rcx, rcx
0x1800011bf  jz      short loc_1800011D6
0x1800011c1  mov     rax, rdx
0x1800011c4  inc     rax
0x1800011c7  cmp     [rcx+rax*2], di
0x1800011cb  jnz     short loc_1800011C4
0x1800011cd  lea     eax, ds:2[rax*2]
0x1800011d4  jmp     short loc_1800011E0
0x1800011d6  lea     rcx, dword_180013CCC
0x1800011dd  mov     eax, r9d
0x1800011e0  mov     [rbp+80h+var_38], eax
0x1800011e3  lea     rsi, byte_180013CC8
0x1800011ea  mov     rax, [rbp+80h+arg_90]
0x1800011f1  mov     r8d, 1
0x1800011f7  mov     [rbp+80h+var_40], rcx
0x1800011fb  mov     [rbp+80h+var_34], edi
0x1800011fe  mov     rcx, [rax]
0x180001201  test    rcx, rcx
0x180001204  jz      short loc_180001216
0x180001206  mov     rax, rdx
0x180001209  inc     rax
0x18000120c  cmp     [rcx+rax], dil
0x180001210  jnz     short loc_180001209
0x180001212  inc     eax
0x180001214  jmp     short loc_18000121C
0x180001216  mov     rcx, rsi
0x180001219  mov     eax, r8d
0x18000121c  mov     [rbp+80h+var_48], eax
0x18000121f  mov     rax, [rbp+80h+arg_88]
0x180001226  mov     [rbp+80h+var_60], rax
0x18000122a  mov     rax, [rbp+80h+arg_80]
0x180001231  mov     [rbp+80h+var_50], rcx
0x180001235  mov     [rbp+80h+var_44], edi
0x180001238  mov     [rbp+80h+var_58], 4
0x180001240  mov     rcx, [rax]
0x180001243  test    rcx, rcx
0x180001246  jz      short loc_18000125D
0x180001248  mov     rax, rdx
0x18000124b  inc     rax
0x18000124e  cmp     [rcx+rax*2], di
0x180001252  jnz     short loc_18000124B
0x180001254  lea     eax, ds:2[rax*2]
0x18000125b  jmp     short loc_180001267
0x18000125d  lea     rcx, dword_180013CCC
0x180001264  mov     eax, r9d
0x180001267  mov     [rbp+80h+var_68], eax
0x18000126a  mov     rax, [rbp+80h+arg_78]
0x180001271  mov     [rbp+80h+var_70], rcx
0x180001275  mov     [rbp+80h+var_64], edi
0x180001278  mov     rcx, [rax]
0x18000127b  test    rcx, rcx
0x18000127e  jz      short loc_180001290
0x180001280  mov     rax, rdx
0x180001283  inc     rax
0x180001286  cmp     [rcx+rax], dil
0x18000128a  jnz     short loc_180001283
0x18000128c  inc     eax
0x18000128e  jmp     short loc_180001296
0x180001290  mov     rcx, rsi
0x180001293  mov     eax, r8d
0x180001296  mov     [rbp+80h+var_78], eax
0x180001299  mov     rax, [rbp+80h+arg_70]
0x1800012a0  mov     [rbp+80h+var_90], rax
0x1800012a4  mov     rax, [rbp+80h+arg_68]
0x1800012ab  mov     [rbp+80h+var_80], rcx
0x1800012af  mov     [rbp+80h+var_74], edi
0x1800012b2  mov     [rbp+80h+var_88], 4
0x1800012ba  mov     rcx, [rax]
0x1800012bd  test    rcx, rcx
0x1800012c0  jz      short loc_1800012D2
0x1800012c2  mov     rax, rdx
0x1800012c5  inc     rax
0x1800012c8  cmp     [rcx+rax], dil
0x1800012cc  jnz     short loc_1800012C5
0x1800012ce  inc     eax
0x1800012d0  jmp     short loc_1800012D8
0x1800012d2  mov     rcx, rsi
0x1800012d5  mov     eax, r8d
0x1800012d8  mov     [rbp+80h+var_98], eax
0x1800012db  mov     rax, [rbp+80h+arg_60]
0x1800012e2  mov     [rbp+80h+var_B0], rax
0x1800012e6  mov     rax, [rbp+80h+arg_58]
0x1800012ed  mov     [rbp+80h+var_A0], rcx
0x1800012f1  mov     [rbp+80h+var_94], edi
0x1800012f4  mov     [rbp+80h+var_A8], 4
0x1800012fc  mov     rcx, [rax]
0x1800012ff  test    rcx, rcx
0x180001302  jz      short loc_18000131A
0x180001304  mov     rax, rdx
0x180001307  inc     rax
0x18000130a  cmp     [rcx+rax*2], di
0x18000130e  jnz     short loc_180001307
0x180001310  lea     r9d, ds:2[rax*2]
0x180001318  jmp     short loc_180001321
0x18000131a  lea     rcx, dword_180013CCC
0x180001321  mov     rax, [rbp+80h+arg_50]
0x180001328  mov     [rbp+80h+var_D0], rax
0x18000132c  mov     rax, [rbp+80h+arg_48]
0x180001333  mov     [rbp+80h+var_C0], rcx
0x180001337  mov     [rbp+80h+var_B8], r9d
0x18000133b  mov     [rbp+80h+var_B4], edi
0x18000133e  mov     rcx, [rax]
0x180001341  mov     [rbp+80h+var_C8], 4
0x180001349  test    rcx, rcx
0x18000134c  jz      short loc_18000135E
0x18000134e  mov     rax, rdx
0x180001351  inc     rax
0x180001354  cmp     [rcx+rax], dil
0x180001358  jnz     short loc_180001351
0x18000135a  inc     eax
0x18000135c  jmp     short loc_180001364
0x18000135e  mov     rcx, rsi
0x180001361  mov     eax, r8d
0x180001364  mov     [rbp+80h+var_D8], eax
0x180001367  mov     rax, [rbp+80h+arg_40]
0x18000136e  mov     [rbp+80h+var_F0], rax
0x180001372  mov     rax, [rbp+80h+arg_38]
0x180001379  mov     [rbp+80h+var_E0], rcx
0x18000137d  mov     [rbp+80h+var_D4], edi
0x180001380  mov     [rbp+80h+var_E8], 4
0x180001388  mov     rcx, [rax]
0x18000138b  test    rcx, rcx
0x18000138e  jz      short loc_18000139F
0x180001390  inc     rdx
0x180001393  cmp     [rcx+rdx], dil
0x180001397  jnz     short loc_180001390
0x180001399  lea     r8d, [rdx+1]
0x18000139d  jmp     short loc_1800013A2
0x18000139f  mov     rcx, rsi
0x1800013a2  mov     rax, [rbp+80h+arg_30]
0x1800013a9  xor     r9d, r9d
0x1800013ac  mov     [rsp+180h+var_110], rax
0x1800013b1  mov     rdx, r11
0x1800013b4  mov     rax, [rbp+80h+arg_28]
0x1800013bb  mov     [rsp+180h+var_120], rax
0x1800013c0  mov     rax, [rbp+80h+arg_20]
0x1800013c7  mov     [rsp+180h+var_130], rax
0x1800013cc  lea     rax, [rsp+180h+var_150]
0x1800013d1  mov     [rbp+80h+var_100], rcx
0x1800013d5  mov     rcx, r10
0x1800013d8  mov     [rbp+80h+var_F8], r8d
0x1800013dc  mov     r8, rbx
0x1800013df  mov     [rsp+180h+var_158], rax
0x1800013e4  mov     [rsp+180h+var_160], 12h
0x1800013ec  mov     [rbp+80h+var_F4], edi
0x1800013ef  mov     [rsp+180h+var_108], 4
0x1800013f8  mov     [rsp+180h+var_118], 8
0x180001401  mov     [rsp+180h+var_128], 8
0x18000140a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000140f  mov     rcx, [rbp+80h+var_30]
0x180001413  xor     rcx, rsp; StackCookie
0x180001416  call    __security_check_cookie
0x18000141b  add     rsp, 160h
0x180001422  pop     r14
0x180001424  pop     rdi
0x180001425  pop     rsi
0x180001426  pop     rbx
0x180001427  pop     rbp
0x180001428  retn
```
