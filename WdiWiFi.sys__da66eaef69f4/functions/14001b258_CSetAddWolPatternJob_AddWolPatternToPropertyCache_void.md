# CSetAddWolPatternJob::AddWolPatternToPropertyCache(void)

- ea: `0x14001b258`
- end: `0x14001b3da`
- name: `?AddWolPatternToPropertyCache@CSetAddWolPatternJob@@QEAAHXZ`
- size: `386`
- prototype: `__int64 __fastcall(CSetAddWolPatternJob *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1400697a0`

## callees

- `0x140010390`
- `0x14001b258`
- `0x14001b84c`
- `0x14001b968`
- `0x14001ba38`
- `0x14002c5d8`
- `0x14002dab0`
- `0x140034e04`
- `0x140034ec4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001b287`
- `ntoskrnl!ExAllocatePool2` at `0x14001b287`

## pseudocode

```c
__int64 __fastcall CSetAddWolPatternJob::AddWolPatternToPropertyCache(CSetAddWolPatternJob *this)
{
  struct CPort *PortFromNdisPortNumber; // rbp
  CPropertyCache *Pool2; // rax
  int v4; // edx
  struct CPropertyCache *v5; // r8
  CPropertyCache *v6; // rdi
  unsigned int v7; // edx
  unsigned int v8; // ebx
  int v9; // r9d
  int PropertyPropertyCacheList; // eax
  struct CPropertyCache *v11; // r9
  struct CPropertyCache *v13; // [rsp+60h] [rbp+8h] BYREF

  PortFromNdisPortNumber = CAdapter::GetPortFromNdisPortNumber(this->m_pAdapter, this->COidJobBase::m_NdisPortNumber);
  Pool2 = (CPropertyCache *)ExAllocatePool2(64, 24, 1198089303);
  v6 = Pool2;
  if ( Pool2 )
  {
    Pool2->Next = 0;
    Pool2->m_PropertyTable = 0;
    v13 = 0;
    v8 = CPropertyCache::Initialize(Pool2, 0x86u, v5);
    if ( v8 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
LABEL_12:
        CPropertyCache::`scalar deleting destructor'(v6, v7);
        return v8;
      }
      v9 = 62;
LABEL_5:
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        v9,
        (__int64)WPP_984157a2d4d43e2348b6e3f75fb3939d_Traceguids,
        v8);
      goto LABEL_12;
    }
    v8 = CPropertyCache::SetPropertyBuffer(
           v6,
           0x4Du,
           this->m_pOidRequest->DATA.QUERY_INFORMATION.InformationBufferLength,
           (unsigned __int8 *)this->m_pOidRequest->DATA.QUERY_INFORMATION.InformationBuffer);
    if ( v8 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_12;
      v9 = 63;
      goto LABEL_5;
    }
    PropertyPropertyCacheList = CPropertyCache::GetPropertyPropertyCacheList(
                                  &PortFromNdisPortNumber->m_PortPropertyCache,
                                  0x4Cu,
                                  &v13);
    v11 = v13;
    if ( PropertyPropertyCacheList )
      v11 = 0;
    v6->Next = v11;
    v8 = CPropertyCache::SetPropertyPropertyCacheList(&PortFromNdisPortNumber->m_PortPropertyCache, 0x4Cu, v6);
    if ( v8 )
      goto LABEL_12;
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
        61,
        (__int64)WPP_984157a2d4d43e2348b6e3f75fb3939d_Traceguids);
    }
    return (unsigned int)-1073741670;
  }
  return v8;
}

