# CDriveConfiguration::GetTargetDiskNumber(void)

- ea: `0x18000f9c0`
- end: `0x18000f9db`
- name: `?GetTargetDiskNumber@CDriveConfiguration@@QEAAKXZ`
- size: `27`
- prototype: `__int64 __fastcall(CDriveConfiguration *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f9c0`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::GetTargetDiskNumber(CDriveConfiguration *this)
{
  unsigned int v1; // r8d

  v1 = 0;
  if ( *((_DWORD *)this + 16) == 1 || *((_DWORD *)this + 16) == 2 )
    return *((unsigned int *)this + 288);
  return v1;
}

```

## disassembly

```asm
0x18000f9c0  mov     edx, [rcx+40h]
0x18000f9c3  xor     r8d, r8d
0x18000f9c6  sub     edx, 1
0x18000f9c9  jz      short loc_18000F9D0
0x18000f9cb  cmp     edx, 1
0x18000f9ce  jnz     short loc_18000F9D7
0x18000f9d0  mov     r8d, [rcx+480h]
0x18000f9d7  mov     eax, r8d
0x18000f9da  retn
```
