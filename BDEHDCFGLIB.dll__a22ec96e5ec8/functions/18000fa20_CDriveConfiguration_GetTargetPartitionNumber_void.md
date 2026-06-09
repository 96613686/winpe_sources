# CDriveConfiguration::GetTargetPartitionNumber(void)

- ea: `0x18000fa20`
- end: `0x18000fa3b`
- name: `?GetTargetPartitionNumber@CDriveConfiguration@@QEAAKXZ`
- size: `27`
- prototype: `__int64 __fastcall(CDriveConfiguration *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000fa20`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::GetTargetPartitionNumber(CDriveConfiguration *this)
{
  unsigned int v1; // r8d

  v1 = 0;
  if ( *((_DWORD *)this + 16) == 1 || *((_DWORD *)this + 16) == 2 )
    return *((unsigned int *)this + 289);
  return v1;
}

```

## disassembly

```asm
0x18000fa20  mov     edx, [rcx+40h]
0x18000fa23  xor     r8d, r8d
0x18000fa26  sub     edx, 1
0x18000fa29  jz      short loc_18000FA30
0x18000fa2b  cmp     edx, 1
0x18000fa2e  jnz     short loc_18000FA37
0x18000fa30  mov     r8d, [rcx+484h]
0x18000fa37  mov     eax, r8d
0x18000fa3a  retn
```
