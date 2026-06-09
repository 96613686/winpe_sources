# A2DP_Device::AVDT_Open_Ind(long,void *,void *,uchar)

- ea: `0x14002fa70`
- end: `0x14002fc23`
- name: `?AVDT_Open_Ind@A2DP_Device@@CAJJPEAX0E@Z`
- size: `435`
- prototype: `static int(int, void *, void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003530`
- `0x140006380`
- `0x140006410`
- `0x140007374`
- `0x1400077e0`
- `0x140012b28`
- `0x140020a70`
- `0x14002d940`
- `0x14002fa70`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002fb78`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fb78`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fb48`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fb48`

## pseudocode

```c
__int64 __fastcall A2DP_Device::AVDT_Open_Ind(unsigned int a1, void *a2, void *a3, unsigned __int8 a4)
{
  int v4; // edi
  int v6; // edx
  struct A2DP_Device *v7; // rbx
  __int64 v8; // r8
  char v9; // di
  KIRQL v10; // al
  __int64 v11; // rsi
  KIRQL v12; // r14
  __int64 v13; // r8
  __int64 v14; // r8
  NTSTATUS v15; // edx
  __int64 v17; // [rsp+50h] [rbp-48h] BYREF
  utl::_RefCountBase *v18; // [rsp+58h] [rbp-40h]

  v4 = a4;
  v7 = A2DP_Device::CheckCallbackParms(a2, a3);
  LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      131,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)v7);
  A2DP_Device::SetLastAvdtpActivity(v7, 31, v8);
  if ( v4 != 36 && v4 != 52 && v4 != 54 && v4 != 55 )
  {
    if ( v4 != 56 )
    {
      v9 = 18;
      goto LABEL_17;
    }
    Feature_A2dpAptxAdaptive__private_IsEnabledPreCheck();
  }
  v9 = 0;
LABEL_17:
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 87);
  v11 = *((_QWORD *)v7 + 50);
  v12 = v10;
  if ( v11 )
    (*((void (__fastcall **)(_QWORD))v7 + 53))(*((_QWORD *)v7 + 50));
  KeReleaseSpinLock((PKSPIN_LOCK)v7 + 87, v12);
  if ( v11 )
  {
    A2DP_Device::SetLastAvdtpActivity(v7, 32, v13);
    LOBYTE(v14) = v9;
    (*((void (__fastcall **)(_QWORD, __int64, __int64))v7 + 75))(a1, v11, v14);
    (*((void (__fastcall **)(__int64))v7 + 54))(v11);
  }
  A2dpRole::GetCurrentSelectedCodec(*((_QWORD *)v7 + 1), &v17);
  if ( !v9 && v17 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v17 + 128LL))(v17) )
  {
    v15 = 0;
  }
  else
  {
    A2DP_Device::SetConnectionClosedUnlocked(v7);
    v15 = -1073741823;
  }
  IrpQueue::CompleteAllRequests((PIO_CSQ)((char *)v7 + 32), v15);
  if ( v18 )
    utl::_RefCountBase::_DecStrong(v18);
  return 0;
}

```

## disassembly

