# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180010e90`
- end: `0x180011291`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `1025`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `29`
- callee_count: `2`
- tags: ``

## callers

- `0x180018fa0`
- `0x180019d80`
- `0x180019fc0`
- `0x18001a200`
- `0x18001a440`
- `0x18001a680`
- `0x18001a8c0`
- `0x18001ab00`
- `0x18001ad40`
- `0x18001c650`
- `0x18001c890`
- `0x18001cad0`
- `0x18001cd10`
- `0x18001d7b0`
- `0x18001ece0`
- `0x18002d7e0`
- `0x18002da20`
- `0x18002ebf0`
- `0x18002ee30`
- `0x18002f070`
- `0x18002f2b0`
- `0x180030850`
- `0x180030a90`
- `0x180030cd0`
- `0x180030f10`
- `0x180032920`
- `0x180033880`
- `0x180033ac0`
- `0x180033d00`

## callees

- `0x180010e90`
- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800111da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800111da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
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
        int **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23)
{
  __int64 v26; // rcx
  const unsigned __int16 *v27; // r8
  __int64 v28; // rax
  int v29; // eax
  int *v30; // rdx
  __int64 v31; // rax
  bool v32; // zf
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  int *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rdx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rdx
  __int64 v44; // rax
  int v45; // eax
  int *v46; // rdx
  __int64 v47; // rax
  int v48; // eax
  const unsigned __int16 *v49; // rdx
  __int64 v50; // rax
  int v51; // eax
  const unsigned __int16 *v52; // rdx
  int v53; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v57; // [rsp+60h] [rbp-A0h]
  int v58; // [rsp+68h] [rbp-98h]
  int v59; // [rsp+6Ch] [rbp-94h]
  __int64 v60; // [rsp+70h] [rbp-90h]
  __int64 v61; // [rsp+78h] [rbp-88h]
  __int64 v62; // [rsp+80h] [rbp-80h]
  __int64 v63; // [rsp+88h] [rbp-78h]
  __int64 v64; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v66; // [rsp+A0h] [rbp-60h]
  int v67; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+ACh] [rbp-54h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v71; // [rsp+C0h] [rbp-40h]
  int v72; // [rsp+C8h] [rbp-38h]
  int v73; // [rsp+CCh] [rbp-34h]
  __int64 v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]
  int *v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E8h] [rbp-18h]
  int v78; // [rsp+ECh] [rbp-14h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v81; // [rsp+100h] [rbp+0h]
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
  const unsigned __int16 *v94; // [rsp+150h] [rbp+50h]
  int v95; // [rsp+158h] [rbp+58h]
  int v96; // [rsp+15Ch] [rbp+5Ch]
  int *v97; // [rsp+160h] [rbp+60h]
  int v98; // [rsp+168h] [rbp+68h]
  int v99; // [rsp+16Ch] [rbp+6Ch]
  __int64 v100; // [rsp+170h] [rbp+70h]
  __int64 v101; // [rsp+178h] [rbp+78h]
  __int64 v102; // [rsp+180h] [rbp+80h]
  __int64 v103; // [rsp+188h] [rbp+88h]
  const unsigned __int16 *v104; // [rsp+190h] [rbp+90h]
  int v105; // [rsp+198h] [rbp+98h]
  int v106; // [rsp+19Ch] [rbp+9Ch]

  v26 = -1;
  v27 = *a23;
  if ( *a23 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &byte_18003A073;
    v29 = 1;
  }
  v105 = v29;
  v102 = a22;
  v100 = a21;
  v104 = v27;
  v106 = 0;
  v103 = 4;
  v30 = *a20;
  v101 = 4;
  if ( v30 )
  {
    v31 = -1;
    do
      v32 = *((_WORD *)v30 + ++v31) == 0;
    while ( !v32 );
    v33 = 2 * v31 + 2;
  }
  else
  {
    v30 = &dword_18003A074;
    v33 = 2;
  }
  v98 = v33;
  v97 = v30;
  v99 = 0;
  v34 = *a19;
  if ( *a19 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &byte_18003A073;
    v36 = 1;
  }
  v95 = v36;
  v92 = a18;
  v94 = v34;
  v96 = 0;
  v93 = 4;
  v37 = *a17;
  if ( *a17 )
  {
    v38 = -1;
    do
      v32 = *((_WORD *)v37 + ++v38) == 0;
    while ( !v32 );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &dword_18003A074;
    v39 = 2;
  }
  v90 = v39;
  v89 = v37;
  v91 = 0;
  v40 = *a16;
  if ( *a16 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &byte_18003A073;
    v42 = 1;
  }
  v87 = v42;
  v84 = a15;
  v86 = v40;
  v88 = 0;
  v85 = 4;
  v43 = *a14;
  if ( *a14 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &byte_18003A073;
    v45 = 1;
  }
  v82 = v45;
  v79 = a13;
  v81 = v43;
  v83 = 0;
  v80 = 4;
  v46 = *a12;
  if ( *a12 )
  {
    v47 = -1;
    do
      v32 = *((_WORD *)v46 + ++v47) == 0;
    while ( !v32 );
    v48 = 2 * v47 + 2;
  }
  else
  {
    v46 = &dword_18003A074;
    v48 = 2;
  }
  v77 = v48;
  v74 = a11;
  v76 = v46;
  v78 = 0;
  v75 = 4;
  v49 = *a10;
  if ( *a10 )
  {
    v50 = -1;
    do
      ++v50;
    while ( *((_BYTE *)v49 + v50) );
    v51 = v50 + 1;
  }
  else
  {
    v49 = &byte_18003A073;
    v51 = 1;
  }
  v72 = v51;
  v69 = a9;
  v71 = v49;
  v73 = 0;
  v70 = 4;
  v52 = *a8;
  if ( *a8 )
  {
    do
      ++v26;
    while ( *((_BYTE *)v52 + v26) );
    v53 = v26 + 1;
  }
  else
  {
    v52 = &byte_18003A073;
    v53 = 1;
  }
  v64 = a7;
  v62 = a6;
  v60 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v67 = v53;
  v66 = v52;
  v68 = 0;
  v65 = 4;
  v63 = 8;
  v61 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v58 = *(unsigned __int16 *)(a2 + 11);
  v57 = a2 + 11;
  UserData.Reserved = 2;
  v59 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 0x15u, &UserData);
}

