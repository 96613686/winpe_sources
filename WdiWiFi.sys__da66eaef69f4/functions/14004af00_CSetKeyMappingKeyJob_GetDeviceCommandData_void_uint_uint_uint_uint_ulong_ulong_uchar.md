# CSetKeyMappingKeyJob::GetDeviceCommandData(void *,uint,uint *,uint *,uint,ulong *,ulong *,uchar * *)

- ea: `0x14004af00`
- end: `0x14004b67a`
- name: `?GetDeviceCommandData@CSetKeyMappingKeyJob@@UEAAHPEAXIPEAI1IPEAK2PEAPEAE@Z`
- size: `1914`
- prototype: `__int64 __fastcall(CSetKeyMappingKeyJob *__hidden this, void *, unsigned int, unsigned int *, unsigned int *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1400122e0`
- `0x14001a808`
- `0x14001a8e0`
- `0x14001aedc`
- `0x140023ae0`
- `0x1400297a0`
- `0x14002aa28`
- `0x14004af00`
- `0x14004b680`
- `0x14004b6c4`
- `0x14004f5e8`
- `0x14008c9c8`
- `0x14008cc08`
- `0x1400ac754`
- `0x1400ae5e0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004b0ad`
- `ntoskrnl!ExAllocatePool2` at `0x14004b45e`
- `ntoskrnl!ExAllocatePool2` at `0x14004b0ad`
- `ntoskrnl!ExAllocatePool2` at `0x14004b45e`

## pseudocode

