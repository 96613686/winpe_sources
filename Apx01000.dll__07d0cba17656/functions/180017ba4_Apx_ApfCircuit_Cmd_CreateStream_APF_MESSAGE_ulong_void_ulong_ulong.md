# Apx::ApfCircuit::Cmd_CreateStream(APF_MESSAGE *,ulong,void *,ulong,ulong *)

- ea: `0x180017ba4`
- end: `0x1800181a3`
- name: `?Cmd_CreateStream@ApfCircuit@Apx@@AEAAJPEAUAPF_MESSAGE@@KPEAXKPEAK@Z`
- size: `1535`
- prototype: `__int64 __fastcall(unsigned __int64 this, struct APF_MESSAGE *, unsigned int, struct Apx::ApfIpcLink *, char, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180017a08`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18000d210`
- `0x18000d2f0`
- `0x18000d3c0`
- `0x18001051c`
- `0x180011f50`
- `0x180017ba4`
- `0x180018d04`
- `0x18001909c`
- `0x1800195e8`
- `0x180019afc`
- `0x18001d680`
- `0x1800208ec`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800180dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800180dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018081`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018081`

## pseudocode

```c
__int64 __fastcall Apx::ApfCircuit::Cmd_CreateStream(
        unsigned __int64 this,
        struct APF_MESSAGE *a2,
        unsigned int a3,
        struct Apx::ApfIpcLink *a4,
        char a5,
        unsigned int *a6)
{
  __int64 v9; // rdi
  Apx::ApfVerify *v10; // r14
  char v11; // r12
  int v12; // ebx
  Apx::ApfVerify *v13; // rdx
  __int64 v14; // rdx
  Apx::ApfVerify *v15; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  unsigned int *v19; // rax
  __int64 v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // r8
  int v23; // eax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  Apx::ApfVerify *v29; // r15
  Apx::ApfCircuit **v30; // r8
  unsigned __int64 v31; // r15
  __int64 v32; // [rsp+40h] [rbp-40h] BYREF
  __int64 v33; // [rsp+48h] [rbp-38h] BYREF
  __int64 v34; // [rsp+50h] [rbp-30h]
  char *v35; // [rsp+58h] [rbp-28h]
  __int64 v36; // [rsp+60h] [rbp-20h]
  struct Apx::ApfIpcLink *v37; // [rsp+68h] [rbp-18h]
  __int64 v38; // [rsp+70h] [rbp-10h]
  Apx::ApfVerify *v39; // [rsp+C8h] [rbp+48h] BYREF
  struct Apx::ApfIpcLink *v40; // [rsp+D8h] [rbp+58h] BYREF

  v40 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids);
  }
  v40 = 0;
  v9 = 0;
  v39 = 0;
  v10 = 0;
  v32 = 0;
  v11 = 0;
  *a6 = 0;
  if ( !a2 || a3 < 0x318 )
  {
    v12 = -1073741811;
LABEL_79:
    if ( v10 )
      imp_ApxObjectDelete(0, v10);
    goto LABEL_81;
  }
  if ( !*((_QWORD *)a2 + 6) )
  {
    v12 = -1073741811;
    goto LABEL_9;
  }
  if ( (*(int (__fastcall **)(_QWORD))(**(_QWORD **)(this + 24) + 32LL))(*(_QWORD *)(this + 24)) < 0 )
  {
    v12 = -1073741436;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 30;
LABEL_37:
      WPP_SF_qd(v17[2], v18, &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids, ~this, v12);
      goto LABEL_81;
    }
    goto LABEL_81;
  }
  v11 = 1;
  a5 = 1;
  v19 = (unsigned int *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  a6 = v19;
  if ( !v19
    || (v20 = Apx::ApfStreamInit::ApfStreamInit((Apx::ApfStreamInit *)v19, (struct Apx::ApfCircuit *)this),
        (v9 = v20) == 0) )
  {
    v12 = -1073741670;
    goto LABEL_81;
  }
  *(_DWORD *)(v20 + 32) &= ~1u;
  *(_QWORD *)(v20 + 96) = *((_QWORD *)a2 + 6);
  v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct Apx::ApfIpcLink **))(**(_QWORD **)(this + 24) + 64LL))(
          *(_QWORD *)(this + 24),
          *((_QWORD *)a2 + 6),
          &v40);
  if ( v21 >= 0 )
  {
    if ( *((_WORD *)a2 + 40) )
    {
      v38 = *((_QWORD *)a2 + 9);
      v35 = (char *)a2 + 80;
      v37 = v40;
      v34 = 0;
      v36 = 0;
      v33 = 0x300000030LL;
      v23 = ApfObjectBagOpen((Apx::ApfVerify **)&v33, (Apx::ApfVerify *)&v39, v22);
      if ( v23 < 0 )
      {
        v12 = Apx::ApfHelper::NtStatusFromHr(v23);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids,
            ~this,
            v12);
        }
        v10 = v39;
        goto LABEL_79;
      }
      v10 = v39;
    }
    v34 = 0;
    v35 = (char *)a2 + 600;
    v33 = 24;
    v24 = imp_ApxDataFormatCreate(0, 0, (struct _APX_DATAFORMAT_CONFIG *)&v33, (Apx::ApfVerify *)&v32);
    if ( v24 < 0 )
    {
      v12 = Apx::ApfHelper::NtStatusFromHr(v24);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids, ~this, v12);
      }
      goto LABEL_79;
    }
    *(_QWORD *)(v9 + 24) = this;
    imp_ApxObjectReferenceActual(0, (Apx::ApfVerify *)~this);
    v25 = v32;
    *(_QWORD *)(v9 + 80) = (char *)a2 + 56;
    *(_QWORD *)(v9 + 88) = ~v25;
    v26 = (*(__int64 (__fastcall **)(unsigned __int64, __int64))(this + 136))(~this, ~v9);
    if ( v26 >= 0 )
    {
      v29 = *(Apx::ApfVerify **)(v9 + 104);
      if ( v29 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(this + 88));
        imp_ApxObjectReferenceActual(0, v29);
        v30 = *(Apx::ApfCircuit ***)(this + 608);
        if ( *v30 != (Apx::ApfCircuit *)(this + 600) )
          __fastfail(3u);
        v31 = ~(unsigned __int64)v29;
        *(_QWORD *)(v31 + 248) = this + 600;
        *(_QWORD *)(v31 + 256) = v30;
        *v30 = (Apx::ApfCircuit *)(v31 + 248);
        *(_QWORD *)(this + 608) = v31 + 248;
        LeaveCriticalSection((LPCRITICAL_SECTION)(this + 88));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_qqqqi(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids,
            ~*(_QWORD *)(this + 24),
            ~this,
            *(_QWORD *)(v9 + 104),
            ~(unsigned __int64)v40,
            *((_QWORD *)a2 + 6));
        }
        Apx::ApfStream::AddIpcLink((Apx::ApfStream *)v31, v40);
        v12 = 0;
        goto LABEL_64;
      }
      v12 = -1073741823;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_64:
        v11 = a5;
        goto LABEL_79;
      }
      v28 = 35;
    }
    else
    {
      v12 = Apx::ApfHelper::NtStatusFromHr(v26);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_64;
      }
      v28 = 34;
    }
    WPP_SF_qd(v27[2], v28, &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids, ~this, v12);
    goto LABEL_64;
  }
  v12 = Apx::ApfHelper::NtStatusFromHr(v21);
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = 31;
    goto LABEL_37;
  }
