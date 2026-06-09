# std::collate<ushort>::do_compare(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180016090`
- end: `0x1800160e0`
- name: `?do_compare@?$collate@G@std@@MEBAHPEBG000@Z`
- size: `80`
- prototype: `__int64 __fastcall(__int64, _WORD *, _WORD *, _WORD *, _WORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016090`

## pseudocode

```c
__int64 __fastcall std::collate<unsigned short>::do_compare(__int64 a1, _WORD *a2, _WORD *a3, _WORD *a4, _WORD *a5)
{
  int v5; // ecx
  __int64 result; // rax

  while ( a2 != a3 && a4 != a5 )
  {
    if ( *a2 < *a4 )
    {
      v5 = -1;
      goto LABEL_9;
    }
    if ( *a2 > *a4 )
    {
      v5 = 1;
      goto LABEL_9;
    }
    ++a2;
    ++a4;
  }
  v5 = a2 != a3;
  if ( a4 != a5 )
    v5 = -1;
LABEL_9:
  result = v5 != 0;
  if ( v5 < 0 )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x180016090  or      r10d, 0FFFFFFFFh
0x180016094  jmp     short loc_1800160B0
0x180016096  cmp     r9, [rsp+arg_20]
0x18001609b  jz      short loc_1800160B5
0x18001609d  movzx   eax, word ptr [rdx]
0x1800160a0  cmp     ax, [r9]
0x1800160a4  jb      short loc_1800160DB
0x1800160a6  ja      short loc_1800160D4
0x1800160a8  add     rdx, 2
0x1800160ac  add     r9, 2
0x1800160b0  cmp     rdx, r8
0x1800160b3  jnz     short loc_180016096
0x1800160b5  xor     ecx, ecx
0x1800160b7  cmp     rdx, r8
0x1800160ba  setnz   cl
0x1800160bd  cmp     r9, [rsp+arg_20]
0x1800160c2  cmovnz  ecx, r10d
0x1800160c6  xor     eax, eax
0x1800160c8  test    ecx, ecx
0x1800160ca  setnz   al
0x1800160cd  test    ecx, ecx
0x1800160cf  cmovs   eax, r10d
0x1800160d3  retn
0x1800160d4  mov     ecx, 1
0x1800160d9  jmp     short loc_1800160C6
0x1800160db  mov     ecx, r10d
0x1800160de  jmp     short loc_1800160C6
```
