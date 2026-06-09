# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001008`
- end: `0x1800012fb`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U2@U1@U?$_tlgWrapSz@G@@U1@U2@U1@U2@U3@U1@U2@U3@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@343AEBU?$_tlgWrapSz@G@@34345345334@Z`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800060a0`

## callees

- `0x180001008`
- `0x180001304`
- `0x180002650`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        int **a10,
        __int64 a11,
        const unsigned __int16 **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        int **a15,
        __int64 a16,
        const unsigned __int16 **a17,
        int **a18,
        __int64 a19,
        __int64 a20,
        const unsigned __int16 **a21)
{
  __int64 v22; // rdx
  int v23; // r8d
  const unsigned __int16 *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r9d
  int *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  const unsigned __int16 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  int *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  int *v43; // rcx
  __int64 v44; // rax
  const unsigned __int16 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  const unsigned __int16 *v48; // rcx
  struct _EVENT_DATA_DESCRIPTOR v50; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h]
  __int64 v52; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v53; // [rsp+60h] [rbp-A0h]
  int v54; // [rsp+68h] [rbp-98h]
  int v55; // [rsp+6Ch] [rbp-94h]
  __int64 v56; // [rsp+70h] [rbp-90h]
  __int64 v57; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v58; // [rsp+80h] [rbp-80h]
  int v59; // [rsp+88h] [rbp-78h]
  int v60; // [rsp+8Ch] [rbp-74h]
  __int64 v61; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+98h] [rbp-68h]
  int *v63; // [rsp+A0h] [rbp-60h]
  int v64; // [rsp+A8h] [rbp-58h]
  int v65; // [rsp+ACh] [rbp-54h]
  __int64 v66; // [rsp+B0h] [rbp-50h]
  __int64 v67; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v68; // [rsp+C0h] [rbp-40h]
  int v69; // [rsp+C8h] [rbp-38h]
  int v70; // [rsp+CCh] [rbp-34h]
  __int64 v71; // [rsp+D0h] [rbp-30h]
  __int64 v72; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v73; // [rsp+E0h] [rbp-20h]
  int v74; // [rsp+E8h] [rbp-18h]
  int v75; // [rsp+ECh] [rbp-14h]
  int *v76; // [rsp+F0h] [rbp-10h]
  int v77; // [rsp+F8h] [rbp-8h]
  int v78; // [rsp+FCh] [rbp-4h]
  __int64 v79; // [rsp+100h] [rbp+0h]
  __int64 v80; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v81; // [rsp+110h] [rbp+10h]
  int v82; // [rsp+118h] [rbp+18h]
  int v83; // [rsp+11Ch] [rbp+1Ch]
  int *v84; // [rsp+120h] [rbp+20h]
  int v85; // [rsp+128h] [rbp+28h]
  int v86; // [rsp+12Ch] [rbp+2Ch]
  __int64 v87; // [rsp+130h] [rbp+30h]
  __int64 v88; // [rsp+138h] [rbp+38h]
  __int64 v89; // [rsp+140h] [rbp+40h]
  __int64 v90; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v91; // [rsp+150h] [rbp+50h]
  int v92; // [rsp+158h] [rbp+58h]
  int v93; // [rsp+15Ch] [rbp+5Ch]

  v22 = -1;
  v23 = 1;
  v24 = *a21;
  if ( *a21 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_BYTE *)v24 + v25) );
    v26 = v25 + 1;
  }
  else
  {
    v24 = &byte_18000EE30;
    v26 = 1;
  }
  v92 = v26;
  v27 = 2;
  v89 = a20;
  v87 = a19;
  v91 = v24;
  v93 = 0;
  v90 = 4;
  v28 = *a18;
  v88 = 4;
  if ( v28 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)v28 + v29) );
    v30 = 2 * v29 + 2;
  }
  else
  {
    v28 = &dword_18000EE34;
    v30 = 2;
  }
  v85 = v30;
  v84 = v28;
  v86 = 0;
  v31 = *a17;
  if ( *a17 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_BYTE *)v31 + v32) );
    v33 = v32 + 1;
  }
  else
  {
    v31 = &byte_18000EE30;
    v33 = 1;
  }
  v82 = v33;
  v79 = a16;
  v81 = v31;
  v83 = 0;
  v80 = 4;
  v34 = *a15;
  if ( *a15 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_WORD *)v34 + v35) );
    v36 = 2 * v35 + 2;
  }
  else
  {
    v34 = &dword_18000EE34;
    v36 = 2;
  }
  v77 = v36;
  v76 = v34;
  v78 = 0;
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
    v37 = &byte_18000EE30;
    v39 = 1;
  }
  v74 = v39;
  v71 = a13;
  v73 = v37;
  v75 = 0;
  v72 = 4;
  v40 = *a12;
  if ( *a12 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &byte_18000EE30;
    v42 = 1;
  }
  v69 = v42;
  v66 = a11;
  v68 = v40;
  v70 = 0;
  v67 = 4;
  v43 = *a10;
  if ( *a10 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_WORD *)v43 + v44) );
    v27 = 2 * v44 + 2;
  }
  else
  {
    v43 = &dword_18000EE34;
  }
  v61 = a9;
  v63 = v43;
  v64 = v27;
  v65 = 0;
  v45 = *a8;
  v62 = 4;
  if ( v45 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_BYTE *)v45 + v46) );
    v47 = v46 + 1;
  }
  else
  {
    v45 = &byte_18000EE30;
    v47 = 1;
  }
  v59 = v47;
  v56 = a7;
  v58 = v45;
  v60 = 0;
  v57 = 4;
  v48 = *a6;
  if ( *a6 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v48 + v22) );
    v23 = v22 + 1;
  }
  else
  {
    v48 = &byte_18000EE30;
  }
  v51 = a5;
  v53 = v48;
  v54 = v23;
  v55 = 0;
  v52 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014000, a2, 0, 0, 0x13u, &v50);
}

