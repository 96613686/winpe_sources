# CAdapter::PersistAdapterProperty(ulong)

- ea: `0x1400874ec`
- end: `0x140087533`
- name: `?PersistAdapterProperty@CAdapter@@QEAAHK@Z`
- size: `71`
- prototype: `__int64 __fastcall(CAdapter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140077230`

## callees

- `0x1400874ec`
- `0x14008753c`

## import_xrefs

- `NDIS!NdisCloseConfiguration` at `0x14008751e`
- `NDIS!NdisCloseConfiguration` at `0x14008751e`

## pseudocode

```c
__int64 __fastcall CAdapter::PersistAdapterProperty(
        CAdapter *this,
        unsigned int a2,
        __int64 a3,
        struct _WFC_REG_ENTRY *a4)
{
  unsigned int v4; // ebx
  unsigned int v6; // [rsp+20h] [rbp-28h]
  void *m_MiniportAdapterHandle; // [rsp+30h] [rbp-18h] BYREF
  NDIS_HANDLE ConfigurationHandle; // [rsp+38h] [rbp-10h]

  m_MiniportAdapterHandle = this->m_MiniportAdapterHandle;
  ConfigurationHandle = 0;
  v4 = CRegistryHelper::SavePropertyToRegistry(
         (CRegistryHelper *)&m_MiniportAdapterHandle,
         a2,
         &this->m_AdapterPropertyCache,
         a4,
         v6);
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
  return v4;
}

```

## disassembly

```asm
0x1400874ec  push    rbx
0x1400874ee  sub     rsp, 40h
0x1400874f2  mov     rax, [rcx+58h]
0x1400874f6  lea     r8, [rcx+78h]; struct CPropertyCache *
0x1400874fa  lea     rcx, [rsp+48h+var_18]; this
0x1400874ff  mov     [rsp+48h+var_18], rax
0x140087504  mov     [rsp+48h+ConfigurationHandle], 0
0x14008750d  call    ?SavePropertyToRegistry@CRegistryHelper@@QEAAHKPEAVCPropertyCache@@PEAU_WFC_REG_ENTRY@@K@Z; CRegistryHelper::SavePropertyToRegistry(ulong,CPropertyCache *,_WFC_REG_ENTRY *,ulong)
0x140087512  mov     rcx, [rsp+48h+ConfigurationHandle]; ConfigurationHandle
0x140087517  mov     ebx, eax
0x140087519  test    rcx, rcx
0x14008751c  jz      short loc_14008752A
0x14008751e  call    cs:__imp_NdisCloseConfiguration
0x140087525  nop     dword ptr [rax+rax+00h]
0x14008752a  mov     eax, ebx
0x14008752c  add     rsp, 40h
0x140087530  pop     rbx
0x140087531  retn
```