```

## disassembly

```asm
0x180010e90  push    rbp
0x180010e92  lea     rbp, [rsp-0B0h]
0x180010e9a  sub     rsp, 1B0h
0x180010ea1  mov     rax, cs:__security_cookie
0x180010ea8  xor     rax, rsp
0x180010eab  mov     [rbp+0B0h+var_10], rax
0x180010eb2  mov     rax, [rbp+0B0h+arg_B0]
0x180010eb9  mov     r11, r8
0x180010ebc  mov     r10, rcx
0x180010ebf  mov     r9, rdx
0x180010ec2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180010ec9  mov     r8, [rax]
0x180010ecc  test    r8, r8
0x180010ecf  jz      loc_18001122B
0x180010ed5  mov     rax, rcx
0x180010ed8  nop     dword ptr [rax+rax+00000000h]
0x180010ee0  inc     rax
0x180010ee3  cmp     byte ptr [r8+rax], 0
0x180010ee8  jnz     short loc_180010EE0
0x180010eea  inc     eax
0x180010eec  mov     [rbp+0B0h+var_18], eax
0x180010ef2  mov     rax, [rbp+0B0h+arg_A8]
0x180010ef9  mov     [rbp+0B0h+var_30], rax
0x180010f00  mov     rax, [rbp+0B0h+arg_A0]
0x180010f07  mov     [rbp+0B0h+var_40], rax
0x180010f0b  mov     rax, [rbp+0B0h+arg_98]
0x180010f12  mov     [rbp+0B0h+var_20], r8
0x180010f19  xor     r8d, r8d
0x180010f1c  mov     [rbp+0B0h+var_14], r8d
0x180010f23  mov     [rbp+0B0h+var_28], 4
0x180010f2e  mov     rdx, [rax]
0x180010f31  mov     [rbp+0B0h+var_38], 4
0x180010f39  test    rdx, rdx
0x180010f3c  jz      loc_1800111F8
0x180010f42  mov     rax, rcx
0x180010f45  nop     word ptr [rax+rax+00000000h]
0x180010f50  cmp     [rdx+rax*2+2], r8w
0x180010f56  lea     rax, [rax+1]
0x180010f5a  jnz     short loc_180010F50
0x180010f5c  lea     eax, ds:2[rax*2]
0x180010f63  mov     [rbp+0B0h+var_48], eax
0x180010f66  mov     rax, [rbp+0B0h+arg_90]
0x180010f6d  mov     [rbp+0B0h+var_50], rdx
0x180010f71  mov     [rbp+0B0h+var_44], r8d
0x180010f75  mov     rdx, [rax]
0x180010f78  test    rdx, rdx
0x180010f7b  jz      loc_18001123C
0x180010f81  mov     rax, rcx
0x180010f84  inc     rax
0x180010f87  cmp     [rdx+rax], r8b
0x180010f8b  jnz     short loc_180010F84
0x180010f8d  inc     eax
0x180010f8f  mov     [rbp+0B0h+var_58], eax
0x180010f92  mov     rax, [rbp+0B0h+arg_88]
0x180010f99  mov     [rbp+0B0h+var_70], rax
0x180010f9d  mov     rax, [rbp+0B0h+arg_80]
0x180010fa4  mov     [rbp+0B0h+var_60], rdx
0x180010fa8  mov     [rbp+0B0h+var_54], r8d
0x180010fac  mov     [rbp+0B0h+var_68], 4
0x180010fb4  mov     rdx, [rax]
0x180010fb7  test    rdx, rdx
0x180010fba  jz      loc_180011209
0x180010fc0  mov     rax, rcx
0x180010fc3  cmp     [rdx+rax*2+2], r8w
0x180010fc9  lea     rax, [rax+1]
0x180010fcd  jnz     short loc_180010FC3
0x180010fcf  lea     eax, ds:2[rax*2]
0x180010fd6  mov     [rbp+0B0h+var_78], eax
0x180010fd9  mov     rax, [rbp+0B0h+arg_78]
0x180010fe0  mov     [rbp+0B0h+var_80], rdx
0x180010fe4  mov     [rbp+0B0h+var_74], r8d
0x180010fe8  mov     rdx, [rax]
0x180010feb  test    rdx, rdx
0x180010fee  jz      loc_18001124D
0x180010ff4  mov     rax, rcx
0x180010ff7  inc     rax
0x180010ffa  cmp     [rdx+rax], r8b
0x180010ffe  jnz     short loc_180010FF7
0x180011000  inc     eax
0x180011002  mov     [rbp+0B0h+var_88], eax
0x180011005  mov     rax, [rbp+0B0h+arg_70]
0x18001100c  mov     [rbp+0B0h+var_A0], rax
0x180011010  mov     rax, [rbp+0B0h+arg_68]
0x180011017  mov     [rbp+0B0h+var_90], rdx
0x18001101b  mov     [rbp+0B0h+var_84], r8d
0x18001101f  mov     [rbp+0B0h+var_98], 4
0x180011027  mov     rdx, [rax]
0x18001102a  test    rdx, rdx
0x18001102d  jz      loc_18001125E
0x180011033  mov     rax, rcx
0x180011036  inc     rax
0x180011039  cmp     [rdx+rax], r8b
0x18001103d  jnz     short loc_180011036
0x18001103f  inc     eax
0x180011041  mov     [rbp+0B0h+var_A8], eax
0x180011044  mov     rax, [rbp+0B0h+arg_60]
0x18001104b  mov     [rbp+0B0h+var_C0], rax
0x18001104f  mov     rax, [rbp+0B0h+arg_58]
0x180011056  mov     [rbp+0B0h+var_B0], rdx
0x18001105a  mov     [rbp+0B0h+var_A4], r8d
0x18001105e  mov     [rbp+0B0h+var_B8], 4
0x180011066  mov     rdx, [rax]
0x180011069  test    rdx, rdx
0x18001106c  jz      loc_18001121A
0x180011072  mov     rax, rcx
0x180011075  nop     word ptr [rax+rax+00000000h]
0x180011080  cmp     [rdx+rax*2+2], r8w
0x180011086  lea     rax, [rax+1]
0x18001108a  jnz     short loc_180011080
0x18001108c  lea     eax, ds:2[rax*2]
0x180011093  mov     [rbp+0B0h+var_C8], eax
0x180011096  mov     rax, [rbp+0B0h+arg_50]
0x18001109d  mov     [rbp+0B0h+var_E0], rax
0x1800110a1  mov     rax, [rbp+0B0h+arg_48]
0x1800110a8  mov     [rbp+0B0h+var_D0], rdx
0x1800110ac  mov     [rbp+0B0h+var_C4], r8d
0x1800110b0  mov     [rbp+0B0h+var_D8], 4
0x1800110b8  mov     rdx, [rax]
0x1800110bb  test    rdx, rdx
0x1800110be  jz      loc_18001126F
0x1800110c4  mov     rax, rcx
0x1800110c7  inc     rax
0x1800110ca  cmp     [rdx+rax], r8b
0x1800110ce  jnz     short loc_1800110C7
0x1800110d0  inc     eax
0x1800110d2  mov     [rbp+0B0h+var_E8], eax
0x1800110d5  mov     rax, [rbp+0B0h+arg_40]
0x1800110dc  mov     [rbp+0B0h+var_100], rax
0x1800110e0  mov     rax, [rbp+0B0h+arg_38]
0x1800110e7  mov     [rbp+0B0h+var_F0], rdx
0x1800110eb  mov     [rbp+0B0h+var_E4], r8d
0x1800110ef  mov     [rbp+0B0h+var_F8], 4
0x1800110f7  mov     rdx, [rax]
0x1800110fa  test    rdx, rdx
0x1800110fd  jz      loc_180011280
0x180011103  inc     rcx
0x180011106  cmp     [rdx+rcx], r8b
0x18001110a  jnz     short loc_180011103
0x18001110c  inc     ecx
0x18001110e  mov     rax, [rbp+0B0h+arg_30]
0x180011115  mov     [rbp+0B0h+var_120], rax
0x180011119  mov     rax, [rbp+0B0h+arg_28]
0x180011120  mov     [rbp+0B0h+var_130], rax
0x180011124  mov     rax, [rbp+0B0h+arg_20]
0x18001112b  mov     [rsp+1B0h+var_140], rax
0x180011130  movzx   eax, byte ptr [r9]
0x180011134  shl     eax, 18h
0x180011137  mov     dword ptr [rsp+1B0h+EventDescriptor.Id], eax
0x18001113b  movzx   eax, word ptr [r9+1]
0x180011140  mov     dword ptr [rsp+1B0h+EventDescriptor.Level], eax
0x180011144  mov     rax, [r9+3]
0x180011148  mov     [rsp+1B0h+EventDescriptor.Keyword], rax
0x18001114d  mov     rax, [r10+8]
0x180011151  mov     [rsp+1B0h+var_160.Ptr], rax
0x180011156  mov     [rbp+0B0h+var_108], ecx
0x180011159  lea     rcx, [r9+0Bh]
0x18001115d  mov     [rbp+0B0h+var_110], rdx
0x180011161  xor     r9d, r9d; RelatedActivityId
0x180011164  mov     [rbp+0B0h+var_104], r8d
0x180011168  lea     rdx, [rsp+1B0h+EventDescriptor]; EventDescriptor
0x18001116d  mov     [rbp+0B0h+var_118], 4
0x180011175  mov     r8, r11; ActivityId
0x180011178  mov     [rbp+0B0h+var_128], 8
0x180011180  mov     [rsp+1B0h+var_138], 8
0x180011189  movzx   eax, word ptr [rax]
0x18001118c  mov     [rsp+1B0h+var_160.Size], eax
0x180011190  movzx   eax, word ptr [rcx]
0x180011193  mov     [rsp+1B0h+var_148], eax
0x180011197  lea     rax, _TraceLoggingMetadataEnd
0x18001119e  mov     [rsp+1B0h+var_150], rcx
0x1800111a3  lea     rcx, _TraceLoggingMetadata
0x1800111aa  sub     eax, ecx
0x1800111ac  mov     dword ptr [rsp+1B0h+var_160.0Ch], 2
0x1800111b4  mov     [rsp+1B0h+var_144], 1
0x1800111bc  mov     [rsp+1B0h+var_180], eax
0x1800111c0  mov     eax, [rsp+1B0h+var_180]
0x1800111c4  mov     rcx, [r10+20h]; RegHandle
0x1800111c8  lea     rax, [rsp+1B0h+var_160]
0x1800111cd  mov     [rsp+1B0h+UserData], rax; UserData
0x1800111d2  mov     [rsp+1B0h+UserDataCount], 15h; UserDataCount
0x1800111da  call    cs:__imp_EventWriteTransfer
0x1800111e0  mov     rcx, [rbp+0B0h+var_10]
0x1800111e7  xor     rcx, rsp; StackCookie
0x1800111ea  call    __security_check_cookie
0x1800111ef  add     rsp, 1B0h
0x1800111f6  pop     rbp
0x1800111f7  retn
0x1800111f8  lea     rdx, dword_18003A074
0x1800111ff  mov     eax, 2
0x180011204  jmp     loc_180010F63
0x180011209  lea     rdx, dword_18003A074
0x180011210  mov     eax, 2
0x180011215  jmp     loc_180010FD6
0x18001121a  lea     rdx, dword_18003A074
0x180011221  mov     eax, 2
0x180011226  jmp     loc_180011093
0x18001122b  lea     r8, byte_18003A073
0x180011232  mov     eax, 1
0x180011237  jmp     loc_180010EEC
0x18001123c  lea     rdx, byte_18003A073
0x180011243  mov     eax, 1
0x180011248  jmp     loc_180010F8F
0x18001124d  lea     rdx, byte_18003A073
0x180011254  mov     eax, 1
0x180011259  jmp     loc_180011002
0x18001125e  lea     rdx, byte_18003A073
0x180011265  mov     eax, 1
0x18001126a  jmp     loc_180011041
0x18001126f  lea     rdx, byte_18003A073
0x180011276  mov     eax, 1
0x18001127b  jmp     loc_1800110D2
0x180011280  lea     rdx, byte_18003A073
0x180011287  mov     ecx, 1
0x18001128c  jmp     loc_18001110E
```
