# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800164bc`
- end: `0x18001650b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180017b40`
- `0x18001ac08`

## callees

- `0x1800164bc`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  unsigned __int16 *v5; // rdx
  __int64 result; // rax

  v3 = 2147483646;
  v4 = 260;
  do
  {
    if ( !v3 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = a1 - 1;
  result = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v5 = a1;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x1800164bc  mov     eax, 7FFFFFFEh
0x1800164c1  mov     r9d, 104h
0x1800164c7  xor     r10d, r10d
0x1800164ca  test    rax, rax
0x1800164cd  jz      short loc_1800164EC
0x1800164cf  movzx   edx, word ptr [r8]
0x1800164d3  test    dx, dx
0x1800164d6  jz      short loc_1800164EC
0x1800164d8  mov     [rcx], dx
0x1800164db  add     r8, 2
0x1800164df  add     rcx, 2
0x1800164e3  dec     rax
0x1800164e6  sub     r9, 1
0x1800164ea  jnz     short loc_1800164CA
0x1800164ec  mov     rax, r9
0x1800164ef  lea     rdx, [rcx-2]
0x1800164f3  neg     rax
0x1800164f6  sbb     eax, eax
0x1800164f8  not     eax
0x1800164fa  and     eax, 8007007Ah
0x1800164ff  test    r9, r9
0x180016502  cmovnz  rdx, rcx
0x180016506  mov     [rdx], r10w
0x18001650a  retn
```
