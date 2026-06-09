# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000c90c`
- end: `0x18000c95b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e30`

## callees

- `0x18000c90c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  unsigned __int16 *v5; // rdx
  __int64 result; // rax

  v3 = 2147483646;
  v4 = 32;
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
0x18000c90c  mov     eax, 7FFFFFFEh
0x18000c911  mov     r9d, 20h ; ' '
0x18000c917  xor     r10d, r10d
0x18000c91a  test    rax, rax
0x18000c91d  jz      short loc_18000C93C
0x18000c91f  movzx   edx, word ptr [r8]
0x18000c923  test    dx, dx
0x18000c926  jz      short loc_18000C93C
0x18000c928  mov     [rcx], dx
0x18000c92b  add     r8, 2
0x18000c92f  add     rcx, 2
0x18000c933  dec     rax
0x18000c936  sub     r9, 1
0x18000c93a  jnz     short loc_18000C91A
0x18000c93c  mov     rax, r9
0x18000c93f  lea     rdx, [rcx-2]
0x18000c943  neg     rax
0x18000c946  sbb     eax, eax
0x18000c948  not     eax
0x18000c94a  and     eax, 8007007Ah
0x18000c94f  test    r9, r9
0x18000c952  cmovnz  rdx, rcx
0x18000c956  mov     [rdx], r10w
0x18000c95a  retn
```
