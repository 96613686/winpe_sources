# CDriveConfiguration::GetNumberOfSteps(void)

- ea: `0x18000f910`
- end: `0x18000f939`
- name: `?GetNumberOfSteps@CDriveConfiguration@@QEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(CDriveConfiguration *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f910`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::GetNumberOfSteps(CDriveConfiguration *this)
{
  unsigned int v1; // edx
  int v2; // eax

  v1 = 0;
  if ( *(_BYTE *)this )
  {
    v2 = *((_DWORD *)this + 16);
    if ( v2 == 1 )
    {
      return 3;
    }
    else if ( v2 == 3 )
    {
      return 2;
    }
    else
    {
      return v2 != 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000f910  mov     al, [rcx]
0x18000f912  xor     edx, edx
0x18000f914  test    al, al
0x18000f916  jz      short loc_18000F936
0x18000f918  mov     eax, [rcx+40h]
0x18000f91b  lea     ecx, [rdx+1]
0x18000f91e  cmp     eax, ecx
0x18000f920  jnz     short loc_18000F927
0x18000f922  lea     edx, [rcx+2]
0x18000f925  jmp     short loc_18000F936
0x18000f927  cmp     eax, 3
0x18000f92a  jnz     short loc_18000F931
0x18000f92c  lea     edx, [rax-1]
0x18000f92f  jmp     short loc_18000F936
0x18000f931  test    eax, eax
0x18000f933  cmovnz  edx, ecx
0x18000f936  mov     eax, edx
0x18000f938  retn
```
