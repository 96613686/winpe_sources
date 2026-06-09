# CDriveConfiguration::GetTargetDriveLetter(void)

- ea: `0x18000f9f0`
- end: `0x18000fa0d`
- name: `?GetTargetDriveLetter@CDriveConfiguration@@QEAAGXZ`
- size: `29`
- prototype: `__int64 __fastcall(CDriveConfiguration *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f9f0`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::GetTargetDriveLetter(CDriveConfiguration *this)
{
  unsigned __int16 v1; // r8

  v1 = 0;
  if ( *((_DWORD *)this + 16) == 1 || *((_DWORD *)this + 16) == 2 )
    return *((unsigned __int16 *)this + 574);
  return v1;
}

```

## disassembly

```asm
0x18000f9f0  mov     edx, [rcx+40h]
0x18000f9f3  xor     r8d, r8d
0x18000f9f6  sub     edx, 1
0x18000f9f9  jz      short loc_18000FA00
0x18000f9fb  cmp     edx, 1
0x18000f9fe  jnz     short loc_18000FA08
0x18000fa00  movzx   r8d, word ptr [rcx+47Ch]
0x18000fa08  movzx   eax, r8w
0x18000fa0c  retn
```
