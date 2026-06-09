# CSetReceiveCoalescingJob::AddReceiveCoalesceToPropertyCache(void)

- ea: `0x1400d1e1c`
- end: `0x1400d1ff6`
- name: `?AddReceiveCoalesceToPropertyCache@CSetReceiveCoalescingJob@@QEAAHXZ`
- size: `474`
- prototype: `__int64 __fastcall(CSetReceiveCoalescingJob *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x14007c0e0`

## callees

- `0x140010390`
- `0x1400174e8`
- `0x14001b84c`
- `0x14001b968`
- `0x14001ba38`
- `0x14002c5d8`
- `0x14002dab0`
- `0x140034e04`
- `0x140034ec4`
- `0x1400d1e1c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400d1e4b`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1e4b`

## pseudocode

```c
__int64 __fastcall CSetReceiveCoalescingJob::AddReceiveCoalesceToPropertyCache(CSetReceiveCoalescingJob *this)
{
  struct CPort *PortFromNdisPortNumber; // rbp
  CPropertyCache *Pool2; // rax
  int v4; // edx
  struct CPropertyCache *v5; // r8
  CPropertyCache *v6; // rdi
  int v7; // eax
  unsigned int v8; // edx
  unsigned int v9; // ebx
  int v10; // r9d
  _NDIS_OID_REQUEST *m_pOidRequest; // r9
  unsigned int InformationBufferLength; // r8d
  int PropertyPropertyCacheList; // eax
  struct CPropertyCache *v14; // r9
  struct CPropertyCache *v16; // [rsp+70h] [rbp+8h] BYREF

  PortFromNdisPortNumber = CAdapter::GetPortFromNdisPortNumber(this->m_pAdapter, this->COidJobBase::m_NdisPortNumber);
  Pool2 = (CPropertyCache *)ExAllocatePool2(64, 24, 1198089303);
  v6 = Pool2;
  if ( Pool2 )
  {
    Pool2->Next = 0;
    Pool2->m_PropertyTable = 0;
    v16 = 0;
    v7 = CPropertyCache::Initialize(Pool2, 0x86u, v5);
    v9 = v7;
    if ( v7 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
LABEL_16:
        CPropertyCache::`scalar deleting destructor'(v6, v8);
        return v9;
      }
      v10 = 23;
LABEL_5:
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        1,
        v10,
        (__int64)WPP_49253296cc563c5c1b6e95d5ca96a5a5_Traceguids,
        v7);
      goto LABEL_16;
    }
    m_pOidRequest = this->m_pOidRequest;
    InformationBufferLength = m_pOidRequest->DATA.QUERY_INFORMATION.InformationBufferLength;
    if ( InformationBufferLength < 0x2C )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          1,
          24,
          (__int64)WPP_49253296cc563c5c1b6e95d5ca96a5a5_Traceguids,
          InformationBufferLength,
          44);
      }
      v9 = -1073676268;
      goto LABEL_16;
    }
    v7 = CPropertyCache::SetPropertyBuffer(
           v6,
           0x4Fu,
           InformationBufferLength,
           (unsigned __int8 *)m_pOidRequest->DATA.QUERY_INFORMATION.InformationBuffer);
    v9 = v7;
    if ( v7 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_16;
      v10 = 25;
      goto LABEL_5;
    }
    PropertyPropertyCacheList = CPropertyCache::GetPropertyPropertyCacheList(
                                  &PortFromNdisPortNumber->m_PortPropertyCache,
                                  0x4Eu,
                                  &v16);
    v14 = v16;
    if ( PropertyPropertyCacheList )
      v14 = 0;
    v6->Next = v14;
    v9 = CPropertyCache::SetPropertyPropertyCacheList(&PortFromNdisPortNumber->m_PortPropertyCache, 0x4Eu, v6);
    if ( v9 )
      goto LABEL_16;
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        1,
        22,
        (__int64)WPP_49253296cc563c5c1b6e95d5ca96a5a5_Traceguids);
    }
    return (unsigned int)-1073741670;
  }
  return v9;
}

```

## disassembly

```asm
0x1400d1e1c  push    rbx
0x1400d1e1e  push    rbp
0x1400d1e1f  push    rsi
0x1400d1e20  push    rdi
0x1400d1e21  sub     rsp, 48h
0x1400d1e25  mov     edx, [rcx+218h]; unsigned int
0x1400d1e2b  mov     rsi, rcx
0x1400d1e2e  mov     rcx, [rcx+200h]; this
0x1400d1e35  call    ?GetPortFromNdisPortNumber@CAdapter@@QEAAPEAVCPort@@K@Z; CAdapter::GetPortFromNdisPortNumber(ulong)
0x1400d1e3a  mov     edx, 18h
0x1400d1e3f  mov     r8d, 47696457h
0x1400d1e45  mov     rbp, rax
0x1400d1e48  lea     ecx, [rdx+28h]
0x1400d1e4b  call    cs:__imp_ExAllocatePool2
0x1400d1e52  nop     dword ptr [rax+rax+00h]
0x1400d1e57  mov     rdi, rax
0x1400d1e5a  test    rax, rax
0x1400d1e5d  jz      loc_1400D1FAD
0x1400d1e63  mov     edx, 86h; unsigned int
0x1400d1e68  mov     qword ptr [rax], 0
0x1400d1e6f  mov     rcx, rax; this
0x1400d1e72  mov     qword ptr [rax+10h], 0
0x1400d1e7a  mov     [rsp+68h+arg_0], 0
0x1400d1e83  call    ?Initialize@CPropertyCache@@QEAAHIPEAV1@@Z; CPropertyCache::Initialize(uint,CPropertyCache *)
0x1400d1e88  mov     ebx, eax
0x1400d1e8a  test    eax, eax
0x1400d1e8c  jz      short loc_1400D1ED5
0x1400d1e8e  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d1e95  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d1e9c  jz      loc_1400D1FA3
0x1400d1ea2  mov     r9d, 17h
0x1400d1ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1eaf  mov     r8d, 1
0x1400d1eb5  mov     [rsp+68h+var_40], eax
0x1400d1eb9  mov     dl, 2
0x1400d1ebb  lea     rax, WPP_49253296cc563c5c1b6e95d5ca96a5a5_Traceguids
0x1400d1ec2  mov     [rsp+68h+var_48], rax
0x1400d1ec7  mov     rcx, [rcx+40h]
0x1400d1ecb  call    WPP_RECORDER_SF_D
0x1400d1ed0  jmp     loc_1400D1FA3
0x1400d1ed5  mov     r9, [rsi+210h]
0x1400d1edc  mov     r8d, [r9+30h]; unsigned int
0x1400d1ee0  cmp     r8d, 2Ch ; ','
0x1400d1ee4  jnb     short loc_1400D1F32
0x1400d1ee6  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d1eed  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d1ef4  jz      short loc_1400D1F2B
0x1400d1ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1efd  lea     rax, WPP_49253296cc563c5c1b6e95d5ca96a5a5_Traceguids
0x1400d1f04  mov     r9d, 18h
0x1400d1f0a  mov     [rsp+68h+var_38], 2Ch ; ','
0x1400d1f12  mov     [rsp+68h+var_40], r8d
0x1400d1f17  mov     dl, 2
0x1400d1f19  mov     [rsp+68h+var_48], rax
0x1400d1f1e  mov     rcx, [rcx+40h]
0x1400d1f22  lea     r8d, [r9-17h]
0x1400d1f26  call    WPP_RECORDER_SF_DD
0x1400d1f2b  mov     ebx, 0C0010014h
0x1400d1f30  jmp     short loc_1400D1FA3
0x1400d1f32  mov     r9, [r9+28h]; unsigned __int8 *
0x1400d1f36  mov     edx, 4Fh ; 'O'; unsigned int
0x1400d1f3b  mov     rcx, rdi; this
0x1400d1f3e  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEAE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar *)
0x1400d1f43  mov     ebx, eax
0x1400d1f45  test    eax, eax
0x1400d1f47  jz      short loc_1400D1F64
0x1400d1f49  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d1f50  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d1f57  jz      short loc_1400D1FA3
0x1400d1f59  mov     r9d, 19h
0x1400d1f5f  jmp     loc_1400D1EA8
0x1400d1f64  lea     rbx, [rbp+3A8h]
0x1400d1f6b  mov     esi, 4Eh ; 'N'
0x1400d1f70  mov     edx, esi; unsigned int
0x1400d1f72  lea     r8, [rsp+68h+arg_0]; struct CPropertyCache **
0x1400d1f77  mov     rcx, rbx; this
0x1400d1f7a  call    ?GetPropertyPropertyCacheList@CPropertyCache@@QEAAHKPEAPEAV1@@Z; CPropertyCache::GetPropertyPropertyCacheList(ulong,CPropertyCache * *)
0x1400d1f7f  mov     r9, [rsp+68h+arg_0]
0x1400d1f84  xor     r8d, r8d
0x1400d1f87  test    eax, eax
0x1400d1f89  mov     edx, esi; unsigned int
0x1400d1f8b  mov     rcx, rbx; this
0x1400d1f8e  cmovnz  r9, r8
0x1400d1f92  mov     r8, rdi; struct CPropertyCache *
0x1400d1f95  mov     [rdi], r9
0x1400d1f98  call    ?SetPropertyPropertyCacheList@CPropertyCache@@QEAAHKPEAV1@@Z; CPropertyCache::SetPropertyPropertyCacheList(ulong,CPropertyCache *)
0x1400d1f9d  mov     ebx, eax
0x1400d1f9f  test    eax, eax
0x1400d1fa1  jz      short loc_1400D1FEA
0x1400d1fa3  mov     rcx, rdi; this
0x1400d1fa6  call    ??_GCPropertyCache@@QEAAPEAXI@Z; CPropertyCache::`scalar deleting destructor'(uint)
0x1400d1fab  jmp     short loc_1400D1FEA
0x1400d1fad  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d1fb4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d1fbb  jz      short loc_1400D1FE5
0x1400d1fbd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1fc4  lea     rax, WPP_49253296cc563c5c1b6e95d5ca96a5a5_Traceguids
0x1400d1fcb  mov     r9d, 16h
0x1400d1fd1  mov     [rsp+68h+var_48], rax
0x1400d1fd6  mov     dl, 2
0x1400d1fd8  mov     rcx, [rcx+40h]
0x1400d1fdc  lea     r8d, [r9-15h]
0x1400d1fe0  call    WPP_RECORDER_SF_
0x1400d1fe5  mov     ebx, 0C000009Ah
0x1400d1fea  mov     eax, ebx
0x1400d1fec  add     rsp, 48h
0x1400d1ff0  pop     rdi
0x1400d1ff1  pop     rsi
0x1400d1ff2  pop     rbp
0x1400d1ff3  pop     rbx
0x1400d1ff4  retn
```
