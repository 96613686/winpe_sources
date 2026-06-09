# A2dpRole::DecodeIncomingAudioBuffer(uchar * const,unsigned __int64,unsigned __int64,ulong)

- ea: `0x140007540`
- end: `0x1400077da`
- name: `?DecodeIncomingAudioBuffer@A2dpRole@@QEAAJQEAE_K1K@Z`
- size: `666`
- prototype: `__int64 __fastcall(A2dpRole *this, unsigned __int8 *const, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007330`

## callees

- `0x140006380`
- `0x140006410`
- `0x140007540`
- `0x14001433c`
- `0x14001bd20`
- `0x14001d1b0`
- `0x14002d38c`
- `0x14005c870`
- `0x14005ce00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140007635`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007781`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007635`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007781`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007620`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400076c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007620`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400076c7`
- `ks!KsPinAttemptProcessing` at `0x14000776f`
- `ks!KsPinAttemptProcessing` at `0x14000776f`

## pseudocode

```c
__int64 __fastcall A2dpRole::DecodeIncomingAudioBuffer(
        A2dpRole *this,
        unsigned __int8 *const a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v6; // r14
  bool v9; // r10
  __int64 v10; // rdx
  bool v11; // zf
  __int64 v12; // rbx
  KSPIN_LOCK *v13; // rdi
  KIRQL v14; // al
  KSPIN_LOCK *v15; // r15
  KIRQL v16; // r12
  _QWORD *v17; // r14
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  PVOID v20; // r13
  struct _KSPIN *v21; // rcx
  PVOID P; // [rsp+60h] [rbp-21h] BYREF
  __int64 v24; // [rsp+68h] [rbp-19h] BYREF
  utl::_RefCountBase *v25; // [rsp+70h] [rbp-11h]
  char v26[88]; // [rsp+78h] [rbp-9h] BYREF

  v6 = a3;
  v9 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = (__int64)(*((_QWORD *)this + 30) - *((_QWORD *)this + 29)) >> 3;
    LOBYTE(v10) = v9;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_Pddq(WPP_GLOBAL_Control->AttachedDevice, v10, a3, WPP_GLOBAL_Control->DeviceExtension);
  }
  v11 = *((_BYTE *)this + 88) == 0;
  P = 0;
  if ( v11 )
  {
    LODWORD(v12) = 0;
    return (unsigned int)v12;
  }
  if ( a2 && v6 )
  {
    if ( a5 != 36 )
    {
      LODWORD(v12) = -1073741811;
      return (unsigned int)v12;
    }
    v13 = (KSPIN_LOCK *)*((_QWORD *)this + 21);
    v14 = KeAcquireSpinLockRaiseToDpc(v13);
    v12 = *((_QWORD *)this + 3);
    KeReleaseSpinLock(v13, v14);
    if ( !v12 )
      goto LABEL_36;
    A2dpRole::GetCurrentSelectedCodec(this, &v24);
    v12 = v24;
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 88LL))(v24, v26);
      if ( v26[0] )
      {
        LODWORD(v12) = -1073741275;
        MicrosoftTelemetryAssertTriggeredMsgKM("Currently selected codec for sink role is not SBC");
      }
      else
      {
        LODWORD(v12) = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *const, __int64, __int64, PVOID *))(*(_QWORD *)v12 + 144LL))(
                         v12,
                         a2,
                         v6,
                         a4,
                         &P);
      }
      if ( (int)v12 >= 0 )
      {
        v15 = (KSPIN_LOCK *)*((_QWORD *)this + 21);
        v16 = KeAcquireSpinLockRaiseToDpc(v15);
        if ( !*((_QWORD *)this + 3) )
        {
LABEL_31:
          KeReleaseSpinLock(v15, v16);
          goto LABEL_32;
        }
        v17 = (_QWORD *)*((_QWORD *)this + 29);
        v18 = (_QWORD *)*((_QWORD *)this + 30);
        v19 = (_QWORD *)*((_QWORD *)this + 31);
        if ( v17 == v18 )
        {
          if ( v18 != v19
            || (unsigned __int8)utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Grow((char *)this + 232) )
          {
            **((_QWORD **)this + 30) = P;
            *((_QWORD *)this + 30) += 8LL;
          }
          goto LABEL_30;
        }
        v20 = P;
        if ( v18 == v19 )
        {
          if ( !(unsigned __int8)utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Grow((char *)this + 232) )
          {
LABEL_30:
            v21 = (struct _KSPIN *)*((_QWORD *)this + 3);
            P = 0;
            KsPinAttemptProcessing(v21, 1u);
            goto LABEL_31;
          }
          v17 = (_QWORD *)*((_QWORD *)this + 29);
        }
        **((_QWORD **)this + 30) = *(_QWORD *)(*((_QWORD *)this + 30) - 8LL);
        *((_QWORD *)this + 30) += 8LL;
        memmove(v17 + 1, v17, (*((_QWORD *)this + 30) - (_QWORD)v17 - 16LL) & 0xFFFFFFFFFFFFFFF8uLL);
        *v17 = v20;
        goto LABEL_30;
      }
    }
    else
    {
      LODWORD(v12) = -1073741275;
      MicrosoftTelemetryAssertTriggeredMsgKM("SBC codec is not available");
    }
LABEL_32:
    if ( v25 )
      utl::_RefCountBase::_DecStrong(v25);
    goto LABEL_36;
  }
  LODWORD(v12) = -1073741811;
LABEL_36:
  if ( P )
    FrameListEntry::FreeFrameListEntry(P);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140007540  push    rbp
0x140007542  push    rbx
0x140007543  push    rsi
0x140007544  push    rdi
0x140007545  push    r12
0x140007547  push    r13
0x140007549  push    r14
0x14000754b  push    r15
0x14000754d  lea     rbp, [rsp-17h]
0x140007552  sub     rsp, 98h
0x140007559  mov     r12, r9
0x14000755c  mov     r14, r8
0x14000755f  mov     r15, rdx
0x140007562  mov     rsi, rcx
0x140007565  mov     rcx, cs:WPP_GLOBAL_Control
0x14000756c  lea     rax, WPP_GLOBAL_Control
0x140007573  cmp     rcx, rax
0x140007576  jz      short loc_14000758A
0x140007578  mov     eax, [rcx+2Ch]
0x14000757b  test    al, 10h
0x14000757d  jz      short loc_14000758A
0x14000757f  cmp     byte ptr [rcx+29h], 4
0x140007583  jb      short loc_14000758A
0x140007585  mov     r10b, 1
0x140007588  jmp     short loc_14000758D
0x14000758a  xor     r10b, r10b
0x14000758d  mov     ebx, [rbp+4Fh+arg_20]
0x140007590  lea     rax, WPP_RECORDER_INITIALIZED
0x140007597  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000759e  setnz   r8b
0x1400075a2  test    r10b, r10b
0x1400075a5  jnz     short loc_1400075AC
0x1400075a7  test    r8b, r8b
0x1400075aa  jz      short loc_1400075E0
0x1400075ac  mov     rdx, [rsi+0F0h]
0x1400075b3  sub     rdx, [rsi+0E8h]
0x1400075ba  mov     r9, [rcx+40h]
0x1400075be  mov     rcx, [rcx+18h]
0x1400075c2  sar     rdx, 3
0x1400075c6  mov     [rsp+0D0h+var_78], rsi
0x1400075cb  mov     [rsp+0D0h+var_80], edx
0x1400075cf  mov     dl, r10b
0x1400075d2  mov     [rsp+0D0h+var_88], ebx
0x1400075d6  mov     [rsp+0D0h+var_90], r14
0x1400075db  call    WPP_RECORDER_AND_TRACE_SF_Pddq
0x1400075e0  cmp     byte ptr [rsi+58h], 0
0x1400075e4  mov     [rbp+4Fh+P], 0
0x1400075ec  jnz     short loc_1400075F5
0x1400075ee  xor     ebx, ebx
0x1400075f0  jmp     loc_1400077C3
0x1400075f5  test    r15, r15
0x1400075f8  jz      loc_1400077B0
0x1400075fe  test    r14, r14
0x140007601  jz      loc_1400077B0
0x140007607  cmp     ebx, 24h ; '$'
0x14000760a  jz      short loc_140007616
0x14000760c  mov     ebx, 0C000000Dh
0x140007611  jmp     loc_1400077C3
0x140007616  mov     rdi, [rsi+0A8h]
0x14000761d  mov     rcx, rdi; SpinLock
0x140007620  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007627  nop     dword ptr [rax+rax+00h]
0x14000762c  mov     rbx, [rsi+18h]
0x140007630  mov     rcx, rdi; SpinLock
0x140007633  mov     dl, al; NewIrql
0x140007635  call    cs:__imp_KeReleaseSpinLock
0x14000763c  nop     dword ptr [rax+rax+00h]
0x140007641  test    rbx, rbx
0x140007644  jz      loc_1400077B5
0x14000764a  lea     rdx, [rbp+4Fh+var_68]
0x14000764e  mov     rcx, rsi
0x140007651  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x140007656  mov     rbx, [rbp+4Fh+var_68]
0x14000765a  test    rbx, rbx
0x14000765d  jz      loc_14000779D
0x140007663  mov     rax, [rbx]
0x140007666  lea     rdx, [rbp+4Fh+var_58]
0x14000766a  mov     rcx, rbx
0x14000766d  mov     rax, [rax+58h]
0x140007671  call    _guard_dispatch_icall
0x140007676  cmp     [rbp+4Fh+var_58], 0
0x14000767a  jnz     short loc_1400076A4
0x14000767c  mov     rax, [rbx]
0x14000767f  lea     rcx, [rbp+4Fh+P]
0x140007683  mov     [rsp+0D0h+var_B0], rcx
0x140007688  mov     r9, r12
0x14000768b  mov     r8, r14
0x14000768e  mov     rdx, r15
0x140007691  mov     rcx, rbx
0x140007694  mov     rax, [rax+90h]
0x14000769b  call    _guard_dispatch_icall
0x1400076a0  mov     ebx, eax
0x1400076a2  jmp     short loc_1400076B5
0x1400076a4  mov     ebx, 0C0000225h
0x1400076a9  lea     rcx, aCurrentlySelec; "Currently selected codec for sink role "...
0x1400076b0  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400076b5  test    ebx, ebx
0x1400076b7  js      loc_14000778D
0x1400076bd  mov     r15, [rsi+0A8h]
0x1400076c4  mov     rcx, r15; SpinLock
0x1400076c7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400076ce  nop     dword ptr [rax+rax+00h]
0x1400076d3  cmp     qword ptr [rsi+18h], 0
0x1400076d8  mov     r12b, al
0x1400076db  jz      loc_14000777B
0x1400076e1  lea     rdi, [rsi+0E8h]
0x1400076e8  mov     r14, [rdi]
0x1400076eb  mov     rcx, [rdi+8]
0x1400076ef  mov     rdx, [rdi+10h]
0x1400076f3  cmp     r14, rcx
0x1400076f6  jnz     short loc_14000771B
0x1400076f8  cmp     rcx, rdx
0x1400076fb  jnz     short loc_140007709
0x1400076fd  mov     rcx, rdi
0x140007700  call    ?_Grow@?$vector@PEAUFrameListEntry@@V?$allocator@PEAUFrameListEntry@@@utl@@@utl@@AEAA_NXZ; utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Grow(void)
0x140007705  test    al, al
0x140007707  jz      short loc_140007761
0x140007709  mov     rcx, [rdi+8]
0x14000770d  mov     rax, [rbp+4Fh+P]
0x140007711  mov     [rcx], rax
0x140007714  add     qword ptr [rdi+8], 8
0x140007719  jmp     short loc_140007761
0x14000771b  mov     r13, [rbp+4Fh+P]
0x14000771f  cmp     rcx, rdx
0x140007722  jnz     short loc_140007733
0x140007724  mov     rcx, rdi
0x140007727  call    ?_Grow@?$vector@PEAUFrameListEntry@@V?$allocator@PEAUFrameListEntry@@@utl@@@utl@@AEAA_NXZ; utl::vector<FrameListEntry *,utl::allocator<FrameListEntry *>>::_Grow(void)
0x14000772c  test    al, al
0x14000772e  jz      short loc_140007761
0x140007730  mov     r14, [rdi]
0x140007733  mov     rcx, [rdi+8]
0x140007737  mov     rdx, r14; Src
0x14000773a  mov     rax, [rcx-8]
0x14000773e  mov     [rcx], rax
0x140007741  lea     rcx, [r14+8]; void *
0x140007745  add     qword ptr [rdi+8], 8
0x14000774a  mov     r8, [rdi+8]
0x14000774e  sub     r8, r14
0x140007751  sub     r8, 10h
0x140007755  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x140007759  call    memmove
0x14000775e  mov     [r14], r13
0x140007761  mov     rcx, [rsi+18h]; Pin
0x140007765  mov     dl, 1; Asynchronous
0x140007767  mov     [rbp+4Fh+P], 0
0x14000776f  call    cs:__imp_KsPinAttemptProcessing
0x140007776  nop     dword ptr [rax+rax+00h]
0x14000777b  mov     dl, r12b; NewIrql
0x14000777e  mov     rcx, r15; SpinLock
0x140007781  call    cs:__imp_KeReleaseSpinLock
0x140007788  nop     dword ptr [rax+rax+00h]
0x14000778d  mov     rcx, [rbp+4Fh+var_60]; this
0x140007791  test    rcx, rcx
0x140007794  jz      short loc_1400077B5
0x140007796  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14000779b  jmp     short loc_1400077B5
0x14000779d  mov     ebx, 0C0000225h
0x1400077a2  lea     rcx, aSbcCodecIsNotA; "SBC codec is not available"
0x1400077a9  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400077ae  jmp     short loc_14000778D
0x1400077b0  mov     ebx, 0C000000Dh
0x1400077b5  mov     rcx, [rbp+4Fh+P]; P
0x1400077b9  test    rcx, rcx
0x1400077bc  jz      short loc_1400077C3
0x1400077be  call    ?FreeFrameListEntry@FrameListEntry@@SAXPEAU1@@Z; FrameListEntry::FreeFrameListEntry(FrameListEntry *)
0x1400077c3  mov     eax, ebx
0x1400077c5  add     rsp, 98h
0x1400077cc  pop     r15
0x1400077ce  pop     r14
0x1400077d0  pop     r13
0x1400077d2  pop     r12
0x1400077d4  pop     rdi
0x1400077d5  pop     rsi
0x1400077d6  pop     rbx
0x1400077d7  pop     rbp
0x1400077d8  retn
```
