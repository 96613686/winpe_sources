# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x18000132e`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U?$_tlgWrapSz@G@@U2@U1@U1@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33333333333333AEBU?$_tlgWrapSz@G@@4334444@Z`
- size: `806`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800102a8`

## callees

- `0x180001008`
- `0x1800013bc`
- `0x180016280`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        char **a20,
        char **a21,
        __int64 a22,
        __int64 a23,
        char **a24,
        char **a25,
        char **a26,
        char **a27)
{
  __int64 v27; // rcx
  int v29; // edx
  char *v30; // r8
  __int64 v31; // rax
  int v32; // eax
  char *v33; // r8
  __int64 v34; // rax
  int v35; // eax
  char *v36; // r8
  __int64 v37; // rax
  int v38; // eax
  char *v39; // r8
  __int64 v40; // rax
  int v41; // eax
  char *v42; // r8
  __int64 v43; // rax
  int v44; // eax
  char *v45; // r8
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  __int64 v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h]
  __int64 v56; // [rsp+90h] [rbp-70h]
  __int64 v57; // [rsp+98h] [rbp-68h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  __int64 v60; // [rsp+B0h] [rbp-50h]
  __int64 v61; // [rsp+B8h] [rbp-48h]
  __int64 v62; // [rsp+C0h] [rbp-40h]
  __int64 v63; // [rsp+C8h] [rbp-38h]
  __int64 v64; // [rsp+D0h] [rbp-30h]
  __int64 v65; // [rsp+D8h] [rbp-28h]
  __int64 v66; // [rsp+E0h] [rbp-20h]
  __int64 v67; // [rsp+E8h] [rbp-18h]
  __int64 v68; // [rsp+F0h] [rbp-10h]
  __int64 v69; // [rsp+F8h] [rbp-8h]
  __int64 v70; // [rsp+100h] [rbp+0h]
  __int64 v71; // [rsp+108h] [rbp+8h]
  __int64 v72; // [rsp+110h] [rbp+10h]
  __int64 v73; // [rsp+118h] [rbp+18h]
  __int64 v74; // [rsp+120h] [rbp+20h]
  __int64 v75; // [rsp+128h] [rbp+28h]
  __int64 v76; // [rsp+130h] [rbp+30h]
  __int64 v77; // [rsp+138h] [rbp+38h]
  char *v78; // [rsp+140h] [rbp+40h]
  int v79; // [rsp+148h] [rbp+48h]
  int v80; // [rsp+14Ch] [rbp+4Ch]
  char *v81; // [rsp+150h] [rbp+50h]
  int v82; // [rsp+158h] [rbp+58h]
  int v83; // [rsp+15Ch] [rbp+5Ch]
  __int64 v84; // [rsp+160h] [rbp+60h]
  __int64 v85; // [rsp+168h] [rbp+68h]
  __int64 v86; // [rsp+170h] [rbp+70h]
  __int64 v87; // [rsp+178h] [rbp+78h]
  char *v88; // [rsp+180h] [rbp+80h]
  int v89; // [rsp+188h] [rbp+88h]
  int v90; // [rsp+18Ch] [rbp+8Ch]
  char *v91; // [rsp+190h] [rbp+90h]
  int v92; // [rsp+198h] [rbp+98h]
  int v93; // [rsp+19Ch] [rbp+9Ch]
  char *v94; // [rsp+1A0h] [rbp+A0h]
  int v95; // [rsp+1A8h] [rbp+A8h]
  int v96; // [rsp+1ACh] [rbp+ACh]
  char *v97; // [rsp+1B0h] [rbp+B0h]
  int v98; // [rsp+1B8h] [rbp+B8h]
  int v99; // [rsp+1BCh] [rbp+BCh]

  v27 = -1;
  v29 = 2;
  v30 = *a27;
  if ( *a27 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *(_WORD *)&v30[2 * v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = byte_1800196B4;
    v32 = 2;
  }
  v98 = v32;
  v97 = v30;
  v99 = 0;
  v33 = *a26;
  if ( *a26 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)&v33[2 * v34] );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = byte_1800196B4;
    v35 = 2;
  }
  v95 = v35;
  v94 = v33;
  v96 = 0;
  v36 = *a25;
  if ( *a25 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *(_WORD *)&v36[2 * v37] );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = byte_1800196B4;
    v38 = 2;
  }
  v92 = v38;
  v91 = v36;
  v93 = 0;
  v39 = *a24;
  if ( *a24 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *(_WORD *)&v39[2 * v40] );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = byte_1800196B4;
    v41 = 2;
  }
  v89 = v41;
  v86 = a23;
  v84 = a22;
  v88 = v39;
  v90 = 0;
  v87 = 4;
  v42 = *a21;
  v85 = 4;
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *(_WORD *)&v42[2 * v43] );
    v44 = 2 * v43 + 2;
  }
  else
  {
    v42 = byte_1800196B4;
    v44 = 2;
  }
  v82 = v44;
  v81 = v42;
  v83 = 0;
  v45 = *a20;
  if ( *a20 )
  {
    do
      ++v27;
    while ( *(_WORD *)&v45[2 * v27] );
    v29 = 2 * v27 + 2;
  }
  else
  {
    v45 = byte_1800196B4;
  }
  v76 = a19;
  v74 = a18;
  v72 = a17;
  v70 = a16;
  v68 = a15;
  v66 = a14;
  v64 = a13;
  v62 = a12;
  v60 = a11;
  v58 = a10;
  v56 = a9;
  v54 = a8;
  v52 = a7;
  v50 = a6;
  v48 = a5;
  v78 = v45;
  v79 = v29;
  v80 = 0;
  v77 = 4;
  v75 = 4;
  v73 = 4;
  v71 = 4;
  v69 = 4;
  v67 = 4;
  v65 = 4;
  v63 = 4;
  v61 = 4;
  v59 = 4;
  v57 = 4;
  v55 = 4;
  v53 = 4;
  v51 = 4;
  v49 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180020098, a2, 0, 0, 0x19u, &v47);
}

```

