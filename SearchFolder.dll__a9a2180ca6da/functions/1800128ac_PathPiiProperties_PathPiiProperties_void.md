# PathPiiProperties::~PathPiiProperties(void)

- ea: `0x1800128ac`
- end: `0x1800128e7`
- name: `??1PathPiiProperties@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(PathPiiProperties *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001296c`

## callees

- `0x1800128ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128db`

## pseudocode

```c
void __fastcall PathPiiProperties::~PathPiiProperties(PathPiiProperties *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( *(_QWORD *)this )
    CoTaskMemFree(*(LPVOID *)this);
}

```

## disassembly

```asm
0x1800128ac  push    rbx
0x1800128ae  sub     rsp, 20h
0x1800128b2  mov     rbx, rcx
0x1800128b5  mov     rcx, [rcx+10h]; pv
0x1800128b9  test    rcx, rcx
0x1800128bc  jz      short loc_1800128C4
0x1800128be  call    cs:__imp_CoTaskMemFree
0x1800128c4  mov     rcx, [rbx+8]; pv
0x1800128c8  test    rcx, rcx
0x1800128cb  jz      short loc_1800128D3
0x1800128cd  call    cs:__imp_CoTaskMemFree
0x1800128d3  mov     rcx, [rbx]; pv
0x1800128d6  test    rcx, rcx
0x1800128d9  jz      short loc_1800128E1
0x1800128db  call    cs:__imp_CoTaskMemFree
0x1800128e1  add     rsp, 20h
0x1800128e5  pop     rbx
0x1800128e6  retn
```
