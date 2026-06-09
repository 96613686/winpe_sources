# FwppInjectTransportSendAsync

- ea: `0x180001600`
- end: `0x180001cc3`
- name: `FwppInjectTransportSendAsync`
- size: `1731`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180001510`
- `0x180001580`
- `0x180003048`

## callees

- `0x180001600`
- `0x180002dd8`
- `0x180003048`
- `0x1800032f0`
- `0x1800082a4`
- `0x18000de60`
- `0x180020400`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x180001644`
- `ntoskrnl!KfRaiseIrql` at `0x180001644`
- `ntoskrnl!KeLowerIrql` at `0x180001c99`
- `ntoskrnl!KeLowerIrql` at `0x180001c99`
- `ntoskrnl!KeIsExecutingDpc` at `0x18000170c`
- `ntoskrnl!KeIsExecutingDpc` at `0x18000170c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000178f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000178f`
- `NETIO!NetioDereferenceNetBufferList` at `0x180001996`
- `NETIO!NetioDereferenceNetBufferList` at `0x180001996`

## string_xrefs

- `0x1800017d4`: `ExAllocateFromNPagedLookasideList`
- `0x18000180c`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall FwppInjectTransportSendAsync(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        UINT AlignOffset,
        __int64 a6,
        unsigned __int16 a7,
        BOOL a8,
        ULONG_PTR a9,
        __int64 a10,
        __int64 a11)
{
  __int64 (__fastcall **v11)(__int64, __int64 *); // rbx
  int v14; // edi
  int v15; // r9d
  __int64 v16; // rax
  PDEVICE_OBJECT v17; // rcx
  bool v18; // zf
  unsigned int v19; // edi
  BOOL v20; // r12d
  int v21; // eax
  __int64 v22; // rax
  __int64 *v23; // rax
  __int64 v24; // r8
  __int64 *v25; // rbx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 **v28; // rax
  __int64 v29; // rdx
  int v30; // r13d
  __int64 v31; // r15
  int v32; // r14d
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  unsigned __int8 v36; // al
  int v37; // r9d
  __int64 v38; // r11
  __int64 v39; // r8
  int v40; // eax
  bool v41; // al
  ULONG_PTR BugCheckParameter3; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+28h] [rbp-D8h]
  char v45; // [rsp+80h] [rbp-80h]
  KIRQL v46; // [rsp+81h] [rbp-7Fh]
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h]
  _DWORD v49[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v50; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-58h]
  __int64 v52; // [rsp+B0h] [rbp-50h] BYREF
  __int64 (__fastcall **v53)(__int64, __int64 *); // [rsp+B8h] [rbp-48h]
  __int128 v54; // [rsp+C0h] [rbp-40h]
  __int128 v55; // [rsp+D0h] [rbp-30h]
  __int128 v56; // [rsp+E0h] [rbp-20h]
  __int128 v57; // [rsp+F0h] [rbp-10h]
  __int128 v58; // [rsp+100h] [rbp+0h]
  __int128 v59; // [rsp+110h] [rbp+10h]
  __int64 v60; // [rsp+120h] [rbp+20h]
  ULONG_PTR v61; // [rsp+128h] [rbp+28h]
  UINT AlignOffseta; // [rsp+190h] [rbp+90h]

  v11 = (__int64 (__fastcall **)(__int64, __int64 *))qword_180048208;
  v47 = 0;
  v50 = 0;
  v49[0] = 0;
  v14 = a2;
  v46 = KfRaiseIrql(2u);
  LODWORD(v16) = HIDWORD(KeGetPcr()[1].LockArray);
  v49[1] = v16;
  v48 = 24 * v16;
  v45 = *(_BYTE *)(24 * v16 + gPerProcessorContext);
  if ( AlignOffset )
  {
    v17 = WPP_GLOBAL_Control;
    v18 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_3:
    v19 = -1071513547;
    if ( !v18 && BYTE1(v17->Timer) >= 2u && (HIDWORD(v17->Timer) & 0x1000) != 0 )
      WPP_SF_sd((__int64)v17->AttachedDevice, 0xAu, 3 * v16, "FwppInjectTransportSendAsync", -1071513547);
    goto LABEL_68;
  }
  if ( a7 != 2 && a7 != 23 )
  {
    v17 = WPP_GLOBAL_Control;
    v18 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    goto LABEL_3;
  }
  v20 = a8;
  if ( !a8 )
    v20 = KeIsExecutingDpc() != 0;
  v21 = 0;
  LOBYTE(v15) = 1;
  if ( a7 != 2 )
    v21 = 41;
  AlignOffseta = v21;
  v22 = FwppInjectPrologue(v14, a3, 2, v15, a9, a10, a11, 0, 0);
  v19 = v22;
  if ( (_DWORD)v22 != 259 )
  {
    if ( v22 )
    {
LABEL_68:
      v26 = v48;
      goto LABEL_69;
    }
    v30 = v11[24](a4, &v47);
    if ( v30 < 0 )
      goto LABEL_39;
    v31 = v47;
    v51 = v11[26](v47, (__int64 *)v49);
    if ( !v51 )
    {
      ((void (__fastcall *)(__int64))v11[25])(v47);
LABEL_39:
      *(_DWORD *)(a9 + 140) = v30;
LABEL_40:
      LOBYTE(v29) = 1;
      NetioDereferenceNetBufferList(a9, v29);
LABEL_67:
      FwppInjectEpilogue();
      goto LABEL_68;
    }
    v32 = ((__int64 (__fastcall *)(_QWORD, __int64, unsigned __int64 *))v11[14])(a7, v47, &v50);
    if ( v32 < 0 )
    {
      v11[27](v51, (__int64 *)v49[0]);
      ((void (__fastcall *)(__int64))v11[25])(v47);
      *(_DWORD *)(a9 + 140) = v32;
      goto LABEL_40;
    }
    if ( a6 )
    {
      v35 = *(_DWORD *)(v31 + 48) >> 4;
      LOBYTE(v35) = (*(_DWORD *)(v31 + 48) & 0x10) != 0;
      v36 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))v11[2])(AlignOffseta, *(unsigned int *)(v31 + 40), v35);
      v34 = *(unsigned int *)(v31 + 52);
      if ( (v34 & 0x4000) != 0 )
        v36 &= ~4u;
      if ( v45 )
      {
        if ( a1 )
        {
          v37 = *(_DWORD *)(a6 + 40);
          v38 = *(_QWORD *)(a6 + 32);
        }
        else
        {
          v37 = 0;
          v38 = 0;
        }
        if ( (*(_DWORD *)(v31 + 52) & 0x10) != 0 )
          v39 = *(_QWORD *)(v31 + 472);
        else
          v39 = 0;
        ((void (__fastcall *)(_QWORD, _QWORD, ULONG_PTR, _QWORD, _DWORD, unsigned __int64, __int64, _QWORD, _DWORD, _DWORD, __int64, BOOL, bool, __int64, int))v11[3])(
          AlignOffseta,
          v36,
          a9,
          *(_QWORD *)(a6 + 16),
          *(_DWORD *)(a6 + 24),
          v50,
          v39,
          *(_QWORD *)a6,
          *(_DWORD *)(a6 + 8),
          *(_DWORD *)(v31 + 40),
          v47,
          v20,
          (*(_DWORD *)(v31 + 48) & 0x10) != 0,
          v38,
          v37);
        goto LABEL_66;
      }
      v54 = 0;
      BYTE12(v54) = v36;
      v58 = *(unsigned __int64 *)(a6 + 16);
      DWORD2(v58) = *(_DWORD *)(a6 + 24);
      v52 = 0;
      v53 = v11;
      v56 = v50;
      v40 = *(_DWORD *)(v31 + 52);
      LODWORD(v52) = 4;
      DWORD2(v54) = AlignOffseta;
      v60 = 0;
      v61 = a9;
      v55 = 0;
      v57 = 0;
      v59 = 0;
      if ( (v40 & 0x10) != 0 )
        *((_QWORD *)&v56 + 1) = *(_QWORD *)(v31 + 472);
      else
        *((_QWORD *)&v56 + 1) = 0;
      *(_QWORD *)&v57 = *(_QWORD *)a6;
      DWORD2(v57) = *(_DWORD *)(a6 + 8);
      LODWORD(v60) = *(_DWORD *)(v31 + 40);
      *(_QWORD *)&v54 = v47;
      v41 = (*(_DWORD *)(v31 + 48) & 0x10) != 0;
      LODWORD(v55) = v20;
      BYTE4(v60) = v41;
      if ( a1 )
      {
        *(_QWORD *)&v59 = *(_QWORD *)(a6 + 32);
        DWORD2(v59) = *(_DWORD *)(a6 + 40);
      }
      else
      {
        *(_QWORD *)&v59 = 0;
        DWORD2(v59) = 0;
      }
    }
    else
    {
      if ( !(unsigned __int8)FwppValidatePacketForRawSend(AlignOffseta) )
      {
        v11[27](v51, (__int64 *)v49[0]);
        ((void (__fastcall *)(__int64))v11[25])(v47);
        *(_DWORD *)(a9 + 140) = -1073741811;
        goto LABEL_40;
      }
      if ( v45 )
      {
        LOBYTE(v44) = 0;
        ((void (__fastcall *)(_QWORD, BOOL, __int64, unsigned __int64, ULONG_PTR, int))v11[7])(
          AlignOffseta,
          v20,
          v47,
          v50,
          a9,
          v44);
LABEL_66:
        v11[27](v51, (__int64 *)v49[0]);
        ((void (__fastcall *)(__int64))v11[25])(v47);
        goto LABEL_67;
      }
      *(_QWORD *)&v54 = v47;
      v52 = 1;
      v55 = 0;
      v53 = v11;
      v56 = v50;
      v60 = 0;
      *((_QWORD *)&v54 + 1) = AlignOffseta;
      v57 = 0;
      LODWORD(v55) = v20;
      v58 = 0;
      v61 = a9;
      v59 = 0;
    }
    NetioExpandKernelStackAndCallout(v34, v33, &v52);
    goto LABEL_66;
  }
  v23 = (__int64 *)ExAllocateFromNPagedLookasideList(&Lookaside);
  v25 = v23;
  if ( !v23 )
  {
    v19 = -1073741801;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      LODWORD(BugCheckParameter3) = -1073741801;
      WPP_SF_sd(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xAu,
        v24,
        "ExAllocateFromNPagedLookasideList",
        BugCheckParameter3);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        LODWORD(BugCheckParameter3) = -1073741801;
        WPP_SF_sd(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0xFu,
          v24,
          "WfpAllocFromNPagedLookasideList",
          BugCheckParameter3);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        LODWORD(BugCheckParameter3) = -1073741801;
        WPP_SF_sd(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0xFu,
          v24,
          "FwppAllocateDelayedInjectionContext",
          BugCheckParameter3);
      }
    }
    goto LABEL_68;
  }
  memset(v23, 0, 0xA0u);
  v25[3] = a2;
  *((_DWORD *)v25 + 5) = 4;
  *((_BYTE *)v25 + 16) = 1;
  v25[4] = a3;
  v25[11] = a4;
  *((_DWORD *)v25 + 10) = 0;
  if ( a6 )
  {
    *((_OWORD *)v25 + 6) = 0;
    *((_OWORD *)v25 + 7) = 0;
    *((_OWORD *)v25 + 8) = 0;
    *((_OWORD *)v25 + 6) = *(_OWORD *)a6;
    *((_OWORD *)v25 + 7) = *(_OWORD *)(a6 + 16);
    if ( a1 )
      *((_OWORD *)v25 + 8) = *(_OWORD *)(a6 + 32);
    *((_BYTE *)v25 + 144) = 1;
  }
  v26 = v48;
  v25[8] = a10;
  v25[9] = a11;
  *((_WORD *)v25 + 22) = a7;
  *((_DWORD *)v25 + 12) = v20;
  v25[7] = a9;
  v27 = v26 + gPerProcessorContext + 8;
  v28 = *(__int64 ***)(v27 + 8);
  if ( *v28 != (__int64 *)v27 )
    __fastfail(3u);
  *v25 = v27;
  v19 = 0;
  v25[1] = (__int64)v28;
  *v28 = v25;
  *(_QWORD *)(v27 + 8) = v25;