## disassembly

```asm
0x180001008  mov     [rsp-8+arg_0], rbx
0x18000100d  push    rbp
0x18000100e  lea     rbp, [rsp-0D0h]
0x180001016  sub     rsp, 1D0h
0x18000101d  mov     rax, cs:__security_cookie
0x180001024  xor     rax, rsp
0x180001027  mov     [rbp+0D0h+var_10], rax
0x18000102e  mov     rax, [rbp+0D0h+arg_D0]
0x180001035  lea     r11, byte_1800196B4
0x18000103c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001040  xor     r9d, r9d
0x180001043  mov     r10, rdx
0x180001046  mov     edx, 2
0x18000104b  mov     r8, [rax]
0x18000104e  test    r8, r8
0x180001051  jz      short loc_180001069
0x180001053  mov     rax, rcx
0x180001056  inc     rax
0x180001059  cmp     [r8+rax*2], r9w
0x18000105e  jnz     short loc_180001056
0x180001060  lea     eax, ds:2[rax*2]
0x180001067  jmp     short loc_18000106E
0x180001069  mov     r8, r11
0x18000106c  mov     eax, edx
0x18000106e  mov     [rbp+0D0h+var_18], eax
0x180001074  mov     rax, [rbp+0D0h+arg_C8]
0x18000107b  mov     [rbp+0D0h+var_20], r8
0x180001082  mov     [rbp+0D0h+var_14], r9d
0x180001089  mov     r8, [rax]
0x18000108c  test    r8, r8
0x18000108f  jz      short loc_1800010A7
0x180001091  mov     rax, rcx
0x180001094  inc     rax
0x180001097  cmp     [r8+rax*2], r9w
0x18000109c  jnz     short loc_180001094
0x18000109e  lea     eax, ds:2[rax*2]
0x1800010a5  jmp     short loc_1800010AC
0x1800010a7  mov     r8, r11
0x1800010aa  mov     eax, edx
0x1800010ac  mov     [rbp+0D0h+var_28], eax
0x1800010b2  mov     rax, [rbp+0D0h+arg_C0]
0x1800010b9  mov     [rbp+0D0h+var_30], r8
0x1800010c0  mov     [rbp+0D0h+var_24], r9d
0x1800010c7  mov     r8, [rax]
0x1800010ca  test    r8, r8
0x1800010cd  jz      short loc_1800010E5
0x1800010cf  mov     rax, rcx
0x1800010d2  inc     rax
0x1800010d5  cmp     [r8+rax*2], r9w
0x1800010da  jnz     short loc_1800010D2
0x1800010dc  lea     eax, ds:2[rax*2]
0x1800010e3  jmp     short loc_1800010EA
0x1800010e5  mov     r8, r11
0x1800010e8  mov     eax, edx
0x1800010ea  mov     [rbp+0D0h+var_38], eax
0x1800010f0  mov     rax, [rbp+0D0h+arg_B8]
0x1800010f7  mov     [rbp+0D0h+var_40], r8
0x1800010fe  mov     [rbp+0D0h+var_34], r9d
0x180001105  mov     r8, [rax]
0x180001108  test    r8, r8
0x18000110b  jz      short loc_180001123
0x18000110d  mov     rax, rcx
0x180001110  inc     rax
0x180001113  cmp     [r8+rax*2], r9w
0x180001118  jnz     short loc_180001110
0x18000111a  lea     eax, ds:2[rax*2]
0x180001121  jmp     short loc_180001128
0x180001123  mov     r8, r11
0x180001126  mov     eax, edx
0x180001128  mov     [rbp+0D0h+var_48], eax
0x18000112e  mov     rax, [rbp+0D0h+arg_B0]
0x180001135  mov     [rbp+0D0h+var_60], rax
0x180001139  mov     rax, [rbp+0D0h+arg_A8]
0x180001140  mov     [rbp+0D0h+var_70], rax
0x180001144  mov     rax, [rbp+0D0h+arg_A0]
0x18000114b  mov     [rbp+0D0h+var_50], r8
0x180001152  mov     [rbp+0D0h+var_44], r9d
0x180001159  mov     [rbp+0D0h+var_58], 4
0x180001161  mov     r8, [rax]
0x180001164  mov     [rbp+0D0h+var_68], 4
0x18000116c  test    r8, r8
0x18000116f  jz      short loc_180001187
0x180001171  mov     rax, rcx
0x180001174  inc     rax
0x180001177  cmp     [r8+rax*2], r9w
0x18000117c  jnz     short loc_180001174
0x18000117e  lea     eax, ds:2[rax*2]
0x180001185  jmp     short loc_18000118C
0x180001187  mov     r8, r11
0x18000118a  mov     eax, edx
0x18000118c  mov     [rbp+0D0h+var_78], eax
0x18000118f  mov     rax, [rbp+0D0h+arg_98]
0x180001196  mov     [rbp+0D0h+var_80], r8
0x18000119a  mov     [rbp+0D0h+var_74], r9d
0x18000119e  mov     r8, [rax]
0x1800011a1  test    r8, r8
0x1800011a4  jz      short loc_1800011B9
0x1800011a6  inc     rcx
0x1800011a9  cmp     [r8+rcx*2], r9w
0x1800011ae  jnz     short loc_1800011A6
0x1800011b0  lea     edx, ds:2[rcx*2]
0x1800011b7  jmp     short loc_1800011BC
0x1800011b9  mov     r8, r11
0x1800011bc  mov     rax, [rbp+0D0h+arg_90]
0x1800011c3  lea     rcx, dword_180020098
0x1800011ca  mov     [rbp+0D0h+var_A0], rax
0x1800011ce  mov     rax, [rbp+0D0h+arg_88]
0x1800011d5  mov     [rbp+0D0h+var_B0], rax
0x1800011d9  mov     rax, [rbp+0D0h+arg_80]
0x1800011e0  mov     [rbp+0D0h+var_C0], rax
0x1800011e4  mov     rax, [rbp+0D0h+arg_78]
0x1800011eb  mov     [rbp+0D0h+var_D0], rax
0x1800011ef  mov     rax, [rbp+0D0h+arg_70]
0x1800011f6  mov     [rbp+0D0h+var_E0], rax
0x1800011fa  mov     rax, [rbp+0D0h+arg_68]
0x180001201  mov     [rbp+0D0h+var_F0], rax
0x180001205  mov     rax, [rbp+0D0h+arg_60]
0x18000120c  mov     [rbp+0D0h+var_100], rax
0x180001210  mov     rax, [rbp+0D0h+arg_58]
0x180001217  mov     [rbp+0D0h+var_110], rax
0x18000121b  mov     rax, [rbp+0D0h+arg_50]
0x180001222  mov     [rbp+0D0h+var_120], rax
0x180001226  mov     rax, [rbp+0D0h+arg_48]
0x18000122d  mov     [rbp+0D0h+var_130], rax
0x180001231  mov     rax, [rbp+0D0h+arg_40]
0x180001238  mov     [rbp+0D0h+var_140], rax
0x18000123c  mov     rax, [rbp+0D0h+arg_38]
0x180001243  mov     [rbp+0D0h+var_150], rax
0x180001247  mov     rax, [rbp+0D0h+arg_30]
0x18000124e  mov     [rsp+1D0h+var_160], rax
0x180001253  mov     rax, [rbp+0D0h+arg_28]
0x18000125a  mov     [rsp+1D0h+var_170], rax
0x18000125f  mov     rax, [rbp+0D0h+arg_20]
0x180001266  mov     [rsp+1D0h+var_180], rax
0x18000126b  lea     rax, [rsp+1D0h+var_1A0]
0x180001270  mov     [rbp+0D0h+var_90], r8
0x180001274  xor     r8d, r8d
0x180001277  mov     [rbp+0D0h+var_88], edx
0x18000127a  mov     rdx, r10
0x18000127d  mov     [rsp+1D0h+var_1A8], rax
0x180001282  mov     [rsp+1D0h+var_1B0], 19h
0x18000128a  mov     [rbp+0D0h+var_84], r9d
0x18000128e  mov     [rbp+0D0h+var_98], 4
0x180001296  mov     [rbp+0D0h+var_A8], 4
0x18000129e  mov     [rbp+0D0h+var_B8], 4
0x1800012a6  mov     [rbp+0D0h+var_C8], 4
0x1800012ae  mov     [rbp+0D0h+var_D8], 4
0x1800012b6  mov     [rbp+0D0h+var_E8], 4
0x1800012be  mov     [rbp+0D0h+var_F8], 4
0x1800012c6  mov     [rbp+0D0h+var_108], 4
0x1800012ce  mov     [rbp+0D0h+var_118], 4
0x1800012d6  mov     [rbp+0D0h+var_128], 4
0x1800012de  mov     [rbp+0D0h+var_138], 4
0x1800012e6  mov     [rbp+0D0h+var_148], 4
0x1800012ee  mov     [rsp+1D0h+var_158], 4
0x1800012f7  mov     [rsp+1D0h+var_168], 4
0x180001300  mov     [rsp+1D0h+var_178], 4
0x180001309  call    _tlgWriteTransfer_EventWriteTransfer
0x18000130e  mov     rcx, [rbp+0D0h+var_10]
0x180001315  xor     rcx, rsp; StackCookie
0x180001318  call    __security_check_cookie
0x18000131d  mov     rbx, [rsp+1D0h+arg_0]
0x180001325  add     rsp, 1D0h
0x18000132c  pop     rbp
0x18000132d  retn
```
