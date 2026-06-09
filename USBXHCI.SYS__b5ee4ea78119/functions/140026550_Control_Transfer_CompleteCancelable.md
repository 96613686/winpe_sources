# Control_Transfer_CompleteCancelable

- ea: `0x140026550`
- end: `0x140026a43`
- name: `Control_Transfer_CompleteCancelable`
- size: `1267`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000af30`
- `0x14000f9f0`
- `0x140010020`
- `0x140027020`

## callees

- `0x140002568`
- `0x140005d48`
- `0x14000d26c`
- `0x14000d2e4`
- `0x140026550`
- `0x140026a50`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400266cf`
- `ntoskrnl!KfRaiseIrql` at `0x1400267b4`
- `ntoskrnl!KfRaiseIrql` at `0x1400266cf`
- `ntoskrnl!KfRaiseIrql` at `0x1400267b4`
- `ntoskrnl!KeLowerIrql` at `0x140026703`
- `ntoskrnl!KeLowerIrql` at `0x1400267e6`
- `ntoskrnl!KeLowerIrql` at `0x140026703`
- `ntoskrnl!KeLowerIrql` at `0x1400267e6`
- `ntoskrnl!IoFreeMdl` at `0x140026819`
- `ntoskrnl!IoFreeMdl` at `0x140026819`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400265b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400266b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400265b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400266b9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026617`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026713`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026617`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026713`

## pseudocode

