# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800015a8`
- end: `0x180001855`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `685`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bc14`
- `0x18000fbf0`
- `0x18000fee0`

## callees

- `0x1800015a8`
- `0x180001bdc`
- `0x180002bc0`

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
  __int64 v22; // rdx
  int v24; // r9d
  __int64 *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // r8d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  __int64 *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  __int64 *v41; // rcx
  __int64 v42; // rax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rcx
  _BYTE v48[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h]
  __int64 v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v55; // [rsp+80h] [rbp-80h]
  int v56; // [rsp+88h] [rbp-78h]
  int v57; // [rsp+8Ch] [rbp-74h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  __int64 *v65; // [rsp+C0h] [rbp-40h]
  int v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+CCh] [rbp-34h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 *v78; // [rsp+110h] [rbp+10h]
  int v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+11Ch] [rbp+1Ch]
  __int64 v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v86; // [rsp+140h] [rbp+40h]
  int v87; // [rsp+148h] [rbp+48h]
  int v88; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v24 = 2;
  v25 = *a20;
  if ( *a20 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *((_WORD *)v25 + v26) );
    v27 = 2 * v26 + 2;
  }
  else
  {
    v25 = &qword_1800142D0;
    v27 = 2;
  }
  v87 = v27;
  v28 = 1;
  v86 = v25;
  v88 = 0;
  v29 = *a19;
  if ( *a19 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &byte_180013B63;
    v31 = 1;
  }
  v84 = v31;
  v81 = a18;
  v83 = v29;
  v85 = 0;
  v82 = 4;
  v32 = *a17;
  if ( *a17 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &qword_1800142D0;
    v34 = 2;
  }
  v79 = v34;
  v78 = v32;
  v80 = 0;
  v35 = *a16;
  if ( *a16 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &byte_180013B63;
    v37 = 1;
  }
  v76 = v37;
  v73 = a15;
  v75 = v35;
  v77 = 0;
  v74 = 4;
  v38 = *a14;
  if ( *a14 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &byte_180013B63;
    v40 = 1;
  }
  v71 = v40;
  v68 = a13;
  v70 = v38;
  v72 = 0;
  v69 = 4;
  v41 = *a12;
  if ( *a12 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_WORD *)v41 + v42) );
    v24 = 2 * v42 + 2;
  }
  else
  {
    v41 = &qword_1800142D0;
  }
  v63 = a11;
  v65 = v41;
  v66 = v24;
  v67 = 0;
  v43 = *a10;
  v64 = 4;
  if ( v43 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &byte_180013B63;
    v45 = 1;
  }
  v61 = v45;
  v58 = a9;
  v60 = v43;
  v62 = 0;
  v59 = 4;
  v46 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v46 + v22) );
    v28 = v22 + 1;
  }
  else
  {
    v46 = &byte_180013B63;
  }
  v53 = a7;
  v51 = a6;
  v49 = a5;
  v55 = v46;
  v56 = v28;
  v57 = 0;
  v54 = 4;
  v52 = 8;
  v50 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 18, v48);
}

```

## disassembly

