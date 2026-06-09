# CRegistryHelper::ReadAdapterRegistryBinaries(ushort const *,ulong *,uchar *)

- ea: `0x14007a86c`
- end: `0x14007a9cf`
- name: `?ReadAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGPEAKPEAE@Z`
- size: `355`
- prototype: `int(CRegistryHelper *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14007a4c8`
- `0x1400a1694`
- `0x1400a4124`

## callees

- `0x140034ec4`
- `0x14007a86c`
- `0x14008234c`
- `0x1400a4630`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14007a915`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007a915`
- `NDIS!NdisReadConfiguration` at `0x14007a939`
- `NDIS!NdisReadConfiguration` at `0x14007a939`

## pseudocode

```c
__int64 __fastcall CRegistryHelper::ReadAdapterRegistryBinaries(
        CRegistryHelper *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  bool v4; // zf
  unsigned int v5; // r15d
  int v10; // edx
  unsigned int v11; // ebx
  int v12; // edx
  int v13; // r8d
  unsigned int Length; // eax
  wchar_t *Buffer; // rdx
  size_t v17; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  int Status; // [rsp+80h] [rbp+30h] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+90h] [rbp+40h] BYREF

  v4 = *((_QWORD *)this + 1) == 0;
  v5 = *a3;
  DestinationString = 0;
  Status = 0;
  *a3 = 0;
  if ( v4 && (Status = CRegistryHelper::Open(this), (v11 = Status) != 0) )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        1,
        24,
        (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
        Status);
      return (unsigned int)Status;
    }
  }
  else
  {
    ParameterValue = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    NdisReadConfiguration(&Status, &ParameterValue, *((NDIS_HANDLE *)this + 1), &DestinationString, NdisParameterBinary);
    v11 = Status;
    if ( Status )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v11;
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_SD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        v13,
        25,
        (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
        (__int64)a2,
        Status);
      return (unsigned int)Status;
    }
    Length = ParameterValue->ParameterData.StringData.Length;
    if ( v5 < Length )
      return 3221225473LL;
    Buffer = ParameterValue->ParameterData.StringData.Buffer;
    v17 = ParameterValue->ParameterData.StringData.Length;
    *a3 = Length;
    memmove(a4, Buffer, v17);
  }
  return v11;
}

```

## disassembly

```asm
0x14007a86c  mov     [rsp-28h+arg_8], rbx
0x14007a871  mov     [rsp-28h+arg_18], rsi
0x14007a876  push    rbp
0x14007a877  push    rdi
0x14007a878  push    r12
0x14007a87a  push    r14
0x14007a87c  push    r15
0x14007a87e  mov     rbp, rsp
0x14007a881  sub     rsp, 50h
0x14007a885  cmp     qword ptr [rcx+8], 0
0x14007a88a  xorps   xmm0, xmm0
0x14007a88d  mov     r15d, [r8]
0x14007a890  mov     r12, r9
0x14007a893  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14007a897  mov     rdi, r8
0x14007a89a  mov     [rbp+Status], 0
0x14007a8a1  mov     r14, rdx
0x14007a8a4  mov     dword ptr [r8], 0
0x14007a8ab  mov     rsi, rcx
0x14007a8ae  jnz     short loc_14007A906
0x14007a8b0  call    ?Open@CRegistryHelper@@AEAAHXZ; CRegistryHelper::Open(void)
0x14007a8b5  mov     [rbp+Status], eax
0x14007a8b8  mov     ebx, eax
0x14007a8ba  test    eax, eax
0x14007a8bc  jz      short loc_14007A906
0x14007a8be  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007a8c5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007a8cc  jz      loc_14007A9B3
0x14007a8d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a8d9  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007a8e0  mov     r9d, 18h
0x14007a8e6  mov     dword ptr [rsp+50h+var_28], ebx
0x14007a8ea  mov     dl, 2
0x14007a8ec  mov     qword ptr [rsp+50h+ParameterType], rax
0x14007a8f1  mov     rcx, [rcx+40h]
0x14007a8f5  lea     r8d, [r9-17h]
0x14007a8f9  call    WPP_RECORDER_SF_D
0x14007a8fe  mov     ebx, [rbp+Status]
0x14007a901  jmp     loc_14007A9B3
0x14007a906  mov     rdx, r14; SourceString
0x14007a909  mov     [rbp+ParameterValue], 0
0x14007a911  lea     rcx, [rbp+DestinationString]; DestinationString
0x14007a915  call    cs:__imp_RtlInitUnicodeString
0x14007a91c  nop     dword ptr [rax+rax+00h]
0x14007a921  mov     r8, [rsi+8]; ConfigurationHandle
0x14007a925  lea     r9, [rbp+DestinationString]; Keyword
0x14007a929  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14007a92d  mov     [rsp+50h+ParameterType], 4; ParameterType
0x14007a935  lea     rcx, [rbp+Status]; Status
0x14007a939  call    cs:__imp_NdisReadConfiguration
0x14007a940  nop     dword ptr [rax+rax+00h]
0x14007a945  mov     ebx, [rbp+Status]
0x14007a948  test    ebx, ebx
0x14007a94a  jz      short loc_14007A98E
0x14007a94c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007a953  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007a95a  jz      short loc_14007A9B3
0x14007a95c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a963  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007a96a  mov     [rsp+50h+var_20], ebx
0x14007a96e  mov     r9d, 19h
0x14007a974  mov     [rsp+50h+var_28], r14
0x14007a979  mov     dl, 4
0x14007a97b  mov     qword ptr [rsp+50h+ParameterType], rax
0x14007a980  mov     rcx, [rcx+40h]
0x14007a984  call    WPP_RECORDER_SF_SD
0x14007a989  jmp     loc_14007A8FE
0x14007a98e  mov     rdx, [rbp+ParameterValue]
0x14007a992  movzx   eax, word ptr [rdx+8]
0x14007a996  cmp     r15d, eax
0x14007a999  jnb     short loc_14007A9A2
0x14007a99b  mov     eax, 0C0000001h
0x14007a9a0  jmp     short loc_14007A9B5
0x14007a9a2  mov     rdx, [rdx+10h]; Src
0x14007a9a6  mov     r8, rax; Size
0x14007a9a9  mov     rcx, r12; void *
0x14007a9ac  mov     [rdi], eax
0x14007a9ae  call    memmove
0x14007a9b3  mov     eax, ebx
0x14007a9b5  lea     r11, [rsp+50h+var_s0]
0x14007a9ba  mov     rbx, [r11+38h]
0x14007a9be  mov     rsi, [r11+48h]
0x14007a9c2  mov     rsp, r11
0x14007a9c5  pop     r15
0x14007a9c7  pop     r14
0x14007a9c9  pop     r12
0x14007a9cb  pop     rdi
0x14007a9cc  pop     rbp
0x14007a9cd  retn
```