LABEL_69:
  *(_BYTE *)(v26 + gPerProcessorContext) = v45;
  KeLowerIrql(v46);
  return v19;
}

```

## disassembly

```asm
0x180001600  mov     [rsp-8+arg_10], rbx
0x180001605  mov     [rsp-8+arg_8], rdx
0x18000160a  mov     [rsp-8+arg_0], ecx
0x18000160e  push    rbp
0x18000160f  push    rsi
0x180001610  push    rdi
0x180001611  push    r12
0x180001613  push    r13
0x180001615  push    r14
0x180001617  push    r15
0x180001619  lea     rbp, [rsp-30h]
0x18000161e  sub     rsp, 130h
0x180001625  mov     rbx, cs:qword_180048208
0x18000162c  xor     esi, esi
0x18000162e  mov     cl, 2; NewIrql
0x180001630  mov     [rbp+60h+var_D8], rsi
0x180001634  mov     [rbp+60h+var_C0], rsi
0x180001638  mov     r15, r9
0x18000163b  mov     [rbp+60h+var_C8], esi
0x18000163e  mov     r13, r8
0x180001641  mov     rdi, rdx
0x180001644  call    cs:__imp_KfRaiseIrql
0x18000164b  nop     dword ptr [rax+rax+00h]
0x180001650  mov     [rbp+60h+var_DF], al
0x180001653  mov     eax, gs:1A4h
0x18000165b  mov     rcx, cs:gPerProcessorContext
0x180001662  mov     [rbp+60h+var_C4], eax
0x180001665  lea     r8, [rax+rax*2]
0x180001669  lea     rax, ds:0[r8*8]
0x180001671  mov     [rbp+60h+var_D0], rax
0x180001675  movzx   eax, byte ptr [rax+rcx]
0x180001679  mov     [rbp+60h+var_E0], al
0x18000167c  cmp     [rbp+60h+AlignOffset], esi
0x180001682  jz      short loc_1800016D7
0x180001684  mov     rcx, cs:WPP_GLOBAL_Control
0x18000168b  lea     rbx, WPP_GLOBAL_Control
0x180001692  cmp     rcx, rbx
0x180001695  mov     rdi, 0FFFFFFFFC0220035h
0x18000169c  jz      loc_180001C83
0x1800016a2  cmp     byte ptr [rcx+29h], 2
0x1800016a6  jb      loc_180001C83
0x1800016ac  test    dword ptr [rcx+2Ch], 1000h
0x1800016b3  jz      loc_180001C83
0x1800016b9  mov     rcx, [rcx+18h]
0x1800016bd  lea     r9, aFwppinjecttran; "FwppInjectTransportSendAsync"
0x1800016c4  mov     edx, 0Ah
0x1800016c9  mov     dword ptr [rsp+160h+BugCheckParameter3], edi
0x1800016cd  call    WPP_SF_sd
0x1800016d2  jmp     loc_180001C83
0x1800016d7  movzx   r14d, [rbp+60h+arg_30]
0x1800016df  cmp     r14w, 2
0x1800016e4  jz      short loc_180001700
0x1800016e6  cmp     r14w, 17h
0x1800016eb  jz      short loc_180001700
0x1800016ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016f4  lea     rbx, WPP_GLOBAL_Control
0x1800016fb  cmp     rcx, rbx
0x1800016fe  jmp     short loc_180001695
0x180001700  mov     r12d, [rbp+60h+arg_38]
0x180001707  test    r12d, r12d
0x18000170a  jnz     short loc_180001723
0x18000170c  call    cs:__imp_KeIsExecutingDpc
0x180001713  nop     dword ptr [rax+rax+00h]
0x180001718  test    eax, eax
0x18000171a  mov     eax, 1
0x18000171f  cmovnz  r12d, eax
0x180001723  mov     [rsp+160h+var_120], rsi; __int64
0x180001728  mov     eax, esi
0x18000172a  mov     [rsp+160h+var_128], rsi; __int64
0x18000172f  mov     ecx, 29h ; ')'
0x180001734  mov     rsi, [rbp+60h+arg_40]
0x18000173b  cmp     r14w, 2
0x180001740  mov     r9b, 1; int
0x180001743  mov     r8d, 2; int
0x180001749  cmovnz  eax, ecx
0x18000174c  mov     rdx, r13; int
0x18000174f  mov     [rbp+60h+AlignOffset], eax
0x180001755  mov     rcx, rdi; int
0x180001758  mov     rax, [rbp+60h+arg_50]
0x18000175f  mov     [rsp+160h+var_130], rax; __int64
0x180001764  mov     rax, [rbp+60h+arg_48]
0x18000176b  mov     [rsp+160h+var_138], rax; __int64
0x180001770  mov     [rsp+160h+BugCheckParameter3], rsi; BugCheckParameter3
0x180001775  call    FwppInjectPrologue
0x18000177a  mov     rdi, rax
0x18000177d  cmp     eax, 103h
0x180001782  jnz     loc_180001937
0x180001788  lea     rcx, Lookaside; Lookaside
0x18000178f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180001796  nop     dword ptr [rax+rax+00h]
0x18000179b  mov     rbx, rax
0x18000179e  test    rax, rax
0x1800017a1  jnz     loc_180001866
0x1800017a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017ae  lea     rbx, WPP_GLOBAL_Control
0x1800017b5  mov     rdi, 0FFFFFFFFC0000017h
0x1800017bc  cmp     rcx, rbx
0x1800017bf  jz      short loc_1800017E9
0x1800017c1  cmp     byte ptr [rcx+29h], 2
0x1800017c5  jb      short loc_1800017E9
0x1800017c7  test    dword ptr [rcx+2Ch], 1000h
0x1800017ce  jz      short loc_1800017E9
0x1800017d0  mov     rcx, [rcx+18h]
0x1800017d4  lea     r9, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x1800017db  mov     edx, 0Ah
0x1800017e0  mov     dword ptr [rsp+160h+BugCheckParameter3], edi
0x1800017e4  call    WPP_SF_sd
0x1800017e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017f0  cmp     rcx, rbx
0x1800017f3  jz      loc_180001C83
0x1800017f9  cmp     byte ptr [rcx+29h], 2
0x1800017fd  jb      short loc_180001821
0x1800017ff  test    dword ptr [rcx+2Ch], 1000h
0x180001806  jz      short loc_180001821
0x180001808  mov     rcx, [rcx+18h]
0x18000180c  lea     r9, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x180001813  mov     edx, 0Fh
0x180001818  mov     dword ptr [rsp+160h+BugCheckParameter3], edi
0x18000181c  call    WPP_SF_sd
0x180001821  mov     rcx, cs:WPP_GLOBAL_Control
0x180001828  cmp     rcx, rbx
0x18000182b  jz      loc_180001C83
0x180001831  cmp     byte ptr [rcx+29h], 2
0x180001835  jb      loc_180001C83
0x18000183b  test    dword ptr [rcx+2Ch], 1000h
0x180001842  jz      loc_180001C83
0x180001848  mov     rcx, [rcx+18h]
0x18000184c  lea     r9, aFwppallocatede_0; "FwppAllocateDelayedInjectionContext"
0x180001853  mov     edx, 0Fh
0x180001858  mov     dword ptr [rsp+160h+BugCheckParameter3], edi
0x18000185c  call    WPP_SF_sd
0x180001861  jmp     loc_180001C83
0x180001866  xor     edx, edx; Val
0x180001868  mov     r8d, 0A0h; Size
0x18000186e  mov     rcx, rbx; void *
0x180001871  call    memset
0x180001876  mov     rax, [rbp+60h+arg_8]
0x18000187a  mov     [rbx+18h], rax
0x18000187e  mov     rax, [rbp+60h+arg_28]
0x180001885  mov     dword ptr [rbx+14h], 4
0x18000188c  mov     byte ptr [rbx+10h], 1
0x180001890  mov     [rbx+20h], r13
0x180001894  mov     [rbx+58h], r15
0x180001898  mov     dword ptr [rbx+28h], 0
0x18000189f  test    rax, rax
0x1800018a2  jz      short loc_1800018DD
0x1800018a4  cmp     [rbp+60h+arg_0], 0
0x1800018a8  xorps   xmm0, xmm0
0x1800018ab  movups  xmmword ptr [rbx+60h], xmm0
0x1800018af  movups  xmmword ptr [rbx+70h], xmm0
0x1800018b3  movups  xmmword ptr [rbx+80h], xmm0
0x1800018ba  movups  xmm0, xmmword ptr [rax]
0x1800018bd  movups  xmmword ptr [rbx+60h], xmm0
0x1800018c1  movups  xmm1, xmmword ptr [rax+10h]
0x1800018c5  movups  xmmword ptr [rbx+70h], xmm1
0x1800018c9  jz      short loc_1800018D6
0x1800018cb  movups  xmm0, xmmword ptr [rax+20h]
0x1800018cf  movups  xmmword ptr [rbx+80h], xmm0
0x1800018d6  mov     byte ptr [rbx+90h], 1
0x1800018dd  mov     rax, [rbp+60h+arg_48]
0x1800018e4  mov     rdx, [rbp+60h+var_D0]
0x1800018e8  mov     [rbx+40h], rax
0x1800018ec  mov     rax, [rbp+60h+arg_50]
0x1800018f3  mov     [rbx+48h], rax
0x1800018f7  mov     [rbx+2Ch], r14w
0x1800018fc  mov     [rbx+30h], r12d
0x180001900  mov     [rbx+38h], rsi
0x180001904  mov     rcx, cs:gPerProcessorContext
0x18000190b  add     rcx, 8
0x18000190f  add     rcx, rdx
0x180001912  mov     rax, [rcx+8]
0x180001916  cmp     [rax], rcx
0x180001919  jz      short loc_180001922
0x18000191b  mov     ecx, 3
0x180001920  int     29h; Win8: RtlFailFast(ecx)
0x180001922  mov     [rbx], rcx
0x180001925  xor     edi, edi
0x180001927  mov     [rbx+8], rax
0x18000192b  mov     [rax], rbx
0x18000192e  mov     [rcx+8], rbx
0x180001932  jmp     loc_180001C87
0x180001937  test    rax, rax
0x18000193a  jnz     loc_180001C83
0x180001940  mov     rax, [rbx+0C0h]
0x180001947  lea     rdx, [rbp+60h+var_D8]
0x18000194b  mov     rcx, r15
0x18000194e  call    _guard_dispatch_icall
0x180001953  mov     r13d, eax
0x180001956  test    eax, eax
0x180001958  js      short loc_18000198A
0x18000195a  mov     r15, [rbp+60h+var_D8]
0x18000195e  lea     rdx, [rbp+60h+var_C8]
0x180001962  mov     rax, [rbx+0D0h]
0x180001969  mov     rcx, r15
0x18000196c  call    _guard_dispatch_icall
0x180001971  mov     [rbp+60h+var_B8], rax
0x180001975  test    rax, rax
0x180001978  jnz     short loc_1800019A7
0x18000197a  mov     rax, [rbx+0C8h]
0x180001981  mov     rcx, [rbp+60h+var_D8]
0x180001985  call    _guard_dispatch_icall
0x18000198a  mov     [rsi+8Ch], r13d
0x180001991  mov     dl, 1
0x180001993  mov     rcx, rsi
0x180001996  call    cs:__imp_NetioDereferenceNetBufferList
0x18000199d  nop     dword ptr [rax+rax+00h]
0x1800019a2  jmp     loc_180001C7E
0x1800019a7  mov     rax, [rbx+70h]
0x1800019ab  lea     r8, [rbp+60h+var_C0]
0x1800019af  mov     rdx, [rbp+60h+var_D8]
0x1800019b3  movzx   ecx, r14w
0x1800019b7  call    _guard_dispatch_icall
0x1800019bc  mov     r14d, eax
0x1800019bf  test    eax, eax
0x1800019c1  jns     short loc_1800019EF
0x1800019c3  mov     rax, [rbx+0D8h]
0x1800019ca  mov     edx, [rbp+60h+var_C8]
0x1800019cd  mov     rcx, [rbp+60h+var_B8]
0x1800019d1  call    _guard_dispatch_icall
0x1800019d6  mov     rax, [rbx+0C8h]
0x1800019dd  mov     rcx, [rbp+60h+var_D8]
0x1800019e1  call    _guard_dispatch_icall
0x1800019e6  mov     [rsi+8Ch], r14d
0x1800019ed  jmp     short loc_180001991
0x1800019ef  mov     r14, [rbp+60h+arg_28]
0x1800019f6  mov     r13d, [rbp+60h+AlignOffset]
0x1800019fd  mov     ecx, r13d; AlignOffset
0x180001a00  test    r14, r14
0x180001a03  jnz     loc_180001AC2
0x180001a09  mov     rdx, rsi
0x180001a0c  call    FwppValidatePacketForRawSend
0x180001a11  test    al, al
0x180001a13  jnz     short loc_180001A47
0x180001a15  mov     rax, [rbx+0D8h]
0x180001a1c  mov     edx, [rbp+60h+var_C8]
0x180001a1f  mov     rcx, [rbp+60h+var_B8]
0x180001a23  call    _guard_dispatch_icall
0x180001a28  mov     rax, [rbx+0C8h]
0x180001a2f  mov     rcx, [rbp+60h+var_D8]
0x180001a33  call    _guard_dispatch_icall
0x180001a38  mov     dword ptr [rsi+8Ch], 0C000000Dh
0x180001a42  jmp     loc_180001991
0x180001a47  cmp     [rbp+60h+var_E0], 0
0x180001a4b  jz      short loc_180001A73
0x180001a4d  mov     rax, [rbx+38h]
0x180001a51  mov     edx, r12d
0x180001a54  mov     r9, [rbp+60h+var_C0]
0x180001a58  mov     ecx, r13d
0x180001a5b  mov     r8, [rbp+60h+var_D8]
0x180001a5f  mov     byte ptr [rsp+160h+var_138], 0
0x180001a64  mov     [rsp+160h+BugCheckParameter3], rsi
0x180001a69  call    _guard_dispatch_icall
0x180001a6e  jmp     loc_180001C5B
0x180001a73  mov     rax, [rbp+60h+var_D8]
0x180001a77  xorps   xmm0, xmm0
0x180001a7a  movups  [rbp+60h+var_A0], xmm0
0x180001a7e  mov     qword ptr [rbp+60h+var_A0], rax
0x180001a82  mov     rax, [rbp+60h+var_C0]
0x180001a86  movups  [rbp+60h+var_B0], xmm0
0x180001a8a  mov     dword ptr [rbp+60h+var_B0], 1
0x180001a91  movups  [rbp+60h+var_90], xmm0
0x180001a95  mov     qword ptr [rbp+60h+var_B0+8], rbx
0x180001a99  movups  [rbp+60h+var_80], xmm0
0x180001a9d  mov     qword ptr [rbp+60h+var_80], rax
0x180001aa1  movups  [rbp+60h+var_40], xmm0
0x180001aa5  mov     dword ptr [rbp+60h+var_A0+8], r13d
0x180001aa9  movups  [rbp+60h+var_70], xmm0
0x180001aad  mov     dword ptr [rbp+60h+var_90], r12d
0x180001ab1  movups  [rbp+60h+var_60], xmm0
0x180001ab5  mov     qword ptr [rbp+60h+var_40+8], rsi
0x180001ab9  movups  [rbp+60h+var_50], xmm0
0x180001abd  jmp     loc_180001C4B
0x180001ac2  mov     r8d, [r15+30h]
0x180001ac6  mov     rax, [rbx+10h]
0x180001aca  mov     edx, [r15+28h]
0x180001ace  shr     r8d, 4
0x180001ad2  and     r8b, 1
0x180001ad6  call    _guard_dispatch_icall
0x180001adb  mov     ecx, [r15+34h]
0x180001adf  bt      ecx, 0Eh
0x180001ae3  jnb     short loc_180001AE7
0x180001ae5  and     al, 0FBh
0x180001ae7  cmp     [rbp+60h+var_E0], 0
0x180001aeb  jz      loc_180001B8B
0x180001af1  cmp     [rbp+60h+arg_0], 0
0x180001af5  jnz     short loc_180001AFF
0x180001af7  xor     r9d, r9d
0x180001afa  xor     r11d, r11d
0x180001afd  jmp     short loc_180001B07
0x180001aff  mov     r9d, [r14+28h]
0x180001b03  mov     r11, [r14+20h]
0x180001b07  mov     edx, [r15+30h]
0x180001b0b  mov     ecx, [r15+34h]
0x180001b0f  shr     edx, 4
0x180001b12  and     dl, 1
0x180001b15  test    cl, 10h
0x180001b18  jz      short loc_180001B23
0x180001b1a  mov     r8, [r15+1D8h]
0x180001b21  jmp     short loc_180001B26
0x180001b23  xor     r8d, r8d
  ... truncated ...
```