```asm
0x1800015a8  push    rbp
0x1800015aa  push    rbx
0x1800015ab  push    rsi
0x1800015ac  push    rdi
0x1800015ad  push    r14
0x1800015af  lea     rbp, [rsp-60h]
0x1800015b4  sub     rsp, 160h
0x1800015bb  mov     rax, cs:__security_cookie
0x1800015c2  xor     rax, rsp
0x1800015c5  mov     [rbp+80h+var_30], rax
0x1800015c9  mov     rax, [rbp+80h+arg_98]
0x1800015d0  mov     r11, rdx
0x1800015d3  mov     r10, rcx
0x1800015d6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800015da  xor     edi, edi
0x1800015dc  mov     rbx, r8
0x1800015df  mov     r9d, 2
0x1800015e5  mov     rcx, [rax]
0x1800015e8  test    rcx, rcx
0x1800015eb  jz      short loc_180001602
0x1800015ed  mov     rax, rdx
0x1800015f0  inc     rax
0x1800015f3  cmp     [rcx+rax*2], di
0x1800015f7  jnz     short loc_1800015F0
0x1800015f9  lea     eax, ds:2[rax*2]
0x180001600  jmp     short loc_18000160C
0x180001602  lea     rcx, qword_1800142D0
0x180001609  mov     eax, r9d
0x18000160c  mov     [rbp+80h+var_38], eax
0x18000160f  lea     rsi, byte_180013B63
0x180001616  mov     rax, [rbp+80h+arg_90]
0x18000161d  mov     r8d, 1
0x180001623  mov     [rbp+80h+var_40], rcx
0x180001627  mov     [rbp+80h+var_34], edi
0x18000162a  mov     rcx, [rax]
0x18000162d  test    rcx, rcx
0x180001630  jz      short loc_180001642
0x180001632  mov     rax, rdx
0x180001635  inc     rax
0x180001638  cmp     [rcx+rax], dil
0x18000163c  jnz     short loc_180001635
0x18000163e  inc     eax
0x180001640  jmp     short loc_180001648
0x180001642  mov     rcx, rsi
0x180001645  mov     eax, r8d
0x180001648  mov     [rbp+80h+var_48], eax
0x18000164b  mov     rax, [rbp+80h+arg_88]
0x180001652  mov     [rbp+80h+var_60], rax
0x180001656  mov     rax, [rbp+80h+arg_80]
0x18000165d  mov     [rbp+80h+var_50], rcx
0x180001661  mov     [rbp+80h+var_44], edi
0x180001664  mov     [rbp+80h+var_58], 4
0x18000166c  mov     rcx, [rax]
0x18000166f  test    rcx, rcx
0x180001672  jz      short loc_180001689
0x180001674  mov     rax, rdx
0x180001677  inc     rax
0x18000167a  cmp     [rcx+rax*2], di
0x18000167e  jnz     short loc_180001677
0x180001680  lea     eax, ds:2[rax*2]
0x180001687  jmp     short loc_180001693
0x180001689  lea     rcx, qword_1800142D0
0x180001690  mov     eax, r9d
0x180001693  mov     [rbp+80h+var_68], eax
0x180001696  mov     rax, [rbp+80h+arg_78]
0x18000169d  mov     [rbp+80h+var_70], rcx
0x1800016a1  mov     [rbp+80h+var_64], edi
0x1800016a4  mov     rcx, [rax]
0x1800016a7  test    rcx, rcx
0x1800016aa  jz      short loc_1800016BC
0x1800016ac  mov     rax, rdx
0x1800016af  inc     rax
0x1800016b2  cmp     [rcx+rax], dil
0x1800016b6  jnz     short loc_1800016AF
0x1800016b8  inc     eax
0x1800016ba  jmp     short loc_1800016C2
0x1800016bc  mov     rcx, rsi
0x1800016bf  mov     eax, r8d
0x1800016c2  mov     [rbp+80h+var_78], eax
0x1800016c5  mov     rax, [rbp+80h+arg_70]
0x1800016cc  mov     [rbp+80h+var_90], rax
0x1800016d0  mov     rax, [rbp+80h+arg_68]
0x1800016d7  mov     [rbp+80h+var_80], rcx
0x1800016db  mov     [rbp+80h+var_74], edi
0x1800016de  mov     [rbp+80h+var_88], 4
0x1800016e6  mov     rcx, [rax]
0x1800016e9  test    rcx, rcx
0x1800016ec  jz      short loc_1800016FE
0x1800016ee  mov     rax, rdx
0x1800016f1  inc     rax
0x1800016f4  cmp     [rcx+rax], dil
0x1800016f8  jnz     short loc_1800016F1
0x1800016fa  inc     eax
0x1800016fc  jmp     short loc_180001704
0x1800016fe  mov     rcx, rsi
0x180001701  mov     eax, r8d
0x180001704  mov     [rbp+80h+var_98], eax
0x180001707  mov     rax, [rbp+80h+arg_60]
0x18000170e  mov     [rbp+80h+var_B0], rax
0x180001712  mov     rax, [rbp+80h+arg_58]
0x180001719  mov     [rbp+80h+var_A0], rcx
0x18000171d  mov     [rbp+80h+var_94], edi
0x180001720  mov     [rbp+80h+var_A8], 4
0x180001728  mov     rcx, [rax]
0x18000172b  test    rcx, rcx
0x18000172e  jz      short loc_180001746
0x180001730  mov     rax, rdx
0x180001733  inc     rax
0x180001736  cmp     [rcx+rax*2], di
0x18000173a  jnz     short loc_180001733
0x18000173c  lea     r9d, ds:2[rax*2]
0x180001744  jmp     short loc_18000174D
0x180001746  lea     rcx, qword_1800142D0
0x18000174d  mov     rax, [rbp+80h+arg_50]
0x180001754  mov     [rbp+80h+var_D0], rax
0x180001758  mov     rax, [rbp+80h+arg_48]
0x18000175f  mov     [rbp+80h+var_C0], rcx
0x180001763  mov     [rbp+80h+var_B8], r9d
0x180001767  mov     [rbp+80h+var_B4], edi
0x18000176a  mov     rcx, [rax]
0x18000176d  mov     [rbp+80h+var_C8], 4
0x180001775  test    rcx, rcx
0x180001778  jz      short loc_18000178A
0x18000177a  mov     rax, rdx
0x18000177d  inc     rax
0x180001780  cmp     [rcx+rax], dil
0x180001784  jnz     short loc_18000177D
0x180001786  inc     eax
0x180001788  jmp     short loc_180001790
0x18000178a  mov     rcx, rsi
0x18000178d  mov     eax, r8d
0x180001790  mov     [rbp+80h+var_D8], eax
0x180001793  mov     rax, [rbp+80h+arg_40]
0x18000179a  mov     [rbp+80h+var_F0], rax
0x18000179e  mov     rax, [rbp+80h+arg_38]
0x1800017a5  mov     [rbp+80h+var_E0], rcx
0x1800017a9  mov     [rbp+80h+var_D4], edi
0x1800017ac  mov     [rbp+80h+var_E8], 4
0x1800017b4  mov     rcx, [rax]
0x1800017b7  test    rcx, rcx
0x1800017ba  jz      short loc_1800017CB
0x1800017bc  inc     rdx
0x1800017bf  cmp     [rcx+rdx], dil
0x1800017c3  jnz     short loc_1800017BC
0x1800017c5  lea     r8d, [rdx+1]
0x1800017c9  jmp     short loc_1800017CE
0x1800017cb  mov     rcx, rsi
0x1800017ce  mov     rax, [rbp+80h+arg_30]
0x1800017d5  xor     r9d, r9d
0x1800017d8  mov     [rsp+180h+var_110], rax
0x1800017dd  mov     rdx, r11
0x1800017e0  mov     rax, [rbp+80h+arg_28]
0x1800017e7  mov     [rsp+180h+var_120], rax
0x1800017ec  mov     rax, [rbp+80h+arg_20]
0x1800017f3  mov     [rsp+180h+var_130], rax
0x1800017f8  lea     rax, [rsp+180h+var_150]
0x1800017fd  mov     [rbp+80h+var_100], rcx
0x180001801  mov     rcx, r10
0x180001804  mov     [rbp+80h+var_F8], r8d
0x180001808  mov     r8, rbx
0x18000180b  mov     [rsp+180h+var_158], rax
0x180001810  mov     [rsp+180h+var_160], 12h
0x180001818  mov     [rbp+80h+var_F4], edi
0x18000181b  mov     [rsp+180h+var_108], 4
0x180001824  mov     [rsp+180h+var_118], 8
0x18000182d  mov     [rsp+180h+var_128], 8
0x180001836  call    _tlgWriteTransfer_EventWriteTransfer
0x18000183b  mov     rcx, [rbp+80h+var_30]
0x18000183f  xor     rcx, rsp; StackCookie
0x180001842  call    __security_check_cookie
0x180001847  add     rsp, 160h
0x18000184e  pop     r14
0x180001850  pop     rdi
0x180001851  pop     rsi
0x180001852  pop     rbx
0x180001853  pop     rbp
0x180001854  retn
```
