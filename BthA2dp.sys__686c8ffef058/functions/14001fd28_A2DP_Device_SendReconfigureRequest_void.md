# A2DP_Device::SendReconfigureRequest(void)

- ea: `0x14001fd28`
- end: `0x14002002d`
- name: `?SendReconfigureRequest@A2DP_Device@@QEAAJXZ`
- size: `773`
- prototype: `__int64 __fastcall(A2DP_Device *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x14003445c`
- `0x14003d940`

## callees

- `0x140003530`
- `0x140006380`
- `0x140006410`
- `0x14000700c`
- `0x1400077e0`
- `0x140010628`
- `0x14001fd28`
- `0x1400202b0`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001fe96`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001fe96`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001fe66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001fe66`

## pseudocode

```c
__int64 __fastcall A2DP_Device::SendReconfigureRequest(A2DP_Device *this)
{
  char v2; // di
  char v3; // dl
  __int64 v4; // rcx
  __int64 *CurrentSelectedCodec; // rax
  char v6; // bl
  __int64 v7; // r14
  utl::_RefCountBase *v8; // r13
  signed int v9; // ebx
  KIRQL v10; // al
  __int64 v11; // r14
  KIRQL v12; // r12
  __int64 v13; // r8
  __int64 v14; // rdx
  char v15; // dl
  char v16; // al
  __int64 *v17; // rdx
  char v19; // [rsp+50h] [rbp-20h] BYREF
  utl::_RefCountBase *v20; // [rsp+58h] [rbp-18h]
  _BYTE v21[8]; // [rsp+60h] [rbp-10h] BYREF
  utl::_RefCountBase *v22; // [rsp+68h] [rbp-8h]
  unsigned int v23; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+48h] BYREF

  v23 = 0;
  v2 = 1;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || (v3 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    v3 = 0;
  }
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      163,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)this);
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    CurrentSelectedCodec = (__int64 *)A2dpRole::GetCurrentSelectedCodec(v4, v21);
    v6 = 1;
    v7 = *CurrentSelectedCodec;
  }
  else
  {
    v20 = 0;
    CurrentSelectedCodec = (__int64 *)&v19;
    v7 = 0;
    v6 = 2;
  }
  v8 = (utl::_RefCountBase *)CurrentSelectedCodec[1];
  CurrentSelectedCodec[1] = 0;
  *CurrentSelectedCodec = 0;
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    if ( v20 )
      utl::_RefCountBase::_DecStrong(v20);
  }
  if ( (v6 & 1) != 0 && v22 )
    utl::_RefCountBase::_DecStrong(v22);
  v24 = 0;
  v23 = 0;
  v9 = v7 == 0 ? 0xC0000184 : 0;
  if ( !v7 )
    goto LABEL_47;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v7 + 72LL))(v7, &v24, &v23);
  if ( v9 < 0 )
    goto LABEL_47;
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 87);
  v11 = *((_QWORD *)this + 50);
  v12 = v10;
  if ( v11 )
    (*((void (__fastcall **)(_QWORD))this + 53))(*((_QWORD *)this + 50));
  KeReleaseSpinLock((PKSPIN_LOCK)this + 87, v12);
  if ( v11 )
  {
    A2DP_Device::SetLastAvdtpActivity(this, 25, v13);
    if ( (unsigned int)(*((_DWORD *)this + 708) - 4) <= 1 )
    {
      v14 = *((_QWORD *)this + 1);
      LOBYTE(v14) = *(_BYTE *)(v14 + 104);
      v9 = (*((__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))this + 72))(v11, v14, v24, v23);
    }
    else
    {
      v9 = -1073741436;
    }
    (*((void (__fastcall **)(__int64))this + 54))(v11);
    if ( v9 < 0 )
    {
LABEL_47:
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || (v15 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      {
        v15 = 0;
      }
      if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          v15,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          5,
          164,
          (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
          v9,
          (char)this);
    }
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || (v16 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    v16 = 0;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || !v16 )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v17 = WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids;
    LOBYTE(v17) = v2;
    WPP_RECORDER_AND_TRACE_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v17,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      165,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)this,
      v9);
  }
  __1__unique_storage_U__resource_policy_PEAU_AVDTP_CATEGORY_HEADER____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_AVDTP_CATEGORY_HEADER___0EDEBFEEC__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v24);
  if ( v8 )
    utl::_RefCountBase::_DecStrong(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001fd28  mov     [rsp-38h+arg_10], rbx
0x14001fd2d  push    rbp
0x14001fd2e  push    rsi
0x14001fd2f  push    rdi
0x14001fd30  push    r12
0x14001fd32  push    r13
0x14001fd34  push    r14
0x14001fd36  push    r15
0x14001fd38  mov     rbp, rsp
0x14001fd3b  sub     rsp, 70h
0x14001fd3f  xor     r15d, r15d
0x14001fd42  mov     rsi, rcx
0x14001fd45  mov     [rbp+arg_0], r15d
0x14001fd49  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fd50  lea     r12, WPP_GLOBAL_Control
0x14001fd57  lea     edi, [r15+1]
0x14001fd5b  cmp     rcx, r12
0x14001fd5e  jz      short loc_14001FD70
0x14001fd60  mov     eax, [rcx+2Ch]
0x14001fd63  test    al, 10h
0x14001fd65  jz      short loc_14001FD70
0x14001fd67  cmp     byte ptr [rcx+29h], 4
0x14001fd6b  mov     dl, dil
0x14001fd6e  jnb     short loc_14001FD73
0x14001fd70  mov     dl, r15b
0x14001fd73  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fd7a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fd81  lea     r9, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14001fd88  setnz   r8b
0x14001fd8c  test    dl, dl
0x14001fd8e  jnz     short loc_14001FD95
0x14001fd90  test    r8b, r8b
0x14001fd93  jz      short loc_14001FDC0
0x14001fd95  mov     [rsp+70h+var_30], rsi
0x14001fd9a  mov     [rsp+70h+var_38], r9
0x14001fd9f  mov     r9, [rcx+40h]
0x14001fda3  mov     rcx, [rcx+18h]
0x14001fda7  mov     [rsp+70h+var_40], 0A3h
0x14001fdae  mov     [rsp+70h+var_48], 5
0x14001fdb6  mov     [rsp+70h+var_50], 4
0x14001fdbb  call    WPP_RECORDER_AND_TRACE_SF_q
0x14001fdc0  mov     rcx, [rsi+8]
0x14001fdc4  test    rcx, rcx
0x14001fdc7  jz      short loc_14001FDD9
0x14001fdc9  lea     rdx, [rbp+var_10]
0x14001fdcd  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x14001fdd2  mov     ebx, edi
0x14001fdd4  mov     r14, [rax]
0x14001fdd7  jmp     short loc_14001FDE9
0x14001fdd9  mov     [rbp+var_18], r15
0x14001fddd  lea     rax, [rbp+var_20]
0x14001fde1  mov     r14, r15
0x14001fde4  mov     ebx, 2
0x14001fde9  mov     r13, [rax+8]
0x14001fded  mov     [rax+8], r15
0x14001fdf1  mov     [rax], r15
0x14001fdf4  test    bl, 2
0x14001fdf7  jz      short loc_14001FE0A
0x14001fdf9  mov     rcx, [rbp+var_18]; this
0x14001fdfd  and     ebx, 0FFFFFFFDh
0x14001fe00  test    rcx, rcx
0x14001fe03  jz      short loc_14001FE0A
0x14001fe05  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001fe0a  test    dil, bl
0x14001fe0d  jz      short loc_14001FE1D
0x14001fe0f  mov     rcx, [rbp+var_8]; this
0x14001fe13  test    rcx, rcx
0x14001fe16  jz      short loc_14001FE1D
0x14001fe18  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001fe1d  mov     rax, r14
0x14001fe20  mov     [rbp+arg_8], r15
0x14001fe24  neg     rax
0x14001fe27  mov     [rbp+arg_0], r15d
0x14001fe2b  sbb     ebx, ebx
0x14001fe2d  not     ebx
0x14001fe2f  and     ebx, 0C0000184h
0x14001fe35  jl      loc_14001FF08
0x14001fe3b  mov     rax, [r14]
0x14001fe3e  lea     r8, [rbp+arg_0]
0x14001fe42  lea     rdx, [rbp+arg_8]
0x14001fe46  mov     rcx, r14
0x14001fe49  mov     rax, [rax+48h]
0x14001fe4d  call    _guard_dispatch_icall
0x14001fe52  mov     ebx, eax
0x14001fe54  test    eax, eax
0x14001fe56  js      loc_14001FF08
0x14001fe5c  lea     r15, [rsi+2B8h]
0x14001fe63  mov     rcx, r15; SpinLock
0x14001fe66  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001fe6d  nop     dword ptr [rax+rax+00h]
0x14001fe72  mov     r14, [rsi+190h]
0x14001fe79  mov     r12b, al
0x14001fe7c  test    r14, r14
0x14001fe7f  jz      short loc_14001FE90
0x14001fe81  mov     rax, [rsi+1A8h]
0x14001fe88  mov     rcx, r14
0x14001fe8b  call    _guard_dispatch_icall
0x14001fe90  mov     dl, r12b; NewIrql
0x14001fe93  mov     rcx, r15; SpinLock
0x14001fe96  call    cs:__imp_KeReleaseSpinLock
0x14001fe9d  nop     dword ptr [rax+rax+00h]
0x14001fea2  xor     r15d, r15d
0x14001fea5  test    r14, r14
0x14001fea8  jz      loc_14001FF7A
0x14001feae  lea     edx, [r15+19h]
0x14001feb2  mov     rcx, rsi
0x14001feb5  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14001feba  mov     eax, [rsi+0B10h]
0x14001fec0  sub     eax, 4
0x14001fec3  cmp     eax, edi
0x14001fec5  jbe     short loc_14001FECE
0x14001fec7  mov     ebx, 0C0000184h
0x14001fecc  jmp     short loc_14001FEEE
0x14001fece  mov     rdx, [rsi+8]
0x14001fed2  mov     rcx, r14
0x14001fed5  mov     rax, [rsi+240h]
0x14001fedc  mov     r9d, [rbp+arg_0]
0x14001fee0  mov     r8, [rbp+arg_8]
0x14001fee4  mov     dl, [rdx+68h]
0x14001fee7  call    _guard_dispatch_icall
0x14001feec  mov     ebx, eax
0x14001feee  mov     rax, [rsi+1B0h]
0x14001fef5  mov     rcx, r14
0x14001fef8  call    _guard_dispatch_icall
0x14001fefd  lea     r12, WPP_GLOBAL_Control
0x14001ff04  test    ebx, ebx
0x14001ff06  jns     short loc_14001FF81
0x14001ff08  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ff0f  cmp     rcx, r12
0x14001ff12  jz      short loc_14001FF24
0x14001ff14  mov     eax, [rcx+2Ch]
0x14001ff17  test    al, 10h
0x14001ff19  jz      short loc_14001FF24
0x14001ff1b  cmp     byte ptr [rcx+29h], 2
0x14001ff1f  mov     dl, dil
0x14001ff22  jnb     short loc_14001FF27
0x14001ff24  mov     dl, r15b
0x14001ff27  lea     r14, WPP_RECORDER_INITIALIZED
0x14001ff2e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001ff35  setnz   r8b
0x14001ff39  test    dl, dl
0x14001ff3b  jnz     short loc_14001FF42
0x14001ff3d  test    r8b, r8b
0x14001ff40  jz      short loc_14001FF88
0x14001ff42  mov     [rsp+70h+var_28], rsi
0x14001ff47  lea     r9, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14001ff4e  mov     dword ptr [rsp+70h+var_30], ebx
0x14001ff52  mov     [rsp+70h+var_38], r9
0x14001ff57  mov     r9, [rcx+40h]
0x14001ff5b  mov     rcx, [rcx+18h]
0x14001ff5f  mov     [rsp+70h+var_40], 0A4h
0x14001ff66  mov     [rsp+70h+var_48], 5
0x14001ff6e  mov     [rsp+70h+var_50], 2
0x14001ff73  call    WPP_RECORDER_AND_TRACE_SF_dq
0x14001ff78  jmp     short loc_14001FF88
0x14001ff7a  lea     r12, WPP_GLOBAL_Control
0x14001ff81  lea     r14, WPP_RECORDER_INITIALIZED
0x14001ff88  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ff8f  mov     eax, [rcx+2Ch]
0x14001ff92  test    al, 10h
0x14001ff94  jz      short loc_14001FF9F
0x14001ff96  cmp     byte ptr [rcx+29h], 4
0x14001ff9a  mov     al, dil
0x14001ff9d  jnb     short loc_14001FFA2
0x14001ff9f  mov     al, r15b
0x14001ffa2  cmp     rcx, r12
0x14001ffa5  jz      short loc_14001FFAB
0x14001ffa7  test    al, al
0x14001ffa9  jnz     short loc_14001FFAE
0x14001ffab  mov     dil, r15b
0x14001ffae  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001ffb5  setnz   r8b
0x14001ffb9  test    dil, dil
0x14001ffbc  jnz     short loc_14001FFC3
0x14001ffbe  test    r8b, r8b
0x14001ffc1  jz      short loc_14001FFFC
0x14001ffc3  mov     r9, [rcx+40h]
0x14001ffc7  lea     rdx, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14001ffce  mov     rcx, [rcx+18h]
0x14001ffd2  mov     dword ptr [rsp+70h+var_28], ebx
0x14001ffd6  mov     [rsp+70h+var_30], rsi
0x14001ffdb  mov     [rsp+70h+var_38], rdx
0x14001ffe0  mov     dl, dil
0x14001ffe3  mov     [rsp+70h+var_40], 0A5h
0x14001ffea  mov     [rsp+70h+var_48], 5
0x14001fff2  mov     [rsp+70h+var_50], 4
0x14001fff7  call    WPP_RECORDER_AND_TRACE_SF_qD
0x14001fffc  lea     rcx, [rbp+arg_8]
0x140020000  call    ??1?$unique_storage@U?$resource_policy@PEAU_AVDTP_CATEGORY_HEADER@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_AVDTP_CATEGORY_HEADER@@$0EDEBFEEC@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140020005  test    r13, r13
0x140020008  jz      short loc_140020012
0x14002000a  mov     rcx, r13; this
0x14002000d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140020012  mov     eax, ebx
0x140020014  mov     rbx, [rsp+70h+arg_10]
0x14002001c  add     rsp, 70h
0x140020020  pop     r15
0x140020022  pop     r14
0x140020024  pop     r13
0x140020026  pop     r12
0x140020028  pop     rdi
0x140020029  pop     rsi
0x14002002a  pop     rbp
0x14002002b  retn
```
