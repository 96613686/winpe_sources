# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14002138c`
- end: `0x1400213e3`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140021710`
- `0x14002b138`

## callees

- `0x14002138c`

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
0x14002138c  cmp     ecx, 80000022h
0x140021392  jz      short loc_1400213D5
0x140021394  cmp     ecx, 0C0000225h
0x14002139a  jz      short loc_1400213D5
0x14002139c  xor     eax, eax
0x14002139e  mov     [r8], rax
0x1400213a1  test    ecx, ecx
0x1400213a3  jz      short loc_1400213B8
0x1400213a5  cmp     ecx, 117h
0x1400213ab  jnz     short loc_1400213DA
0x1400213ad  mov     edx, [rdx+4]
0x1400213b0  and     edx, 80h
0x1400213b6  jmp     short loc_1400213CA
0x1400213b8  mov     eax, [rdx+4]
0x1400213bb  mov     edx, eax
0x1400213bd  and     edx, 40h
0x1400213c0  and     eax, 0B0h
0x1400213c5  shl     edx, 2
0x1400213c8  or      edx, eax
0x1400213ca  shl     edx, 3
0x1400213cd  or      edx, 206h
0x1400213d3  jmp     short loc_1400213DF
0x1400213d5  xor     eax, eax
0x1400213d7  mov     [r8], rax
0x1400213da  mov     edx, 206h
0x1400213df  mov     [r8], edx
0x1400213e2  retn
```
