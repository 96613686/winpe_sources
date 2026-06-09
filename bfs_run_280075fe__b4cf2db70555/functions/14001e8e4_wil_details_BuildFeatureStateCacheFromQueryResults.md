# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14001e8e4`
- end: `0x14001e93b`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001ec10`
- `0x14001f650`

## callees

- `0x14001e8e4`

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
0x14001e8e4  cmp     ecx, 80000022h
0x14001e8ea  jz      short loc_14001E92D
0x14001e8ec  cmp     ecx, 0C0000225h
0x14001e8f2  jz      short loc_14001E92D
0x14001e8f4  xor     eax, eax
0x14001e8f6  mov     [r8], rax
0x14001e8f9  test    ecx, ecx
0x14001e8fb  jz      short loc_14001E910
0x14001e8fd  cmp     ecx, 117h
0x14001e903  jnz     short loc_14001E932
0x14001e905  mov     edx, [rdx+4]
0x14001e908  and     edx, 80h
0x14001e90e  jmp     short loc_14001E922
0x14001e910  mov     eax, [rdx+4]
0x14001e913  mov     edx, eax
0x14001e915  and     edx, 40h
0x14001e918  and     eax, 0B0h
0x14001e91d  shl     edx, 2
0x14001e920  or      edx, eax
0x14001e922  shl     edx, 3
0x14001e925  or      edx, 206h
0x14001e92b  jmp     short loc_14001E937
0x14001e92d  xor     eax, eax
0x14001e92f  mov     [r8], rax
0x14001e932  mov     edx, 206h
0x14001e937  mov     [r8], edx
0x14001e93a  retn
```
