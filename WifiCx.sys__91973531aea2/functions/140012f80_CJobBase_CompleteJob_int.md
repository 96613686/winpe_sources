# CJobBase::CompleteJob(int)

- ea: `0x140012f80`
- end: `0x140013382`
- name: `?CompleteJob@CJobBase@@IEAAHH@Z`
- size: `1026`
- prototype: `__int64 __fastcall(CJobBase *__hidden this, int)`
- caller_count: `98`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140011f9c`
- `0x1400123c0`
- `0x140012610`
- `0x1400127d0`
- `0x140012980`
- `0x140012cc0`
- `0x140028c50`
- `0x14002abbc`
- `0x14004dce4`
- `0x14005d990`
- `0x14005daa0`
- `0x14005dc20`
- `0x14005ddf0`
- `0x14005e1b0`
- `0x140060740`
- `0x140060870`
- `0x140065844`
- `0x140066410`
- `0x140066440`
- `0x140066560`
- `0x1400665e0`
- `0x140066610`
- `0x1400666d8`
- `0x140068e44`
- `0x140068edc`
- `0x1400695e0`
- `0x140069810`
- `0x140069b00`
- `0x140069c00`
- `0x140069ce0`
- `0x140069e70`
- `0x14006a530`
- `0x14006bbdc`
- `0x14006bd60`
- `0x14006ca10`
- `0x14006cb00`
- `0x14006cca0`
- `0x14006cd90`
- `0x14006cf90`
- `0x14006d1b0`
- `0x14006d270`
- `0x14006d380`
- `0x140071820`
- `0x140071ae0`
- `0x140071c10`
- `0x140071f20`
- `0x140072050`
- `0x140075440`
- `0x140075660`
- `0x140075fb0`

## callees

- `0x140009420`
- `0x14000c940`
- `0x14000cf40`
- `0x140012f80`
- `0x1400156d0`
- `0x14001e2c0`
- `0x14001e430`
- `0x14001eed0`
- `0x140064274`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001328c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400132ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001328c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400132ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013231`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013231`

## pseudocode

```c
__int64 __fastcall CJobBase::CompleteJob(CJobBase *this, __int64 a2, __int64 a3, int a4)
{
  int v4; // edi
  CJobBase *v5; // rbx
  unsigned int v6; // edi
  bool v7; // zf
  unsigned int v8; // esi
  __int64 v9; // r14
  Event *v10; // rsi
  __int64 v11; // rbp
  Event *v12; // rax
  char v13; // r15
  _QWORD *v14; // rdi
  __int64 v15; // r14
  __int64 v16; // r15
  _QWORD *v17; // rax
  char v18; // di
  __int64 v19; // r15
  _QWORD *v20; // rax
  KIRQL v21; // dl
  KIRQL v22; // dl
  int v23; // edx
  int v25; // [rsp+20h] [rbp-48h]
  __int64 v26; // [rsp+38h] [rbp-30h]

  v4 = a2;
  v5 = this;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    this = (CJobBase *)WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (unsigned int)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
        64,
        (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
        (char)v5,
        *((_DWORD *)v5 + 4));
    }
  }
  if ( *((_DWORD *)v5 + 16) != 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (unsigned int)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
        65,
        (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
        (char)v5,
        *((_DWORD *)v5 + 4),
        *((_DWORD *)v5 + 16));
    }
    v6 = -1073741436;
    goto LABEL_46;
  }
  v7 = *((_QWORD *)v5 + 64) == 0;
  *((_DWORD *)v5 + 16) = 0;
  if ( !v7 )
  {
    v8 = 0;
    if ( v4 )
    {
      v8 = -1073741823;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_LDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          (unsigned int)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
          a4,
          v25,
          *((_DWORD *)v5 + 15),
          *((_DWORD *)v5 + 4),
          v4);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01031 + 2104))(
      WdfDriverGlobals,
      *((_QWORD *)v5 + 64),
      v8);
    *((_QWORD *)v5 + 64) = 0;
  }
  v9 = *((_QWORD *)v5 + 16);
  v10 = (CJobBase *)((char *)v5 + 208);
  v11 = *((_QWORD *)v5 + 4);
  if ( v5 == (CJobBase *)-208LL )
  {
    v12 = (Event *)operator new(0x48u);
    if ( !v12 || (v10 = Event::Event(v12, 0, 0)) == 0 )
    {
      v6 = -1073741670;
      goto LABEL_46;
    }
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( !v11 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (unsigned int)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
        10,
        (__int64)WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids,
        (char)v10,
        *(_DWORD *)v10);
    }
    v6 = -1073741811;
    goto LABEL_43;
  }
  if ( !*((_BYTE *)v10 + 45) )
  {
    *((_DWORD *)v10 + 4) = 1;
    *((_QWORD *)v10 + 1) = v11;
    *((_QWORD *)v10 + 4) = v9;
    *((_QWORD *)v10 + 3) = v5;
    *((_DWORD *)v10 + 10) = v4;
    v14 = (_QWORD *)((char *)v10 + 48);
    v15 = v11 + 72;
    if ( (unsigned int)Feature_54699885__private_IsEnabledDeviceUsageNoInline(
                         this,
                         a2,
                         WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids) )
    {
      v16 = *(_QWORD *)(v11 + 40);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 2528))(WdfDriverGlobals, v16);
      *((_BYTE *)v10 + 45) = 1;
      v17 = *(_QWORD **)(v11 + 80);
      if ( *v17 == v15 )
      {
        *v14 = v15;
        *((_QWORD *)v10 + 7) = v17;
        *v17 = v14;
        *(_QWORD *)(v11 + 80) = v14;
        v18 = 0;
        if ( !*(_BYTE *)(v11 + 56) )
        {
          v18 = 1;
          *(_QWORD *)(v11 + 88) = KeGetCurrentThread();
          *(_BYTE *)(v11 + 56) = 1;
        }
        if ( v16 )
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 2536))(WdfDriverGlobals, v16);
        if ( !v18 )
        {
          v6 = 0;
          goto LABEL_46;
        }
        goto LABEL_37;
      }
    }
    else
    {
      v19 = *(_QWORD *)(v11 + 32);
      *(_BYTE *)(v19 + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v19);
      *(_BYTE *)(v19 + 16) = 1;
      *((_BYTE *)v10 + 45) = 1;
      v20 = *(_QWORD **)(v11 + 80);
      if ( *v20 == v15 )
      {
        *v14 = v15;
        *((_QWORD *)v10 + 7) = v20;
        *v20 = v14;
        *(_QWORD *)(v11 + 80) = v14;
        if ( *(_BYTE *)(v11 + 56) )
        {
          v22 = *(_BYTE *)(v19 + 8);
          *(_BYTE *)(v19 + 16) = 0;
          KeReleaseSpinLock((PKSPIN_LOCK)v19, v22);
          goto LABEL_39;
        }
        *(_QWORD *)(v11 + 88) = KeGetCurrentThread();
        *(_BYTE *)(v11 + 56) = 1;
        v21 = *(_BYTE *)(v19 + 8);
        *(_BYTE *)(v19 + 16) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)v19, v21);
