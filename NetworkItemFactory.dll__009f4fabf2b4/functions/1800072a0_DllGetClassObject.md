# DllGetClassObject

- ea: `0x1800072a0`
- end: `0x18000730c`
- name: `DllGetClassObject`
- size: `108`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800072a0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  if ( (*(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IClassFactory.Data1
     && *(_QWORD *)riid->Data4 == *(_QWORD *)IID_IClassFactory.Data4
     || *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IUnknown.Data1
     && *(_QWORD *)riid->Data4 == *(_QWORD *)IID_IUnknown.Data4)
    && *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_NetworkItemFactory.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_NetworkItemFactory.Data4 )
  {
    *ppv = &off_18000CCE8;
    _InterlockedIncrement(&g_cRefThisDll);
    return 0;
  }
  else
  {
    *ppv = 0;
    return -2147221231;
  }
}

```

## disassembly

```asm
0x1800072a0  mov     rax, [rdx]
0x1800072a3  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x1800072aa  jnz     short loc_1800072B9
0x1800072ac  mov     rax, [rdx+8]
0x1800072b0  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x1800072b7  jz      short loc_1800072D2
0x1800072b9  mov     rax, [rdx]
0x1800072bc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800072c3  jnz     short loc_1800072FF
0x1800072c5  mov     rax, [rdx+8]
0x1800072c9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800072d0  jnz     short loc_1800072FF
0x1800072d2  mov     rax, [rcx]
0x1800072d5  cmp     rax, qword ptr cs:CLSID_NetworkItemFactory.Data1
0x1800072dc  jnz     short loc_1800072FF
0x1800072de  mov     rax, [rcx+8]
0x1800072e2  cmp     rax, qword ptr cs:CLSID_NetworkItemFactory.Data4
0x1800072e9  jnz     short loc_1800072FF
0x1800072eb  lea     rax, off_18000CCE8
0x1800072f2  mov     [r8], rax
0x1800072f5  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x1800072fc  xor     eax, eax
0x1800072fe  retn
0x1800072ff  mov     qword ptr [r8], 0
0x180007306  mov     eax, 80040111h
0x18000730b  retn
```
