# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x1800012c6`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapSz@G@@U4@U4@U4@U4@U4@U?$_tlgWrapperByVal@$03@@U5@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapSz@G@@66666AEBU?$_tlgWrapperByVal@$03@@7666@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006904`

## callees

- `0x180001008`
- `0x1800012cc`
- `0x180013700`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8,
        const unsigned __int16 **a9,
        const unsigned __int16 **a10,
        const unsigned __int16 **a11,
        const unsigned __int16 **a12,
        const unsigned __int16 **a13,
        const unsigned __int16 **a14,
        __int64 a15,
        __int64 a16,
        const unsigned __int16 **a17,
        const unsigned __int16 **a18,
        const unsigned __int16 **a19)
{
  __int64 v19; // rcx
  int v21; // edx
  const unsigned __int16 *v22; // r8
  __int64 v23; // rax
  int v24; // eax
  const unsigned __int16 *v25; // r8
  __int64 v26; // rax
  int v27; // eax
  const unsigned __int16 *v28; // r8
  __int64 v29; // rax
  int v30; // eax
  const unsigned __int16 *v31; // r8
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // r8
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // r8
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // r8
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // r8
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // r8
  __int64 v47; // rcx
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v50; // [rsp+50h] [rbp-B0h]
  __int64 v51; // [rsp+58h] [rbp-A8h]
  __int64 v52; // [rsp+60h] [rbp-A0h]
  __int64 v53; // [rsp+68h] [rbp-98h]
  __int64 v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
  __int64 v56; // [rsp+80h] [rbp-80h]
  __int64 v57; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v58; // [rsp+90h] [rbp-70h]
  int v59; // [rsp+98h] [rbp-68h]
  int v60; // [rsp+9Ch] [rbp-64h]
  const unsigned __int16 *v61; // [rsp+A0h] [rbp-60h]
  int v62; // [rsp+A8h] [rbp-58h]
  int v63; // [rsp+ACh] [rbp-54h]
  const unsigned __int16 *v64; // [rsp+B0h] [rbp-50h]
  int v65; // [rsp+B8h] [rbp-48h]
  int v66; // [rsp+BCh] [rbp-44h]
  const unsigned __int16 *v67; // [rsp+C0h] [rbp-40h]
  int v68; // [rsp+C8h] [rbp-38h]
  int v69; // [rsp+CCh] [rbp-34h]
  const unsigned __int16 *v70; // [rsp+D0h] [rbp-30h]
  int v71; // [rsp+D8h] [rbp-28h]
  int v72; // [rsp+DCh] [rbp-24h]
  const unsigned __int16 *v73; // [rsp+E0h] [rbp-20h]
  int v74; // [rsp+E8h] [rbp-18h]
  int v75; // [rsp+ECh] [rbp-14h]
  __int64 v76; // [rsp+F0h] [rbp-10h]
  __int64 v77; // [rsp+F8h] [rbp-8h]
  __int64 v78; // [rsp+100h] [rbp+0h]
  __int64 v79; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v80; // [rsp+110h] [rbp+10h]
  int v81; // [rsp+118h] [rbp+18h]
  int v82; // [rsp+11Ch] [rbp+1Ch]
  const unsigned __int16 *v83; // [rsp+120h] [rbp+20h]
  int v84; // [rsp+128h] [rbp+28h]
  int v85; // [rsp+12Ch] [rbp+2Ch]
  const unsigned __int16 *v86; // [rsp+130h] [rbp+30h]
  int v87; // [rsp+138h] [rbp+38h]
  int v88; // [rsp+13Ch] [rbp+3Ch]

  v19 = -1;
  v21 = 2;
  v22 = *a19;
  if ( *a19 )
  {
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = 2 * v23 + 2;
  }
  else
  {
    v22 = &word_180017E8C;
    v24 = 2;
  }
  v87 = v24;
  v86 = v22;
  v88 = 0;
  v25 = *a18;
  if ( *a18 )
  {
    v26 = -1;
    do
      ++v26;
    while ( v25[v26] );
    v27 = 2 * v26 + 2;
  }
  else
  {
    v25 = &word_180017E8C;
    v27 = 2;
  }
  v84 = v27;
  v83 = v25;
  v85 = 0;
  v28 = *a17;
  if ( *a17 )
  {
    v29 = -1;
    do
      ++v29;
    while ( v28[v29] );
    v30 = 2 * v29 + 2;
  }
  else
  {
    v28 = &word_180017E8C;
    v30 = 2;
  }
  v81 = v30;
  v78 = a16;
  v76 = a15;
  v80 = v28;
  v82 = 0;
  v79 = 4;
  v31 = *a14;
  v77 = 4;
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &word_180017E8C;
    v33 = 2;
  }
  v74 = v33;
  v73 = v31;
  v75 = 0;
  v34 = *a13;
  if ( *a13 )
  {
    v35 = -1;
    do
      ++v35;
    while ( v34[v35] );
    v36 = 2 * v35 + 2;
  }
  else
  {
    v34 = &word_180017E8C;
    v36 = 2;
  }
  v71 = v36;
  v70 = v34;
  v72 = 0;
  v37 = *a12;
  if ( *a12 )
  {
    v38 = -1;
    do
      ++v38;
    while ( v37[v38] );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &word_180017E8C;
    v39 = 2;
  }
  v68 = v39;
  v67 = v37;
  v69 = 0;
  v40 = *a11;
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( v40[v41] );
    v42 = 2 * v41 + 2;
  }
  else
  {
    v40 = &word_180017E8C;
    v42 = 2;
  }
  v65 = v42;
  v64 = v40;
  v66 = 0;
  v43 = *a10;
  if ( *a10 )
  {
    v44 = -1;
    do
      ++v44;
    while ( v43[v44] );
    v45 = 2 * v44 + 2;
  }
  else
  {
    v43 = &word_180017E8C;
    v45 = 2;
  }
  v62 = v45;
  v61 = v43;
  v63 = 0;
  v46 = *a9;
  if ( *a9 )
  {
    do
      ++v19;
    while ( v46[v19] );
    v21 = 2 * v19 + 2;
  }
  else
  {
    v46 = &word_180017E8C;
  }
  v56 = a8;
  v54 = a7;
  v58 = v46;
  v59 = v21;
  v60 = 0;
  v47 = *a6;
  v50 = a5;
  v52 = v47;
  v57 = 8;
  v55 = 1;
  v53 = 16;
  v51 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001E2A0, a2, 0, 0, 0x11u, &v49);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-50h]
