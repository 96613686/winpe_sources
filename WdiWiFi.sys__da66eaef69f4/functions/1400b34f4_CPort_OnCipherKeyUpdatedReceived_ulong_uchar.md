# CPort::OnCipherKeyUpdatedReceived(ulong,uchar *)

- ea: `0x1400b34f4`
- end: `0x1400b3783`
- name: `?OnCipherKeyUpdatedReceived@CPort@@QEAAXKPEAE@Z`
- size: `655`
- prototype: `void __fastcall(CPort *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000e2c0`

## callees

- `0x14000da4c`
- `0x1400122e0`
- `0x140023ae0`
- `0x14002aa28`
- `0x140034e04`
- `0x140034ec4`
- `0x14005ab8c`
- `0x14008d990`
- `0x140099e34`
- `0x1400ad434`
- `0x1400b34f4`
- `0x1400b7750`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400b360e`
- `ntoskrnl!ExAllocatePool2` at `0x1400b360e`

## pseudocode

```c
void __fastcall CPort::OnCipherKeyUpdatedReceived(CPort *this, int a2, unsigned __int8 *a3)
{
  int v4; // esi
  int v6; // eax
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // edx
  unsigned int v11; // edi
  void *Pool2; // rsi
  int v13; // r8d
  int v14; // r9d
  int v15; // edx
  int v16; // r8d
  int v17; // [rsp+20h] [rbp-59h]
  unsigned int v18[2]; // [rsp+28h] [rbp-51h]
  struct _WDI_RSN_OFFLOAD_KEYS_CONTAINER v19; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v20; // [rsp+E8h] [rbp+6Fh] BYREF

  *(_DWORD *)&v19.Optional &= ~1u;
  v4 = a2;
  v19.RsnKeyInfo.ProtocolOffloadId = 0;
  v19.RsnKeyInfo.ReplayCounter = 0;
  v19.RsnKeyInfo.KCK_CONTENT.ElementCount = 0;
  v19.RsnKeyInfo.KCK_CONTENT.pElements = 0;
  v19.RsnKeyInfo.KCK_CONTENT.MemoryInternallyAllocated = 0;
  v19.RsnKeyInfo.KEK_CONTENT.ElementCount = 0;
  v19.RsnKeyInfo.KEK_CONTENT.pElements = 0;
  v19.RsnKeyInfo.KEK_CONTENT.MemoryInternallyAllocated = 0;
  v19.CipherKey.ElementCount = 0;
  v19.CipherKey.pElements = 0;
  v19.CipherKey.MemoryInternallyAllocated = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      414,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  v6 = ParseWdiIndicationCipherKeyUpdatedFromIhv(
         (unsigned int)(v4 - 48),
         a3 + 48,
         &this->m_pAdapter->m_TlvContext,
         &v19);
  v9 = v6;
  if ( v6 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_23;
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      415,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      (char)this,
      this->m_WfcPortId,
      v6);
  }
  else
  {
    v11 = 52 * (v19.CipherKey.ElementCount + 2);
    v20 = v11;
    Pool2 = (void *)ExAllocatePool2(64, v11, 1198089303);
    if ( Pool2 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_ddidd(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          v13,
          v14,
          v17,
          v19.CipherKey.ElementCount,
          v19.RsnKeyInfo.ProtocolOffloadId,
          v19.RsnKeyInfo.ReplayCounter,
          v19.RsnKeyInfo.KCK_CONTENT.ElementCount,
          v19.RsnKeyInfo.KEK_CONTENT.ElementCount);
      v9 = CWabiToDot11Converter::MapCipherKeyParams(&v19, v11, &v20, Pool2);
      if ( v9 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qDDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            v16,
            418,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            (char)this,
            this->m_WfcPortId,
            v9,
            v20,
            v20);
      }
      else
      {
        CAdapter::IndicateStatus(this->m_pAdapter, this->m_NdisPortNumber, 1073938478, 0, Pool2, v20);
      }
      operator delete(Pool2);
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          v13,
          416,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          this->m_WfcPortId);
      }
      v9 = -1073741670;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v18[0] = v9;
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      419,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      *(_QWORD *)v18);
  }
LABEL_23:
  _WDI_RSN_OFFLOAD_KEYS_CONTAINER::~_WDI_RSN_OFFLOAD_KEYS_CONTAINER(&v19);
}

