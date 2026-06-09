# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x180001300`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `760`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180018460`
- `0x18002be10`
- `0x180030230`
- `0x180032500`

## callees

- `0x180001008`
- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800012db`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800012db`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        int **a19)
{
  __int64 v21; // rcx
  int *v23; // r8
  __int64 v24; // rax
  int v25; // eax
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rax
  int v28; // eax
  int *v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  int *v38; // rdx
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // rdx
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // rdx
  int v45; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v49; // [rsp+60h] [rbp-A0h]
  int v50; // [rsp+68h] [rbp-98h]
  int v51; // [rsp+6Ch] [rbp-94h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  __int64 v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v56; // [rsp+90h] [rbp-70h]
  int v57; // [rsp+98h] [rbp-68h]
  int v58; // [rsp+9Ch] [rbp-64h]
  __int64 v59; // [rsp+A0h] [rbp-60h]
  __int64 v60; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v61; // [rsp+B0h] [rbp-50h]
  int v62; // [rsp+B8h] [rbp-48h]
  int v63; // [rsp+BCh] [rbp-44h]
  __int64 v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  int *v66; // [rsp+D0h] [rbp-30h]
  int v67; // [rsp+D8h] [rbp-28h]
  int v68; // [rsp+DCh] [rbp-24h]
  __int64 v69; // [rsp+E0h] [rbp-20h]
  __int64 v70; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v71; // [rsp+F0h] [rbp-10h]
  int v72; // [rsp+F8h] [rbp-8h]
  int v73; // [rsp+FCh] [rbp-4h]
  __int64 v74; // [rsp+100h] [rbp+0h]
  __int64 v75; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v76; // [rsp+110h] [rbp+10h]
  int v77; // [rsp+118h] [rbp+18h]
  int v78; // [rsp+11Ch] [rbp+1Ch]
  int *v79; // [rsp+120h] [rbp+20h]
  int v80; // [rsp+128h] [rbp+28h]
  int v81; // [rsp+12Ch] [rbp+2Ch]
  __int64 v82; // [rsp+130h] [rbp+30h]
  __int64 v83; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v84; // [rsp+140h] [rbp+40h]
  int v85; // [rsp+148h] [rbp+48h]
  int v86; // [rsp+14Ch] [rbp+4Ch]
  int *v87; // [rsp+150h] [rbp+50h]
  int v88; // [rsp+158h] [rbp+58h]
  int v89; // [rsp+15Ch] [rbp+5Ch]

  v21 = -1;
  v23 = *a19;
  if ( *a19 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *((_WORD *)v23 + v24) );
    v25 = 2 * v24 + 2;
  }
  else
  {
    v23 = &dword_18003A074;
    v25 = 2;
  }
  v88 = v25;
  v87 = v23;
  v89 = 0;
  v26 = *a18;
  if ( *a18 )
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
  v85 = v28;
  v82 = a17;
  v84 = v26;
  v86 = 0;
  v83 = 4;
  v29 = *a16;
  if ( *a16 )
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
  v80 = v31;
  v79 = v29;
  v81 = 0;
  v32 = *a15;
  if ( *a15 )
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
  v77 = v34;
  v74 = a14;
  v76 = v32;
  v78 = 0;
  v75 = 4;
  v35 = *a13;
  if ( *a13 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &byte_18003A073;
    v37 = 1;
  }
  v72 = v37;
  v69 = a12;
  v71 = v35;
  v73 = 0;
  v70 = 4;
  v38 = *a11;
  if ( *a11 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_WORD *)v38 + v39) );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = &dword_18003A074;
    v40 = 2;
  }
  v67 = v40;
  v64 = a10;
  v66 = v38;
  v68 = 0;
  v65 = 4;
  v41 = *a9;
  if ( *a9 )
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
  v62 = v43;
  v59 = a8;
  v61 = v41;
  v63 = 0;
  v60 = 4;
  v44 = *a7;
  if ( *a7 )
  {
    do
      ++v21;
    while ( *((_BYTE *)v44 + v21) );
    v45 = v21 + 1;
  }
  else
  {
    v44 = &byte_18003A073;
    v45 = 1;
  }
  v54 = a6;
  v52 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v57 = v45;
  v56 = v44;
  v58 = 0;
  v55 = 4;
  v53 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v50 = *(unsigned __int16 *)(a2 + 11);
  v49 = a2 + 11;
  UserData.Reserved = 2;
  v51 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, 0, 0x11u, &UserData);
}