```asm
0x14002fa70  push    rbx
0x14002fa72  push    rbp
0x14002fa73  push    rsi
0x14002fa74  push    rdi
0x14002fa75  push    r14
0x14002fa77  push    r15
0x14002fa79  sub     rsp, 68h
0x14002fa7d  mov     rax, rdx
0x14002fa80  movzx   edi, r9b
0x14002fa84  mov     r15d, ecx
0x14002fa87  mov     rdx, r8; void *
0x14002fa8a  mov     rcx, rax; void *
0x14002fa8d  call    ?CheckCallbackParms@A2DP_Device@@CAPEAV1@PEAX0@Z; A2DP_Device::CheckCallbackParms(void *,void *)
0x14002fa92  mov     rbx, rax
0x14002fa95  mov     rax, cs:WPP_GLOBAL_Control
0x14002fa9c  lea     rcx, WPP_GLOBAL_Control
0x14002faa3  cmp     rax, rcx
0x14002faa6  jz      short loc_14002FABA
0x14002faa8  mov     ecx, [rax+2Ch]
0x14002faab  test    cl, 10h
0x14002faae  jz      short loc_14002FABA
0x14002fab0  cmp     byte ptr [rax+29h], 4
0x14002fab4  jb      short loc_14002FABA
0x14002fab6  mov     dl, 1
0x14002fab8  jmp     short loc_14002FABC
0x14002faba  xor     dl, dl
0x14002fabc  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002fac3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002faca  setnz   r8b
0x14002face  test    dl, dl
0x14002fad0  jnz     short loc_14002FAD7
0x14002fad2  test    r8b, r8b
0x14002fad5  jz      short loc_14002FB09
0x14002fad7  mov     r9, [rax+40h]
0x14002fadb  lea     rcx, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14002fae2  mov     [rsp+98h+var_58], rbx
0x14002fae7  mov     [rsp+98h+var_60], rcx
0x14002faec  mov     rcx, [rax+18h]
0x14002faf0  mov     [rsp+98h+var_68], 83h
0x14002faf7  mov     [rsp+98h+var_70], 5
0x14002faff  mov     [rsp+98h+var_78], 4
0x14002fb04  call    WPP_RECORDER_AND_TRACE_SF_q
0x14002fb09  mov     edx, 1Fh
0x14002fb0e  mov     rcx, rbx
0x14002fb11  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14002fb16  mov     ecx, edi
0x14002fb18  sub     ecx, 24h ; '$'
0x14002fb1b  jz      short loc_14002FB3B
0x14002fb1d  sub     ecx, 10h
0x14002fb20  jz      short loc_14002FB3B
0x14002fb22  sub     ecx, 2
0x14002fb25  jz      short loc_14002FB3B
0x14002fb27  sub     ecx, 1
0x14002fb2a  jz      short loc_14002FB3B
0x14002fb2c  cmp     ecx, 1
0x14002fb2f  jz      short loc_14002FB36
0x14002fb31  mov     dil, 12h
0x14002fb34  jmp     short loc_14002FB3E
0x14002fb36  call    Feature_A2dpAptxAdaptive__private_IsEnabledPreCheck
0x14002fb3b  xor     dil, dil
0x14002fb3e  lea     rbp, [rbx+2B8h]
0x14002fb45  mov     rcx, rbp; SpinLock
0x14002fb48  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002fb4f  nop     dword ptr [rax+rax+00h]
0x14002fb54  mov     rsi, [rbx+190h]
0x14002fb5b  mov     r14b, al
0x14002fb5e  test    rsi, rsi
0x14002fb61  jz      short loc_14002FB72
0x14002fb63  mov     rax, [rbx+1A8h]
0x14002fb6a  mov     rcx, rsi
0x14002fb6d  call    _guard_dispatch_icall
0x14002fb72  mov     dl, r14b; NewIrql
0x14002fb75  mov     rcx, rbp; SpinLock
0x14002fb78  call    cs:__imp_KeReleaseSpinLock
0x14002fb7f  nop     dword ptr [rax+rax+00h]
0x14002fb84  test    rsi, rsi
0x14002fb87  jz      short loc_14002FBBA
0x14002fb89  mov     edx, 20h ; ' '
0x14002fb8e  mov     rcx, rbx
0x14002fb91  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14002fb96  mov     rax, [rbx+258h]
0x14002fb9d  mov     r8b, dil
0x14002fba0  mov     rdx, rsi
0x14002fba3  mov     ecx, r15d
0x14002fba6  call    _guard_dispatch_icall
0x14002fbab  mov     rax, [rbx+1B0h]
0x14002fbb2  mov     rcx, rsi
0x14002fbb5  call    _guard_dispatch_icall
0x14002fbba  mov     rcx, [rbx+8]
0x14002fbbe  lea     rdx, [rsp+98h+var_48]
0x14002fbc3  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x14002fbc8  test    dil, dil
0x14002fbcb  jnz     short loc_14002FBEE
0x14002fbcd  mov     rcx, [rsp+98h+var_48]
0x14002fbd2  test    rcx, rcx
0x14002fbd5  jz      short loc_14002FBEE
0x14002fbd7  mov     rax, [rcx]
0x14002fbda  mov     rax, [rax+80h]
0x14002fbe1  call    _guard_dispatch_icall
0x14002fbe6  test    al, al
0x14002fbe8  jz      short loc_14002FBEE
0x14002fbea  xor     edx, edx
0x14002fbec  jmp     short loc_14002FBFB
0x14002fbee  mov     rcx, rbx; this
0x14002fbf1  call    ?SetConnectionClosedUnlocked@A2DP_Device@@AEAAXXZ; A2DP_Device::SetConnectionClosedUnlocked(void)
0x14002fbf6  mov     edx, 0C0000001h; int
0x14002fbfb  lea     rcx, [rbx+20h]; Csq
0x14002fbff  call    ?CompleteAllRequests@IrpQueue@@QEAAXJ@Z; IrpQueue::CompleteAllRequests(long)
0x14002fc04  mov     rcx, [rsp+98h+var_40]; this
0x14002fc09  test    rcx, rcx
0x14002fc0c  jz      short loc_14002FC13
0x14002fc0e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002fc13  xor     eax, eax
0x14002fc15  add     rsp, 68h
0x14002fc19  pop     r15
0x14002fc1b  pop     r14
0x14002fc1d  pop     rdi
0x14002fc1e  pop     rsi
0x14002fc1f  pop     rbp
0x14002fc20  pop     rbx
0x14002fc21  retn
```
