# av_hwdevice_hwconfig_alloc

- ea: `0x18003f280`
- end: `0x18003f299`
- name: `av_hwdevice_hwconfig_alloc`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18003f280`
- `0x180044aa0`

## pseudocode

```c
void *__fastcall av_hwdevice_hwconfig_alloc(__int64 a1)
{
  size_t v1; // rcx

  v1 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 40LL) + 32LL);
  if ( v1 )
    return av_mallocz(v1);
  else
    return 0;
}

```

## disassembly

```asm
0x18003f280  mov     rax, [rcx+8]
0x18003f284  mov     rcx, [rax+28h]
0x18003f288  mov     rcx, [rcx+20h]
0x18003f28c  test    rcx, rcx
0x18003f28f  jnz     short loc_18003F294
0x18003f291  xor     eax, eax
0x18003f293  retn
0x18003f294  jmp     av_mallocz
```
