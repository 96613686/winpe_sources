# A2DP_Device::AVDT_SetConfiguration_Ind(long,void *,void *,uchar,uchar,_AVDTP_CATEGORY_HEADER const *,ulong)

- ea: `0x140020c00`
- end: `0x140020f09`
- name: `?AVDT_SetConfiguration_Ind@A2DP_Device@@CAJJPEAX0EEPEBU_AVDTP_CATEGORY_HEADER@@K@Z`
- size: `777`
- prototype: `__int64 __fastcall(unsigned int, void *, void *, unsigned __int8, unsigned __int8, const struct _AVDTP_CATEGORY_HEADER *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callees

- `0x140003530`
- `0x140006380`
- `0x140006410`
- `0x140007374`
- `0x1400077e0`
- `0x14001b270`
- `0x140020c00`
- `0x140020f10`
- `0x14002bac4`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140020e1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020e1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020ded`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020ded`

## pseudocode

```c
__int64 __fastcall A2DP_Device::AVDT_SetConfiguration_Ind(
        unsigned int a1,
        void *a2,
        void *a3,
        unsigned __int8 a4,
        unsigned __int8 a5,
        const struct _AVDTP_CATEGORY_HEADER *a6,
        unsigned int a7)
{
  char v7; // r14
  int v9; // edx
  struct A2DP_Device *v10; // rsi
  __int64 v11; // r8
  char v12; // bp
  A2dpRole *v13; // rcx
  unsigned __int8 v14; // al
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdi
  int v18; // ebx
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // r8
  KIRQL v22; // al
  __int64 v23; // rdi
  KIRQL v24; // r13
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // rcx
  _QWORD *CurrentSelectedCodec; // rax
  bool v30; // bl
  void (__fastcall *v31)(void *, __int64, _QWORD); // rbx
  unsigned __int16 Delay; // ax
  __int64 v33; // rdx
  unsigned int v35; // [rsp+20h] [rbp-88h]
  int v36; // [rsp+28h] [rbp-80h]
  int v37; // [rsp+38h] [rbp-70h]
  _BYTE v38[4]; // [rsp+58h] [rbp-50h] BYREF
  int v39; // [rsp+5Ch] [rbp-4Ch]
  __int16 v40; // [rsp+60h] [rbp-48h]
  __int64 v41; // [rsp+68h] [rbp-40h] BYREF
  utl::_RefCountBase *v42; // [rsp+70h] [rbp-38h]

  v7 = 0;
  v10 = A2DP_Device::CheckCallbackParms(a2, a3);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(v9) = 0;
  }
  LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      v11,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      117,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)v10);
  A2DP_Device::SetLastAvdtpActivity(v10, 19, v11);
  v12 = 41;
  if ( a6 )
  {
    if ( a7 >= 2 )
    {
      v13 = (A2dpRole *)*((_QWORD *)v10 + 1);
      if ( v13 )
      {
        v14 = A2dpRole::SetCodecConfiguration(v13, a4, a5, a6, a7);
        v12 = v14;
        if ( v14 )
        {
          LOBYTE(v16) = a5;
          LOBYTE(v15) = a4;
          LOWORD(v37) = 0;
          LOBYTE(v36) = 0;
          LOBYTE(v35) = v14;
          A2DP_Device::LogAvdtpSetConfigurationInfo(v10, 20, v15, v16, v35, v36, 0, v37, 0, 0, 0);
        }
        else
        {
          A2dpRole::GetCurrentSelectedCodec(*((_QWORD *)v10 + 1), &v41);
          v17 = v41;
          *(_WORD *)(v41 + 10) = 0;
          _mm_mfence();
          (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v17 + 88LL))(v17, v38);
          v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 104LL))(v17);
          v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 96LL))(v17);
          LOBYTE(v20) = a5;
          LOBYTE(v21) = a4;
          LOWORD(v37) = v40;
          LOBYTE(v36) = v38[0];
          LOBYTE(v35) = 0;
          A2DP_Device::LogAvdtpSetConfigurationInfo(v10, 20, v21, v20, v35, v36, v39, v37, v19, v18, 0);
          if ( v42 )
            utl::_RefCountBase::_DecStrong(v42);
        }
      }
    }
  }
  v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v10 + 87);
  v23 = *((_QWORD *)v10 + 50);
  v24 = v22;
  if ( v23 )
    (*((void (__fastcall **)(_QWORD))v10 + 53))(*((_QWORD *)v10 + 50));
  KeReleaseSpinLock((PKSPIN_LOCK)v10 + 87, v24);
  if ( v23 )
  {
    A2DP_Device::SetLastAvdtpActivity(v10, 20, v25);
    LOBYTE(v26) = v12;
    LOBYTE(v27) = a4;
    (*((void (__fastcall **)(_QWORD, __int64, __int64, __int64))v10 + 67))(a1, v23, v27, v26);
    v30 = 0;
    if ( !v12 )
    {
      v28 = *((_QWORD *)v10 + 1);
      if ( *(_BYTE *)(v28 + 89) )
      {
        CurrentSelectedCodec = (_QWORD *)A2dpRole::GetCurrentSelectedCodec(v28, &v41);
        v7 = 1;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*CurrentSelectedCodec + 184LL))(*CurrentSelectedCodec) )
          v30 = 1;
      }
    }
    if ( (v7 & 1) != 0 && v42 )
      utl::_RefCountBase::_DecStrong(v42);
    if ( v30 )
    {
      v31 = (void (__fastcall *)(void *, __int64, _QWORD))*((_QWORD *)v10 + 68);
      Delay = A2dpRole::GetDelay(*((A2dpRole **)v10 + 1));
      LOBYTE(v33) = a5;
      v31(a2, v33, Delay);
    }
    (*((void (__fastcall **)(__int64))v10 + 54))(v23);
  }
  return 0;
}

