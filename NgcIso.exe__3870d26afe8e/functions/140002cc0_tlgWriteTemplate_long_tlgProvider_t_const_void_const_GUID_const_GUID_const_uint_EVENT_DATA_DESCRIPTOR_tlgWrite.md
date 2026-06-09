# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140002cc0`
- end: `0x140003007`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `839`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x1400169d0`
- `0x140016fa0`
- `0x14002ffe0`
- `0x140030210`
- `0x140031400`
- `0x140031cf0`
- `0x1400335a0`
- `0x1400337d0`
- `0x140033c40`
- `0x140033e70`
- `0x140035060`
- `0x1400354d0`
- `0x140036240`
- `0x140036d70`
- `0x140042660`
- `0x140042890`
- `0x140042ac0`
- `0x140042cf0`
- `0x1400433a0`
- `0x14005f0e0`
- `0x14005f310`
- `0x14005f540`
- `0x14005f770`
- `0x14005f9a0`
- `0x14005fbd0`
- `0x14005fe00`

## callees

- `0x140002cc0`
- `0x14000f6a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002fec`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002fec`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
  __int64 v23; // rcx
  __int64 *v24; // r8
  __int64 v25; // rax
  bool v26; // zf
  int v27; // eax
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  __int64 *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  __int64 *v40; // rdx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rdx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rdx
  int v47; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v51; // [rsp+60h] [rbp-A0h]
  int v52; // [rsp+68h] [rbp-98h]
  int v53; // [rsp+6Ch] [rbp-94h]
  __int64 v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
  __int64 v56; // [rsp+80h] [rbp-80h]
  __int64 v57; // [rsp+88h] [rbp-78h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v65; // [rsp+C0h] [rbp-40h]
  int v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+CCh] [rbp-34h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  __int64 *v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  __int64 v86; // [rsp+140h] [rbp+40h]
  __int64 v87; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v88; // [rsp+150h] [rbp+50h]
  int v89; // [rsp+158h] [rbp+58h]
  int v90; // [rsp+15Ch] [rbp+5Ch]
  __int64 *v91; // [rsp+160h] [rbp+60h]
  int v92; // [rsp+168h] [rbp+68h]
  int v93; // [rsp+16Ch] [rbp+6Ch]

  v23 = -1;
  v24 = *a20;
  if ( *a20 )
  {
    v25 = -1;
    do
      v26 = *((_WORD *)v24 + ++v25) == 0;
    while ( !v26 );
    v27 = 2 * v25 + 2;
  }
  else
  {
    v24 = &qword_1400793A8;
    v27 = 2;
  }
  v92 = v27;
  v91 = v24;
  v93 = 0;
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
    v28 = &word_1400793A6;
    v30 = 1;
  }
  v89 = v30;
  v86 = a18;
  v88 = v28;
  v90 = 0;
  v87 = 4;
  v31 = *a17;
  if ( *a17 )
  {
    v32 = -1;
    do
      v26 = *((_WORD *)v31 + ++v32) == 0;
    while ( !v26 );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &qword_1400793A8;
    v33 = 2;
  }
  v84 = v33;
  v83 = v31;
  v85 = 0;
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
    v34 = &word_1400793A6;
    v36 = 1;
  }
  v81 = v36;
  v78 = a15;
  v80 = v34;
  v82 = 0;
  v79 = 4;
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
    v37 = &word_1400793A6;
    v39 = 1;
  }
  v76 = v39;
  v73 = a13;
  v75 = v37;
  v77 = 0;
  v74 = 4;
  v40 = *a12;
  if ( *a12 )
  {
    v41 = -1;
    do
      v26 = *((_WORD *)v40 + ++v41) == 0;
    while ( !v26 );
    v42 = 2 * v41 + 2;
  }
  else
  {
    v40 = &qword_1400793A8;
    v42 = 2;
  }
  v71 = v42;
  v68 = a11;
  v70 = v40;
  v72 = 0;
  v69 = 4;
  v43 = *a10;
  if ( *a10 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &word_1400793A6;
    v45 = 1;
  }
  v66 = v45;
  v63 = a9;
  v65 = v43;
  v67 = 0;
  v64 = 4;
  v46 = *a8;
  if ( *a8 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v46 + v23) );
    v47 = v23 + 1;
  }
  else
  {
    v46 = &word_1400793A6;
    v47 = 1;
  }
  v58 = a7;
  v56 = a6;
  v54 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v61 = v47;
  v60 = v46;
  v62 = 0;
  v59 = 4;
  v57 = 8;
  v55 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v52 = *(unsigned __int16 *)(a2 + 11);
  v51 = a2 + 11;
  UserData.Reserved = 2;
  v53 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 0x12u, &UserData);
}

