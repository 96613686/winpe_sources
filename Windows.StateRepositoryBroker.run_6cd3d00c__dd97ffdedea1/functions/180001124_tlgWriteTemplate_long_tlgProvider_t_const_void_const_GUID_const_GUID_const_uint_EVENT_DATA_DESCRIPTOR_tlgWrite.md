# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001124`
- end: `0x1800013cf`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005e84`

## callees

- `0x180001124`
- `0x180001858`
- `0x180001d60`

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
    v24 = &dword_18000E6E4;
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
    v28 = &byte_18000E6E1;
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
    v31 = &dword_18000E6E4;
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
    v34 = &byte_18000E6E1;
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
    v37 = &byte_18000E6E1;
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
    v40 = &dword_18000E6E4;
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
    v42 = &byte_18000E6E1;
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
    v45 = &byte_18000E6E1;
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
0x180001124  mov     [rsp-8+arg_10], rbx
0x180001129  push    rbp
0x18000112a  push    rsi
0x18000112b  push    rdi
0x18000112c  lea     rbp, [rsp-60h]
0x180001131  sub     rsp, 160h
0x180001138  mov     rax, cs:__security_cookie
0x18000113f  xor     rax, rsp
0x180001142  mov     [rbp+70h+var_20], rax
0x180001146  mov     rax, [rbp+70h+arg_98]
0x18000114d  mov     r11, rdx
0x180001150  mov     r10, rcx
0x180001153  xor     ebx, ebx
0x180001155  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001159  mov     r9d, 2
0x18000115f  mov     rdx, [rax]
0x180001162  test    rdx, rdx
0x180001165  jz      short loc_18000117C
0x180001167  mov     rax, rcx
0x18000116a  inc     rax
0x18000116d  cmp     [rdx+rax*2], bx
0x180001171  jnz     short loc_18000116A
0x180001173  lea     eax, ds:2[rax*2]
0x18000117a  jmp     short loc_180001186
0x18000117c  lea     rdx, dword_18000E6E4
0x180001183  mov     eax, r9d
0x180001186  mov     [rbp+70h+var_28], eax
0x180001189  lea     rdi, byte_18000E6E1
0x180001190  mov     rax, [rbp+70h+arg_90]
0x180001197  mov     r8d, 1
0x18000119d  mov     [rbp+70h+var_30], rdx
0x1800011a1  mov     [rbp+70h+var_24], ebx
0x1800011a4  mov     rdx, [rax]
0x1800011a7  test    rdx, rdx
0x1800011aa  jz      short loc_1800011BB
0x1800011ac  mov     rax, rcx
0x1800011af  inc     rax
0x1800011b2  cmp     [rdx+rax], bl
0x1800011b5  jnz     short loc_1800011AF
0x1800011b7  inc     eax
0x1800011b9  jmp     short loc_1800011C1
0x1800011bb  mov     rdx, rdi
0x1800011be  mov     eax, r8d
0x1800011c1  mov     [rbp+70h+var_38], eax
0x1800011c4  mov     rax, [rbp+70h+arg_88]
0x1800011cb  mov     [rbp+70h+var_50], rax
0x1800011cf  mov     rax, [rbp+70h+arg_80]
0x1800011d6  mov     [rbp+70h+var_40], rdx
0x1800011da  mov     [rbp+70h+var_34], ebx
0x1800011dd  mov     [rbp+70h+var_48], 4
0x1800011e5  mov     rdx, [rax]
0x1800011e8  test    rdx, rdx
0x1800011eb  jz      short loc_180001202
0x1800011ed  mov     rax, rcx
0x1800011f0  inc     rax
0x1800011f3  cmp     [rdx+rax*2], bx
0x1800011f7  jnz     short loc_1800011F0
0x1800011f9  lea     eax, ds:2[rax*2]
0x180001200  jmp     short loc_18000120C
0x180001202  lea     rdx, dword_18000E6E4
0x180001209  mov     eax, r9d
0x18000120c  mov     [rbp+70h+var_58], eax
0x18000120f  mov     rax, [rbp+70h+arg_78]
0x180001216  mov     [rbp+70h+var_60], rdx
0x18000121a  mov     [rbp+70h+var_54], ebx
0x18000121d  mov     rdx, [rax]
0x180001220  test    rdx, rdx
0x180001223  jz      short loc_180001234
0x180001225  mov     rax, rcx
0x180001228  inc     rax
0x18000122b  cmp     [rdx+rax], bl
0x18000122e  jnz     short loc_180001228
0x180001230  inc     eax
0x180001232  jmp     short loc_18000123A
0x180001234  mov     rdx, rdi
0x180001237  mov     eax, r8d
0x18000123a  mov     [rbp+70h+var_68], eax
0x18000123d  mov     rax, [rbp+70h+arg_70]
0x180001244  mov     [rbp+70h+var_80], rax
0x180001248  mov     rax, [rbp+70h+arg_68]
0x18000124f  mov     [rbp+70h+var_70], rdx
0x180001253  mov     [rbp+70h+var_64], ebx
0x180001256  mov     [rbp+70h+var_78], 4
0x18000125e  mov     rdx, [rax]
0x180001261  test    rdx, rdx
0x180001264  jz      short loc_180001275
0x180001266  mov     rax, rcx
0x180001269  inc     rax
0x18000126c  cmp     [rdx+rax], bl
0x18000126f  jnz     short loc_180001269
0x180001271  inc     eax
0x180001273  jmp     short loc_18000127B
0x180001275  mov     rdx, rdi
0x180001278  mov     eax, r8d
0x18000127b  mov     [rbp+70h+var_88], eax
0x18000127e  mov     rax, [rbp+70h+arg_60]
0x180001285  mov     [rbp+70h+var_A0], rax
0x180001289  mov     rax, [rbp+70h+arg_58]
0x180001290  mov     [rbp+70h+var_90], rdx
0x180001294  mov     [rbp+70h+var_84], ebx
0x180001297  mov     [rbp+70h+var_98], 4
0x18000129f  mov     rdx, [rax]
0x1800012a2  test    rdx, rdx
0x1800012a5  jz      short loc_1800012BD
0x1800012a7  mov     rax, rcx
0x1800012aa  inc     rax
0x1800012ad  cmp     [rdx+rax*2], bx
0x1800012b1  jnz     short loc_1800012AA
0x1800012b3  lea     r9d, ds:2[rax*2]
0x1800012bb  jmp     short loc_1800012C4
0x1800012bd  lea     rdx, dword_18000E6E4
0x1800012c4  mov     rax, [rbp+70h+arg_50]
0x1800012cb  mov     [rbp+70h+var_C0], rax
0x1800012cf  mov     rax, [rbp+70h+arg_48]
0x1800012d6  mov     [rbp+70h+var_B0], rdx
0x1800012da  mov     [rbp+70h+var_A8], r9d
0x1800012de  mov     [rbp+70h+var_A4], ebx
0x1800012e1  mov     rdx, [rax]
0x1800012e4  mov     [rbp+70h+var_B8], 4
0x1800012ec  test    rdx, rdx
0x1800012ef  jz      short loc_180001300
0x1800012f1  mov     rax, rcx
0x1800012f4  inc     rax
0x1800012f7  cmp     [rdx+rax], bl
0x1800012fa  jnz     short loc_1800012F4
0x1800012fc  inc     eax
0x1800012fe  jmp     short loc_180001306
0x180001300  mov     rdx, rdi
0x180001303  mov     eax, r8d
0x180001306  mov     [rbp+70h+var_C8], eax
0x180001309  mov     rax, [rbp+70h+arg_40]
0x180001310  mov     [rbp+70h+var_E0], rax
0x180001314  mov     rax, [rbp+70h+arg_38]
0x18000131b  mov     [rbp+70h+var_D0], rdx
0x18000131f  mov     [rbp+70h+var_C4], ebx
0x180001322  mov     [rbp+70h+var_D8], 4
0x18000132a  mov     rdx, [rax]
0x18000132d  test    rdx, rdx
0x180001330  jz      short loc_180001340
0x180001332  inc     rcx
0x180001335  cmp     [rdx+rcx], bl
0x180001338  jnz     short loc_180001332
0x18000133a  lea     r8d, [rcx+1]
0x18000133e  jmp     short loc_180001343
0x180001340  mov     rdx, rdi
0x180001343  mov     rax, [rbp+70h+arg_30]
0x18000134a  xor     r9d, r9d
0x18000134d  mov     [rsp+170h+var_100], rax
0x180001352  mov     rcx, r10
0x180001355  mov     rax, [rbp+70h+arg_28]
0x18000135c  mov     [rsp+170h+var_110], rax
0x180001361  mov     rax, [rbp+70h+arg_20]
0x180001368  mov     [rsp+170h+var_120], rax
0x18000136d  lea     rax, [rsp+170h+var_140]
0x180001372  mov     [rbp+70h+var_F0], rdx
0x180001376  mov     rdx, r11
0x180001379  mov     [rbp+70h+var_E8], r8d
0x18000137d  xor     r8d, r8d
0x180001380  mov     [rsp+170h+var_148], rax
0x180001385  mov     [rsp+170h+var_150], 12h
0x18000138d  mov     [rbp+70h+var_E4], ebx
0x180001390  mov     [rsp+170h+var_F8], 4
0x180001399  mov     [rsp+170h+var_108], 8
0x1800013a2  mov     [rsp+170h+var_118], 8
0x1800013ab  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013b0  mov     rcx, [rbp+70h+var_20]
0x1800013b4  xor     rcx, rsp; StackCookie
0x1800013b7  call    __security_check_cookie
0x1800013bc  mov     rbx, [rsp+170h+arg_10]
0x1800013c4  add     rsp, 160h
0x1800013cb  pop     rdi
0x1800013cc  pop     rsi
0x1800013cd  pop     rbp
0x1800013ce  retn
```
