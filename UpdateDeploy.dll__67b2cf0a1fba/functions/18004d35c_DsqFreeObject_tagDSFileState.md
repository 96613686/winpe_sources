# DsqFreeObject(tagDSFileState &)

- ea: `0x18004d35c`
- end: `0x18004d3de`
- name: `?DsqFreeObject@@YAXAEAUtagDSFileState@@@Z`
- size: `130`
- prototype: `void __fastcall(struct tagDSFileState *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004d4dc`

## callees

- `0x18004d35c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d36e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d39c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d3b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d3ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d36e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d39c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d3b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d3ca`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSFileState *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v2 = (void *)*((_QWORD *)a1 + 2);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)a1 + 3);
  *((_QWORD *)a1 + 2) = 0;
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)a1 + 4);
  *((_QWORD *)a1 + 3) = 0;
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)a1 + 5);
  *((_QWORD *)a1 + 4) = 0;
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)a1 + 6);
  *((_QWORD *)a1 + 5) = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  *((_QWORD *)a1 + 6) = 0;
}

```

## disassembly

```asm
0x18004d35c  push    rbx
0x18004d35e  sub     rsp, 20h
0x18004d362  mov     rbx, rcx
0x18004d365  mov     rcx, [rcx+10h]; pv
0x18004d369  test    rcx, rcx
0x18004d36c  jz      short loc_18004D374
0x18004d36e  call    cs:__imp_CoTaskMemFree
0x18004d374  mov     rcx, [rbx+18h]; pv
0x18004d378  mov     qword ptr [rbx+10h], 0
0x18004d380  test    rcx, rcx
0x18004d383  jz      short loc_18004D38B
0x18004d385  call    cs:__imp_CoTaskMemFree
0x18004d38b  mov     rcx, [rbx+20h]; pv
0x18004d38f  mov     qword ptr [rbx+18h], 0
0x18004d397  test    rcx, rcx
0x18004d39a  jz      short loc_18004D3A2
0x18004d39c  call    cs:__imp_CoTaskMemFree
0x18004d3a2  mov     rcx, [rbx+28h]; pv
0x18004d3a6  mov     qword ptr [rbx+20h], 0
0x18004d3ae  test    rcx, rcx
0x18004d3b1  jz      short loc_18004D3B9
0x18004d3b3  call    cs:__imp_CoTaskMemFree
0x18004d3b9  mov     rcx, [rbx+30h]; pv
0x18004d3bd  mov     qword ptr [rbx+28h], 0
0x18004d3c5  test    rcx, rcx
0x18004d3c8  jz      short loc_18004D3D0
0x18004d3ca  call    cs:__imp_CoTaskMemFree
0x18004d3d0  mov     qword ptr [rbx+30h], 0
0x18004d3d8  add     rsp, 20h
0x18004d3dc  pop     rbx
0x18004d3dd  retn
```
