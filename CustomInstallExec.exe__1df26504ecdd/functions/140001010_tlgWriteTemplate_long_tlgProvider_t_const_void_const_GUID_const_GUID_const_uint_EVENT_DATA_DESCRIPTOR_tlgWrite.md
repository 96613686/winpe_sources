# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001010`
- end: `0x1400012c3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `691`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a5c8`
- `0x14000b2e0`
- `0x14000b510`

## callees

- `0x140001010`
- `0x1400025b8`
- `0x1400033b0`

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
        const unsigned __int16 **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const unsigned __int16 **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const unsigned __int16 **a20)
{
  __int64 v20; // r9
  const unsigned __int16 *v21; // rax
  __int64 v22; // r10
  bool v23; // zf
  int v24; // r10d
  int v25; // r11d
  int v26; // ebx
  const unsigned __int16 *v27; // r10
  __int64 v28; // rax
  int v29; // eax
  const unsigned __int16 *v30; // r10
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // r10
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // r10
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // r10
  __int64 v40; // rax
  const unsigned __int16 *v41; // r10
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // r10
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
  const unsigned __int16 *v63; // [rsp+C0h] [rbp-40h]
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
  const unsigned __int16 *v76; // [rsp+110h] [rbp+10h]
  int v77; // [rsp+118h] [rbp+18h]
  int v78; // [rsp+11Ch] [rbp+1Ch]
  __int64 v79; // [rsp+120h] [rbp+20h]
  __int64 v80; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v81; // [rsp+130h] [rbp+30h]
  int v82; // [rsp+138h] [rbp+38h]
  int v83; // [rsp+13Ch] [rbp+3Ch]
  const unsigned __int16 *v84; // [rsp+140h] [rbp+40h]
  int v85; // [rsp+148h] [rbp+48h]
  int v86; // [rsp+14Ch] [rbp+4Ch]

  v20 = -1;
  v21 = *a20;
  if ( *a20 )
  {
    v22 = -1;
    do
      v23 = v21[++v22] == 0;
    while ( !v23 );
    v24 = 2 * v22 + 2;
    v25 = 2;
  }
  else
  {
    v25 = 2;
    v21 = &qword_140010DA8;
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
    v27 = &dword_140010DA4;
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
      v23 = v30[++v31] == 0;
    while ( !v23 );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &qword_140010DA8;
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
    v33 = &dword_140010DA4;
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
    v36 = &dword_140010DA4;
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
      v23 = v39[++v40] == 0;
    while ( !v23 );
    v25 = 2 * v40 + 2;
  }
  else
  {
    v39 = &qword_140010DA8;
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
    v41 = &dword_140010DA4;
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
    v44 = &dword_140010DA4;
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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 18, v46);
}

