# CAdapter::PersistStateInRegistry(void)

- ea: `0x1400a28a0`
- end: `0x1400a29ca`
- name: `?PersistStateInRegistry@CAdapter@@QEAAHXZ`
- size: `298`
- prototype: `__int64 __fastcall(CAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1400a92b0`

## callees

- `0x1400109f8`
- `0x140034ec4`
- `0x1400a28a0`
- `0x1400a4778`
- `0x1400a7c70`

## import_xrefs

- `NDIS!NdisCloseConfiguration` at `0x1400a29ad`
- `NDIS!NdisCloseConfiguration` at `0x1400a29ad`

## pseudocode

```c
__int64 __fastcall CAdapter::PersistStateInRegistry(CAdapter *this)
{
  unsigned int PropertyBuffer; // ebx
  unsigned __int8 *v2; // rdi
  int v3; // edx
  int v4; // r8d
  void *m_MiniportAdapterHandle; // [rsp+50h] [rbp-18h] BYREF
  NDIS_HANDLE ConfigurationHandle; // [rsp+58h] [rbp-10h]
  unsigned int v8; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int8 *v9; // [rsp+78h] [rbp+10h] BYREF

  m_MiniportAdapterHandle = this->m_MiniportAdapterHandle;
  ConfigurationHandle = 0;
  v8 = 0;
  v9 = 0;
  PropertyBuffer = CPropertyCache::GetPropertyBuffer(&this->m_AdapterPropertyCache, 0x43u, &v8, &v9);
  if ( !PropertyBuffer && v8 )
  {
    v2 = v9;
    PropertyBuffer = CRegistryHelper::WriteAdapterRegistryBinaries(
                       (CRegistryHelper *)&m_MiniportAdapterHandle,
                       L"StaLastConnectedAP",
                       v8,
                       v9);
    if ( PropertyBuffer )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v3) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v3,
          1,
          77,
          (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
          PropertyBuffer);
      }
    }
    else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 4;
      WPP_RECORDER_SF__MAC_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        v4,
        PropertyBuffer + 76,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
        (__int64)v2,
        *((_DWORD *)v2 + 2),
        *((_DWORD *)v2 + 3),
        *((_DWORD *)v2 + 4));
    }
  }
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
  return PropertyBuffer;
}

```

## disassembly

```asm
0x1400a28a0  mov     r11, rsp
0x1400a28a3  mov     [r11+18h], rbx
0x1400a28a7  push    rdi
0x1400a28a8  sub     rsp, 60h
0x1400a28ac  mov     rax, [rcx+58h]
0x1400a28b0  lea     r9, [r11+10h]; unsigned __int8 **
0x1400a28b4  add     rcx, 78h ; 'x'; this
0x1400a28b8  mov     [r11-18h], rax
0x1400a28bc  lea     r8, [r11+8]; unsigned int *
0x1400a28c0  mov     qword ptr [r11-10h], 0
0x1400a28c8  mov     edx, 43h ; 'C'; unsigned int
0x1400a28cd  mov     [rsp+68h+arg_0], 0
0x1400a28d5  mov     qword ptr [r11+10h], 0
0x1400a28dd  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400a28e2  mov     ebx, eax
0x1400a28e4  test    eax, eax
0x1400a28e6  jnz     loc_1400A29A3
0x1400a28ec  mov     r8d, [rsp+68h+arg_0]; unsigned int
0x1400a28f1  test    r8d, r8d
0x1400a28f4  jz      loc_1400A29A3
0x1400a28fa  mov     rdi, [rsp+68h+arg_8]
0x1400a28ff  lea     rdx, aStalastconnect; "StaLastConnectedAP"
0x1400a2906  mov     r9, rdi; unsigned __int8 *
0x1400a2909  lea     rcx, [rsp+68h+var_18]; this
0x1400a290e  call    ?WriteAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGKPEAE@Z; CRegistryHelper::WriteAdapterRegistryBinaries(ushort const *,ulong,uchar *)
0x1400a2913  mov     ebx, eax
0x1400a2915  test    eax, eax
0x1400a2917  jnz     short loc_1400A2967
0x1400a2919  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a2920  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a2927  jz      short loc_1400A29A3
0x1400a2929  mov     eax, [rdi+10h]
0x1400a292c  lea     r9d, [rbx+4Ch]
0x1400a2930  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2937  mov     dl, 4
0x1400a2939  mov     [rsp+68h+var_28], eax
0x1400a293d  mov     eax, [rdi+0Ch]
0x1400a2940  mov     [rsp+68h+var_30], eax
0x1400a2944  mov     eax, [rdi+8]
0x1400a2947  mov     rcx, [rcx+40h]
0x1400a294b  mov     [rsp+68h+var_38], eax
0x1400a294f  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a2956  mov     [rsp+68h+var_40], rdi
0x1400a295b  mov     [rsp+68h+var_48], rax
0x1400a2960  call    WPP_RECORDER_SF__MAC_Ddd
0x1400a2965  jmp     short loc_1400A29A3
0x1400a2967  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a296e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a2975  jz      short loc_1400A29A3
0x1400a2977  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a297e  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a2985  mov     r9d, 4Dh ; 'M'
0x1400a298b  mov     dword ptr [rsp+68h+var_40], ebx
0x1400a298f  mov     dl, 2
0x1400a2991  mov     [rsp+68h+var_48], rax
0x1400a2996  mov     rcx, [rcx+40h]
0x1400a299a  lea     r8d, [r9-4Ch]
0x1400a299e  call    WPP_RECORDER_SF_D
0x1400a29a3  mov     rcx, [rsp+68h+ConfigurationHandle]; ConfigurationHandle
0x1400a29a8  test    rcx, rcx
0x1400a29ab  jz      short loc_1400A29B9
0x1400a29ad  call    cs:__imp_NdisCloseConfiguration
0x1400a29b4  nop     dword ptr [rax+rax+00h]
0x1400a29b9  mov     eax, ebx
0x1400a29bb  mov     rbx, [rsp+68h+arg_10]
0x1400a29c3  add     rsp, 60h
0x1400a29c7  pop     rdi
0x1400a29c8  retn
```
