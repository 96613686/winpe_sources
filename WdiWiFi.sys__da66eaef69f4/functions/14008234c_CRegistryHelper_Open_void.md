# CRegistryHelper::Open(void)

- ea: `0x14008234c`
- end: `0x1400823ca`
- name: `?Open@CRegistryHelper@@AEAAHXZ`
- size: `126`
- prototype: `__int64 __fastcall(CRegistryHelper *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14007a4c8`
- `0x14007a86c`
- `0x14007c428`
- `0x14007d2e4`
- `0x14008218c`
- `0x1400a7c70`

## callees

- `0x140034ec4`
- `0x14008234c`

## import_xrefs

- `NDIS!NdisOpenConfigurationEx` at `0x140082373`
- `NDIS!NdisOpenConfigurationEx` at `0x140082373`

## pseudocode

```c
__int64 __fastcall CRegistryHelper::Open(NDIS_HANDLE *this)
{
  int v1; // edx
  unsigned int v2; // ebx
  unsigned int v4; // [rsp+28h] [rbp-30h]
  struct _NDIS_CONFIGURATION_OBJECT v5; // [rsp+30h] [rbp-28h] BYREF

  v5.NdisHandle = *this;
  *(_QWORD *)&v5.Header.Type = 1573289;
  *(_QWORD *)&v5.Flags = 0;
  v2 = NdisOpenConfigurationEx(&v5, this + 1);
  if ( v2 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v4 = v2;
    LOBYTE(v1) = 2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v1,
      1,
      10,
      (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
      v4);
  }
  return v2;
}

```

## disassembly

```asm
0x14008234c  mov     r11, rsp
0x14008234f  push    rbx
0x140082350  sub     rsp, 50h
0x140082354  mov     rax, [rcx]
0x140082357  lea     rdx, [rcx+8]; ConfigurationHandle
0x14008235b  lea     rcx, [r11-28h]; ConfigObject
0x14008235f  mov     [r11-20h], rax
0x140082363  mov     qword ptr [r11-28h], 1801A9h
0x14008236b  mov     qword ptr [r11-18h], 0
0x140082373  call    cs:__imp_NdisOpenConfigurationEx
0x14008237a  nop     dword ptr [rax+rax+00h]
0x14008237f  mov     ebx, eax
0x140082381  test    eax, eax
0x140082383  jz      short loc_1400823C1
0x140082385  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008238c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140082393  jz      short loc_1400823C1
0x140082395  mov     rcx, cs:WPP_GLOBAL_Control
0x14008239c  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x1400823a3  mov     r9d, 0Ah
0x1400823a9  mov     [rsp+58h+var_30], ebx
0x1400823ad  mov     dl, 2
0x1400823af  mov     [rsp+58h+var_38], rax
0x1400823b4  mov     rcx, [rcx+40h]
0x1400823b8  lea     r8d, [r9-9]
0x1400823bc  call    WPP_RECORDER_SF_D
0x1400823c1  mov     eax, ebx
0x1400823c3  add     rsp, 50h
0x1400823c7  pop     rbx
0x1400823c8  retn
```
