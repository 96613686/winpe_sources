# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140011224`
- end: `0x140011246`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400213ec`
- `0x14002157c`
- `0x140021610`
- `0x14002168c`
- `0x140021710`
- `0x14002b078`
- `0x14002b138`

## callees

- `0x140011224`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( a1 < wil_details_featureDescriptors_a )
  {
    if ( *a1 )
      return a1;
    ++a1;
  }
  return 0;
}

```

## disassembly

```asm
0x140011224  xchg    ax, ax
0x140011226  lea     rax, wil_details_featureDescriptors_a
0x14001122d  cmp     rcx, rax
0x140011230  jnb     short loc_140011243
0x140011232  cmp     qword ptr [rcx], 0
0x140011236  jnz     short loc_14001123E
0x140011238  add     rcx, 8
0x14001123c  jmp     short loc_140011226
0x14001123e  mov     rax, rcx
0x140011241  retn
0x140011243  xor     eax, eax
0x140011245  retn
```
