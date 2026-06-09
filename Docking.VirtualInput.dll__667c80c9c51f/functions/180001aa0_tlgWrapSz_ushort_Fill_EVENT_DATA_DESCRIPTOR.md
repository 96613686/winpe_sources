# _tlgWrapSz<ushort>::Fill(_EVENT_DATA_DESCRIPTOR *)

- ea: `0x180001aa0`
- end: `0x180001adc`
- name: `?Fill@?$_tlgWrapSz@G@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `60`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e8c`
- `0x18000244c`
- `0x180002560`

## callees

- `0x180001aa0`

## pseudocode

```c
__int64 __fastcall _tlgWrapSz<unsigned short>::Fill(__int64 **a1, __int64 a2)
{
  __int64 *v2; // rax
  __int64 v3; // rcx
  int v4; // ecx
  __int64 result; // rax

  v2 = *a1;
  if ( *a1 )
  {
    v3 = -1;
    do
      ++v3;
    while ( *((_WORD *)v2 + v3) );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v2 = &qword_18001F2D0;
    v4 = 2;
  }
  *(_QWORD *)a2 = v2;
  result = a2;
  *(_DWORD *)(a2 + 8) = v4;
  *(_DWORD *)(a2 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x180001aa0  mov     rax, [rcx]
0x180001aa3  xor     r8d, r8d
0x180001aa6  test    rax, rax
0x180001aa9  jz      short loc_180001AC2
0x180001aab  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001aaf  inc     rcx
0x180001ab2  cmp     [rax+rcx*2], r8w
0x180001ab7  jnz     short loc_180001AAF
0x180001ab9  lea     ecx, ds:2[rcx*2]
0x180001ac0  jmp     short loc_180001ACE
0x180001ac2  lea     rax, qword_18001F2D0
0x180001ac9  mov     ecx, 2
0x180001ace  mov     [rdx], rax
0x180001ad1  mov     rax, rdx
0x180001ad4  mov     [rdx+8], ecx
0x180001ad7  mov     [rdx+0Ch], r8d
0x180001adb  retn
```
