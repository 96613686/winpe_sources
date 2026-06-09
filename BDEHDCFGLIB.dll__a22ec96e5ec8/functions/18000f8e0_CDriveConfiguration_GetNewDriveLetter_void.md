# CDriveConfiguration::GetNewDriveLetter(void)

- ea: `0x18000f8e0`
- end: `0x18000f907`
- name: `?GetNewDriveLetter@CDriveConfiguration@@QEAAGXZ`
- size: `39`
- prototype: `__int64 __fastcall(CDriveConfiguration *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f8e0`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::GetNewDriveLetter(CDriveConfiguration *this)
{
  unsigned __int16 v1; // r8

  v1 = 0;
  if ( *((_DWORD *)this + 16) == 1 )
  {
    return *((unsigned __int16 *)this + 584);
  }
  else if ( *((_DWORD *)this + 16) == 3 )
  {
    return *((unsigned __int16 *)this + 304);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f8e0  mov     edx, [rcx+40h]
0x18000f8e3  xor     r8d, r8d
0x18000f8e6  sub     edx, 1
0x18000f8e9  jz      short loc_18000F8FA
0x18000f8eb  cmp     edx, 2
0x18000f8ee  jnz     short loc_18000F902
0x18000f8f0  movzx   r8d, word ptr [rcx+260h]
0x18000f8f8  jmp     short loc_18000F902
0x18000f8fa  movzx   r8d, word ptr [rcx+490h]
0x18000f902  movzx   eax, r8w
0x18000f906  retn
```
