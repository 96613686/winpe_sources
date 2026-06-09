# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000a5dc`
- end: `0x18000a62b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a634`

## callees

- `0x18000a5dc`

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
0x18000a5dc  mov     eax, 7FFFFFFEh
0x18000a5e1  mov     r9d, 20h ; ' '
0x18000a5e7  xor     r10d, r10d
0x18000a5ea  test    rax, rax
0x18000a5ed  jz      short loc_18000A60C
0x18000a5ef  movzx   edx, word ptr [r8]
0x18000a5f3  test    dx, dx
0x18000a5f6  jz      short loc_18000A60C
0x18000a5f8  mov     [rcx], dx
0x18000a5fb  add     r8, 2
0x18000a5ff  add     rcx, 2
0x18000a603  dec     rax
0x18000a606  sub     r9, 1
0x18000a60a  jnz     short loc_18000A5EA
0x18000a60c  mov     rax, r9
0x18000a60f  lea     rdx, [rcx-2]
0x18000a613  neg     rax
0x18000a616  sbb     eax, eax
0x18000a618  not     eax
0x18000a61a  and     eax, 8007007Ah
0x18000a61f  test    r9, r9
0x18000a622  cmovnz  rdx, rcx
0x18000a626  mov     [rdx], r10w
0x18000a62a  retn
```
