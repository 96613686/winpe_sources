# BiGetBcdDeviceType

- ea: `0x140016f38`
- end: `0x140016fde`
- name: `BiGetBcdDeviceType`
- size: `166`
- prototype: `const wchar_t *__fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001a6b0`
- `0x140020e68`

## callees

- `0x140016f38`

## string_xrefs

- `0x140016fce`: `COMPOSITE`

## pseudocode

```c
const wchar_t *__fastcall BiGetBcdDeviceType(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx

  if ( a1 <= 8 )
  {
    if ( a1 == 8 )
      return L"LOCATE";
    v1 = a1 - 1;
    if ( !v1 )
      return L"BOOT_DEVICE";
    v2 = v1 - 1;
    if ( !v2 )
      return L"PARTITION";
    v3 = v2 - 1;
    if ( !v3 )
      return L"FILE";
    v4 = v3 - 1;
    if ( !v4 )
      return L"RAMDISK";
    v5 = v4 - 2;
    if ( !v5 )
      return L"QUALIFIED_PARTITION";
    if ( v5 == 1 )
      return L"VMBUS";
    return L"UNKNOWN";
  }
  v7 = a1 - 9;
  if ( !v7 )
    return L"URI";
  v8 = v7 - 1;
  if ( !v8 )
    return L"COMPOSITE";
  v9 = v8 - 1;
  if ( !v9 )
    return L"CIMFS";
  v10 = v9 - 1;
  if ( !v10 )
    return L"MEMDISK";
  if ( v10 != 1 )
    return L"UNKNOWN";
  return L"QUALIFIED_HARD_DISK";
}

```

## disassembly

```asm
0x140016f38  cmp     ecx, 8
0x140016f3b  ja      short loc_140016F95
0x140016f3d  jz      short loc_140016F8D
0x140016f3f  sub     ecx, 1
0x140016f42  jz      short loc_140016F85
0x140016f44  sub     ecx, 1
0x140016f47  jz      short loc_140016F7D
0x140016f49  sub     ecx, 1
0x140016f4c  jz      short loc_140016F75
0x140016f4e  sub     ecx, 1
0x140016f51  jz      short loc_140016F6D
0x140016f53  sub     ecx, 2
0x140016f56  jz      short loc_140016F65
0x140016f58  cmp     ecx, 1
0x140016f5b  jnz     short loc_140016FAE
0x140016f5d  lea     rax, aVmbus; "VMBUS"
0x140016f64  retn
0x140016f65  lea     rax, aQualifiedParti; "QUALIFIED_PARTITION"
0x140016f6c  retn
0x140016f6d  lea     rax, aRamdisk_0; "RAMDISK"
0x140016f74  retn
0x140016f75  lea     rax, aFile; "FILE"
0x140016f7c  retn
0x140016f7d  lea     rax, aPartition_0; "PARTITION"
0x140016f84  retn
0x140016f85  lea     rax, aBootDevice; "BOOT_DEVICE"
0x140016f8c  retn
0x140016f8d  lea     rax, aLocate; "LOCATE"
0x140016f94  retn
0x140016f95  sub     ecx, 9
0x140016f98  jz      short loc_140016FD6
0x140016f9a  sub     ecx, 1
0x140016f9d  jz      short loc_140016FCE
0x140016f9f  sub     ecx, 1
0x140016fa2  jz      short loc_140016FC6
0x140016fa4  sub     ecx, 1
0x140016fa7  jz      short loc_140016FBE
0x140016fa9  cmp     ecx, 1
0x140016fac  jz      short loc_140016FB6
0x140016fae  lea     rax, aUnknown_0; "UNKNOWN"
0x140016fb5  retn
0x140016fb6  lea     rax, aQualifiedHardD; "QUALIFIED_HARD_DISK"
0x140016fbd  retn
0x140016fbe  lea     rax, aMemdisk; "MEMDISK"
0x140016fc5  retn
0x140016fc6  lea     rax, aCimfs; "CIMFS"
0x140016fcd  retn
0x140016fce  lea     rax, aComposite; "COMPOSITE"
0x140016fd5  retn
0x140016fd6  lea     rax, aUri; "URI"
0x140016fdd  retn
```
