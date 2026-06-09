# ATL::CDynamicAccessor::Close(void)

- ea: `0x1800a9780`
- end: `0x1800a97d7`
- name: `?Close@CDynamicAccessor@ATL@@QEAAXXZ`
- size: `87`
- prototype: `void __fastcall(ATL::CDynamicAccessor *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a82f0`
- `0x1800ac820`

## callees

- `0x1800a9780`

## import_xrefs

- `msvcrt!free` at `0x1800a97bb`
- `msvcrt!free` at `0x1800a97bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a97a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a97a9`

## pseudocode

```c
void __fastcall ATL::CDynamicAccessor::Close(ATL::CDynamicAccessor *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 4) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 5) = 0;
  }
  free(*((void **)this + 2));
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x1800a9780  push    rbx
0x1800a9782  sub     rsp, 20h
0x1800a9786  mov     rbx, rcx
0x1800a9789  mov     rcx, [rcx+20h]; pv
0x1800a978d  test    rcx, rcx
0x1800a9790  jz      short loc_1800A97A0
0x1800a9792  call    cs:__imp_CoTaskMemFree
0x1800a9798  mov     qword ptr [rbx+20h], 0
0x1800a97a0  mov     rcx, [rbx+28h]; pv
0x1800a97a4  test    rcx, rcx
0x1800a97a7  jz      short loc_1800A97B7
0x1800a97a9  call    cs:__imp_CoTaskMemFree
0x1800a97af  mov     qword ptr [rbx+28h], 0
0x1800a97b7  mov     rcx, [rbx+10h]; Block
0x1800a97bb  call    cs:__imp_free
0x1800a97c1  mov     qword ptr [rbx+10h], 0
0x1800a97c9  mov     qword ptr [rbx+18h], 0
0x1800a97d1  add     rsp, 20h
0x1800a97d5  pop     rbx
0x1800a97d6  retn
```
