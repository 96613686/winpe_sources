# CDriveConfiguration::GetStepExecutionOrder(_BDECFG_STEP_ID)

- ea: `0x18000f950`
- end: `0x18000f9ab`
- name: `?GetStepExecutionOrder@CDriveConfiguration@@QEAAKW4_BDECFG_STEP_ID@@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f950`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::GetStepExecutionOrder(__int64 a1, int a2)
{
  unsigned int v2; // r8d
  int v3; // edx
  int v4; // eax

  v2 = -1;
  if ( *(_BYTE *)a1 )
  {
    if ( a2 )
    {
      v3 = a2 - 1;
      if ( !v3 )
      {
        if ( *(_DWORD *)(a1 + 64) == 1 )
          return 1;
        if ( *(_DWORD *)(a1 + 64) != 3 )
          return v2;
        return 0;
      }
      if ( v3 == 1 )
      {
        v4 = *(_DWORD *)(a1 + 64);
        switch ( v4 )
        {
          case 1:
            return 2;
          case 3:
            return 1;
          case 0:
            return v2;
        }
        return 0;
      }
    }
    else if ( *(_DWORD *)(a1 + 64) == 1 )
    {
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000f950  mov     al, [rcx]
0x18000f952  or      r8d, 0FFFFFFFFh
0x18000f956  mov     r9, rcx
0x18000f959  test    al, al
0x18000f95b  jz      short loc_18000F9A7
0x18000f95d  test    edx, edx
0x18000f95f  jz      short loc_18000F99C
0x18000f961  sub     edx, 1
0x18000f964  jz      short loc_18000F98E
0x18000f966  cmp     edx, 1
0x18000f969  jnz     short loc_18000F9A7
0x18000f96b  mov     eax, [rcx+40h]
0x18000f96e  cmp     eax, edx
0x18000f970  jnz     short loc_18000F978
0x18000f972  lea     r8d, [rdx+1]
0x18000f976  jmp     short loc_18000F9A7
0x18000f978  cmp     eax, 3
0x18000f97b  jnz     short loc_18000F985
0x18000f97d  mov     r8d, 1
0x18000f983  jmp     short loc_18000F9A7
0x18000f985  test    eax, eax
0x18000f987  jz      short loc_18000F9A7
0x18000f989  xor     r8d, r8d
0x18000f98c  jmp     short loc_18000F9A7
0x18000f98e  cmp     dword ptr [rcx+40h], 1
0x18000f992  jz      short loc_18000F97D
0x18000f994  cmp     dword ptr [rcx+40h], 3
0x18000f998  jnz     short loc_18000F9A7
0x18000f99a  jmp     short loc_18000F989
0x18000f99c  xor     ecx, ecx
0x18000f99e  cmp     dword ptr [r9+40h], 1
0x18000f9a3  cmovz   r8d, ecx
0x18000f9a7  mov     eax, r8d
0x18000f9aa  retn
```
