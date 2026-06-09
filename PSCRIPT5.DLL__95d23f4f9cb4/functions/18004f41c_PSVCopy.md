# PSVCopy

- ea: `0x18004f41c`
- end: `0x18004f45c`
- name: `PSVCopy`
- size: `64`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18004e6e4`
- `0x18004f464`
- `0x18004f538`
- `0x18004f944`
- `0x18004fa84`
- `0x18004fbc4`
- `0x18004ff08`
- `0x180050770`
- `0x1800511ec`
- `0x18005152c`
- `0x180052538`

## callees

- `0x18004f41c`

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
0x18004f41c  mov     r10, rcx
0x18004f41f  cmp     rdx, r8
0x18004f422  jz      short locret_18004F45B
0x18004f424  mov     eax, [r8]
0x18004f427  mov     [rdx], eax
0x18004f429  cmp     dword ptr [r8], 0
0x18004f42d  jz      short loc_18004F454
0x18004f42f  xor     r9d, r9d
0x18004f432  cmp     [rcx+1E8h], r9d
0x18004f439  jle     short locret_18004F45B
0x18004f43b  movsxd  rcx, r9d
0x18004f43e  inc     r9d
0x18004f441  mov     eax, [r8+rcx*4+4]
0x18004f446  mov     [rdx+rcx*4+4], eax
0x18004f44a  cmp     r9d, [r10+1E8h]
0x18004f451  jl      short loc_18004F43B
0x18004f453  retn
0x18004f454  mov     eax, [r8+4]
0x18004f458  mov     [rdx+4], eax
0x18004f45b  retn
```
