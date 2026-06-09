# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140005110`
- end: `0x14000515c`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `76`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b1a4`

## callees

- `0x140005110`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v4; // rax
  __int64 v5; // r9
  unsigned __int16 *v6; // rdx
  __int64 result; // rax

  v4 = 2147483646;
  v5 = 260;
  do
  {
    if ( !v4 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = a1 - 1;
  result = 2147942522LL;
  if ( v5 )
  {
    v6 = a1;
    result = 0;
  }
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x140005110  mov     r10, rcx
0x140005113  mov     eax, 7FFFFFFEh
0x140005118  mov     r9d, 104h
0x14000511e  xchg    ax, ax
0x140005120  test    rax, rax
0x140005123  jz      short loc_140005143
0x140005125  movzx   edx, word ptr [r8]
0x140005129  test    dx, dx
0x14000512c  jz      short loc_140005143
0x14000512e  mov     [r10], dx
0x140005132  add     r8, 2
0x140005136  add     r10, 2
0x14000513a  dec     rax
0x14000513d  sub     r9, 1
0x140005141  jnz     short loc_140005120
0x140005143  xor     ecx, ecx
0x140005145  lea     rdx, [r10-2]
0x140005149  test    r9, r9
0x14000514c  mov     eax, 8007007Ah
0x140005151  cmovnz  rdx, r10
0x140005155  cmovnz  eax, ecx
0x140005158  mov     [rdx], cx
0x14000515b  retn
```
