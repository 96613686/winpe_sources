# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000ff88`
- end: `0x18000fff3`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `34`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f480`
- `0x18000f680`
- `0x18000f7a0`
- `0x180010000`
- `0x1800156d0`
- `0x1800158a0`
- `0x180020170`
- `0x1800202a0`
- `0x180020710`
- `0x180021360`
- `0x180021b30`
- `0x180021d30`
- `0x180022650`
- `0x180022880`
- `0x180022c20`
- `0x180022f80`
- `0x180023270`
- `0x180023590`
- `0x180024c10`
- `0x180024eb0`
- `0x180027fa0`
- `0x180028160`
- `0x180028510`
- `0x180028710`
- `0x18002c940`
- `0x18002d080`
- `0x180030880`
- `0x18003475c`
- `0x180038abc`
- `0x18003ac00`
- `0x18003b5e0`
- `0x18003c920`
- `0x18003cb60`
- `0x18003e790`

## callees

- `0x18000ff88`

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
0x18000ff88  xor     r10d, r10d
0x18000ff8b  mov     r9, rcx
0x18000ff8e  test    rdx, rdx
0x18000ff91  jz      short loc_18000FFE4
0x18000ff93  cmp     rdx, 7FFFFFFFh
0x18000ff9a  jbe     short loc_18000FFA3
0x18000ff9c  mov     eax, 80070057h
0x18000ffa1  jmp     short loc_18000FFEE
0x18000ffa3  mov     eax, 7FFFFFFEh
0x18000ffa8  test    rax, rax
0x18000ffab  jz      short loc_18000FFCB
0x18000ffad  movzx   ecx, word ptr [r8]
0x18000ffb1  test    cx, cx
0x18000ffb4  jz      short loc_18000FFCB
0x18000ffb6  mov     [r9], cx
0x18000ffba  add     r8, 2
0x18000ffbe  add     r9, 2
0x18000ffc2  dec     rax
0x18000ffc5  sub     rdx, 1
0x18000ffc9  jnz     short loc_18000FFA8
0x18000ffcb  test    rdx, rdx
0x18000ffce  lea     rcx, [r9-2]
0x18000ffd2  cmovnz  rcx, r9
0x18000ffd6  neg     rdx
0x18000ffd9  sbb     eax, eax
0x18000ffdb  not     eax
0x18000ffdd  and     eax, 8007007Ah
0x18000ffe2  jmp     short loc_18000FFEE
0x18000ffe4  mov     eax, 80070057h
0x18000ffe9  test    rdx, rdx
0x18000ffec  jz      short locret_18000FFF2
0x18000ffee  mov     [rcx], r10w
0x18000fff2  retn
```
