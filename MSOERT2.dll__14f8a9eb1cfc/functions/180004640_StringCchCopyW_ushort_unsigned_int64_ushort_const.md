# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180004640`
- end: `0x1800046ab`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x180001cb0`
- `0x180003f80`
- `0x180005860`
- `0x180006ac0`
- `0x180006e30`
- `0x180007ba8`
- `0x180009b20`
- `0x18000ab80`
- `0x18000af00`
- `0x18000b5e0`
- `0x18000b770`
- `0x18000be70`
- `0x18000c570`
- `0x18000d3ec`
- `0x18000d640`
- `0x18000d860`
- `0x18000de50`
- `0x18000df50`
- `0x1800120c8`
- `0x18001240c`

## callees

- `0x180004640`

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
0x180004640  xor     r10d, r10d
0x180004643  mov     r9, rcx
0x180004646  test    rdx, rdx
0x180004649  jz      short loc_18000469C
0x18000464b  cmp     rdx, 7FFFFFFFh
0x180004652  jbe     short loc_18000465B
0x180004654  mov     eax, 80070057h
0x180004659  jmp     short loc_1800046A6
0x18000465b  mov     eax, 7FFFFFFEh
0x180004660  test    rax, rax
0x180004663  jz      short loc_180004683
0x180004665  movzx   ecx, word ptr [r8]
0x180004669  test    cx, cx
0x18000466c  jz      short loc_180004683
0x18000466e  mov     [r9], cx
0x180004672  add     r8, 2
0x180004676  add     r9, 2
0x18000467a  dec     rax
0x18000467d  sub     rdx, 1
0x180004681  jnz     short loc_180004660
0x180004683  test    rdx, rdx
0x180004686  lea     rcx, [r9-2]
0x18000468a  cmovnz  rcx, r9
0x18000468e  neg     rdx
0x180004691  sbb     eax, eax
0x180004693  not     eax
0x180004695  and     eax, 8007007Ah
0x18000469a  jmp     short loc_1800046A6
0x18000469c  mov     eax, 80070057h
0x1800046a1  test    rdx, rdx
0x1800046a4  jz      short locret_1800046AA
0x1800046a6  mov     [rcx], r10w
0x1800046aa  retn
```
