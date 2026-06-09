# CPcmPin::GetAudioPresentationPosition(_IRP *,KSIDENTIFIER const *,KSAUDIO_PRESENTATION_POSITION *)

- ea: `0x140003600`
- end: `0x140003a0d`
- name: `?GetAudioPresentationPosition@CPcmPin@@SAJPEAU_IRP@@PEBUKSIDENTIFIER@@PEAUKSAUDIO_PRESENTATION_POSITION@@@Z`
- size: `1037`
- prototype: `__int64 __fastcall(struct _IRP *, const struct KSIDENTIFIER *, struct KSAUDIO_PRESENTATION_POSITION *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140003600`
- `0x140005060`
- `0x14003b4ec`
- `0x14005c870`
- `0x140089850`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400036e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400036e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003657`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003671`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003710`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000385a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003657`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003671`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003710`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000385a`
- `HAL!KeQueryPerformanceCounter` at `0x140003636`
- `HAL!KeQueryPerformanceCounter` at `0x140003636`
- `ks!KsGetPinFromIrp` at `0x14000361d`
- `ks!KsGetPinFromIrp` at `0x14000361d`

## pseudocode

```c
__int64 __fastcall CPcmPin::GetAudioPresentationPosition(
        struct _IRP *a1,
        const struct KSIDENTIFIER *a2,
        struct KSAUDIO_PRESENTATION_POSITION *a3)
{
  char *Context; // rsi
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v6; // rdi
  UINT64 QuadPart; // rbx
  KSPIN_LOCK *v8; // r13
  KIRQL v9; // al
  KSPIN_LOCK *v10; // rdi
  KSPIN_LOCK *v11; // r14
  KIRQL v12; // al
  KSPIN_LOCK v13; // r15
  volatile signed __int32 *v14; // rdi
  KSPIN_LOCK *v15; // rdi
  KSPIN_LOCK *v16; // r15
  KIRQL v17; // al
  __int64 v18; // rdx
  __int64 v19; // r8
  KSPIN_LOCK v20; // r13
  volatile signed __int32 *v21; // rdi
  UINT64 v22; // rsi
  __int64 v23; // r9
  int v25; // eax
  KSPIN_LOCK *v26; // r13
  int v27; // r15d
  KIRQL v28; // al
  __int64 v29; // rdx
  KIRQL v30; // r10
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // rcx
  __int64 v34; // rax
  KSPIN_LOCK *v35; // [rsp+70h] [rbp-10h] BYREF
  KIRQL v36; // [rsp+78h] [rbp-8h]
  KIRQL v37; // [rsp+D0h] [rbp+50h]
  int AdditionalPresentationDelayMs; // [rsp+D0h] [rbp+50h]
  unsigned int v39; // [rsp+D8h] [rbp+58h]

  Context = (char *)KsGetPinFromIrp(a1)->Context;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v6 = *((_QWORD *)Context + 4);
  QuadPart = PerformanceCounter.QuadPart;
  v39 = 0;
  v8 = (KSPIN_LOCK *)(v6 + 696);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 696));
  v10 = *(KSPIN_LOCK **)(v6 + 8);
  v37 = v9;
  v11 = v10 + 12;
  v12 = KeAcquireSpinLockRaiseToDpc(v10 + 12);
  v13 = v10[14];
  v14 = (volatile signed __int32 *)v10[15];
  if ( v14 )
    _InterlockedIncrement(v14 + 2);
  if ( v11 )
  {
    v36 = v12;
    v35 = v11;
    wil::details::kspin_lock_saved_irql::Release((const struct wil::details::kspin_lock_saved_irql *)&v35);
  }
  if ( v13 )
    v39 = *(unsigned __int16 *)(v13 + 10) / 0xAu;
  if ( v14 )
  {
    if ( *((_QWORD *)v14 + 1) == 0x100000001LL )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
LABEL_43:
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      goto LABEL_10;
    }
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( *((_DWORD *)v14 + 3) == 1 || _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        goto LABEL_43;
    }
  }
