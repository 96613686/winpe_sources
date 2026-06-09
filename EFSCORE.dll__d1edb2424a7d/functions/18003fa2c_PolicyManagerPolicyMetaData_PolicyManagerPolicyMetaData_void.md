# PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(void)

- ea: `0x18003fa2c`
- end: `0x18003fabf`
- name: `??1PolicyManagerPolicyMetaData@@QEAA@XZ`
- size: `147`
- prototype: `void __fastcall(PolicyManagerPolicyMetaData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003fac8`

## callees

- `0x18003fa2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fab3`

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
0x18003fa2c  push    rbx
0x18003fa2e  sub     rsp, 20h
0x18003fa32  mov     rbx, rcx
0x18003fa35  mov     rcx, [rcx+20h]; pv
0x18003fa39  test    rcx, rcx
0x18003fa3c  jz      short loc_18003FA44
0x18003fa3e  call    cs:__imp_CoTaskMemFree
0x18003fa44  mov     rcx, [rbx+28h]; pv
0x18003fa48  test    rcx, rcx
0x18003fa4b  jz      short loc_18003FA53
0x18003fa4d  call    cs:__imp_CoTaskMemFree
0x18003fa53  mov     rcx, [rbx+30h]; pv
0x18003fa57  test    rcx, rcx
0x18003fa5a  jz      short loc_18003FA62
0x18003fa5c  call    cs:__imp_CoTaskMemFree
0x18003fa62  mov     rcx, [rbx+38h]; pv
0x18003fa66  test    rcx, rcx
0x18003fa69  jz      short loc_18003FA71
0x18003fa6b  call    cs:__imp_CoTaskMemFree
0x18003fa71  mov     rcx, [rbx+48h]; pv
0x18003fa75  test    rcx, rcx
0x18003fa78  jz      short loc_18003FA80
0x18003fa7a  call    cs:__imp_CoTaskMemFree
0x18003fa80  mov     rcx, [rbx+58h]; pv
0x18003fa84  test    rcx, rcx
0x18003fa87  jz      short loc_18003FA8F
0x18003fa89  call    cs:__imp_CoTaskMemFree
0x18003fa8f  mov     rcx, [rbx+68h]; pv
0x18003fa93  test    rcx, rcx
0x18003fa96  jz      short loc_18003FA9E
0x18003fa98  call    cs:__imp_CoTaskMemFree
0x18003fa9e  mov     ecx, [rbx]
0x18003faa0  sub     ecx, 1
0x18003faa3  jz      short loc_18003FAAA
0x18003faa5  cmp     ecx, 2
0x18003faa8  jnz     short loc_18003FAB9
0x18003faaa  mov     rcx, [rbx+8]; pv
0x18003faae  test    rcx, rcx
0x18003fab1  jz      short loc_18003FAB9
0x18003fab3  call    cs:__imp_CoTaskMemFree
0x18003fab9  add     rsp, 20h
0x18003fabd  pop     rbx
0x18003fabe  retn
```
