# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001430`
- end: `0x1800016cb`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800097b0`

## callees

- `0x180001430`
- `0x180001a4c`
- `0x180002300`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        int **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  int *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rcx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+7Ch] [rbp-84h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  int *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  int *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  int *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]

  v21 = -1;
  v23 = 2;
  v24 = *a19;
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &dword_180013CCC;
    v26 = 2;
  }
  v84 = v26;
  v27 = 1;
  v83 = v24;
  v85 = 0;
  v28 = *a18;
  if ( *a18 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &byte_180013CC8;
    v30 = 1;
  }
  v81 = v30;
  v78 = a17;
  v80 = v28;
  v82 = 0;
  v79 = 4;
  v31 = *a16;
  if ( *a16 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_180013CCC;
    v33 = 2;
  }
  v76 = v33;
  v75 = v31;
  v77 = 0;
  v34 = *a15;
  if ( *a15 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &byte_180013CC8;
    v36 = 1;
  }
  v73 = v36;
  v70 = a14;
  v72 = v34;
  v74 = 0;
  v71 = 4;
  v37 = *a13;
  if ( *a13 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &byte_180013CC8;
    v39 = 1;
  }
  v68 = v39;
  v65 = a12;
  v67 = v37;
  v69 = 0;
  v66 = 4;
  v40 = *a11;
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &dword_180013CCC;
  }
  v60 = a10;
  v62 = v40;
  v63 = v23;
  v64 = 0;
  v42 = *a9;
  v61 = 4;
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
    v42 = &byte_180013CC8;
    v44 = 1;
  }
  v58 = v44;
  v55 = a8;
  v57 = v42;
  v59 = 0;
  v56 = 4;
  v45 = *a7;
  if ( *a7 )
  {
    do
      ++v21;
    while ( *((_BYTE *)v45 + v21) );
    v27 = v21 + 1;
  }
  else
  {
    v45 = &byte_180013CC8;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 17, v47);
}

```

## disassembly

