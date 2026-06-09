# DllGetClassObject

- ea: `0x180005c60`
- end: `0x180005cd7`
- name: `DllGetClassObject`
- size: `119`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005c60`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v6; // rax

  v3 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IClassFactory.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IClassFactory.Data1 )
    v3 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IClassFactory.Data4;
  if ( v3 )
  {
    v6 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v6 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v6 )
      goto LABEL_9;
  }
  v4 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_NetworkExplorerFolder.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_NetworkExplorerFolder.Data1 )
    v4 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_NetworkExplorerFolder.Data4;
  if ( v4 )
  {
LABEL_9:
    *ppv = 0;
    return -2147221231;
  }
  else
  {
    *ppv = &off_180011320;
    _InterlockedIncrement(&g_cRefThisDll);
    return 0;
  }
}

```

## disassembly

```asm
0x180005c60  mov     rax, [rdx]
0x180005c63  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x180005c6a  jnz     short loc_180005C77
0x180005c6c  mov     rax, [rdx+8]
0x180005c70  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x180005c77  test    rax, rax
0x180005c7a  jnz     short loc_180005CBE
0x180005c7c  mov     rax, [rcx]
0x180005c7f  sub     rax, qword ptr cs:CLSID_NetworkExplorerFolder.Data1
0x180005c86  jnz     short loc_180005C93
0x180005c88  mov     rax, [rcx+8]
0x180005c8c  sub     rax, qword ptr cs:CLSID_NetworkExplorerFolder.Data4
0x180005c93  test    rax, rax
0x180005c96  jnz     short loc_180005CB1
0x180005c98  lea     rax, off_180011320
0x180005c9f  mov     [r8], rax
0x180005ca2  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180005ca9  xor     eax, eax
0x180005cab  retn
0x180005cac  test    rax, rax
0x180005caf  jz      short loc_180005C7C
0x180005cb1  mov     qword ptr [r8], 0
0x180005cb8  mov     eax, 80040111h
0x180005cbd  retn
0x180005cbe  mov     rax, [rdx]
0x180005cc1  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180005cc8  jnz     short loc_180005CAC
0x180005cca  mov     rax, [rdx+8]
0x180005cce  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180005cd5  jmp     short loc_180005CAC
```
