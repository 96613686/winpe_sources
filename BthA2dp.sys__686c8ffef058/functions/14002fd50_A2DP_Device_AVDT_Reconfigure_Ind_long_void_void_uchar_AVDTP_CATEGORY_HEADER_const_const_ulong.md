# A2DP_Device::AVDT_Reconfigure_Ind(long,void *,void *,uchar,_AVDTP_CATEGORY_HEADER const * const,ulong)

- ea: `0x14002fd50`
- end: `0x14002fefe`
- name: `?AVDT_Reconfigure_Ind@A2DP_Device@@CAJJPEAX0EQEBU_AVDTP_CATEGORY_HEADER@@K@Z`
- size: `430`
- prototype: `__int64 __fastcall(unsigned int, void *, void *, char, const struct _AVDTP_CATEGORY_HEADER *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x140003530`
- `0x140006380`
- `0x140006410`
- `0x140007374`
- `0x1400077e0`
- `0x14002fd50`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002fea9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fea9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fe79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fe79`

## pseudocode

```c
__int64 __fastcall A2DP_Device::AVDT_Reconfigure_Ind(
        unsigned int a1,
        void *a2,
        void *a3,
        char a4,
        const struct _AVDTP_CATEGORY_HEADER *a5,
        unsigned int a6)
{
  int Timer_high; // edx
  struct A2DP_Device *v9; // rbx
  __int64 v10; // r8
  __int64 v11; // rdi
  char v12; // si
  KIRQL v13; // al
  __int64 v14; // rdi
  KIRQL v15; // r14
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v19; // [rsp+50h] [rbp-48h] BYREF
  utl::_RefCountBase *v20; // [rsp+58h] [rbp-40h]

  v9 = A2DP_Device::CheckCallbackParms(a2, a3);
  LOBYTE(Timer_high) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer), (Timer_high & 0x10) != 0)
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)Timer_high || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      Timer_high,
      v10,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      122,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)v9);
  A2DP_Device::SetLastAvdtpActivity(v9, 27, v10);
  if ( a5 && a6 >= 2 )
  {
    v11 = *((_QWORD *)v9 + 1);
    A2dpRole::GetCurrentSelectedCodec(v11, &v19);
    if ( v19 && a4 == *(_BYTE *)(v11 + 105) )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, const struct _AVDTP_CATEGORY_HEADER *, _QWORD))(*(_QWORD *)v19 + 8LL))(
              v19,
              a5,
              a6);
      if ( v20 )
        utl::_RefCountBase::_DecStrong(v20);
    }
    else
    {
      if ( v20 )
        utl::_RefCountBase::_DecStrong(v20);
      v12 = 18;
    }
  }
  else
  {
    v12 = 41;
  }
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v9 + 87);
  v14 = *((_QWORD *)v9 + 50);
  v15 = v13;
  if ( v14 )
    (*((void (__fastcall **)(_QWORD))v9 + 53))(*((_QWORD *)v9 + 50));
  KeReleaseSpinLock((PKSPIN_LOCK)v9 + 87, v15);
  if ( v14 )
  {
    A2DP_Device::SetLastAvdtpActivity(v9, 28, v16);
    LOBYTE(v17) = v12;
    (*((void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))v9 + 73))(a1, v14, 0, v17);
    (*((void (__fastcall **)(__int64))v9 + 54))(v14);
  }
  return 0;
}

