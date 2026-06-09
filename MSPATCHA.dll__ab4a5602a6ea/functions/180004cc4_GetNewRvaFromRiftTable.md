# GetNewRvaFromRiftTable

- ea: `0x180004cc4`
- end: `0x180004d07`
- name: `GetNewRvaFromRiftTable`
- size: `67`
- prototype: `__int64 __fastcall(int *, unsigned int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000541c`
- `0x180005754`
- `0x180005934`
- `0x180005d5c`
- `0x180005f64`
- `0x1800061e4`
- `0x18000677c`
- `0x180006858`
- `0x180006928`
- `0x180006a60`

## callees

- `0x180004cc4`

## pseudocode

```c
__int64 __fastcall GetNewRvaFromRiftTable(int *a1, unsigned int a2)
{
  __int64 v2; // r10
  unsigned int v4; // r9d
  unsigned int v5; // ecx
  __int64 v6; // rax
  __int64 v7; // rdx

  v2 = *((_QWORD *)a1 + 1);
  v4 = *a1;
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = (v4 + v5) >> 1;
    v7 = v6;
    if ( *(_DWORD *)(v2 + 8 * v6) >= a2 )
    {
      if ( *(_DWORD *)(v2 + 8 * v6) <= a2 )
        return a2 + *(_DWORD *)(v2 + 8 * v7 + 4) - *(_DWORD *)(v2 + 8 * v7);
      v4 = v6;
    }
    else
    {
      v5 = v6 + 1;
    }
  }
  if ( !v5 )
    return a2;
  v7 = v5 - 1;
  return a2 + *(_DWORD *)(v2 + 8 * v7 + 4) - *(_DWORD *)(v2 + 8 * v7);
}

```

## disassembly

```asm
0x180004cc4  mov     r10, [rcx+8]
0x180004cc8  mov     r8d, edx
0x180004ccb  mov     r9d, [rcx]
0x180004cce  xor     ecx, ecx
0x180004cd0  cmp     ecx, r9d
0x180004cd3  jnb     short loc_180004CEF
0x180004cd5  lea     eax, [r9+rcx]
0x180004cd9  shr     eax, 1
0x180004cdb  mov     edx, eax
0x180004cdd  cmp     [r10+rax*8], r8d
0x180004ce1  jnb     short loc_180004CE8
0x180004ce3  lea     ecx, [rax+1]
0x180004ce6  jmp     short loc_180004CD0
0x180004ce8  jbe     short loc_180004CFA
0x180004cea  mov     r9d, edx
0x180004ced  jmp     short loc_180004CD0
0x180004cef  test    ecx, ecx
0x180004cf1  jnz     short loc_180004CF7
0x180004cf3  mov     eax, r8d
0x180004cf6  retn
0x180004cf7  lea     edx, [rcx-1]
0x180004cfa  mov     eax, [r10+rdx*8+4]
0x180004cff  sub     eax, [r10+rdx*8]
0x180004d03  add     eax, r8d
0x180004d06  retn
```
