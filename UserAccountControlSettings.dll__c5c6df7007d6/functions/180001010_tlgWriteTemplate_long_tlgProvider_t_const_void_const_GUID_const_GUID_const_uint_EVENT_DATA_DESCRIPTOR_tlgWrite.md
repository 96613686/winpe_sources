# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001010`
- end: `0x1800012d4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `708`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007d78`

## callees

- `0x180001010`
- `0x180001758`
- `0x18000b710`

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
  __int64 v20; // r8
  __int64 *v21; // rax
  __int64 v22; // r9
  bool v23; // zf
  int v24; // r9d
  int v25; // r10d
  int v26; // r11d
  const unsigned __int16 *v27; // r9
  __int64 v28; // rax
  int v29; // eax
  __int64 *v30; // r9
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // r9
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // r9
  __int64 v37; // rax
  int v38; // eax
  __int64 *v39; // r9
  __int64 v40; // rax
  const unsigned __int16 *v41; // r9
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // r9
  _BYTE v46[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B0h]
  __int64 v48; // [rsp+58h] [rbp-A8h]
  __int64 v49; // [rsp+60h] [rbp-A0h]
  __int64 v50; // [rsp+68h] [rbp-98h]
  __int64 v51; // [rsp+70h] [rbp-90h]
  __int64 v52; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v53; // [rsp+80h] [rbp-80h]
  int v54; // [rsp+88h] [rbp-78h]
  int v55; // [rsp+8Ch] [rbp-74h]
  __int64 v56; // [rsp+90h] [rbp-70h]
  __int64 v57; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v58; // [rsp+A0h] [rbp-60h]
  int v59; // [rsp+A8h] [rbp-58h]
  int v60; // [rsp+ACh] [rbp-54h]
  __int64 v61; // [rsp+B0h] [rbp-50h]
  __int64 v62; // [rsp+B8h] [rbp-48h]
  __int64 *v63; // [rsp+C0h] [rbp-40h]
  int v64; // [rsp+C8h] [rbp-38h]
  int v65; // [rsp+CCh] [rbp-34h]
  __int64 v66; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v68; // [rsp+E0h] [rbp-20h]
  int v69; // [rsp+E8h] [rbp-18h]
  int v70; // [rsp+ECh] [rbp-14h]
  __int64 v71; // [rsp+F0h] [rbp-10h]
  __int64 v72; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v73; // [rsp+100h] [rbp+0h]
  int v74; // [rsp+108h] [rbp+8h]
  int v75; // [rsp+10Ch] [rbp+Ch]
  __int64 *v76; // [rsp+110h] [rbp+10h]
  int v77; // [rsp+118h] [rbp+18h]
  int v78; // [rsp+11Ch] [rbp+1Ch]
  __int64 v79; // [rsp+120h] [rbp+20h]
  __int64 v80; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v81; // [rsp+130h] [rbp+30h]
  int v82; // [rsp+138h] [rbp+38h]
  int v83; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v84; // [rsp+140h] [rbp+40h]
  int v85; // [rsp+148h] [rbp+48h]
  int v86; // [rsp+14Ch] [rbp+4Ch]

  v20 = -1;
  v21 = *a20;
  if ( *a20 )
  {
    v22 = -1;
    do
      v23 = *((_WORD *)v21 + ++v22) == 0;
    while ( !v23 );
    v24 = 2 * v22 + 2;
    v25 = 2;
  }
  else
  {
    v25 = 2;
    v21 = &qword_18000F0A0;
    v24 = 2;
  }
  v84 = v21;
  v26 = 1;
  v85 = v24;
  v86 = 0;
  v27 = *a19;
  if ( *a19 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &dword_18000ECFC;
    v29 = 1;
  }
  v82 = v29;
  v79 = a18;
  v81 = v27;
  v83 = 0;
  v80 = 4;
  v30 = *a17;
  if ( *a17 )
  {
    v31 = -1;
    do
      v23 = *((_WORD *)v30 + ++v31) == 0;
    while ( !v23 );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &qword_18000F0A0;
    v32 = 2;
  }
  v77 = v32;
  v76 = v30;
  v78 = 0;
  v33 = *a16;
  if ( *a16 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &dword_18000ECFC;
    v35 = 1;
  }
  v74 = v35;
  v71 = a15;
  v73 = v33;
  v75 = 0;
  v72 = 4;
  v36 = *a14;
  if ( *a14 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &dword_18000ECFC;
    v38 = 1;
  }
  v69 = v38;
  v66 = a13;
  v68 = v36;
  v70 = 0;
  v67 = 4;
  v39 = *a12;
  if ( *a12 )
  {
    v40 = -1;
    do
      v23 = *((_WORD *)v39 + ++v40) == 0;
    while ( !v23 );
    v25 = 2 * v40 + 2;
  }
  else
  {
    v39 = &qword_18000F0A0;
  }
  v61 = a11;
  v63 = v39;
  v64 = v25;
  v65 = 0;
  v41 = *a10;
  v62 = 4;
  if ( v41 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &dword_18000ECFC;
    v43 = 1;
  }
  v59 = v43;
  v56 = a9;
  v58 = v41;
  v60 = 0;
  v57 = 4;
  v44 = *a8;
  if ( *a8 )
  {
    do
      v23 = *((_BYTE *)v44 + ++v20) == 0;
    while ( !v23 );
    v26 = v20 + 1;
  }
  else
  {
    v44 = &dword_18000ECFC;
  }
  v51 = a7;
  v49 = a6;
  v47 = a5;
  v53 = v44;
  v54 = v26;
  v55 = 0;
  v52 = 4;
  v50 = 8;
  v48 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 18, v46);
}

