# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001d7c`
- end: `0x14000208e`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `786`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14002b130`
- `0x140047b70`
- `0x14004dc30`

## callees

- `0x140001d7c`
- `0x14001bd40`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002062`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002062`

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
  int *v24; // r8
  __int64 v25; // rax
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  int *v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // rdx
  __int64 v37; // rax
  int v38; // eax
  int *v39; // rdx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  int v46; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v50; // [rsp+60h] [rbp-A0h]
  int v51; // [rsp+68h] [rbp-98h]
  int v52; // [rsp+6Ch] [rbp-94h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  int *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  __int64 v77; // [rsp+110h] [rbp+10h]
  __int64 v78; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v79; // [rsp+120h] [rbp+20h]
  int v80; // [rsp+128h] [rbp+28h]
  int v81; // [rsp+12Ch] [rbp+2Ch]
  int *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  __int64 v85; // [rsp+140h] [rbp+40h]
  __int64 v86; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v87; // [rsp+150h] [rbp+50h]
  int v88; // [rsp+158h] [rbp+58h]
  int v89; // [rsp+15Ch] [rbp+5Ch]
  int *v90; // [rsp+160h] [rbp+60h]
  int v91; // [rsp+168h] [rbp+68h]
  int v92; // [rsp+16Ch] [rbp+6Ch]

  v22 = -1;
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
    v24 = &dword_14008BB54;
    v26 = 2;
  }
  v91 = v26;
  v90 = v24;
  v92 = 0;
  v27 = *a19;
  if ( *a19 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &word_14008BBFE;
    v29 = 1;
  }
  v88 = v29;
  v85 = a18;
  v87 = v27;
  v89 = 0;
  v86 = 4;
  v30 = *a17;
  if ( *a17 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &dword_14008BB54;
    v32 = 2;
  }
  v83 = v32;
  v82 = v30;
  v84 = 0;
  v33 = *a16;
  if ( *a16 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &word_14008BBFE;
    v35 = 1;
  }
  v80 = v35;
  v77 = a15;
  v79 = v33;
  v81 = 0;
  v78 = 4;
  v36 = *a14;
  if ( *a14 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &word_14008BBFE;
    v38 = 1;
  }
  v75 = v38;
  v72 = a13;
  v74 = v36;
  v76 = 0;
  v73 = 4;
  v39 = *a12;
  if ( *a12 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_WORD *)v39 + v40) );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = &dword_14008BB54;
    v41 = 2;
  }
  v70 = v41;
  v67 = a11;
  v69 = v39;
  v71 = 0;
  v68 = 4;
  v42 = *a10;
  if ( *a10 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &word_14008BBFE;
    v44 = 1;
  }
  v65 = v44;
  v62 = a9;
  v64 = v42;
  v66 = 0;
  v63 = 4;
  v45 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v45 + v22) );
    v46 = v22 + 1;
  }
  else
  {
    v45 = &word_14008BBFE;
    v46 = 1;
  }
  v57 = a7;
  v55 = a6;
  v53 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v60 = v46;
  v59 = v45;
  v61 = 0;
  v58 = 4;
  v56 = 8;
  v54 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v51 = *(unsigned __int16 *)(a2 + 11);
  v50 = a2 + 11;
  UserData.Reserved = 2;
  v52 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 0x12u, &UserData);
}

```

## disassembly

