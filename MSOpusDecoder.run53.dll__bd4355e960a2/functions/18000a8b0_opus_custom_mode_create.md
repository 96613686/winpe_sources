# opus_custom_mode_create

- ea: `0x18000a8b0`
- end: `0x18000a914`
- name: `opus_custom_mode_create`
- size: `100`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800072f0`
- `0x180007330`
- `0x180008680`

## callees

- `0x18000a8b0`

## pseudocode

```c
_DWORD *__fastcall opus_custom_mode_create(int a1, int a2, _DWORD *a3)
{
  _DWORD *result; // rax
  int v5; // ecx

  result = dword_180028A70;
  v5 = 0;
  while ( a1 != dword_180028A70[0] || a2 << v5 != unk_180028A9C * unk_180028AA0 )
  {
    if ( ++v5 >= 4 )
    {
      if ( a3 )
        *a3 = -1;
      return 0;
    }
  }
  if ( a3 )
    *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x18000a8b0  mov     [rsp+arg_0], rbx
0x18000a8b5  mov     rax, cs:off_180028B10
0x18000a8bc  mov     r10d, ecx
0x18000a8bf  mov     r9, r8
0x18000a8c2  mov     ebx, edx
0x18000a8c4  xor     ecx, ecx
0x18000a8c6  mov     r11d, [rax]
0x18000a8c9  nop     dword ptr [rax+00000000h]
0x18000a8d0  cmp     r10d, r11d
0x18000a8d3  jnz     short loc_18000A8E7
0x18000a8d5  mov     r8d, [rax+30h]
0x18000a8d9  mov     edx, ebx
0x18000a8db  imul    r8d, [rax+2Ch]
0x18000a8e0  shl     edx, cl
0x18000a8e2  cmp     edx, r8d
0x18000a8e5  jz      short loc_18000A902
0x18000a8e7  inc     ecx
0x18000a8e9  cmp     ecx, 4
0x18000a8ec  jl      short loc_18000A8D0
0x18000a8ee  test    r9, r9
0x18000a8f1  jz      short loc_18000A8FA
0x18000a8f3  mov     dword ptr [r9], 0FFFFFFFFh
0x18000a8fa  xor     eax, eax
0x18000a8fc  mov     rbx, [rsp+arg_0]
0x18000a901  retn
0x18000a902  test    r9, r9
0x18000a905  jz      short loc_18000A8FC
0x18000a907  mov     rbx, [rsp+arg_0]
0x18000a90c  mov     dword ptr [r9], 0
0x18000a913  retn
```
