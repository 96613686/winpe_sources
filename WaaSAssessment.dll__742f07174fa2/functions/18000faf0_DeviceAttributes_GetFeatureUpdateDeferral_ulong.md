# DeviceAttributes::GetFeatureUpdateDeferral(ulong &)

- ea: `0x18000faf0`
- end: `0x18000fb63`
- name: `?GetFeatureUpdateDeferral@DeviceAttributes@@UEAAJAEAK@Z`
- size: `115`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000faf0`
- `0x18001752c`
- `0x180019290`
- `0x1800194f4`

## string_xrefs

- `0x18000fb3b`: `Feature Update Deferred %d days`

## pseudocode

```c
__int64 __fastcall DeviceAttributes::GetFeatureUpdateDeferral(DeviceAttributes *this, unsigned int *a2)
{
  int v3; // edi
  struct tagEnterprisePolicyValue_V1 *v5; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v5 = 0;
  v3 = ReadEnterprisePolicyValueWrapper(9u, &v5);
  if ( v3 >= 0 && *((_DWORD *)v5 + 1) == 1 && *((_WORD *)v5 + 8) == 3 )
    *a2 = *((_DWORD *)v5 + 6);
  LogLevel(4u, L"Feature Update Deferred %d days", *a2);
  ReleaseEnterprisePolicyValueWrapper(&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000faf0  mov     [rsp+arg_0], rbx
0x18000faf5  push    rdi
0x18000faf6  sub     rsp, 20h
0x18000fafa  mov     rbx, rdx
0x18000fafd  mov     dword ptr [rdx], 0
0x18000fb03  lea     rdx, [rsp+28h+arg_8]
0x18000fb08  mov     [rsp+28h+arg_8], 0
0x18000fb11  mov     ecx, 9
0x18000fb16  call    ?ReadEnterprisePolicyValueWrapper@@YAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReadEnterprisePolicyValueWrapper(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x18000fb1b  mov     edi, eax
0x18000fb1d  test    eax, eax
0x18000fb1f  js      short loc_18000FB38
0x18000fb21  mov     rcx, [rsp+28h+arg_8]
0x18000fb26  cmp     dword ptr [rcx+4], 1
0x18000fb2a  jnz     short loc_18000FB38
0x18000fb2c  cmp     word ptr [rcx+10h], 3
0x18000fb31  jnz     short loc_18000FB38
0x18000fb33  mov     ecx, [rcx+18h]
0x18000fb36  mov     [rbx], ecx
0x18000fb38  mov     r8d, [rbx]
0x18000fb3b  lea     rdx, aFeatureUpdateD; "Feature Update Deferred %d days"
0x18000fb42  mov     ecx, 4; unsigned __int8
0x18000fb47  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000fb4c  lea     rcx, [rsp+28h+arg_8]; struct tagEnterprisePolicyValue_V1 **
0x18000fb51  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x18000fb56  mov     rbx, [rsp+28h+arg_0]
0x18000fb5b  mov     eax, edi
0x18000fb5d  add     rsp, 20h
0x18000fb61  pop     rdi
0x18000fb62  retn
```
