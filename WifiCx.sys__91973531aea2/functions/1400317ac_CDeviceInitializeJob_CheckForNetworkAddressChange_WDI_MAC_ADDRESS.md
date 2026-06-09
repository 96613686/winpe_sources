# CDeviceInitializeJob::CheckForNetworkAddressChange(_WDI_MAC_ADDRESS *)

- ea: `0x1400317ac`
- end: `0x1400318ec`
- name: `?CheckForNetworkAddressChange@CDeviceInitializeJob@@AEAAHPEAU_WDI_MAC_ADDRESS@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(CDeviceInitializeJob *__hidden this, struct _WDI_MAC_ADDRESS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006b040`

## callees

- `0x140004d48`
- `0x14001ed44`
- `0x1400317ac`
- `0x1400318f4`
- `0x1400dfd00`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003188f`
- `ntoskrnl!RtlCompareMemory` at `0x14003188f`
- `NDIS!NdisCloseConfiguration` at `0x1400318be`
- `NDIS!NdisCloseConfiguration` at `0x1400318be`
- `NDIS!NdisReadNetworkAddress` at `0x140031861`
- `NDIS!NdisReadNetworkAddress` at `0x140031861`
- `NDIS!NdisOpenConfigurationEx` at `0x14003183e`
- `NDIS!NdisOpenConfigurationEx` at `0x14003183e`

## pseudocode

```c
NDIS_STATUS __fastcall CDeviceInitializeJob::CheckForNetworkAddressChange(CAdapter **this, struct _WDI_MAC_ADDRESS *a2)
{
  NDIS_STATUS result; // eax
  CAdapter *v5; // rcx
  _WORD *v6; // rcx
  int Status; // [rsp+20h] [rbp-40h] BYREF
  unsigned int NetworkAddressLength; // [rsp+24h] [rbp-3Ch] BYREF
  PVOID NetworkAddress; // [rsp+28h] [rbp-38h] BYREF
  PVOID ConfigurationHandle; // [rsp+30h] [rbp-30h] BYREF
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+38h] [rbp-28h] BYREF
  int Source1; // [rsp+50h] [rbp-10h] BYREF
  __int16 v13; // [rsp+54h] [rbp-Ch]

  if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline() )
    return CDeviceInitializeJob::CheckForNetworkAddressChange_NetCxAPIs((CDeviceInitializeJob *)this, a2);
  v5 = this[68];
  *(_QWORD *)&ConfigObject.Header.Revision = 0;
  *(_QWORD *)&ConfigObject.Flags = 0;
  ConfigObject.Header = (NDIS_OBJECT_HEADER)1311145;
  NetworkAddress = 0;
  NetworkAddressLength = 0;
  ConfigurationHandle = 0;
  Source1 = 0;
  v13 = 0;
  ConfigObject.NdisHandle = CAdapter::GetAdapterNdisHandleFromNdisPortNumber(v5, 0);
  result = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  Status = result;
  if ( !result )
  {
    NdisReadNetworkAddress(&Status, &NetworkAddress, &NetworkAddressLength, ConfigurationHandle);
    if ( !Status )
    {
      if ( NetworkAddressLength == 6
        && (*(_BYTE *)NetworkAddress & 3) == 2
        && RtlCompareMemory(&Source1, NetworkAddress, 6u) != 6 )
      {
        v6 = NetworkAddress;
        *(_DWORD *)a2->Address = *(_DWORD *)NetworkAddress;
        *(_WORD *)&a2->Address[4] = v6[2];
      }
      else
      {
        Status = -1073741811;
      }
    }
    NdisCloseConfiguration(ConfigurationHandle);
    return Status;
  }
  return result;
}

