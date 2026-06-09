# DllGetClassObject

- ea: `0x1800130b0`
- end: `0x18001311f`
- name: `DllGetClassObject`
- size: `111`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800121e4`
- `0x1800126bc`
- `0x1800130b0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800130ed`
- `RPCRT4!NdrDllGetClassObject` at `0x1800130ed`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  int v5; // eax

  *ppv = 0;
  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&pProxyFileList,
             (const CLSID *)qword_180056700,
             &pPSFactoryBuffer);
  if ( result < 0 )
  {
    v5 = sub_1800126BC();
    return sub_1800121E4(v5, ppv);
  }
  return result;
}

```

## disassembly

```asm
0x1800130b0  mov     r11, rsp
0x1800130b3  mov     [r11+8], rbx
0x1800130b7  mov     [r11+10h], rsi
0x1800130bb  push    rdi
0x1800130bc  sub     rsp, 30h
0x1800130c0  lea     rax, pPSFactoryBuffer
0x1800130c7  mov     qword ptr [r8], 0
0x1800130ce  mov     [r11-10h], rax
0x1800130d2  lea     r9, pProxyFileList; pProxyFileList
0x1800130d9  lea     rax, qword_180056700
0x1800130e0  mov     rbx, r8
0x1800130e3  mov     [r11-18h], rax
0x1800130e7  mov     rdi, rdx
0x1800130ea  mov     rsi, rcx
0x1800130ed  call    cs:NdrDllGetClassObject
0x1800130f3  test    eax, eax
0x1800130f5  jns     short loc_18001310F
0x1800130f7  call    sub_1800126BC
0x1800130fc  mov     r9, rdi
0x1800130ff  mov     [rsp+38h+var_18], rbx; PVOID
0x180013104  mov     r8, rsi
0x180013107  mov     rcx, rax; int
0x18001310a  call    sub_1800121E4
0x18001310f  mov     rbx, [rsp+38h+arg_0]
0x180013114  mov     rsi, [rsp+38h+arg_8]
0x180013119  add     rsp, 30h
0x18001311d  pop     rdi
0x18001311e  retn
```
