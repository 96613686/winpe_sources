# GetHttpBITSManager

- ea: `0x18001e480`
- end: `0x18001e4f2`
- name: `GetHttpBITSManager`
- size: `114`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e154`
- `0x18001e3a4`

## callees

- `0x18001e480`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18001e4a2`
- `ole32!CoCreateInstance` at `0x18001e4a2`
- `ole32!CoSetProxyBlanket` at `0x18001e4df`
- `ole32!CoSetProxyBlanket` at `0x18001e4df`

## pseudocode

```c
int __fastcall GetHttpBITSManager(LPVOID *ppv)
{
  int result; // eax

  result = CoCreateInstance(
             &GUID_4991d34b_80a1_4291_83b6_3328366b9097,
             0,
             0x17u,
             &GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c,
             ppv);
  if ( result >= 0 )
    return CoSetProxyBlanket((IUnknown *)*ppv, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x20u);
  return result;
}

```

## disassembly

```asm
0x18001e480  push    rbx
0x18001e482  sub     rsp, 40h
0x18001e486  xor     edx, edx; pUnkOuter
0x18001e488  mov     [rsp+48h+ppv], rcx; ppv
0x18001e48d  mov     rbx, rcx
0x18001e490  lea     r9, _GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c; riid
0x18001e497  lea     rcx, _GUID_4991d34b_80a1_4291_83b6_3328366b9097; rclsid
0x18001e49e  lea     r8d, [rdx+17h]; dwClsContext
0x18001e4a2  call    cs:__imp_CoCreateInstance
0x18001e4a9  nop     dword ptr [rax+rax+00h]
0x18001e4ae  test    eax, eax
0x18001e4b0  js      short loc_18001E4EB
0x18001e4b2  mov     rcx, [rbx]; pProxy
0x18001e4b5  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001e4b8  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001e4c0  mov     r8d, edx; dwAuthzSvc
0x18001e4c3  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18001e4cc  xor     r9d, r9d; pServerPrincName
0x18001e4cf  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x18001e4d7  mov     dword ptr [rsp+48h+ppv], 0; dwAuthnLevel
0x18001e4df  call    cs:__imp_CoSetProxyBlanket
0x18001e4e6  nop     dword ptr [rax+rax+00h]
0x18001e4eb  add     rsp, 40h
0x18001e4ef  pop     rbx
0x18001e4f0  retn
```