```c
__int64 __fastcall CSetKeyMappingKeyJob::GetDeviceCommandData(
        CSetKeyMappingKeyJob *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int8 **a9)
{
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v9; // rdi
  unsigned __int8 *v12; // rbx
  int v14; // r8d
  int v15; // edx
  unsigned int v16; // eax
  unsigned int v17; // edi
  unsigned int v18; // r14d
  unsigned int v19; // r12d
  _QWORD *v20; // rax
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int WdiSetAddCipherKeysToIhv; // eax
  int v24; // r9d
  _WDI_SET_DELETE_CIPHER_KEYS_CONTAINER *Pool2; // rax
  _WDI_SET_DELETE_CIPHER_KEYS_CONTAINER *v26; // rdi
  _WORD *v27; // rcx
  unsigned int v28; // eax
  unsigned int m_ActivityId; // [rsp+30h] [rbp-71h]
  __int64 v31; // [rsp+38h] [rbp-69h]
  unsigned int v32; // [rsp+38h] [rbp-69h]
  int v33; // [rsp+70h] [rbp-31h] BYREF
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v34; // [rsp+78h] [rbp-29h]
  char v35; // [rsp+80h] [rbp-21h]
  int v36; // [rsp+88h] [rbp-19h] BYREF
  void *v37; // [rsp+90h] [rbp-11h]
  char v38; // [rsp+98h] [rbp-9h]

  v9 = 0;
  v33 = 0;
  v34 = 0;
  v12 = a2;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      73,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  v14 = 1;
  *a4 = 0;
  *a5 = 0;
  v15 = *v12;
  if ( (_BYTE)v15 == 0x80 && v12[1] && *((_WORD *)v12 + 1) >= 0x10u )
  {
    v16 = *((_DWORD *)v12 + 1) + 12;
    *a5 = v16;
    if ( a3 < v16 )
    {
      v17 = -2147483643;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          1,
          75,
          (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
          (char)this,
          this->m_ActivityId,
          v16,
          a3);
      }
      goto LABEL_53;
    }
    v18 = *((_DWORD *)v12 + 1);
    if ( v18 < 0x14 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          1,
          79,
          (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
          (char)this,
          this->m_ActivityId);
      }
      goto LABEL_50;
    }
    v19 = *((unsigned __int16 *)v12 + 15) + 20;
    if ( v18 < v19 )
    {
      v17 = -1073676267;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          1,
          76,
          (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
          (char)this,
          this->m_ActivityId);
      }
      goto LABEL_53;
    }
    if ( v12[28] )
    {
      v36 = 1;
      *a7 = 30;
      Pool2 = (_WDI_SET_DELETE_CIPHER_KEYS_CONTAINER *)ExAllocatePool2(64, 32, 1198089303);
      v26 = Pool2;
      if ( Pool2 )
        _WDI_SET_DELETE_CIPHER_KEYS_CONTAINER::_WDI_SET_DELETE_CIPHER_KEYS_CONTAINER(Pool2);
      else
        v26 = 0;
      v37 = v26;
      v26->CipherKeyID.CipherKeyID = 0;
      *((_DWORD *)v37 + 4) = CDot11ToWabiConverter::MapCipherAlgorithm(*((enum _DOT11_CIPHER_ALGORITHM *)v12 + 5));
      *((_DWORD *)v37 + 5) = CDot11ToWabiConverter::MapP2PScanType(*((enum _DOT11_WFD_SCAN_TYPE *)v12 + 6));
      *((_DWORD *)v37 + 7) = 1;
      *((_BYTE *)v37 + 24) = v12[29];
      v27 = v37;
      *((_DWORD *)v37 + 1) = *((_DWORD *)v12 + 3);
      v27[4] = *((_WORD *)v12 + 8);
      v28 = GenerateWdiSetDeleteCipherKeysToIhv(
              (unsigned int)&v36,
              a6,
              (unsigned int)this->m_pAdapter + 16376,
              (_DWORD)a8,
              (__int64)a9);
      v17 = v28;
      if ( v28 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_53;
        v32 = v28;
        v24 = 78;
        m_ActivityId = this->m_ActivityId;
LABEL_39:
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          v14,
          v24,
          (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
          (char)this,
          m_ActivityId,
          v32);
        goto LABEL_53;
      }
      goto LABEL_46;
    }
    this->m_IsKeyAdded = 1;
    v33 = 1;
    *a7 = 29;
    v20 = (_QWORD *)ExAllocatePool2(64, 264, 1198089303);
    if ( v20 )
    {
      v9 = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER *)(v20 + 1);
      *v20 = 1;
      `vector constructor iterator'(
        v20 + 1,
        0x100u,
        1u,
        (void *(*)(void *))_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER);
    }
    v34 = v9;
    *(_DWORD *)&v9->Optional |= 1u;
    v34->PeerMacAddress = *(_WDI_MAC_ADDRESS *)(v12 + 2);
    v34->CipherKeyTypeInfo.KeyType = WDI_CIPHER_KEY_TYPE_PAIRWISE_KEY;
    v34->CipherKeyTypeInfo.CipherAlgorithm = CDot11ToWabiConverter::MapCipherAlgorithm(*((enum _DOT11_CIPHER_ALGORITHM *)v12
                                                                                       + 5));
    v34->CipherKeyTypeInfo.Direction = CDot11ToWabiConverter::MapP2PScanType(*((enum _DOT11_WFD_SCAN_TYPE *)v12 + 6));
    v34->CipherKeyTypeInfo.Static = v12[29];
    *(_DWORD *)&v34->Optional &= ~2u;
    v21 = *(_DWORD *)&v34->Optional & 0xFFFFFFBF;
    v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v21;
    v21 &= ~8u;
    v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v21;
    v21 &= ~0x10u;
    v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v21;
    v21 &= ~0x20u;
    v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v21;
    v21 &= ~0x80u;
    v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v21;
    v22 = v21 & 0xFFFFFEFF;
    v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)v22;
    v14 = *((_DWORD *)v12 + 5);
    if ( v14 != 1 )
    {
      if ( *((_DWORD *)v12 + 5) == 2 )
      {
        v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v22 | 4);
        v34->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(v12 + 32);
        *(_DWORD *)&v34->Optional |= 0x20u;
        v34->TKIPInfo.TKIPKey.ElementCount = *((_DWORD *)v12 + 10);
        v34->TKIPInfo.TKIPKey.pElements = v12 + 48;
        v34->TKIPInfo.TKIPMIC.ElementCount = *((_DWORD *)v12 + 11);
        v34->TKIPInfo.TKIPMIC.pElements = &v12[*((unsigned int *)v12 + 10) + 48];
        goto LABEL_36;
      }
      if ( *((_DWORD *)v12 + 5) == 4 )
      {
        v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v22 | 4);
        v34->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(v12 + 32);
        *(_DWORD *)&v34->Optional |= 8u;
        v34->CCMPKey.ElementCount = *((unsigned __int16 *)v12 + 20);
        v34->CCMPKey.pElements = v12 + 44;
        goto LABEL_36;
      }
      if ( *((_DWORD *)v12 + 5) != 5 )
      {
        switch ( *((_DWORD *)v12 + 5) )
        {
          case 6:
            v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v22 | 4);
            v34->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(v12 + 32);
            *(_DWORD *)&v34->Optional |= 0x40u;
            v34->BIPKey.ElementCount = *((unsigned __int16 *)v12 + 20);
            v34->BIPKey.pElements = v12 + 44;
            goto LABEL_36;
          case 8:
            v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v22 | 4);
            v34->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(v12 + 32);
            *(_DWORD *)&v34->Optional |= 0x10u;
            v34->GCMPKey.ElementCount = *((unsigned __int16 *)v12 + 20);
            v34->GCMPKey.pElements = v12 + 44;
            goto LABEL_36;
          case 9:
            v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v22 | 4);
            v34->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(v12 + 32);
            *(_DWORD *)&v34->Optional |= 0x200u;
            v34->GCMP_256Key.ElementCount = *((unsigned __int16 *)v12 + 20);
            v34->GCMP_256Key.pElements = v12 + 44;
            goto LABEL_36;
        }
        v15 = *((_DWORD *)v12 + 5) - 12;
        if ( *((_DWORD *)v12 + 5) == 12 )
        {
          v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v22 | 4);
          v34->ReceiveSequenceCount = *(_WDI_RECEIVE_SEQUENCE_COUNT_STRUCT *)(v12 + 32);
          *(_DWORD *)&v34->Optional |= 0x400u;
          v34->BIP_GMAC_256Key.ElementCount = *((unsigned __int16 *)v12 + 20);
          v34->BIP_GMAC_256Key.pElements = v12 + 44;
          goto LABEL_36;
        }
        if ( *((_DWORD *)v12 + 5) != 257 )
        {
          if ( v14 <= -1 )
          {
            v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v22 | 0x100);
            v34->IHVKey.ElementCount = *((unsigned __int16 *)v12 + 15);
            v34->IHVKey.pElements = v12 + 32;
            goto LABEL_36;
          }
