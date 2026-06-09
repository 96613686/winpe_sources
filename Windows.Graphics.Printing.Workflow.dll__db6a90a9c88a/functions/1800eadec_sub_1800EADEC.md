# sub_1800EADEC

- ea: `0x1800eadec`
- end: `0x1800eae18`
- name: `sub_1800EADEC`
- size: `44`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e9e3c`
- `0x1800ea4d0`
- `0x1800ea5e8`
- `0x1800ea720`
- `0x1800ea82c`
- `0x1800ea92c`
- `0x1800eaa38`

## callees

- `0x1800eadec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eadfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eadfd`

## pseudocode

```c
void __fastcall sub_1800EADEC(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800eadec  push    rbx
0x1800eadee  sub     rsp, 20h
0x1800eadf2  mov     rbx, rcx
0x1800eadf5  mov     rcx, [rcx]; pv
0x1800eadf8  test    rcx, rcx
0x1800eadfb  jz      short loc_1800EAE12
0x1800eadfd  call    cs:CoTaskMemFree
0x1800eae03  mov     qword ptr [rbx], 0
0x1800eae0a  mov     qword ptr [rbx+8], 0
0x1800eae12  add     rsp, 20h
0x1800eae16  pop     rbx
0x1800eae17  retn
```
