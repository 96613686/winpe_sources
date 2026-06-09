# CRegistryHelper::WriteAdapterRegistryBinaries(ushort const *,ulong,uchar *)

- ea: `0x1400a7c70`
- end: `0x1400a7d4e`
- name: `?WriteAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGKPEAE@Z`
- size: `222`
- prototype: `int(CRegistryHelper *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400a1694`
- `0x1400a28a0`
- `0x1400a4124`

## callees

- `0x140034ec4`
- `0x14008234c`
- `0x1400a7c70`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7d0d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7d0d`
- `NDIS!NdisWriteConfiguration` at `0x1400a7d29`
- `NDIS!NdisWriteConfiguration` at `0x1400a7d29`

## pseudocode

```c
__int64 __fastcall CRegistryHelper::WriteAdapterRegistryBinaries(
        CRegistryHelper *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        wchar_t *a4)
{
  bool v4; // zf
  __int64 result; // rax
  int v10; // edx
  int v11; // [rsp+28h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-30h] BYREF
  struct _NDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+40h] [rbp-20h] BYREF
  int Status; // [rsp+80h] [rbp+20h] BYREF

  v4 = *((_QWORD *)this + 1) == 0;
  DestinationString = 0;
  Status = 0;
  if ( v4 && (result = CRegistryHelper::Open((NDIS_HANDLE *)this), (Status = result) != 0) )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return result;
    v11 = result;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      26,
      (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
      v11,
      *(_QWORD *)&DestinationString.Length,
      DestinationString.Buffer);
  }
  else
  {
    ParameterValue.ParameterData.StringData.Buffer = a4;
    *(_OWORD *)&ParameterValue.ParameterType = 0;
    ParameterValue.ParameterType = NdisParameterBinary;
    ParameterValue.ParameterData.StringData.Length = a3;
    RtlInitUnicodeString(&DestinationString, a2);
    NdisWriteConfiguration(&Status, *((NDIS_HANDLE *)this + 1), &DestinationString, &ParameterValue);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400a7c70  mov     [rsp-18h+arg_8], rbx
0x1400a7c75  mov     [rsp-18h+arg_10], rsi
0x1400a7c7a  push    rbp
0x1400a7c7b  push    rdi
0x1400a7c7c  push    r14
0x1400a7c7e  mov     rbp, rsp
0x1400a7c81  sub     rsp, 60h
0x1400a7c85  cmp     qword ptr [rcx+8], 0
0x1400a7c8a  xorps   xmm0, xmm0
0x1400a7c8d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400a7c91  mov     rdi, r9
0x1400a7c94  mov     [rbp+Status], 0
0x1400a7c9b  mov     esi, r8d
0x1400a7c9e  mov     r14, rdx
0x1400a7ca1  mov     rbx, rcx
0x1400a7ca4  jnz     short loc_1400A7CF0
0x1400a7ca6  call    ?Open@CRegistryHelper@@AEAAHXZ; CRegistryHelper::Open(void)
0x1400a7cab  mov     [rbp+Status], eax
0x1400a7cae  test    eax, eax
0x1400a7cb0  jz      short loc_1400A7CF0
0x1400a7cb2  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a7cb9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a7cc0  jz      short loc_1400A7D38
0x1400a7cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7cc9  mov     r9d, 1Ah
0x1400a7ccf  mov     [rsp+60h+var_38], eax
0x1400a7cd3  mov     dl, 2
0x1400a7cd5  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x1400a7cdc  mov     [rsp+60h+var_40], rax
0x1400a7ce1  mov     rcx, [rcx+40h]
0x1400a7ce5  lea     r8d, [r9-19h]
0x1400a7ce9  call    WPP_RECORDER_SF_D
0x1400a7cee  jmp     short loc_1400A7D35
0x1400a7cf0  xorps   xmm0, xmm0
0x1400a7cf3  mov     qword ptr [rbp+ParameterValue.ParameterData+8], rdi
0x1400a7cf7  movups  xmmword ptr [rbp+ParameterValue.ParameterType], xmm0
0x1400a7cfb  mov     rdx, r14; SourceString
0x1400a7cfe  mov     [rbp+ParameterValue.ParameterType], 4
0x1400a7d05  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400a7d09  mov     word ptr [rbp+ParameterValue.ParameterData], si
0x1400a7d0d  call    cs:__imp_RtlInitUnicodeString
0x1400a7d14  nop     dword ptr [rax+rax+00h]
0x1400a7d19  mov     rdx, [rbx+8]; ConfigurationHandle
0x1400a7d1d  lea     r9, [rbp+ParameterValue]; ParameterValue
0x1400a7d21  lea     r8, [rbp+DestinationString]; Keyword
0x1400a7d25  lea     rcx, [rbp+Status]; Status
0x1400a7d29  call    cs:__imp_NdisWriteConfiguration
0x1400a7d30  nop     dword ptr [rax+rax+00h]
0x1400a7d35  mov     eax, [rbp+Status]
0x1400a7d38  lea     r11, [rsp+60h+var_s0]
0x1400a7d3d  mov     rbx, [r11+28h]
0x1400a7d41  mov     rsi, [r11+30h]
0x1400a7d45  mov     rsp, r11
0x1400a7d48  pop     r14
0x1400a7d4a  pop     rdi
0x1400a7d4b  pop     rbp
0x1400a7d4c  retn
```
