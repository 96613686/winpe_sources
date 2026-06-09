# CDriveConfiguration::GetTargetPartitionSize(void)

- ea: `0x18000fa50`
- end: `0x18000fa79`
- name: `?GetTargetPartitionSize@CDriveConfiguration@@QEAA_KXZ`
- size: `41`
- prototype: `unsigned __int64 __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000fa50`

## pseudocode

```c
unsigned __int64 __fastcall CDriveConfiguration::GetTargetPartitionSize(CDriveConfiguration *this)
{
  __int64 v1; // r8

  v1 = 0;
  if ( *((_DWORD *)this + 16) == 1 || *((_DWORD *)this + 16) == 2 )
    return *((_QWORD *)this + 140);
  if ( *((_DWORD *)this + 16) == 3 )
    return *((_QWORD *)this + 75);
  return v1;
}

```

## disassembly

```asm
0x18000fa50  mov     edx, [rcx+40h]
0x18000fa53  xor     r8d, r8d
0x18000fa56  sub     edx, 1
0x18000fa59  jz      short loc_18000FA6E
0x18000fa5b  sub     edx, 1
0x18000fa5e  jz      short loc_18000FA6E
0x18000fa60  cmp     edx, 1
0x18000fa63  jnz     short loc_18000FA75
0x18000fa65  mov     r8, [rcx+258h]
0x18000fa6c  jmp     short loc_18000FA75
0x18000fa6e  mov     r8, [rcx+460h]
0x18000fa75  mov     rax, r8
0x18000fa78  retn
```
