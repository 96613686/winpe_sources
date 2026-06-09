# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14000b534`
- end: `0x14000b58b`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b8c0`
- `0x1400162ac`

## callees

- `0x14000b534`

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
0x14000b534  cmp     ecx, 80000022h
0x14000b53a  jz      short loc_14000B57D
0x14000b53c  cmp     ecx, 0C0000225h
0x14000b542  jz      short loc_14000B57D
0x14000b544  xor     eax, eax
0x14000b546  mov     [r8], rax
0x14000b549  test    ecx, ecx
0x14000b54b  jz      short loc_14000B560
0x14000b54d  cmp     ecx, 117h
0x14000b553  jnz     short loc_14000B582
0x14000b555  mov     edx, [rdx+4]
0x14000b558  and     edx, 80h
0x14000b55e  jmp     short loc_14000B572
0x14000b560  mov     eax, [rdx+4]
0x14000b563  mov     edx, eax
0x14000b565  and     edx, 40h
0x14000b568  and     eax, 0B0h
0x14000b56d  shl     edx, 2
0x14000b570  or      edx, eax
0x14000b572  shl     edx, 3
0x14000b575  or      edx, 206h
0x14000b57b  jmp     short loc_14000B587
0x14000b57d  xor     eax, eax
0x14000b57f  mov     [r8], rax
0x14000b582  mov     edx, 206h
0x14000b587  mov     [r8], edx
0x14000b58a  retn
```
