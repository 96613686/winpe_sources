# CAdapter::SimulateFirmwareHang(ulong)

- ea: `0x1400a36d8`
- end: `0x1400a38f1`
- name: `?SimulateFirmwareHang@CAdapter@@QEAAHK@Z`
- size: `537`
- prototype: `__int64 __fastcall(CAdapter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140077e34`

## callees

- `0x140012214`
- `0x1400176b0`
- `0x140034e04`
- `0x140034ec4`
- `0x14007c428`
- `0x1400a36d8`

## import_xrefs

- `NDIS!NdisCloseConfiguration` at `0x1400a38ce`
- `NDIS!NdisCloseConfiguration` at `0x1400a38ce`

## pseudocode

```c
__int64 __fastcall CAdapter::SimulateFirmwareHang(CAdapter *this)
{
  void *m_MiniportAdapterHandle; // rax
  signed int v2; // ebx
  unsigned int m_HungResetRecoveryIterations; // r10d
  unsigned int v5; // eax
  unsigned int v6; // edx
  unsigned int v7; // r14d
  unsigned int v8; // r9d
  unsigned int v9; // r11d
  int v10; // r8d
  unsigned int v11; // eax
  signed int v12; // ecx
  __int64 v13; // rcx
  __int128 v14; // xmm1
  __int64 v15; // xmm0_8
  int v16; // eax
  int v17; // r8d
  __int64 v19; // [rsp+28h] [rbp-41h]
  void *v20; // [rsp+40h] [rbp-29h] BYREF
  NDIS_HANDLE ConfigurationHandle; // [rsp+48h] [rbp-21h]
  __int128 v22; // [rsp+50h] [rbp-19h] BYREF
  __int128 v23; // [rsp+60h] [rbp-9h]
  __int64 v24; // [rsp+70h] [rbp+7h]

  m_MiniportAdapterHandle = this->m_MiniportAdapterHandle;
  v2 = 0;
  ConfigurationHandle = 0;
  v20 = m_MiniportAdapterHandle;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      15,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  CPropertyCache::GetPropertyULong(&this->m_AdapterPropertyCache, 0x3Fu, &this->m_EventQueue.m_HungAtWdiCommandPasses);
  m_HungResetRecoveryIterations = this->m_EventQueue.m_HungResetRecoveryIterations;
  this->m_EventQueue.m_HungAtWdiCommandPasses += m_HungResetRecoveryIterations;
  v5 = 0;
  this->m_EventQueue.m_CountCommandsToLe = 0;
  v24 = 0;
  v6 = 0;
  v22 = 0;
  v23 = 0;
  do
  {
    v7 = v5;
    v8 = v6;
    v9 = v6;
    v10 = *((_DWORD *)&g_AdapterRegTable + 10 * (int)v6 + 6);
    if ( v10 == 64 )
      break;
    v5 = ++v6;
  }
  while ( v6 < 0x2B );
  v11 = v9 + 1;
  v12 = v8 + 1;
  if ( v10 == 64 )
  {
    v11 = v7;
    v12 = v8;
  }
  if ( v11 < 0x2B )
  {
    v13 = 5LL * v12;
    v14 = *(_OWORD *)(&g_AdapterRegTable + v13 + 2);
    v22 = *(_OWORD *)(&g_AdapterRegTable + v13);
    v15 = (__int64)*(&g_AdapterRegTable + v13 + 4);
    v23 = v14;
    HIDWORD(v23) = m_HungResetRecoveryIterations - 1;
    v24 = v15;
    v16 = CRegistryHelper::WriteAdapterRegistryEntry((CRegistryHelper *)&v20, (struct _WFC_REG_ENTRY *)&v22);
    v2 = v16;
    if ( v16 >= 0 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_21;
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        v17,
        17,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
        this->m_EventQueue.m_HungResetRecoveryIterations,
        this->m_EventQueue.m_HungAtWdiCommandPasses);
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          16,
          (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
          v16);
      }
      v2 = (v2 >> 31) & 0xC0000001;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v19) = v2;
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      18,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      v19);
  }
LABEL_21:
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400a36d8  push    rbp
0x1400a36da  push    rbx
0x1400a36db  push    rsi
0x1400a36dc  push    rdi
0x1400a36dd  push    r12
0x1400a36df  push    r13
0x1400a36e1  push    r14
0x1400a36e3  push    r15
0x1400a36e5  lea     rbp, [rsp-1Fh]
0x1400a36ea  sub     rsp, 88h
0x1400a36f1  mov     rax, [rcx+58h]
0x1400a36f5  xor     r15d, r15d
0x1400a36f8  mov     ebx, r15d
0x1400a36fb  mov     [rbp+57h+ConfigurationHandle], r15
0x1400a36ff  mov     [rbp+57h+var_80], rax
0x1400a3703  mov     rdi, rcx
0x1400a3706  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a370d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400a3714  lea     r13, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a371b  jz      short loc_1400A374B
0x1400a371d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3724  cmp     byte ptr [rcx+29h], 5
0x1400a3728  jnb     short loc_1400A3731
0x1400a372a  cmp     [rcx+48h], r15w
0x1400a372f  jz      short loc_1400A374B
0x1400a3731  mov     rcx, [rcx+40h]
0x1400a3735  mov     r9d, 0Fh
0x1400a373b  mov     dl, 5
0x1400a373d  mov     [rsp+0C0h+var_A0], r13
0x1400a3742  lea     r8d, [r9-0Eh]
0x1400a3746  call    WPP_RECORDER_SF_
0x1400a374b  lea     rsi, [rdi+33Ch]
0x1400a3752  mov     edx, 3Fh ; '?'; unsigned int
0x1400a3757  mov     r8, rsi; unsigned int *
0x1400a375a  lea     rcx, [rdi+78h]; this
0x1400a375e  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400a3763  mov     r10d, [rdi+338h]
0x1400a376a  lea     r12, ?g_AdapterRegTable@@3PAU_WFC_REG_ENTRY@@A; " \""
0x1400a3771  add     [rsi], r10d
0x1400a3774  xorps   xmm0, xmm0
0x1400a3777  xor     eax, eax
0x1400a3779  mov     [rdi+340h], r15d
0x1400a3780  mov     [rbp+57h+var_50], rax
0x1400a3784  mov     edx, r15d
0x1400a3787  movups  [rbp+57h+var_70], xmm0
0x1400a378b  movups  [rbp+57h+var_60], xmm0
0x1400a378f  mov     r14d, eax
0x1400a3792  mov     r9d, edx
0x1400a3795  movsxd  rax, edx
0x1400a3798  mov     r11d, edx
0x1400a379b  lea     rcx, [rax+rax*4]
0x1400a379f  mov     r8d, [r12+rcx*8+18h]
0x1400a37a4  cmp     r8d, 40h ; '@'
0x1400a37a8  jz      short loc_1400A37B3
0x1400a37aa  inc     edx
0x1400a37ac  mov     eax, edx
0x1400a37ae  cmp     edx, 2Bh ; '+'
0x1400a37b1  jb      short loc_1400A378F
0x1400a37b3  cmp     r8d, 40h ; '@'
0x1400a37b7  lea     eax, [r11+1]
0x1400a37bb  lea     ecx, [r9+1]
0x1400a37bf  cmovz   eax, r14d
0x1400a37c3  lea     r12, WPP_RECORDER_INITIALIZED
0x1400a37ca  cmovz   ecx, r9d
0x1400a37ce  cmp     eax, 2Bh ; '+'
0x1400a37d1  jnb     loc_1400A388A
0x1400a37d7  movsxd  rax, ecx
0x1400a37da  lea     rdx, [rbp+57h+var_70]; struct _WFC_REG_ENTRY *
0x1400a37de  lea     rcx, [rax+rax*4]
0x1400a37e2  lea     rax, ?g_AdapterRegTable@@3PAU_WFC_REG_ENTRY@@A; " \""
0x1400a37e9  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1400a37ed  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x1400a37f2  movups  [rbp+57h+var_70], xmm0
0x1400a37f6  movsd   xmm0, qword ptr [rax+rcx*8+20h]
0x1400a37fc  lea     eax, [r10-1]
0x1400a3800  movups  [rbp+57h+var_60], xmm1
0x1400a3804  lea     rcx, [rbp+57h+var_80]; this
0x1400a3808  mov     dword ptr [rbp+57h+var_60+0Ch], eax
0x1400a380b  movsd   [rbp+57h+var_50], xmm0
0x1400a3810  call    ?WriteAdapterRegistryEntry@CRegistryHelper@@QEAAHPEAU_WFC_REG_ENTRY@@@Z; CRegistryHelper::WriteAdapterRegistryEntry(_WFC_REG_ENTRY *)
0x1400a3815  mov     ebx, eax
0x1400a3817  test    eax, eax
0x1400a3819  jns     short loc_1400A3854
0x1400a381b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400a3822  jz      short loc_1400A3849
0x1400a3824  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a382b  mov     r9d, 10h
0x1400a3831  mov     dword ptr [rsp+0C0h+var_98], eax
0x1400a3835  mov     dl, 2
0x1400a3837  mov     [rsp+0C0h+var_A0], r13
0x1400a383c  mov     rcx, [rcx+40h]
0x1400a3840  lea     r8d, [r9-0Fh]
0x1400a3844  call    WPP_RECORDER_SF_D
0x1400a3849  sar     ebx, 1Fh
0x1400a384c  and     ebx, 0C0000001h
0x1400a3852  jmp     short loc_1400A388A
0x1400a3854  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400a385b  jz      short loc_1400A38C5
0x1400a385d  mov     eax, [rsi]
0x1400a385f  mov     r9d, 11h
0x1400a3865  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a386c  mov     dl, 4
0x1400a386e  mov     [rsp+0C0h+var_90], eax
0x1400a3872  mov     eax, [rdi+338h]
0x1400a3878  mov     dword ptr [rsp+0C0h+var_98], eax
0x1400a387c  mov     rcx, [rcx+40h]
0x1400a3880  mov     [rsp+0C0h+var_A0], r13
0x1400a3885  call    WPP_RECORDER_SF_Ld
0x1400a388a  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400a3891  jz      short loc_1400A38C5
0x1400a3893  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a389a  cmp     byte ptr [rcx+29h], 5
0x1400a389e  jnb     short loc_1400A38A7
0x1400a38a0  cmp     [rcx+48h], r15w
0x1400a38a5  jz      short loc_1400A38C5
0x1400a38a7  mov     rcx, [rcx+40h]
0x1400a38ab  mov     r9d, 12h
0x1400a38b1  mov     dword ptr [rsp+0C0h+var_98], ebx
0x1400a38b5  mov     dl, 5
0x1400a38b7  mov     [rsp+0C0h+var_A0], r13
0x1400a38bc  lea     r8d, [r9-11h]
0x1400a38c0  call    WPP_RECORDER_SF_D
0x1400a38c5  mov     rcx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400a38c9  test    rcx, rcx
0x1400a38cc  jz      short loc_1400A38DA
0x1400a38ce  call    cs:__imp_NdisCloseConfiguration
0x1400a38d5  nop     dword ptr [rax+rax+00h]
0x1400a38da  mov     eax, ebx
0x1400a38dc  add     rsp, 88h
0x1400a38e3  pop     r15
0x1400a38e5  pop     r14
0x1400a38e7  pop     r13
0x1400a38e9  pop     r12
0x1400a38eb  pop     rdi
0x1400a38ec  pop     rsi
0x1400a38ed  pop     rbx
0x1400a38ee  pop     rbp
0x1400a38ef  retn
```
