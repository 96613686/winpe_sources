# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800018fc`
- end: `0x180001bec`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b8a0`
- `0x18002d8c0`

## callees

- `0x1800018fc`
- `0x180001c7c`
- `0x1800350e0`

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
    v27 = &byte_18003D198;
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
    v31 = &dword_18003D19C;
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
    v34 = &byte_18003D198;
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
    v37 = &dword_18003D19C;
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
    v40 = &byte_18003D198;
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
    v43 = &byte_18003D198;
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
    v46 = &dword_18003D19C;
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
    v48 = &byte_18003D198;
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
    v51 = &byte_18003D198;
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
0x1800018fc  push    rbp
0x1800018fe  push    rbx
0x1800018ff  push    rsi
0x180001900  push    rdi
0x180001901  push    r15
0x180001903  lea     rbp, [rsp-80h]
0x180001908  sub     rsp, 180h
0x18000190f  mov     rax, cs:__security_cookie
0x180001916  xor     rax, rsp
0x180001919  mov     [rbp+0A0h+var_30], rax
0x18000191d  mov     rax, [rbp+0A0h+arg_A8]
0x180001924  lea     rsi, byte_18003D198
0x18000192b  mov     r11, rdx
0x18000192e  mov     r10, rcx
0x180001931  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001935  xor     edi, edi
0x180001937  mov     rbx, r8
0x18000193a  mov     r8d, 1
0x180001940  mov     rcx, [rax]
0x180001943  test    rcx, rcx
0x180001946  jz      short loc_180001958
0x180001948  mov     rax, rdx
0x18000194b  inc     rax
0x18000194e  cmp     [rcx+rax], dil
0x180001952  jnz     short loc_18000194B
0x180001954  inc     eax
0x180001956  jmp     short loc_18000195E
0x180001958  mov     rcx, rsi
0x18000195b  mov     eax, r8d
0x18000195e  mov     [rbp+0A0h+var_38], eax
0x180001961  mov     r9d, 2
0x180001967  mov     rax, [rbp+0A0h+arg_A0]
0x18000196e  mov     [rbp+0A0h+var_50], rax
0x180001972  mov     rax, [rbp+0A0h+arg_98]
0x180001979  mov     [rbp+0A0h+var_60], rax
0x18000197d  mov     rax, [rbp+0A0h+arg_90]
0x180001984  mov     [rbp+0A0h+var_40], rcx
0x180001988  mov     [rbp+0A0h+var_34], edi
0x18000198b  mov     [rbp+0A0h+var_48], 4
0x180001993  mov     rcx, [rax]
0x180001996  mov     [rbp+0A0h+var_58], 4
0x18000199e  test    rcx, rcx
0x1800019a1  jz      short loc_1800019B8
0x1800019a3  mov     rax, rdx
0x1800019a6  inc     rax
0x1800019a9  cmp     [rcx+rax*2], di
0x1800019ad  jnz     short loc_1800019A6
0x1800019af  lea     eax, ds:2[rax*2]
0x1800019b6  jmp     short loc_1800019C2
0x1800019b8  lea     rcx, dword_18003D19C
0x1800019bf  mov     eax, r9d
0x1800019c2  mov     [rbp+0A0h+var_68], eax
0x1800019c5  mov     rax, [rbp+0A0h+arg_88]
0x1800019cc  mov     [rbp+0A0h+var_70], rcx
0x1800019d0  mov     [rbp+0A0h+var_64], edi
0x1800019d3  mov     rcx, [rax]
0x1800019d6  test    rcx, rcx
0x1800019d9  jz      short loc_1800019EB
0x1800019db  mov     rax, rdx
0x1800019de  inc     rax
0x1800019e1  cmp     [rcx+rax], dil
0x1800019e5  jnz     short loc_1800019DE
0x1800019e7  inc     eax
0x1800019e9  jmp     short loc_1800019F1
0x1800019eb  mov     rcx, rsi
0x1800019ee  mov     eax, r8d
0x1800019f1  mov     [rbp+0A0h+var_78], eax
0x1800019f4  mov     rax, [rbp+0A0h+arg_80]
0x1800019fb  mov     [rbp+0A0h+var_90], rax
0x1800019ff  mov     rax, [rbp+0A0h+arg_78]
0x180001a06  mov     [rbp+0A0h+var_80], rcx
0x180001a0a  mov     [rbp+0A0h+var_74], edi
0x180001a0d  mov     [rbp+0A0h+var_88], 4
0x180001a15  mov     rcx, [rax]
0x180001a18  test    rcx, rcx
0x180001a1b  jz      short loc_180001A32
0x180001a1d  mov     rax, rdx
0x180001a20  inc     rax
0x180001a23  cmp     [rcx+rax*2], di
0x180001a27  jnz     short loc_180001A20
0x180001a29  lea     eax, ds:2[rax*2]
0x180001a30  jmp     short loc_180001A3C
0x180001a32  lea     rcx, dword_18003D19C
0x180001a39  mov     eax, r9d
0x180001a3c  mov     [rbp+0A0h+var_98], eax
0x180001a3f  mov     rax, [rbp+0A0h+arg_70]
0x180001a46  mov     [rbp+0A0h+var_A0], rcx
0x180001a4a  mov     [rbp+0A0h+var_94], edi
0x180001a4d  mov     rcx, [rax]
0x180001a50  test    rcx, rcx
0x180001a53  jz      short loc_180001A65
0x180001a55  mov     rax, rdx
0x180001a58  inc     rax
0x180001a5b  cmp     [rcx+rax], dil
0x180001a5f  jnz     short loc_180001A58
0x180001a61  inc     eax
0x180001a63  jmp     short loc_180001A6B
0x180001a65  mov     rcx, rsi
0x180001a68  mov     eax, r8d
0x180001a6b  mov     [rbp+0A0h+var_A8], eax
0x180001a6e  mov     rax, [rbp+0A0h+arg_68]
0x180001a75  mov     [rbp+0A0h+var_C0], rax
0x180001a79  mov     rax, [rbp+0A0h+arg_60]
0x180001a80  mov     [rbp+0A0h+var_B0], rcx
0x180001a84  mov     [rbp+0A0h+var_A4], edi
0x180001a87  mov     [rbp+0A0h+var_B8], 4
0x180001a8f  mov     rcx, [rax]
0x180001a92  test    rcx, rcx
0x180001a95  jz      short loc_180001AA7
0x180001a97  mov     rax, rdx
0x180001a9a  inc     rax
0x180001a9d  cmp     [rcx+rax], dil
0x180001aa1  jnz     short loc_180001A9A
0x180001aa3  inc     eax
0x180001aa5  jmp     short loc_180001AAD
0x180001aa7  mov     rcx, rsi
0x180001aaa  mov     eax, r8d
0x180001aad  mov     [rbp+0A0h+var_C8], eax
0x180001ab0  mov     rax, [rbp+0A0h+arg_58]
0x180001ab7  mov     [rbp+0A0h+var_E0], rax
0x180001abb  mov     rax, [rbp+0A0h+arg_50]
0x180001ac2  mov     [rbp+0A0h+var_D0], rcx
0x180001ac6  mov     [rbp+0A0h+var_C4], edi
0x180001ac9  mov     [rbp+0A0h+var_D8], 4
0x180001ad1  mov     rcx, [rax]
0x180001ad4  test    rcx, rcx
0x180001ad7  jz      short loc_180001AEF
0x180001ad9  mov     rax, rdx
0x180001adc  inc     rax
0x180001adf  cmp     [rcx+rax*2], di
0x180001ae3  jnz     short loc_180001ADC
0x180001ae5  lea     r9d, ds:2[rax*2]
0x180001aed  jmp     short loc_180001AF6
0x180001aef  lea     rcx, dword_18003D19C
0x180001af6  mov     rax, [rbp+0A0h+arg_48]
0x180001afd  mov     [rbp+0A0h+var_100], rax
0x180001b01  mov     rax, [rbp+0A0h+arg_40]
0x180001b08  mov     [rbp+0A0h+var_F0], rcx
0x180001b0c  mov     [rbp+0A0h+var_E8], r9d
0x180001b10  mov     [rbp+0A0h+var_E4], edi
0x180001b13  mov     rcx, [rax]
0x180001b16  mov     [rbp+0A0h+var_F8], 4
0x180001b1e  test    rcx, rcx
0x180001b21  jz      short loc_180001B33
0x180001b23  mov     rax, rdx
0x180001b26  inc     rax
0x180001b29  cmp     [rcx+rax], dil
0x180001b2d  jnz     short loc_180001B26
0x180001b2f  inc     eax
0x180001b31  jmp     short loc_180001B39
0x180001b33  mov     rcx, rsi
0x180001b36  mov     eax, r8d
0x180001b39  mov     [rbp+0A0h+var_108], eax
0x180001b3c  mov     rax, [rbp+0A0h+arg_38]
0x180001b43  mov     [rbp+0A0h+var_120], rax
0x180001b47  mov     rax, [rbp+0A0h+arg_30]
0x180001b4e  mov     [rbp+0A0h+var_110], rcx
0x180001b52  mov     [rbp+0A0h+var_104], edi
0x180001b55  mov     [rbp+0A0h+var_118], 4
0x180001b5d  mov     rcx, [rax]
0x180001b60  test    rcx, rcx
0x180001b63  jz      short loc_180001B74
0x180001b65  inc     rdx
0x180001b68  cmp     [rcx+rdx], dil
0x180001b6c  jnz     short loc_180001B65
0x180001b6e  lea     r8d, [rdx+1]
0x180001b72  jmp     short loc_180001B77
0x180001b74  mov     rcx, rsi
0x180001b77  mov     rax, [rbp+0A0h+arg_28]
0x180001b7e  xor     r9d, r9d
0x180001b81  mov     [rsp+1A0h+var_140], rax
0x180001b86  mov     rdx, r11
0x180001b89  mov     rax, [rbp+0A0h+arg_20]
0x180001b90  mov     [rsp+1A0h+var_150], rax
0x180001b95  lea     rax, [rsp+1A0h+var_170]
0x180001b9a  mov     [rsp+1A0h+var_130], rcx
0x180001b9f  mov     rcx, r10
0x180001ba2  mov     [rsp+1A0h+var_128], r8d
0x180001ba7  mov     r8, rbx
0x180001baa  mov     [rsp+1A0h+var_178], rax
0x180001baf  mov     [rsp+1A0h+var_180], 14h
0x180001bb7  mov     [rsp+1A0h+var_124], edi
0x180001bbb  mov     [rsp+1A0h+var_138], 4
0x180001bc4  mov     [rsp+1A0h+var_148], 8
0x180001bcd  call    _tlgWriteTransfer_EventWriteTransfer
0x180001bd2  mov     rcx, [rbp+0A0h+var_30]
0x180001bd6  xor     rcx, rsp; StackCookie
0x180001bd9  call    __security_check_cookie
0x180001bde  add     rsp, 180h
0x180001be5  pop     r15
0x180001be7  pop     rdi
0x180001be8  pop     rsi
0x180001be9  pop     rbx
0x180001bea  pop     rbp
0x180001beb  retn
```