```

## disassembly

```asm
0x1400317ac  mov     [rsp-8+arg_10], rbx
0x1400317b1  mov     [rsp-8+arg_18], rdi
0x1400317b6  push    rbp
0x1400317b7  mov     rbp, rsp
0x1400317ba  sub     rsp, 60h
0x1400317be  mov     rax, cs:__security_cookie
0x1400317c5  xor     rax, rsp
0x1400317c8  mov     [rbp+var_8], rax
0x1400317cc  mov     rbx, rdx
0x1400317cf  mov     rdi, rcx
0x1400317d2  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x1400317d7  test    eax, eax
0x1400317d9  jz      short loc_1400317EB
0x1400317db  mov     rdx, rbx; struct _WDI_MAC_ADDRESS *
0x1400317de  mov     rcx, rdi; this
0x1400317e1  call    ?CheckForNetworkAddressChange_NetCxAPIs@CDeviceInitializeJob@@AEAAHPEAU_WDI_MAC_ADDRESS@@@Z; CDeviceInitializeJob::CheckForNetworkAddressChange_NetCxAPIs(_WDI_MAC_ADDRESS *)
0x1400317e6  jmp     loc_1400318CD
0x1400317eb  mov     rcx, [rdi+220h]; this
0x1400317f2  xor     eax, eax
0x1400317f4  xorps   xmm0, xmm0
0x1400317f7  mov     [rbp+Status], 0
0x1400317fe  movups  xmmword ptr [rbp+ConfigObject.Header.Revision], xmm0
0x140031802  xor     edx, edx; unsigned int
0x140031804  mov     qword ptr [rbp+ConfigObject.Flags], rax
0x140031808  mov     dword ptr [rbp+ConfigObject.Header.Type], 1401A9h
0x14003180f  mov     [rbp+NetworkAddress], 0
0x140031817  mov     [rbp+NetworkAddressLength], 0
0x14003181e  mov     [rbp+ConfigurationHandle], 0
0x140031826  mov     [rbp+Source1], eax
0x140031829  mov     [rbp+var_C], ax
0x14003182d  call    ?GetAdapterNdisHandleFromNdisPortNumber@CAdapter@@QEAAPEAXK@Z; CAdapter::GetAdapterNdisHandleFromNdisPortNumber(ulong)
0x140031832  lea     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x140031836  mov     [rbp+ConfigObject.NdisHandle], rax
0x14003183a  lea     rcx, [rbp+ConfigObject]; ConfigObject
0x14003183e  call    cs:__imp_NdisOpenConfigurationEx
0x140031845  nop     dword ptr [rax+rax+00h]
0x14003184a  mov     [rbp+Status], eax
0x14003184d  test    eax, eax
0x14003184f  jnz     short loc_1400318CD
0x140031851  mov     r9, [rbp+ConfigurationHandle]; ConfigurationHandle
0x140031855  lea     r8, [rbp+NetworkAddressLength]; NetworkAddressLength
0x140031859  lea     rdx, [rbp+NetworkAddress]; NetworkAddress
0x14003185d  lea     rcx, [rbp+Status]; Status
0x140031861  call    cs:__imp_NdisReadNetworkAddress
0x140031868  nop     dword ptr [rax+rax+00h]
0x14003186d  cmp     [rbp+Status], 0
0x140031871  jnz     short loc_1400318BA
0x140031873  cmp     [rbp+NetworkAddressLength], 6
0x140031877  jnz     short loc_1400318B3
0x140031879  mov     rdx, [rbp+NetworkAddress]; Source2
0x14003187d  mov     al, [rdx]
0x14003187f  and     al, 3
0x140031881  cmp     al, 2
0x140031883  jnz     short loc_1400318B3
0x140031885  mov     r8d, 6; Length
0x14003188b  lea     rcx, [rbp+Source1]; Source1
0x14003188f  call    cs:__imp_RtlCompareMemory
0x140031896  nop     dword ptr [rax+rax+00h]
0x14003189b  cmp     rax, 6
0x14003189f  jz      short loc_1400318B3
0x1400318a1  mov     rcx, [rbp+NetworkAddress]
0x1400318a5  mov     eax, [rcx]
0x1400318a7  mov     [rbx], eax
0x1400318a9  movzx   eax, word ptr [rcx+4]
0x1400318ad  mov     [rbx+4], ax
0x1400318b1  jmp     short loc_1400318BA
0x1400318b3  mov     [rbp+Status], 0C000000Dh
0x1400318ba  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x1400318be  call    cs:__imp_NdisCloseConfiguration
0x1400318c5  nop     dword ptr [rax+rax+00h]
0x1400318ca  mov     eax, [rbp+Status]
0x1400318cd  mov     rcx, [rbp+var_8]
0x1400318d1  xor     rcx, rsp; StackCookie
0x1400318d4  call    __security_check_cookie
0x1400318d9  lea     r11, [rsp+60h+var_s0]
0x1400318de  mov     rbx, [r11+20h]
0x1400318e2  mov     rdi, [r11+28h]
0x1400318e6  mov     rsp, r11
0x1400318e9  pop     rbp
0x1400318ea  retn
```
