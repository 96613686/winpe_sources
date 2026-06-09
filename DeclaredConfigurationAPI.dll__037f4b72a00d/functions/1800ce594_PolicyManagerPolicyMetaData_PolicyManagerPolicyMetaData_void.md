# PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(void)

- ea: `0x1800ce594`
- end: `0x1800ce627`
- name: `??1PolicyManagerPolicyMetaData@@QEAA@XZ`
- size: `147`
- prototype: `void __fastcall(PolicyManagerPolicyMetaData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ce630`

## callees

- `0x1800ce594`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce600`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce61b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce5f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce600`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce61b`

## pseudocode

```c
void __fastcall PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(PolicyManagerPolicyMetaData *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 6);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)this + 7);
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)this + 9);
  if ( v6 )
    CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)this + 11);
  if ( v7 )
    CoTaskMemFree(v7);
  v8 = (void *)*((_QWORD *)this + 13);
  if ( v8 )
    CoTaskMemFree(v8);
  if ( *(_DWORD *)this == 1 || *(_DWORD *)this == 3 )
  {
    v9 = (void *)*((_QWORD *)this + 1);
    if ( v9 )
      CoTaskMemFree(v9);
  }
}

```

## disassembly

```asm
0x1800ce594  push    rbx
0x1800ce596  sub     rsp, 20h
0x1800ce59a  mov     rbx, rcx
0x1800ce59d  mov     rcx, [rcx+20h]; pv
0x1800ce5a1  test    rcx, rcx
0x1800ce5a4  jz      short loc_1800CE5AC
0x1800ce5a6  call    cs:__imp_CoTaskMemFree
0x1800ce5ac  mov     rcx, [rbx+28h]; pv
0x1800ce5b0  test    rcx, rcx
0x1800ce5b3  jz      short loc_1800CE5BB
0x1800ce5b5  call    cs:__imp_CoTaskMemFree
0x1800ce5bb  mov     rcx, [rbx+30h]; pv
0x1800ce5bf  test    rcx, rcx
0x1800ce5c2  jz      short loc_1800CE5CA
0x1800ce5c4  call    cs:__imp_CoTaskMemFree
0x1800ce5ca  mov     rcx, [rbx+38h]; pv
0x1800ce5ce  test    rcx, rcx
0x1800ce5d1  jz      short loc_1800CE5D9
0x1800ce5d3  call    cs:__imp_CoTaskMemFree
0x1800ce5d9  mov     rcx, [rbx+48h]; pv
0x1800ce5dd  test    rcx, rcx
0x1800ce5e0  jz      short loc_1800CE5E8
0x1800ce5e2  call    cs:__imp_CoTaskMemFree
0x1800ce5e8  mov     rcx, [rbx+58h]; pv
0x1800ce5ec  test    rcx, rcx
0x1800ce5ef  jz      short loc_1800CE5F7
0x1800ce5f1  call    cs:__imp_CoTaskMemFree
0x1800ce5f7  mov     rcx, [rbx+68h]; pv
0x1800ce5fb  test    rcx, rcx
0x1800ce5fe  jz      short loc_1800CE606
0x1800ce600  call    cs:__imp_CoTaskMemFree
0x1800ce606  mov     ecx, [rbx]
0x1800ce608  sub     ecx, 1
0x1800ce60b  jz      short loc_1800CE612
0x1800ce60d  cmp     ecx, 2
0x1800ce610  jnz     short loc_1800CE621
0x1800ce612  mov     rcx, [rbx+8]; pv
0x1800ce616  test    rcx, rcx
0x1800ce619  jz      short loc_1800CE621
0x1800ce61b  call    cs:__imp_CoTaskMemFree
0x1800ce621  add     rsp, 20h
0x1800ce625  pop     rbx
0x1800ce626  retn
```
