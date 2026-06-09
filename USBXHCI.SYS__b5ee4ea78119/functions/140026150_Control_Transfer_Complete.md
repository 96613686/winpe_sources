# Control_Transfer_Complete

- ea: `0x140026150`
- end: `0x14002653f`
- name: `Control_Transfer_Complete`
- size: `1007`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14004c0b8`

## callees

- `0x14000d26c`
- `0x14000d2e4`
- `0x140026150`
- `0x140026a50`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140026237`
- `ntoskrnl!KfRaiseIrql` at `0x1400262ff`
- `ntoskrnl!KfRaiseIrql` at `0x140026237`
- `ntoskrnl!KfRaiseIrql` at `0x1400262ff`
- `ntoskrnl!KeLowerIrql` at `0x14002626a`
- `ntoskrnl!KeLowerIrql` at `0x140026339`
- `ntoskrnl!KeLowerIrql` at `0x14002626a`
- `ntoskrnl!KeLowerIrql` at `0x140026339`
- `ntoskrnl!IoFreeMdl` at `0x140026374`
- `ntoskrnl!IoFreeMdl` at `0x140026374`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002616f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026221`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002616f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026221`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400261e5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002627a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400261e5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002627a`

## pseudocode

```c
KIRQL __fastcall Control_Transfer_Complete(__int64 a1, __int64 a2)
{
  unsigned __int64 v4; // r8
  int v5; // r9d
  int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // r15
  int v10; // r13d
  _QWORD *v11; // r12
  _QWORD *v12; // rdi
  _QWORD *v13; // rcx
  KIRQL v14; // bl
  KIRQL result; // al
  __int64 v16; // rax
  __int64 v17; // rdi
  KIRQL v18; // si
  __int64 v19; // r8
  struct _MDL *v20; // rcx
  int v21; // kr00_4
  int v22; // eax
  unsigned int v23; // eax
  int v24; // eax
  __int64 v25; // [rsp+90h] [rbp+8h]

  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
  v6 = *(_DWORD *)(a2 + 124);
  v7 = *(_QWORD *)(a2 + 48);
  if ( v6 )
  {
    if ( v6 == 28 )
    {
LABEL_3:
      *(_DWORD *)(v7 + 4) = 0;
      v8 = 0;
    }
    else
    {
      v21 = v4;
      v4 = 0x140000000uLL;
      switch ( v6 )
      {
        case 0:
          *(_DWORD *)(v7 + 4) = -1;
          goto LABEL_25;
        case 1:
        case 13:
        case 26:
          goto LABEL_3;
        case 2:
          *(_DWORD *)(v7 + 4) = -1073741805;
          goto LABEL_25;
        case 3:
        case 31:
          *(_DWORD *)(v7 + 4) = -1073741806;
          v8 = -1073741823;
          break;
        case 6:
          *(_DWORD *)(v7 + 4) = -1073741820;
          v8 = -1073741823;
          break;
        case 10:
          *(_DWORD *)(v7 + 4) = -1073741803;
          goto LABEL_25;
        case 20:
          *(_DWORD *)(v7 + 4) = -1073741804;
          v8 = -1073741823;
          break;
        case 23:
          *(_DWORD *)(v7 + 4) = -1073545216;
          v8 = -1073741823;
          break;
        case 27:
          *(_DWORD *)(v7 + 4) = -1073610752;
          goto LABEL_25;
        case 34:
          *(_DWORD *)(v7 + 4) = -1073741802;
          goto LABEL_25;
        case 199:
          v24 = -1073741807;
          if ( _bittest64((const signed __int64 *)(*(_QWORD *)(a1 + 40) + 736LL), 0x3Eu) )
            v24 = -1073709056;
          *(_DWORD *)(v7 + 4) = v24;
          goto LABEL_25;
        default:
          LODWORD(v4) = v21;
          *(_DWORD *)(v7 + 4) = -1073741807;
LABEL_25:
          v8 = -1073741823;
          break;
      }
    }
    *(_DWORD *)(a2 + 120) = v8;
  }
  else
  {
    if ( *(_DWORD *)(a2 + 112) == 3 || *(_DWORD *)(a2 + 116) == 3 )
      *(_DWORD *)(a2 + 120) = -1073741536;
    v22 = *(_DWORD *)(a2 + 120);
    switch ( v22 )
    {
      case -1073741810:
        v23 = -1073713152;
        break;
      case -1073741670:
        v23 = -1073737728;
        break;
      case -1073741637:
        v23 = -1073738240;
        break;
      case -1073741536:
        v23 = -1073676288;
        break;
      default:
        v23 = v22 != 0 ? 0x80000300 : 0;
        break;
    }
    *(_DWORD *)(v7 + 4) = v23;
  }
  v9 = *(unsigned int *)(a2 + 108);
  v10 = *(_DWORD *)(a2 + 120);
  *(_DWORD *)(v7 + 36) = v9;
  v11 = (_QWORD *)(a2 + 24);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_DDqdDD(
      *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
      *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL),
      v4,
      v5);
  if ( *(_DWORD *)(a2 + 64) == 2 )
  {
    v12 = *(_QWORD **)(a2 + 88);
    *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
    v13 = *(_QWORD **)(a1 + 232);
    if ( *v13 != a1 + 224 )
      __fastfail(3u);
    v12[1] = v13;
    *v12 = a1 + 224;
    *v13 = v12;
    *(_QWORD *)(a1 + 232) = v12;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
    *(_QWORD *)(a2 + 88) = 0;
    goto LABEL_11;
  }
  if ( *(_DWORD *)(a2 + 64) != 3 )
    goto LABEL_11;
  v16 = *(_QWORD *)(a2 + 48);
  v25 = v16;
  if ( *(_BYTE *)(a1 + 288) )
  {
    if ( !*(_DWORD *)(a2 + 200) )
      goto LABEL_19;
    TR_SendCompleteStageRequest(a1);
    SecureDmaEnabler_ReleaseResourcesAfterDma(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 104LL), a2 + 168);
    v11 = (_QWORD *)(a2 + 24);
    goto LABEL_18;
  }
  if ( *(_QWORD *)(a2 + 96) )
  {
    v17 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 96LL) + 24LL);
    v18 = KfRaiseIrql(2u);
    v19 = *(unsigned int *)(v25 + 32);
    LOBYTE(v19) = (v19 & 1) == 0;
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v17 + 8) + 96LL))(v17, *(_QWORD *)(a2 + 96), v19);
    KeLowerIrql(v18);
    *(_QWORD *)(a2 + 96) = 0;