```

## disassembly

```asm
0x140020c00  mov     rax, rsp
0x140020c03  mov     [rax+18h], rbx
0x140020c07  mov     [rax+20h], rbp
0x140020c0b  mov     [rax+10h], rdx
0x140020c0f  mov     [rax+8], ecx
0x140020c12  push    rsi
0x140020c13  push    rdi
0x140020c14  push    r12
0x140020c16  push    r13
0x140020c18  push    r14
0x140020c1a  sub     rsp, 80h
0x140020c21  xor     r13d, r13d
0x140020c24  mov     rcx, rdx; void *
0x140020c27  mov     rdx, r8; void *
0x140020c2a  mov     [rsp+0A8h+var_58], r13d
0x140020c2f  mov     r14d, r13d
0x140020c32  mov     r12b, r9b
0x140020c35  call    ?CheckCallbackParms@A2DP_Device@@CAPEAV1@PEAX0@Z; A2DP_Device::CheckCallbackParms(void *,void *)
0x140020c3a  mov     rsi, rax
0x140020c3d  mov     rax, cs:WPP_GLOBAL_Control
0x140020c44  lea     rcx, WPP_GLOBAL_Control
0x140020c4b  cmp     rax, rcx
0x140020c4e  jz      short loc_140020C60
0x140020c50  mov     ecx, [rax+2Ch]
0x140020c53  test    cl, 10h
0x140020c56  jz      short loc_140020C60
0x140020c58  cmp     byte ptr [rax+29h], 4
0x140020c5c  mov     dl, 1
0x140020c5e  jnb     short loc_140020C63
0x140020c60  mov     dl, r13b
0x140020c63  lea     rcx, WPP_RECORDER_INITIALIZED
0x140020c6a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140020c71  setnz   r8b
0x140020c75  test    dl, dl
0x140020c77  jnz     short loc_140020C7E
0x140020c79  test    r8b, r8b
0x140020c7c  jz      short loc_140020CB0
0x140020c7e  mov     r9, [rax+40h]
0x140020c82  lea     rcx, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x140020c89  mov     [rsp+0A8h+var_68], rsi
0x140020c8e  mov     [rsp+0A8h+var_70], rcx
0x140020c93  mov     rcx, [rax+18h]
0x140020c97  mov     word ptr [rsp+0A8h+var_78], 75h ; 'u'
0x140020c9e  mov     [rsp+0A8h+var_80], 5
0x140020ca6  mov     byte ptr [rsp+0A8h+var_88], 4
0x140020cab  call    WPP_RECORDER_AND_TRACE_SF_q
0x140020cb0  mov     edx, 13h
0x140020cb5  mov     rcx, rsi
0x140020cb8  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x140020cbd  mov     r9, [rsp+0A8h+arg_28]; struct _AVDTP_CATEGORY_HEADER *
0x140020cc5  mov     bpl, 29h ; ')'
0x140020cc8  test    r9, r9
0x140020ccb  jz      loc_140020DE3
0x140020cd1  mov     eax, [rsp+0A8h+arg_30]
0x140020cd8  cmp     eax, 2
0x140020cdb  jb      loc_140020DE3
0x140020ce1  mov     rcx, [rsi+8]; this
0x140020ce5  test    rcx, rcx
0x140020ce8  jz      loc_140020DE3
0x140020cee  mov     r8b, [rsp+0A8h+arg_20]; unsigned __int8
0x140020cf6  mov     dl, r12b; unsigned __int8
0x140020cf9  mov     [rsp+0A8h+var_88], eax; unsigned int
0x140020cfd  call    ?SetCodecConfiguration@A2dpRole@@QEAAEEEPEBU_AVDTP_CATEGORY_HEADER@@K@Z; A2dpRole::SetCodecConfiguration(uchar,uchar,_AVDTP_CATEGORY_HEADER const *,ulong)
0x140020d02  mov     bpl, al
0x140020d05  test    al, al
0x140020d07  jnz     loc_140020DAD
0x140020d0d  mov     rcx, [rsi+8]
0x140020d11  lea     rdx, [rsp+0A8h+var_40]
0x140020d16  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x140020d1b  mov     rdi, [rsp+0A8h+var_40]
0x140020d20  nop
0x140020d21  mov     [rdi+0Ah], r13w
0x140020d26  mfence
0x140020d29  mov     rcx, [rdi]
0x140020d2c  lea     rdx, [rsp+0A8h+var_50]
0x140020d31  mov     rax, [rcx+58h]
0x140020d35  mov     rcx, rdi
0x140020d38  call    _guard_dispatch_icall
0x140020d3d  mov     rax, [rdi]
0x140020d40  mov     rcx, rdi
0x140020d43  mov     rax, [rax+68h]
0x140020d47  call    _guard_dispatch_icall
0x140020d4c  mov     rdx, [rdi]
0x140020d4f  mov     ebx, eax
0x140020d51  mov     rcx, rdi
0x140020d54  mov     rax, [rdx+60h]
0x140020d58  call    _guard_dispatch_icall
0x140020d5d  mov     r9b, [rsp+0A8h+arg_20]
0x140020d65  mov     r8b, r12b
0x140020d68  mov     [rsp+0A8h+var_60], ebx
0x140020d6c  mov     edx, 14h
0x140020d71  mov     dword ptr [rsp+0A8h+var_68], eax
0x140020d75  mov     rcx, rsi
0x140020d78  movzx   eax, [rsp+0A8h+var_48]
0x140020d7d  mov     word ptr [rsp+0A8h+var_70], ax
0x140020d82  mov     eax, [rsp+0A8h+var_4C]
0x140020d86  mov     [rsp+0A8h+var_78], eax
0x140020d8a  mov     al, [rsp+0A8h+var_50]
0x140020d8e  mov     byte ptr [rsp+0A8h+var_80], al
0x140020d92  mov     byte ptr [rsp+0A8h+var_88], r13b
0x140020d97  call    ?LogAvdtpSetConfigurationInfo@A2DP_Device@@AEAAXW4LastAvdtpActivity@@EEEEIGHH@Z; A2DP_Device::LogAvdtpSetConfigurationInfo(LastAvdtpActivity,uchar,uchar,uchar,uchar,uint,ushort,int,int)
0x140020d9c  mov     rcx, [rsp+0A8h+var_38]; this
0x140020da1  test    rcx, rcx
0x140020da4  jz      short loc_140020DE3
0x140020da6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140020dab  jmp     short loc_140020DE3
0x140020dad  mov     r9b, [rsp+0A8h+arg_20]
0x140020db5  mov     r8b, r12b
0x140020db8  mov     [rsp+0A8h+var_60], r13d
0x140020dbd  mov     edx, 14h
0x140020dc2  mov     dword ptr [rsp+0A8h+var_68], r13d
0x140020dc7  mov     rcx, rsi
0x140020dca  mov     word ptr [rsp+0A8h+var_70], r13w
0x140020dd0  mov     [rsp+0A8h+var_78], r13d
0x140020dd5  mov     byte ptr [rsp+0A8h+var_80], r13b
0x140020dda  mov     byte ptr [rsp+0A8h+var_88], al
0x140020dde  call    ?LogAvdtpSetConfigurationInfo@A2DP_Device@@AEAAXW4LastAvdtpActivity@@EEEEIGHH@Z; A2DP_Device::LogAvdtpSetConfigurationInfo(LastAvdtpActivity,uchar,uchar,uchar,uchar,uint,ushort,int,int)
0x140020de3  lea     rbx, [rsi+2B8h]
0x140020dea  mov     rcx, rbx; SpinLock
0x140020ded  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140020df4  nop     dword ptr [rax+rax+00h]
0x140020df9  mov     rdi, [rsi+190h]
0x140020e00  mov     r13b, al
0x140020e03  test    rdi, rdi
0x140020e06  jz      short loc_140020E17
0x140020e08  mov     rax, [rsi+1A8h]
0x140020e0f  mov     rcx, rdi
0x140020e12  call    _guard_dispatch_icall
0x140020e17  mov     dl, r13b; NewIrql
0x140020e1a  mov     rcx, rbx; SpinLock
0x140020e1d  call    cs:__imp_KeReleaseSpinLock
0x140020e24  nop     dword ptr [rax+rax+00h]
0x140020e29  test    rdi, rdi
0x140020e2c  jz      loc_140020EEA
0x140020e32  mov     edx, 14h
0x140020e37  mov     rcx, rsi
0x140020e3a  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x140020e3f  mov     rax, [rsi+218h]
0x140020e46  mov     r9b, bpl
0x140020e49  mov     ecx, [rsp+0A8h+arg_0]
0x140020e50  mov     r8b, r12b
0x140020e53  mov     rdx, rdi
0x140020e56  call    _guard_dispatch_icall
0x140020e5b  test    bpl, bpl
0x140020e5e  jnz     short loc_140020E95
0x140020e60  mov     rcx, [rsi+8]
0x140020e64  cmp     [rcx+59h], r14b
0x140020e68  jz      short loc_140020E95
0x140020e6a  lea     rdx, [rsp+0A8h+var_40]
0x140020e6f  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x140020e74  mov     r14d, 1
0x140020e7a  mov     rcx, [rax]
0x140020e7d  mov     rax, [rcx]
0x140020e80  mov     rax, [rax+0B8h]
0x140020e87  call    _guard_dispatch_icall
0x140020e8c  test    al, al
0x140020e8e  jz      short loc_140020E95
0x140020e90  mov     bl, r14b
0x140020e93  jmp     short loc_140020E97
0x140020e95  xor     bl, bl
0x140020e97  test    r14b, 1
0x140020e9b  jz      short loc_140020EAC
0x140020e9d  mov     rcx, [rsp+0A8h+var_38]; this
0x140020ea2  test    rcx, rcx
0x140020ea5  jz      short loc_140020EAC
0x140020ea7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140020eac  test    bl, bl
0x140020eae  jz      short loc_140020EDB
0x140020eb0  mov     rcx, [rsi+8]; this
0x140020eb4  mov     rbx, [rsi+220h]
0x140020ebb  call    ?GetDelay@A2dpRole@@QEAAGXZ; A2dpRole::GetDelay(void)
0x140020ec0  mov     dl, [rsp+0A8h+arg_20]
0x140020ec7  movzx   r8d, ax
0x140020ecb  mov     rcx, [rsp+0A8h+arg_8]
0x140020ed3  mov     rax, rbx
0x140020ed6  call    _guard_dispatch_icall
0x140020edb  mov     rax, [rsi+1B0h]
0x140020ee2  mov     rcx, rdi
0x140020ee5  call    _guard_dispatch_icall
0x140020eea  lea     r11, [rsp+0A8h+var_28]
0x140020ef2  xor     eax, eax
0x140020ef4  mov     rbx, [r11+40h]
0x140020ef8  mov     rbp, [r11+48h]
0x140020efc  mov     rsp, r11
0x140020eff  pop     r14
0x140020f01  pop     r13
0x140020f03  pop     r12
0x140020f05  pop     rdi
0x140020f06  pop     rsi
0x140020f07  retn
```
