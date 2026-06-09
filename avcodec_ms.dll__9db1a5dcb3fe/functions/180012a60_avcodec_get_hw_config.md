# avcodec_get_hw_config

- ea: `0x180012a60`
- end: `0x180012a99`
- name: `avcodec_get_hw_config`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006e20`

## callees

- `0x180012a60`

## pseudocode

```c
__int64 __fastcall avcodec_get_hw_config(__int64 a1, int a2)
{
  _QWORD *v2; // r8
  __int64 v3; // r9
  __int64 v4; // rdx

  v2 = *(_QWORD **)(a1 + 168);
  if ( v2 && a2 >= 0 )
  {
    v3 = a2;
    v4 = 0;
    while ( *v2 )
    {
      ++v4;
      ++v2;
      if ( v4 > v3 )
      {
        _mm_lfence();
        return *(_QWORD *)(*(_QWORD *)(a1 + 168) + 8 * v3);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012a60  mov     r8, [rcx+0A8h]
0x180012a67  test    r8, r8
0x180012a6a  jz      short loc_180012A96
0x180012a6c  test    edx, edx
0x180012a6e  js      short loc_180012A96
0x180012a70  movsxd  r9, edx
0x180012a73  xor     edx, edx
0x180012a75  cmp     qword ptr [r8], 0
0x180012a79  jz      short loc_180012A96
0x180012a7b  inc     rdx
0x180012a7e  add     r8, 8
0x180012a82  cmp     rdx, r9
0x180012a85  jle     short loc_180012A75
0x180012a87  lfence
0x180012a8a  mov     rax, [rcx+0A8h]
0x180012a91  mov     rax, [rax+r9*8]
0x180012a95  retn
0x180012a96  xor     eax, eax
0x180012a98  retn
```