```

## disassembly

```asm
0x1400b34f4  mov     [rsp-8+arg_0], rbx
0x1400b34f9  mov     [rsp-8+arg_10], rsi
0x1400b34fe  push    rbp
0x1400b34ff  push    rdi
0x1400b3500  push    r12
0x1400b3502  push    r14
0x1400b3504  push    r15
0x1400b3506  lea     rbp, [rsp-37h]
0x1400b350b  sub     rsp, 0B0h
0x1400b3512  and     dword ptr [rbp+57h+var_80.Optional.CipherKey_IsPresent], 0FFFFFFFEh
0x1400b3516  mov     rdi, r8
0x1400b3519  xor     r14d, r14d
0x1400b351c  mov     esi, edx
0x1400b351e  mov     [rbp+57h+var_80.RsnKeyInfo.ProtocolOffloadId], r14d
0x1400b3522  mov     rbx, rcx
0x1400b3525  mov     [rbp+57h+var_80.RsnKeyInfo.ReplayCounter], r14
0x1400b3529  mov     [rbp+57h+var_80.RsnKeyInfo.KCK_CONTENT.ElementCount], r14d
0x1400b352d  mov     [rbp+57h+var_80.RsnKeyInfo.KCK_CONTENT.pElements], r14
0x1400b3531  mov     [rbp+57h+var_80.RsnKeyInfo.KCK_CONTENT.MemoryInternallyAllocated], r14b
0x1400b3535  mov     [rbp+57h+var_80.RsnKeyInfo.KEK_CONTENT.ElementCount], r14d
0x1400b3539  mov     [rbp+57h+var_80.RsnKeyInfo.KEK_CONTENT.pElements], r14
0x1400b353d  mov     [rbp+57h+var_80.RsnKeyInfo.KEK_CONTENT.MemoryInternallyAllocated], r14b
0x1400b3541  mov     [rbp+57h+var_80.CipherKey.ElementCount], r14d
0x1400b3545  mov     [rbp+57h+var_80.CipherKey.pElements], r14
0x1400b3549  mov     [rbp+57h+var_80.CipherKey.MemoryInternallyAllocated], r14b
0x1400b354d  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b3554  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400b355b  lea     r12, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b3562  jz      short loc_1400B3594
0x1400b3564  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b356b  cmp     byte ptr [rcx+29h], 5
0x1400b356f  jnb     short loc_1400B3578
0x1400b3571  cmp     [rcx+48h], r14w
0x1400b3576  jz      short loc_1400B3594
0x1400b3578  mov     rcx, [rcx+40h]
0x1400b357c  mov     r9d, 19Eh
0x1400b3582  mov     r8d, 1
0x1400b3588  mov     [rsp+0D0h+var_B0], r12
0x1400b358d  mov     dl, 5
0x1400b358f  call    WPP_RECORDER_SF_
0x1400b3594  mov     r8, [rbx+58h]
0x1400b3598  lea     rdx, [rdi+30h]
0x1400b359c  add     r8, 3FF8h
0x1400b35a3  lea     ecx, [rsi-30h]
0x1400b35a6  lea     r9, [rbp+57h+var_80]
0x1400b35aa  call    ParseWdiIndicationCipherKeyUpdatedFromIhv
0x1400b35af  mov     edi, eax
0x1400b35b1  test    eax, eax
0x1400b35b3  jz      short loc_1400B35F5
0x1400b35b5  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400b35bc  jz      loc_1400B375D
0x1400b35c2  movzx   ecx, word ptr [rbx+64h]
0x1400b35c6  mov     r9d, 19Fh
0x1400b35cc  mov     dword ptr [rsp+0D0h+var_98], eax
0x1400b35d0  mov     dl, 2
0x1400b35d2  mov     [rsp+0D0h+var_A0], ecx
0x1400b35d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b35dd  mov     qword ptr [rsp+0D0h+var_A8], rbx
0x1400b35e2  mov     [rsp+0D0h+var_B0], r12
0x1400b35e7  mov     rcx, [rcx+40h]
0x1400b35eb  call    WPP_RECORDER_SF_qDD
0x1400b35f0  jmp     loc_1400B3720
0x1400b35f5  mov     eax, [rbp+57h+var_80.CipherKey.ElementCount]
0x1400b35f8  mov     ecx, 40h ; '@'
0x1400b35fd  add     eax, 2
0x1400b3600  mov     r8d, 47696457h
0x1400b3606  imul    edi, eax, 34h ; '4'
0x1400b3609  mov     edx, edi
0x1400b360b  mov     [rbp+57h+arg_8], edi
0x1400b360e  call    cs:__imp_ExAllocatePool2
0x1400b3615  nop     dword ptr [rax+rax+00h]
0x1400b361a  mov     rsi, rax
0x1400b361d  test    rax, rax
0x1400b3620  jnz     short loc_1400B365F
0x1400b3622  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400b3629  jz      short loc_1400B3655
0x1400b362b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3632  mov     r9d, 1A0h
0x1400b3638  movzx   eax, word ptr [rbx+64h]
0x1400b363c  mov     dl, 2
0x1400b363e  mov     [rsp+0D0h+var_A0], eax
0x1400b3642  mov     qword ptr [rsp+0D0h+var_A8], rbx
0x1400b3647  mov     rcx, [rcx+40h]
0x1400b364b  mov     [rsp+0D0h+var_B0], r12
0x1400b3650  call    WPP_RECORDER_SF_qD
0x1400b3655  mov     edi, 0C000009Ah
0x1400b365a  jmp     loc_1400B3720
0x1400b365f  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400b3666  jz      short loc_1400B369D
0x1400b3668  mov     eax, [rbp+57h+var_80.RsnKeyInfo.KEK_CONTENT.ElementCount]
0x1400b366b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3672  mov     [rsp+0D0h+var_88], eax
0x1400b3676  mov     eax, [rbp+57h+var_80.RsnKeyInfo.KCK_CONTENT.ElementCount]
0x1400b3679  mov     [rsp+0D0h+var_90], eax
0x1400b367d  mov     rax, [rbp+57h+var_80.RsnKeyInfo.ReplayCounter]
0x1400b3681  mov     rcx, [rcx+40h]
0x1400b3685  mov     [rsp+0D0h+var_98], rax
0x1400b368a  mov     eax, [rbp+57h+var_80.RsnKeyInfo.ProtocolOffloadId]
0x1400b368d  mov     [rsp+0D0h+var_A0], eax
0x1400b3691  mov     eax, [rbp+57h+var_80.CipherKey.ElementCount]
0x1400b3694  mov     [rsp+0D0h+var_A8], eax
0x1400b3698  call    WPP_RECORDER_SF_ddidd
0x1400b369d  mov     r9, rsi; void *
0x1400b36a0  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x1400b36a4  mov     edx, edi; unsigned int
0x1400b36a6  lea     rcx, [rbp+57h+var_80]; struct _WDI_RSN_OFFLOAD_KEYS_CONTAINER *
0x1400b36aa  call    ?MapCipherKeyParams@CWabiToDot11Converter@@SAHPEAU_WDI_RSN_OFFLOAD_KEYS_CONTAINER@@IPEAIPEAX@Z; CWabiToDot11Converter::MapCipherKeyParams(_WDI_RSN_OFFLOAD_KEYS_CONTAINER *,uint,uint *,void *)
0x1400b36af  mov     edi, eax
0x1400b36b1  test    eax, eax
0x1400b36b3  jz      short loc_1400B36F7
0x1400b36b5  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400b36bc  jz      short loc_1400B3718
0x1400b36be  mov     eax, [rbp+57h+arg_8]
0x1400b36c1  mov     r9d, 1A2h
0x1400b36c7  movzx   ecx, word ptr [rbx+64h]
0x1400b36cb  mov     [rsp+0D0h+var_88], eax
0x1400b36cf  mov     [rsp+0D0h+var_90], eax
0x1400b36d3  mov     dword ptr [rsp+0D0h+var_98], edi
0x1400b36d7  mov     [rsp+0D0h+var_A0], ecx
0x1400b36db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b36e2  mov     qword ptr [rsp+0D0h+var_A8], rbx
0x1400b36e7  mov     [rsp+0D0h+var_B0], r12
0x1400b36ec  mov     rcx, [rcx+40h]
0x1400b36f0  call    WPP_RECORDER_SF_qDDdd
0x1400b36f5  jmp     short loc_1400B3718
0x1400b36f7  mov     eax, [rbp+57h+arg_8]
0x1400b36fa  xor     r9d, r9d; void *
0x1400b36fd  mov     edx, [rbx+60h]; unsigned int
0x1400b3700  mov     r8d, 4003002Eh; int
0x1400b3706  mov     rcx, [rbx+58h]; this
0x1400b370a  mov     [rsp+0D0h+var_A8], eax; unsigned int
0x1400b370e  mov     [rsp+0D0h+var_B0], rsi; void *
0x1400b3713  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x1400b3718  mov     rcx, rsi; void *
0x1400b371b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b3720  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400b3727  jz      short loc_1400B375D
0x1400b3729  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3730  cmp     byte ptr [rcx+29h], 5
0x1400b3734  jnb     short loc_1400B373D
0x1400b3736  cmp     [rcx+48h], r14w
0x1400b373b  jz      short loc_1400B375D
0x1400b373d  mov     rcx, [rcx+40h]
0x1400b3741  mov     r9d, 1A3h
0x1400b3747  mov     [rsp+0D0h+var_A8], edi
0x1400b374b  mov     r8d, 1
0x1400b3751  mov     dl, 5
0x1400b3753  mov     [rsp+0D0h+var_B0], r12
0x1400b3758  call    WPP_RECORDER_SF_D
0x1400b375d  lea     rcx, [rbp+57h+var_80]; this
0x1400b3761  call    ??1_WDI_RSN_OFFLOAD_KEYS_CONTAINER@@QEAA@XZ; _WDI_RSN_OFFLOAD_KEYS_CONTAINER::~_WDI_RSN_OFFLOAD_KEYS_CONTAINER(void)
0x1400b3766  lea     r11, [rsp+0D0h+var_20]
0x1400b376e  mov     rbx, [r11+30h]
0x1400b3772  mov     rsi, [r11+40h]
0x1400b3776  mov     rsp, r11
0x1400b3779  pop     r15
0x1400b377b  pop     r14
0x1400b377d  pop     r12
0x1400b377f  pop     rdi
0x1400b3780  pop     rbp
0x1400b3781  retn
```
