# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001ce0`
- end: `0x180002087`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `935`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const wchar_t **, const wchar_t **, __int64, const wchar_t **, const wchar_t **, __int64, __int64, const wchar_t **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010480`
- `0x1800124a0`

## callees

- `0x180001ce0`
- `0x1800181b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002069`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002069`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const wchar_t **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        const wchar_t **a11,
        __int64 a12,
        const wchar_t **a13,
        __int64 a14,
        const wchar_t **a15,
        const wchar_t **a16,
        __int64 a17,
        const wchar_t **a18,
        const wchar_t **a19,
        __int64 a20,
        __int64 a21,
        const wchar_t **a22)
{
  __int64 v25; // rcx
  const wchar_t *v26; // r8
  __int64 v27; // rax
  int v28; // eax
  const wchar_t *v29; // rdx
  __int64 v30; // rax
  bool v31; // zf
  int v32; // eax
  const wchar_t *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  const wchar_t *v36; // rdx
  __int64 v37; // rax
  int v38; // eax
  const wchar_t *v39; // rdx
  __int64 v40; // rax
  int v41; // eax
  const wchar_t *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const wchar_t *v45; // rdx
  __int64 v46; // rax
  int v47; // eax
  const wchar_t *v48; // rdx
  __int64 v49; // rax
  int v50; // eax
  const wchar_t *v51; // rdx
  int v52; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v56; // [rsp+60h] [rbp-A0h]
  int v57; // [rsp+68h] [rbp-98h]
  int v58; // [rsp+6Ch] [rbp-94h]
  __int64 v59; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+78h] [rbp-88h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const wchar_t *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  const wchar_t *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const wchar_t *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const wchar_t *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  __int64 v81; // [rsp+100h] [rbp+0h]
  __int64 v82; // [rsp+108h] [rbp+8h]
  const wchar_t *v83; // [rsp+110h] [rbp+10h]
  int v84; // [rsp+118h] [rbp+18h]
  int v85; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  __int64 v89; // [rsp+130h] [rbp+30h]
  __int64 v90; // [rsp+138h] [rbp+38h]
  const wchar_t *v91; // [rsp+140h] [rbp+40h]
  int v92; // [rsp+148h] [rbp+48h]
  int v93; // [rsp+14Ch] [rbp+4Ch]
  const wchar_t *v94; // [rsp+150h] [rbp+50h]
  int v95; // [rsp+158h] [rbp+58h]
  int v96; // [rsp+15Ch] [rbp+5Ch]
  __int64 v97; // [rsp+160h] [rbp+60h]
  __int64 v98; // [rsp+168h] [rbp+68h]
  __int64 v99; // [rsp+170h] [rbp+70h]
  __int64 v100; // [rsp+178h] [rbp+78h]
  const wchar_t *v101; // [rsp+180h] [rbp+80h]
  int v102; // [rsp+188h] [rbp+88h]
  int v103; // [rsp+18Ch] [rbp+8Ch]

  v25 = -1;
  v26 = *a22;
  if ( *a22 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &qword_1800250A8;
    v28 = 1;
  }
  v102 = v28;
  v99 = a21;
  v97 = a20;
  v101 = v26;
  v103 = 0;
  v100 = 4;
  v29 = *a19;
  v98 = 4;
  if ( v29 )
  {
    v30 = -1;
    do
      v31 = v29[++v30] == 0;
    while ( !v31 );
    v32 = 2 * v30 + 2;
  }
  else
  {
    v29 = &S2;
    v32 = 2;
  }
  v95 = v32;
  v94 = v29;
  v96 = 0;
  v33 = *a18;
  if ( *a18 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &qword_1800250A8;
    v35 = 1;
  }
  v92 = v35;
  v89 = a17;
  v91 = v33;
  v93 = 0;
  v90 = 4;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      v31 = v36[++v37] == 0;
    while ( !v31 );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &S2;
    v38 = 2;
  }
  v87 = v38;
  v86 = v36;
  v88 = 0;
  v39 = *a15;
  if ( *a15 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &qword_1800250A8;
    v41 = 1;
  }
  v84 = v41;
  v81 = a14;
  v83 = v39;
  v85 = 0;
  v82 = 4;
  v42 = *a13;
  if ( *a13 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &qword_1800250A8;
    v44 = 1;
  }
  v79 = v44;
  v76 = a12;
  v78 = v42;
  v80 = 0;
  v77 = 4;
  v45 = *a11;
  if ( *a11 )
  {
    v46 = -1;
    do
      v31 = v45[++v46] == 0;
    while ( !v31 );
    v47 = 2 * v46 + 2;
  }
  else
  {
    v45 = &S2;
    v47 = 2;
  }
  v74 = v47;
  v71 = a10;
  v73 = v45;
  v75 = 0;
  v72 = 4;
  v48 = *a9;
  if ( *a9 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &qword_1800250A8;
    v50 = 1;
  }
  v69 = v50;
  v66 = a8;
  v68 = v48;
  v70 = 0;
  v67 = 4;
  v51 = *a7;
  if ( *a7 )
  {
    do
      ++v25;
    while ( *((_BYTE *)v51 + v25) );
    v52 = v25 + 1;
  }
  else
  {
    v51 = &qword_1800250A8;
    v52 = 1;
  }
  v61 = a6;
  v59 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v64 = v52;
  v63 = v51;
  v65 = 0;
  v62 = 4;
  v60 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v57 = *(unsigned __int16 *)(a2 + 11);
  v56 = a2 + 11;
  UserData.Reserved = 2;
  v58 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 0x14u, &UserData);
}

