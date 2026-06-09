# Avdtp_impl::SendBTHDWithTempBuffer(_BRB *,void *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *,bool)

- ea: `0x140019718`
- end: `0x140019c3c`
- name: `?SendBTHDWithTempBuffer@Avdtp_impl@@AEAAJPEAU_BRB@@PEAXP6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@1@Z1_N@Z`
- size: `1316`
- prototype: `__int64 __usercall@<rax>(Avdtp_impl *__hidden this@<rcx>, struct _BRB *@<rdx>, void *@<r8>, int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)@<r9>, void *, bool)`
- caller_count: `9`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017d1c`
- `0x140019340`
- `0x140046688`
- `0x140046eb0`
- `0x140048fe0`
- `0x14004d790`
- `0x140050a78`
- `0x140051b50`
- `0x1400520b0`

## callees

- `0x140006a88`
- `0x14000e690`
- `0x14000f300`
- `0x14000f600`
- `0x14000f7e0`
- `0x14000fde0`
- `0x140019718`
- `0x14002d890`
- `0x1400426b0`
- `0x140046b04`
- `0x140049a40`
- `0x14004a244`
- `0x14004ccf4`
- `0x14004f964`
- `0x14005393c`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400199b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400199b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019c09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019c09`
- `ntoskrnl!IofCallDriver` at `0x140019bde`
- `ntoskrnl!IofCallDriver` at `0x140019bde`
- `ntoskrnl!IoAllocateIrp` at `0x1400199f0`
- `ntoskrnl!IoAllocateIrp` at `0x1400199f0`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140019bb1`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140019bb1`
- `ntoskrnl!IoFreeIrp` at `0x140019b1e`
- `ntoskrnl!IoFreeIrp` at `0x140019bf5`
- `ntoskrnl!IoFreeIrp` at `0x140019b1e`
- `ntoskrnl!IoFreeIrp` at `0x140019bf5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019ade`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019b7f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019ade`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019b7f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019abb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019abb`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::SendBTHDWithTempBuffer(
        Avdtp_impl *this,
        struct _BRB *a2,
        void *a3,
        int (*a4)(struct _DEVICE_OBJECT *, struct _IRP *, void *),
        void *a5,
        bool a6)
{
  void *v7; // r13
  struct _BRB *v8; // rsi
  bool v10; // di
  int v12; // edx
  int v13; // r8d
  bool v14; // r12
  int v15; // edx
  int v16; // r8d
  _QWORD *Pool2; // r14
  PIRP Irp; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  IRP *v22; // rbp
  struct _IO_STACK_LOCATION *v23; // rcx
  struct _DEVICE_OBJECT *v24; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v26; // eax
  int v27; // eax
  unsigned int v28; // r15d
  KIRQL v29; // dl
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned int v34; // eax
  Avdtp_impl **v35; // rcx
  struct _IO_STACK_LOCATION *v36; // rax
  __int64 v37; // [rsp+70h] [rbp-68h] BYREF
  char v38; // [rsp+80h] [rbp-58h]

  v7 = a3;
  v8 = a2;
  if ( a2 )
  {
    if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
    {
      v14 = IsCriticalBrb(v8) || a6;
      GetBtAddressAndChannelHandle(&v37, v8);
      if ( v38 )
      {
        LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_Lbth_addrqqq(
            WPP_GLOBAL_Control->AttachedDevice,
            v15,
            v16,
            WPP_GLOBAL_Control->DeviceExtension);
        }
      }
      else
      {
        LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_Lqq(
            WPP_GLOBAL_Control->AttachedDevice,
            v15,
            v16,
            WPP_GLOBAL_Control->DeviceExtension);
        }
      }
    }
    else
    {
      LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_Dq(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          v13,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          60,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          v8->BrbHeader.Type,
          this);
      }
      v14 = a6;
    }
    Pool2 = (_QWORD *)ExAllocatePool2(64, 48, 1096172628);
    if ( Pool2 )
    {
      Irp = IoAllocateIrp(*(_BYTE *)(*((_QWORD *)this + 137) + 76LL) + 1, 0);
      v22 = Irp;
      if ( Irp )
      {
        --Irp->CurrentLocation;
        v23 = --Irp->Tail.Overlay.CurrentStackLocation;
        Pool2[4] = a5;
        v24 = (struct _DEVICE_OBJECT *)*((_QWORD *)this + 136);
        Pool2[5] = v7;
        Pool2[2] = v22;
        *((_DWORD *)Pool2 + 6) = 1;
        *((_BYTE *)Pool2 + 28) = v14;
        v23->DeviceObject = v24;
        v23->Parameters.WMI.ProviderId = (ULONG_PTR)v8;
        v23->CompletionRoutine = a4;
        v23->Context = Pool2;
        CurrentStackLocation = v22->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].MajorFunction = 15;
        CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4259843;
        CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)v8;
        if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v23, v19, v20, v21) )
        {
          v26 = Avdtp_impl::GetRemoveLockClient(v8->BrbHeader.Type);
          v27 = Avdtp_impl::AcquireRemoveLock(this, v26);
        }
        else
        {
          v27 = Avdtp_impl::AcquireRemoveLock(this);
        }
        v28 = v27;
        if ( v27 < 0 )
        {
          IoFreeIrp(v22);
          ExFreePoolWithTag(Pool2, 0x41564454u);
          (*((void (__fastcall **)(struct _BRB *))this + 132))(v8);
        }
        else
        {
          Avdtp_impl::InterfaceReference(this, v22);
          v29 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 222);
          if ( *((_DWORD *)this + 446) && !v14 )
          {
            KeReleaseSpinLock((PKSPIN_LOCK)this + 222, v29);
            Avdtp_impl::InterfaceDereference(this, v22);
            if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v31, v30, v32, v33) )
            {
              v34 = Avdtp_impl::GetRemoveLockClient(v8->BrbHeader.Type);
              Avdtp_impl::ReleaseRemoveLock(this, v34);
            }
            else
            {
              Avdtp_impl::ReleaseRemoveLock(this);
            }
            IoFreeIrp(v22);
            ExFreePoolWithTag(Pool2, 0x41564454u);
            (*((void (__fastcall **)(struct _BRB *))this + 132))(v8);
            return 3221225635LL;
          }
          v35 = (Avdtp_impl **)*((_QWORD *)this + 221);
          if ( *v35 != (Avdtp_impl *)((char *)this + 1760) )
            __fastfail(3u);
          Pool2[1] = v35;
          *Pool2 = (char *)this + 1760;
          *v35 = (Avdtp_impl *)Pool2;
          *((_QWORD *)this + 221) = Pool2;
          KeReleaseSpinLock((PKSPIN_LOCK)this + 222, v29);
          if ( IoSetCompletionRoutineEx(
                 *((PDEVICE_OBJECT *)this + 136),
                 v22,
                 Avdtp_impl::SendBTHD_Completion,
                 this,
                 1u,
                 1u,
                 1u) < 0 )
          {
            v36 = v22->Tail.Overlay.CurrentStackLocation;
            v36[-1].CompletionRoutine = Avdtp_impl::SendBTHD_Completion;
            v36[-1].Context = this;
            v36[-1].Control = -32;
          }
          IofCallDriver(*((PDEVICE_OBJECT *)this + 137), v22);
          return 259;
        }
        return v28;
      }
      ExFreePoolWithTag(Pool2, 0x41564454u);
    }
    (*((void (__fastcall **)(struct _BRB *))this + 132))(v8);
    return 3221225626LL;
  }
  v10 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
     && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = v10;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      18,
      57,
      (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
      13);
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140019718  push    rbx
0x14001971a  push    rbp
0x14001971b  push    rsi
0x14001971c  push    rdi
0x14001971d  push    r12
0x14001971f  push    r13
0x140019721  push    r14
0x140019723  push    r15
0x140019725  sub     rsp, 98h
0x14001972c  mov     r15, r9
0x14001972f  mov     r13, r8
0x140019732  mov     rsi, rdx
0x140019735  mov     rbx, rcx
0x140019738  test    rdx, rdx
0x14001973b  jnz     loc_1400197C7
0x140019741  mov     rcx, cs:WPP_GLOBAL_Control
0x140019748  lea     rax, WPP_GLOBAL_Control
0x14001974f  cmp     rcx, rax
0x140019752  jz      short loc_140019768
0x140019754  test    dword ptr [rcx+2Ch], 20000h
0x14001975b  jz      short loc_140019768
0x14001975d  cmp     byte ptr [rcx+29h], 2
0x140019761  jb      short loc_140019768
0x140019763  lea     edi, [rdx+1]
0x140019766  jmp     short loc_14001976B
0x140019768  xor     dil, dil
0x14001976b  lea     rax, WPP_RECORDER_INITIALIZED
0x140019772  mov     ebx, 0C000000Dh
0x140019777  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001977e  setnz   r8b
0x140019782  test    dil, dil
0x140019785  jnz     short loc_14001978C
0x140019787  test    r8b, r8b
0x14001978a  jz      short loc_1400197C0
0x14001978c  mov     [rsp+0D8h+var_98], ebx
0x140019790  lea     r9, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x140019797  mov     [rsp+0D8h+var_A0], r9
0x14001979c  mov     dl, dil
0x14001979f  mov     r9, [rcx+40h]
0x1400197a3  mov     rcx, [rcx+18h]
0x1400197a7  mov     word ptr [rsp+0D8h+InvokeOnCancel], 39h ; '9'
0x1400197ae  mov     dword ptr [rsp+0D8h+InvokeOnError], 12h
0x1400197b6  mov     [rsp+0D8h+InvokeOnSuccess], 2
0x1400197bb  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400197c0  mov     eax, ebx
0x1400197c2  jmp     loc_140019C27
0x1400197c7  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400197cc  test    eax, eax
0x1400197ce  jz      loc_14001991D
0x1400197d4  mov     rcx, rsi; struct _BRB *
0x1400197d7  call    ?IsCriticalBrb@@YA_NPEBU_BRB@@@Z; IsCriticalBrb(_BRB const *)
0x1400197dc  mov     edi, 1
0x1400197e1  test    al, al
0x1400197e3  jnz     short loc_1400197F3
0x1400197e5  cmp     [rsp+0D8h+arg_28], al
0x1400197ec  jnz     short loc_1400197F3
0x1400197ee  xor     r12b, r12b
0x1400197f1  jmp     short loc_1400197F6
0x1400197f3  mov     r12b, dil
0x1400197f6  mov     rdx, rsi
0x1400197f9  lea     rcx, [rsp+0D8h+var_68]
0x1400197fe  call    ?GetBtAddressAndChannelHandle@@YA?AV?$optional@U?$pair@_KPEAX@utl@@@utl@@PEAU_BRB@@@Z; GetBtAddressAndChannelHandle(_BRB *)
0x140019803  cmp     [rsp+0D8h+var_58], 0
0x14001980b  jz      loc_140019898
0x140019811  mov     rcx, cs:WPP_GLOBAL_Control
0x140019818  lea     rax, WPP_GLOBAL_Control
0x14001981f  cmp     rcx, rax
0x140019822  jz      short loc_140019836
0x140019824  mov     eax, [rcx+2Ch]
0x140019827  test    al, 8
0x140019829  jz      short loc_140019836
0x14001982b  cmp     byte ptr [rcx+29h], 4
0x14001982f  jb      short loc_140019836
0x140019831  mov     dl, dil
0x140019834  jmp     short loc_140019838
0x140019836  xor     dl, dl
0x140019838  lea     rax, WPP_RECORDER_INITIALIZED
0x14001983f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019846  setnz   r8b
0x14001984a  test    dl, dl
0x14001984c  jnz     short loc_140019857
0x14001984e  test    r8b, r8b
0x140019851  jz      loc_1400199A6
0x140019857  movzx   r9d, word ptr [rsi+16h]
0x14001985c  mov     rax, [rsp+0D8h+var_60]
0x140019861  mov     [rsp+0D8h+var_78], rbx
0x140019866  mov     [rsp+0D8h+var_80], rsi
0x14001986b  mov     [rsp+0D8h+var_88], rax
0x140019870  mov     rax, [rsp+0D8h+var_68]
0x140019875  mov     [rsp+0D8h+var_90], rax
0x14001987a  mov     [rsp+0D8h+var_98], r9d
0x14001987f  mov     r9, [rcx+40h]
0x140019883  mov     rcx, [rcx+18h]
0x140019887  mov     word ptr [rsp+0D8h+InvokeOnCancel], 3Ah ; ':'
0x14001988e  call    WPP_RECORDER_AND_TRACE_SF_Lbth_addrqqq
0x140019893  jmp     loc_1400199A6
0x140019898  mov     rcx, cs:WPP_GLOBAL_Control
0x14001989f  lea     rax, WPP_GLOBAL_Control
0x1400198a6  cmp     rcx, rax
0x1400198a9  jz      short loc_1400198BD
0x1400198ab  mov     eax, [rcx+2Ch]
0x1400198ae  test    al, 8
0x1400198b0  jz      short loc_1400198BD
0x1400198b2  cmp     byte ptr [rcx+29h], 4
0x1400198b6  jb      short loc_1400198BD
0x1400198b8  mov     dl, dil
0x1400198bb  jmp     short loc_1400198BF
0x1400198bd  xor     dl, dl
0x1400198bf  lea     rax, WPP_RECORDER_INITIALIZED
0x1400198c6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400198cd  setnz   r8b
0x1400198d1  test    dl, dl
0x1400198d3  jnz     short loc_1400198DE
0x1400198d5  test    r8b, r8b
0x1400198d8  jz      loc_1400199A6
0x1400198de  movzx   eax, word ptr [rsi+16h]
0x1400198e2  lea     r9, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x1400198e9  mov     [rsp+0D8h+var_88], rbx
0x1400198ee  mov     [rsp+0D8h+var_90], rsi
0x1400198f3  mov     [rsp+0D8h+var_98], eax
0x1400198f7  mov     [rsp+0D8h+var_A0], r9
0x1400198fc  mov     r9, [rcx+40h]
0x140019900  mov     rcx, [rcx+18h]
0x140019904  mov     word ptr [rsp+0D8h+InvokeOnCancel], 3Bh ; ';'
0x14001990b  mov     dword ptr [rsp+0D8h+InvokeOnError], 4
0x140019913  call    WPP_RECORDER_AND_TRACE_SF_Lqq
0x140019918  jmp     loc_1400199A6
0x14001991d  mov     rcx, cs:WPP_GLOBAL_Control
0x140019924  lea     rax, WPP_GLOBAL_Control
0x14001992b  mov     edi, 1
0x140019930  cmp     rcx, rax
0x140019933  jz      short loc_140019947
0x140019935  mov     eax, [rcx+2Ch]
0x140019938  test    al, 8
0x14001993a  jz      short loc_140019947
0x14001993c  cmp     byte ptr [rcx+29h], 4
0x140019940  jb      short loc_140019947
0x140019942  mov     dl, dil
0x140019945  jmp     short loc_140019949
0x140019947  xor     dl, dl
0x140019949  lea     rax, WPP_RECORDER_INITIALIZED
0x140019950  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019957  setnz   r8b
0x14001995b  test    dl, dl
0x14001995d  jnz     short loc_140019964
0x14001995f  test    r8b, r8b
0x140019962  jz      short loc_14001999E
0x140019964  movzx   eax, word ptr [rsi+16h]
0x140019968  lea     r9, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14001996f  mov     [rsp+0D8h+var_90], rbx
0x140019974  mov     [rsp+0D8h+var_98], eax
0x140019978  mov     [rsp+0D8h+var_A0], r9
0x14001997d  mov     r9, [rcx+40h]
0x140019981  mov     rcx, [rcx+18h]
0x140019985  mov     word ptr [rsp+0D8h+InvokeOnCancel], 3Ch ; '<'
0x14001998c  mov     dword ptr [rsp+0D8h+InvokeOnError], 4
0x140019994  mov     [rsp+0D8h+InvokeOnSuccess], 4
0x140019999  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x14001999e  mov     r12b, [rsp+0D8h+arg_28]
0x1400199a6  mov     edx, 30h ; '0'
0x1400199ab  mov     r8d, 41564454h
0x1400199b1  lea     ecx, [rdx+10h]
0x1400199b4  call    cs:__imp_ExAllocatePool2
0x1400199bb  nop     dword ptr [rax+rax+00h]
0x1400199c0  mov     r14, rax
0x1400199c3  test    rax, rax
0x1400199c6  jnz     short loc_1400199E1
0x1400199c8  mov     rax, [rbx+420h]
0x1400199cf  mov     rcx, rsi
0x1400199d2  call    _guard_dispatch_icall
0x1400199d7  mov     eax, 0C000009Ah
0x1400199dc  jmp     loc_140019C27
0x1400199e1  mov     rax, [rbx+448h]
0x1400199e8  xor     edx, edx; ChargeQuota
0x1400199ea  mov     cl, [rax+4Ch]
0x1400199ed  add     cl, dil; StackSize
0x1400199f0  call    cs:__imp_IoAllocateIrp
0x1400199f7  nop     dword ptr [rax+rax+00h]
0x1400199fc  mov     rbp, rax
0x1400199ff  test    rax, rax
0x140019a02  jnz     short loc_140019A1A
0x140019a04  mov     edx, 41564454h; Tag
0x140019a09  mov     rcx, r14; P
0x140019a0c  call    cs:__imp_ExFreePoolWithTag
0x140019a13  nop     dword ptr [rax+rax+00h]
0x140019a18  jmp     short loc_1400199C8
0x140019a1a  dec     byte ptr [rbp+43h]
0x140019a1d  add     qword ptr [rbp+0B8h], 0FFFFFFFFFFFFFFB8h
0x140019a25  mov     rcx, [rbp+0B8h]
0x140019a2c  mov     rax, [rsp+0D8h+arg_20]
0x140019a34  mov     [r14+20h], rax
0x140019a38  mov     rax, [rbx+440h]
0x140019a3f  mov     [r14+28h], r13
0x140019a43  mov     [r14+10h], rbp
0x140019a47  mov     [r14+18h], edi
0x140019a4b  mov     [r14+1Ch], r12b
0x140019a4f  mov     [rcx+28h], rax
0x140019a53  mov     [rcx+8], rsi
0x140019a57  mov     [rcx+38h], r15
0x140019a5b  mov     [rcx+40h], r14
0x140019a5f  mov     rax, [rbp+0B8h]
0x140019a66  mov     byte ptr [rax-48h], 0Fh
0x140019a6a  mov     dword ptr [rax-30h], 410003h
0x140019a71  mov     [rax-40h], rsi
0x140019a75  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140019a7a  test    eax, eax
0x140019a7c  jz      short loc_140019A93
0x140019a7e  movzx   ecx, word ptr [rsi+16h]
0x140019a82  call    ?GetRemoveLockClient@Avdtp_impl@@CA?AW4RemoveLockClient@1@G@Z; Avdtp_impl::GetRemoveLockClient(ushort)
0x140019a87  mov     edx, eax
0x140019a89  mov     rcx, rbx
0x140019a8c  call    ?AcquireRemoveLock@Avdtp_impl@@QEAAJW4RemoveLockClient@1@@Z; Avdtp_impl::AcquireRemoveLock(Avdtp_impl::RemoveLockClient)
0x140019a91  jmp     short loc_140019A9B
0x140019a93  mov     rcx, rbx; this
0x140019a96  call    ?AcquireRemoveLock@Avdtp_impl@@QEAAJXZ; Avdtp_impl::AcquireRemoveLock(void)
0x140019a9b  mov     r15d, eax
0x140019a9e  test    eax, eax
0x140019aa0  js      loc_140019BF2
0x140019aa6  mov     rdx, rbp; void *
0x140019aa9  mov     rcx, rbx; this
0x140019aac  call    ?InterfaceReference@Avdtp_impl@@AEAAXPEAX@Z; Avdtp_impl::InterfaceReference(void *)
0x140019ab1  lea     r15, [rbx+6F0h]
0x140019ab8  mov     rcx, r15; SpinLock
0x140019abb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019ac2  nop     dword ptr [rax+rax+00h]
0x140019ac7  cmp     dword ptr [rbx+6F8h], 0
0x140019ace  mov     dl, al; NewIrql
0x140019ad0  jz      loc_140019B57
0x140019ad6  test    r12b, r12b
0x140019ad9  jnz     short loc_140019B57
0x140019adb  mov     rcx, r15; SpinLock
0x140019ade  call    cs:__imp_KeReleaseSpinLock
0x140019ae5  nop     dword ptr [rax+rax+00h]
0x140019aea  mov     rdx, rbp; void *
0x140019aed  mov     rcx, rbx; this
0x140019af0  call    ?InterfaceDereference@Avdtp_impl@@AEAAXPEAX@Z; Avdtp_impl::InterfaceDereference(void *)
0x140019af5  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140019afa  test    eax, eax
0x140019afc  jz      short loc_140019B13
0x140019afe  movzx   ecx, word ptr [rsi+16h]
0x140019b02  call    ?GetRemoveLockClient@Avdtp_impl@@CA?AW4RemoveLockClient@1@G@Z; Avdtp_impl::GetRemoveLockClient(ushort)
0x140019b07  mov     edx, eax
0x140019b09  mov     rcx, rbx
0x140019b0c  call    ?ReleaseRemoveLock@Avdtp_impl@@QEAAXW4RemoveLockClient@1@@Z; Avdtp_impl::ReleaseRemoveLock(Avdtp_impl::RemoveLockClient)
0x140019b11  jmp     short loc_140019B1B
0x140019b13  mov     rcx, rbx; this
0x140019b16  call    ?ReleaseRemoveLock@Avdtp_impl@@QEAAXXZ; Avdtp_impl::ReleaseRemoveLock(void)
0x140019b1b  mov     rcx, rbp; Irp
0x140019b1e  call    cs:__imp_IoFreeIrp
0x140019b25  nop     dword ptr [rax+rax+00h]
0x140019b2a  mov     edx, 41564454h; Tag
0x140019b2f  mov     rcx, r14; P
0x140019b32  call    cs:__imp_ExFreePoolWithTag
0x140019b39  nop     dword ptr [rax+rax+00h]
0x140019b3e  mov     rax, [rbx+420h]
0x140019b45  mov     rcx, rsi
0x140019b48  call    _guard_dispatch_icall
0x140019b4d  mov     eax, 0C00000A3h
0x140019b52  jmp     loc_140019C27
0x140019b57  lea     rax, [rbx+6E0h]
0x140019b5e  mov     rcx, [rax+8]
0x140019b62  cmp     [rcx], rax
0x140019b65  jz      short loc_140019B6E
0x140019b67  mov     ecx, 3
0x140019b6c  int     29h; Win8: RtlFailFast(ecx)
0x140019b6e  mov     [r14+8], rcx
0x140019b72  mov     [r14], rax
0x140019b75  mov     [rcx], r14
0x140019b78  mov     rcx, r15; SpinLock
0x140019b7b  mov     [rax+8], r14
0x140019b7f  call    cs:__imp_KeReleaseSpinLock
0x140019b86  nop     dword ptr [rax+rax+00h]
0x140019b8b  mov     rcx, [rbx+440h]; DeviceObject
0x140019b92  mov     r9, rbx; Context
0x140019b95  mov     [rsp+0D8h+InvokeOnCancel], dil; InvokeOnCancel
0x140019b9a  mov     rdx, rbp; Irp
0x140019b9d  mov     [rsp+0D8h+InvokeOnError], dil; InvokeOnError
0x140019ba2  mov     [rsp+0D8h+InvokeOnSuccess], dil; InvokeOnSuccess
0x140019ba7  lea     rdi, ?SendBTHD_Completion@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; Avdtp_impl::SendBTHD_Completion(_DEVICE_OBJECT *,_IRP *,void *)
0x140019bae  mov     r8, rdi; CompletionRoutine
0x140019bb1  call    cs:__imp_IoSetCompletionRoutineEx
0x140019bb8  nop     dword ptr [rax+rax+00h]
0x140019bbd  test    eax, eax
0x140019bbf  jns     short loc_140019BD4
0x140019bc1  mov     rax, [rbp+0B8h]
0x140019bc8  mov     [rax-10h], rdi
0x140019bcc  mov     [rax-8], rbx
0x140019bd0  mov     byte ptr [rax-45h], 0E0h
0x140019bd4  mov     rcx, [rbx+448h]; DeviceObject
0x140019bdb  mov     rdx, rbp; Irp
0x140019bde  call    cs:__imp_IofCallDriver
0x140019be5  nop     dword ptr [rax+rax+00h]
0x140019bea  mov     r15d, 103h
0x140019bf0  jmp     short loc_140019C24
0x140019bf2  mov     rcx, rbp; Irp
0x140019bf5  call    cs:__imp_IoFreeIrp
0x140019bfc  nop     dword ptr [rax+rax+00h]
0x140019c01  mov     edx, 41564454h; Tag
0x140019c06  mov     rcx, r14; P
0x140019c09  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
