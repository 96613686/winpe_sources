# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180003e84`
- end: `0x180004174`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180027e30`
- `0x180029554`

## callees

- `0x180001010`
- `0x180003e84`
- `0x1800050f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v26; // r8d
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  int *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  int *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  _BYTE v53[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  int *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  int *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  int *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v96; // [rsp+160h] [rbp+60h]
  int v97; // [rsp+168h] [rbp+68h]
  int v98; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v26 = 1;
  v27 = *a22;
  if ( *a22 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &byte_180031EE0;
    v29 = 1;
  }
  v97 = v29;
  v30 = 2;
  v94 = a21;
  v92 = a20;
  v96 = v27;
  v98 = 0;
  v95 = 4;
  v31 = *a19;
  v93 = 4;
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_180031EE4;
    v33 = 2;
  }
  v90 = v33;
  v89 = v31;
  v91 = 0;
  v34 = *a18;
  if ( *a18 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &byte_180031EE0;
    v36 = 1;
  }
  v87 = v36;
  v84 = a17;
  v86 = v34;
  v88 = 0;
  v85 = 4;
  v37 = *a16;
  if ( *a16 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &dword_180031EE4;
    v39 = 2;
  }
  v82 = v39;
  v81 = v37;
  v83 = 0;
  v40 = *a15;
  if ( *a15 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &byte_180031EE0;
    v42 = 1;
  }
  v79 = v42;
  v76 = a14;
  v78 = v40;
  v80 = 0;
  v77 = 4;
  v43 = *a13;
  if ( *a13 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &byte_180031EE0;
    v45 = 1;
  }
  v74 = v45;
  v71 = a12;
  v73 = v43;
  v75 = 0;
  v72 = 4;
  v46 = *a11;
  if ( *a11 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_WORD *)v46 + v47) );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &dword_180031EE4;
  }
  v66 = a10;
  v68 = v46;
  v69 = v30;
  v70 = 0;
  v48 = *a9;
  v67 = 4;
  if ( v48 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &byte_180031EE0;
    v50 = 1;
  }
  v64 = v50;
  v61 = a8;
  v63 = v48;
  v65 = 0;
  v62 = 4;
  v51 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v51 + v24) );
    v26 = v24 + 1;
  }
  else
  {
    v51 = &byte_180031EE0;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 20, v53);
}