```

## disassembly

```asm
0x180001ce0  push    rbp
0x180001ce2  lea     rbp, [rsp-0A0h]
0x180001cea  sub     rsp, 1A0h
0x180001cf1  mov     rax, cs:__security_cookie
0x180001cf8  xor     rax, rsp
0x180001cfb  mov     [rbp+0A0h+var_10], rax
0x180001d02  mov     rax, [rbp+0A0h+arg_A8]
0x180001d09  mov     r11, r8
0x180001d0c  mov     r10, rcx
0x180001d0f  mov     r9, rdx
0x180001d12  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001d19  mov     r8, [rax]
0x180001d1c  test    r8, r8
0x180001d1f  jz      short loc_180001D32
0x180001d21  mov     rax, rcx
0x180001d24  inc     rax
0x180001d27  cmp     byte ptr [r8+rax], 0
0x180001d2c  jnz     short loc_180001D24
0x180001d2e  inc     eax
0x180001d30  jmp     short loc_180001D3E
0x180001d32  lea     r8, qword_1800250A8
0x180001d39  mov     eax, 1
0x180001d3e  mov     [rbp+0A0h+var_18], eax
0x180001d44  mov     rax, [rbp+0A0h+arg_A0]
0x180001d4b  mov     [rbp+0A0h+var_30], rax
0x180001d4f  mov     rax, [rbp+0A0h+arg_98]
0x180001d56  mov     [rbp+0A0h+var_40], rax
0x180001d5a  mov     rax, [rbp+0A0h+arg_90]
0x180001d61  mov     [rbp+0A0h+var_20], r8
0x180001d68  xor     r8d, r8d
0x180001d6b  mov     [rbp+0A0h+var_14], r8d
0x180001d72  mov     [rbp+0A0h+var_28], 4
0x180001d7a  mov     rdx, [rax]
0x180001d7d  mov     [rbp+0A0h+var_38], 4
0x180001d85  test    rdx, rdx
0x180001d88  jz      short loc_180001DA5
0x180001d8a  mov     rax, rcx
0x180001d8d  nop     dword ptr [rax]
0x180001d90  cmp     [rdx+rax*2+2], r8w
0x180001d96  lea     rax, [rax+1]
0x180001d9a  jnz     short loc_180001D90
0x180001d9c  lea     eax, ds:2[rax*2]
0x180001da3  jmp     short loc_180001DB1
0x180001da5  lea     rdx, S2
0x180001dac  mov     eax, 2
0x180001db1  mov     [rbp+0A0h+var_48], eax
0x180001db4  mov     rax, [rbp+0A0h+arg_88]
0x180001dbb  mov     [rbp+0A0h+var_50], rdx
0x180001dbf  mov     [rbp+0A0h+var_44], r8d
0x180001dc3  mov     rdx, [rax]
0x180001dc6  test    rdx, rdx
0x180001dc9  jz      short loc_180001DDD
0x180001dcb  mov     rax, rcx
0x180001dce  xchg    ax, ax
0x180001dd0  inc     rax
0x180001dd3  cmp     [rdx+rax], r8b
0x180001dd7  jnz     short loc_180001DD0
0x180001dd9  inc     eax
0x180001ddb  jmp     short loc_180001DE9
0x180001ddd  lea     rdx, qword_1800250A8
0x180001de4  mov     eax, 1
0x180001de9  mov     [rbp+0A0h+var_58], eax
0x180001dec  mov     rax, [rbp+0A0h+arg_80]
0x180001df3  mov     [rbp+0A0h+var_70], rax
0x180001df7  mov     rax, [rbp+0A0h+arg_78]
0x180001dfe  mov     [rbp+0A0h+var_60], rdx
0x180001e02  mov     [rbp+0A0h+var_54], r8d
0x180001e06  mov     [rbp+0A0h+var_68], 4
0x180001e0e  mov     rdx, [rax]
0x180001e11  test    rdx, rdx
0x180001e14  jz      short loc_180001E35
0x180001e16  mov     rax, rcx
0x180001e19  nop     dword ptr [rax+00000000h]
0x180001e20  cmp     [rdx+rax*2+2], r8w
0x180001e26  lea     rax, [rax+1]
0x180001e2a  jnz     short loc_180001E20
0x180001e2c  lea     eax, ds:2[rax*2]
0x180001e33  jmp     short loc_180001E41
0x180001e35  lea     rdx, S2
0x180001e3c  mov     eax, 2
0x180001e41  mov     [rbp+0A0h+var_78], eax
0x180001e44  mov     rax, [rbp+0A0h+arg_70]
0x180001e4b  mov     [rbp+0A0h+var_80], rdx
0x180001e4f  mov     [rbp+0A0h+var_74], r8d
0x180001e53  mov     rdx, [rax]
0x180001e56  test    rdx, rdx
0x180001e59  jz      short loc_180001E6D
0x180001e5b  mov     rax, rcx
0x180001e5e  xchg    ax, ax
0x180001e60  inc     rax
0x180001e63  cmp     [rdx+rax], r8b
0x180001e67  jnz     short loc_180001E60
0x180001e69  inc     eax
0x180001e6b  jmp     short loc_180001E79
0x180001e6d  lea     rdx, qword_1800250A8
0x180001e74  mov     eax, 1
0x180001e79  mov     [rbp+0A0h+var_88], eax
0x180001e7c  mov     rax, [rbp+0A0h+arg_68]
0x180001e83  mov     [rbp+0A0h+var_A0], rax
0x180001e87  mov     rax, [rbp+0A0h+arg_60]
0x180001e8e  mov     [rbp+0A0h+var_90], rdx
0x180001e92  mov     [rbp+0A0h+var_84], r8d
0x180001e96  mov     [rbp+0A0h+var_98], 4
0x180001e9e  mov     rdx, [rax]
0x180001ea1  test    rdx, rdx
0x180001ea4  jz      short loc_180001EBD
0x180001ea6  mov     rax, rcx
0x180001ea9  nop     dword ptr [rax+00000000h]
0x180001eb0  inc     rax
0x180001eb3  cmp     [rdx+rax], r8b
0x180001eb7  jnz     short loc_180001EB0
0x180001eb9  inc     eax
0x180001ebb  jmp     short loc_180001EC9
0x180001ebd  lea     rdx, qword_1800250A8
0x180001ec4  mov     eax, 1
0x180001ec9  mov     [rbp+0A0h+var_A8], eax
0x180001ecc  mov     rax, [rbp+0A0h+arg_58]
0x180001ed3  mov     [rbp+0A0h+var_C0], rax
0x180001ed7  mov     rax, [rbp+0A0h+arg_50]
0x180001ede  mov     [rbp+0A0h+var_B0], rdx
0x180001ee2  mov     [rbp+0A0h+var_A4], r8d
0x180001ee6  mov     [rbp+0A0h+var_B8], 4
0x180001eee  mov     rdx, [rax]
0x180001ef1  test    rdx, rdx
0x180001ef4  jz      short loc_180001F15
0x180001ef6  mov     rax, rcx
0x180001ef9  nop     dword ptr [rax+00000000h]
0x180001f00  cmp     [rdx+rax*2+2], r8w
0x180001f06  lea     rax, [rax+1]
0x180001f0a  jnz     short loc_180001F00
0x180001f0c  lea     eax, ds:2[rax*2]
0x180001f13  jmp     short loc_180001F21
0x180001f15  lea     rdx, S2
0x180001f1c  mov     eax, 2
0x180001f21  mov     [rbp+0A0h+var_C8], eax
0x180001f24  mov     rax, [rbp+0A0h+arg_48]
0x180001f2b  mov     [rbp+0A0h+var_E0], rax
0x180001f2f  mov     rax, [rbp+0A0h+arg_40]
0x180001f36  mov     [rbp+0A0h+var_D0], rdx
0x180001f3a  mov     [rbp+0A0h+var_C4], r8d
0x180001f3e  mov     [rbp+0A0h+var_D8], 4
0x180001f46  mov     rdx, [rax]
0x180001f49  test    rdx, rdx
0x180001f4c  jz      short loc_180001F5E
0x180001f4e  mov     rax, rcx
0x180001f51  inc     rax
0x180001f54  cmp     [rdx+rax], r8b
0x180001f58  jnz     short loc_180001F51
0x180001f5a  inc     eax
0x180001f5c  jmp     short loc_180001F6A
0x180001f5e  lea     rdx, qword_1800250A8
0x180001f65  mov     eax, 1
0x180001f6a  mov     [rbp+0A0h+var_E8], eax
0x180001f6d  mov     rax, [rbp+0A0h+arg_38]
0x180001f74  mov     [rbp+0A0h+var_100], rax
0x180001f78  mov     rax, [rbp+0A0h+arg_30]
0x180001f7f  mov     [rbp+0A0h+var_F0], rdx
0x180001f83  mov     [rbp+0A0h+var_E4], r8d
0x180001f87  mov     [rbp+0A0h+var_F8], 4
0x180001f8f  mov     rdx, [rax]
0x180001f92  test    rdx, rdx
0x180001f95  jz      short loc_180001FA4
0x180001f97  inc     rcx
0x180001f9a  cmp     [rdx+rcx], r8b
0x180001f9e  jnz     short loc_180001F97
0x180001fa0  inc     ecx
0x180001fa2  jmp     short loc_180001FB0
0x180001fa4  lea     rdx, qword_1800250A8
0x180001fab  mov     ecx, 1
0x180001fb0  mov     rax, [rbp+0A0h+arg_28]
0x180001fb7  mov     [rbp+0A0h+var_120], rax
0x180001fbb  mov     rax, [rbp+0A0h+arg_20]
0x180001fc2  mov     [rsp+1A0h+var_130], rax
0x180001fc7  movzx   eax, byte ptr [r9]
0x180001fcb  shl     eax, 18h
0x180001fce  mov     dword ptr [rsp+1A0h+EventDescriptor.Id], eax
0x180001fd2  movzx   eax, word ptr [r9+1]
0x180001fd7  mov     dword ptr [rsp+1A0h+EventDescriptor.Level], eax
0x180001fdb  mov     rax, [r9+3]
0x180001fdf  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x180001fe4  mov     rax, [r10+8]
0x180001fe8  mov     [rsp+1A0h+var_150.Ptr], rax
0x180001fed  mov     [rbp+0A0h+var_108], ecx
0x180001ff0  lea     rcx, [r9+0Bh]
0x180001ff4  mov     [rbp+0A0h+var_110], rdx
0x180001ff8  xor     r9d, r9d; RelatedActivityId
0x180001ffb  mov     [rbp+0A0h+var_104], r8d
0x180001fff  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x180002004  mov     [rbp+0A0h+var_118], 4
0x18000200c  mov     r8, r11; ActivityId
0x18000200f  mov     [rsp+1A0h+var_128], 8
0x180002018  movzx   eax, word ptr [rax]
0x18000201b  mov     [rsp+1A0h+var_150.Size], eax
0x18000201f  movzx   eax, word ptr [rcx]
0x180002022  mov     [rsp+1A0h+var_138], eax
0x180002026  lea     rax, _TraceLoggingMetadataEnd
0x18000202d  mov     [rsp+1A0h+var_140], rcx
0x180002032  lea     rcx, _TraceLoggingMetadata
0x180002039  sub     eax, ecx
0x18000203b  mov     dword ptr [rsp+1A0h+var_150.0Ch], 2
0x180002043  mov     [rsp+1A0h+var_134], 1
0x18000204b  mov     [rsp+1A0h+var_170], eax
0x18000204f  mov     eax, [rsp+1A0h+var_170]
0x180002053  mov     rcx, [r10+20h]; RegHandle
0x180002057  lea     rax, [rsp+1A0h+var_150]
0x18000205c  mov     [rsp+1A0h+UserData], rax; UserData
0x180002061  mov     [rsp+1A0h+UserDataCount], 14h; UserDataCount
0x180002069  call    cs:__imp_EventWriteTransfer
0x18000206f  mov     rcx, [rbp+0A0h+var_10]
0x180002076  xor     rcx, rsp; StackCookie
0x180002079  call    __security_check_cookie
0x18000207e  add     rsp, 1A0h
0x180002085  pop     rbp
0x180002086  retn
```
