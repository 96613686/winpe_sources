# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14002a114`
- end: `0x14002a16b`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002a490`
- `0x14003036c`

## callees

- `0x14002a114`

## pseudocode

```c
__int64 __fastcall wil_details_BuildFeatureStateCacheFromQueryResults(int a1, __int64 a2, _QWORD *a3)
{
  __int64 result; // rax
  int v4; // edx
  int v5; // edx

  if ( a1 == -2147483614 || a1 == -1073741275 )
  {
    result = 0;
    *a3 = 0;
    goto LABEL_9;
  }
  result = 0;
  *a3 = 0;
  if ( !a1 )
  {
    result = *(_DWORD *)(a2 + 4) & 0xB0;
    v4 = result | (4 * (*(_DWORD *)(a2 + 4) & 0x40));
    goto LABEL_7;
  }
  if ( a1 != 279 )
  {
LABEL_9:
    v5 = 518;
    goto LABEL_10;
  }
  v4 = *(_DWORD *)(a2 + 4) & 0x80;
LABEL_7:
  v5 = (8 * v4) | 0x206;
LABEL_10:
  *(_DWORD *)a3 = v5;
  return result;
}

```

## disassembly

```asm
0x14002a114  cmp     ecx, 80000022h
0x14002a11a  jz      short loc_14002A15D
0x14002a11c  cmp     ecx, 0C0000225h
0x14002a122  jz      short loc_14002A15D
0x14002a124  xor     eax, eax
0x14002a126  mov     [r8], rax
0x14002a129  test    ecx, ecx
0x14002a12b  jz      short loc_14002A140
0x14002a12d  cmp     ecx, 117h
0x14002a133  jnz     short loc_14002A162
0x14002a135  mov     edx, [rdx+4]
0x14002a138  and     edx, 80h
0x14002a13e  jmp     short loc_14002A152
0x14002a140  mov     eax, [rdx+4]
0x14002a143  mov     edx, eax
0x14002a145  and     edx, 40h
0x14002a148  and     eax, 0B0h
0x14002a14d  shl     edx, 2
0x14002a150  or      edx, eax
0x14002a152  shl     edx, 3
0x14002a155  or      edx, 206h
0x14002a15b  jmp     short loc_14002A167
0x14002a15d  xor     eax, eax
0x14002a15f  mov     [r8], rax
0x14002a162  mov     edx, 206h
0x14002a167  mov     [r8], edx
0x14002a16a  retn
```