LABEL_10:
  KeReleaseSpinLock(v8, v37);
  AdditionalPresentationDelayMs = CPcmPin::GetAdditionalPresentationDelayMs((CPcmPin *)Context);
  v15 = *(KSPIN_LOCK **)(*((_QWORD *)Context + 4) + 8LL);
  v16 = v15 + 12;
  v17 = KeAcquireSpinLockRaiseToDpc(v15 + 12);
  v20 = v15[14];
  v21 = (volatile signed __int32 *)v15[15];
  if ( v21 )
    _InterlockedIncrement(v21 + 2);
  if ( v16 )
  {
    v36 = v17;
    v35 = v16;
    wil::details::kspin_lock_saved_irql::Release((const struct wil::details::kspin_lock_saved_irql *)&v35);
  }
  if ( !v20 )
  {
    v22 = 0;
LABEL_16:
    v23 = v39;
    goto LABEL_17;
  }
  v25 = (*(__int64 (__fastcall **)(KSPIN_LOCK))(*(_QWORD *)v20 + 104LL))(v20);
  v26 = (KSPIN_LOCK *)(Context + 80);
  v27 = 2 * v25;
  v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 10);
  v29 = *((_QWORD *)Context + 13);
  v30 = v28;
  v31 = *((_QWORD *)Context + 18);
  if ( v29 )
    v31 = *((_QWORD *)Context + 12) + (__int64)((QuadPart - v29) * *((int *)Context + 13)) / *((_QWORD *)Context + 14);
  v32 = *((_QWORD *)Context + 7);
  v33 = 0;
  if ( v31 > 0 )
    v33 = v31;
  if ( v33 < v32 )
    v32 = v33;
  if ( v32 <= *((_QWORD *)Context + 18) )
    v32 = *((_QWORD *)Context + 18);
  v23 = v39;
  *((_QWORD *)Context + 18) = v32;
  v19 = v32 - *((_DWORD *)Context + 13) * (AdditionalPresentationDelayMs + v39) / 0x3E8;
  v34 = 0;
  if ( v19 >= 0 )
    v34 = v19;
  v18 = v34 % v27;
  v22 = v34 / v27;
  if ( v26 )
  {
    v35 = v26;
    v36 = v30;
    wil::details::kspin_lock_saved_irql::Release((const struct wil::details::kspin_lock_saved_irql *)&v35);
    goto LABEL_16;
  }
LABEL_17:
  LOBYTE(v18) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
  LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
             && LOWORD(WPP_GLOBAL_Control->DeviceType);
  if ( (_BYTE)v18 || (_BYTE)v19 )
    WPP_RECORDER_AND_TRACE_SF_IiDd(WPP_GLOBAL_Control->AttachedDevice, v18, v19, WPP_GLOBAL_Control->DeviceExtension);
  a3->u64PositionInBlocks = v22;
  a3->u64QPCPosition = QuadPart;
  if ( v21 )
  {
    if ( *((_QWORD *)v21 + 1) == 0x100000001LL )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64, __int64))v21)(v21, v18, v19, v23);
