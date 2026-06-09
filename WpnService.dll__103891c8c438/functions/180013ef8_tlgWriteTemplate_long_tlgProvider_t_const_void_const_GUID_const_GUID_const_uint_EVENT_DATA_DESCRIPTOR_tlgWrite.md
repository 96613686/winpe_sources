# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180013ef8`
- end: `0x180014255`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `861`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180018460`
- `0x18002a0b8`
- `0x18002be10`
- `0x180030230`
- `0x180032500`

## callees

- `0x180013ef8`
- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001422d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001422d`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
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
  __int64 v24; // rcx
  const unsigned __int16 *v26; // r8
  __int64 v27; // rax
  int v28; // eax
  int *v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  int *v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // rdx
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // rdx
  __int64 v42; // rax
  int v43; // eax
  int *v44; // rdx
  __int64 v45; // rax
  int v46; // eax
  const unsigned __int16 *v47; // rdx
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rdx
  int v51; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v55; // [rsp+60h] [rbp-A0h]
  int v56; // [rsp+68h] [rbp-98h]
  int v57; // [rsp+6Ch] [rbp-94h]
  __int64 v58; // [rsp+70h] [rbp-90h]
  __int64 v59; // [rsp+78h] [rbp-88h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  int *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  __int64 v80; // [rsp+100h] [rbp+0h]
  __int64 v81; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  int *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  __int64 v88; // [rsp+130h] [rbp+30h]
  __int64 v89; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v90; // [rsp+140h] [rbp+40h]
  int v91; // [rsp+148h] [rbp+48h]
  int v92; // [rsp+14Ch] [rbp+4Ch]
  int *v93; // [rsp+150h] [rbp+50h]
  int v94; // [rsp+158h] [rbp+58h]
  int v95; // [rsp+15Ch] [rbp+5Ch]
  __int64 v96; // [rsp+160h] [rbp+60h]
  __int64 v97; // [rsp+168h] [rbp+68h]
  __int64 v98; // [rsp+170h] [rbp+70h]
  __int64 v99; // [rsp+178h] [rbp+78h]
  const unsigned __int16 *v100; // [rsp+180h] [rbp+80h]
  int v101; // [rsp+188h] [rbp+88h]
  int v102; // [rsp+18Ch] [rbp+8Ch]

  v24 = -1;
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
    v26 = &byte_18003A073;
    v28 = 1;
  }
  v101 = v28;
  v98 = a21;
  v96 = a20;
  v100 = v26;
  v102 = 0;
  v99 = 4;
  v29 = *a19;
  v97 = 4;
  if ( v29 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)v29 + v30) );
    v31 = 2 * v30 + 2;
  }
  else
  {
    v29 = &dword_18003A074;
    v31 = 2;
  }
  v94 = v31;
  v93 = v29;
  v95 = 0;
  v32 = *a18;
  if ( *a18 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_BYTE *)v32 + v33) );
    v34 = v33 + 1;
  }
  else
  {
    v32 = &byte_18003A073;
    v34 = 1;
  }
  v91 = v34;
  v88 = a17;
  v90 = v32;
  v92 = 0;
  v89 = 4;
  v35 = *a16;
  if ( *a16 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_WORD *)v35 + v36) );
    v37 = 2 * v36 + 2;
  }
  else
  {
    v35 = &dword_18003A074;
    v37 = 2;
  }
  v86 = v37;
  v85 = v35;
  v87 = 0;
  v38 = *a15;
  if ( *a15 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &byte_18003A073;
    v40 = 1;
  }
  v83 = v40;
  v80 = a14;
  v82 = v38;
  v84 = 0;
  v81 = 4;
  v41 = *a13;
  if ( *a13 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &byte_18003A073;
    v43 = 1;
  }
  v78 = v43;
  v75 = a12;
  v77 = v41;
  v79 = 0;
  v76 = 4;
  v44 = *a11;
  if ( *a11 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_WORD *)v44 + v45) );
    v46 = 2 * v45 + 2;
  }
  else
  {
    v44 = &dword_18003A074;
    v46 = 2;
  }
  v73 = v46;
  v70 = a10;
  v72 = v44;
  v74 = 0;
  v71 = 4;
  v47 = *a9;
  if ( *a9 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &byte_18003A073;
    v49 = 1;
  }
  v68 = v49;
  v65 = a8;
  v67 = v47;
  v69 = 0;
  v66 = 4;
  v50 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v50 + v24) );
    v51 = v24 + 1;
  }
  else
  {
    v50 = &byte_18003A073;
    v51 = 1;
  }
  v60 = a6;
  v58 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v63 = v51;
  v62 = v50;
  v64 = 0;
  v61 = 4;
  v59 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v56 = *(unsigned __int16 *)(a2 + 11);
  v55 = a2 + 11;
  UserData.Reserved = 2;
  v57 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 0x14u, &UserData);
}