```

## disassembly

```asm
0x140001010  push    rbp
0x140001012  push    rbx
0x140001013  push    rdi
0x140001014  lea     rbp, [rsp-60h]
0x140001019  sub     rsp, 160h
0x140001020  mov     rax, cs:__security_cookie
0x140001027  xor     rax, rsp
0x14000102a  mov     [rbp+70h+var_20], rax
0x14000102e  mov     rax, [rbp+70h+arg_98]
0x140001035  mov     r9, 0FFFFFFFFFFFFFFFFh
0x14000103c  mov     rax, [rax]
0x14000103f  test    rax, rax
0x140001042  jz      short loc_140001064
0x140001044  mov     r10, r9
0x140001047  cmp     word ptr [rax+r10*2+2], 0
0x14000104e  lea     r10, [r10+1]
0x140001052  jnz     short loc_140001047
0x140001054  lea     r10d, ds:2[r10*2]
0x14000105c  mov     r11d, 2
0x140001062  jmp     short loc_140001074
0x140001064  mov     r11d, 2
0x14000106a  lea     rax, qword_140010DA8
0x140001071  mov     r10d, r11d
0x140001074  xor     edi, edi
0x140001076  mov     [rbp+70h+var_30], rax
0x14000107a  mov     rax, [rbp+70h+arg_90]
0x140001081  mov     ebx, 1
0x140001086  mov     [rbp+70h+var_28], r10d
0x14000108a  mov     [rbp+70h+var_24], edi
0x14000108d  mov     r10, [rax]
0x140001090  test    r10, r10
0x140001093  jz      short loc_1400010A5
0x140001095  mov     rax, r9
0x140001098  inc     rax
0x14000109b  cmp     [r10+rax], dil
0x14000109f  jnz     short loc_140001098
0x1400010a1  inc     eax
0x1400010a3  jmp     short loc_1400010AE
0x1400010a5  lea     r10, dword_140010DA4
0x1400010ac  mov     eax, ebx
0x1400010ae  mov     [rbp+70h+var_38], eax
0x1400010b1  mov     rax, [rbp+70h+arg_88]
0x1400010b8  mov     [rbp+70h+var_50], rax
0x1400010bc  mov     rax, [rbp+70h+arg_80]
0x1400010c3  mov     [rbp+70h+var_40], r10
0x1400010c7  mov     [rbp+70h+var_34], edi
0x1400010ca  mov     [rbp+70h+var_48], 4
0x1400010d2  mov     r10, [rax]
0x1400010d5  test    r10, r10
0x1400010d8  jz      short loc_1400010F2
0x1400010da  mov     rax, r9
0x1400010dd  cmp     [r10+rax*2+2], di
0x1400010e3  lea     rax, [rax+1]
0x1400010e7  jnz     short loc_1400010DD
0x1400010e9  lea     eax, ds:2[rax*2]
0x1400010f0  jmp     short loc_1400010FC
0x1400010f2  lea     r10, qword_140010DA8
0x1400010f9  mov     eax, r11d
0x1400010fc  mov     [rbp+70h+var_58], eax
0x1400010ff  mov     rax, [rbp+70h+arg_78]
0x140001106  mov     [rbp+70h+var_60], r10
0x14000110a  mov     [rbp+70h+var_54], edi
0x14000110d  mov     r10, [rax]
0x140001110  test    r10, r10
0x140001113  jz      short loc_140001125
0x140001115  mov     rax, r9
0x140001118  inc     rax
0x14000111b  cmp     [r10+rax], dil
0x14000111f  jnz     short loc_140001118
0x140001121  inc     eax
0x140001123  jmp     short loc_14000112E
0x140001125  lea     r10, dword_140010DA4
0x14000112c  mov     eax, ebx
0x14000112e  mov     [rbp+70h+var_68], eax
0x140001131  mov     rax, [rbp+70h+arg_70]
0x140001138  mov     [rbp+70h+var_80], rax
0x14000113c  mov     rax, [rbp+70h+arg_68]
0x140001143  mov     [rbp+70h+var_70], r10
0x140001147  mov     [rbp+70h+var_64], edi
0x14000114a  mov     [rbp+70h+var_78], 4
0x140001152  mov     r10, [rax]
0x140001155  test    r10, r10
0x140001158  jz      short loc_14000116A
0x14000115a  mov     rax, r9
0x14000115d  inc     rax
0x140001160  cmp     [r10+rax], dil
0x140001164  jnz     short loc_14000115D
0x140001166  inc     eax
0x140001168  jmp     short loc_140001173
0x14000116a  lea     r10, dword_140010DA4
0x140001171  mov     eax, ebx
0x140001173  mov     [rbp+70h+var_88], eax
0x140001176  mov     rax, [rbp+70h+arg_60]
0x14000117d  mov     [rbp+70h+var_A0], rax
0x140001181  mov     rax, [rbp+70h+arg_58]
0x140001188  mov     [rbp+70h+var_90], r10
0x14000118c  mov     [rbp+70h+var_84], edi
0x14000118f  mov     [rbp+70h+var_98], 4
0x140001197  mov     r10, [rax]
0x14000119a  test    r10, r10
0x14000119d  jz      short loc_1400011B8
0x14000119f  mov     rax, r9
0x1400011a2  cmp     [r10+rax*2+2], di
0x1400011a8  lea     rax, [rax+1]
0x1400011ac  jnz     short loc_1400011A2
0x1400011ae  lea     r11d, ds:2[rax*2]
0x1400011b6  jmp     short loc_1400011BF
0x1400011b8  lea     r10, qword_140010DA8
0x1400011bf  mov     rax, [rbp+70h+arg_50]
0x1400011c6  mov     [rbp+70h+var_C0], rax
0x1400011ca  mov     rax, [rbp+70h+arg_48]
0x1400011d1  mov     [rbp+70h+var_B0], r10
0x1400011d5  mov     [rbp+70h+var_A8], r11d
0x1400011d9  mov     [rbp+70h+var_A4], edi
0x1400011dc  mov     r10, [rax]
0x1400011df  mov     [rbp+70h+var_B8], 4
0x1400011e7  test    r10, r10
0x1400011ea  jz      short loc_1400011FC
0x1400011ec  mov     rax, r9
0x1400011ef  inc     rax
0x1400011f2  cmp     [r10+rax], dil
0x1400011f6  jnz     short loc_1400011EF
0x1400011f8  inc     eax
0x1400011fa  jmp     short loc_140001205
0x1400011fc  lea     r10, dword_140010DA4
0x140001203  mov     eax, ebx
0x140001205  mov     [rbp+70h+var_C8], eax
0x140001208  mov     rax, [rbp+70h+arg_40]
0x14000120f  mov     [rbp+70h+var_E0], rax
0x140001213  mov     rax, [rbp+70h+arg_38]
0x14000121a  mov     [rbp+70h+var_D0], r10
0x14000121e  mov     [rbp+70h+var_C4], edi
0x140001221  mov     [rbp+70h+var_D8], 4
0x140001229  mov     r10, [rax]
0x14000122c  test    r10, r10
0x14000122f  jz      short loc_140001242
0x140001231  cmp     [r10+r9+1], dil
0x140001236  lea     r9, [r9+1]
0x14000123a  jnz     short loc_140001231
0x14000123c  lea     ebx, [r9+1]
0x140001240  jmp     short loc_140001249
0x140001242  lea     r10, dword_140010DA4
0x140001249  mov     rax, [rbp+70h+arg_30]
0x140001250  xor     r9d, r9d
0x140001253  mov     [rsp+170h+var_100], rax
0x140001258  mov     rax, [rbp+70h+arg_28]
0x14000125f  mov     [rsp+170h+var_110], rax
0x140001264  mov     rax, [rbp+70h+arg_20]
0x14000126b  mov     [rsp+170h+var_120], rax
0x140001270  lea     rax, [rsp+170h+var_140]
0x140001275  mov     [rsp+170h+var_148], rax
0x14000127a  mov     [rsp+170h+var_150], 12h
0x140001282  mov     [rbp+70h+var_F0], r10
0x140001286  mov     [rbp+70h+var_E8], ebx
0x140001289  mov     [rbp+70h+var_E4], edi
0x14000128c  mov     [rsp+170h+var_F8], 4
0x140001295  mov     [rsp+170h+var_108], 8
0x14000129e  mov     [rsp+170h+var_118], 8
0x1400012a7  call    _tlgWriteTransfer_EventWriteTransfer
0x1400012ac  mov     rcx, [rbp+70h+var_20]
0x1400012b0  xor     rcx, rsp; StackCookie
0x1400012b3  call    __security_check_cookie
0x1400012b8  add     rsp, 160h
0x1400012bf  pop     rdi
0x1400012c0  pop     rbx
0x1400012c1  pop     rbp
0x1400012c2  retn
```
