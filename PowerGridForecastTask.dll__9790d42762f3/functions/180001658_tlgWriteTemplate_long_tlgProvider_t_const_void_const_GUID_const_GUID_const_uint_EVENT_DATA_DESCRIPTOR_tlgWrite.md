# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001658`
- end: `0x1800018f3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b8a0`

## callees

- `0x180001658`
- `0x180001c7c`
- `0x1800350e0`

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
    v24 = &dword_18003D19C;
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
    v28 = &byte_18003D198;
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
    v31 = &dword_18003D19C;
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
    v34 = &byte_18003D198;
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
    v37 = &byte_18003D198;
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
    v40 = &dword_18003D19C;
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
    v42 = &byte_18003D198;
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
    v45 = &byte_18003D198;
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
0x180001658  push    rbp
0x18000165a  push    rbx
0x18000165b  push    rsi
0x18000165c  push    rdi
0x18000165d  push    r14
0x18000165f  lea     rbp, [rsp-50h]
0x180001664  sub     rsp, 150h
0x18000166b  mov     rax, cs:__security_cookie
0x180001672  xor     rax, rsp
0x180001675  mov     [rbp+70h+var_30], rax
0x180001679  mov     rax, [rbp+70h+arg_90]
0x180001680  mov     r11, rdx
0x180001683  mov     r10, rcx
0x180001686  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000168a  xor     edi, edi
0x18000168c  mov     rbx, r8
0x18000168f  mov     r9d, 2
0x180001695  mov     rcx, [rax]
0x180001698  test    rcx, rcx
0x18000169b  jz      short loc_1800016B2
0x18000169d  mov     rax, rdx
0x1800016a0  inc     rax
0x1800016a3  cmp     [rcx+rax*2], di
0x1800016a7  jnz     short loc_1800016A0
0x1800016a9  lea     eax, ds:2[rax*2]
0x1800016b0  jmp     short loc_1800016BC
0x1800016b2  lea     rcx, dword_18003D19C
0x1800016b9  mov     eax, r9d
0x1800016bc  mov     [rbp+70h+var_38], eax
0x1800016bf  lea     rsi, byte_18003D198
0x1800016c6  mov     rax, [rbp+70h+arg_88]
0x1800016cd  mov     r8d, 1
0x1800016d3  mov     [rbp+70h+var_40], rcx
0x1800016d7  mov     [rbp+70h+var_34], edi
0x1800016da  mov     rcx, [rax]
0x1800016dd  test    rcx, rcx
0x1800016e0  jz      short loc_1800016F2
0x1800016e2  mov     rax, rdx
0x1800016e5  inc     rax
0x1800016e8  cmp     [rcx+rax], dil
0x1800016ec  jnz     short loc_1800016E5
0x1800016ee  inc     eax
0x1800016f0  jmp     short loc_1800016F8
0x1800016f2  mov     rcx, rsi
0x1800016f5  mov     eax, r8d
0x1800016f8  mov     [rbp+70h+var_48], eax
0x1800016fb  mov     rax, [rbp+70h+arg_80]
0x180001702  mov     [rbp+70h+var_60], rax
0x180001706  mov     rax, [rbp+70h+arg_78]
0x18000170d  mov     [rbp+70h+var_50], rcx
0x180001711  mov     [rbp+70h+var_44], edi
0x180001714  mov     [rbp+70h+var_58], 4
0x18000171c  mov     rcx, [rax]
0x18000171f  test    rcx, rcx
0x180001722  jz      short loc_180001739
0x180001724  mov     rax, rdx
0x180001727  inc     rax
0x18000172a  cmp     [rcx+rax*2], di
0x18000172e  jnz     short loc_180001727
0x180001730  lea     eax, ds:2[rax*2]
0x180001737  jmp     short loc_180001743
0x180001739  lea     rcx, dword_18003D19C
0x180001740  mov     eax, r9d
0x180001743  mov     [rbp+70h+var_68], eax
0x180001746  mov     rax, [rbp+70h+arg_70]
0x18000174d  mov     [rbp+70h+var_70], rcx
0x180001751  mov     [rbp+70h+var_64], edi
0x180001754  mov     rcx, [rax]
0x180001757  test    rcx, rcx
0x18000175a  jz      short loc_18000176C
0x18000175c  mov     rax, rdx
0x18000175f  inc     rax
0x180001762  cmp     [rcx+rax], dil
0x180001766  jnz     short loc_18000175F
0x180001768  inc     eax
0x18000176a  jmp     short loc_180001772
0x18000176c  mov     rcx, rsi
0x18000176f  mov     eax, r8d
0x180001772  mov     [rbp+70h+var_78], eax
0x180001775  mov     rax, [rbp+70h+arg_68]
0x18000177c  mov     [rbp+70h+var_90], rax
0x180001780  mov     rax, [rbp+70h+arg_60]
0x180001787  mov     [rbp+70h+var_80], rcx
0x18000178b  mov     [rbp+70h+var_74], edi
0x18000178e  mov     [rbp+70h+var_88], 4
0x180001796  mov     rcx, [rax]
0x180001799  test    rcx, rcx
0x18000179c  jz      short loc_1800017AE
0x18000179e  mov     rax, rdx
0x1800017a1  inc     rax
0x1800017a4  cmp     [rcx+rax], dil
0x1800017a8  jnz     short loc_1800017A1
0x1800017aa  inc     eax
0x1800017ac  jmp     short loc_1800017B4
0x1800017ae  mov     rcx, rsi
0x1800017b1  mov     eax, r8d
0x1800017b4  mov     [rbp+70h+var_98], eax
0x1800017b7  mov     rax, [rbp+70h+arg_58]
0x1800017be  mov     [rbp+70h+var_B0], rax
0x1800017c2  mov     rax, [rbp+70h+arg_50]
0x1800017c9  mov     [rbp+70h+var_A0], rcx
0x1800017cd  mov     [rbp+70h+var_94], edi
0x1800017d0  mov     [rbp+70h+var_A8], 4
0x1800017d8  mov     rcx, [rax]
0x1800017db  test    rcx, rcx
0x1800017de  jz      short loc_1800017F6
0x1800017e0  mov     rax, rdx
0x1800017e3  inc     rax
0x1800017e6  cmp     [rcx+rax*2], di
0x1800017ea  jnz     short loc_1800017E3
0x1800017ec  lea     r9d, ds:2[rax*2]
0x1800017f4  jmp     short loc_1800017FD
0x1800017f6  lea     rcx, dword_18003D19C
0x1800017fd  mov     rax, [rbp+70h+arg_48]
0x180001804  mov     [rbp+70h+var_D0], rax
0x180001808  mov     rax, [rbp+70h+arg_40]
0x18000180f  mov     [rbp+70h+var_C0], rcx
0x180001813  mov     [rbp+70h+var_B8], r9d
0x180001817  mov     [rbp+70h+var_B4], edi
0x18000181a  mov     rcx, [rax]
0x18000181d  mov     [rbp+70h+var_C8], 4
0x180001825  test    rcx, rcx
0x180001828  jz      short loc_18000183A
0x18000182a  mov     rax, rdx
0x18000182d  inc     rax
0x180001830  cmp     [rcx+rax], dil
0x180001834  jnz     short loc_18000182D
0x180001836  inc     eax
0x180001838  jmp     short loc_180001840
0x18000183a  mov     rcx, rsi
0x18000183d  mov     eax, r8d
0x180001840  mov     [rbp+70h+var_D8], eax
0x180001843  mov     rax, [rbp+70h+arg_38]
0x18000184a  mov     [rbp+70h+var_F0], rax
0x18000184e  mov     rax, [rbp+70h+arg_30]
0x180001855  mov     [rbp+70h+var_E0], rcx
0x180001859  mov     [rbp+70h+var_D4], edi
0x18000185c  mov     [rbp+70h+var_E8], 4
0x180001864  mov     rcx, [rax]
0x180001867  test    rcx, rcx
0x18000186a  jz      short loc_18000187B
0x18000186c  inc     rdx
0x18000186f  cmp     [rcx+rdx], dil
0x180001873  jnz     short loc_18000186C
0x180001875  lea     r8d, [rdx+1]
0x180001879  jmp     short loc_18000187E
0x18000187b  mov     rcx, rsi
0x18000187e  mov     rax, [rbp+70h+arg_28]
0x180001885  xor     r9d, r9d
0x180001888  mov     [rsp+170h+var_110], rax
0x18000188d  mov     rdx, r11
0x180001890  mov     rax, [rbp+70h+arg_20]
0x180001897  mov     [rsp+170h+var_120], rax
0x18000189c  lea     rax, [rsp+170h+var_140]
0x1800018a1  mov     [rsp+170h+var_100], rcx
0x1800018a6  mov     rcx, r10
0x1800018a9  mov     [rsp+170h+var_F8], r8d
0x1800018ae  mov     r8, rbx
0x1800018b1  mov     [rsp+170h+var_148], rax
0x1800018b6  mov     [rsp+170h+var_150], 11h
0x1800018be  mov     [rsp+170h+var_F4], edi
0x1800018c2  mov     [rsp+170h+var_108], 4
0x1800018cb  mov     [rsp+170h+var_118], 8
0x1800018d4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800018d9  mov     rcx, [rbp+70h+var_30]
0x1800018dd  xor     rcx, rsp; StackCookie
0x1800018e0  call    __security_check_cookie
0x1800018e5  add     rsp, 150h
0x1800018ec  pop     r14
0x1800018ee  pop     rdi
0x1800018ef  pop     rsi
0x1800018f0  pop     rbx
0x1800018f1  pop     rbp
0x1800018f2  retn
```
