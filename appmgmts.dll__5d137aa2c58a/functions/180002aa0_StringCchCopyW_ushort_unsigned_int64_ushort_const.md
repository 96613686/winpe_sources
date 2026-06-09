# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180002aa0`
- end: `0x180002b0b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `30`
- callee_count: `1`
- tags: ``

## callers

- `0x180002788`
- `0x180002b14`
- `0x180002d40`
- `0x180003370`
- `0x1800061f8`
- `0x180007388`
- `0x18000ca60`
- `0x18000edc0`
- `0x18000fe58`
- `0x18000ffdc`
- `0x180011268`
- `0x18001231c`
- `0x180012a7c`
- `0x18001a140`
- `0x18001a6a8`
- `0x18001a960`
- `0x18001cb90`
- `0x18001e690`
- `0x1800222f0`
- `0x18002350c`
- `0x180023fac`
- `0x1800240b0`
- `0x1800245f0`
- `0x180026fd0`
- `0x180028190`
- `0x180028c90`
- `0x1800290cc`
- `0x18002962c`
- `0x1800297b4`
- `0x180029d60`

## callees

- `0x180002aa0`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180002aa0  xor     r10d, r10d
0x180002aa3  mov     r9, rcx
0x180002aa6  test    rdx, rdx
0x180002aa9  jz      short loc_180002AFC
0x180002aab  cmp     rdx, 7FFFFFFFh
0x180002ab2  jbe     short loc_180002ABB
0x180002ab4  mov     eax, 80070057h
0x180002ab9  jmp     short loc_180002B06
0x180002abb  mov     eax, 7FFFFFFEh
0x180002ac0  test    rax, rax
0x180002ac3  jz      short loc_180002AE3
0x180002ac5  movzx   ecx, word ptr [r8]
0x180002ac9  test    cx, cx
0x180002acc  jz      short loc_180002AE3
0x180002ace  mov     [r9], cx
0x180002ad2  add     r8, 2
0x180002ad6  add     r9, 2
0x180002ada  dec     rax
0x180002add  sub     rdx, 1
0x180002ae1  jnz     short loc_180002AC0
0x180002ae3  test    rdx, rdx
0x180002ae6  lea     rcx, [r9-2]
0x180002aea  cmovnz  rcx, r9
0x180002aee  neg     rdx
0x180002af1  sbb     eax, eax
0x180002af3  not     eax
0x180002af5  and     eax, 8007007Ah
0x180002afa  jmp     short loc_180002B06
0x180002afc  mov     eax, 80070057h
0x180002b01  test    rdx, rdx
0x180002b04  jz      short locret_180002B0A
0x180002b06  mov     [rcx], r10w
0x180002b0a  retn
```
