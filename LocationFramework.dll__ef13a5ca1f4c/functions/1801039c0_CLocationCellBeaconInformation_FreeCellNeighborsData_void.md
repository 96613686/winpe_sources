# CLocationCellBeaconInformation::FreeCellNeighborsData(void)

- ea: `0x1801039c0`
- end: `0x180103a7d`
- name: `?FreeCellNeighborsData@CLocationCellBeaconInformation@@AEAAXXZ`
- size: `189`
- prototype: `void __fastcall(CLocationCellBeaconInformation *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180103500`
- `0x180103870`

## callees

- `0x1801039c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801039d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801039f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180103a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180103a2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180103a49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180103a66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801039d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801039f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180103a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180103a2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180103a49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180103a66`

## pseudocode

```c
void __fastcall CLocationCellBeaconInformation::FreeCellNeighborsData(CLocationCellBeaconInformation *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  v2 = (void *)*((_QWORD *)this + 16);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 16) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 18);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 18) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 20);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 20) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 22);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 22) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 24);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 24) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 26);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 26) = 0;
  }
}

```

## disassembly

```asm
0x1801039c0  push    rbx
0x1801039c2  sub     rsp, 20h
0x1801039c6  mov     rbx, rcx
0x1801039c9  mov     rcx, [rcx+80h]; pv
0x1801039d0  test    rcx, rcx
0x1801039d3  jz      short loc_1801039E6
0x1801039d5  call    cs:__imp_CoTaskMemFree
0x1801039db  mov     qword ptr [rbx+80h], 0
0x1801039e6  mov     rcx, [rbx+90h]; pv
0x1801039ed  test    rcx, rcx
0x1801039f0  jz      short loc_180103A03
0x1801039f2  call    cs:__imp_CoTaskMemFree
0x1801039f8  mov     qword ptr [rbx+90h], 0
0x180103a03  mov     rcx, [rbx+0A0h]; pv
0x180103a0a  test    rcx, rcx
0x180103a0d  jz      short loc_180103A20
0x180103a0f  call    cs:__imp_CoTaskMemFree
0x180103a15  mov     qword ptr [rbx+0A0h], 0
0x180103a20  mov     rcx, [rbx+0B0h]; pv
0x180103a27  test    rcx, rcx
0x180103a2a  jz      short loc_180103A3D
0x180103a2c  call    cs:__imp_CoTaskMemFree
0x180103a32  mov     qword ptr [rbx+0B0h], 0
0x180103a3d  mov     rcx, [rbx+0C0h]; pv
0x180103a44  test    rcx, rcx
0x180103a47  jz      short loc_180103A5A
0x180103a49  call    cs:__imp_CoTaskMemFree
0x180103a4f  mov     qword ptr [rbx+0C0h], 0
0x180103a5a  mov     rcx, [rbx+0D0h]; pv
0x180103a61  test    rcx, rcx
0x180103a64  jz      short loc_180103A77
0x180103a66  call    cs:__imp_CoTaskMemFree
0x180103a6c  mov     qword ptr [rbx+0D0h], 0
0x180103a77  add     rsp, 20h
0x180103a7b  pop     rbx
0x180103a7c  retn
```