```

## disassembly

```asm
0x180013ef8  mov     [rsp-8+arg_8], rbx
0x180013efd  push    rbp
0x180013efe  push    rsi
0x180013eff  push    rdi
0x180013f00  lea     rbp, [rsp-0A0h]
0x180013f08  sub     rsp, 1A0h
0x180013f0f  mov     rax, cs:__security_cookie
0x180013f16  xor     rax, rsp
0x180013f19  mov     [rbp+0B0h+var_20], rax
0x180013f20  mov     rax, [rbp+0B0h+arg_A8]
0x180013f27  lea     rdi, byte_18003A073
0x180013f2e  mov     r11, r8
0x180013f31  mov     r10, rcx
0x180013f34  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013f38  xor     ebx, ebx
0x180013f3a  mov     r9, rdx
0x180013f3d  mov     esi, 1
0x180013f42  mov     r8, [rax]
0x180013f45  test    r8, r8
0x180013f48  jz      short loc_180013F5A
0x180013f4a  mov     rax, rcx
0x180013f4d  inc     rax
0x180013f50  cmp     [r8+rax], bl
0x180013f54  jnz     short loc_180013F4D
0x180013f56  inc     eax
0x180013f58  jmp     short loc_180013F5F
0x180013f5a  mov     r8, rdi
0x180013f5d  mov     eax, esi
0x180013f5f  mov     [rbp+0B0h+var_28], eax
0x180013f65  mov     rax, [rbp+0B0h+arg_A0]
0x180013f6c  mov     [rbp+0B0h+var_40], rax
0x180013f70  mov     rax, [rbp+0B0h+arg_98]
0x180013f77  mov     [rbp+0B0h+var_50], rax
0x180013f7b  mov     rax, [rbp+0B0h+arg_90]
0x180013f82  mov     [rbp+0B0h+var_30], r8
0x180013f89  mov     [rbp+0B0h+var_24], ebx
0x180013f8f  mov     [rbp+0B0h+var_38], 4
0x180013f97  mov     rdx, [rax]
0x180013f9a  mov     [rbp+0B0h+var_48], 4
0x180013fa2  test    rdx, rdx
0x180013fa5  jz      short loc_180013FBC
0x180013fa7  mov     rax, rcx
0x180013faa  inc     rax
0x180013fad  cmp     [rdx+rax*2], bx
0x180013fb1  jnz     short loc_180013FAA
0x180013fb3  lea     eax, ds:2[rax*2]
0x180013fba  jmp     short loc_180013FC8
0x180013fbc  lea     rdx, dword_18003A074
0x180013fc3  mov     eax, 2
0x180013fc8  mov     [rbp+0B0h+var_58], eax
0x180013fcb  mov     rax, [rbp+0B0h+arg_88]
0x180013fd2  mov     [rbp+0B0h+var_60], rdx
0x180013fd6  mov     [rbp+0B0h+var_54], ebx
0x180013fd9  mov     rdx, [rax]
0x180013fdc  test    rdx, rdx
0x180013fdf  jz      short loc_180013FF0
0x180013fe1  mov     rax, rcx
0x180013fe4  inc     rax
0x180013fe7  cmp     [rdx+rax], bl
0x180013fea  jnz     short loc_180013FE4
0x180013fec  inc     eax
0x180013fee  jmp     short loc_180013FF5
0x180013ff0  mov     rdx, rdi
0x180013ff3  mov     eax, esi
0x180013ff5  mov     [rbp+0B0h+var_68], eax
0x180013ff8  mov     rax, [rbp+0B0h+arg_80]
0x180013fff  mov     [rbp+0B0h+var_80], rax
0x180014003  mov     rax, [rbp+0B0h+arg_78]
0x18001400a  mov     [rbp+0B0h+var_70], rdx
0x18001400e  mov     [rbp+0B0h+var_64], ebx
0x180014011  mov     [rbp+0B0h+var_78], 4
0x180014019  mov     rdx, [rax]
0x18001401c  test    rdx, rdx
0x18001401f  jz      short loc_180014036
0x180014021  mov     rax, rcx
0x180014024  inc     rax
0x180014027  cmp     [rdx+rax*2], bx
0x18001402b  jnz     short loc_180014024
0x18001402d  lea     eax, ds:2[rax*2]
0x180014034  jmp     short loc_180014042
0x180014036  lea     rdx, dword_18003A074
0x18001403d  mov     eax, 2
0x180014042  mov     [rbp+0B0h+var_88], eax
0x180014045  mov     rax, [rbp+0B0h+arg_70]
0x18001404c  mov     [rbp+0B0h+var_90], rdx
0x180014050  mov     [rbp+0B0h+var_84], ebx
0x180014053  mov     rdx, [rax]
0x180014056  test    rdx, rdx
0x180014059  jz      short loc_18001406A
0x18001405b  mov     rax, rcx
0x18001405e  inc     rax
0x180014061  cmp     [rdx+rax], bl
0x180014064  jnz     short loc_18001405E
0x180014066  inc     eax
0x180014068  jmp     short loc_18001406F
0x18001406a  mov     rdx, rdi
0x18001406d  mov     eax, esi
0x18001406f  mov     [rbp+0B0h+var_98], eax
0x180014072  mov     rax, [rbp+0B0h+arg_68]
0x180014079  mov     [rbp+0B0h+var_B0], rax
0x18001407d  mov     rax, [rbp+0B0h+arg_60]
0x180014084  mov     [rbp+0B0h+var_A0], rdx
0x180014088  mov     [rbp+0B0h+var_94], ebx
0x18001408b  mov     [rbp+0B0h+var_A8], 4
0x180014093  mov     rdx, [rax]
0x180014096  test    rdx, rdx
0x180014099  jz      short loc_1800140AA
0x18001409b  mov     rax, rcx
0x18001409e  inc     rax
0x1800140a1  cmp     [rdx+rax], bl
0x1800140a4  jnz     short loc_18001409E
0x1800140a6  inc     eax
0x1800140a8  jmp     short loc_1800140AF
0x1800140aa  mov     rdx, rdi
0x1800140ad  mov     eax, esi
0x1800140af  mov     [rbp+0B0h+var_B8], eax
0x1800140b2  mov     rax, [rbp+0B0h+arg_58]
0x1800140b9  mov     [rbp+0B0h+var_D0], rax
0x1800140bd  mov     rax, [rbp+0B0h+arg_50]
0x1800140c4  mov     [rbp+0B0h+var_C0], rdx
0x1800140c8  mov     [rbp+0B0h+var_B4], ebx
0x1800140cb  mov     [rbp+0B0h+var_C8], 4
0x1800140d3  mov     rdx, [rax]
0x1800140d6  test    rdx, rdx
0x1800140d9  jz      short loc_1800140F0
0x1800140db  mov     rax, rcx
0x1800140de  inc     rax
0x1800140e1  cmp     [rdx+rax*2], bx
0x1800140e5  jnz     short loc_1800140DE
0x1800140e7  lea     eax, ds:2[rax*2]
0x1800140ee  jmp     short loc_1800140FC
0x1800140f0  lea     rdx, dword_18003A074
0x1800140f7  mov     eax, 2
0x1800140fc  mov     [rbp+0B0h+var_D8], eax
0x1800140ff  mov     rax, [rbp+0B0h+arg_48]
0x180014106  mov     [rbp+0B0h+var_F0], rax
0x18001410a  mov     rax, [rbp+0B0h+arg_40]
0x180014111  mov     [rbp+0B0h+var_E0], rdx
0x180014115  mov     [rbp+0B0h+var_D4], ebx
0x180014118  mov     [rbp+0B0h+var_E8], 4
0x180014120  mov     rdx, [rax]
0x180014123  test    rdx, rdx
0x180014126  jz      short loc_180014137
0x180014128  mov     rax, rcx
0x18001412b  inc     rax
0x18001412e  cmp     [rdx+rax], bl
0x180014131  jnz     short loc_18001412B
0x180014133  inc     eax
0x180014135  jmp     short loc_18001413C
0x180014137  mov     rdx, rdi
0x18001413a  mov     eax, esi
0x18001413c  mov     [rbp+0B0h+var_F8], eax
0x18001413f  mov     rax, [rbp+0B0h+arg_38]
0x180014146  mov     [rbp+0B0h+var_110], rax
0x18001414a  mov     rax, [rbp+0B0h+arg_30]
0x180014151  mov     [rbp+0B0h+var_100], rdx
0x180014155  mov     [rbp+0B0h+var_F4], ebx
0x180014158  mov     [rbp+0B0h+var_108], 4
0x180014160  mov     rdx, [rax]
0x180014163  test    rdx, rdx
0x180014166  jz      short loc_180014174
0x180014168  inc     rcx
0x18001416b  cmp     [rdx+rcx], bl
0x18001416e  jnz     short loc_180014168
0x180014170  inc     ecx
0x180014172  jmp     short loc_180014179
0x180014174  mov     rdx, rdi
0x180014177  mov     ecx, esi
0x180014179  mov     rax, [rbp+0B0h+arg_28]
0x180014180  mov     r8, r11; ActivityId
0x180014183  mov     [rbp+0B0h+var_130], rax
0x180014187  mov     rax, [rbp+0B0h+arg_20]
0x18001418e  mov     [rsp+1B0h+var_140], rax
0x180014193  movzx   eax, byte ptr [r9]
0x180014197  shl     eax, 18h
0x18001419a  mov     dword ptr [rsp+1B0h+EventDescriptor.Id], eax
0x18001419e  movzx   eax, word ptr [r9+1]
0x1800141a3  mov     dword ptr [rsp+1B0h+EventDescriptor.Level], eax
0x1800141a7  mov     rax, [r9+3]
0x1800141ab  mov     [rsp+1B0h+EventDescriptor.Keyword], rax
0x1800141b0  mov     rax, [r10+8]
0x1800141b4  mov     [rsp+1B0h+var_160.Ptr], rax
0x1800141b9  mov     [rbp+0B0h+var_118], ecx
0x1800141bc  lea     rcx, [r9+0Bh]
0x1800141c0  mov     [rbp+0B0h+var_120], rdx
0x1800141c4  xor     r9d, r9d; RelatedActivityId
0x1800141c7  mov     [rbp+0B0h+var_114], ebx
0x1800141ca  lea     rdx, [rsp+1B0h+EventDescriptor]; EventDescriptor
0x1800141cf  mov     [rbp+0B0h+var_128], 4
0x1800141d7  mov     [rsp+1B0h+var_138], 8
0x1800141e0  movzx   eax, word ptr [rax]
0x1800141e3  mov     [rsp+1B0h+var_160.Size], eax
0x1800141e7  movzx   eax, word ptr [rcx]
0x1800141ea  mov     [rsp+1B0h+var_148], eax
0x1800141ee  lea     rax, _TraceLoggingMetadataEnd
0x1800141f5  mov     [rsp+1B0h+var_150], rcx
0x1800141fa  lea     rcx, _TraceLoggingMetadata
0x180014201  sub     eax, ecx
0x180014203  mov     dword ptr [rsp+1B0h+var_160.0Ch], 2
0x18001420b  mov     [rsp+1B0h+var_144], esi
0x18001420f  mov     [rsp+1B0h+var_180], eax
0x180014213  mov     eax, [rsp+1B0h+var_180]
0x180014217  mov     rcx, [r10+20h]; RegHandle
0x18001421b  lea     rax, [rsp+1B0h+var_160]
0x180014220  mov     [rsp+1B0h+UserData], rax; UserData
0x180014225  mov     [rsp+1B0h+UserDataCount], 14h; UserDataCount
0x18001422d  call    cs:__imp_EventWriteTransfer
0x180014233  mov     rcx, [rbp+0B0h+var_20]
0x18001423a  xor     rcx, rsp; StackCookie
0x18001423d  call    __security_check_cookie
0x180014242  mov     rbx, [rsp+1B0h+arg_8]
0x18001424a  add     rsp, 1A0h
0x180014251  pop     rdi
0x180014252  pop     rsi
0x180014253  pop     rbp
0x180014254  retn
```
