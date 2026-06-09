# CRegistryHelper::ReadAdapterRegistryDword(_UNICODE_STRING *,ulong *)

- ea: `0x14007d2e4`
- end: `0x14007d3f8`
- name: `?ReadAdapterRegistryDword@CRegistryHelper@@QEAAHPEAU_UNICODE_STRING@@PEAK@Z`
- size: `276`
- prototype: `int(CRegistryHelper *__hidden this, struct _UNICODE_STRING *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140077e34`

## callees

- `0x140034ec4`
- `0x14007d2e4`
- `0x14008234c`
- `0x1400a4630`

## import_xrefs

- `NDIS!NdisReadConfiguration` at `0x14007d383`
- `NDIS!NdisReadConfiguration` at `0x14007d383`

## pseudocode

```c
__int64 __fastcall CRegistryHelper::ReadAdapterRegistryDword(
        CRegistryHelper *this,
        struct _UNICODE_STRING *a2,
        unsigned int *a3)
{
  bool v3; // zf
  __int64 result; // rax
  int v8; // edx
  void *v9; // r8
  int v10; // edx
  int v11; // r8d
  int Status; // [rsp+50h] [rbp+8h] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+68h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 1) == 0;
  Status = 0;
  if ( v3 )
  {
    result = CRegistryHelper::Open((NDIS_HANDLE *)this);
    Status = result;
    if ( (_DWORD)result )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return result;
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        1,
        27,
        (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
        result);
      return (unsigned int)Status;
    }
  }
  v9 = (void *)*((_QWORD *)this + 1);
  ParameterValue = 0;
  NdisReadConfiguration(&Status, &ParameterValue, v9, a2, NdisParameterHexInteger);
  result = (unsigned int)Status;
  if ( Status )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_SD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        28,
        (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
        (__int64)a2->Buffer,
        Status);
      return (unsigned int)Status;
    }
  }
  else
  {
    *a3 = ParameterValue->ParameterData.IntegerData;
  }
  return result;
}

```

## disassembly

```asm
0x14007d2e4  mov     [rsp+arg_8], rbx
0x14007d2e9  mov     [rsp+arg_10], rsi
0x14007d2ee  push    rdi
0x14007d2ef  sub     rsp, 40h
0x14007d2f3  cmp     qword ptr [rcx+8], 0
0x14007d2f8  mov     rdi, r8
0x14007d2fb  mov     rsi, rdx
0x14007d2fe  mov     [rsp+48h+Status], 0
0x14007d306  mov     rbx, rcx
0x14007d309  jnz     short loc_14007D361
0x14007d30b  call    ?Open@CRegistryHelper@@AEAAHXZ; CRegistryHelper::Open(void)
0x14007d310  mov     [rsp+48h+Status], eax
0x14007d314  test    eax, eax
0x14007d316  jz      short loc_14007D361
0x14007d318  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007d31f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14007d326  jz      loc_14007D3E7
0x14007d32c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d333  mov     r9d, 1Bh
0x14007d339  mov     dword ptr [rsp+48h+var_20], eax
0x14007d33d  mov     dl, 2
0x14007d33f  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007d346  mov     qword ptr [rsp+48h+ParameterType], rax
0x14007d34b  mov     rcx, [rcx+40h]
0x14007d34f  lea     r8d, [r9-1Ah]
0x14007d353  call    WPP_RECORDER_SF_D
0x14007d358  mov     eax, [rsp+48h+Status]
0x14007d35c  jmp     loc_14007D3E7
0x14007d361  mov     r8, [rbx+8]; ConfigurationHandle
0x14007d365  lea     rdx, [rsp+48h+ParameterValue]; ParameterValue
0x14007d36a  mov     r9, rsi; Keyword
0x14007d36d  mov     [rsp+48h+ParameterValue], 0
0x14007d376  lea     rcx, [rsp+48h+Status]; Status
0x14007d37b  mov     [rsp+48h+ParameterType], 1; ParameterType
0x14007d383  call    cs:__imp_NdisReadConfiguration
0x14007d38a  nop     dword ptr [rax+rax+00h]
0x14007d38f  mov     eax, [rsp+48h+Status]
0x14007d393  test    eax, eax
0x14007d395  jz      short loc_14007D3DD
0x14007d397  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007d39e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14007d3a5  jz      short loc_14007D3E7
0x14007d3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d3ae  mov     r9d, 1Ch
0x14007d3b4  mov     [rsp+48h+var_18], eax
0x14007d3b8  mov     dl, 2
0x14007d3ba  mov     rax, [rsi+8]
0x14007d3be  mov     [rsp+48h+var_20], rax
0x14007d3c3  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007d3ca  mov     rcx, [rcx+40h]
0x14007d3ce  mov     qword ptr [rsp+48h+ParameterType], rax
0x14007d3d3  call    WPP_RECORDER_SF_SD
0x14007d3d8  jmp     loc_14007D358
0x14007d3dd  mov     rcx, [rsp+48h+ParameterValue]
0x14007d3e2  mov     edx, [rcx+8]
0x14007d3e5  mov     [rdi], edx
0x14007d3e7  mov     rbx, [rsp+48h+arg_8]
0x14007d3ec  mov     rsi, [rsp+48h+arg_10]
0x14007d3f1  add     rsp, 40h
0x14007d3f5  pop     rdi
0x14007d3f6  retn
```
