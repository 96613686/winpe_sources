# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140005b48`
- end: `0x140005bb3`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140008974`
- `0x140008e34`

## callees

- `0x140005b48`

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
0x140005b48  xor     r10d, r10d
0x140005b4b  mov     r9, rcx
0x140005b4e  test    rdx, rdx
0x140005b51  jz      short loc_140005BA4
0x140005b53  cmp     rdx, 7FFFFFFFh
0x140005b5a  jbe     short loc_140005B63
0x140005b5c  mov     eax, 80070057h
0x140005b61  jmp     short loc_140005BAE
0x140005b63  mov     eax, 7FFFFFFEh
0x140005b68  test    rax, rax
0x140005b6b  jz      short loc_140005B8B
0x140005b6d  movzx   ecx, word ptr [r8]
0x140005b71  test    cx, cx
0x140005b74  jz      short loc_140005B8B
0x140005b76  mov     [r9], cx
0x140005b7a  add     r8, 2
0x140005b7e  add     r9, 2
0x140005b82  dec     rax
0x140005b85  sub     rdx, 1
0x140005b89  jnz     short loc_140005B68
0x140005b8b  test    rdx, rdx
0x140005b8e  lea     rcx, [r9-2]
0x140005b92  cmovnz  rcx, r9
0x140005b96  neg     rdx
0x140005b99  sbb     eax, eax
0x140005b9b  not     eax
0x140005b9d  and     eax, 8007007Ah
0x140005ba2  jmp     short loc_140005BAE
0x140005ba4  mov     eax, 80070057h
0x140005ba9  test    rdx, rdx
0x140005bac  jz      short locret_140005BB2
0x140005bae  mov     [rcx], r10w
0x140005bb2  retn
```