```c
__int64 __fastcall Control_Transfer_CompleteCancelable(__int64 a1)
{
  __int64 v1; // rbx
  int v3; // edi
  KIRQL v4; // dl
  unsigned __int64 v5; // r8
  int v6; // r9d
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // r15
  int v11; // r12d
  _QWORD *v12; // rdi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  char v15; // r8
  KIRQL v16; // di
  KIRQL v17; // al
  __int64 v19; // r13
  __int64 v20; // rdi
  KIRQL v21; // al
  __int64 v22; // r8
  KIRQL v23; // si
  struct _MDL *v24; // rcx
  int v25; // kr00_4
  int v26; // edx
  int v27; // eax
  unsigned int v28; // eax
  int v29; // eax

  v1 = *(_QWORD *)(a1 + 360);
  if ( *(_DWORD *)(v1 + 112) == 1 )
  {
    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 2048))(
           WdfDriverGlobals,
           *(_QWORD *)(v1 + 24));
    if ( v3 < 0 )
    {
      *(_DWORD *)(v1 + 112) = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = *(_QWORD *)(a1 + 48);
        v15 = *(_BYTE *)(v14 + 143);
        LOBYTE(v14) = 4;
        WPP_RECORDER_SF_ddL(
          *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
          v14,
          14,
          44,
          (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
          v15,
          *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL),
          v3);
      }
      return (unsigned int)v3;
    }
    *(_DWORD *)(v1 + 112) = 0;
  }
  if ( *(_DWORD *)(v1 + 116) != 1 )
  {
LABEL_5:
    v4 = *(_BYTE *)(a1 + 104);
    *(_QWORD *)(a1 + 360) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v4);
    v7 = *(_DWORD *)(v1 + 124);
    v8 = *(_QWORD *)(v1 + 48);
    if ( v7 )
    {
      if ( v7 == 28 )
      {
LABEL_7:
        *(_DWORD *)(v8 + 4) = 0;
        v9 = 0;
      }
      else
      {
        v25 = v5;
        v5 = 0x140000000uLL;
        switch ( v7 )
        {
          case 0:
            *(_DWORD *)(v8 + 4) = -1;
            goto LABEL_33;
          case 1:
          case 13:
          case 26:
            goto LABEL_7;
          case 2:
            *(_DWORD *)(v8 + 4) = -1073741805;
            goto LABEL_33;
          case 3:
          case 31:
            *(_DWORD *)(v8 + 4) = -1073741806;
            v9 = -1073741823;
            break;
          case 6:
            *(_DWORD *)(v8 + 4) = -1073741820;
            v9 = -1073741823;
            break;
          case 10:
            *(_DWORD *)(v8 + 4) = -1073741803;
            goto LABEL_33;
          case 20:
            *(_DWORD *)(v8 + 4) = -1073741804;
            v9 = -1073741823;
            break;
          case 23:
            *(_DWORD *)(v8 + 4) = -1073545216;
            v9 = -1073741823;
            break;
          case 27:
            *(_DWORD *)(v8 + 4) = -1073610752;
            goto LABEL_33;
          case 34:
            *(_DWORD *)(v8 + 4) = -1073741802;
            goto LABEL_33;
          case 199:
            v29 = -1073741807;
            if ( _bittest64((const signed __int64 *)(*(_QWORD *)(a1 + 40) + 736LL), 0x3Eu) )
              v29 = -1073709056;
            *(_DWORD *)(v8 + 4) = v29;
            goto LABEL_33;
          default:
            LODWORD(v5) = v25;
            *(_DWORD *)(v8 + 4) = -1073741807;
LABEL_33:
            v9 = -1073741823;
            break;
        }
      }
      *(_DWORD *)(v1 + 120) = v9;
    }
    else
    {
      if ( *(_DWORD *)(v1 + 112) == 3 || *(_DWORD *)(v1 + 116) == 3 )
        *(_DWORD *)(v1 + 120) = -1073741536;
      v27 = *(_DWORD *)(v1 + 120);
      switch ( v27 )
      {
        case -1073741810:
          v28 = -1073713152;
          break;
        case -1073741670:
          v28 = -1073737728;
          break;
        case -1073741637:
          v28 = -1073738240;
          break;
        case -1073741536:
          v28 = -1073676288;
          break;
        default:
          v28 = v27 != 0 ? 0x80000300 : 0;
          break;
      }
      *(_DWORD *)(v8 + 4) = v28;
    }
    v10 = *(unsigned int *)(v1 + 108);
    v11 = *(_DWORD *)(v1 + 120);
    *(_DWORD *)(v8 + 36) = v10;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_DDqdDD(
        *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
        *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL),
        v5,
        v6);
    if ( *(_DWORD *)(v1 + 64) == 2 )
    {
      v12 = *(_QWORD **)(v1 + 88);
      *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
      v13 = *(_QWORD **)(a1 + 232);
      if ( *v13 != a1 + 224 )
        __fastfail(3u);
      v12[1] = v13;
      *v12 = a1 + 224;
      *v13 = v12;
      *(_QWORD *)(a1 + 232) = v12;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
      *(_QWORD *)(v1 + 88) = 0;
    }
    else if ( *(_DWORD *)(v1 + 64) == 3 )
    {
      v19 = *(_QWORD *)(v1 + 48);
      if ( *(_BYTE *)(a1 + 288) )
      {
        if ( *(_DWORD *)(v1 + 200) )
        {
          TR_SendCompleteStageRequest(a1);
          SecureDmaEnabler_ReleaseResourcesAfterDma(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 104LL), v1 + 168);
        }
      }
      else if ( *(_QWORD *)(v1 + 96) )
      {
        v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 96LL) + 24LL);
        v21 = KfRaiseIrql(2u);
        v22 = *(unsigned int *)(v19 + 32);
        v23 = v21;
        LOBYTE(v22) = (v22 & 1) == 0;
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v20 + 8) + 96LL))(v20, *(_QWORD *)(v1 + 96), v22);
        KeLowerIrql(v23);
        *(_QWORD *)(v1 + 96) = 0;
      }
      v24 = *(struct _MDL **)(v1 + 72);
      if ( v24 && v24 != *(struct _MDL **)(v19 + 48) && v24 != *(struct _MDL **)(a1 + 120) )
      {
        IoFreeMdl(v24);
        *(_QWORD *)(v1 + 72) = 0;
      }
    }
    *(_BYTE *)(v1 + 16) = 0;
    v16 = KfRaiseIrql(2u);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2104))(
      WdfDriverGlobals,
      *(_QWORD *)(v1 + 24),
      (unsigned int)v11);
    KeLowerIrql(v16);
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
    ++*(_DWORD *)(a1 + 248);
    *(_QWORD *)(a1 + 256) += v10;
    *(_BYTE *)(a1 + 104) = v17;
    if ( v11 < 0 )
      ++*(_DWORD *)(a1 + 252);
    return 0;
  }
  if ( (*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2560))(
         WdfDriverGlobals,
         *(_QWORD *)(a1 + 352),
         0) )
  {
    *(_DWORD *)(v1 + 116) = 0;
    goto LABEL_5;
  }
  v3 = -1073741536;
  *(_DWORD *)(v1 + 116) = 2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v26 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL);
    LOBYTE(v26) = 4;
    WPP_RECORDER_SF_DD(
      *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
      v26,
      14,
      45,
      (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
      *(_BYTE *)(*(_QWORD *)(a1 + 48) + 143LL),
      *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL));
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140026550  push    rbx
0x140026552  push    rbp
0x140026553  push    rsi
0x140026554  push    rdi
0x140026555  push    r12
0x140026557  push    r13
0x140026559  push    r14
0x14002655b  push    r15
0x14002655d  sub     rsp, 68h
0x140026561  mov     rbx, [rcx+168h]
0x140026568  xor     esi, esi
0x14002656a  mov     rbp, rcx
0x14002656d  cmp     dword ptr [rbx+70h], 1
0x140026571  jnz     short loc_14002659E
0x140026573  mov     rax, cs:WdfFunctions_01033
0x14002657a  mov     rdx, [rbx+18h]
0x14002657e  mov     rcx, cs:WdfDriverGlobals
0x140026585  mov     rax, [rax+800h]
0x14002658c  call    _guard_dispatch_icall
0x140026591  mov     edi, eax
0x140026593  test    eax, eax
0x140026595  js      loc_14002663D
0x14002659b  mov     [rbx+70h], esi
0x14002659e  cmp     dword ptr [rbx+74h], 1
0x1400265a2  jz      loc_140026752
0x1400265a8  movzx   edx, byte ptr [rbp+68h]; NewIrql
0x1400265ac  lea     rcx, [rbp+60h]; SpinLock
0x1400265b0  mov     [rbp+168h], rsi
0x1400265b7  call    cs:__imp_KeReleaseSpinLock
0x1400265be  nop     dword ptr [rax+rax+00h]
0x1400265c3  mov     eax, [rbx+7Ch]
0x1400265c6  mov     rdx, [rbx+30h]
0x1400265ca  test    eax, eax
0x1400265cc  jz      loc_140026988
0x1400265d2  cmp     eax, 1Ch
0x1400265d5  jnz     loc_140026873
0x1400265db  mov     [rdx+4], esi; jumptable 0000000140026899 cases 1,13,26
0x1400265de  mov     eax, esi
0x1400265e0  mov     [rbx+78h], eax
0x1400265e3  mov     r15d, [rbx+6Ch]
0x1400265e7  mov     r12d, [rbx+78h]
0x1400265eb  mov     [rdx+24h], r15d
0x1400265ef  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400265f6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400265fd  jnz     loc_14002682E
0x140026603  mov     ecx, [rbx+40h]
0x140026606  sub     ecx, 2
0x140026609  jnz     loc_140026786
0x14002660f  mov     rdi, [rbx+58h]
0x140026613  lea     rcx, [rbp+60h]; SpinLock
0x140026617  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002661e  nop     dword ptr [rax+rax+00h]
0x140026623  mov     [rbp+68h], al
0x140026626  lea     rax, [rbp+0E0h]
0x14002662d  mov     rcx, [rax+8]
0x140026631  cmp     [rcx], rax
0x140026634  jz      short loc_1400266A3
0x140026636  mov     ecx, 3
0x14002663b  int     29h; Win8: RtlFailFast(ecx)
0x14002663d  mov     dword ptr [rbx+70h], 2
0x140026644  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002664b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026652  jz      loc_140026736
0x140026658  mov     rcx, [rbp+38h]
0x14002665c  mov     r9d, 2Ch ; ','
0x140026662  mov     rdx, [rbp+30h]
0x140026666  mov     dword ptr [rsp+0A8h+var_70], edi
0x14002666a  mov     eax, [rcx+98h]
0x140026670  movzx   r8d, byte ptr [rdx+8Fh]
0x140026678  mov     dl, 4
0x14002667a  mov     rcx, [rcx+50h]
0x14002667e  mov     [rsp+0A8h+var_78], eax
0x140026682  lea     rax, WPP_033405c12d5f32917339b215e0870938_Traceguids
0x140026689  mov     [rsp+0A8h+var_80], r8d
0x14002668e  mov     r8d, 0Eh
0x140026694  mov     [rsp+0A8h+var_88], rax
0x140026699  call    WPP_RECORDER_SF_ddL
0x14002669e  jmp     loc_140026736
0x1400266a3  mov     [rdi+8], rcx
0x1400266a7  mov     [rdi], rax
0x1400266aa  mov     [rcx], rdi
0x1400266ad  lea     rcx, [rbp+60h]; SpinLock
0x1400266b1  mov     [rax+8], rdi
0x1400266b5  movzx   edx, byte ptr [rbp+68h]; NewIrql
0x1400266b9  call    cs:__imp_KeReleaseSpinLock
0x1400266c0  nop     dword ptr [rax+rax+00h]
0x1400266c5  mov     [rbx+58h], rsi
0x1400266c9  mov     cl, 2; NewIrql
0x1400266cb  mov     byte ptr [rbx+10h], 0
0x1400266cf  call    cs:__imp_KfRaiseIrql
0x1400266d6  nop     dword ptr [rax+rax+00h]
0x1400266db  mov     r8, cs:WdfFunctions_01033
0x1400266e2  movzx   edi, al
0x1400266e5  mov     rdx, [rbx+18h]
0x1400266e9  mov     rcx, cs:WdfDriverGlobals
0x1400266f0  mov     rax, [r8+838h]
0x1400266f7  mov     r8d, r12d
0x1400266fa  call    _guard_dispatch_icall
0x1400266ff  movzx   ecx, dil; NewIrql
0x140026703  call    cs:__imp_KeLowerIrql
0x14002670a  nop     dword ptr [rax+rax+00h]
0x14002670f  lea     rcx, [rbp+60h]; SpinLock
0x140026713  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002671a  nop     dword ptr [rax+rax+00h]
0x14002671f  inc     dword ptr [rbp+0F8h]
0x140026725  add     [rbp+100h], r15
0x14002672c  mov     [rbp+68h], al
0x14002672f  test    r12d, r12d
0x140026732  js      short loc_14002674A
0x140026734  mov     edi, esi
0x140026736  mov     eax, edi
0x140026738  add     rsp, 68h
0x14002673c  pop     r15
0x14002673e  pop     r14
0x140026740  pop     r13
0x140026742  pop     r12
0x140026744  pop     rdi
0x140026745  pop     rsi
0x140026746  pop     rbp
0x140026747  pop     rbx
0x140026748  retn
0x14002674a  inc     dword ptr [rbp+0FCh]
0x140026750  jmp     short loc_140026734
0x140026752  mov     rax, cs:WdfFunctions_01033
0x140026759  xor     r8d, r8d
0x14002675c  mov     rdx, [rbp+160h]
0x140026763  mov     rcx, cs:WdfDriverGlobals
0x14002676a  mov     rax, [rax+0A00h]
0x140026771  call    _guard_dispatch_icall
0x140026776  test    al, al
0x140026778  jz      loc_140026923
0x14002677e  mov     [rbx+74h], esi
0x140026781  jmp     loc_1400265A8
0x140026786  cmp     ecx, 1
0x140026789  jnz     loc_1400266C9
0x14002678f  mov     r13, [rbx+30h]
0x140026793  cmp     [rbp+120h], sil
0x14002679a  jnz     loc_1400268D2
0x1400267a0  cmp     [rbx+60h], rsi
0x1400267a4  jz      short loc_1400267F8
0x1400267a6  mov     rax, [rbp+28h]
0x1400267aa  mov     rcx, [rax+60h]
0x1400267ae  mov     rdi, [rcx+18h]
0x1400267b2  mov     cl, 2; NewIrql
0x1400267b4  call    cs:__imp_KfRaiseIrql
0x1400267bb  nop     dword ptr [rax+rax+00h]
0x1400267c0  mov     rdx, [rdi+8]
0x1400267c4  mov     rcx, rdi
0x1400267c7  mov     r8d, [r13+20h]
0x1400267cb  movzx   esi, al
0x1400267ce  not     r8b
0x1400267d1  and     r8b, 1
0x1400267d5  mov     rax, [rdx+60h]
0x1400267d9  mov     rdx, [rbx+60h]
0x1400267dd  call    _guard_dispatch_icall
0x1400267e2  movzx   ecx, sil; NewIrql
0x1400267e6  call    cs:__imp_KeLowerIrql
0x1400267ed  nop     dword ptr [rax+rax+00h]
0x1400267f2  xor     esi, esi
0x1400267f4  mov     [rbx+60h], rsi
0x1400267f8  mov     rcx, [rbx+48h]; Mdl
0x1400267fc  test    rcx, rcx
0x1400267ff  jz      loc_1400266C9
0x140026805  cmp     rcx, [r13+30h]
0x140026809  jz      loc_1400266C9
0x14002680f  cmp     rcx, [rbp+78h]
0x140026813  jz      loc_1400266C9
0x140026819  call    cs:__imp_IoFreeMdl
0x140026820  nop     dword ptr [rax+rax+00h]
0x140026825  mov     [rbx+48h], rsi
0x140026829  jmp     loc_1400266C9
0x14002682e  mov     rax, [rbp+30h]
0x140026832  mov     rcx, [rbp+38h]
0x140026836  movzx   edx, byte ptr [rax+8Fh]
0x14002683d  mov     eax, [rbx+68h]
0x140026840  mov     [rsp+0A8h+var_58], eax
0x140026844  mov     rax, [rbx+18h]
0x140026848  mov     [rsp+0A8h+var_60], r15d
0x14002684d  mov     [rsp+0A8h+var_68], r12d
0x140026852  mov     [rsp+0A8h+var_70], rax
0x140026857  mov     eax, [rcx+98h]
0x14002685d  mov     rcx, [rcx+50h]
0x140026861  mov     [rsp+0A8h+var_78], eax
0x140026865  mov     [rsp+0A8h+var_80], edx
0x140026869  call    WPP_RECORDER_SF_DDqdDD
0x14002686e  jmp     loc_140026603
0x140026873  cmp     eax, 0C7h; switch 200 cases
0x140026878  ja      def_140026899; jumptable 0000000140026899 default case, cases 4,5,7-9,11,12,14-19,21,22,24,25,28-30,32,33,35-198
0x14002687e  lea     r8, cs:140000000h
0x140026885  movzx   eax, ds:(byte_1400644D8 - 140000000h)[r8+rax]
0x14002688e  mov     ecx, ds:(jpt_140026899 - 140000000h)[r8+rax*4]
0x140026896  add     rcx, r8
0x140026899  jmp     rcx; switch jump
0x14002689f  mov     dword ptr [rdx+4], 0FFFFFFFFh; jumptable 0000000140026899 case 0
0x1400268a6  mov     eax, 0C0000001h
0x1400268ab  jmp     loc_1400265E0
0x1400268b0  mov     dword ptr [rdx+4], 0C0000014h; jumptable 0000000140026899 case 20
0x1400268b7  mov     eax, 0C0000001h
0x1400268bc  jmp     loc_1400265E0
0x1400268c1  mov     dword ptr [rdx+4], 0C0000004h; jumptable 0000000140026899 case 6
0x1400268c8  mov     eax, 0C0000001h
0x1400268cd  jmp     loc_1400265E0
0x1400268d2  mov     edx, [rbx+0C8h]
0x1400268d8  test    edx, edx
0x1400268da  jz      loc_1400267F8
0x1400268e0  mov     rcx, rbp
0x1400268e3  call    TR_SendCompleteStageRequest
0x1400268e8  mov     rcx, [rbp+28h]
0x1400268ec  lea     rdx, [rbx+0A8h]
0x1400268f3  mov     rcx, [rcx+68h]
0x1400268f7  call    SecureDmaEnabler_ReleaseResourcesAfterDma
0x1400268fc  jmp     loc_1400267F8
0x140026901  mov     dword ptr [rdx+4], 0C0000012h; jumptable 0000000140026899 cases 3,31
0x140026908  mov     eax, 0C0000001h
0x14002690d  jmp     loc_1400265E0
0x140026912  mov     dword ptr [rdx+4], 0C0030000h; jumptable 0000000140026899 case 23
0x140026919  mov     eax, 0C0000001h
0x14002691e  jmp     loc_1400265E0
0x140026923  mov     edi, 0C0000120h
0x140026928  mov     dword ptr [rbx+74h], 2
0x14002692f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140026936  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002693d  jz      loc_140026736
0x140026943  mov     rax, [rbp+30h]
0x140026947  mov     r9d, 2Dh ; '-'
0x14002694d  mov     rcx, [rbp+38h]
0x140026951  mov     r8d, 0Eh
0x140026957  movzx   edx, byte ptr [rax+8Fh]
0x14002695e  mov     eax, [rcx+98h]
0x140026964  mov     rcx, [rcx+50h]
0x140026968  mov     [rsp+0A8h+var_78], eax
0x14002696c  lea     rax, WPP_033405c12d5f32917339b215e0870938_Traceguids
0x140026973  mov     [rsp+0A8h+var_80], edx
0x140026977  mov     dl, 4
0x140026979  mov     [rsp+0A8h+var_88], rax
0x14002697e  call    WPP_RECORDER_SF_DD
0x140026983  jmp     loc_140026736
0x140026988  cmp     dword ptr [rbx+70h], 3
0x14002698c  mov     edi, 0C0000120h
0x140026991  jz      short loc_140026999
0x140026993  cmp     dword ptr [rbx+74h], 3
0x140026997  jnz     short loc_14002699C
0x140026999  mov     [rbx+78h], edi
0x14002699c  mov     eax, [rbx+78h]
0x14002699f  cmp     eax, 0C000000Eh
0x1400269a4  jz      short loc_1400269D8
0x1400269a6  cmp     eax, 0C000009Ah
0x1400269ab  jz      short loc_1400269D1
0x1400269ad  cmp     eax, 0C00000BBh
0x1400269b2  jz      short loc_1400269CA
0x1400269b4  cmp     eax, edi
0x1400269b6  jz      short loc_1400269C3
0x1400269b8  neg     eax
0x1400269ba  sbb     eax, eax
0x1400269bc  and     eax, 80000300h
0x1400269c1  jmp     short loc_1400269DD
0x1400269c3  mov     eax, 0C0010000h
0x1400269c8  jmp     short loc_1400269DD
0x1400269ca  mov     eax, 0C0000E00h
0x1400269cf  jmp     short loc_1400269DD
0x1400269d1  mov     eax, 0C0001000h
0x1400269d6  jmp     short loc_1400269DD
0x1400269d8  mov     eax, 0C0007000h
0x1400269dd  mov     [rdx+4], eax
0x1400269e0  jmp     loc_1400265E3
0x1400269e5  mov     dword ptr [rdx+4], 0C0000013h; jumptable 0000000140026899 case 2
0x1400269ec  jmp     loc_1400268A6
0x1400269f1  mov     dword ptr [rdx+4], 0C0020000h; jumptable 0000000140026899 case 27
0x1400269f8  jmp     loc_1400268A6
0x1400269fd  mov     dword ptr [rdx+4], 0C0000015h; jumptable 0000000140026899 case 10
0x140026a04  jmp     loc_1400268A6
0x140026a09  mov     dword ptr [rdx+4], 0C0000016h; jumptable 0000000140026899 case 34
0x140026a10  jmp     loc_1400268A6
0x140026a15  mov     rax, [rbp+28h]; jumptable 0000000140026899 case 199
0x140026a19  mov     ecx, 0C0008000h
0x140026a1e  bt      qword ptr [rax+2E0h], 3Eh ; '>'
0x140026a27  mov     eax, 0C0000011h
0x140026a2c  cmovb   eax, ecx
0x140026a2f  mov     [rdx+4], eax
0x140026a32  jmp     loc_1400268A6
0x140026a37  mov     dword ptr [rdx+4], 0C0000011h; jumptable 0000000140026899 default case, cases 4,5,7-9,11,12,14-19,21,22,24,25,28-30,32,33,35-198
0x140026a3e  jmp     loc_1400268A6
```