```asm
0x140001d7c  mov     [rsp-8+arg_8], rbx
0x140001d81  push    rbp
0x140001d82  push    rsi
0x140001d83  push    rdi
0x140001d84  lea     rbp, [rsp-80h]
0x140001d89  sub     rsp, 180h
0x140001d90  mov     rax, cs:__security_cookie
0x140001d97  xor     rax, rsp
0x140001d9a  mov     [rbp+90h+var_20], rax
0x140001d9e  mov     rax, [rbp+90h+arg_98]
0x140001da5  mov     r11, r8
0x140001da8  mov     r10, rcx
0x140001dab  xor     ebx, ebx
0x140001dad  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001db1  mov     r9, rdx
0x140001db4  mov     r8, [rax]
0x140001db7  test    r8, r8
0x140001dba  jz      short loc_140001DD2
0x140001dbc  mov     rax, rcx
0x140001dbf  inc     rax
0x140001dc2  cmp     [r8+rax*2], bx
0x140001dc7  jnz     short loc_140001DBF
0x140001dc9  lea     eax, ds:2[rax*2]
0x140001dd0  jmp     short loc_140001DDE
0x140001dd2  lea     r8, dword_14008BB54
0x140001dd9  mov     eax, 2
0x140001dde  mov     [rbp+90h+var_28], eax
0x140001de1  mov     edi, 1
0x140001de6  mov     rax, [rbp+90h+arg_90]
0x140001ded  mov     [rbp+90h+var_30], r8
0x140001df1  lea     r8, word_14008BBFE
0x140001df8  mov     [rbp+90h+var_24], ebx
0x140001dfb  mov     rdx, [rax]
0x140001dfe  test    rdx, rdx
0x140001e01  jz      short loc_140001E12
0x140001e03  mov     rax, rcx
0x140001e06  inc     rax
0x140001e09  cmp     [rdx+rax], bl
0x140001e0c  jnz     short loc_140001E06
0x140001e0e  inc     eax
0x140001e10  jmp     short loc_140001E17
0x140001e12  mov     rdx, r8
0x140001e15  mov     eax, edi
0x140001e17  mov     [rbp+90h+var_38], eax
0x140001e1a  mov     rax, [rbp+90h+arg_88]
0x140001e21  mov     [rbp+90h+var_50], rax
0x140001e25  mov     rax, [rbp+90h+arg_80]
0x140001e2c  mov     [rbp+90h+var_40], rdx
0x140001e30  mov     [rbp+90h+var_34], ebx
0x140001e33  mov     [rbp+90h+var_48], 4
0x140001e3b  mov     rdx, [rax]
0x140001e3e  test    rdx, rdx
0x140001e41  jz      short loc_140001E58
0x140001e43  mov     rax, rcx
0x140001e46  inc     rax
0x140001e49  cmp     [rdx+rax*2], bx
0x140001e4d  jnz     short loc_140001E46
0x140001e4f  lea     eax, ds:2[rax*2]
0x140001e56  jmp     short loc_140001E64
0x140001e58  lea     rdx, dword_14008BB54
0x140001e5f  mov     eax, 2
0x140001e64  mov     [rbp+90h+var_58], eax
0x140001e67  mov     rax, [rbp+90h+arg_78]
0x140001e6e  mov     [rbp+90h+var_60], rdx
0x140001e72  mov     [rbp+90h+var_54], ebx
0x140001e75  mov     rdx, [rax]
0x140001e78  test    rdx, rdx
0x140001e7b  jz      short loc_140001E8C
0x140001e7d  mov     rax, rcx
0x140001e80  inc     rax
0x140001e83  cmp     [rdx+rax], bl
0x140001e86  jnz     short loc_140001E80
0x140001e88  inc     eax
0x140001e8a  jmp     short loc_140001E91
0x140001e8c  mov     rdx, r8
0x140001e8f  mov     eax, edi
0x140001e91  mov     [rbp+90h+var_68], eax
0x140001e94  mov     rax, [rbp+90h+arg_70]
0x140001e9b  mov     [rbp+90h+var_80], rax
0x140001e9f  mov     rax, [rbp+90h+arg_68]
0x140001ea6  mov     [rbp+90h+var_70], rdx
0x140001eaa  mov     [rbp+90h+var_64], ebx
0x140001ead  mov     [rbp+90h+var_78], 4
0x140001eb5  mov     rdx, [rax]
0x140001eb8  test    rdx, rdx
0x140001ebb  jz      short loc_140001ECC
0x140001ebd  mov     rax, rcx
0x140001ec0  inc     rax
0x140001ec3  cmp     [rdx+rax], bl
0x140001ec6  jnz     short loc_140001EC0
0x140001ec8  inc     eax
0x140001eca  jmp     short loc_140001ED1
0x140001ecc  mov     rdx, r8
0x140001ecf  mov     eax, edi
0x140001ed1  mov     [rbp+90h+var_88], eax
0x140001ed4  mov     rax, [rbp+90h+arg_60]
0x140001edb  mov     [rbp+90h+var_A0], rax
0x140001edf  mov     rax, [rbp+90h+arg_58]
0x140001ee6  mov     [rbp+90h+var_90], rdx
0x140001eea  mov     [rbp+90h+var_84], ebx
0x140001eed  mov     [rbp+90h+var_98], 4
0x140001ef5  mov     rdx, [rax]
0x140001ef8  test    rdx, rdx
0x140001efb  jz      short loc_140001F12
0x140001efd  mov     rax, rcx
0x140001f00  inc     rax
0x140001f03  cmp     [rdx+rax*2], bx
0x140001f07  jnz     short loc_140001F00
0x140001f09  lea     eax, ds:2[rax*2]
0x140001f10  jmp     short loc_140001F1E
0x140001f12  lea     rdx, dword_14008BB54
0x140001f19  mov     eax, 2
0x140001f1e  mov     [rbp+90h+var_A8], eax
0x140001f21  mov     rax, [rbp+90h+arg_50]
0x140001f28  mov     [rbp+90h+var_C0], rax
0x140001f2c  mov     rax, [rbp+90h+arg_48]
0x140001f33  mov     [rbp+90h+var_B0], rdx
0x140001f37  mov     [rbp+90h+var_A4], ebx
0x140001f3a  mov     [rbp+90h+var_B8], 4
0x140001f42  mov     rdx, [rax]
0x140001f45  test    rdx, rdx
0x140001f48  jz      short loc_140001F59
0x140001f4a  mov     rax, rcx
0x140001f4d  inc     rax
0x140001f50  cmp     [rdx+rax], bl
0x140001f53  jnz     short loc_140001F4D
0x140001f55  inc     eax
0x140001f57  jmp     short loc_140001F5E
0x140001f59  mov     rdx, r8
0x140001f5c  mov     eax, edi
0x140001f5e  mov     [rbp+90h+var_C8], eax
0x140001f61  mov     rax, [rbp+90h+arg_40]
0x140001f68  mov     [rbp+90h+var_E0], rax
0x140001f6c  mov     rax, [rbp+90h+arg_38]
0x140001f73  mov     [rbp+90h+var_D0], rdx
0x140001f77  mov     [rbp+90h+var_C4], ebx
0x140001f7a  mov     [rbp+90h+var_D8], 4
0x140001f82  mov     rdx, [rax]
0x140001f85  test    rdx, rdx
0x140001f88  jz      short loc_140001F96
0x140001f8a  inc     rcx
0x140001f8d  cmp     [rdx+rcx], bl
0x140001f90  jnz     short loc_140001F8A
0x140001f92  inc     ecx
0x140001f94  jmp     short loc_140001F9B
0x140001f96  mov     rdx, r8
0x140001f99  mov     ecx, edi
0x140001f9b  mov     rax, [rbp+90h+arg_30]
0x140001fa2  mov     r8, r11; ActivityId
0x140001fa5  mov     [rbp+90h+var_100], rax
0x140001fa9  mov     rax, [rbp+90h+arg_28]
0x140001fb0  mov     [rbp+90h+var_110], rax
0x140001fb4  mov     rax, [rbp+90h+arg_20]
0x140001fbb  mov     [rsp+190h+var_120], rax
0x140001fc0  movzx   eax, byte ptr [r9]
0x140001fc4  shl     eax, 18h
0x140001fc7  mov     dword ptr [rsp+190h+EventDescriptor.Id], eax
0x140001fcb  movzx   eax, word ptr [r9+1]
0x140001fd0  mov     dword ptr [rsp+190h+EventDescriptor.Level], eax
0x140001fd4  mov     rax, [r9+3]
0x140001fd8  mov     [rsp+190h+EventDescriptor.Keyword], rax
0x140001fdd  mov     rax, [r10+8]
0x140001fe1  mov     [rsp+190h+var_140.Ptr], rax
0x140001fe6  mov     [rbp+90h+var_E8], ecx
0x140001fe9  lea     rcx, [r9+0Bh]
0x140001fed  mov     [rbp+90h+var_F0], rdx
0x140001ff1  xor     r9d, r9d; RelatedActivityId
0x140001ff4  mov     [rbp+90h+var_E4], ebx
0x140001ff7  lea     rdx, [rsp+190h+EventDescriptor]; EventDescriptor
0x140001ffc  mov     [rbp+90h+var_F8], 4
0x140002004  mov     [rbp+90h+var_108], 8
0x14000200c  mov     [rsp+190h+var_118], 8
0x140002015  movzx   eax, word ptr [rax]
0x140002018  mov     [rsp+190h+var_140.Size], eax
0x14000201c  movzx   eax, word ptr [rcx]
0x14000201f  mov     [rsp+190h+var_128], eax
0x140002023  lea     rax, _TraceLoggingMetadataEnd
0x14000202a  mov     [rsp+190h+var_130], rcx
0x14000202f  lea     rcx, _TraceLoggingMetadata
0x140002036  sub     eax, ecx
0x140002038  mov     dword ptr [rsp+190h+var_140.0Ch], 2
0x140002040  mov     [rsp+190h+var_124], edi
0x140002044  mov     [rsp+190h+var_160], eax
0x140002048  mov     eax, [rsp+190h+var_160]
0x14000204c  mov     rcx, [r10+20h]; RegHandle
0x140002050  lea     rax, [rsp+190h+var_140]
0x140002055  mov     [rsp+190h+UserData], rax; UserData
0x14000205a  mov     [rsp+190h+UserDataCount], 12h; UserDataCount
0x140002062  call    cs:__imp_EventWriteTransfer
0x140002069  nop     dword ptr [rax+rax+00h]
0x14000206e  mov     rcx, [rbp+90h+var_20]
0x140002072  xor     rcx, rsp; StackCookie
0x140002075  call    __security_check_cookie
0x14000207a  mov     rbx, [rsp+190h+arg_8]
0x140002082  add     rsp, 180h
0x140002089  pop     rdi
0x14000208a  pop     rsi
0x14000208b  pop     rbp
0x14000208c  retn
```
