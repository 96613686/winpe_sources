# DeviceAttributes::IsWSUSManaged(int &)

- ea: `0x180010630`
- end: `0x180010695`
- name: `?IsWSUSManaged@DeviceAttributes@@UEAAJAEAH@Z`
- size: `101`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180010630`
- `0x18001752c`
- `0x1800193b8`
- `0x1800195b4`

## string_xrefs

- `0x180010667`: `WSUS Url Configured`

## pseudocode

```c
__int64 __fastcall DeviceAttributes::IsWSUSManaged(DeviceAttributes *this, int *a2)
{
  int updated; // ebx
  struct tagUpdatePolicyValue_V1 *v5; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v5 = 0;
  updated = ReadUpdatePolicyValueWrapper((__int64)this, &v5);
  if ( updated >= 0 && *((_DWORD *)v5 + 1) == 1 )
  {
    *a2 = 1;
    LogLevel(4u, L"WSUS Url Configured");
  }
  ReleaseUpdatePolicyValueWrapper(&v5);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180010630  mov     [rsp+arg_0], rbx
0x180010635  push    rdi
0x180010636  sub     rsp, 20h
0x18001063a  mov     rdi, rdx
0x18001063d  mov     dword ptr [rdx], 0
0x180010643  lea     rdx, [rsp+28h+arg_8]
0x180010648  mov     [rsp+28h+arg_8], 0
0x180010651  call    ?ReadUpdatePolicyValueWrapper@@YAJW4tagUpdatePolicy@@PEAPEAUtagUpdatePolicyValue_V1@@@Z; ReadUpdatePolicyValueWrapper(tagUpdatePolicy,tagUpdatePolicyValue_V1 * *)
0x180010656  mov     ebx, eax
0x180010658  test    eax, eax
0x18001065a  js      short loc_18001067E
0x18001065c  mov     rcx, [rsp+28h+arg_8]
0x180010661  cmp     dword ptr [rcx+4], 1
0x180010665  jnz     short loc_18001067E
0x180010667  lea     rdx, aWsusUrlConfigu; "WSUS Url Configured"
0x18001066e  mov     dword ptr [rdi], 1
0x180010674  mov     ecx, 4; unsigned __int8
0x180010679  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18001067e  lea     rcx, [rsp+28h+arg_8]; struct tagUpdatePolicyValue_V1 **
0x180010683  call    ?ReleaseUpdatePolicyValueWrapper@@YAJPEAPEAUtagUpdatePolicyValue_V1@@@Z; ReleaseUpdatePolicyValueWrapper(tagUpdatePolicyValue_V1 * *)
0x180010688  mov     eax, ebx
0x18001068a  mov     rbx, [rsp+28h+arg_0]
0x18001068f  add     rsp, 20h
0x180010693  pop     rdi
0x180010694  retn
```