```asm
0x180001430  push    rbp
0x180001432  push    rbx
0x180001433  push    rsi
0x180001434  push    rdi
0x180001435  push    r14
0x180001437  lea     rbp, [rsp-50h]
0x18000143c  sub     rsp, 150h
0x180001443  mov     rax, cs:__security_cookie
0x18000144a  xor     rax, rsp
0x18000144d  mov     [rbp+70h+var_30], rax
0x180001451  mov     rax, [rbp+70h+arg_90]
0x180001458  mov     r11, rdx
0x18000145b  mov     r10, rcx
0x18000145e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001462  xor     edi, edi
0x180001464  mov     rbx, r8
0x180001467  mov     r9d, 2
0x18000146d  mov     rcx, [rax]
0x180001470  test    rcx, rcx
0x180001473  jz      short loc_18000148A
0x180001475  mov     rax, rdx
0x180001478  inc     rax
0x18000147b  cmp     [rcx+rax*2], di
0x18000147f  jnz     short loc_180001478
0x180001481  lea     eax, ds:2[rax*2]
0x180001488  jmp     short loc_180001494
0x18000148a  lea     rcx, dword_180013CCC
0x180001491  mov     eax, r9d
0x180001494  mov     [rbp+70h+var_38], eax
0x180001497  lea     rsi, byte_180013CC8
0x18000149e  mov     rax, [rbp+70h+arg_88]
0x1800014a5  mov     r8d, 1
0x1800014ab  mov     [rbp+70h+var_40], rcx
0x1800014af  mov     [rbp+70h+var_34], edi
0x1800014b2  mov     rcx, [rax]
0x1800014b5  test    rcx, rcx
0x1800014b8  jz      short loc_1800014CA
0x1800014ba  mov     rax, rdx
0x1800014bd  inc     rax
0x1800014c0  cmp     [rcx+rax], dil
0x1800014c4  jnz     short loc_1800014BD
0x1800014c6  inc     eax
0x1800014c8  jmp     short loc_1800014D0
0x1800014ca  mov     rcx, rsi
0x1800014cd  mov     eax, r8d
0x1800014d0  mov     [rbp+70h+var_48], eax
0x1800014d3  mov     rax, [rbp+70h+arg_80]
0x1800014da  mov     [rbp+70h+var_60], rax
0x1800014de  mov     rax, [rbp+70h+arg_78]
0x1800014e5  mov     [rbp+70h+var_50], rcx
0x1800014e9  mov     [rbp+70h+var_44], edi
0x1800014ec  mov     [rbp+70h+var_58], 4
0x1800014f4  mov     rcx, [rax]
0x1800014f7  test    rcx, rcx
0x1800014fa  jz      short loc_180001511
0x1800014fc  mov     rax, rdx
0x1800014ff  inc     rax
0x180001502  cmp     [rcx+rax*2], di
0x180001506  jnz     short loc_1800014FF
0x180001508  lea     eax, ds:2[rax*2]
0x18000150f  jmp     short loc_18000151B
0x180001511  lea     rcx, dword_180013CCC
0x180001518  mov     eax, r9d
0x18000151b  mov     [rbp+70h+var_68], eax
0x18000151e  mov     rax, [rbp+70h+arg_70]
0x180001525  mov     [rbp+70h+var_70], rcx
0x180001529  mov     [rbp+70h+var_64], edi
0x18000152c  mov     rcx, [rax]
0x18000152f  test    rcx, rcx
0x180001532  jz      short loc_180001544
0x180001534  mov     rax, rdx
0x180001537  inc     rax
0x18000153a  cmp     [rcx+rax], dil
0x18000153e  jnz     short loc_180001537
0x180001540  inc     eax
0x180001542  jmp     short loc_18000154A
0x180001544  mov     rcx, rsi
0x180001547  mov     eax, r8d
0x18000154a  mov     [rbp+70h+var_78], eax
0x18000154d  mov     rax, [rbp+70h+arg_68]
0x180001554  mov     [rbp+70h+var_90], rax
0x180001558  mov     rax, [rbp+70h+arg_60]
0x18000155f  mov     [rbp+70h+var_80], rcx
0x180001563  mov     [rbp+70h+var_74], edi
0x180001566  mov     [rbp+70h+var_88], 4
0x18000156e  mov     rcx, [rax]
0x180001571  test    rcx, rcx
0x180001574  jz      short loc_180001586
0x180001576  mov     rax, rdx
0x180001579  inc     rax
0x18000157c  cmp     [rcx+rax], dil
0x180001580  jnz     short loc_180001579
0x180001582  inc     eax
0x180001584  jmp     short loc_18000158C
0x180001586  mov     rcx, rsi
0x180001589  mov     eax, r8d
0x18000158c  mov     [rbp+70h+var_98], eax
0x18000158f  mov     rax, [rbp+70h+arg_58]
0x180001596  mov     [rbp+70h+var_B0], rax
0x18000159a  mov     rax, [rbp+70h+arg_50]
0x1800015a1  mov     [rbp+70h+var_A0], rcx
0x1800015a5  mov     [rbp+70h+var_94], edi
0x1800015a8  mov     [rbp+70h+var_A8], 4
0x1800015b0  mov     rcx, [rax]
0x1800015b3  test    rcx, rcx
0x1800015b6  jz      short loc_1800015CE
0x1800015b8  mov     rax, rdx
0x1800015bb  inc     rax
0x1800015be  cmp     [rcx+rax*2], di
0x1800015c2  jnz     short loc_1800015BB
0x1800015c4  lea     r9d, ds:2[rax*2]
0x1800015cc  jmp     short loc_1800015D5
0x1800015ce  lea     rcx, dword_180013CCC
0x1800015d5  mov     rax, [rbp+70h+arg_48]
0x1800015dc  mov     [rbp+70h+var_D0], rax
0x1800015e0  mov     rax, [rbp+70h+arg_40]
0x1800015e7  mov     [rbp+70h+var_C0], rcx
0x1800015eb  mov     [rbp+70h+var_B8], r9d
0x1800015ef  mov     [rbp+70h+var_B4], edi
0x1800015f2  mov     rcx, [rax]
0x1800015f5  mov     [rbp+70h+var_C8], 4
0x1800015fd  test    rcx, rcx
0x180001600  jz      short loc_180001612
0x180001602  mov     rax, rdx
0x180001605  inc     rax
0x180001608  cmp     [rcx+rax], dil
0x18000160c  jnz     short loc_180001605
0x18000160e  inc     eax
0x180001610  jmp     short loc_180001618
0x180001612  mov     rcx, rsi
0x180001615  mov     eax, r8d
0x180001618  mov     [rbp+70h+var_D8], eax
0x18000161b  mov     rax, [rbp+70h+arg_38]
0x180001622  mov     [rbp+70h+var_F0], rax
0x180001626  mov     rax, [rbp+70h+arg_30]
0x18000162d  mov     [rbp+70h+var_E0], rcx
0x180001631  mov     [rbp+70h+var_D4], edi
0x180001634  mov     [rbp+70h+var_E8], 4
0x18000163c  mov     rcx, [rax]
0x18000163f  test    rcx, rcx
0x180001642  jz      short loc_180001653
0x180001644  inc     rdx
0x180001647  cmp     [rcx+rdx], dil
0x18000164b  jnz     short loc_180001644
0x18000164d  lea     r8d, [rdx+1]
0x180001651  jmp     short loc_180001656
0x180001653  mov     rcx, rsi
0x180001656  mov     rax, [rbp+70h+arg_28]
0x18000165d  xor     r9d, r9d
0x180001660  mov     [rsp+170h+var_110], rax
0x180001665  mov     rdx, r11
0x180001668  mov     rax, [rbp+70h+arg_20]
0x18000166f  mov     [rsp+170h+var_120], rax
0x180001674  lea     rax, [rsp+170h+var_140]
0x180001679  mov     [rsp+170h+var_100], rcx
0x18000167e  mov     rcx, r10
0x180001681  mov     [rsp+170h+var_F8], r8d
0x180001686  mov     r8, rbx
0x180001689  mov     [rsp+170h+var_148], rax
0x18000168e  mov     [rsp+170h+var_150], 11h
0x180001696  mov     [rsp+170h+var_F4], edi
0x18000169a  mov     [rsp+170h+var_108], 4
0x1800016a3  mov     [rsp+170h+var_118], 8
0x1800016ac  call    _tlgWriteTransfer_EventWriteTransfer
0x1800016b1  mov     rcx, [rbp+70h+var_30]
0x1800016b5  xor     rcx, rsp; StackCookie
0x1800016b8  call    __security_check_cookie
0x1800016bd  add     rsp, 150h
0x1800016c4  pop     r14
0x1800016c6  pop     rdi
0x1800016c7  pop     rsi
0x1800016c8  pop     rbx
0x1800016c9  pop     rbp
0x1800016ca  retn
```