```

## disassembly

```asm
0x140002cc0  push    rbp
0x140002cc2  lea     rbp, [rsp-80h]
0x140002cc7  sub     rsp, 180h
0x140002cce  mov     rax, cs:__security_cookie
0x140002cd5  xor     rax, rsp
0x140002cd8  mov     [rbp+80h+var_10], rax
0x140002cdc  mov     rax, [rbp+80h+arg_98]
0x140002ce3  mov     r11, r8
0x140002ce6  mov     r10, rcx
0x140002ce9  mov     r9, rdx
0x140002cec  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140002cf3  mov     r8, [rax]
0x140002cf6  test    r8, r8
0x140002cf9  jz      short loc_140002D16
0x140002cfb  mov     rax, rcx
0x140002cfe  xchg    ax, ax
0x140002d00  cmp     word ptr [r8+rax*2+2], 0
0x140002d07  lea     rax, [rax+1]
0x140002d0b  jnz     short loc_140002D00
0x140002d0d  lea     eax, ds:2[rax*2]
0x140002d14  jmp     short loc_140002D22
0x140002d16  lea     r8, qword_1400793A8
0x140002d1d  mov     eax, 2
0x140002d22  mov     [rbp+80h+var_18], eax
0x140002d25  mov     rax, [rbp+80h+arg_90]
0x140002d2c  mov     [rbp+80h+var_20], r8
0x140002d30  xor     r8d, r8d
0x140002d33  mov     [rbp+80h+var_14], r8d
0x140002d37  mov     rdx, [rax]
0x140002d3a  test    rdx, rdx
0x140002d3d  jz      short loc_140002D4F
0x140002d3f  mov     rax, rcx
0x140002d42  inc     rax
0x140002d45  cmp     [rdx+rax], r8b
0x140002d49  jnz     short loc_140002D42
0x140002d4b  inc     eax
0x140002d4d  jmp     short loc_140002D5B
0x140002d4f  lea     rdx, word_1400793A6
0x140002d56  mov     eax, 1
0x140002d5b  mov     [rbp+80h+var_28], eax
0x140002d5e  mov     rax, [rbp+80h+arg_88]
0x140002d65  mov     [rbp+80h+var_40], rax
0x140002d69  mov     rax, [rbp+80h+arg_80]
0x140002d70  mov     [rbp+80h+var_30], rdx
0x140002d74  mov     [rbp+80h+var_24], r8d
0x140002d78  mov     [rbp+80h+var_38], 4
0x140002d80  mov     rdx, [rax]
0x140002d83  test    rdx, rdx
0x140002d86  jz      short loc_140002DA5
0x140002d88  mov     rax, rcx
0x140002d8b  nop     dword ptr [rax+rax+00h]
0x140002d90  cmp     [rdx+rax*2+2], r8w
0x140002d96  lea     rax, [rax+1]
0x140002d9a  jnz     short loc_140002D90
0x140002d9c  lea     eax, ds:2[rax*2]
0x140002da3  jmp     short loc_140002DB1
0x140002da5  lea     rdx, qword_1400793A8
0x140002dac  mov     eax, 2
0x140002db1  mov     [rbp+80h+var_48], eax
0x140002db4  mov     rax, [rbp+80h+arg_78]
0x140002dbb  mov     [rbp+80h+var_50], rdx
0x140002dbf  mov     [rbp+80h+var_44], r8d
0x140002dc3  mov     rdx, [rax]
0x140002dc6  test    rdx, rdx
0x140002dc9  jz      short loc_140002DDD
0x140002dcb  mov     rax, rcx
0x140002dce  xchg    ax, ax
0x140002dd0  inc     rax
0x140002dd3  cmp     [rdx+rax], r8b
0x140002dd7  jnz     short loc_140002DD0
0x140002dd9  inc     eax
0x140002ddb  jmp     short loc_140002DE9
0x140002ddd  lea     rdx, word_1400793A6
0x140002de4  mov     eax, 1
0x140002de9  mov     [rbp+80h+var_58], eax
0x140002dec  mov     rax, [rbp+80h+arg_70]
0x140002df3  mov     [rbp+80h+var_70], rax
0x140002df7  mov     rax, [rbp+80h+arg_68]
0x140002dfe  mov     [rbp+80h+var_60], rdx
0x140002e02  mov     [rbp+80h+var_54], r8d
0x140002e06  mov     [rbp+80h+var_68], 4
0x140002e0e  mov     rdx, [rax]
0x140002e11  test    rdx, rdx
0x140002e14  jz      short loc_140002E2D
0x140002e16  mov     rax, rcx
0x140002e19  nop     dword ptr [rax+00000000h]
0x140002e20  inc     rax
0x140002e23  cmp     [rdx+rax], r8b
0x140002e27  jnz     short loc_140002E20
0x140002e29  inc     eax
0x140002e2b  jmp     short loc_140002E39
0x140002e2d  lea     rdx, word_1400793A6
0x140002e34  mov     eax, 1
0x140002e39  mov     [rbp+80h+var_78], eax
0x140002e3c  mov     rax, [rbp+80h+arg_60]
0x140002e43  mov     [rbp+80h+var_90], rax
0x140002e47  mov     rax, [rbp+80h+arg_58]
0x140002e4e  mov     [rbp+80h+var_80], rdx
0x140002e52  mov     [rbp+80h+var_74], r8d
0x140002e56  mov     [rbp+80h+var_88], 4
0x140002e5e  mov     rdx, [rax]
0x140002e61  test    rdx, rdx
0x140002e64  jz      short loc_140002E85
0x140002e66  mov     rax, rcx
0x140002e69  nop     dword ptr [rax+00000000h]
0x140002e70  cmp     [rdx+rax*2+2], r8w
0x140002e76  lea     rax, [rax+1]
0x140002e7a  jnz     short loc_140002E70
0x140002e7c  lea     eax, ds:2[rax*2]
0x140002e83  jmp     short loc_140002E91
0x140002e85  lea     rdx, qword_1400793A8
0x140002e8c  mov     eax, 2
0x140002e91  mov     [rbp+80h+var_98], eax
0x140002e94  mov     rax, [rbp+80h+arg_50]
0x140002e9b  mov     [rbp+80h+var_B0], rax
0x140002e9f  mov     rax, [rbp+80h+arg_48]
0x140002ea6  mov     [rbp+80h+var_A0], rdx
0x140002eaa  mov     [rbp+80h+var_94], r8d
0x140002eae  mov     [rbp+80h+var_A8], 4
0x140002eb6  mov     rdx, [rax]
0x140002eb9  test    rdx, rdx
0x140002ebc  jz      short loc_140002ECE
0x140002ebe  mov     rax, rcx
0x140002ec1  inc     rax
0x140002ec4  cmp     [rdx+rax], r8b
0x140002ec8  jnz     short loc_140002EC1
0x140002eca  inc     eax
0x140002ecc  jmp     short loc_140002EDA
0x140002ece  lea     rdx, word_1400793A6
0x140002ed5  mov     eax, 1
0x140002eda  mov     [rbp+80h+var_B8], eax
0x140002edd  mov     rax, [rbp+80h+arg_40]
0x140002ee4  mov     [rbp+80h+var_D0], rax
0x140002ee8  mov     rax, [rbp+80h+arg_38]
0x140002eef  mov     [rbp+80h+var_C0], rdx
0x140002ef3  mov     [rbp+80h+var_B4], r8d
0x140002ef7  mov     [rbp+80h+var_C8], 4
0x140002eff  mov     rdx, [rax]
0x140002f02  test    rdx, rdx
0x140002f05  jz      short loc_140002F14
0x140002f07  inc     rcx
0x140002f0a  cmp     [rdx+rcx], r8b
0x140002f0e  jnz     short loc_140002F07
0x140002f10  inc     ecx
0x140002f12  jmp     short loc_140002F20
0x140002f14  lea     rdx, word_1400793A6
0x140002f1b  mov     ecx, 1
0x140002f20  mov     rax, [rbp+80h+arg_30]
0x140002f27  mov     [rbp+80h+var_F0], rax
0x140002f2b  mov     rax, [rbp+80h+arg_28]
0x140002f32  mov     [rbp+80h+var_100], rax
0x140002f36  mov     rax, [rbp+80h+arg_20]
0x140002f3d  mov     [rsp+180h+var_110], rax
0x140002f42  movzx   eax, byte ptr [r9]
0x140002f46  shl     eax, 18h
0x140002f49  mov     dword ptr [rsp+180h+EventDescriptor.Id], eax
0x140002f4d  movzx   eax, word ptr [r9+1]
0x140002f52  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x140002f56  mov     rax, [r9+3]
0x140002f5a  mov     [rsp+180h+EventDescriptor.Keyword], rax
0x140002f5f  mov     rax, [r10+8]
0x140002f63  mov     [rsp+180h+var_130.Ptr], rax
0x140002f68  mov     [rbp+80h+var_D8], ecx
0x140002f6b  lea     rcx, [r9+0Bh]
0x140002f6f  mov     [rbp+80h+var_E0], rdx
0x140002f73  xor     r9d, r9d; RelatedActivityId
0x140002f76  mov     [rbp+80h+var_D4], r8d
0x140002f7a  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x140002f7f  mov     [rbp+80h+var_E8], 4
0x140002f87  mov     r8, r11; ActivityId
0x140002f8a  mov     [rbp+80h+var_F8], 8
0x140002f92  mov     [rsp+180h+var_108], 8
0x140002f9b  movzx   eax, word ptr [rax]
0x140002f9e  mov     [rsp+180h+var_130.Size], eax
0x140002fa2  movzx   eax, word ptr [rcx]
0x140002fa5  mov     [rsp+180h+var_118], eax
0x140002fa9  lea     rax, _TraceLoggingMetadataEnd
0x140002fb0  mov     [rsp+180h+var_120], rcx
0x140002fb5  lea     rcx, _TraceLoggingMetadata
0x140002fbc  sub     eax, ecx
0x140002fbe  mov     dword ptr [rsp+180h+var_130.0Ch], 2
0x140002fc6  mov     [rsp+180h+var_114], 1
0x140002fce  mov     [rsp+180h+var_150], eax
0x140002fd2  mov     eax, [rsp+180h+var_150]
0x140002fd6  mov     rcx, [r10+20h]; RegHandle
0x140002fda  lea     rax, [rsp+180h+var_130]
0x140002fdf  mov     [rsp+180h+UserData], rax; UserData
0x140002fe4  mov     [rsp+180h+UserDataCount], 12h; UserDataCount
0x140002fec  call    cs:__imp_EventWriteTransfer
0x140002ff2  mov     rcx, [rbp+80h+var_10]
0x140002ff6  xor     rcx, rsp; StackCookie
0x140002ff9  call    __security_check_cookie
0x140002ffe  add     rsp, 180h
0x140003005  pop     rbp
0x140003006  retn
```
