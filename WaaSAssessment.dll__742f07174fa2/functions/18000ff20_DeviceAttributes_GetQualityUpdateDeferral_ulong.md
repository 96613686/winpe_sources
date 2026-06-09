# DeviceAttributes::GetQualityUpdateDeferral(ulong &)

- ea: `0x18000ff20`
- end: `0x18000ff93`
- name: `?GetQualityUpdateDeferral@DeviceAttributes@@UEAAJAEAK@Z`
- size: `115`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000ff20`
- `0x18001752c`
- `0x180019290`
- `0x1800194f4`

## string_xrefs

- `0x18000ff6b`: `Quality Update Deferred %d days`

## pseudocode

```c
__int64 __fastcall DeviceAttributes::GetQualityUpdateDeferral(DeviceAttributes *this, unsigned int *a2)
{
  int v3; // edi
  struct tagEnterprisePolicyValue_V1 *v5; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v5 = 0;
  v3 = ReadEnterprisePolicyValueWrapper(7u, &v5);
  if ( v3 >= 0 && *((_DWORD *)v5 + 1) == 1 && *((_WORD *)v5 + 8) == 3 )
    *a2 = *((_DWORD *)v5 + 6);
  LogLevel(4u, L"Quality Update Deferred %d days", *a2);
  ReleaseEnterprisePolicyValueWrapper(&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ff20  mov     [rsp+arg_0], rbx
0x18000ff25  push    rdi
0x18000ff26  sub     rsp, 20h
0x18000ff2a  mov     rbx, rdx
0x18000ff2d  mov     dword ptr [rdx], 0
0x18000ff33  lea     rdx, [rsp+28h+arg_8]
0x18000ff38  mov     [rsp+28h+arg_8], 0
0x18000ff41  mov     ecx, 7
0x18000ff46  call    ?ReadEnterprisePolicyValueWrapper@@YAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReadEnterprisePolicyValueWrapper(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x18000ff4b  mov     edi, eax
0x18000ff4d  test    eax, eax
0x18000ff4f  js      short loc_18000FF68
0x18000ff51  mov     rcx, [rsp+28h+arg_8]
0x18000ff56  cmp     dword ptr [rcx+4], 1
0x18000ff5a  jnz     short loc_18000FF68
0x18000ff5c  cmp     word ptr [rcx+10h], 3
0x18000ff61  jnz     short loc_18000FF68
0x18000ff63  mov     ecx, [rcx+18h]
0x18000ff66  mov     [rbx], ecx
0x18000ff68  mov     r8d, [rbx]
0x18000ff6b  lea     rdx, aQualityUpdateD; "Quality Update Deferred %d days"
0x18000ff72  mov     ecx, 4; unsigned __int8
0x18000ff77  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000ff7c  lea     rcx, [rsp+28h+arg_8]; struct tagEnterprisePolicyValue_V1 **
0x18000ff81  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x18000ff86  mov     rbx, [rsp+28h+arg_0]
0x18000ff8b  mov     eax, edi
0x18000ff8d  add     rsp, 20h
0x18000ff91  pop     rdi
0x18000ff92  retn
```
