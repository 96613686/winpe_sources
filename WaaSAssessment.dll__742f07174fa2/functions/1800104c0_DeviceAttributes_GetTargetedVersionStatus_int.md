# DeviceAttributes::GetTargetedVersionStatus(int &)

- ea: `0x1800104c0`
- end: `0x180010531`
- name: `?GetTargetedVersionStatus@DeviceAttributes@@UEAAJAEAH@Z`
- size: `113`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x1800104c0`
- `0x18001752c`
- `0x180019290`
- `0x1800194f4`

## string_xrefs

- `0x180010503`: `Targeted version configured`

## pseudocode

```c
__int64 __fastcall DeviceAttributes::GetTargetedVersionStatus(DeviceAttributes *this, int *a2)
{
  int v3; // ebx
  struct tagEnterprisePolicyValue_V1 *v5; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v5 = 0;
  v3 = ReadEnterprisePolicyValueWrapper(0x32u, &v5);
  if ( v3 >= 0 && *((_DWORD *)v5 + 1) == 1 && *((_WORD *)v5 + 8) == 8 )
  {
    *a2 = 1;
    LogLevel(4u, L"Targeted version configured");
  }
  ReleaseEnterprisePolicyValueWrapper(&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800104c0  mov     [rsp+arg_0], rbx
0x1800104c5  push    rdi
0x1800104c6  sub     rsp, 20h
0x1800104ca  mov     rdi, rdx
0x1800104cd  mov     dword ptr [rdx], 0
0x1800104d3  lea     rdx, [rsp+28h+arg_8]
0x1800104d8  mov     [rsp+28h+arg_8], 0
0x1800104e1  mov     ecx, 32h ; '2'
0x1800104e6  call    ?ReadEnterprisePolicyValueWrapper@@YAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReadEnterprisePolicyValueWrapper(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x1800104eb  mov     ebx, eax
0x1800104ed  test    eax, eax
0x1800104ef  js      short loc_18001051A
0x1800104f1  mov     rcx, [rsp+28h+arg_8]
0x1800104f6  cmp     dword ptr [rcx+4], 1
0x1800104fa  jnz     short loc_18001051A
0x1800104fc  cmp     word ptr [rcx+10h], 8
0x180010501  jnz     short loc_18001051A
0x180010503  lea     rdx, aTargetedVersio; "Targeted version configured"
0x18001050a  mov     dword ptr [rdi], 1
0x180010510  mov     ecx, 4; unsigned __int8
0x180010515  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18001051a  lea     rcx, [rsp+28h+arg_8]; struct tagEnterprisePolicyValue_V1 **
0x18001051f  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x180010524  mov     eax, ebx
0x180010526  mov     rbx, [rsp+28h+arg_0]
0x18001052b  add     rsp, 20h
0x18001052f  pop     rdi
0x180010530  retn
```
