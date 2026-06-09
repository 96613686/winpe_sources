# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000341c`
- end: `0x1800036c7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800293e4`

## callees

- `0x180001010`
- `0x18000341c`
- `0x1800050f0`

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
    v24 = &dword_180031EE4;
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
    v28 = &byte_180031EE0;
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
    v31 = &dword_180031EE4;
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
    v34 = &byte_180031EE0;
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
    v37 = &byte_180031EE0;
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
    v40 = &dword_180031EE4;
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
    v42 = &byte_180031EE0;
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
    v45 = &byte_180031EE0;
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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 18, v47);
}

```

## disassembly

```asm
0x18000341c  mov     [rsp-8+arg_10], rbx
0x180003421  push    rbp
0x180003422  push    rsi
0x180003423  push    rdi
0x180003424  lea     rbp, [rsp-60h]
0x180003429  sub     rsp, 160h
0x180003430  mov     rax, cs:__security_cookie
0x180003437  xor     rax, rsp
0x18000343a  mov     [rbp+70h+var_20], rax
0x18000343e  mov     rax, [rbp+70h+arg_98]
0x180003445  mov     r11, rdx
0x180003448  mov     r10, rcx
0x18000344b  xor     ebx, ebx
0x18000344d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003451  mov     r9d, 2
0x180003457  mov     rdx, [rax]
0x18000345a  test    rdx, rdx
0x18000345d  jz      short loc_180003474
0x18000345f  mov     rax, rcx
0x180003462  inc     rax
0x180003465  cmp     [rdx+rax*2], bx
0x180003469  jnz     short loc_180003462
0x18000346b  lea     eax, ds:2[rax*2]
0x180003472  jmp     short loc_18000347E
0x180003474  lea     rdx, dword_180031EE4
0x18000347b  mov     eax, r9d
0x18000347e  mov     [rbp+70h+var_28], eax
0x180003481  lea     rdi, byte_180031EE0
0x180003488  mov     rax, [rbp+70h+arg_90]
0x18000348f  mov     r8d, 1
0x180003495  mov     [rbp+70h+var_30], rdx
0x180003499  mov     [rbp+70h+var_24], ebx
0x18000349c  mov     rdx, [rax]
0x18000349f  test    rdx, rdx
0x1800034a2  jz      short loc_1800034B3
0x1800034a4  mov     rax, rcx
0x1800034a7  inc     rax
0x1800034aa  cmp     [rdx+rax], bl
0x1800034ad  jnz     short loc_1800034A7
0x1800034af  inc     eax
0x1800034b1  jmp     short loc_1800034B9
0x1800034b3  mov     rdx, rdi
0x1800034b6  mov     eax, r8d
0x1800034b9  mov     [rbp+70h+var_38], eax
0x1800034bc  mov     rax, [rbp+70h+arg_88]
0x1800034c3  mov     [rbp+70h+var_50], rax
0x1800034c7  mov     rax, [rbp+70h+arg_80]
0x1800034ce  mov     [rbp+70h+var_40], rdx
0x1800034d2  mov     [rbp+70h+var_34], ebx
0x1800034d5  mov     [rbp+70h+var_48], 4
0x1800034dd  mov     rdx, [rax]
0x1800034e0  test    rdx, rdx
0x1800034e3  jz      short loc_1800034FA
0x1800034e5  mov     rax, rcx
0x1800034e8  inc     rax
0x1800034eb  cmp     [rdx+rax*2], bx
0x1800034ef  jnz     short loc_1800034E8
0x1800034f1  lea     eax, ds:2[rax*2]
0x1800034f8  jmp     short loc_180003504
0x1800034fa  lea     rdx, dword_180031EE4
0x180003501  mov     eax, r9d
0x180003504  mov     [rbp+70h+var_58], eax
0x180003507  mov     rax, [rbp+70h+arg_78]
0x18000350e  mov     [rbp+70h+var_60], rdx
0x180003512  mov     [rbp+70h+var_54], ebx
0x180003515  mov     rdx, [rax]
0x180003518  test    rdx, rdx
0x18000351b  jz      short loc_18000352C
0x18000351d  mov     rax, rcx
0x180003520  inc     rax
0x180003523  cmp     [rdx+rax], bl
0x180003526  jnz     short loc_180003520
0x180003528  inc     eax
0x18000352a  jmp     short loc_180003532
0x18000352c  mov     rdx, rdi
0x18000352f  mov     eax, r8d
0x180003532  mov     [rbp+70h+var_68], eax
0x180003535  mov     rax, [rbp+70h+arg_70]
0x18000353c  mov     [rbp+70h+var_80], rax
0x180003540  mov     rax, [rbp+70h+arg_68]
0x180003547  mov     [rbp+70h+var_70], rdx
0x18000354b  mov     [rbp+70h+var_64], ebx
0x18000354e  mov     [rbp+70h+var_78], 4
0x180003556  mov     rdx, [rax]
0x180003559  test    rdx, rdx
0x18000355c  jz      short loc_18000356D
0x18000355e  mov     rax, rcx
0x180003561  inc     rax
0x180003564  cmp     [rdx+rax], bl
0x180003567  jnz     short loc_180003561
0x180003569  inc     eax
0x18000356b  jmp     short loc_180003573
0x18000356d  mov     rdx, rdi
0x180003570  mov     eax, r8d
0x180003573  mov     [rbp+70h+var_88], eax
0x180003576  mov     rax, [rbp+70h+arg_60]
0x18000357d  mov     [rbp+70h+var_A0], rax
0x180003581  mov     rax, [rbp+70h+arg_58]
0x180003588  mov     [rbp+70h+var_90], rdx
0x18000358c  mov     [rbp+70h+var_84], ebx
0x18000358f  mov     [rbp+70h+var_98], 4
0x180003597  mov     rdx, [rax]
0x18000359a  test    rdx, rdx
0x18000359d  jz      short loc_1800035B5
0x18000359f  mov     rax, rcx
0x1800035a2  inc     rax
0x1800035a5  cmp     [rdx+rax*2], bx
0x1800035a9  jnz     short loc_1800035A2
0x1800035ab  lea     r9d, ds:2[rax*2]
0x1800035b3  jmp     short loc_1800035BC
0x1800035b5  lea     rdx, dword_180031EE4
0x1800035bc  mov     rax, [rbp+70h+arg_50]
0x1800035c3  mov     [rbp+70h+var_C0], rax
0x1800035c7  mov     rax, [rbp+70h+arg_48]
0x1800035ce  mov     [rbp+70h+var_B0], rdx
0x1800035d2  mov     [rbp+70h+var_A8], r9d
0x1800035d6  mov     [rbp+70h+var_A4], ebx
0x1800035d9  mov     rdx, [rax]
0x1800035dc  mov     [rbp+70h+var_B8], 4
0x1800035e4  test    rdx, rdx
0x1800035e7  jz      short loc_1800035F8
0x1800035e9  mov     rax, rcx
0x1800035ec  inc     rax
0x1800035ef  cmp     [rdx+rax], bl
0x1800035f2  jnz     short loc_1800035EC
0x1800035f4  inc     eax
0x1800035f6  jmp     short loc_1800035FE
0x1800035f8  mov     rdx, rdi
0x1800035fb  mov     eax, r8d
0x1800035fe  mov     [rbp+70h+var_C8], eax
0x180003601  mov     rax, [rbp+70h+arg_40]
0x180003608  mov     [rbp+70h+var_E0], rax
0x18000360c  mov     rax, [rbp+70h+arg_38]
0x180003613  mov     [rbp+70h+var_D0], rdx
0x180003617  mov     [rbp+70h+var_C4], ebx
0x18000361a  mov     [rbp+70h+var_D8], 4
0x180003622  mov     rdx, [rax]
0x180003625  test    rdx, rdx
0x180003628  jz      short loc_180003638
0x18000362a  inc     rcx
0x18000362d  cmp     [rdx+rcx], bl
0x180003630  jnz     short loc_18000362A
0x180003632  lea     r8d, [rcx+1]
0x180003636  jmp     short loc_18000363B
0x180003638  mov     rdx, rdi
0x18000363b  mov     rax, [rbp+70h+arg_30]
0x180003642  xor     r9d, r9d
0x180003645  mov     [rsp+170h+var_100], rax
0x18000364a  mov     rcx, r10
0x18000364d  mov     rax, [rbp+70h+arg_28]
0x180003654  mov     [rsp+170h+var_110], rax
0x180003659  mov     rax, [rbp+70h+arg_20]
0x180003660  mov     [rsp+170h+var_120], rax
0x180003665  lea     rax, [rsp+170h+var_140]
0x18000366a  mov     [rbp+70h+var_F0], rdx
0x18000366e  mov     rdx, r11
0x180003671  mov     [rbp+70h+var_E8], r8d
0x180003675  xor     r8d, r8d
0x180003678  mov     [rsp+170h+var_148], rax
0x18000367d  mov     [rsp+170h+var_150], 12h
0x180003685  mov     [rbp+70h+var_E4], ebx
0x180003688  mov     [rsp+170h+var_F8], 4
0x180003691  mov     [rsp+170h+var_108], 8
0x18000369a  mov     [rsp+170h+var_118], 8
0x1800036a3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800036a8  mov     rcx, [rbp+70h+var_20]
0x1800036ac  xor     rcx, rsp; StackCookie
0x1800036af  call    __security_check_cookie
0x1800036b4  mov     rbx, [rsp+170h+arg_10]
0x1800036bc  add     rsp, 160h
0x1800036c3  pop     rdi
0x1800036c4  pop     rsi
0x1800036c5  pop     rbp
0x1800036c6  retn
```
