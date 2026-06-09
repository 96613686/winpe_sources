# PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(void)

- ea: `0x18002f69c`
- end: `0x18002f760`
- name: `??1PolicyManagerPolicyMetaData@@QEAA@XZ`
- size: `196`
- prototype: `void __fastcall(PolicyManagerPolicyMetaData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f768`

## callees

- `0x18002f69c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f6ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f6c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f6d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f6ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f717`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f72c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f74d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f6ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f6c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f6d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f6ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f717`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f72c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f74d`

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
0x18002f69c  push    rbx
0x18002f69e  sub     rsp, 20h
0x18002f6a2  mov     rbx, rcx
0x18002f6a5  mov     rcx, [rcx+20h]; pv
0x18002f6a9  test    rcx, rcx
0x18002f6ac  jz      short loc_18002F6BA
0x18002f6ae  call    cs:__imp_CoTaskMemFree
0x18002f6b5  nop     dword ptr [rax+rax+00h]
0x18002f6ba  mov     rcx, [rbx+28h]; pv
0x18002f6be  test    rcx, rcx
0x18002f6c1  jz      short loc_18002F6CF
0x18002f6c3  call    cs:__imp_CoTaskMemFree
0x18002f6ca  nop     dword ptr [rax+rax+00h]
0x18002f6cf  mov     rcx, [rbx+30h]; pv
0x18002f6d3  test    rcx, rcx
0x18002f6d6  jz      short loc_18002F6E4
0x18002f6d8  call    cs:__imp_CoTaskMemFree
0x18002f6df  nop     dword ptr [rax+rax+00h]
0x18002f6e4  mov     rcx, [rbx+38h]; pv
0x18002f6e8  test    rcx, rcx
0x18002f6eb  jz      short loc_18002F6F9
0x18002f6ed  call    cs:__imp_CoTaskMemFree
0x18002f6f4  nop     dword ptr [rax+rax+00h]
0x18002f6f9  mov     rcx, [rbx+48h]; pv
0x18002f6fd  test    rcx, rcx
0x18002f700  jz      short loc_18002F70E
0x18002f702  call    cs:__imp_CoTaskMemFree
0x18002f709  nop     dword ptr [rax+rax+00h]
0x18002f70e  mov     rcx, [rbx+58h]; pv
0x18002f712  test    rcx, rcx
0x18002f715  jz      short loc_18002F723
0x18002f717  call    cs:__imp_CoTaskMemFree
0x18002f71e  nop     dword ptr [rax+rax+00h]
0x18002f723  mov     rcx, [rbx+68h]; pv
0x18002f727  test    rcx, rcx
0x18002f72a  jz      short loc_18002F738
0x18002f72c  call    cs:__imp_CoTaskMemFree
0x18002f733  nop     dword ptr [rax+rax+00h]
0x18002f738  mov     ecx, [rbx]
0x18002f73a  sub     ecx, 1
0x18002f73d  jz      short loc_18002F744
0x18002f73f  cmp     ecx, 2
0x18002f742  jnz     short loc_18002F759
0x18002f744  mov     rcx, [rbx+8]; pv
0x18002f748  test    rcx, rcx
0x18002f74b  jz      short loc_18002F759
0x18002f74d  call    cs:__imp_CoTaskMemFree
0x18002f754  nop     dword ptr [rax+rax+00h]
0x18002f759  add     rsp, 20h
0x18002f75d  pop     rbx
0x18002f75e  retn
```