```

## disassembly

```asm
0x180001008  mov     [rsp-8+arg_0], rbx
0x18000100d  mov     [rsp-8+arg_10], rdi
0x180001012  push    rbp
0x180001013  lea     rbp, [rsp-70h]
0x180001018  sub     rsp, 170h
0x18000101f  mov     rax, cs:__security_cookie
0x180001026  xor     rax, rsp
0x180001029  mov     [rbp+70h+var_10], rax
0x18000102d  mov     rax, [rbp+70h+arg_A0]
0x180001034  lea     rbx, byte_18000EE30
0x18000103b  mov     r10, rdx
0x18000103e  xor     r11d, r11d
0x180001041  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001045  mov     r8d, 1
0x18000104b  mov     rcx, [rax]
0x18000104e  test    rcx, rcx
0x180001051  jz      short loc_180001063
0x180001053  mov     rax, rdx
0x180001056  inc     rax
0x180001059  cmp     [rcx+rax], r11b
0x18000105d  jnz     short loc_180001056
0x18000105f  inc     eax
0x180001061  jmp     short loc_180001069
0x180001063  mov     rcx, rbx
0x180001066  mov     eax, r8d
0x180001069  mov     [rbp+70h+var_18], eax
0x18000106c  mov     r9d, 2
0x180001072  mov     rax, [rbp+70h+arg_98]
0x180001079  mov     [rbp+70h+var_30], rax
0x18000107d  mov     rax, [rbp+70h+arg_90]
0x180001084  mov     [rbp+70h+var_40], rax
0x180001088  mov     rax, [rbp+70h+arg_88]
0x18000108f  mov     [rbp+70h+var_20], rcx
0x180001093  mov     [rbp+70h+var_14], r11d
0x180001097  mov     [rbp+70h+var_28], 4
0x18000109f  mov     rcx, [rax]
0x1800010a2  mov     [rbp+70h+var_38], 4
0x1800010aa  test    rcx, rcx
0x1800010ad  jz      short loc_1800010C5
0x1800010af  mov     rax, rdx
0x1800010b2  inc     rax
0x1800010b5  cmp     [rcx+rax*2], r11w
0x1800010ba  jnz     short loc_1800010B2
0x1800010bc  lea     eax, ds:2[rax*2]
0x1800010c3  jmp     short loc_1800010CF
0x1800010c5  lea     rcx, dword_18000EE34
0x1800010cc  mov     eax, r9d
0x1800010cf  mov     [rbp+70h+var_48], eax
0x1800010d2  mov     rax, [rbp+70h+arg_80]
0x1800010d9  mov     [rbp+70h+var_50], rcx
0x1800010dd  mov     [rbp+70h+var_44], r11d
0x1800010e1  mov     rcx, [rax]
0x1800010e4  test    rcx, rcx
0x1800010e7  jz      short loc_1800010F9
0x1800010e9  mov     rax, rdx
0x1800010ec  inc     rax
0x1800010ef  cmp     [rcx+rax], r11b
0x1800010f3  jnz     short loc_1800010EC
0x1800010f5  inc     eax
0x1800010f7  jmp     short loc_1800010FF
0x1800010f9  mov     rcx, rbx
0x1800010fc  mov     eax, r8d
0x1800010ff  mov     [rbp+70h+var_58], eax
0x180001102  mov     rax, [rbp+70h+arg_78]
0x180001109  mov     [rbp+70h+var_70], rax
0x18000110d  mov     rax, [rbp+70h+arg_70]
0x180001114  mov     [rbp+70h+var_60], rcx
0x180001118  mov     [rbp+70h+var_54], r11d
0x18000111c  mov     [rbp+70h+var_68], 4
0x180001124  mov     rcx, [rax]
0x180001127  test    rcx, rcx
0x18000112a  jz      short loc_180001142
0x18000112c  mov     rax, rdx
0x18000112f  inc     rax
0x180001132  cmp     [rcx+rax*2], r11w
0x180001137  jnz     short loc_18000112F
0x180001139  lea     eax, ds:2[rax*2]
0x180001140  jmp     short loc_18000114C
0x180001142  lea     rcx, dword_18000EE34
0x180001149  mov     eax, r9d
0x18000114c  mov     [rbp+70h+var_78], eax
0x18000114f  mov     rax, [rbp+70h+arg_68]
0x180001156  mov     [rbp+70h+var_80], rcx
0x18000115a  mov     [rbp+70h+var_74], r11d
0x18000115e  mov     rcx, [rax]
0x180001161  test    rcx, rcx
0x180001164  jz      short loc_180001176
0x180001166  mov     rax, rdx
0x180001169  inc     rax
0x18000116c  cmp     [rcx+rax], r11b
0x180001170  jnz     short loc_180001169
0x180001172  inc     eax
0x180001174  jmp     short loc_18000117C
0x180001176  mov     rcx, rbx
0x180001179  mov     eax, r8d
0x18000117c  mov     [rbp+70h+var_88], eax
0x18000117f  mov     rax, [rbp+70h+arg_60]
0x180001186  mov     [rbp+70h+var_A0], rax
0x18000118a  mov     rax, [rbp+70h+arg_58]
0x180001191  mov     [rbp+70h+var_90], rcx
0x180001195  mov     [rbp+70h+var_84], r11d
0x180001199  mov     [rbp+70h+var_98], 4
0x1800011a1  mov     rcx, [rax]
0x1800011a4  test    rcx, rcx
0x1800011a7  jz      short loc_1800011B9
0x1800011a9  mov     rax, rdx
0x1800011ac  inc     rax
0x1800011af  cmp     [rcx+rax], r11b
0x1800011b3  jnz     short loc_1800011AC
0x1800011b5  inc     eax
0x1800011b7  jmp     short loc_1800011BF
0x1800011b9  mov     rcx, rbx
0x1800011bc  mov     eax, r8d
0x1800011bf  mov     [rbp+70h+var_A8], eax
0x1800011c2  mov     rax, [rbp+70h+arg_50]
0x1800011c9  mov     [rbp+70h+var_C0], rax
0x1800011cd  mov     rax, [rbp+70h+arg_48]
0x1800011d4  mov     [rbp+70h+var_B0], rcx
0x1800011d8  mov     [rbp+70h+var_A4], r11d
0x1800011dc  mov     [rbp+70h+var_B8], 4
0x1800011e4  mov     rcx, [rax]
0x1800011e7  test    rcx, rcx
0x1800011ea  jz      short loc_180001203
0x1800011ec  mov     rax, rdx
0x1800011ef  inc     rax
0x1800011f2  cmp     [rcx+rax*2], r11w
0x1800011f7  jnz     short loc_1800011EF
0x1800011f9  lea     r9d, ds:2[rax*2]
0x180001201  jmp     short loc_18000120A
0x180001203  lea     rcx, dword_18000EE34
0x18000120a  mov     rax, [rbp+70h+arg_40]
0x180001211  mov     [rbp+70h+var_E0], rax
0x180001215  mov     rax, [rbp+70h+arg_38]
0x18000121c  mov     [rbp+70h+var_D0], rcx
0x180001220  mov     [rbp+70h+var_C8], r9d
0x180001224  mov     [rbp+70h+var_C4], r11d
0x180001228  mov     rcx, [rax]
0x18000122b  mov     [rbp+70h+var_D8], 4
0x180001233  test    rcx, rcx
0x180001236  jz      short loc_180001248
0x180001238  mov     rax, rdx
0x18000123b  inc     rax
0x18000123e  cmp     [rcx+rax], r11b
0x180001242  jnz     short loc_18000123B
0x180001244  inc     eax
0x180001246  jmp     short loc_18000124E
0x180001248  mov     rcx, rbx
0x18000124b  mov     eax, r8d
0x18000124e  mov     [rbp+70h+var_E8], eax
0x180001251  mov     rax, [rbp+70h+arg_30]
0x180001258  mov     [rsp+170h+var_100], rax
0x18000125d  mov     rax, [rbp+70h+arg_28]
0x180001264  mov     [rbp+70h+var_F0], rcx
0x180001268  mov     [rbp+70h+var_E4], r11d
0x18000126c  mov     [rsp+170h+var_F8], 4
0x180001275  mov     rcx, [rax]
0x180001278  test    rcx, rcx
0x18000127b  jz      short loc_18000128C
0x18000127d  inc     rdx
0x180001280  cmp     [rcx+rdx], r11b
0x180001284  jnz     short loc_18000127D
0x180001286  lea     r8d, [rdx+1]
0x18000128a  jmp     short loc_18000128F
0x18000128c  mov     rcx, rbx
0x18000128f  mov     rax, [rbp+70h+arg_20]
0x180001296  xor     r9d, r9d; int
0x180001299  mov     [rsp+170h+var_120], rax
0x18000129e  mov     rdx, r10; int
0x1800012a1  lea     rax, [rsp+170h+var_140]
0x1800012a6  mov     [rsp+170h+var_110], rcx
0x1800012ab  mov     [rsp+170h+var_108], r8d
0x1800012b0  lea     rcx, dword_180014000; int
0x1800012b7  mov     [rsp+170h+var_148], rax; PEVENT_DATA_DESCRIPTOR
0x1800012bc  xor     r8d, r8d; int
0x1800012bf  mov     [rsp+170h+var_150], 13h; ULONG
0x1800012c7  mov     [rsp+170h+var_104], r11d
0x1800012cc  mov     [rsp+170h+var_118], 4
0x1800012d5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012da  mov     rcx, [rbp+70h+var_10]
0x1800012de  xor     rcx, rsp; StackCookie
0x1800012e1  call    __security_check_cookie
0x1800012e6  lea     r11, [rsp+170h+var_s0]
0x1800012ee  mov     rbx, [r11+10h]
0x1800012f2  mov     rdi, [r11+20h]
0x1800012f6  mov     rsp, r11
0x1800012f9  pop     rbp
0x1800012fa  retn
```
