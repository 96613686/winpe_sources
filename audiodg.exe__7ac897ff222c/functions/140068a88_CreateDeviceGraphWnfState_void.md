# CreateDeviceGraphWnfState(void)

- ea: `0x140068a88`
- end: `0x140068b27`
- name: `?CreateDeviceGraphWnfState@@YAJXZ`
- size: `159`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007ca80`

## callees

- `0x140068a88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140068ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140068ab9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140068b19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140068b19`
- `ntdll!NtCreateWnfStateName` at `0x140068af8`
- `ntdll!NtCreateWnfStateName` at `0x140068af8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140068aaf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140068aaf`

## pseudocode

```c
__int64 CreateDeviceGraphWnfState(void)
{
  unsigned int v0; // ebx
  signed int LastError; // eax
  int WnfStateName; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  SecurityDescriptor = 0;
  if ( !g_DeviceGraphWnfStateNameCreated )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:P(A;;GA;;;WD)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-1692970155-4054893335-185714091-3362601943-3526593181-11598"
            "16984-2199008581-497492991)",
           1u,
           &SecurityDescriptor,
           0) )
    {
      WnfStateName = NtCreateWnfStateName(&g_DeviceGraphWnfStateName, 3, 0);
      if ( WnfStateName >= 0 )
        g_DeviceGraphWnfStateNameCreated = 1;
      else
        v0 = WnfStateName | 0x10000000;
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  LocalFree(SecurityDescriptor);
  return v0;
}

```

## disassembly

```asm
0x140068a88  push    rbx
0x140068a8a  sub     rsp, 40h
0x140068a8e  xor     ebx, ebx
0x140068a90  cmp     cs:?g_DeviceGraphWnfStateNameCreated@@3HA, ebx; int g_DeviceGraphWnfStateNameCreated
0x140068a96  mov     [rsp+48h+SecurityDescriptor], rbx
0x140068a9b  jnz     short loc_140068B14
0x140068a9d  xor     r9d, r9d; SecurityDescriptorSize
0x140068aa0  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x140068aa5  lea     edx, [rbx+1]; StringSDRevision
0x140068aa8  lea     rcx, aDPAGaWdAGrAcAG; "D:P(A;;GA;;;WD)(A;;GR;;;AC)(A;;GR;;;S-1"...
0x140068aaf  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140068ab5  test    eax, eax
0x140068ab7  jnz     short loc_140068AD0
0x140068ab9  call    cs:__imp_GetLastError
0x140068abf  mov     ebx, eax
0x140068ac1  test    eax, eax
0x140068ac3  jle     short loc_140068B14
0x140068ac5  movzx   ebx, ax
0x140068ac8  or      ebx, 80070000h
0x140068ace  jmp     short loc_140068B14
0x140068ad0  mov     rax, [rsp+48h+SecurityDescriptor]
0x140068ad5  lea     rcx, ?g_DeviceGraphWnfStateName@@3U_WNF_STATE_NAME@@A; _WNF_STATE_NAME g_DeviceGraphWnfStateName
0x140068adc  mov     [rsp+48h+var_18], rax
0x140068ae1  xor     r9d, r9d
0x140068ae4  mov     [rsp+48h+var_20], 1000h
0x140068aec  xor     r8d, r8d
0x140068aef  mov     [rsp+48h+var_28], rbx
0x140068af4  lea     edx, [r9+3]
0x140068af8  call    cs:__imp_NtCreateWnfStateName
0x140068afe  test    eax, eax
0x140068b00  jns     short loc_140068B0A
0x140068b02  mov     ebx, eax
0x140068b04  bts     ebx, 1Ch
0x140068b08  jmp     short loc_140068B14
0x140068b0a  mov     cs:?g_DeviceGraphWnfStateNameCreated@@3HA, 1; int g_DeviceGraphWnfStateNameCreated
0x140068b14  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x140068b19  call    cs:__imp_LocalFree
0x140068b1f  mov     eax, ebx
0x140068b21  add     rsp, 40h
0x140068b25  pop     rbx
0x140068b26  retn
```