0x18000100f  sub     rsp, 150h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+50h+var_10], rax
0x180001024  mov     rax, [rbp+50h+arg_90]
0x18000102b  lea     r11, word_180017E8C
0x180001032  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001036  xor     r9d, r9d
0x180001039  mov     r10, rdx
0x18000103c  mov     edx, 2
0x180001041  mov     r8, [rax]
0x180001044  test    r8, r8
0x180001047  jz      short loc_18000105F
0x180001049  mov     rax, rcx
0x18000104c  inc     rax
0x18000104f  cmp     [r8+rax*2], r9w
0x180001054  jnz     short loc_18000104C
0x180001056  lea     eax, ds:2[rax*2]
0x18000105d  jmp     short loc_180001064
0x18000105f  mov     r8, r11
0x180001062  mov     eax, edx
0x180001064  mov     [rbp+50h+var_18], eax
0x180001067  mov     rax, [rbp+50h+arg_88]
0x18000106e  mov     [rbp+50h+var_20], r8
0x180001072  mov     [rbp+50h+var_14], r9d
0x180001076  mov     r8, [rax]
0x180001079  test    r8, r8
0x18000107c  jz      short loc_180001094
0x18000107e  mov     rax, rcx
0x180001081  inc     rax
0x180001084  cmp     [r8+rax*2], r9w
0x180001089  jnz     short loc_180001081
0x18000108b  lea     eax, ds:2[rax*2]
0x180001092  jmp     short loc_180001099
0x180001094  mov     r8, r11
0x180001097  mov     eax, edx
0x180001099  mov     [rbp+50h+var_28], eax
0x18000109c  mov     rax, [rbp+50h+arg_80]
0x1800010a3  mov     [rbp+50h+var_30], r8
0x1800010a7  mov     [rbp+50h+var_24], r9d
0x1800010ab  mov     r8, [rax]
0x1800010ae  test    r8, r8
0x1800010b1  jz      short loc_1800010C9
0x1800010b3  mov     rax, rcx
0x1800010b6  inc     rax
0x1800010b9  cmp     [r8+rax*2], r9w
0x1800010be  jnz     short loc_1800010B6
0x1800010c0  lea     eax, ds:2[rax*2]
0x1800010c7  jmp     short loc_1800010CE
0x1800010c9  mov     r8, r11
0x1800010cc  mov     eax, edx
0x1800010ce  mov     [rbp+50h+var_38], eax
0x1800010d1  mov     rax, [rbp+50h+arg_78]
0x1800010d8  mov     [rbp+50h+var_50], rax
0x1800010dc  mov     rax, [rbp+50h+arg_70]
0x1800010e3  mov     [rbp+50h+var_60], rax
0x1800010e7  mov     rax, [rbp+50h+arg_68]
0x1800010ee  mov     [rbp+50h+var_40], r8
0x1800010f2  mov     [rbp+50h+var_34], r9d
0x1800010f6  mov     [rbp+50h+var_48], 4
0x1800010fe  mov     r8, [rax]
0x180001101  mov     [rbp+50h+var_58], 4
0x180001109  test    r8, r8
0x18000110c  jz      short loc_180001124
0x18000110e  mov     rax, rcx
0x180001111  inc     rax
0x180001114  cmp     [r8+rax*2], r9w
0x180001119  jnz     short loc_180001111
0x18000111b  lea     eax, ds:2[rax*2]
0x180001122  jmp     short loc_180001129
0x180001124  mov     r8, r11
0x180001127  mov     eax, edx
0x180001129  mov     [rbp+50h+var_68], eax
0x18000112c  mov     rax, [rbp+50h+arg_60]
0x180001133  mov     [rbp+50h+var_70], r8
0x180001137  mov     [rbp+50h+var_64], r9d
0x18000113b  mov     r8, [rax]
0x18000113e  test    r8, r8
0x180001141  jz      short loc_180001159
0x180001143  mov     rax, rcx
0x180001146  inc     rax
0x180001149  cmp     [r8+rax*2], r9w
0x18000114e  jnz     short loc_180001146
0x180001150  lea     eax, ds:2[rax*2]
0x180001157  jmp     short loc_18000115E
0x180001159  mov     r8, r11
0x18000115c  mov     eax, edx
0x18000115e  mov     [rbp+50h+var_78], eax
0x180001161  mov     rax, [rbp+50h+arg_58]
0x180001168  mov     [rbp+50h+var_80], r8
0x18000116c  mov     [rbp+50h+var_74], r9d
0x180001170  mov     r8, [rax]
0x180001173  test    r8, r8
0x180001176  jz      short loc_18000118E
0x180001178  mov     rax, rcx
0x18000117b  inc     rax
0x18000117e  cmp     [r8+rax*2], r9w
0x180001183  jnz     short loc_18000117B
0x180001185  lea     eax, ds:2[rax*2]
0x18000118c  jmp     short loc_180001193
0x18000118e  mov     r8, r11
0x180001191  mov     eax, edx
0x180001193  mov     [rbp+50h+var_88], eax
0x180001196  mov     rax, [rbp+50h+arg_50]
0x18000119d  mov     [rbp+50h+var_90], r8
0x1800011a1  mov     [rbp+50h+var_84], r9d
0x1800011a5  mov     r8, [rax]
0x1800011a8  test    r8, r8
0x1800011ab  jz      short loc_1800011C3
0x1800011ad  mov     rax, rcx
0x1800011b0  inc     rax
0x1800011b3  cmp     [r8+rax*2], r9w
0x1800011b8  jnz     short loc_1800011B0
0x1800011ba  lea     eax, ds:2[rax*2]
0x1800011c1  jmp     short loc_1800011C8
0x1800011c3  mov     r8, r11
0x1800011c6  mov     eax, edx
0x1800011c8  mov     [rbp+50h+var_98], eax
0x1800011cb  mov     rax, [rbp+50h+arg_48]
0x1800011d2  mov     [rbp+50h+var_A0], r8
0x1800011d6  mov     [rbp+50h+var_94], r9d
0x1800011da  mov     r8, [rax]
0x1800011dd  test    r8, r8
0x1800011e0  jz      short loc_1800011F8
0x1800011e2  mov     rax, rcx
0x1800011e5  inc     rax
0x1800011e8  cmp     [r8+rax*2], r9w
0x1800011ed  jnz     short loc_1800011E5
0x1800011ef  lea     eax, ds:2[rax*2]
0x1800011f6  jmp     short loc_1800011FD
0x1800011f8  mov     r8, r11
0x1800011fb  mov     eax, edx
0x1800011fd  mov     [rbp+50h+var_A8], eax
0x180001200  mov     rax, [rbp+50h+arg_40]
0x180001207  mov     [rbp+50h+var_B0], r8
0x18000120b  mov     [rbp+50h+var_A4], r9d
0x18000120f  mov     r8, [rax]
0x180001212  test    r8, r8
0x180001215  jz      short loc_18000122A
0x180001217  inc     rcx
0x18000121a  cmp     [r8+rcx*2], r9w
0x18000121f  jnz     short loc_180001217
0x180001221  lea     edx, ds:2[rcx*2]
0x180001228  jmp     short loc_18000122D
0x18000122a  mov     r8, r11
0x18000122d  mov     rax, [rbp+50h+arg_38]
0x180001234  mov     [rbp+50h+var_D0], rax
0x180001238  mov     rax, [rbp+50h+arg_30]
0x18000123f  mov     [rsp+150h+var_E0], rax
0x180001244  mov     rax, [rbp+50h+arg_28]
0x18000124b  mov     [rbp+50h+var_C0], r8
0x18000124f  xor     r8d, r8d
0x180001252  mov     [rbp+50h+var_B8], edx
0x180001255  mov     rdx, r10
0x180001258  mov     [rbp+50h+var_B4], r9d
0x18000125c  mov     rcx, [rax]
0x18000125f  mov     rax, [rbp+50h+arg_20]
0x180001266  mov     [rsp+150h+var_100], rax
0x18000126b  lea     rax, [rsp+150h+var_120]
0x180001270  mov     [rsp+150h+var_F0], rcx
0x180001275  lea     rcx, dword_18001E2A0
0x18000127c  mov     [rsp+150h+var_128], rax
0x180001281  mov     [rsp+150h+var_130], 11h
0x180001289  mov     [rbp+50h+var_C8], 8
0x180001291  mov     [rsp+150h+var_D8], 1
0x18000129a  mov     [rsp+150h+var_E8], 10h
0x1800012a3  mov     [rsp+150h+var_F8], 8
0x1800012ac  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012b1  mov     rcx, [rbp+50h+var_10]
0x1800012b5  xor     rcx, rsp; StackCookie
0x1800012b8  call    __security_check_cookie
0x1800012bd  add     rsp, 150h
0x1800012c4  pop     rbp
0x1800012c5  retn
```
