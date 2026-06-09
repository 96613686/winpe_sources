# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x18004fac4`
- end: `0x18004fe67`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `931`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005ce20`
- `0x18007c32c`

## callees

- `0x18004fac4`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004fdc9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004fdc9`

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
    v26 = &word_1800DBB72;
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
    v29 = &dword_1800DB714;
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
    v32 = &word_1800DBB72;
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
    v35 = &dword_1800DB714;
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
    v38 = &word_1800DBB72;
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
    v41 = &word_1800DBB72;
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
    v44 = &dword_1800DB714;
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
    v47 = &word_1800DBB72;
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
    v50 = &word_1800DBB72;
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
0x18004fac4  mov     [rsp-8+arg_8], rbx
0x18004fac9  push    rbp
0x18004faca  push    rsi
0x18004facb  push    rdi
0x18004facc  lea     rbp, [rsp-0A0h]
0x18004fad4  sub     rsp, 1A0h
0x18004fadb  mov     rax, cs:__security_cookie
0x18004fae2  xor     rax, rsp
0x18004fae5  mov     [rbp+0B0h+var_20], rax
0x18004faec  mov     rax, [rbp+0B0h+arg_A8]
0x18004faf3  lea     rdi, word_1800DBB72
0x18004fafa  mov     r11, r8
0x18004fafd  mov     r10, rcx
0x18004fb00  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004fb04  xor     ebx, ebx
0x18004fb06  mov     r9, rdx
0x18004fb09  mov     esi, 1
0x18004fb0e  mov     r8, [rax]
0x18004fb11  test    r8, r8
0x18004fb14  jz      loc_18004FE2B
0x18004fb1a  mov     rax, rcx
0x18004fb1d  inc     rax
0x18004fb20  cmp     [r8+rax], bl
0x18004fb24  jnz     short loc_18004FB1D
0x18004fb26  inc     eax
0x18004fb28  mov     [rbp+0B0h+var_28], eax
0x18004fb2e  mov     rax, [rbp+0B0h+arg_A0]
0x18004fb35  mov     [rbp+0B0h+var_40], rax
0x18004fb39  mov     rax, [rbp+0B0h+arg_98]
0x18004fb40  mov     [rbp+0B0h+var_50], rax
0x18004fb44  mov     rax, [rbp+0B0h+arg_90]
0x18004fb4b  mov     [rbp+0B0h+var_30], r8
0x18004fb52  mov     [rbp+0B0h+var_24], ebx
0x18004fb58  mov     [rbp+0B0h+var_38], 4
0x18004fb60  mov     rdx, [rax]
0x18004fb63  mov     [rbp+0B0h+var_48], 4
0x18004fb6b  test    rdx, rdx
0x18004fb6e  jz      loc_18004FDF8
0x18004fb74  mov     rax, rcx
0x18004fb77  inc     rax
0x18004fb7a  cmp     [rdx+rax*2], bx
0x18004fb7e  jnz     short loc_18004FB77
0x18004fb80  lea     eax, ds:2[rax*2]
0x18004fb87  mov     [rbp+0B0h+var_58], eax
0x18004fb8a  mov     rax, [rbp+0B0h+arg_88]
0x18004fb91  mov     [rbp+0B0h+var_60], rdx
0x18004fb95  mov     [rbp+0B0h+var_54], ebx
0x18004fb98  mov     rdx, [rax]
0x18004fb9b  test    rdx, rdx
0x18004fb9e  jz      loc_18004FE35
0x18004fba4  mov     rax, rcx
0x18004fba7  inc     rax
0x18004fbaa  cmp     [rdx+rax], bl
0x18004fbad  jnz     short loc_18004FBA7
0x18004fbaf  inc     eax
0x18004fbb1  mov     [rbp+0B0h+var_68], eax
0x18004fbb4  mov     rax, [rbp+0B0h+arg_80]
0x18004fbbb  mov     [rbp+0B0h+var_80], rax
0x18004fbbf  mov     rax, [rbp+0B0h+arg_78]
0x18004fbc6  mov     [rbp+0B0h+var_70], rdx
0x18004fbca  mov     [rbp+0B0h+var_64], ebx
0x18004fbcd  mov     [rbp+0B0h+var_78], 4
0x18004fbd5  mov     rdx, [rax]
0x18004fbd8  test    rdx, rdx
0x18004fbdb  jz      loc_18004FE09
0x18004fbe1  mov     rax, rcx
0x18004fbe4  inc     rax
0x18004fbe7  cmp     [rdx+rax*2], bx
0x18004fbeb  jnz     short loc_18004FBE4
0x18004fbed  lea     eax, ds:2[rax*2]
0x18004fbf4  mov     [rbp+0B0h+var_88], eax
0x18004fbf7  mov     rax, [rbp+0B0h+arg_70]
0x18004fbfe  mov     [rbp+0B0h+var_90], rdx
0x18004fc02  mov     [rbp+0B0h+var_84], ebx
0x18004fc05  mov     rdx, [rax]
0x18004fc08  test    rdx, rdx
0x18004fc0b  jz      loc_18004FE3F
0x18004fc11  mov     rax, rcx
0x18004fc14  inc     rax
0x18004fc17  cmp     [rdx+rax], bl
0x18004fc1a  jnz     short loc_18004FC14
0x18004fc1c  inc     eax
0x18004fc1e  mov     [rbp+0B0h+var_98], eax
0x18004fc21  mov     rax, [rbp+0B0h+arg_68]
0x18004fc28  mov     [rbp+0B0h+var_B0], rax
0x18004fc2c  mov     rax, [rbp+0B0h+arg_60]
0x18004fc33  mov     [rbp+0B0h+var_A0], rdx
0x18004fc37  mov     [rbp+0B0h+var_94], ebx
0x18004fc3a  mov     [rbp+0B0h+var_A8], 4
0x18004fc42  mov     rdx, [rax]
0x18004fc45  test    rdx, rdx
0x18004fc48  jz      loc_18004FE49
0x18004fc4e  mov     rax, rcx
0x18004fc51  inc     rax
0x18004fc54  cmp     [rdx+rax], bl
0x18004fc57  jnz     short loc_18004FC51
0x18004fc59  inc     eax
0x18004fc5b  mov     [rbp+0B0h+var_B8], eax
0x18004fc5e  mov     rax, [rbp+0B0h+arg_58]
0x18004fc65  mov     [rbp+0B0h+var_D0], rax
0x18004fc69  mov     rax, [rbp+0B0h+arg_50]
0x18004fc70  mov     [rbp+0B0h+var_C0], rdx
0x18004fc74  mov     [rbp+0B0h+var_B4], ebx
0x18004fc77  mov     [rbp+0B0h+var_C8], 4
0x18004fc7f  mov     rdx, [rax]
0x18004fc82  test    rdx, rdx
0x18004fc85  jz      loc_18004FE1A
0x18004fc8b  mov     rax, rcx
0x18004fc8e  inc     rax
0x18004fc91  cmp     [rdx+rax*2], bx
0x18004fc95  jnz     short loc_18004FC8E
0x18004fc97  lea     eax, ds:2[rax*2]
0x18004fc9e  mov     [rbp+0B0h+var_D8], eax
0x18004fca1  mov     rax, [rbp+0B0h+arg_48]
0x18004fca8  mov     [rbp+0B0h+var_F0], rax
0x18004fcac  mov     rax, [rbp+0B0h+arg_40]
0x18004fcb3  mov     [rbp+0B0h+var_E0], rdx
0x18004fcb7  mov     [rbp+0B0h+var_D4], ebx
0x18004fcba  mov     [rbp+0B0h+var_E8], 4
0x18004fcc2  mov     rdx, [rax]
0x18004fcc5  test    rdx, rdx
0x18004fcc8  jz      loc_18004FE53
0x18004fcce  mov     rax, rcx
0x18004fcd1  inc     rax
0x18004fcd4  cmp     [rdx+rax], bl
0x18004fcd7  jnz     short loc_18004FCD1
0x18004fcd9  inc     eax
0x18004fcdb  mov     [rbp+0B0h+var_F8], eax
0x18004fcde  mov     rax, [rbp+0B0h+arg_38]
0x18004fce5  mov     [rbp+0B0h+var_110], rax
0x18004fce9  mov     rax, [rbp+0B0h+arg_30]
0x18004fcf0  mov     [rbp+0B0h+var_100], rdx
0x18004fcf4  mov     [rbp+0B0h+var_F4], ebx
0x18004fcf7  mov     [rbp+0B0h+var_108], 4
0x18004fcff  mov     rdx, [rax]
0x18004fd02  test    rdx, rdx
0x18004fd05  jz      loc_18004FE5D
0x18004fd0b  inc     rcx
0x18004fd0e  cmp     [rdx+rcx], bl
0x18004fd11  jnz     short loc_18004FD0B
0x18004fd13  inc     ecx
0x18004fd15  mov     rax, [rbp+0B0h+arg_28]
0x18004fd1c  mov     r8, r11; ActivityId
0x18004fd1f  mov     [rbp+0B0h+var_130], rax
0x18004fd23  mov     rax, [rbp+0B0h+arg_20]
0x18004fd2a  mov     [rsp+1B0h+var_140], rax
0x18004fd2f  movzx   eax, byte ptr [r9]
0x18004fd33  shl     eax, 18h
0x18004fd36  mov     dword ptr [rsp+1B0h+EventDescriptor.Id], eax
0x18004fd3a  movzx   eax, word ptr [r9+1]
0x18004fd3f  mov     dword ptr [rsp+1B0h+EventDescriptor.Level], eax
0x18004fd43  mov     rax, [r9+3]
0x18004fd47  mov     [rsp+1B0h+EventDescriptor.Keyword], rax
0x18004fd4c  mov     rax, [r10+8]
0x18004fd50  mov     [rsp+1B0h+var_160.Ptr], rax
0x18004fd55  mov     [rbp+0B0h+var_118], ecx
0x18004fd58  lea     rcx, [r9+0Bh]
0x18004fd5c  mov     [rbp+0B0h+var_120], rdx
0x18004fd60  xor     r9d, r9d; RelatedActivityId
0x18004fd63  mov     [rbp+0B0h+var_114], ebx
0x18004fd66  lea     rdx, [rsp+1B0h+EventDescriptor]; EventDescriptor
0x18004fd6b  mov     [rbp+0B0h+var_128], 4
0x18004fd73  mov     [rsp+1B0h+var_138], 8
0x18004fd7c  movzx   eax, word ptr [rax]
0x18004fd7f  mov     [rsp+1B0h+var_160.Size], eax
0x18004fd83  movzx   eax, word ptr [rcx]
0x18004fd86  mov     [rsp+1B0h+var_148], eax
0x18004fd8a  lea     rax, _TraceLoggingMetadataEnd
0x18004fd91  mov     [rsp+1B0h+var_150], rcx
0x18004fd96  lea     rcx, _TraceLoggingMetadata
0x18004fd9d  sub     eax, ecx
0x18004fd9f  mov     dword ptr [rsp+1B0h+var_160.0Ch], 2
0x18004fda7  mov     [rsp+1B0h+var_144], esi
0x18004fdab  mov     [rsp+1B0h+var_180], eax
0x18004fdaf  mov     eax, [rsp+1B0h+var_180]
0x18004fdb3  mov     rcx, [r10+20h]; RegHandle
0x18004fdb7  lea     rax, [rsp+1B0h+var_160]
0x18004fdbc  mov     [rsp+1B0h+UserData], rax; UserData
0x18004fdc1  mov     [rsp+1B0h+UserDataCount], 14h; UserDataCount
0x18004fdc9  call    cs:__imp_EventWriteTransfer
0x18004fdd0  nop     dword ptr [rax+rax+00h]
0x18004fdd5  mov     rcx, [rbp+0B0h+var_20]
0x18004fddc  xor     rcx, rsp; StackCookie
0x18004fddf  call    __security_check_cookie
0x18004fde4  mov     rbx, [rsp+1B0h+arg_8]
0x18004fdec  add     rsp, 1A0h
0x18004fdf3  pop     rdi
0x18004fdf4  pop     rsi
0x18004fdf5  pop     rbp
0x18004fdf6  retn
0x18004fdf8  lea     rdx, dword_1800DB714
0x18004fdff  mov     eax, 2
0x18004fe04  jmp     loc_18004FB87
0x18004fe09  lea     rdx, dword_1800DB714
0x18004fe10  mov     eax, 2
0x18004fe15  jmp     loc_18004FBF4
0x18004fe1a  lea     rdx, dword_1800DB714
0x18004fe21  mov     eax, 2
0x18004fe26  jmp     loc_18004FC9E
0x18004fe2b  mov     r8, rdi
0x18004fe2e  mov     eax, esi
0x18004fe30  jmp     loc_18004FB28
0x18004fe35  mov     rdx, rdi
0x18004fe38  mov     eax, esi
0x18004fe3a  jmp     loc_18004FBB1
0x18004fe3f  mov     rdx, rdi
0x18004fe42  mov     eax, esi
0x18004fe44  jmp     loc_18004FC1E
0x18004fe49  mov     rdx, rdi
0x18004fe4c  mov     eax, esi
0x18004fe4e  jmp     loc_18004FC5B
0x18004fe53  mov     rdx, rdi
0x18004fe56  mov     eax, esi
0x18004fe58  jmp     loc_18004FCDB
0x18004fe5d  mov     rdx, rdi
0x18004fe60  mov     ecx, esi
0x18004fe62  jmp     loc_18004FD15
```