```

## disassembly

```asm
0x180001010  mov     [rsp-8+arg_10], rbx
0x180001015  push    rbp
0x180001016  lea     rbp, [rsp-60h]
0x18000101b  sub     rsp, 160h
0x180001022  mov     rax, cs:__security_cookie
0x180001029  xor     rax, rsp
0x18000102c  mov     [rbp+60h+var_10], rax
0x180001030  mov     rax, [rbp+60h+arg_98]
0x180001037  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000103e  mov     rax, [rax]
0x180001041  test    rax, rax
0x180001044  jz      short loc_180001066
0x180001046  mov     r9, r8
0x180001049  cmp     word ptr [rax+r9*2+2], 0
0x180001050  lea     r9, [r9+1]
0x180001054  jnz     short loc_180001049
0x180001056  lea     r9d, ds:2[r9*2]
0x18000105e  mov     r10d, 2
0x180001064  jmp     short loc_180001076
0x180001066  mov     r10d, 2
0x18000106c  lea     rax, qword_18000F0A0
0x180001073  mov     r9d, r10d
0x180001076  xor     ebx, ebx
0x180001078  mov     [rbp+60h+var_20], rax
0x18000107c  mov     rax, [rbp+60h+arg_90]
0x180001083  mov     r11d, 1
0x180001089  mov     [rbp+60h+var_18], r9d
0x18000108d  mov     [rbp+60h+var_14], ebx
0x180001090  mov     r9, [rax]
0x180001093  test    r9, r9
0x180001096  jz      short loc_1800010A8
0x180001098  mov     rax, r8
0x18000109b  inc     rax
0x18000109e  cmp     [r9+rax], bl
0x1800010a2  jnz     short loc_18000109B
0x1800010a4  inc     eax
0x1800010a6  jmp     short loc_1800010B2
0x1800010a8  lea     r9, dword_18000ECFC
0x1800010af  mov     eax, r11d
0x1800010b2  mov     [rbp+60h+var_28], eax
0x1800010b5  mov     rax, [rbp+60h+arg_88]
0x1800010bc  mov     [rbp+60h+var_40], rax
0x1800010c0  mov     rax, [rbp+60h+arg_80]
0x1800010c7  mov     [rbp+60h+var_30], r9
0x1800010cb  mov     [rbp+60h+var_24], ebx
0x1800010ce  mov     [rbp+60h+var_38], 4
0x1800010d6  mov     r9, [rax]
0x1800010d9  test    r9, r9
0x1800010dc  jz      short loc_1800010F6
0x1800010de  mov     rax, r8
0x1800010e1  cmp     [r9+rax*2+2], bx
0x1800010e7  lea     rax, [rax+1]
0x1800010eb  jnz     short loc_1800010E1
0x1800010ed  lea     eax, ds:2[rax*2]
0x1800010f4  jmp     short loc_180001100
0x1800010f6  lea     r9, qword_18000F0A0
0x1800010fd  mov     eax, r10d
0x180001100  mov     [rbp+60h+var_48], eax
0x180001103  mov     rax, [rbp+60h+arg_78]
0x18000110a  mov     [rbp+60h+var_50], r9
0x18000110e  mov     [rbp+60h+var_44], ebx
0x180001111  mov     r9, [rax]
0x180001114  test    r9, r9
0x180001117  jz      short loc_180001129
0x180001119  mov     rax, r8
0x18000111c  inc     rax
0x18000111f  cmp     [r9+rax], bl
0x180001123  jnz     short loc_18000111C
0x180001125  inc     eax
0x180001127  jmp     short loc_180001133
0x180001129  lea     r9, dword_18000ECFC
0x180001130  mov     eax, r11d
0x180001133  mov     [rbp+60h+var_58], eax
0x180001136  mov     rax, [rbp+60h+arg_70]
0x18000113d  mov     [rbp+60h+var_70], rax
0x180001141  mov     rax, [rbp+60h+arg_68]
0x180001148  mov     [rbp+60h+var_60], r9
0x18000114c  mov     [rbp+60h+var_54], ebx
0x18000114f  mov     [rbp+60h+var_68], 4
0x180001157  mov     r9, [rax]
0x18000115a  test    r9, r9
0x18000115d  jz      short loc_18000116F
0x18000115f  mov     rax, r8
0x180001162  inc     rax
0x180001165  cmp     [r9+rax], bl
0x180001169  jnz     short loc_180001162
0x18000116b  inc     eax
0x18000116d  jmp     short loc_180001179
0x18000116f  lea     r9, dword_18000ECFC
0x180001176  mov     eax, r11d
0x180001179  mov     [rbp+60h+var_78], eax
0x18000117c  mov     rax, [rbp+60h+arg_60]
0x180001183  mov     [rbp+60h+var_90], rax
0x180001187  mov     rax, [rbp+60h+arg_58]
0x18000118e  mov     [rbp+60h+var_80], r9
0x180001192  mov     [rbp+60h+var_74], ebx
0x180001195  mov     [rbp+60h+var_88], 4
0x18000119d  mov     r9, [rax]
0x1800011a0  test    r9, r9
0x1800011a3  jz      short loc_1800011BE
0x1800011a5  mov     rax, r8
0x1800011a8  cmp     [r9+rax*2+2], bx
0x1800011ae  lea     rax, [rax+1]
0x1800011b2  jnz     short loc_1800011A8
0x1800011b4  lea     r10d, ds:2[rax*2]
0x1800011bc  jmp     short loc_1800011C5
0x1800011be  lea     r9, qword_18000F0A0
0x1800011c5  mov     rax, [rbp+60h+arg_50]
0x1800011cc  mov     [rbp+60h+var_B0], rax
0x1800011d0  mov     rax, [rbp+60h+arg_48]
0x1800011d7  mov     [rbp+60h+var_A0], r9
0x1800011db  mov     [rbp+60h+var_98], r10d
0x1800011df  mov     [rbp+60h+var_94], ebx
0x1800011e2  mov     r9, [rax]
0x1800011e5  mov     [rbp+60h+var_A8], 4
0x1800011ed  test    r9, r9
0x1800011f0  jz      short loc_180001202
0x1800011f2  mov     rax, r8
0x1800011f5  inc     rax
0x1800011f8  cmp     [r9+rax], bl
0x1800011fc  jnz     short loc_1800011F5
0x1800011fe  inc     eax
0x180001200  jmp     short loc_18000120C
0x180001202  lea     r9, dword_18000ECFC
0x180001209  mov     eax, r11d
0x18000120c  mov     [rbp+60h+var_B8], eax
0x18000120f  mov     rax, [rbp+60h+arg_40]
0x180001216  mov     [rbp+60h+var_D0], rax
0x18000121a  mov     rax, [rbp+60h+arg_38]
0x180001221  mov     [rbp+60h+var_C0], r9
0x180001225  mov     [rbp+60h+var_B4], ebx
0x180001228  mov     [rbp+60h+var_C8], 4
0x180001230  mov     r9, [rax]
0x180001233  test    r9, r9
0x180001236  jz      short loc_180001249
0x180001238  cmp     [r9+r8+1], bl
0x18000123d  lea     r8, [r8+1]
0x180001241  jnz     short loc_180001238
0x180001243  lea     r11d, [r8+1]
0x180001247  jmp     short loc_180001250
0x180001249  lea     r9, dword_18000ECFC
0x180001250  mov     rax, [rbp+60h+arg_30]
0x180001257  xor     r8d, r8d
0x18000125a  mov     [rsp+160h+var_F0], rax
0x18000125f  mov     rax, [rbp+60h+arg_28]
0x180001266  mov     [rsp+160h+var_100], rax
0x18000126b  mov     rax, [rbp+60h+arg_20]
0x180001272  mov     [rsp+160h+var_110], rax
0x180001277  lea     rax, [rsp+160h+var_130]
0x18000127c  mov     [rbp+60h+var_E0], r9
0x180001280  xor     r9d, r9d
0x180001283  mov     [rsp+160h+var_138], rax
0x180001288  mov     [rsp+160h+var_140], 12h
0x180001290  mov     [rbp+60h+var_D8], r11d
0x180001294  mov     [rbp+60h+var_D4], ebx
0x180001297  mov     [rsp+160h+var_E8], 4
0x1800012a0  mov     [rsp+160h+var_F8], 8
0x1800012a9  mov     [rsp+160h+var_108], 8
0x1800012b2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012b7  mov     rcx, [rbp+60h+var_10]
0x1800012bb  xor     rcx, rsp; StackCookie
0x1800012be  call    __security_check_cookie
0x1800012c3  mov     rbx, [rsp+160h+arg_10]
0x1800012cb  add     rsp, 160h
0x1800012d2  pop     rbp
0x1800012d3  retn
```
