# ec_dec_update

- ea: `0x180009290`
- end: `0x1800092c2`
- name: `ec_dec_update`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, installer_update`

## callers

- `0x18000d040`
- `0x180015a40`

## callees

- `0x180009040`
- `0x180009290`

## pseudocode

```c
__int64 __fastcall ec_dec_update(_DWORD *a1, int a2, int a3, int a4)
{
  int v5; // r8d
  int v6; // r9d

  v5 = a1[10];
  v6 = v5 * (a4 - a3);
  a1[9] -= v6;
  if ( a2 )
    a1[8] = v5 * (a3 - a2);
  else
    a1[8] -= v6;
  return ec_dec_normalize();
}

```

## disassembly

```asm
0x180009290  mov     eax, r8d
0x180009293  mov     r8d, [rcx+28h]
0x180009297  sub     r9d, eax
0x18000929a  imul    r9d, r8d
0x18000929e  sub     [rcx+24h], r9d
0x1800092a2  test    edx, edx
0x1800092a4  jz      short loc_1800092B4
0x1800092a6  sub     eax, edx
0x1800092a8  imul    eax, r8d
0x1800092ac  mov     [rcx+20h], eax
0x1800092af  jmp     ec_dec_normalize
0x1800092b4  mov     eax, [rcx+20h]
0x1800092b7  sub     eax, r9d
0x1800092ba  mov     [rcx+20h], eax
0x1800092bd  jmp     ec_dec_normalize
```