LABEL_37:
        EventQueue::ProcessEventQueueUntilEmpty((EventQueue *)v11);
LABEL_39:
        v6 = 0;
        goto LABEL_46;
      }
    }
    __fastfail(3u);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (unsigned int)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      11,
      (__int64)WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids,
      (char)v10,
      *(_DWORD *)v10);
  }
  v6 = -1073741436;
LABEL_43:
  if ( v10 && v13 )
    operator delete(v10);
LABEL_46:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v23 = *((_DWORD *)v5 + 4);
    LODWORD(v26) = v6;
    LOBYTE(v23) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      (unsigned int)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      67,
      (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      (char)v5,
      *((_DWORD *)v5 + 4),
      v26);
  }
  return v6;
}

```

## disassembly

```asm
0x140012f80  push    rbx
0x140012f82  push    rdi
0x140012f83  push    r12
0x140012f85  sub     rsp, 50h
0x140012f89  mov     edi, edx
0x140012f8b  mov     rbx, rcx
0x140012f8e  lea     r12, WPP_RECORDER_INITIALIZED
0x140012f95  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140012f9c  lea     r8, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x140012fa3  jz      short loc_140012FE2
0x140012fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140012fac  cmp     byte ptr [rcx+29h], 5
0x140012fb0  jnb     short loc_140012FB9
0x140012fb2  cmp     word ptr [rcx+48h], 0
0x140012fb7  jz      short loc_140012FE2
0x140012fb9  mov     eax, [rbx+10h]
0x140012fbc  mov     r9d, 40h ; '@'
0x140012fc2  mov     rcx, [rcx+40h]
0x140012fc6  mov     dl, 5
0x140012fc8  mov     [rsp+68h+var_38], eax
0x140012fcc  mov     [rsp+68h+var_40], rbx
0x140012fd1  mov     [rsp+68h+var_48], r8
0x140012fd6  call    WPP_RECORDER_SF_qD
0x140012fdb  lea     r8, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x140012fe2  mov     eax, [rbx+40h]
0x140012fe5  mov     [rsp+68h+arg_0], rbp
0x140012fea  mov     [rsp+68h+arg_8], rsi
0x140012fef  mov     [rsp+68h+arg_10], r14
0x140012ff7  mov     [rsp+68h+arg_18], r15
0x140012fff  cmp     eax, 1
0x140013002  jz      short loc_14001304B
0x140013004  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001300b  jz      short loc_140013041
0x14001300d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013014  mov     r9d, 41h ; 'A'
0x14001301a  mov     dword ptr [rsp+68h+var_30], eax
0x14001301e  mov     dl, 2
0x140013020  mov     eax, [rbx+10h]
0x140013023  mov     [rsp+68h+var_38], eax
0x140013027  mov     rcx, [rcx+40h]
0x14001302b  mov     [rsp+68h+var_40], rbx
0x140013030  mov     [rsp+68h+var_48], r8
0x140013035  call    WPP_RECORDER_SF_qDD
0x14001303a  lea     r8, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x140013041  mov     edi, 0C0000184h
0x140013046  jmp     loc_140013319
0x14001304b  cmp     qword ptr [rbx+200h], 0
0x140013053  mov     dword ptr [rbx+40h], 0
0x14001305a  jz      short loc_1400130C8
0x14001305c  xor     esi, esi
0x14001305e  test    edi, edi
0x140013060  jz      short loc_140013092
0x140013062  mov     esi, 0C0000001h
0x140013067  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001306e  jz      short loc_140013092
0x140013070  mov     eax, [rbx+10h]
0x140013073  mov     rcx, cs:WPP_GLOBAL_Control
0x14001307a  mov     dword ptr [rsp+68h+var_30], edi
0x14001307e  mov     [rsp+68h+var_38], eax
0x140013082  mov     eax, [rbx+3Ch]
0x140013085  mov     rcx, [rcx+40h]
0x140013089  mov     dword ptr [rsp+68h+var_40], eax
0x14001308d  call    WPP_RECORDER_SF_LDdd
0x140013092  mov     rax, cs:WdfFunctions_01031
0x140013099  mov     r8d, esi
0x14001309c  mov     rdx, [rbx+200h]
0x1400130a3  mov     rcx, cs:WdfDriverGlobals
0x1400130aa  mov     rax, [rax+838h]
0x1400130b1  call    _guard_dispatch_icall
0x1400130b6  lea     r8, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x1400130bd  mov     qword ptr [rbx+200h], 0
0x1400130c8  mov     r14, [rbx+80h]
0x1400130cf  lea     rsi, [rbx+0D0h]
0x1400130d6  mov     rbp, [rbx+20h]
0x1400130da  test    rsi, rsi
0x1400130dd  jnz     short loc_140013119
0x1400130df  mov     ecx, 48h ; 'H'; unsigned __int64
0x1400130e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400130e9  test    rax, rax
0x1400130ec  jz      short loc_14001310F
0x1400130ee  xor     r8d, r8d; unsigned int
0x1400130f1  xor     edx, edx; bool
0x1400130f3  mov     rcx, rax; this
0x1400130f6  call    ??0Event@@QEAA@_NK@Z; Event::Event(bool,ulong)
0x1400130fb  mov     rsi, rax
0x1400130fe  test    rax, rax
0x140013101  jz      short loc_14001310F
0x140013103  mov     r15b, 1
0x140013106  lea     r8, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x14001310d  jmp     short loc_14001311C
0x14001310f  mov     edi, 0C000009Ah
0x140013114  jmp     loc_140013312
0x140013119  xor     r15b, r15b
0x14001311c  test    rbp, rbp
0x14001311f  jz      loc_1400132BC
0x140013125  cmp     byte ptr [rsi+2Dh], 0
0x140013129  jz      short loc_140013174
0x14001312b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140013132  jz      short loc_14001316A
0x140013134  mov     eax, [rsi]
0x140013136  mov     r9d, 0Bh
0x14001313c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013143  mov     dl, 2
0x140013145  mov     [rsp+68h+var_38], eax
0x140013149  lea     rax, WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids
0x140013150  mov     [rsp+68h+var_40], rsi
0x140013155  mov     [rsp+68h+var_48], rax
0x14001315a  mov     rcx, [rcx+40h]
0x14001315e  call    WPP_RECORDER_SF_qD
0x140013163  lea     r8, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x14001316a  mov     edi, 0C0000184h
0x14001316f  jmp     loc_140013300
0x140013174  mov     dword ptr [rsi+10h], 1
0x14001317b  mov     [rsi+8], rbp
0x14001317f  mov     [rsi+20h], r14
0x140013183  mov     [rsi+18h], rbx
0x140013187  mov     [rsi+28h], edi
0x14001318a  lea     rdi, [rsi+30h]
0x14001318e  lea     r14, [rbp+48h]
0x140013192  call    Feature_54699885__private_IsEnabledDeviceUsageNoInline
0x140013197  test    eax, eax
0x140013199  jz      loc_14001322A
0x14001319f  mov     rax, cs:WdfFunctions_01031
0x1400131a6  mov     r15, [rbp+28h]
0x1400131aa  mov     rcx, cs:WdfDriverGlobals
0x1400131b1  mov     rdx, r15
0x1400131b4  mov     rax, [rax+9E0h]
0x1400131bb  call    _guard_dispatch_icall
0x1400131c0  mov     byte ptr [rsi+2Dh], 1
0x1400131c4  mov     rax, [r14+8]
0x1400131c8  cmp     [rax], r14
0x1400131cb  jnz     loc_140013253
0x1400131d1  mov     [rdi], r14
0x1400131d4  mov     [rdi+8], rax
0x1400131d8  mov     [rax], rdi
0x1400131db  mov     [r14+8], rdi
0x1400131df  xor     dil, dil
0x1400131e2  cmp     [rbp+38h], dil
0x1400131e6  jnz     short loc_1400131FC
0x1400131e8  mov     rax, gs:188h
0x1400131f1  mov     dil, 1
0x1400131f4  mov     [rbp+58h], rax
0x1400131f8  mov     byte ptr [rbp+38h], 1
0x1400131fc  test    r15, r15
0x1400131ff  jz      short loc_14001321E
0x140013201  mov     rax, cs:WdfFunctions_01031
0x140013208  mov     rdx, r15
0x14001320b  mov     rcx, cs:WdfDriverGlobals
0x140013212  mov     rax, [rax+9E8h]
0x140013219  call    _guard_dispatch_icall
0x14001321e  test    dil, dil
0x140013221  jnz     short loc_140013298
0x140013223  xor     edi, edi
0x140013225  jmp     loc_140013312
0x14001322a  mov     r15, [rbp+20h]
0x14001322e  mov     rcx, r15; SpinLock
0x140013231  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013238  nop     dword ptr [rax+rax+00h]
0x14001323d  mov     [r15+8], al
0x140013241  mov     byte ptr [r15+10h], 1
0x140013246  mov     byte ptr [rsi+2Dh], 1
0x14001324a  mov     rax, [r14+8]
0x14001324e  cmp     [rax], r14
0x140013251  jz      short loc_14001325A
0x140013253  mov     ecx, 3
0x140013258  int     29h; Win8: RtlFailFast(ecx)
0x14001325a  mov     [rdi], r14
0x14001325d  mov     rcx, r15; SpinLock
0x140013260  mov     [rdi+8], rax
0x140013264  mov     [rax], rdi
0x140013267  mov     [r14+8], rdi
0x14001326b  cmp     byte ptr [rbp+38h], 0
0x14001326f  jnz     short loc_1400132A2
0x140013271  mov     rax, gs:188h
0x14001327a  mov     [rbp+58h], rax
0x14001327e  mov     byte ptr [rbp+38h], 1
0x140013282  movzx   edx, byte ptr [r15+8]; NewIrql
0x140013287  mov     byte ptr [r15+10h], 0
0x14001328c  call    cs:__imp_KeReleaseSpinLock
0x140013293  nop     dword ptr [rax+rax+00h]
0x140013298  mov     rcx, rbp; this
0x14001329b  call    ?ProcessEventQueueUntilEmpty@EventQueue@@IEAAXXZ; EventQueue::ProcessEventQueueUntilEmpty(void)
0x1400132a0  jmp     short loc_1400132B8
0x1400132a2  movzx   edx, byte ptr [r15+8]; NewIrql
0x1400132a7  mov     byte ptr [r15+10h], 0
0x1400132ac  call    cs:__imp_KeReleaseSpinLock
0x1400132b3  nop     dword ptr [rax+rax+00h]
0x1400132b8  xor     edi, edi
0x1400132ba  jmp     short loc_140013312
0x1400132bc  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400132c3  jz      short loc_1400132FB
0x1400132c5  mov     eax, [rsi]
0x1400132c7  mov     r9d, 0Ah
0x1400132cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400132d4  mov     dl, 2
0x1400132d6  mov     [rsp+68h+var_38], eax
0x1400132da  lea     rax, WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids
0x1400132e1  mov     [rsp+68h+var_40], rsi
0x1400132e6  mov     [rsp+68h+var_48], rax
0x1400132eb  mov     rcx, [rcx+40h]
0x1400132ef  call    WPP_RECORDER_SF_qD
0x1400132f4  lea     r8, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x1400132fb  mov     edi, 0C000000Dh
0x140013300  test    rsi, rsi
0x140013303  jz      short loc_140013319
0x140013305  test    r15b, r15b
0x140013308  jz      short loc_140013319
0x14001330a  mov     rcx, rsi; void *
0x14001330d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140013312  lea     r8, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x140013319  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140013320  jz      short loc_14001335C
0x140013322  mov     rcx, cs:WPP_GLOBAL_Control
0x140013329  cmp     byte ptr [rcx+29h], 5
0x14001332d  jnb     short loc_140013336
0x14001332f  cmp     word ptr [rcx+48h], 0
0x140013334  jz      short loc_14001335C
0x140013336  mov     edx, [rbx+10h]
0x140013339  mov     r9d, 43h ; 'C'
0x14001333f  mov     rcx, [rcx+40h]
0x140013343  mov     dword ptr [rsp+68h+var_30], edi
0x140013347  mov     [rsp+68h+var_38], edx
0x14001334b  mov     dl, 5
0x14001334d  mov     [rsp+68h+var_40], rbx
0x140013352  mov     [rsp+68h+var_48], r8
0x140013357  call    WPP_RECORDER_SF_qDD
0x14001335c  mov     r15, [rsp+68h+arg_18]
0x140013364  mov     eax, edi
0x140013366  mov     r14, [rsp+68h+arg_10]
0x14001336e  mov     rsi, [rsp+68h+arg_8]
0x140013373  mov     rbp, [rsp+68h+arg_0]
0x140013378  add     rsp, 50h
0x14001337c  pop     r12
0x14001337e  pop     rdi
0x14001337f  pop     rbx
0x140013380  retn
```
