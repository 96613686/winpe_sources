# CRegistryHelper::WriteAdapterRegistryEntry(_WFC_REG_ENTRY *)

- ea: `0x14007c428`
- end: `0x14007c551`
- name: `?WriteAdapterRegistryEntry@CRegistryHelper@@QEAAHPEAU_WFC_REG_ENTRY@@@Z`
- size: `297`
- prototype: `int(CRegistryHelper *__hidden this, struct _WFC_REG_ENTRY *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14007aa9c`
- `0x14008753c`
- `0x1400a36d8`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x14007c428`
- `0x14008234c`

## import_xrefs

- `NDIS!NdisWriteConfiguration` at `0x14007c4f9`
- `NDIS!NdisWriteConfiguration` at `0x14007c4f9`

## pseudocode

```c
__int64 __fastcall CRegistryHelper::WriteAdapterRegistryEntry(CRegistryHelper *this, struct _WFC_REG_ENTRY *a2)
{
  bool v2; // cf
  struct _WFC_REG_ENTRY *v3; // rbx
  int v5; // r9d
  unsigned int v6; // eax
  int v7; // edx
  void *v8; // rdx
  ULONG v9; // eax
  struct _NDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+30h] [rbp-28h] BYREF
  int Status; // [rsp+68h] [rbp+10h] BYREF

  v2 = *((_BYTE *)a2 + 16) < 2u;
  v3 = a2;
  Status = -1073741823;
  if ( v2 )
  {
    v6 = *((_DWORD *)a2 + 7);
    if ( v6 > *((_DWORD *)a2 + 9) || v6 < *((_DWORD *)a2 + 8) )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v5 = 22;
        goto LABEL_13;
      }
    }
    else if ( *((_QWORD *)this + 1) || (Status = CRegistryHelper::Open(this)) == 0 )
    {
      v8 = (void *)*((_QWORD *)this + 1);
      v9 = *((_DWORD *)v3 + 7);
      memset(&ParameterValue, 0, sizeof(ParameterValue));
      ParameterValue.ParameterData.IntegerData = v9;
      NdisWriteConfiguration(&Status, v8, (PNDIS_STRING)v3, &ParameterValue);
    }
    else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        23,
        (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
        Status);
    }
  }
  else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v5 = 21;
LABEL_13:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      v5,
      (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14007c428  mov     [rsp+arg_0], rbx
0x14007c42d  push    rdi
0x14007c42e  sub     rsp, 50h
0x14007c432  cmp     byte ptr [rdx+10h], 2
0x14007c436  mov     rbx, rdx
0x14007c439  mov     rdi, rcx
0x14007c43c  mov     [rsp+58h+Status], 0C0000001h
0x14007c444  jb      short loc_14007C465
0x14007c446  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007c44d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007c454  jz      loc_14007C541
0x14007c45a  mov     r9d, 15h
0x14007c460  jmp     loc_14007C51D
0x14007c465  mov     eax, [rdx+1Ch]
0x14007c468  cmp     eax, [rdx+24h]
0x14007c46b  ja      loc_14007C507
0x14007c471  cmp     eax, [rdx+20h]
0x14007c474  jb      loc_14007C507
0x14007c47a  cmp     qword ptr [rcx+8], 0
0x14007c47f  jnz     short loc_14007C4D2
0x14007c481  call    ?Open@CRegistryHelper@@AEAAHXZ; CRegistryHelper::Open(void)
0x14007c486  mov     [rsp+58h+Status], eax
0x14007c48a  mov     ecx, eax
0x14007c48c  test    eax, eax
0x14007c48e  jz      short loc_14007C4D2
0x14007c490  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007c497  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007c49e  jz      loc_14007C541
0x14007c4a4  mov     [rsp+58h+var_30], ecx
0x14007c4a8  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007c4af  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c4b6  mov     r9d, 17h
0x14007c4bc  mov     dl, 2
0x14007c4be  mov     [rsp+58h+var_38], rax
0x14007c4c3  mov     rcx, [rcx+40h]
0x14007c4c7  lea     r8d, [r9-16h]
0x14007c4cb  call    WPP_RECORDER_SF_D
0x14007c4d0  jmp     short loc_14007C541
0x14007c4d2  mov     rdx, [rdi+8]; ConfigurationHandle
0x14007c4d6  lea     r9, [rsp+58h+ParameterValue]; ParameterValue
0x14007c4db  xor     eax, eax
0x14007c4dd  lea     rcx, [rsp+58h+Status]; Status
0x14007c4e2  xorps   xmm0, xmm0
0x14007c4e5  mov     qword ptr [rsp+58h+ParameterValue.ParameterData+8], rax
0x14007c4ea  mov     eax, [rbx+1Ch]
0x14007c4ed  mov     r8, rbx; Keyword
0x14007c4f0  movups  xmmword ptr [rsp+58h+ParameterValue.ParameterType], xmm0
0x14007c4f5  mov     dword ptr [rsp+58h+ParameterValue.ParameterData], eax
0x14007c4f9  call    cs:__imp_NdisWriteConfiguration
0x14007c500  nop     dword ptr [rax+rax+00h]
0x14007c505  jmp     short loc_14007C541
0x14007c507  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007c50e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007c515  jz      short loc_14007C541
0x14007c517  mov     r9d, 16h
0x14007c51d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c524  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14007c52b  mov     r8d, 1
0x14007c531  mov     [rsp+58h+var_38], rax
0x14007c536  mov     dl, 2
0x14007c538  mov     rcx, [rcx+40h]
0x14007c53c  call    WPP_RECORDER_SF_
0x14007c541  mov     eax, [rsp+58h+Status]
0x14007c545  mov     rbx, [rsp+58h+arg_0]
0x14007c54a  add     rsp, 50h
0x14007c54e  pop     rdi
0x14007c54f  retn
```
