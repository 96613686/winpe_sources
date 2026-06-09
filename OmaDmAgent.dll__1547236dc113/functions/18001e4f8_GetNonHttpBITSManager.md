# GetNonHttpBITSManager

- ea: `0x18001e4f8`
- end: `0x18001e527`
- name: `GetNonHttpBITSManager`
- size: `47`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e3a4`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18001e515`
- `ole32!CoCreateInstance` at `0x18001e515`

## pseudocode

```c
HRESULT __fastcall GetNonHttpBITSManager(LPVOID *ppv)
{
  return CoCreateInstance(
           &GUID_4991d34b_80a1_4291_83b6_3328366b9097,
           0,
           0x17u,
           &GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c,
           ppv);
}

```

## disassembly

```asm
0x18001e4f8  sub     rsp, 38h
0x18001e4fc  xor     edx, edx; pUnkOuter
0x18001e4fe  mov     [rsp+38h+ppv], rcx; ppv
0x18001e503  lea     r9, _GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c; riid
0x18001e50a  lea     rcx, _GUID_4991d34b_80a1_4291_83b6_3328366b9097; rclsid
0x18001e511  lea     r8d, [rdx+17h]; dwClsContext
0x18001e515  call    cs:__imp_CoCreateInstance
0x18001e51c  nop     dword ptr [rax+rax+00h]
0x18001e521  add     rsp, 38h
0x18001e525  retn
```