LABEL_41:
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      return 0;
    }
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64, __int64))v21)(v21, v18, v19, v23);
      if ( *((_DWORD *)v21 + 3) == 1 || _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        goto LABEL_41;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140003600  mov     [rsp-38h+arg_0], rbx
0x140003605  push    rbp
0x140003606  push    rsi
0x140003607  push    rdi
0x140003608  push    r12
0x14000360a  push    r13
0x14000360c  push    r14
0x14000360e  push    r15
0x140003610  mov     rbp, rsp
0x140003613  sub     rsp, 80h
0x14000361a  mov     r12, r8
0x14000361d  call    cs:__imp_KsGetPinFromIrp
0x140003624  nop     dword ptr [rax+rax+00h]
0x140003629  xor     r14d, r14d
0x14000362c  xor     ecx, ecx; PerformanceFrequency
0x14000362e  mov     [rbp+var_20], r14
0x140003632  mov     rsi, [rax+10h]
0x140003636  call    cs:__imp_KeQueryPerformanceCounter
0x14000363d  nop     dword ptr [rax+rax+00h]
0x140003642  mov     rdi, [rsi+20h]
0x140003646  mov     rbx, rax
0x140003649  mov     [rbp+arg_18], r14d
0x14000364d  lea     r13, [rdi+2B8h]
0x140003654  mov     rcx, r13; SpinLock
0x140003657  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000365e  nop     dword ptr [rax+rax+00h]
0x140003663  mov     rdi, [rdi+8]
0x140003667  mov     byte ptr [rbp+arg_10], al
0x14000366a  lea     r14, [rdi+60h]
0x14000366e  mov     rcx, r14; SpinLock
0x140003671  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003678  nop     dword ptr [rax+rax+00h]
0x14000367d  mov     r15, [rdi+70h]
0x140003681  mov     rdi, [rdi+78h]
0x140003685  test    rdi, rdi
0x140003688  jz      short loc_14000368E
0x14000368a  lock inc dword ptr [rdi+8]
0x14000368e  test    r14, r14
0x140003691  jnz     loc_1400037E9
0x140003697  test    r15, r15
0x14000369a  jz      short loc_1400036AF
0x14000369c  movzx   ecx, word ptr [r15+0Ah]
0x1400036a1  mov     eax, 0CCCCCCCDh
0x1400036a6  mul     ecx
0x1400036a8  nop
0x1400036a9  shr     edx, 3
0x1400036ac  mov     [rbp+arg_18], edx
0x1400036af  mov     rcx, 100000001h
0x1400036b9  mov     r14d, 0FFFFFFFFh
0x1400036bf  test    rdi, rdi
0x1400036c2  jz      short loc_1400036E2
0x1400036c4  mov     rax, [rdi+8]
0x1400036c8  cmp     rax, rcx
0x1400036cb  jz      loc_140003989
0x1400036d1  mov     eax, r14d
0x1400036d4  lock xadd [rdi+8], eax
0x1400036d9  cmp     eax, 1
0x1400036dc  jz      loc_14000394C
0x1400036e2  movzx   edx, byte ptr [rbp+arg_10]; NewIrql
0x1400036e6  mov     rcx, r13; SpinLock
0x1400036e9  call    cs:__imp_KeReleaseSpinLock
0x1400036f0  nop     dword ptr [rax+rax+00h]
0x1400036f5  mov     rcx, rsi; this
0x1400036f8  call    ?GetAdditionalPresentationDelayMs@CPcmPin@@AEAAFXZ; CPcmPin::GetAdditionalPresentationDelayMs(void)
0x1400036fd  cwde
0x1400036fe  mov     [rbp+arg_10], eax
0x140003701  mov     rax, [rsi+20h]
0x140003705  mov     rdi, [rax+8]
0x140003709  lea     r15, [rdi+60h]
0x14000370d  mov     rcx, r15; SpinLock
0x140003710  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003717  nop     dword ptr [rax+rax+00h]
0x14000371c  mov     r13, [rdi+70h]
0x140003720  mov     rdi, [rdi+78h]
0x140003724  test    rdi, rdi
0x140003727  jz      short loc_14000372D
0x140003729  lock inc dword ptr [rdi+8]
0x14000372d  test    r15, r15
0x140003730  jnz     loc_140003813
0x140003736  test    r13, r13
0x140003739  jnz     loc_14000383D
0x14000373f  mov     rsi, [rbp+var_20]
0x140003743  mov     r11d, [rbp+arg_10]
0x140003747  mov     r9d, [rbp+arg_18]
0x14000374b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003752  lea     rax, WPP_GLOBAL_Control
0x140003759  cmp     rcx, rax
0x14000375c  jz      short loc_14000376B
0x14000375e  test    dword ptr [rcx+2Ch], 2000h
0x140003765  jnz     loc_1400039AD
0x14000376b  xor     dl, dl
0x14000376d  lea     rax, WPP_RECORDER_INITIALIZED
0x140003774  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000377b  jnz     loc_140003976
0x140003781  xor     r8b, r8b
0x140003784  test    dl, dl
0x140003786  jnz     loc_1400039BE
0x14000378c  test    r8b, r8b
0x14000378f  jnz     loc_1400039BE
0x140003795  mov     [r12], rsi
0x140003799  mov     [r12+8], rbx
0x14000379e  test    rdi, rdi
0x1400037a1  jz      short loc_1400037CB
0x1400037a3  mov     rax, [rdi+8]
0x1400037a7  mov     rcx, 100000001h
0x1400037b1  cmp     rax, rcx
0x1400037b4  jz      loc_1400039E4
0x1400037ba  mov     eax, r14d
0x1400037bd  lock xadd [rdi+8], eax
0x1400037c2  cmp     eax, 1
0x1400037c5  jz      loc_14000391E
0x1400037cb  mov     rbx, [rsp+80h+arg_0]
0x1400037d3  xor     eax, eax
0x1400037d5  add     rsp, 80h
0x1400037dc  pop     r15
0x1400037de  pop     r14
0x1400037e0  pop     r13
0x1400037e2  pop     r12
0x1400037e4  pop     rdi
0x1400037e5  pop     rsi
0x1400037e6  pop     rbp
0x1400037e7  retn
0x1400037e9  mov     [rbp+var_8], al
0x1400037ec  lea     rcx, [rbp+var_10]; struct wil::details::kspin_lock_saved_irql *
0x1400037f0  mov     eax, [rbp+var_7]
0x1400037f3  mov     [rbp+var_7], eax
0x1400037f6  movzx   eax, [rbp+var_3]
0x1400037fa  mov     [rbp+var_3], ax
0x1400037fe  movzx   eax, [rbp+var_1]
0x140003802  mov     [rbp+var_1], al
0x140003805  mov     [rbp+var_10], r14
0x140003809  call    ?Release@kspin_lock_saved_irql@details@wil@@SAXAEBU123@@Z; wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &)
0x14000380e  jmp     loc_140003697
0x140003813  mov     [rbp+var_8], al
0x140003816  lea     rcx, [rbp+var_10]; struct wil::details::kspin_lock_saved_irql *
0x14000381a  mov     eax, [rbp+var_7]
0x14000381d  mov     [rbp+var_7], eax
0x140003820  movzx   eax, [rbp+var_3]
0x140003824  mov     [rbp+var_3], ax
0x140003828  movzx   eax, [rbp+var_1]
0x14000382c  mov     [rbp+var_1], al
0x14000382f  mov     [rbp+var_10], r15
0x140003833  call    ?Release@kspin_lock_saved_irql@details@wil@@SAXAEBU123@@Z; wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &)
0x140003838  jmp     loc_140003736
0x14000383d  mov     rax, [r13+0]
0x140003841  mov     rcx, r13
0x140003844  mov     rax, [rax+68h]
0x140003848  call    _guard_dispatch_icall
0x14000384d  mov     r15d, eax
0x140003850  lea     r13, [rsi+50h]
0x140003854  mov     rcx, r13; SpinLock
0x140003857  add     r15d, r15d
0x14000385a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003861  nop     dword ptr [rax+rax+00h]
0x140003866  mov     rdx, [rsi+68h]
0x14000386a  movzx   r10d, al
0x14000386e  mov     r9, [rsi+90h]
0x140003875  mov     rax, r9
0x140003878  test    rdx, rdx
0x14000387b  jz      short loc_140003895
0x14000387d  movsxd  rax, dword ptr [rsi+34h]
0x140003881  mov     rcx, rbx
0x140003884  sub     rcx, rdx
0x140003887  imul    rax, rcx
0x14000388b  cqo
0x14000388d  idiv    qword ptr [rsi+70h]
0x140003891  add     rax, [rsi+60h]
0x140003895  mov     r8, [rsi+38h]
0x140003899  xor     ecx, ecx
0x14000389b  mov     r11d, [rbp+arg_10]
0x14000389f  test    rax, rax
0x1400038a2  cmovg   rcx, rax
0x1400038a6  mov     eax, 10624DD3h
0x1400038ab  cmp     rcx, r8
0x1400038ae  cmovl   r8, rcx
0x1400038b2  cmp     r8, r9
0x1400038b5  cmovle  r8, r9
0x1400038b9  mov     r9d, [rbp+arg_18]
0x1400038bd  mov     [rsi+90h], r8
0x1400038c4  lea     ecx, [r11+r9]
0x1400038c8  imul    ecx, [rsi+34h]
0x1400038cc  mul     ecx
0x1400038ce  movsxd  rcx, r15d
0x1400038d1  shr     edx, 6
0x1400038d4  mov     eax, edx
0x1400038d6  sub     r8, rax
0x1400038d9  mov     eax, 0
0x1400038de  cmovns  rax, r8
0x1400038e2  cqo
0x1400038e4  idiv    rcx
0x1400038e7  mov     rsi, rax
0x1400038ea  test    r13, r13
0x1400038ed  jz      loc_14000374B
0x1400038f3  mov     ecx, [rbp+var_7]
0x1400038f6  mov     [rbp+var_7], ecx
0x1400038f9  movzx   ecx, [rbp+var_3]
0x1400038fd  mov     [rbp+var_3], cx
0x140003901  movzx   ecx, [rbp+var_1]
0x140003905  mov     [rbp+var_1], cl
0x140003908  lea     rcx, [rbp+var_10]; struct wil::details::kspin_lock_saved_irql *
0x14000390c  mov     [rbp+var_10], r13
0x140003910  mov     [rbp+var_8], r10b
0x140003914  call    ?Release@kspin_lock_saved_irql@details@wil@@SAXAEBU123@@Z; wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &)
0x140003919  jmp     loc_140003743
0x14000391e  mov     rax, [rdi]
0x140003921  mov     rcx, rdi
0x140003924  mov     rax, [rax]
0x140003927  call    _guard_dispatch_icall
0x14000392c  mov     eax, [rdi+0Ch]
0x14000392f  cmp     eax, 1
0x140003932  jnz     loc_1400039F7
0x140003938  mov     rax, [rdi]
0x14000393b  mov     rcx, rdi
0x14000393e  mov     rax, [rax+8]
0x140003942  call    _guard_dispatch_icall
0x140003947  jmp     loc_1400037CB
0x14000394c  mov     rax, [rdi]
0x14000394f  mov     rcx, rdi
0x140003952  mov     rax, [rax]
0x140003955  call    _guard_dispatch_icall
0x14000395a  mov     eax, [rdi+0Ch]
0x14000395d  cmp     eax, 1
0x140003960  jnz     short loc_140003999
0x140003962  mov     rax, [rdi]
0x140003965  mov     rcx, rdi
0x140003968  mov     rax, [rax+8]
0x14000396c  call    _guard_dispatch_icall
0x140003971  jmp     loc_1400036E2
0x140003976  cmp     word ptr [rcx+48h], 0
0x14000397b  jz      loc_140003781
0x140003981  mov     r8b, 1
0x140003984  jmp     loc_140003784
0x140003989  mov     rax, [rdi]
0x14000398c  mov     rcx, rdi
0x14000398f  mov     rax, [rax]
0x140003992  call    _guard_dispatch_icall
0x140003997  jmp     short loc_140003962
0x140003999  nop
0x14000399a  mov     eax, r14d
0x14000399d  lock xadd [rdi+0Ch], eax
0x1400039a2  cmp     eax, 1
0x1400039a5  jnz     loc_1400036E2
0x1400039ab  jmp     short loc_140003962
0x1400039ad  cmp     byte ptr [rcx+29h], 5
0x1400039b1  jb      loc_14000376B
0x1400039b7  mov     dl, 1
0x1400039b9  jmp     loc_14000376D
0x1400039be  mov     [rsp+80h+var_28], r11d
0x1400039c3  mov     [rsp+80h+var_30], r9d
0x1400039c8  mov     r9, [rcx+40h]
0x1400039cc  mov     rcx, [rcx+18h]
0x1400039d0  mov     [rsp+80h+var_38], rbx
0x1400039d5  mov     [rsp+80h+var_40], rsi
0x1400039da  call    WPP_RECORDER_AND_TRACE_SF_IiDd
0x1400039df  jmp     loc_140003795
0x1400039e4  mov     rax, [rdi]
0x1400039e7  mov     rcx, rdi
0x1400039ea  mov     rax, [rax]
0x1400039ed  call    _guard_dispatch_icall
0x1400039f2  jmp     loc_140003938
0x1400039f7  nop
0x1400039f8  lock xadd [rdi+0Ch], r14d
0x1400039fe  cmp     r14d, 1
0x140003a02  jnz     loc_1400037CB
0x140003a08  jmp     loc_140003938
```
