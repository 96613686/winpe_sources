# HrRegSetValueStringW(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180009d00`
- end: `0x180009d33`
- name: `?HrRegSetValueStringW@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `51`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ca70`

## callees

- `0x180009d00`
- `0x18000be30`

## pseudocode

```c
__int64 __fastcall HrRegSetValueStringW(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // rax

  v4 = -1;
  do
    ++v4;
  while ( a4[v4] );
  return HrSHSetValueW((int)a1, (int)a2, (int)a3, 1, a4, 2 * (int)v4 + 2);
}

```

## disassembly

```asm
0x180009d00  sub     rsp, 38h
0x180009d04  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009d08  inc     rax
0x180009d0b  cmp     word ptr [r9+rax*2], 0
0x180009d11  jnz     short loc_180009D08
0x180009d13  lea     eax, ds:2[rax*2]
0x180009d1a  mov     [rsp+38h+var_10], eax; DWORD
0x180009d1e  mov     [rsp+38h+var_18], r9; LPCVOID
0x180009d23  mov     r9d, 1; int
0x180009d29  call    HrSHSetValueW
0x180009d2e  add     rsp, 38h
0x180009d32  retn
```
