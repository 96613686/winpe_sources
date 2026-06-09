# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140004dd8`
- end: `0x140004df8`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `32`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14002a174`
- `0x14002a380`
- `0x14002a40c`
- `0x14002a490`
- `0x1400302ac`
- `0x14003036c`

## callees

- `0x140004dd8`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( 1 )
  {
    if ( a1 >= wil_details_featureDescriptors_z )
      return 0;
    if ( *a1 )
      break;
    ++a1;
  }
  return a1;
}

```

## disassembly

```asm
0x140004dd8  lea     rax, wil_details_featureDescriptors_z
0x140004ddf  jmp     short loc_140004DEB
0x140004de1  cmp     qword ptr [rcx], 0
0x140004de5  jnz     short loc_140004DF4
0x140004de7  add     rcx, 8
0x140004deb  cmp     rcx, rax
0x140004dee  jb      short loc_140004DE1
0x140004df0  xor     eax, eax
0x140004df2  retn
0x140004df4  mov     rax, rcx
0x140004df7  retn
```