```

## disassembly

```asm
0x180001008  mov     [rsp-8+arg_8], rbx
0x18000100d  push    rbp
0x18000100e  push    rsi
0x18000100f  push    rdi
0x180001010  lea     rbp, [rsp-70h]
0x180001015  sub     rsp, 170h
0x18000101c  mov     rax, cs:__security_cookie
0x180001023  xor     rax, rsp
0x180001026  mov     [rbp+80h+var_20], rax
0x18000102a  mov     rax, [rbp+80h+arg_90]
0x180001031  mov     r11, r8
0x180001034  mov     r10, rcx
0x180001037  xor     ebx, ebx
0x180001039  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000103d  mov     r9, rdx
0x180001040  mov     r8, [rax]
0x180001043  test    r8, r8
0x180001046  jz      short loc_18000105E
0x180001048  mov     rax, rcx
0x18000104b  inc     rax
0x18000104e  cmp     [r8+rax*2], bx
0x180001053  jnz     short loc_18000104B
0x180001055  lea     eax, ds:2[rax*2]
0x18000105c  jmp     short loc_18000106A
0x18000105e  lea     r8, dword_18003A074
0x180001065  mov     eax, 2
0x18000106a  mov     [rbp+80h+var_28], eax
0x18000106d  mov     edi, 1
0x180001072  mov     rax, [rbp+80h+arg_88]
0x180001079  mov     [rbp+80h+var_30], r8
0x18000107d  lea     r8, byte_18003A073
0x180001084  mov     [rbp+80h+var_24], ebx
0x180001087  mov     rdx, [rax]
0x18000108a  test    rdx, rdx
0x18000108d  jz      short loc_18000109E
0x18000108f  mov     rax, rcx
0x180001092  inc     rax
0x180001095  cmp     [rdx+rax], bl
0x180001098  jnz     short loc_180001092
0x18000109a  inc     eax
0x18000109c  jmp     short loc_1800010A3
0x18000109e  mov     rdx, r8
0x1800010a1  mov     eax, edi
0x1800010a3  mov     [rbp+80h+var_38], eax
0x1800010a6  mov     rax, [rbp+80h+arg_80]
0x1800010ad  mov     [rbp+80h+var_50], rax
0x1800010b1  mov     rax, [rbp+80h+arg_78]
0x1800010b8  mov     [rbp+80h+var_40], rdx
0x1800010bc  mov     [rbp+80h+var_34], ebx
0x1800010bf  mov     [rbp+80h+var_48], 4
0x1800010c7  mov     rdx, [rax]
0x1800010ca  test    rdx, rdx
0x1800010cd  jz      short loc_1800010E4
0x1800010cf  mov     rax, rcx
0x1800010d2  inc     rax
0x1800010d5  cmp     [rdx+rax*2], bx
0x1800010d9  jnz     short loc_1800010D2
0x1800010db  lea     eax, ds:2[rax*2]
0x1800010e2  jmp     short loc_1800010F0
0x1800010e4  lea     rdx, dword_18003A074
0x1800010eb  mov     eax, 2
0x1800010f0  mov     [rbp+80h+var_58], eax
0x1800010f3  mov     rax, [rbp+80h+arg_70]
0x1800010fa  mov     [rbp+80h+var_60], rdx
0x1800010fe  mov     [rbp+80h+var_54], ebx
0x180001101  mov     rdx, [rax]
0x180001104  test    rdx, rdx
0x180001107  jz      short loc_180001118
0x180001109  mov     rax, rcx
0x18000110c  inc     rax
0x18000110f  cmp     [rdx+rax], bl
0x180001112  jnz     short loc_18000110C
0x180001114  inc     eax
0x180001116  jmp     short loc_18000111D
0x180001118  mov     rdx, r8
0x18000111b  mov     eax, edi
0x18000111d  mov     [rbp+80h+var_68], eax
0x180001120  mov     rax, [rbp+80h+arg_68]
0x180001127  mov     [rbp+80h+var_80], rax
0x18000112b  mov     rax, [rbp+80h+arg_60]
0x180001132  mov     [rbp+80h+var_70], rdx
0x180001136  mov     [rbp+80h+var_64], ebx
0x180001139  mov     [rbp+80h+var_78], 4
0x180001141  mov     rdx, [rax]
0x180001144  test    rdx, rdx
0x180001147  jz      short loc_180001158
0x180001149  mov     rax, rcx
0x18000114c  inc     rax
0x18000114f  cmp     [rdx+rax], bl
0x180001152  jnz     short loc_18000114C
0x180001154  inc     eax
0x180001156  jmp     short loc_18000115D
0x180001158  mov     rdx, r8
0x18000115b  mov     eax, edi
0x18000115d  mov     [rbp+80h+var_88], eax
0x180001160  mov     rax, [rbp+80h+arg_58]
0x180001167  mov     [rbp+80h+var_A0], rax
0x18000116b  mov     rax, [rbp+80h+arg_50]
0x180001172  mov     [rbp+80h+var_90], rdx
0x180001176  mov     [rbp+80h+var_84], ebx
0x180001179  mov     [rbp+80h+var_98], 4
0x180001181  mov     rdx, [rax]
0x180001184  test    rdx, rdx
0x180001187  jz      short loc_18000119E
0x180001189  mov     rax, rcx
0x18000118c  inc     rax
0x18000118f  cmp     [rdx+rax*2], bx
0x180001193  jnz     short loc_18000118C
0x180001195  lea     eax, ds:2[rax*2]
0x18000119c  jmp     short loc_1800011AA
0x18000119e  lea     rdx, dword_18003A074
0x1800011a5  mov     eax, 2
0x1800011aa  mov     [rbp+80h+var_A8], eax
0x1800011ad  mov     rax, [rbp+80h+arg_48]
0x1800011b4  mov     [rbp+80h+var_C0], rax
0x1800011b8  mov     rax, [rbp+80h+arg_40]
0x1800011bf  mov     [rbp+80h+var_B0], rdx
0x1800011c3  mov     [rbp+80h+var_A4], ebx
0x1800011c6  mov     [rbp+80h+var_B8], 4
0x1800011ce  mov     rdx, [rax]
0x1800011d1  test    rdx, rdx
0x1800011d4  jz      short loc_1800011E5
0x1800011d6  mov     rax, rcx
0x1800011d9  inc     rax
0x1800011dc  cmp     [rdx+rax], bl
0x1800011df  jnz     short loc_1800011D9
0x1800011e1  inc     eax
0x1800011e3  jmp     short loc_1800011EA
0x1800011e5  mov     rdx, r8
0x1800011e8  mov     eax, edi
0x1800011ea  mov     [rbp+80h+var_C8], eax
0x1800011ed  mov     rax, [rbp+80h+arg_38]
0x1800011f4  mov     [rbp+80h+var_E0], rax
0x1800011f8  mov     rax, [rbp+80h+arg_30]
0x1800011ff  mov     [rbp+80h+var_D0], rdx
0x180001203  mov     [rbp+80h+var_C4], ebx
0x180001206  mov     [rbp+80h+var_D8], 4
0x18000120e  mov     rdx, [rax]
0x180001211  test    rdx, rdx
0x180001214  jz      short loc_180001222
0x180001216  inc     rcx
0x180001219  cmp     [rdx+rcx], bl
0x18000121c  jnz     short loc_180001216
0x18000121e  inc     ecx
0x180001220  jmp     short loc_180001227
0x180001222  mov     rdx, r8
0x180001225  mov     ecx, edi
0x180001227  mov     rax, [rbp+80h+arg_28]
0x18000122e  mov     r8, r11; ActivityId
0x180001231  mov     [rbp+80h+var_100], rax
0x180001235  mov     rax, [rbp+80h+arg_20]
0x18000123c  mov     [rsp+180h+var_110], rax
0x180001241  movzx   eax, byte ptr [r9]
0x180001245  shl     eax, 18h
0x180001248  mov     dword ptr [rsp+180h+EventDescriptor.Id], eax
0x18000124c  movzx   eax, word ptr [r9+1]
0x180001251  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180001255  mov     rax, [r9+3]
0x180001259  mov     [rsp+180h+EventDescriptor.Keyword], rax
0x18000125e  mov     rax, [r10+8]
0x180001262  mov     [rsp+180h+var_130.Ptr], rax
0x180001267  mov     [rbp+80h+var_E8], ecx
0x18000126a  lea     rcx, [r9+0Bh]
0x18000126e  mov     [rbp+80h+var_F0], rdx
0x180001272  xor     r9d, r9d; RelatedActivityId
0x180001275  mov     [rbp+80h+var_E4], ebx
0x180001278  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x18000127d  mov     [rbp+80h+var_F8], 4
0x180001285  mov     [rsp+180h+var_108], 8
0x18000128e  movzx   eax, word ptr [rax]
0x180001291  mov     [rsp+180h+var_130.Size], eax
0x180001295  movzx   eax, word ptr [rcx]
0x180001298  mov     [rsp+180h+var_118], eax
0x18000129c  lea     rax, _TraceLoggingMetadataEnd
0x1800012a3  mov     [rsp+180h+var_120], rcx
0x1800012a8  lea     rcx, _TraceLoggingMetadata
0x1800012af  sub     eax, ecx
0x1800012b1  mov     dword ptr [rsp+180h+var_130.0Ch], 2
0x1800012b9  mov     [rsp+180h+var_114], edi
0x1800012bd  mov     [rsp+180h+var_150], eax
0x1800012c1  mov     eax, [rsp+180h+var_150]
0x1800012c5  mov     rcx, [r10+20h]; RegHandle
0x1800012c9  lea     rax, [rsp+180h+var_130]
0x1800012ce  mov     [rsp+180h+UserData], rax; UserData
0x1800012d3  mov     [rsp+180h+UserDataCount], 11h; UserDataCount
0x1800012db  call    cs:__imp_EventWriteTransfer
0x1800012e1  mov     rcx, [rbp+80h+var_20]
0x1800012e5  xor     rcx, rsp; StackCookie
0x1800012e8  call    __security_check_cookie
0x1800012ed  mov     rbx, [rsp+180h+arg_8]
0x1800012f5  add     rsp, 170h
0x1800012fc  pop     rdi
0x1800012fd  pop     rsi
0x1800012fe  pop     rbp
0x1800012ff  retn
```