```

## disassembly

```asm
0x180003e84  push    rbp
0x180003e86  push    rbx
0x180003e87  push    rsi
0x180003e88  push    rdi
0x180003e89  push    r15
0x180003e8b  lea     rbp, [rsp-80h]
0x180003e90  sub     rsp, 180h
0x180003e97  mov     rax, cs:__security_cookie
0x180003e9e  xor     rax, rsp
0x180003ea1  mov     [rbp+0A0h+var_30], rax
0x180003ea5  mov     rax, [rbp+0A0h+arg_A8]
0x180003eac  lea     rsi, byte_180031EE0
0x180003eb3  mov     r11, rdx
0x180003eb6  mov     r10, rcx
0x180003eb9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180003ebd  xor     edi, edi
0x180003ebf  mov     rbx, r8
0x180003ec2  mov     r8d, 1
0x180003ec8  mov     rcx, [rax]
0x180003ecb  test    rcx, rcx
0x180003ece  jz      short loc_180003EE0
0x180003ed0  mov     rax, rdx
0x180003ed3  inc     rax
0x180003ed6  cmp     [rcx+rax], dil
0x180003eda  jnz     short loc_180003ED3
0x180003edc  inc     eax
0x180003ede  jmp     short loc_180003EE6
0x180003ee0  mov     rcx, rsi
0x180003ee3  mov     eax, r8d
0x180003ee6  mov     [rbp+0A0h+var_38], eax
0x180003ee9  mov     r9d, 2
0x180003eef  mov     rax, [rbp+0A0h+arg_A0]
0x180003ef6  mov     [rbp+0A0h+var_50], rax
0x180003efa  mov     rax, [rbp+0A0h+arg_98]
0x180003f01  mov     [rbp+0A0h+var_60], rax
0x180003f05  mov     rax, [rbp+0A0h+arg_90]
0x180003f0c  mov     [rbp+0A0h+var_40], rcx
0x180003f10  mov     [rbp+0A0h+var_34], edi
0x180003f13  mov     [rbp+0A0h+var_48], 4
0x180003f1b  mov     rcx, [rax]
0x180003f1e  mov     [rbp+0A0h+var_58], 4
0x180003f26  test    rcx, rcx
0x180003f29  jz      short loc_180003F40
0x180003f2b  mov     rax, rdx
0x180003f2e  inc     rax
0x180003f31  cmp     [rcx+rax*2], di
0x180003f35  jnz     short loc_180003F2E
0x180003f37  lea     eax, ds:2[rax*2]
0x180003f3e  jmp     short loc_180003F4A
0x180003f40  lea     rcx, dword_180031EE4
0x180003f47  mov     eax, r9d
0x180003f4a  mov     [rbp+0A0h+var_68], eax
0x180003f4d  mov     rax, [rbp+0A0h+arg_88]
0x180003f54  mov     [rbp+0A0h+var_70], rcx
0x180003f58  mov     [rbp+0A0h+var_64], edi
0x180003f5b  mov     rcx, [rax]
0x180003f5e  test    rcx, rcx
0x180003f61  jz      short loc_180003F73
0x180003f63  mov     rax, rdx
0x180003f66  inc     rax
0x180003f69  cmp     [rcx+rax], dil
0x180003f6d  jnz     short loc_180003F66
0x180003f6f  inc     eax
0x180003f71  jmp     short loc_180003F79
0x180003f73  mov     rcx, rsi
0x180003f76  mov     eax, r8d
0x180003f79  mov     [rbp+0A0h+var_78], eax
0x180003f7c  mov     rax, [rbp+0A0h+arg_80]
0x180003f83  mov     [rbp+0A0h+var_90], rax
0x180003f87  mov     rax, [rbp+0A0h+arg_78]
0x180003f8e  mov     [rbp+0A0h+var_80], rcx
0x180003f92  mov     [rbp+0A0h+var_74], edi
0x180003f95  mov     [rbp+0A0h+var_88], 4
0x180003f9d  mov     rcx, [rax]
0x180003fa0  test    rcx, rcx
0x180003fa3  jz      short loc_180003FBA
0x180003fa5  mov     rax, rdx
0x180003fa8  inc     rax
0x180003fab  cmp     [rcx+rax*2], di
0x180003faf  jnz     short loc_180003FA8
0x180003fb1  lea     eax, ds:2[rax*2]
0x180003fb8  jmp     short loc_180003FC4
0x180003fba  lea     rcx, dword_180031EE4
0x180003fc1  mov     eax, r9d
0x180003fc4  mov     [rbp+0A0h+var_98], eax
0x180003fc7  mov     rax, [rbp+0A0h+arg_70]
0x180003fce  mov     [rbp+0A0h+var_A0], rcx
0x180003fd2  mov     [rbp+0A0h+var_94], edi
0x180003fd5  mov     rcx, [rax]
0x180003fd8  test    rcx, rcx
0x180003fdb  jz      short loc_180003FED
0x180003fdd  mov     rax, rdx
0x180003fe0  inc     rax
0x180003fe3  cmp     [rcx+rax], dil
0x180003fe7  jnz     short loc_180003FE0
0x180003fe9  inc     eax
0x180003feb  jmp     short loc_180003FF3
0x180003fed  mov     rcx, rsi
0x180003ff0  mov     eax, r8d
0x180003ff3  mov     [rbp+0A0h+var_A8], eax
0x180003ff6  mov     rax, [rbp+0A0h+arg_68]
0x180003ffd  mov     [rbp+0A0h+var_C0], rax
0x180004001  mov     rax, [rbp+0A0h+arg_60]
0x180004008  mov     [rbp+0A0h+var_B0], rcx
0x18000400c  mov     [rbp+0A0h+var_A4], edi
0x18000400f  mov     [rbp+0A0h+var_B8], 4
0x180004017  mov     rcx, [rax]
0x18000401a  test    rcx, rcx
0x18000401d  jz      short loc_18000402F
0x18000401f  mov     rax, rdx
0x180004022  inc     rax
0x180004025  cmp     [rcx+rax], dil
0x180004029  jnz     short loc_180004022
0x18000402b  inc     eax
0x18000402d  jmp     short loc_180004035
0x18000402f  mov     rcx, rsi
0x180004032  mov     eax, r8d
0x180004035  mov     [rbp+0A0h+var_C8], eax
0x180004038  mov     rax, [rbp+0A0h+arg_58]
0x18000403f  mov     [rbp+0A0h+var_E0], rax
0x180004043  mov     rax, [rbp+0A0h+arg_50]
0x18000404a  mov     [rbp+0A0h+var_D0], rcx
0x18000404e  mov     [rbp+0A0h+var_C4], edi
0x180004051  mov     [rbp+0A0h+var_D8], 4
0x180004059  mov     rcx, [rax]
0x18000405c  test    rcx, rcx
0x18000405f  jz      short loc_180004077
0x180004061  mov     rax, rdx
0x180004064  inc     rax
0x180004067  cmp     [rcx+rax*2], di
0x18000406b  jnz     short loc_180004064
0x18000406d  lea     r9d, ds:2[rax*2]
0x180004075  jmp     short loc_18000407E
0x180004077  lea     rcx, dword_180031EE4
0x18000407e  mov     rax, [rbp+0A0h+arg_48]
0x180004085  mov     [rbp+0A0h+var_100], rax
0x180004089  mov     rax, [rbp+0A0h+arg_40]
0x180004090  mov     [rbp+0A0h+var_F0], rcx
0x180004094  mov     [rbp+0A0h+var_E8], r9d
0x180004098  mov     [rbp+0A0h+var_E4], edi
0x18000409b  mov     rcx, [rax]
0x18000409e  mov     [rbp+0A0h+var_F8], 4
0x1800040a6  test    rcx, rcx
0x1800040a9  jz      short loc_1800040BB
0x1800040ab  mov     rax, rdx
0x1800040ae  inc     rax
0x1800040b1  cmp     [rcx+rax], dil
0x1800040b5  jnz     short loc_1800040AE
0x1800040b7  inc     eax
0x1800040b9  jmp     short loc_1800040C1
0x1800040bb  mov     rcx, rsi
0x1800040be  mov     eax, r8d
0x1800040c1  mov     [rbp+0A0h+var_108], eax
0x1800040c4  mov     rax, [rbp+0A0h+arg_38]
0x1800040cb  mov     [rbp+0A0h+var_120], rax
0x1800040cf  mov     rax, [rbp+0A0h+arg_30]
0x1800040d6  mov     [rbp+0A0h+var_110], rcx
0x1800040da  mov     [rbp+0A0h+var_104], edi
0x1800040dd  mov     [rbp+0A0h+var_118], 4
0x1800040e5  mov     rcx, [rax]
0x1800040e8  test    rcx, rcx
0x1800040eb  jz      short loc_1800040FC
0x1800040ed  inc     rdx
0x1800040f0  cmp     [rcx+rdx], dil
0x1800040f4  jnz     short loc_1800040ED
0x1800040f6  lea     r8d, [rdx+1]
0x1800040fa  jmp     short loc_1800040FF
0x1800040fc  mov     rcx, rsi
0x1800040ff  mov     rax, [rbp+0A0h+arg_28]
0x180004106  xor     r9d, r9d
0x180004109  mov     [rsp+1A0h+var_140], rax
0x18000410e  mov     rdx, r11
0x180004111  mov     rax, [rbp+0A0h+arg_20]
0x180004118  mov     [rsp+1A0h+var_150], rax
0x18000411d  lea     rax, [rsp+1A0h+var_170]
0x180004122  mov     [rsp+1A0h+var_130], rcx
0x180004127  mov     rcx, r10
0x18000412a  mov     [rsp+1A0h+var_128], r8d
0x18000412f  mov     r8, rbx
0x180004132  mov     [rsp+1A0h+var_178], rax
0x180004137  mov     [rsp+1A0h+var_180], 14h
0x18000413f  mov     [rsp+1A0h+var_124], edi
0x180004143  mov     [rsp+1A0h+var_138], 4
0x18000414c  mov     [rsp+1A0h+var_148], 8
0x180004155  call    _tlgWriteTransfer_EventWriteTransfer
0x18000415a  mov     rcx, [rbp+0A0h+var_30]
0x18000415e  xor     rcx, rsp; StackCookie
0x180004161  call    __security_check_cookie
0x180004166  add     rsp, 180h
0x18000416d  pop     r15
0x18000416f  pop     rdi
0x180004170  pop     rsi
0x180004171  pop     rbx
0x180004172  pop     rbp
0x180004173  retn
```