```

## disassembly

```asm
0x14001b258  push    rbx
0x14001b25a  push    rbp
0x14001b25b  push    rsi
0x14001b25c  push    rdi
0x14001b25d  sub     rsp, 38h
0x14001b261  mov     edx, [rcx+218h]; unsigned int
0x14001b267  mov     rsi, rcx
0x14001b26a  mov     rcx, [rcx+200h]; this
0x14001b271  call    ?GetPortFromNdisPortNumber@CAdapter@@QEAAPEAVCPort@@K@Z; CAdapter::GetPortFromNdisPortNumber(ulong)
0x14001b276  mov     edx, 18h
0x14001b27b  mov     r8d, 47696457h
0x14001b281  mov     rbp, rax
0x14001b284  lea     ecx, [rdx+28h]
0x14001b287  call    cs:__imp_ExAllocatePool2
0x14001b28e  nop     dword ptr [rax+rax+00h]
0x14001b293  mov     rdi, rax
0x14001b296  test    rax, rax
0x14001b299  jz      loc_14001B391
0x14001b29f  mov     edx, 86h; unsigned int
0x14001b2a4  mov     qword ptr [rax], 0
0x14001b2ab  mov     rcx, rax; this
0x14001b2ae  mov     qword ptr [rax+10h], 0
0x14001b2b6  mov     [rsp+58h+arg_0], 0
0x14001b2bf  call    ?Initialize@CPropertyCache@@QEAAHIPEAV1@@Z; CPropertyCache::Initialize(uint,CPropertyCache *)
0x14001b2c4  mov     ebx, eax
0x14001b2c6  test    eax, eax
0x14001b2c8  jz      short loc_14001B30E
0x14001b2ca  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b2d1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b2d8  jz      loc_14001B387
0x14001b2de  mov     r9d, 3Eh ; '>'
0x14001b2e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b2eb  lea     rax, WPP_984157a2d4d43e2348b6e3f75fb3939d_Traceguids
0x14001b2f2  mov     [rsp+58h+var_30], ebx
0x14001b2f6  mov     r8d, 1
0x14001b2fc  mov     dl, 2
0x14001b2fe  mov     [rsp+58h+var_38], rax
0x14001b303  mov     rcx, [rcx+40h]
0x14001b307  call    WPP_RECORDER_SF_D
0x14001b30c  jmp     short loc_14001B387
0x14001b30e  mov     r8, [rsi+210h]
0x14001b315  mov     edx, 4Dh ; 'M'; unsigned int
0x14001b31a  mov     rcx, rdi; this
0x14001b31d  mov     r9, [r8+28h]; unsigned __int8 *
0x14001b321  mov     r8d, [r8+30h]; unsigned int
0x14001b325  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEAE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar *)
0x14001b32a  mov     ebx, eax
0x14001b32c  test    eax, eax
0x14001b32e  jz      short loc_14001B348
0x14001b330  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b337  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b33e  jz      short loc_14001B387
0x14001b340  mov     r9d, 3Fh ; '?'
0x14001b346  jmp     short loc_14001B2E4
0x14001b348  lea     rbx, [rbp+3A8h]
0x14001b34f  mov     esi, 4Ch ; 'L'
0x14001b354  mov     edx, esi; unsigned int
0x14001b356  lea     r8, [rsp+58h+arg_0]; struct CPropertyCache **
0x14001b35b  mov     rcx, rbx; this
0x14001b35e  call    ?GetPropertyPropertyCacheList@CPropertyCache@@QEAAHKPEAPEAV1@@Z; CPropertyCache::GetPropertyPropertyCacheList(ulong,CPropertyCache * *)
0x14001b363  mov     r9, [rsp+58h+arg_0]
0x14001b368  xor     r8d, r8d
0x14001b36b  test    eax, eax
0x14001b36d  mov     edx, esi; unsigned int
0x14001b36f  mov     rcx, rbx; this
0x14001b372  cmovnz  r9, r8
0x14001b376  mov     r8, rdi; struct CPropertyCache *
0x14001b379  mov     [rdi], r9
0x14001b37c  call    ?SetPropertyPropertyCacheList@CPropertyCache@@QEAAHKPEAV1@@Z; CPropertyCache::SetPropertyPropertyCacheList(ulong,CPropertyCache *)
0x14001b381  mov     ebx, eax
0x14001b383  test    eax, eax
0x14001b385  jz      short loc_14001B3CE
0x14001b387  mov     rcx, rdi; this
0x14001b38a  call    ??_GCPropertyCache@@QEAAPEAXI@Z; CPropertyCache::`scalar deleting destructor'(uint)
0x14001b38f  jmp     short loc_14001B3CE
0x14001b391  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b398  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b39f  jz      short loc_14001B3C9
0x14001b3a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b3a8  lea     rax, WPP_984157a2d4d43e2348b6e3f75fb3939d_Traceguids
0x14001b3af  mov     r9d, 3Dh ; '='
0x14001b3b5  mov     [rsp+58h+var_38], rax
0x14001b3ba  mov     dl, 2
0x14001b3bc  mov     rcx, [rcx+40h]
0x14001b3c0  lea     r8d, [r9-3Ch]
0x14001b3c4  call    WPP_RECORDER_SF_
0x14001b3c9  mov     ebx, 0C000009Ah
0x14001b3ce  mov     eax, ebx
0x14001b3d0  add     rsp, 38h
0x14001b3d4  pop     rdi
0x14001b3d5  pop     rsi
0x14001b3d6  pop     rbp
0x14001b3d7  pop     rbx
0x14001b3d8  retn
```
