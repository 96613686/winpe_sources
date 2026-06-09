# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001210`
- end: `0x1400014bb`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e08c`

## callees

- `0x140001210`
- `0x140001898`
- `0x140008c80`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        const size_t **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const size_t **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const size_t **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  const size_t *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  const size_t *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  const size_t *v40; // rdx
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
  const size_t *v64; // [rsp+C0h] [rbp-40h]
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
  const size_t *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  const size_t *v85; // [rsp+140h] [rbp+40h]
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
    v24 = &Format;
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
    v28 = &dword_1400135E4;
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
    v31 = &Format;
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
    v34 = &dword_1400135E4;
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
    v37 = &dword_1400135E4;
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
    v40 = &Format;
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
    v42 = &dword_1400135E4;
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
    v45 = &dword_1400135E4;
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
  return tlgWriteTransfer_EtwEventWriteTransfer(a1, a2, 0, 0, 18, (__int64)v47);
}

```

## disassembly

```asm
0x140001210  mov     [rsp-8+arg_10], rbx
0x140001215  push    rbp
0x140001216  push    rsi
0x140001217  push    rdi
0x140001218  lea     rbp, [rsp-60h]
0x14000121d  sub     rsp, 160h
0x140001224  mov     rax, cs:__security_cookie
0x14000122b  xor     rax, rsp
0x14000122e  mov     [rbp+70h+var_20], rax
0x140001232  mov     rax, [rbp+70h+arg_98]
0x140001239  mov     r11, rdx
0x14000123c  mov     r10, rcx
0x14000123f  xor     ebx, ebx
0x140001241  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001245  mov     r9d, 2
0x14000124b  mov     rdx, [rax]
0x14000124e  test    rdx, rdx
0x140001251  jz      short loc_140001268
0x140001253  mov     rax, rcx
0x140001256  inc     rax
0x140001259  cmp     [rdx+rax*2], bx
0x14000125d  jnz     short loc_140001256
0x14000125f  lea     eax, ds:2[rax*2]
0x140001266  jmp     short loc_140001272
0x140001268  lea     rdx, Format
0x14000126f  mov     eax, r9d
0x140001272  mov     [rbp+70h+var_28], eax
0x140001275  lea     rdi, dword_1400135E4
0x14000127c  mov     rax, [rbp+70h+arg_90]
0x140001283  mov     r8d, 1
0x140001289  mov     [rbp+70h+var_30], rdx
0x14000128d  mov     [rbp+70h+var_24], ebx
0x140001290  mov     rdx, [rax]
0x140001293  test    rdx, rdx
0x140001296  jz      short loc_1400012A7
0x140001298  mov     rax, rcx
0x14000129b  inc     rax
0x14000129e  cmp     [rdx+rax], bl
0x1400012a1  jnz     short loc_14000129B
0x1400012a3  inc     eax
0x1400012a5  jmp     short loc_1400012AD
0x1400012a7  mov     rdx, rdi
0x1400012aa  mov     eax, r8d
0x1400012ad  mov     [rbp+70h+var_38], eax
0x1400012b0  mov     rax, [rbp+70h+arg_88]
0x1400012b7  mov     [rbp+70h+var_50], rax
0x1400012bb  mov     rax, [rbp+70h+arg_80]
0x1400012c2  mov     [rbp+70h+var_40], rdx
0x1400012c6  mov     [rbp+70h+var_34], ebx
0x1400012c9  mov     [rbp+70h+var_48], 4
0x1400012d1  mov     rdx, [rax]
0x1400012d4  test    rdx, rdx
0x1400012d7  jz      short loc_1400012EE
0x1400012d9  mov     rax, rcx
0x1400012dc  inc     rax
0x1400012df  cmp     [rdx+rax*2], bx
0x1400012e3  jnz     short loc_1400012DC
0x1400012e5  lea     eax, ds:2[rax*2]
0x1400012ec  jmp     short loc_1400012F8
0x1400012ee  lea     rdx, Format
0x1400012f5  mov     eax, r9d
0x1400012f8  mov     [rbp+70h+var_58], eax
0x1400012fb  mov     rax, [rbp+70h+arg_78]
0x140001302  mov     [rbp+70h+var_60], rdx
0x140001306  mov     [rbp+70h+var_54], ebx
0x140001309  mov     rdx, [rax]
0x14000130c  test    rdx, rdx
0x14000130f  jz      short loc_140001320
0x140001311  mov     rax, rcx
0x140001314  inc     rax
0x140001317  cmp     [rdx+rax], bl
0x14000131a  jnz     short loc_140001314
0x14000131c  inc     eax
0x14000131e  jmp     short loc_140001326
0x140001320  mov     rdx, rdi
0x140001323  mov     eax, r8d
0x140001326  mov     [rbp+70h+var_68], eax
0x140001329  mov     rax, [rbp+70h+arg_70]
0x140001330  mov     [rbp+70h+var_80], rax
0x140001334  mov     rax, [rbp+70h+arg_68]
0x14000133b  mov     [rbp+70h+var_70], rdx
0x14000133f  mov     [rbp+70h+var_64], ebx
0x140001342  mov     [rbp+70h+var_78], 4
0x14000134a  mov     rdx, [rax]
0x14000134d  test    rdx, rdx
0x140001350  jz      short loc_140001361
0x140001352  mov     rax, rcx
0x140001355  inc     rax
0x140001358  cmp     [rdx+rax], bl
0x14000135b  jnz     short loc_140001355
0x14000135d  inc     eax
0x14000135f  jmp     short loc_140001367
0x140001361  mov     rdx, rdi
0x140001364  mov     eax, r8d
0x140001367  mov     [rbp+70h+var_88], eax
0x14000136a  mov     rax, [rbp+70h+arg_60]
0x140001371  mov     [rbp+70h+var_A0], rax
0x140001375  mov     rax, [rbp+70h+arg_58]
0x14000137c  mov     [rbp+70h+var_90], rdx
0x140001380  mov     [rbp+70h+var_84], ebx
0x140001383  mov     [rbp+70h+var_98], 4
0x14000138b  mov     rdx, [rax]
0x14000138e  test    rdx, rdx
0x140001391  jz      short loc_1400013A9
0x140001393  mov     rax, rcx
0x140001396  inc     rax
0x140001399  cmp     [rdx+rax*2], bx
0x14000139d  jnz     short loc_140001396
0x14000139f  lea     r9d, ds:2[rax*2]
0x1400013a7  jmp     short loc_1400013B0
0x1400013a9  lea     rdx, Format
0x1400013b0  mov     rax, [rbp+70h+arg_50]
0x1400013b7  mov     [rbp+70h+var_C0], rax
0x1400013bb  mov     rax, [rbp+70h+arg_48]
0x1400013c2  mov     [rbp+70h+var_B0], rdx
0x1400013c6  mov     [rbp+70h+var_A8], r9d
0x1400013ca  mov     [rbp+70h+var_A4], ebx
0x1400013cd  mov     rdx, [rax]
0x1400013d0  mov     [rbp+70h+var_B8], 4
0x1400013d8  test    rdx, rdx
0x1400013db  jz      short loc_1400013EC
0x1400013dd  mov     rax, rcx
0x1400013e0  inc     rax
0x1400013e3  cmp     [rdx+rax], bl
0x1400013e6  jnz     short loc_1400013E0
0x1400013e8  inc     eax
0x1400013ea  jmp     short loc_1400013F2
0x1400013ec  mov     rdx, rdi
0x1400013ef  mov     eax, r8d
0x1400013f2  mov     [rbp+70h+var_C8], eax
0x1400013f5  mov     rax, [rbp+70h+arg_40]
0x1400013fc  mov     [rbp+70h+var_E0], rax
0x140001400  mov     rax, [rbp+70h+arg_38]
0x140001407  mov     [rbp+70h+var_D0], rdx
0x14000140b  mov     [rbp+70h+var_C4], ebx
0x14000140e  mov     [rbp+70h+var_D8], 4
0x140001416  mov     rdx, [rax]
0x140001419  test    rdx, rdx
0x14000141c  jz      short loc_14000142C
0x14000141e  inc     rcx
0x140001421  cmp     [rdx+rcx], bl
0x140001424  jnz     short loc_14000141E
0x140001426  lea     r8d, [rcx+1]
0x14000142a  jmp     short loc_14000142F
0x14000142c  mov     rdx, rdi
0x14000142f  mov     rax, [rbp+70h+arg_30]
0x140001436  xor     r9d, r9d
0x140001439  mov     [rsp+170h+var_100], rax
0x14000143e  mov     rcx, r10
0x140001441  mov     rax, [rbp+70h+arg_28]
0x140001448  mov     [rsp+170h+var_110], rax
0x14000144d  mov     rax, [rbp+70h+arg_20]
0x140001454  mov     [rsp+170h+var_120], rax
0x140001459  lea     rax, [rsp+170h+var_140]
0x14000145e  mov     [rbp+70h+var_F0], rdx
0x140001462  mov     rdx, r11
0x140001465  mov     [rbp+70h+var_E8], r8d
0x140001469  xor     r8d, r8d
0x14000146c  mov     [rsp+170h+var_148], rax
0x140001471  mov     [rsp+170h+var_150], 12h
0x140001479  mov     [rbp+70h+var_E4], ebx
0x14000147c  mov     [rsp+170h+var_F8], 4
0x140001485  mov     [rsp+170h+var_108], 8
0x14000148e  mov     [rsp+170h+var_118], 8
0x140001497  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x14000149c  mov     rcx, [rbp+70h+var_20]
0x1400014a0  xor     rcx, rsp; StackCookie
0x1400014a3  call    __security_check_cookie
0x1400014a8  mov     rbx, [rsp+170h+arg_10]
0x1400014b0  add     rsp, 160h
0x1400014b7  pop     rdi
0x1400014b8  pop     rsi
0x1400014b9  pop     rbp
0x1400014ba  retn
```
