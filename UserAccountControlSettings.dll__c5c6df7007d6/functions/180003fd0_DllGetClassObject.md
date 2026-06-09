# DllGetClassObject

- ea: `0x180003fd0`
- end: `0x18000402a`
- name: `DllGetClassObject`
- size: `90`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003224`
- `0x180003fd0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v3; // rax
  int (*v4)(const struct _GUID *, void **); // rcx
  __int64 v5; // rax

  *ppv = 0;
  v3 = 0x457BC590EA2C6B24LL - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&rclsid->Data1 == 0x457BC590EA2C6B24LL )
    v3 = 0xB8B5139B0F4AC8BAuLL - *(_QWORD *)rclsid->Data4;
  if ( !v3 )
  {
    v4 = (int (*)(const struct _GUID *, void **))CUserAccountControlSettingsSource_CreateInstance;
    return CClassFactory_CreateInstance(v4, riid, ppv);
  }
  v5 = 0x4F39621206C792F8LL - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&rclsid->Data1 == 0x4F39621206C792F8LL )
    v5 = 0x235C96ACC0E870BFLL - *(_QWORD *)rclsid->Data4;
  if ( !v5 )
  {
    v4 = (int (*)(const struct _GUID *, void **))CUserAccountControlSettingsSink_CreateInstance;
    return CClassFactory_CreateInstance(v4, riid, ppv);
  }
  return -2147221231;
}

```

## disassembly

```asm
0x180003fd0  mov     qword ptr [r8], 0
0x180003fd7  mov     rax, cs:qword_18000E9F8
0x180003fde  sub     rax, [rcx]
0x180003fe1  jnz     short loc_180003FEE
0x180003fe3  mov     rax, cs:qword_18000EA00
0x180003fea  sub     rax, [rcx+8]
0x180003fee  test    rax, rax
0x180003ff1  jnz     short loc_180003FFC
0x180003ff3  lea     rcx, ?CUserAccountControlSettingsSource_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CUserAccountControlSettingsSource_CreateInstance(_GUID const &,void * *)
0x180003ffa  jmp     short loc_18000401F
0x180003ffc  mov     rax, cs:qword_18000E9E8
0x180004003  sub     rax, [rcx]
0x180004006  jnz     short loc_180004013
0x180004008  mov     rax, cs:qword_18000E9F0
0x18000400f  sub     rax, [rcx+8]
0x180004013  test    rax, rax
0x180004016  jnz     short loc_180004024
0x180004018  lea     rcx, ?CUserAccountControlSettingsSink_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; int (*)(const struct _GUID *, void **)
0x18000401f  jmp     ?CClassFactory_CreateInstance@@YAJP6AJAEBU_GUID@@PEAPEAX@Z01@Z; CClassFactory_CreateInstance(long (*)(_GUID const &,void * *),_GUID const &,void * *)
0x180004024  mov     eax, 80040111h
0x180004029  retn
```