LABEL_50:
          v17 = -1073676267;
          goto LABEL_53;
        }
      }
    }
    v34->Optional = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER_Optional)(v22 | 0x80);
    v34->WEPKey.ElementCount = *((unsigned __int16 *)v12 + 15);
    v34->WEPKey.pElements = v12 + 32;
LABEL_36:
    WdiSetAddCipherKeysToIhv = GenerateWdiSetAddCipherKeysToIhv(
                                 (unsigned int)&v33,
                                 a6,
                                 (unsigned int)this->m_pAdapter + 16376,
                                 (_DWORD)a8,
                                 (__int64)a9);
    v17 = WdiSetAddCipherKeysToIhv;
    if ( WdiSetAddCipherKeysToIhv )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_53;
      v24 = 77;
      v32 = WdiSetAddCipherKeysToIhv;
      m_ActivityId = this->m_ActivityId;
      goto LABEL_39;
    }
LABEL_46:
    *a4 = *a5;
    if ( v18 != v19 )
      v17 = -1073676267;
    goto LABEL_53;
  }
  v17 = -1073676267;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDDddddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      1,
      74,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      this->m_ActivityId,
      128,
      1,
      16,
      v15,
      v12[1],
      *((_WORD *)v12 + 1));
LABEL_53:
  if ( v34 )
    _WDI_SET_ADD_CIPHER_KEYS_CONTAINER::`vector deleting destructor'(v34, 3u);
  if ( v37 )
    operator delete(v37);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v15) = 5;
    LODWORD(v31) = v17;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      v14,
      80,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      this->m_ActivityId,
      v31);
  }
  ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(&v36);
  ArrayOfElements<_WDI_SET_ADD_CIPHER_KEYS_CONTAINER>::Cleanup(&v33);
  return v17;
}

```

## disassembly