LABEL_81:
  if ( v40 )
    imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~(unsigned __int64)v40);
LABEL_9:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl'::`2'::impl) )
  {
    if ( v9 )
    {
      v13 = *(Apx::ApfVerify **)(v9 + 104);
      if ( v13 )
        imp_ApxObjectDereferenceActual(0, v13);
    }
  }
  if ( v12 < 0 )
  {
    if ( v9 )
    {
      v14 = *(_QWORD *)(v9 + 88);
      if ( v14 )
      {
        imp_ApxObjectDelete(0, (Apx::ApfVerify *)~v14);
        *(_QWORD *)(v9 + 88) = 0;
      }
      v15 = *(Apx::ApfVerify **)(v9 + 104);
      if ( v15 )
      {
        imp_ApxObjectDelete(0, v15);
        *(_QWORD *)(v9 + 104) = 0;
      }
      if ( v40 )
      {
        imp_ApxObjectDelete(0, (Apx::ApfVerify *)~(unsigned __int64)v40);
        v40 = 0;
      }
    }
    if ( v11 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(this + 24) + 40LL))(*(_QWORD *)(this + 24));
  }
  if ( v9 )
  {
    if ( *(_QWORD *)(v9 + 24) )
    {
      imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~this);
      *(_QWORD *)(v9 + 24) = 0;
    }
    (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180017ba4  mov     [rsp-38h+arg_0], rbx
0x180017ba9  mov     [rsp-38h+arg_18], r9
0x180017bae  push    rbp
0x180017baf  push    rsi
0x180017bb0  push    rdi
0x180017bb1  push    r12
0x180017bb3  push    r13
0x180017bb5  push    r14
0x180017bb7  push    r15
0x180017bb9  mov     rbp, rsp
0x180017bbc  sub     rsp, 80h
0x180017bc3  mov     r15d, r8d
0x180017bc6  mov     rbx, rdx
0x180017bc9  mov     rsi, rcx
0x180017bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bd3  lea     rax, WPP_GLOBAL_Control
0x180017bda  cmp     rcx, rax
0x180017bdd  jz      short loc_180017C00
0x180017bdf  test    byte ptr [rcx+1Ch], 1
0x180017be3  jz      short loc_180017C00
0x180017be5  cmp     byte ptr [rcx+19h], 5
0x180017be9  jb      short loc_180017C00
0x180017beb  mov     rcx, [rcx+10h]
0x180017bef  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180017bf6  mov     edx, 1Dh
0x180017bfb  call    WPP_SF_
0x180017c00  mov     rax, [rbp+arg_28]
0x180017c04  xor     r13d, r13d
0x180017c07  mov     [rbp+arg_18], r13
0x180017c0b  mov     edi, r13d
0x180017c0e  mov     [rbp+arg_8], r13
0x180017c12  mov     r14d, r13d
0x180017c15  mov     [rbp+var_40], r13
0x180017c19  mov     r12b, r13b
0x180017c1c  mov     [rax], r13d
0x180017c1f  test    rbx, rbx
0x180017c22  jz      loc_18001815B
0x180017c28  cmp     r15d, 318h
0x180017c2f  jb      loc_18001815B
0x180017c35  cmp     [rbx+30h], r13
0x180017c39  jnz     loc_180017D72
0x180017c3f  mov     ebx, 0C000000Dh
0x180017c44  lea     r14, aOnecoreuapDriv_2; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180017c4b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56664216@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216> `wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl(void)'::`2'::impl
0x180017c52  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(void)
0x180017c57  test    al, al
0x180017c59  jz      short loc_180017C81
0x180017c5b  test    rdi, rdi
0x180017c5e  jz      short loc_180017C81
0x180017c60  mov     rdx, [rdi+68h]; Apx::ApfVerify *
0x180017c64  test    rdx, rdx
0x180017c67  jz      short loc_180017C81
0x180017c69  xor     ecx, ecx; this
0x180017c6b  mov     [rsp+80h+var_60], r14
0x180017c70  mov     r9d, 2ECh
0x180017c76  mov     r8d, 44787041h
0x180017c7c  call    imp_ApxObjectDereferenceActual
0x180017c81  test    ebx, ebx
0x180017c83  jns     short loc_180017CE1
0x180017c85  test    rdi, rdi
0x180017c88  jz      short loc_180017CCC
0x180017c8a  mov     rdx, [rdi+58h]
0x180017c8e  test    rdx, rdx
0x180017c91  jz      short loc_180017CA1
0x180017c93  not     rdx; Apx::ApfVerify *
0x180017c96  xor     ecx, ecx; this
0x180017c98  call    imp_ApxObjectDelete
0x180017c9d  mov     [rdi+58h], r13
0x180017ca1  mov     rdx, [rdi+68h]; Apx::ApfVerify *
0x180017ca5  test    rdx, rdx
0x180017ca8  jz      short loc_180017CB5
0x180017caa  xor     ecx, ecx; this
0x180017cac  call    imp_ApxObjectDelete
0x180017cb1  mov     [rdi+68h], r13
0x180017cb5  mov     rdx, [rbp+arg_18]
0x180017cb9  test    rdx, rdx
0x180017cbc  jz      short loc_180017CCC
0x180017cbe  not     rdx; Apx::ApfVerify *
0x180017cc1  xor     ecx, ecx; this
0x180017cc3  call    imp_ApxObjectDelete
0x180017cc8  mov     [rbp+arg_18], r13
0x180017ccc  test    r12b, r12b
0x180017ccf  jz      short loc_180017CE1
0x180017cd1  mov     rcx, [rsi+18h]
0x180017cd5  mov     rax, [rcx]
0x180017cd8  mov     rax, [rax+28h]
0x180017cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ce1  test    rdi, rdi
0x180017ce4  jz      short loc_180017D21
0x180017ce6  cmp     [rdi+18h], r13
0x180017cea  jz      short loc_180017D0E
0x180017cec  not     rsi
0x180017cef  mov     [rsp+80h+var_60], r14
0x180017cf4  mov     rdx, rsi; Apx::ApfVerify *
0x180017cf7  mov     r9d, 312h
0x180017cfd  mov     r8d, 44787041h
0x180017d03  xor     ecx, ecx; this
0x180017d05  call    imp_ApxObjectDereferenceActual
0x180017d0a  mov     [rdi+18h], r13
0x180017d0e  mov     rax, [rdi]
0x180017d11  mov     edx, 1
0x180017d16  mov     rcx, rdi
0x180017d19  mov     rax, [rax]
0x180017d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d28  lea     rax, WPP_GLOBAL_Control
0x180017d2f  cmp     rcx, rax
0x180017d32  jz      short loc_180017D55
0x180017d34  test    byte ptr [rcx+1Ch], 1
0x180017d38  jz      short loc_180017D55
0x180017d3a  cmp     byte ptr [rcx+19h], 5
0x180017d3e  jb      short loc_180017D55
0x180017d40  mov     rcx, [rcx+10h]
0x180017d44  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180017d4b  mov     edx, 25h ; '%'
0x180017d50  call    WPP_SF_
0x180017d55  mov     eax, ebx
0x180017d57  mov     rbx, [rsp+80h+arg_0]
0x180017d5f  add     rsp, 80h
0x180017d66  pop     r15
0x180017d68  pop     r14
0x180017d6a  pop     r13
0x180017d6c  pop     r12
0x180017d6e  pop     rdi
0x180017d6f  pop     rsi
0x180017d70  pop     rbp
0x180017d71  retn
0x180017d72  mov     rcx, [rsi+18h]
0x180017d76  mov     rax, [rcx]
0x180017d79  mov     rax, [rax+20h]
0x180017d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d82  test    eax, eax
0x180017d84  jns     short loc_180017DDA
0x180017d86  mov     ebx, 0C0000184h
0x180017d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d92  lea     rax, WPP_GLOBAL_Control
0x180017d99  cmp     rcx, rax
0x180017d9c  jz      loc_18001816F
0x180017da2  test    byte ptr [rcx+1Ch], 10h
0x180017da6  jz      loc_18001816F
0x180017dac  cmp     byte ptr [rcx+19h], 2
0x180017db0  jb      loc_18001816F
0x180017db6  mov     edx, 1Eh
0x180017dbb  mov     rcx, [rcx+10h]
0x180017dbf  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180017dc6  mov     r9, rsi
0x180017dc9  mov     dword ptr [rsp+80h+var_60], ebx
0x180017dcd  not     r9
0x180017dd0  call    WPP_SF_qd
0x180017dd5  jmp     loc_18001816F
0x180017dda  mov     r12b, 1
0x180017ddd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017de4  mov     ecx, 78h ; 'x'; unsigned __int64
0x180017de9  mov     [rbp+arg_20], r12b
0x180017ded  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017df2  mov     [rbp+arg_28], rax
0x180017df6  test    rax, rax
0x180017df9  jz      loc_180018154
0x180017dff  mov     rdx, rsi; struct Apx::ApfCircuit *
0x180017e02  mov     rcx, rax; this
0x180017e05  call    ??0ApfStreamInit@Apx@@QEAA@PEAVApfCircuit@1@@Z; Apx::ApfStreamInit::ApfStreamInit(Apx::ApfCircuit *)
0x180017e0a  mov     rdi, rax
0x180017e0d  test    rax, rax
0x180017e10  jz      loc_180018154
0x180017e16  and     dword ptr [rax+20h], 0FFFFFFFEh
0x180017e1a  lea     r8, [rbp+arg_18]
0x180017e1e  mov     rax, [rbx+30h]
0x180017e22  mov     [rdi+60h], rax
0x180017e26  mov     rcx, [rsi+18h]
0x180017e2a  mov     rdx, [rbx+30h]
0x180017e2e  mov     rax, [rcx]
0x180017e31  mov     rax, [rax+40h]
0x180017e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e3a  test    eax, eax
0x180017e3c  jns     short loc_180017E7C
0x180017e3e  mov     ecx, eax; int
0x180017e40  call    ?NtStatusFromHr@ApfHelper@Apx@@SAJJ@Z; Apx::ApfHelper::NtStatusFromHr(long)
0x180017e45  mov     ebx, eax
0x180017e47  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e4e  lea     rax, WPP_GLOBAL_Control
0x180017e55  cmp     rcx, rax
0x180017e58  jz      loc_18001816F
0x180017e5e  test    byte ptr [rcx+1Ch], 10h
0x180017e62  jz      loc_18001816F
0x180017e68  cmp     byte ptr [rcx+19h], 2
0x180017e6c  jb      loc_18001816F
0x180017e72  mov     edx, 1Fh
0x180017e77  jmp     loc_180017DBB
0x180017e7c  lea     rcx, [rbx+50h]
0x180017e80  cmp     [rcx], r13w
0x180017e84  jz      loc_180017F19
0x180017e8a  mov     rax, [rbx+48h]
0x180017e8e  lea     rdx, [rbp+arg_8]; this
0x180017e92  mov     [rbp+var_10], rax
0x180017e96  mov     rax, [rbp+arg_18]
0x180017e9a  mov     [rbp+var_28], rcx
0x180017e9e  lea     rcx, [rbp+var_38]; struct Apx::_APF_OBJECTBAG_CONFIG *
0x180017ea2  mov     [rbp+var_18], rax
0x180017ea6  mov     [rbp+var_30], r13
0x180017eaa  mov     [rbp+var_20], r13
0x180017eae  mov     dword ptr [rbp+var_38], 30h ; '0'
0x180017eb5  mov     dword ptr [rbp+var_38+4], 3
0x180017ebc  call    ApfObjectBagOpen
0x180017ec1  test    eax, eax
0x180017ec3  jns     short loc_180017F15
0x180017ec5  mov     ecx, eax; int
0x180017ec7  call    ?NtStatusFromHr@ApfHelper@Apx@@SAJJ@Z; Apx::ApfHelper::NtStatusFromHr(long)
0x180017ecc  mov     ebx, eax
0x180017ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ed5  lea     rax, WPP_GLOBAL_Control
0x180017edc  cmp     rcx, rax
0x180017edf  jz      short loc_180017F0C
0x180017ee1  test    byte ptr [rcx+1Ch], 10h
0x180017ee5  jz      short loc_180017F0C
0x180017ee7  cmp     byte ptr [rcx+19h], 2
0x180017eeb  jb      short loc_180017F0C
0x180017eed  mov     rcx, [rcx+10h]
0x180017ef1  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180017ef8  mov     r9, rsi
0x180017efb  mov     dword ptr [rsp+80h+var_60], ebx
0x180017eff  not     r9
0x180017f02  mov     edx, 20h ; ' '
0x180017f07  call    WPP_SF_qd
0x180017f0c  mov     r14, [rbp+arg_8]
0x180017f10  jmp     loc_180018160
0x180017f15  mov     r14, [rbp+arg_8]
0x180017f19  lea     rax, [rbx+258h]
0x180017f20  mov     [rbp+var_30], r13
0x180017f24  lea     r9, [rbp+var_40]; Apx::ApfVerify *
0x180017f28  mov     [rbp+var_28], rax
0x180017f2c  lea     r8, [rbp+var_38]; struct _APX_DATAFORMAT_CONFIG *
0x180017f30  mov     [rbp+var_38], 18h
0x180017f38  xor     edx, edx; Apx::ApfVerify *
0x180017f3a  xor     ecx, ecx; this
0x180017f3c  call    imp_ApxDataFormatCreate
0x180017f41  test    eax, eax
0x180017f43  jns     short loc_180017F9D
0x180017f45  mov     ecx, eax; int
0x180017f47  call    ?NtStatusFromHr@ApfHelper@Apx@@SAJJ@Z; Apx::ApfHelper::NtStatusFromHr(long)
0x180017f4c  mov     ebx, eax
0x180017f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f55  lea     rax, WPP_GLOBAL_Control
0x180017f5c  cmp     rcx, rax
0x180017f5f  jz      loc_180018160
0x180017f65  test    byte ptr [rcx+1Ch], 10h
0x180017f69  jz      loc_180018160
0x180017f6f  cmp     byte ptr [rcx+19h], 2
0x180017f73  jb      loc_180018160
0x180017f79  mov     rcx, [rcx+10h]
0x180017f7d  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180017f84  mov     r9, rsi
0x180017f87  mov     dword ptr [rsp+80h+var_60], ebx
0x180017f8b  not     r9
0x180017f8e  mov     edx, 21h ; '!'
0x180017f93  call    WPP_SF_qd
0x180017f98  jmp     loc_180018160
0x180017f9d  lea     rax, aOnecoreuapDriv_2; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180017fa4  mov     [rdi+18h], rsi
0x180017fa8  mov     r12, rsi
0x180017fab  mov     [rsp+80h+var_60], rax
0x180017fb0  not     r12
0x180017fb3  mov     r9d, 296h
0x180017fb9  mov     rdx, r12; Apx::ApfVerify *
0x180017fbc  mov     r8d, 44787041h
0x180017fc2  xor     ecx, ecx; this
0x180017fc4  call    imp_ApxObjectReferenceActual
0x180017fc9  mov     r8, [rbp+var_40]
0x180017fcd  lea     r9, [rbx+38h]
0x180017fd1  mov     rax, r8
0x180017fd4  mov     [rdi+50h], r9
0x180017fd8  not     rax
0x180017fdb  mov     [rsp+80h+var_60], r14
0x180017fe0  mov     [rdi+58h], rax
0x180017fe4  mov     rdx, rdi
0x180017fe7  mov     rax, [rsi+88h]
0x180017fee  not     rdx
0x180017ff1  mov     rcx, r12
0x180017ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ff9  test    eax, eax
0x180017ffb  jns     short loc_18001804A
0x180017ffd  mov     ecx, eax; int
0x180017fff  call    ?NtStatusFromHr@ApfHelper@Apx@@SAJJ@Z; Apx::ApfHelper::NtStatusFromHr(long)
0x180018004  mov     ebx, eax
0x180018006  mov     rcx, cs:WPP_GLOBAL_Control
0x18001800d  lea     rax, WPP_GLOBAL_Control
0x180018014  cmp     rcx, rax
0x180018017  jz      short loc_180018041
0x180018019  test    byte ptr [rcx+1Ch], 10h
0x18001801d  jz      short loc_180018041
0x18001801f  cmp     byte ptr [rcx+19h], 2
0x180018023  jb      short loc_180018041
0x180018025  mov     edx, 22h ; '"'
0x18001802a  mov     rcx, [rcx+10h]
0x18001802e  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180018035  mov     r9, r12
0x180018038  mov     dword ptr [rsp+80h+var_60], ebx
0x18001803c  call    WPP_SF_qd
0x180018041  mov     r12b, [rbp+arg_20]
0x180018045  jmp     loc_180018160
0x18001804a  mov     r15, [rdi+68h]
  ... truncated ...
```
