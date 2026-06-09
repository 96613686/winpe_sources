# PSVCopy

- ea: `0x180050d8c`
- end: `0x180050dcd`
- name: `PSVCopy`
- size: `65`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180050040`
- `0x180050dd4`
- `0x180050ea8`
- `0x1800512b8`
- `0x1800513f8`
- `0x180051538`
- `0x180051880`
- `0x1800520e8`
- `0x180052b68`
- `0x180052ea8`
- `0x180053eb8`

## callees

- `0x180050d8c`

## pseudocode

```c
__int64 __fastcall PSVCopy(__int64 a1, unsigned int *a2, unsigned int *a3)
{
  __int64 result; // rax
  int i; // r9d
  __int64 v6; // rcx

  if ( a2 != a3 )
  {
    result = *a3;
    *a2 = result;
    if ( *a3 )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 488); a2[v6 + 1] = result )
      {
        v6 = i++;
        result = a3[v6 + 1];
      }
    }
    else
    {
      result = a3[1];
      a2[1] = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180050d8c  mov     r10, rcx
0x180050d8f  cmp     rdx, r8
0x180050d92  jz      short locret_180050DCC
0x180050d94  mov     eax, [r8]
0x180050d97  mov     [rdx], eax
0x180050d99  cmp     dword ptr [r8], 0
0x180050d9d  jz      short loc_180050DC5
0x180050d9f  xor     r9d, r9d
0x180050da2  cmp     [rcx+1E8h], r9d
0x180050da9  jle     short locret_180050DCC
0x180050dab  movsxd  rcx, r9d
0x180050dae  inc     r9d
0x180050db1  mov     eax, [r8+rcx*4+4]
0x180050db6  mov     [rdx+rcx*4+4], eax
0x180050dba  cmp     r9d, [r10+1E8h]
0x180050dc1  jl      short loc_180050DAB
0x180050dc3  retn
0x180050dc5  mov     eax, [r8+4]
0x180050dc9  mov     [rdx+4], eax
0x180050dcc  retn
```
