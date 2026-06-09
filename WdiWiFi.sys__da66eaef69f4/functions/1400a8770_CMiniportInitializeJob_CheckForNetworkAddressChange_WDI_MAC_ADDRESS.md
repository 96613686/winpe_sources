# CMiniportInitializeJob::CheckForNetworkAddressChange(_WDI_MAC_ADDRESS *)

- ea: `0x1400a8770`
- end: `0x1400a8888`
- name: `?CheckForNetworkAddressChange@CMiniportInitializeJob@@AEAAHPEAU_WDI_MAC_ADDRESS@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(CMiniportInitializeJob *__hidden this, struct _WDI_MAC_ADDRESS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400aa060`

## callees

- `0x1400a8770`
- `0x1400da4f0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400a882f`
- `ntoskrnl!RtlCompareMemory` at `0x1400a882f`
- `NDIS!NdisReadNetworkAddress` at `0x1400a8801`
- `NDIS!NdisReadNetworkAddress` at `0x1400a8801`
- `NDIS!NdisCloseConfiguration` at `0x1400a885e`
- `NDIS!NdisCloseConfiguration` at `0x1400a885e`
- `NDIS!NdisOpenConfigurationEx` at `0x1400a87de`
- `NDIS!NdisOpenConfigurationEx` at `0x1400a87de`

## pseudocode

```c
NDIS_STATUS __fastcall CMiniportInitializeJob::CheckForNetworkAddressChange(
        CMiniportInitializeJob *this,
        struct _WDI_MAC_ADDRESS *a2)
{
  CAdapter *m_pAdapter; // rax
  NDIS_STATUS result; // eax
  _WORD *v5; // rcx
  int Status; // [rsp+20h] [rbp-40h] BYREF
  unsigned int NetworkAddressLength; // [rsp+24h] [rbp-3Ch] BYREF
  PVOID NetworkAddress; // [rsp+28h] [rbp-38h] BYREF
  PVOID ConfigurationHandle; // [rsp+30h] [rbp-30h] BYREF
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+38h] [rbp-28h] BYREF
  int Source1; // [rsp+50h] [rbp-10h] BYREF
  __int16 v12; // [rsp+54h] [rbp-Ch]

  Status = 0;
  Source1 = 0;
  memset(&ConfigObject.Header.Revision, 0, 23);
  v12 = 0;
  m_pAdapter = this->m_pAdapter;
  NetworkAddress = 0;
  NetworkAddressLength = 0;
  ConfigurationHandle = 0;
  ConfigObject.Header = (NDIS_OBJECT_HEADER)1311145;
  ConfigObject.NdisHandle = m_pAdapter->m_MiniportAdapterHandle;
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
        v5 = NetworkAddress;
        *(_DWORD *)a2->Address = *(_DWORD *)NetworkAddress;
        *(_WORD *)&a2->Address[4] = v5[2];
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
0x1400a8770  mov     [rsp-8+arg_10], rbx
0x1400a8775  push    rbp
0x1400a8776  mov     rbp, rsp
0x1400a8779  sub     rsp, 60h
0x1400a877d  mov     rax, cs:__security_cookie
0x1400a8784  xor     rax, rsp
0x1400a8787  mov     [rbp+var_8], rax
0x1400a878b  xor     eax, eax
0x1400a878d  mov     [rbp+Status], 0
0x1400a8794  mov     [rbp+Source1], eax
0x1400a8797  xorps   xmm0, xmm0
0x1400a879a  movups  xmmword ptr [rbp+ConfigObject.Header.Revision], xmm0
0x1400a879e  mov     qword ptr [rbp+ConfigObject.Flags], rax
0x1400a87a2  mov     rbx, rdx
0x1400a87a5  mov     [rbp+var_C], ax
0x1400a87a9  lea     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x1400a87ad  mov     rax, [rcx+208h]
0x1400a87b4  mov     [rbp+NetworkAddress], 0
0x1400a87bc  mov     [rbp+NetworkAddressLength], 0
0x1400a87c3  mov     [rbp+ConfigurationHandle], 0
0x1400a87cb  mov     dword ptr [rbp-28h], 1401A9h
0x1400a87d2  mov     rcx, [rax+58h]
0x1400a87d6  mov     [rbp+ConfigObject.NdisHandle], rcx
0x1400a87da  lea     rcx, [rbp+ConfigObject]; ConfigObject
0x1400a87de  call    cs:__imp_NdisOpenConfigurationEx
0x1400a87e5  nop     dword ptr [rax+rax+00h]
0x1400a87ea  mov     [rbp+Status], eax
0x1400a87ed  test    eax, eax
0x1400a87ef  jnz     short loc_1400A886D
0x1400a87f1  mov     r9, [rbp+ConfigurationHandle]; ConfigurationHandle
0x1400a87f5  lea     r8, [rbp+NetworkAddressLength]; NetworkAddressLength
0x1400a87f9  lea     rdx, [rbp+NetworkAddress]; NetworkAddress
0x1400a87fd  lea     rcx, [rbp+Status]; Status
0x1400a8801  call    cs:__imp_NdisReadNetworkAddress
0x1400a8808  nop     dword ptr [rax+rax+00h]
0x1400a880d  cmp     [rbp+Status], 0
0x1400a8811  jnz     short loc_1400A885A
0x1400a8813  cmp     [rbp+NetworkAddressLength], 6
0x1400a8817  jnz     short loc_1400A8853
0x1400a8819  mov     rdx, [rbp+NetworkAddress]; Source2
0x1400a881d  mov     al, [rdx]
0x1400a881f  and     al, 3
0x1400a8821  cmp     al, 2
0x1400a8823  jnz     short loc_1400A8853
0x1400a8825  mov     r8d, 6; Length
0x1400a882b  lea     rcx, [rbp+Source1]; Source1
0x1400a882f  call    cs:__imp_RtlCompareMemory
0x1400a8836  nop     dword ptr [rax+rax+00h]
0x1400a883b  cmp     rax, 6
0x1400a883f  jz      short loc_1400A8853
0x1400a8841  mov     rcx, [rbp+NetworkAddress]
0x1400a8845  mov     eax, [rcx]
0x1400a8847  mov     [rbx], eax
0x1400a8849  movzx   eax, word ptr [rcx+4]
0x1400a884d  mov     [rbx+4], ax
0x1400a8851  jmp     short loc_1400A885A
0x1400a8853  mov     [rbp+Status], 0C000000Dh
0x1400a885a  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x1400a885e  call    cs:__imp_NdisCloseConfiguration
0x1400a8865  nop     dword ptr [rax+rax+00h]
0x1400a886a  mov     eax, [rbp+Status]
0x1400a886d  mov     rcx, [rbp+var_8]
0x1400a8871  xor     rcx, rsp; StackCookie
0x1400a8874  call    __security_check_cookie
0x1400a8879  mov     rbx, [rsp+60h+arg_10]
0x1400a8881  add     rsp, 60h
0x1400a8885  pop     rbp
0x1400a8886  retn
```