```

## disassembly

```asm
0x14002fd50  push    rbx
0x14002fd52  push    rbp
0x14002fd53  push    rsi
0x14002fd54  push    rdi
0x14002fd55  push    r14
0x14002fd57  push    r15
0x14002fd59  sub     rsp, 68h
0x14002fd5d  mov     rax, rdx
0x14002fd60  mov     r15d, ecx
0x14002fd63  mov     rcx, rax; void *
0x14002fd66  mov     rdx, r8; void *
0x14002fd69  mov     bpl, r9b
0x14002fd6c  call    ?CheckCallbackParms@A2DP_Device@@CAPEAV1@PEAX0@Z; A2DP_Device::CheckCallbackParms(void *,void *)
0x14002fd71  mov     rbx, rax
0x14002fd74  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fd7b  lea     rax, WPP_GLOBAL_Control
0x14002fd82  cmp     rcx, rax
0x14002fd85  jz      short loc_14002FD99
0x14002fd87  mov     edx, [rcx+2Ch]
0x14002fd8a  test    dl, 10h
0x14002fd8d  jz      short loc_14002FD99
0x14002fd8f  cmp     byte ptr [rcx+29h], 4
0x14002fd93  jb      short loc_14002FD99
0x14002fd95  mov     dl, 1
0x14002fd97  jmp     short loc_14002FD9B
0x14002fd99  xor     dl, dl
0x14002fd9b  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fda2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fda9  setnz   r8b
0x14002fdad  test    dl, dl
0x14002fdaf  jnz     short loc_14002FDB6
0x14002fdb1  test    r8b, r8b
0x14002fdb4  jz      short loc_14002FDE8
0x14002fdb6  mov     r9, [rcx+40h]
0x14002fdba  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14002fdc1  mov     rcx, [rcx+18h]
0x14002fdc5  mov     [rsp+98h+var_58], rbx
0x14002fdca  mov     [rsp+98h+var_60], rax
0x14002fdcf  mov     [rsp+98h+var_68], 7Ah ; 'z'
0x14002fdd6  mov     [rsp+98h+var_70], 5
0x14002fdde  mov     [rsp+98h+var_78], 4
0x14002fde3  call    WPP_RECORDER_AND_TRACE_SF_q
0x14002fde8  mov     edx, 1Bh
0x14002fded  mov     rcx, rbx
0x14002fdf0  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14002fdf5  mov     rsi, [rsp+98h+arg_20]
0x14002fdfd  test    rsi, rsi
0x14002fe00  jz      short loc_14002FE6C
0x14002fe02  cmp     [rsp+98h+arg_28], 2
0x14002fe0a  jb      short loc_14002FE6C
0x14002fe0c  mov     rdi, [rbx+8]
0x14002fe10  lea     rdx, [rsp+98h+var_48]
0x14002fe15  mov     rcx, rdi
0x14002fe18  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x14002fe1d  mov     rcx, [rsp+98h+var_48]
0x14002fe22  test    rcx, rcx
0x14002fe25  jz      short loc_14002FE58
0x14002fe27  cmp     bpl, [rdi+69h]
0x14002fe2b  jnz     short loc_14002FE58
0x14002fe2d  mov     rax, [rcx]
0x14002fe30  mov     rdx, rsi
0x14002fe33  mov     r8d, [rsp+98h+arg_28]
0x14002fe3b  mov     rax, [rax+8]
0x14002fe3f  call    _guard_dispatch_icall
0x14002fe44  mov     rcx, [rsp+98h+var_40]; this
0x14002fe49  mov     sil, al
0x14002fe4c  test    rcx, rcx
0x14002fe4f  jz      short loc_14002FE6F
0x14002fe51  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002fe56  jmp     short loc_14002FE6F
0x14002fe58  mov     rcx, [rsp+98h+var_40]; this
0x14002fe5d  test    rcx, rcx
0x14002fe60  jz      short loc_14002FE67
0x14002fe62  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002fe67  mov     sil, 12h
0x14002fe6a  jmp     short loc_14002FE6F
0x14002fe6c  mov     sil, 29h ; ')'
0x14002fe6f  lea     rbp, [rbx+2B8h]
0x14002fe76  mov     rcx, rbp; SpinLock
0x14002fe79  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002fe80  nop     dword ptr [rax+rax+00h]
0x14002fe85  mov     rdi, [rbx+190h]
0x14002fe8c  mov     r14b, al
0x14002fe8f  test    rdi, rdi
0x14002fe92  jz      short loc_14002FEA3
0x14002fe94  mov     rax, [rbx+1A8h]
0x14002fe9b  mov     rcx, rdi
0x14002fe9e  call    _guard_dispatch_icall
0x14002fea3  mov     dl, r14b; NewIrql
0x14002fea6  mov     rcx, rbp; SpinLock
0x14002fea9  call    cs:__imp_KeReleaseSpinLock
0x14002feb0  nop     dword ptr [rax+rax+00h]
0x14002feb5  test    rdi, rdi
0x14002feb8  jz      short loc_14002FEEE
0x14002feba  mov     edx, 1Ch
0x14002febf  mov     rcx, rbx
0x14002fec2  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14002fec7  mov     rax, [rbx+248h]
0x14002fece  mov     r9b, sil
0x14002fed1  xor     r8d, r8d
0x14002fed4  mov     rdx, rdi
0x14002fed7  mov     ecx, r15d
0x14002feda  call    _guard_dispatch_icall
0x14002fedf  mov     rax, [rbx+1B0h]
0x14002fee6  mov     rcx, rdi
0x14002fee9  call    _guard_dispatch_icall
0x14002feee  xor     eax, eax
0x14002fef0  add     rsp, 68h
0x14002fef4  pop     r15
0x14002fef6  pop     r14
0x14002fef8  pop     rdi
0x14002fef9  pop     rsi
0x14002fefa  pop     rbp
0x14002fefb  pop     rbx
0x14002fefc  retn
```