```asm
0x14004af00  push    rbp
0x14004af02  push    rbx
0x14004af03  push    rsi
0x14004af04  push    rdi
0x14004af05  push    r12
0x14004af07  push    r13
0x14004af09  push    r14
0x14004af0b  push    r15
0x14004af0d  lea     rbp, [rsp-7]
0x14004af12  sub     rsp, 0A8h
0x14004af19  xor     edi, edi
0x14004af1b  mov     r13, r9
0x14004af1e  mov     [rbp+3Fh+var_70], edi
0x14004af21  mov     r14d, r8d
0x14004af24  mov     [rbp+3Fh+var_68], rdi
0x14004af28  mov     rbx, rdx
0x14004af2b  mov     [rbp+3Fh+var_60], dil
0x14004af2f  mov     rsi, rcx
0x14004af32  mov     [rbp+3Fh+var_58], edi
0x14004af35  mov     [rbp+3Fh+var_50], rdi
0x14004af39  mov     [rbp+3Fh+var_48], dil
0x14004af3d  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004af44  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14004af4b  lea     r10, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x14004af52  jz      short loc_14004AF97
0x14004af54  mov     rcx, cs:WPP_GLOBAL_Control
0x14004af5b  cmp     byte ptr [rcx+29h], 5
0x14004af5f  jnb     short loc_14004AF67
0x14004af61  cmp     [rcx+48h], di
0x14004af65  jz      short loc_14004AF90
0x14004af67  mov     eax, [rsi+10h]
0x14004af6a  mov     r9d, 49h ; 'I'
0x14004af70  mov     rcx, [rcx+40h]
0x14004af74  mov     dl, 5
0x14004af76  mov     [rsp+0E0h+var_B0], eax
0x14004af7a  mov     [rsp+0E0h+var_B8], rsi
0x14004af7f  mov     [rsp+0E0h+var_C0], r10
0x14004af84  call    WPP_RECORDER_SF_qD
0x14004af89  lea     r10, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x14004af90  lea     rcx, WPP_RECORDER_INITIALIZED
0x14004af97  mov     r15, [rbp+3Fh+arg_20]
0x14004af9b  mov     r8d, 1
0x14004afa1  mov     [r13+0], edi
0x14004afa5  mov     [r15], edi
0x14004afa8  lea     r11d, [r8+0Fh]
0x14004afac  movzx   edx, byte ptr [rbx]
0x14004afaf  cmp     dl, 80h
0x14004afb2  jnz     loc_14004B585
0x14004afb8  cmp     [rbx+1], r8b
0x14004afbc  jb      loc_14004B585
0x14004afc2  cmp     [rbx+2], r11w
0x14004afc7  jb      loc_14004B585
0x14004afcd  mov     eax, [rbx+4]
0x14004afd0  add     eax, 0Ch
0x14004afd3  mov     [r15], eax
0x14004afd6  cmp     r14d, eax
0x14004afd9  jnb     short loc_14004B022
0x14004afdb  mov     edi, 80000005h
0x14004afe0  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x14004afe7  jz      loc_14004B5E0
0x14004afed  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aff4  lea     r9d, [r8+4Ah]
0x14004aff8  mov     [rsp+0E0h+var_A0], r14d
0x14004affd  mov     dl, 2
0x14004afff  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14004b003  mov     eax, [rsi+10h]
0x14004b006  mov     rcx, [rcx+40h]
0x14004b00a  mov     [rsp+0E0h+var_B0], eax
0x14004b00e  mov     [rsp+0E0h+var_B8], rsi
0x14004b013  mov     [rsp+0E0h+var_C0], r10
0x14004b018  call    WPP_RECORDER_SF_qDdd
0x14004b01d  jmp     loc_14004B5E0
0x14004b022  mov     r14d, [rbx+4]
0x14004b026  cmp     r14d, 14h
0x14004b02a  jb      loc_14004B54C
0x14004b030  movzx   r12d, word ptr [rbx+1Eh]
0x14004b035  add     r12d, 14h
0x14004b039  cmp     r14d, r12d
0x14004b03c  jnb     short loc_14004B07E
0x14004b03e  mov     edi, 0C0010015h
0x14004b043  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x14004b04a  jz      loc_14004B5E0
0x14004b050  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b057  mov     r9d, 4Ch ; 'L'
0x14004b05d  mov     eax, [rsi+10h]
0x14004b060  mov     dl, 2
0x14004b062  mov     [rsp+0E0h+var_B0], eax
0x14004b066  mov     [rsp+0E0h+var_B8], rsi
0x14004b06b  mov     rcx, [rcx+40h]
0x14004b06f  mov     [rsp+0E0h+var_C0], r10
0x14004b074  call    WPP_RECORDER_SF_qD
0x14004b079  jmp     loc_14004B5E0
0x14004b07e  mov     ecx, 40h ; '@'
0x14004b083  mov     rax, [rbp+3Fh+arg_30]
0x14004b087  cmp     [rbx+1Ch], dil
0x14004b08b  jnz     loc_14004B449
0x14004b091  mov     [rsi+440h], r8b
0x14004b098  mov     edx, 108h
0x14004b09d  mov     [rbp+3Fh+var_70], r8d
0x14004b0a1  mov     r8d, 47696457h
0x14004b0a7  mov     dword ptr [rax], 1Dh
0x14004b0ad  call    cs:__imp_ExAllocatePool2
0x14004b0b4  nop     dword ptr [rax+rax+00h]
0x14004b0b9  test    rax, rax
0x14004b0bc  jz      short loc_14004B0E1
0x14004b0be  mov     ecx, 1
0x14004b0c3  lea     rdi, [rax+8]
0x14004b0c7  mov     [rax], rcx
0x14004b0ca  lea     r9, ??0_WDI_SET_ADD_CIPHER_KEYS_CONTAINER@@QEAA@XZ; void *(*)(void *)
0x14004b0d1  mov     r8d, ecx; unsigned __int64
0x14004b0d4  mov     edx, 100h; unsigned __int64
0x14004b0d9  mov     rcx, rdi; void *
0x14004b0dc  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14004b0e1  mov     [rbp+3Fh+var_68], rdi
0x14004b0e5  or      dword ptr [rdi], 1
0x14004b0e8  mov     rcx, [rbp+3Fh+var_68]
0x14004b0ec  mov     eax, [rbx+0Ch]
0x14004b0ef  mov     [rcx+4], eax
0x14004b0f2  movzx   eax, word ptr [rbx+10h]
0x14004b0f6  mov     [rcx+8], ax
0x14004b0fa  mov     rax, [rbp+3Fh+var_68]
0x14004b0fe  mov     dword ptr [rax+1Ch], 1
0x14004b105  mov     ecx, [rbx+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004b108  call    ?MapCipherAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_CIPHER_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@@Z; CDot11ToWabiConverter::MapCipherAlgorithm(_DOT11_CIPHER_ALGORITHM)
0x14004b10d  mov     r9d, eax
0x14004b110  mov     rax, [rbp+3Fh+var_68]
0x14004b114  mov     [rax+10h], r9d
0x14004b118  mov     ecx, [rbx+18h]; enum _DOT11_WFD_SCAN_TYPE
0x14004b11b  call    ?MapP2PScanType@CDot11ToWabiConverter@@SA?AW4_WDI_P2P_SCAN_TYPE@@W4_DOT11_WFD_SCAN_TYPE@@@Z; CDot11ToWabiConverter::MapP2PScanType(_DOT11_WFD_SCAN_TYPE)
0x14004b120  mov     edx, eax
0x14004b122  mov     rax, [rbp+3Fh+var_68]
0x14004b126  mov     [rax+14h], edx
0x14004b129  mov     rax, [rbp+3Fh+var_68]
0x14004b12d  mov     cl, [rbx+1Dh]
0x14004b130  mov     [rax+18h], cl
0x14004b133  mov     rax, [rbp+3Fh+var_68]
0x14004b137  and     dword ptr [rax], 0FFFFFFFDh
0x14004b13a  mov     rax, [rbp+3Fh+var_68]
0x14004b13e  mov     ecx, [rax]
0x14004b140  and     ecx, 0FFFFFFBFh
0x14004b143  mov     [rax], ecx
0x14004b145  and     ecx, 0FFFFFFF7h
0x14004b148  mov     rax, [rbp+3Fh+var_68]
0x14004b14c  mov     [rax], ecx
0x14004b14e  and     ecx, 0FFFFFFEFh
0x14004b151  mov     rax, [rbp+3Fh+var_68]
0x14004b155  mov     [rax], ecx
0x14004b157  and     ecx, 0FFFFFFDFh
0x14004b15a  mov     rax, [rbp+3Fh+var_68]
0x14004b15e  mov     [rax], ecx
0x14004b160  btr     ecx, 7
0x14004b164  mov     rax, [rbp+3Fh+var_68]
0x14004b168  mov     [rax], ecx
0x14004b16a  btr     ecx, 8
0x14004b16e  mov     rax, [rbp+3Fh+var_68]
0x14004b172  mov     [rax], ecx
0x14004b174  mov     r8d, [rbx+14h]
0x14004b178  mov     edx, r8d
0x14004b17b  sub     edx, 1
0x14004b17e  jz      loc_14004B39E
0x14004b184  sub     edx, 1
0x14004b187  jz      loc_14004B348
0x14004b18d  sub     edx, 2
0x14004b190  jz      loc_14004B30D
0x14004b196  sub     edx, 1
0x14004b199  jz      loc_14004B39E
0x14004b19f  sub     edx, 1
0x14004b1a2  jz      loc_14004B2C9
0x14004b1a8  sub     edx, 2
0x14004b1ab  jz      loc_14004B28B
0x14004b1b1  sub     edx, 1
0x14004b1b4  jz      loc_14004B246
0x14004b1ba  sub     edx, 3
0x14004b1bd  jz      short loc_14004B201
0x14004b1bf  cmp     edx, 0F5h
0x14004b1c5  jz      loc_14004B39E
0x14004b1cb  cmp     r8d, 0FFFFFFFFh
0x14004b1cf  jg      loc_14004B57E
0x14004b1d5  mov     rax, [rbp+3Fh+var_68]
0x14004b1d9  bts     ecx, 8
0x14004b1dd  mov     [rax], ecx
0x14004b1df  mov     rax, [rbp+3Fh+var_68]
0x14004b1e3  movzx   ecx, word ptr [rbx+1Eh]
0x14004b1e7  mov     [rax+0B8h], ecx
0x14004b1ed  lea     rcx, [rbx+20h]
0x14004b1f1  mov     rax, [rbp+3Fh+var_68]
0x14004b1f5  mov     [rax+0C0h], rcx
0x14004b1fc  jmp     loc_14004B3C5
0x14004b201  mov     rax, [rbp+3Fh+var_68]
0x14004b205  or      ecx, 4
0x14004b208  mov     [rax], ecx
0x14004b20a  mov     rcx, [rbp+3Fh+var_68]
0x14004b20e  mov     eax, [rbx+20h]
0x14004b211  mov     [rcx+20h], eax
0x14004b214  movzx   eax, word ptr [rbx+24h]
0x14004b218  mov     [rcx+24h], ax
0x14004b21c  mov     rax, [rbp+3Fh+var_68]
0x14004b220  bts     dword ptr [rax], 0Ah
0x14004b224  mov     rax, [rbp+3Fh+var_68]
0x14004b228  movzx   ecx, word ptr [rbx+28h]
0x14004b22c  mov     [rax+0E8h], ecx
0x14004b232  lea     rcx, [rbx+2Ch]
0x14004b236  mov     rax, [rbp+3Fh+var_68]
0x14004b23a  mov     [rax+0F0h], rcx
0x14004b241  jmp     loc_14004B3C5
0x14004b246  mov     rax, [rbp+3Fh+var_68]
0x14004b24a  or      ecx, 4
0x14004b24d  mov     [rax], ecx
0x14004b24f  mov     rcx, [rbp+3Fh+var_68]
0x14004b253  mov     eax, [rbx+20h]
0x14004b256  mov     [rcx+20h], eax
0x14004b259  movzx   eax, word ptr [rbx+24h]
0x14004b25d  mov     [rcx+24h], ax
0x14004b261  mov     rax, [rbp+3Fh+var_68]
0x14004b265  bts     dword ptr [rax], 9
0x14004b269  mov     rax, [rbp+3Fh+var_68]
0x14004b26d  movzx   ecx, word ptr [rbx+28h]
0x14004b271  mov     [rax+0D0h], ecx
0x14004b277  lea     rcx, [rbx+2Ch]
0x14004b27b  mov     rax, [rbp+3Fh+var_68]
0x14004b27f  mov     [rax+0D8h], rcx
0x14004b286  jmp     loc_14004B3C5
0x14004b28b  mov     rax, [rbp+3Fh+var_68]
0x14004b28f  or      ecx, 4
0x14004b292  mov     [rax], ecx
0x14004b294  mov     rcx, [rbp+3Fh+var_68]
0x14004b298  mov     eax, [rbx+20h]
0x14004b29b  mov     [rcx+20h], eax
0x14004b29e  movzx   eax, word ptr [rbx+24h]
0x14004b2a2  mov     [rcx+24h], ax
0x14004b2a6  mov     rax, [rbp+3Fh+var_68]
0x14004b2aa  or      dword ptr [rax], 10h
0x14004b2ad  mov     rax, [rbp+3Fh+var_68]
0x14004b2b1  movzx   ecx, word ptr [rbx+28h]
0x14004b2b5  mov     [rax+40h], ecx
0x14004b2b8  lea     rcx, [rbx+2Ch]
0x14004b2bc  mov     rax, [rbp+3Fh+var_68]
0x14004b2c0  mov     [rax+48h], rcx
0x14004b2c4  jmp     loc_14004B3C5
0x14004b2c9  mov     rax, [rbp+3Fh+var_68]
0x14004b2cd  or      ecx, 4
0x14004b2d0  mov     [rax], ecx
0x14004b2d2  mov     rcx, [rbp+3Fh+var_68]
0x14004b2d6  mov     eax, [rbx+20h]
0x14004b2d9  mov     [rcx+20h], eax
0x14004b2dc  movzx   eax, word ptr [rbx+24h]
0x14004b2e0  mov     [rcx+24h], ax
0x14004b2e4  mov     rax, [rbp+3Fh+var_68]
0x14004b2e8  or      dword ptr [rax], 40h
0x14004b2eb  mov     rax, [rbp+3Fh+var_68]
0x14004b2ef  movzx   ecx, word ptr [rbx+28h]
0x14004b2f3  mov     [rax+88h], ecx
0x14004b2f9  lea     rcx, [rbx+2Ch]
0x14004b2fd  mov     rax, [rbp+3Fh+var_68]
0x14004b301  mov     [rax+90h], rcx
0x14004b308  jmp     loc_14004B3C5
0x14004b30d  mov     rax, [rbp+3Fh+var_68]
0x14004b311  or      ecx, 4
0x14004b314  mov     [rax], ecx
0x14004b316  mov     rcx, [rbp+3Fh+var_68]
0x14004b31a  mov     eax, [rbx+20h]
0x14004b31d  mov     [rcx+20h], eax
0x14004b320  movzx   eax, word ptr [rbx+24h]
0x14004b324  mov     [rcx+24h], ax
0x14004b328  mov     rax, [rbp+3Fh+var_68]
0x14004b32c  or      dword ptr [rax], 8
0x14004b32f  mov     rax, [rbp+3Fh+var_68]
0x14004b333  movzx   ecx, word ptr [rbx+28h]
0x14004b337  mov     [rax+28h], ecx
0x14004b33a  lea     rcx, [rbx+2Ch]
0x14004b33e  mov     rax, [rbp+3Fh+var_68]
0x14004b342  mov     [rax+30h], rcx
0x14004b346  jmp     short loc_14004B3C5
0x14004b348  mov     rax, [rbp+3Fh+var_68]
0x14004b34c  or      ecx, 4
0x14004b34f  mov     [rax], ecx
0x14004b351  mov     rcx, [rbp+3Fh+var_68]
0x14004b355  mov     eax, [rbx+20h]
0x14004b358  mov     [rcx+20h], eax
0x14004b35b  movzx   eax, word ptr [rbx+24h]
0x14004b35f  mov     [rcx+24h], ax
0x14004b363  mov     rax, [rbp+3Fh+var_68]
0x14004b367  or      dword ptr [rax], 20h
0x14004b36a  mov     rax, [rbp+3Fh+var_68]
0x14004b36e  mov     ecx, [rbx+28h]
0x14004b371  mov     [rax+58h], ecx
0x14004b374  lea     rcx, [rbx+30h]
0x14004b378  mov     rax, [rbp+3Fh+var_68]
0x14004b37c  mov     [rax+60h], rcx
0x14004b380  mov     rax, [rbp+3Fh+var_68]
0x14004b384  mov     ecx, [rbx+2Ch]
0x14004b387  mov     [rax+70h], ecx
0x14004b38a  mov     ecx, [rbx+28h]
0x14004b38d  mov     rax, [rbp+3Fh+var_68]
0x14004b391  add     rcx, 30h ; '0'
0x14004b395  add     rcx, rbx
0x14004b398  mov     [rax+78h], rcx
0x14004b39c  jmp     short loc_14004B3C5
0x14004b39e  mov     rax, [rbp+3Fh+var_68]
0x14004b3a2  bts     ecx, 7
  ... truncated ...
```
