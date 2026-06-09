# CPenProcess::Init(CPenProcessInfo const *,CPenSession *)

- ea: `0x180016620`
- end: `0x18001692b`
- name: `?Init@CPenProcess@@QEAAHPEBVCPenProcessInfo@@PEAVCPenSession@@@Z`
- size: `779`
- prototype: `__int64 __fastcall(CPenProcess *this, const struct CPenProcessInfo *, struct CPenSession *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014d40`

## callees

- `0x180012680`
- `0x180016620`
- `0x18001bbe0`
- `0x18002b3a8`
- `0x18002db5c`
- `0x180031010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800167e4`
- `ntdll!EtwEventWriteTransfer` at `0x1800167e4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016811`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016833`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016811`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016833`

## string_xrefs

- `0x1800168ee`: `PENSERVICE_CPenProcess::Init`

## pseudocode

```c
__int64 __fastcall CPenProcess::Init(CPenProcess *this, const struct CPenProcessInfo *a2, struct CPenSession *a3)
{
  const unsigned __int16 *v5; // rdi
  __int64 v6; // rax
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  _WORD *v10; // rbx
  int v11; // r14d
  __int64 v12; // rcx
  __int64 v13; // rax
  bool v14; // zf
  HANDLE v15; // rax
  HANDLE v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  _WORD *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r9
  _WORD *v22; // rcx
  _WORD *v23; // rax
  _WORD *v24; // rcx
  _DWORD v26[2]; // [rsp+40h] [rbp-69h] BYREF
  _DWORD v27[2]; // [rsp+48h] [rbp-61h] BYREF
  __int64 v28; // [rsp+50h] [rbp-59h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+58h] [rbp-51h] BYREF
  __int16 *v30; // [rsp+70h] [rbp-39h] BYREF
  int v31; // [rsp+78h] [rbp-31h]
  int v32; // [rsp+7Ch] [rbp-2Dh]
  __int16 *v33; // [rsp+80h] [rbp-29h]
  int v34; // [rsp+88h] [rbp-21h]
  int v35; // [rsp+8Ch] [rbp-1Dh]
  _DWORD *v36; // [rsp+90h] [rbp-19h]
  __int64 v37; // [rsp+98h] [rbp-11h]
  _WORD *v38; // [rsp+A0h] [rbp-9h]
  int v39; // [rsp+A8h] [rbp-1h]
  int v40; // [rsp+ACh] [rbp+3h]
  const unsigned __int16 *v41; // [rsp+B0h] [rbp+7h]
  int v42; // [rsp+B8h] [rbp+Fh]
  int v43; // [rsp+BCh] [rbp+13h]

  *(_QWORD *)this = a2;
  if ( !a2 )
    return 0;
  if ( !a3 )
    return 0;
  v5 = CPenProcessInfo::Path(a2);
  if ( !v5 )
    return 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 64LL))(*(_QWORD *)this);
  v10 = (_WORD *)v6;
  if ( !v6 )
    return 0;
  v11 = *((_DWORD *)a3 + 1);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_slSS(*(_QWORD *)&WPP_GLOBAL_Control[1].Data1, v7, v8, v9, v11, v6, (__int64)v5);
  if ( (unsigned int)dword_1800411A8 > 5
    && (qword_1800411B8 & 0x4000000) != 0
    && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
  {
    v12 = -1;
    v26[0] = v11;
    v13 = -1;
    do
      v14 = v5[++v13] == 0;
    while ( !v14 );
    v41 = v5;
    v42 = 2 * v13 + 2;
    v43 = 0;
    do
      v14 = v10[++v12] == 0;
    while ( !v14 );
    v38 = v10;
    v39 = 2 * v12 + 2;
    v40 = 0;
    v36 = v26;
    v27[1] = 5;
    v30 = (__int16 *)off_1800411B0;
    v37 = 4;
    v27[0] = 184549376;
    v28 = 0x4000000;
    v31 = *(unsigned __int16 *)off_1800411B0;
    v33 = &word_18003AB06;
    v32 = 2;
    v34 = 68;
    v35 = 1;
    v26[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_1800411C8, v27, 0, 0, 5, &v30);
  }
  *(_OWORD *)&EventAttributes.nLength = 0;
  *(&EventAttributes.bInheritHandle + 1) = 0;
  EventAttributes.nLength = 24;
  EventAttributes.bInheritHandle = 1;
  v15 = CreateEventW(&EventAttributes, 0, 0, 0);
  *((_QWORD *)this + 139) = v15;
  if ( !v15 )
    return 0;
  v16 = CreateEventW(&EventAttributes, 0, 0, 0);
  *((_QWORD *)this + 140) = v16;
  if ( !v16 )
    return 0;
  v17 = 2147483646;
  *((_DWORD *)this + 8) = v11;
  v18 = 260;
  v19 = (_WORD *)((char *)this + 36);
  v20 = 2147483646;
  v21 = 260;
  do
  {
    if ( !v20 )
      break;
    if ( !*v5 )
      break;
    *v19++ = *v5++;
    --v20;
    --v21;
  }
  while ( v21 );
  v22 = v19 - 1;
  if ( v21 )
    v22 = v19;
  *v22 = 0;
  if ( !v21 )
    return 0;
  v23 = (_WORD *)((char *)this + 558);
  do
  {
    if ( !v17 )
      break;
    if ( !*v10 )
      break;
    *v23++ = *v10++;
    --v17;
    --v18;
  }
  while ( v18 );
  v24 = v23 - 1;
  if ( v18 )
    v24 = v23;
  *v24 = 0;
  if ( !v18 )
    return 0;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      11,
      WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
      "PENSERVICE_CPenProcess::Init");
  return 1;
}