LABEL_18:
    v16 = v25;
  }
LABEL_19:
  v20 = *(struct _MDL **)(a2 + 72);
  if ( v20 && v20 != *(struct _MDL **)(v16 + 48) && v20 != *(struct _MDL **)(a1 + 120) )
  {
    IoFreeMdl(v20);
    *(_QWORD *)(a2 + 72) = 0;
  }
LABEL_11:
  *(_BYTE *)(a2 + 16) = 0;
  v14 = KfRaiseIrql(2u);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2104))(
    WdfDriverGlobals,
    *v11,
    (unsigned int)v10);
  KeLowerIrql(v14);
  result = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  ++*(_DWORD *)(a1 + 248);
  *(_QWORD *)(a1 + 256) += v9;
  *(_BYTE *)(a1 + 104) = result;
  if ( v10 < 0 )
    ++*(_DWORD *)(a1 + 252);
  return result;
}

```

## disassembly

```asm
0x140026150  mov     [rsp+arg_18], rbx
0x140026155  push    rbp
0x140026156  push    rsi
0x140026157  push    r13
0x140026159  push    r14
0x14002615b  push    r15
0x14002615d  sub     rsp, 60h
0x140026161  mov     rbx, rdx
0x140026164  mov     rbp, rcx
0x140026167  movzx   edx, byte ptr [rcx+68h]; NewIrql
0x14002616b  add     rcx, 60h ; '`'; SpinLock
0x14002616f  call    cs:__imp_KeReleaseSpinLock
0x140026176  nop     dword ptr [rax+rax+00h]
0x14002617b  mov     eax, [rbx+7Ch]
0x14002617e  xor     esi, esi
0x140026180  mov     rdx, [rbx+30h]
0x140026184  test    eax, eax
0x140026186  jz      loc_140026482
0x14002618c  cmp     eax, 1Ch
0x14002618f  jnz     loc_1400263CE
0x140026195  mov     [rdx+4], esi; jumptable 00000001400263F4 cases 1,13,26
0x140026198  mov     eax, esi
0x14002619a  mov     [rbx+78h], eax
0x14002619d  mov     r15d, [rbx+6Ch]
0x1400261a1  mov     r13d, [rbx+78h]
0x1400261a5  mov     [rdx+24h], r15d
0x1400261a9  mov     [rsp+88h+arg_10], r12
0x1400261b1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400261b8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400261bf  lea     r12, [rbx+18h]
0x1400261c3  jnz     loc_140026389
0x1400261c9  mov     ecx, [rbx+40h]
0x1400261cc  mov     [rsp+88h+arg_8], rdi
0x1400261d4  sub     ecx, 2
0x1400261d7  jnz     loc_1400262C9
0x1400261dd  mov     rdi, [rbx+58h]
0x1400261e1  lea     rcx, [rbp+60h]; SpinLock
0x1400261e5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400261ec  nop     dword ptr [rax+rax+00h]
0x1400261f1  mov     [rbp+68h], al
0x1400261f4  lea     rax, [rbp+0E0h]
0x1400261fb  mov     rcx, [rax+8]
0x1400261ff  cmp     [rcx], rax
0x140026202  jz      short loc_14002620B
0x140026204  mov     ecx, 3
0x140026209  int     29h; Win8: RtlFailFast(ecx)
0x14002620b  mov     [rdi+8], rcx
0x14002620f  mov     [rdi], rax
0x140026212  mov     [rcx], rdi
0x140026215  lea     rcx, [rbp+60h]; SpinLock
0x140026219  mov     [rax+8], rdi
0x14002621d  movzx   edx, byte ptr [rbp+68h]; NewIrql
0x140026221  call    cs:__imp_KeReleaseSpinLock
0x140026228  nop     dword ptr [rax+rax+00h]
0x14002622d  mov     [rbx+58h], rsi
0x140026231  mov     cl, 2; NewIrql
0x140026233  mov     byte ptr [rbx+10h], 0
0x140026237  call    cs:__imp_KfRaiseIrql
0x14002623e  nop     dword ptr [rax+rax+00h]
0x140026243  mov     r8, cs:WdfFunctions_01033
0x14002624a  movzx   ebx, al
0x14002624d  mov     rdx, [r12]
0x140026251  mov     rcx, cs:WdfDriverGlobals
0x140026258  mov     rax, [r8+838h]
0x14002625f  mov     r8d, r13d
0x140026262  call    _guard_dispatch_icall
0x140026267  movzx   ecx, bl; NewIrql
0x14002626a  call    cs:__imp_KeLowerIrql
0x140026271  nop     dword ptr [rax+rax+00h]
0x140026276  lea     rcx, [rbp+60h]; SpinLock
0x14002627a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140026281  nop     dword ptr [rax+rax+00h]
0x140026286  inc     dword ptr [rbp+0F8h]
0x14002628c  add     [rbp+100h], r15
0x140026293  mov     [rbp+68h], al
0x140026296  test    r13d, r13d
0x140026299  js      short loc_1400262C1
0x14002629b  mov     r12, [rsp+88h+arg_10]
0x1400262a3  mov     rdi, [rsp+88h+arg_8]
0x1400262ab  mov     rbx, [rsp+88h+arg_18]
0x1400262b3  add     rsp, 60h
0x1400262b7  pop     r15
0x1400262b9  pop     r14
0x1400262bb  pop     r13
0x1400262bd  pop     rsi
0x1400262be  pop     rbp
0x1400262bf  retn
0x1400262c1  inc     dword ptr [rbp+0FCh]
0x1400262c7  jmp     short loc_14002629B
0x1400262c9  cmp     ecx, 1
0x1400262cc  jnz     loc_140026231
0x1400262d2  mov     rax, [rbx+30h]
0x1400262d6  mov     [rsp+88h+arg_0], rax
0x1400262de  cmp     [rbp+120h], sil
0x1400262e5  jnz     loc_14002642D
0x1400262eb  cmp     [rbx+60h], rsi
0x1400262ef  jz      short loc_140026353
0x1400262f1  mov     rax, [rbp+28h]
0x1400262f5  mov     rcx, [rax+60h]
0x1400262f9  mov     rdi, [rcx+18h]
0x1400262fd  mov     cl, 2; NewIrql
0x1400262ff  call    cs:__imp_KfRaiseIrql
0x140026306  nop     dword ptr [rax+rax+00h]
0x14002630b  mov     rdx, [rdi+8]
0x14002630f  mov     rcx, rdi
0x140026312  mov     r8, [rsp+88h+arg_0]
0x14002631a  movzx   esi, al
0x14002631d  mov     rax, [rdx+60h]
0x140026321  mov     r8d, [r8+20h]
0x140026325  mov     rdx, [rbx+60h]
0x140026329  not     r8b
0x14002632c  and     r8b, 1
0x140026330  call    _guard_dispatch_icall
0x140026335  movzx   ecx, sil; NewIrql
0x140026339  call    cs:__imp_KeLowerIrql
0x140026340  nop     dword ptr [rax+rax+00h]
0x140026345  xor     esi, esi
0x140026347  mov     [rbx+60h], rsi
0x14002634b  mov     rax, [rsp+88h+arg_0]
0x140026353  mov     rcx, [rbx+48h]; Mdl
0x140026357  test    rcx, rcx
0x14002635a  jz      loc_140026231
0x140026360  cmp     rcx, [rax+30h]
0x140026364  jz      loc_140026231
0x14002636a  cmp     rcx, [rbp+78h]
0x14002636e  jz      loc_140026231
0x140026374  call    cs:__imp_IoFreeMdl
0x14002637b  nop     dword ptr [rax+rax+00h]
0x140026380  mov     [rbx+48h], rsi
0x140026384  jmp     loc_140026231
0x140026389  mov     rax, [rbp+30h]
0x14002638d  mov     rcx, [rbp+38h]
0x140026391  movzx   edx, byte ptr [rax+8Fh]
0x140026398  mov     eax, [rbx+68h]
0x14002639b  mov     [rsp+88h+var_38], eax
0x14002639f  mov     rax, [r12]
0x1400263a3  mov     [rsp+88h+var_40], r15d
0x1400263a8  mov     [rsp+88h+var_48], r13d
0x1400263ad  mov     [rsp+88h+var_50], rax
0x1400263b2  mov     eax, [rcx+98h]
0x1400263b8  mov     rcx, [rcx+50h]
0x1400263bc  mov     [rsp+88h+var_58], eax
0x1400263c0  mov     [rsp+88h+var_60], edx
0x1400263c4  call    WPP_RECORDER_SF_DDqdDD
0x1400263c9  jmp     loc_1400261C9
0x1400263ce  cmp     eax, 0C7h; switch 200 cases
0x1400263d3  ja      def_1400263F4; jumptable 00000001400263F4 default case, cases 4,5,7-9,11,12,14-19,21,22,24,25,28-30,32,33,35-198
0x1400263d9  lea     r8, cs:140000000h
0x1400263e0  movzx   eax, ds:(byte_1400645D4 - 140000000h)[r8+rax]
0x1400263e9  mov     ecx, ds:(jpt_1400263F4 - 140000000h)[r8+rax*4]
0x1400263f1  add     rcx, r8
0x1400263f4  jmp     rcx; switch jump
0x1400263fa  mov     dword ptr [rdx+4], 0FFFFFFFFh; jumptable 00000001400263F4 case 0
0x140026401  mov     eax, 0C0000001h
0x140026406  jmp     loc_14002619A
0x14002640b  mov     dword ptr [rdx+4], 0C0000014h; jumptable 00000001400263F4 case 20
0x140026412  mov     eax, 0C0000001h
0x140026417  jmp     loc_14002619A
0x14002641c  mov     dword ptr [rdx+4], 0C0000004h; jumptable 00000001400263F4 case 6
0x140026423  mov     eax, 0C0000001h
0x140026428  jmp     loc_14002619A
0x14002642d  mov     edx, [rbx+0C8h]
0x140026433  test    edx, edx
0x140026435  jz      loc_140026353
0x14002643b  mov     rcx, rbp
0x14002643e  call    TR_SendCompleteStageRequest
0x140026443  mov     rcx, [rbp+28h]
0x140026447  lea     rdx, [rbx+0A8h]
0x14002644e  mov     rcx, [rcx+68h]
0x140026452  call    SecureDmaEnabler_ReleaseResourcesAfterDma
0x140026457  lea     r12, [rbx+18h]
0x14002645b  jmp     loc_14002634B
0x140026460  mov     dword ptr [rdx+4], 0C0000012h; jumptable 00000001400263F4 cases 3,31
0x140026467  mov     eax, 0C0000001h
0x14002646c  jmp     loc_14002619A
0x140026471  mov     dword ptr [rdx+4], 0C0030000h; jumptable 00000001400263F4 case 23
0x140026478  mov     eax, 0C0000001h
0x14002647d  jmp     loc_14002619A
0x140026482  cmp     dword ptr [rbx+70h], 3
0x140026486  jz      short loc_14002648E
0x140026488  cmp     dword ptr [rbx+74h], 3
0x14002648c  jnz     short loc_140026495
0x14002648e  mov     dword ptr [rbx+78h], 0C0000120h
0x140026495  mov     eax, [rbx+78h]
0x140026498  cmp     eax, 0C000000Eh
0x14002649d  jz      short loc_1400264D4
0x14002649f  cmp     eax, 0C000009Ah
0x1400264a4  jz      short loc_1400264CD
0x1400264a6  cmp     eax, 0C00000BBh
0x1400264ab  jz      short loc_1400264C6
0x1400264ad  cmp     eax, 0C0000120h
0x1400264b2  jz      short loc_1400264BF
0x1400264b4  neg     eax
0x1400264b6  sbb     eax, eax
0x1400264b8  and     eax, 80000300h
0x1400264bd  jmp     short loc_1400264D9
0x1400264bf  mov     eax, 0C0010000h
0x1400264c4  jmp     short loc_1400264D9
0x1400264c6  mov     eax, 0C0000E00h
0x1400264cb  jmp     short loc_1400264D9
0x1400264cd  mov     eax, 0C0001000h
0x1400264d2  jmp     short loc_1400264D9
0x1400264d4  mov     eax, 0C0007000h
0x1400264d9  mov     [rdx+4], eax
0x1400264dc  jmp     loc_14002619D
0x1400264e1  mov     dword ptr [rdx+4], 0C0000013h; jumptable 00000001400263F4 case 2
0x1400264e8  jmp     loc_140026401
0x1400264ed  mov     dword ptr [rdx+4], 0C0020000h; jumptable 00000001400263F4 case 27
0x1400264f4  jmp     loc_140026401
0x1400264f9  mov     dword ptr [rdx+4], 0C0000015h; jumptable 00000001400263F4 case 10
0x140026500  jmp     loc_140026401
0x140026505  mov     dword ptr [rdx+4], 0C0000016h; jumptable 00000001400263F4 case 34
0x14002650c  jmp     loc_140026401
0x140026511  mov     rax, [rbp+28h]; jumptable 00000001400263F4 case 199
0x140026515  mov     ecx, 0C0008000h
0x14002651a  bt      qword ptr [rax+2E0h], 3Eh ; '>'
0x140026523  mov     eax, 0C0000011h
0x140026528  cmovb   eax, ecx
0x14002652b  mov     [rdx+4], eax
0x14002652e  jmp     loc_140026401
0x140026533  mov     dword ptr [rdx+4], 0C0000011h; jumptable 00000001400263F4 default case, cases 4,5,7-9,11,12,14-19,21,22,24,25,28-30,32,33,35-198
0x14002653a  jmp     loc_140026401
```
