# DllGetClassObject

- ea: `0x180002000`
- end: `0x1800020aa`
- name: `DllGetClassObject`
- size: `170`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002000`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000209f`
- `RPCRT4!NdrDllGetClassObject` at `0x18000209f`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  CLSID *pclsid; // [rsp+30h] [rbp-18h]

  if ( *aProxyFileList->pStubVtblList )
    pclsid = **(CLSID ***)aProxyFileList->pStubVtblList;
  else
    pclsid = 0;
  return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
}

```

## disassembly

```asm
0x180002000  mov     [rsp+ppv], r8
0x180002005  mov     [rsp+riid], rdx
0x18000200a  mov     [rsp+rclsid], rcx
0x18000200f  sub     rsp, 48h
0x180002013  mov     eax, 8
0x180002018  imul    rax, 0
0x18000201c  lea     rcx, aProxyFileList
0x180002023  mov     rax, [rcx+rax]
0x180002027  mov     ecx, 8
0x18000202c  imul    rcx, 0
0x180002030  mov     rax, [rax+8]
0x180002034  cmp     qword ptr [rcx+rax], 0
0x180002039  jz      short loc_18000206A
0x18000203b  mov     eax, 8
0x180002040  imul    rax, 0
0x180002044  lea     rcx, aProxyFileList
0x18000204b  mov     rax, [rcx+rax]
0x18000204f  mov     ecx, 8
0x180002054  imul    rcx, 0
0x180002058  mov     rax, [rax+8]
0x18000205c  mov     rax, [rax+rcx]
0x180002060  mov     rax, [rax]
0x180002063  mov     [rsp+48h+var_18], rax
0x180002068  jmp     short loc_180002073
0x18000206a  mov     [rsp+48h+var_18], 0
0x180002073  lea     rax, gPFactory
0x18000207a  mov     [rsp+48h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000207f  mov     rax, [rsp+48h+var_18]
0x180002084  mov     [rsp+48h+pclsid], rax; pclsid
0x180002089  lea     r9, aProxyFileList; pProxyFileList
0x180002090  mov     r8, [rsp+48h+ppv]; ppv
0x180002095  mov     rdx, [rsp+48h+riid]; riid
0x18000209a  mov     rcx, [rsp+48h+rclsid]; rclsid
0x18000209f  call    cs:__imp_NdrDllGetClassObject
0x1800020a5  add     rsp, 48h
0x1800020a9  retn
```