```

## disassembly

```asm
0x180016620  push    rbp
0x180016622  push    rbx
0x180016623  push    rsi
0x180016624  push    rdi
0x180016625  push    r12
0x180016627  push    r14
0x180016629  lea     rbp, [rsp-2Fh]
0x18001662e  sub     rsp, 0D8h
0x180016635  mov     rax, cs:__security_cookie
0x18001663c  xor     rax, rsp
0x18001663f  mov     [rbp+57h+var_40], rax
0x180016643  mov     [rcx], rdx
0x180016646  mov     r14, r8
0x180016649  mov     rsi, rcx
0x18001664c  test    rdx, rdx
0x18001664f  jz      loc_18001690D
0x180016655  test    r8, r8
0x180016658  jz      loc_18001690D
0x18001665e  mov     rcx, rdx; this
0x180016661  call    ?Path@CPenProcessInfo@@QEBAPEBGXZ; CPenProcessInfo::Path(void)
0x180016666  mov     rdi, rax
0x180016669  test    rax, rax
0x18001666c  jz      loc_18001690D
0x180016672  mov     rcx, [rsi]
0x180016675  mov     rax, [rcx]
0x180016678  mov     rax, [rax+40h]
0x18001667c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016681  mov     rbx, rax
0x180016684  test    rax, rax
0x180016687  jz      loc_18001690D
0x18001668d  mov     r14d, [r14+4]
0x180016691  mov     rcx, cs:WPP_GLOBAL_Control
0x180016698  lea     r12, WPP_GLOBAL_Control
0x18001669f  cmp     rcx, r12
0x1800166a2  jz      short loc_1800166C2
0x1800166a4  test    byte ptr [rcx+1Ch], 10h
0x1800166a8  jz      short loc_1800166C2
0x1800166aa  mov     rcx, [rcx+10h]
0x1800166ae  mov     [rsp+100h+var_D0], rdi
0x1800166b3  mov     [rsp+100h+var_D8], rax
0x1800166b8  mov     [rsp+100h+var_E0], r14d
0x1800166bd  call    WPP_SF_slSS
0x1800166c2  mov     eax, cs:dword_1800411A8
0x1800166c8  cmp     eax, 5
0x1800166cb  jbe     loc_1800167EA
0x1800166d1  mov     rcx, cs:qword_1800411C0
0x1800166d8  mov     rax, cs:qword_1800411B8
0x1800166df  bt      rax, 1Ah
0x1800166e4  jnb     loc_1800167EA
0x1800166ea  mov     rax, rcx
0x1800166ed  and     eax, 4000000h
0x1800166f2  cmp     rax, rcx
0x1800166f5  jnz     loc_1800167EA
0x1800166fb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016702  mov     [rbp+57h+var_C0], r14d
0x180016706  mov     rax, rcx
0x180016709  nop     dword ptr [rax+00000000h]
0x180016710  cmp     word ptr [rdi+rax*2+2], 0
0x180016716  lea     rax, [rax+1]
0x18001671a  jnz     short loc_180016710
0x18001671c  lea     eax, ds:2[rax*2]
0x180016723  mov     [rbp+57h+var_50], rdi
0x180016727  mov     [rbp+57h+var_48], eax
0x18001672a  mov     [rbp+57h+var_44], 0
0x180016731  cmp     word ptr [rbx+rcx*2+2], 0
0x180016737  lea     rcx, [rcx+1]
0x18001673b  jnz     short loc_180016731
0x18001673d  lea     eax, ds:2[rcx*2]
0x180016744  mov     [rbp+57h+var_60], rbx
0x180016748  mov     [rbp+57h+var_58], eax
0x18001674b  lea     rcx, _TraceLoggingMetadata
0x180016752  lea     rax, [rbp+57h+var_C0]
0x180016756  mov     [rbp+57h+var_54], 0
0x18001675d  mov     [rbp+57h+var_70], rax
0x180016761  lea     rdx, [rbp+57h+var_B8]
0x180016765  movzx   eax, cs:word_18003AAFC
0x18001676c  xor     r9d, r9d
0x18001676f  mov     [rbp+57h+var_B4], eax
0x180016772  xor     r8d, r8d
0x180016775  mov     rax, cs:off_1800411B0
0x18001677c  mov     [rbp+57h+var_90], rax
0x180016780  mov     [rbp+57h+var_68], 4
0x180016788  mov     [rbp+57h+var_B8], 0B000000h
0x18001678f  mov     [rbp+57h+var_B0], 4000000h
0x180016797  movzx   eax, word ptr [rax]
0x18001679a  mov     [rbp+57h+var_88], eax
0x18001679d  lea     rax, word_18003AB06
0x1800167a4  mov     [rbp+57h+var_80], rax
0x1800167a8  lea     rax, _TraceLoggingMetadataEnd
0x1800167af  sub     eax, ecx
0x1800167b1  mov     [rbp+57h+var_84], 2
0x1800167b8  mov     [rbp+57h+var_78], 44h ; 'D'
0x1800167bf  mov     [rbp+57h+var_74], 1
0x1800167c6  mov     [rbp+57h+var_BC], eax
0x1800167c9  mov     eax, [rbp+57h+var_BC]
0x1800167cc  mov     rcx, cs:qword_1800411C8
0x1800167d3  lea     rax, [rbp+57h+var_90]
0x1800167d7  mov     [rsp+100h+var_D8], rax
0x1800167dc  mov     [rsp+100h+var_E0], 5
0x1800167e4  call    cs:__imp_EtwEventWriteTransfer
0x1800167ea  xorps   xmm0, xmm0
0x1800167ed  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x1800167f1  xor     eax, eax
0x1800167f3  xor     r9d, r9d; lpName
0x1800167f6  movups  xmmword ptr [rbp+57h+EventAttributes.nLength], xmm0
0x1800167fa  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], rax
0x1800167fe  xor     r8d, r8d; bInitialState
0x180016801  xor     edx, edx; bManualReset
0x180016803  mov     [rbp+57h+EventAttributes.nLength], 18h
0x18001680a  mov     [rbp+57h+EventAttributes.bInheritHandle], 1
0x180016811  call    cs:__imp_CreateEventW
0x180016817  mov     [rsi+458h], rax
0x18001681e  test    rax, rax
0x180016821  jz      loc_18001690D
0x180016827  xor     r9d, r9d; lpName
0x18001682a  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x18001682e  xor     r8d, r8d; bInitialState
0x180016831  xor     edx, edx; bManualReset
0x180016833  call    cs:__imp_CreateEventW
0x180016839  mov     [rsi+460h], rax
0x180016840  test    rax, rax
0x180016843  jz      loc_18001690D
0x180016849  mov     r8d, 7FFFFFFEh
0x18001684f  mov     [rsi+20h], r14d
0x180016853  mov     edx, 104h
0x180016858  lea     rax, [rsi+24h]
0x18001685c  mov     ecx, r8d
0x18001685f  mov     r9d, edx
0x180016862  test    rcx, rcx
0x180016865  jz      short loc_180016886
0x180016867  movzx   r10d, word ptr [rdi]
0x18001686b  test    r10w, r10w
0x18001686f  jz      short loc_180016886
0x180016871  mov     [rax], r10w
0x180016875  add     rdi, 2
0x180016879  add     rax, 2
0x18001687d  dec     rcx
0x180016880  sub     r9, 1
0x180016884  jnz     short loc_180016862
0x180016886  test    r9, r9
0x180016889  lea     rcx, [rax-2]
0x18001688d  cmovnz  rcx, rax
0x180016891  xor     eax, eax
0x180016893  mov     [rcx], ax
0x180016896  test    r9, r9
0x180016899  jz      short loc_18001690D
0x18001689b  lea     rax, [rsi+22Eh]
0x1800168a2  test    r8, r8
0x1800168a5  jz      short loc_1800168C3
0x1800168a7  movzx   ecx, word ptr [rbx]
0x1800168aa  test    cx, cx
0x1800168ad  jz      short loc_1800168C3
0x1800168af  mov     [rax], cx
0x1800168b2  add     rbx, 2
0x1800168b6  add     rax, 2
0x1800168ba  dec     r8
0x1800168bd  sub     rdx, 1
0x1800168c1  jnz     short loc_1800168A2
0x1800168c3  test    rdx, rdx
0x1800168c6  lea     rcx, [rax-2]
0x1800168ca  cmovnz  rcx, rax
0x1800168ce  xor     eax, eax
0x1800168d0  mov     [rcx], ax
0x1800168d3  test    rdx, rdx
0x1800168d6  jz      short loc_18001690D
0x1800168d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168df  cmp     rcx, r12
0x1800168e2  jz      short loc_180016906
0x1800168e4  test    byte ptr [rcx+1Ch], 10h
0x1800168e8  jz      short loc_180016906
0x1800168ea  mov     rcx, [rcx+10h]
0x1800168ee  lea     r9, aPenserviceCpen_1; "PENSERVICE_CPenProcess::Init"
0x1800168f5  mov     edx, 0Bh
0x1800168fa  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x180016901  call    WPP_SF_s
0x180016906  mov     eax, 1
0x18001690b  jmp     short loc_18001690F
0x18001690d  xor     eax, eax
0x18001690f  mov     rcx, [rbp+57h+var_40]
0x180016913  xor     rcx, rsp; StackCookie
0x180016916  call    __security_check_cookie
0x18001691b  add     rsp, 0D8h
0x180016922  pop     r14
0x180016924  pop     r12
0x180016926  pop     rdi
0x180016927  pop     rsi
0x180016928  pop     rbx
0x180016929  pop     rbp
0x18001692a  retn
```
