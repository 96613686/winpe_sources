# _DBG_BASENAME(char const *)

- ea: `0x1800070d0`
- end: `0x1800070f7`
- name: `?_DBG_BASENAME@@YAPEBDPEBD@Z`
- size: `39`
- prototype: `const char *__fastcall(const char *)`
- caller_count: `80`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800013a0`
- `0x180001a40`
- `0x180001d00`
- `0x180001fe0`
- `0x180002470`
- `0x1800029b0`
- `0x1800031b0`
- `0x180003650`
- `0x180003fb0`
- `0x180004670`
- `0x1800049c0`
- `0x180004f90`
- `0x1800057a0`
- `0x180006150`
- `0x180006da0`
- `0x180007100`
- `0x180007180`
- `0x180007730`
- `0x180008000`
- `0x180008110`
- `0x1800084b0`
- `0x1800088d0`
- `0x180008b10`
- `0x180008dc0`
- `0x180008ffc`
- `0x180009180`
- `0x1800094a0`
- `0x180009a10`
- `0x180009f80`
- `0x18000a310`
- `0x18000b1e0`
- `0x18000b3b0`
- `0x18000c2d0`
- `0x18000c75c`
- `0x18000c990`
- `0x18000cfb0`
- `0x18000d1f0`
- `0x18000e220`
- `0x18000e290`
- `0x18000e750`
- `0x18000ee80`
- `0x18000f200`
- `0x18000f7d0`
- `0x18000fe50`
- `0x180010520`
- `0x180010730`
- `0x1800109c0`
- `0x180010bd0`
- `0x180010da0`

## callees

- `0x1800070d0`

## pseudocode

```c
const char *__fastcall _DBG_BASENAME(const char *a1)
{
  __int64 v1; // rax
  const char *result; // rax
  const char *v3; // rdx

  v1 = -1;
  do
    ++v1;
  while ( a1[v1] );
  result = &a1[v1];
  if ( result > a1 )
  {
    do
    {
      v3 = result - 1;
      if ( *(result - 1) == 92 )
        break;
      --result;
    }
    while ( v3 > a1 );
  }
  return result;
}

```

## disassembly

```asm
0x1800070d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800070d4  inc     rax
0x1800070d7  cmp     byte ptr [rcx+rax], 0
0x1800070db  jnz     short loc_1800070D4
0x1800070dd  add     rax, rcx
0x1800070e0  cmp     rax, rcx
0x1800070e3  jbe     short locret_1800070F6
0x1800070e5  lea     rdx, [rax-1]
0x1800070e9  cmp     byte ptr [rdx], 5Ch ; '\'
0x1800070ec  jz      short locret_1800070F6
0x1800070ee  mov     rax, rdx
0x1800070f1  cmp     rdx, rcx
0x1800070f4  ja      short loc_1800070E5
0x1800070f6  retn
```
