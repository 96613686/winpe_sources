# PortListRemoveNextRequest

- ea: `0x14000ae10`
- end: `0x14000ae74`
- name: `PortListRemoveNextRequest`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006a70`
- `0x14000ac24`

## callees

- `0x14000ae10`

## pseudocode

```c
_QWORD *__fastcall PortListRemoveNextRequest(__int64 a1)
{
  _QWORD *v1; // r8
  __int64 v2; // rdx
  _QWORD *v3; // rax
  __int64 v4; // rax

  if ( *(_QWORD *)a1 == a1 )
    return 0;
  v1 = *(_QWORD **)(a1 + 16);
  *(_QWORD *)(a1 + 16) = *v1;
  *(_QWORD *)(a1 + 40) = v1[2] + 1LL;
  v2 = *v1;
  if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v3 = (_QWORD *)v1[1], (_QWORD *)*v3 != v1) )
    __fastfail(3u);
  *v3 = v2;
  *(_QWORD *)(v2 + 8) = v3;
  v4 = *(_QWORD *)(a1 + 32);
  --*(_DWORD *)(a1 + 24);
  if ( v4 )
    --*(_DWORD *)(v4 + 4);
  if ( *(_QWORD *)(a1 + 16) == a1 )
    *(_QWORD *)(a1 + 16) = *(_QWORD *)a1;
  return v1;
}

```

## disassembly

```asm
0x14000ae10  cmp     [rcx], rcx
0x14000ae13  jz      short loc_14000AE65
0x14000ae15  mov     r8, [rcx+10h]
0x14000ae19  mov     rax, [r8]
0x14000ae1c  mov     [rcx+10h], rax
0x14000ae20  mov     rax, [r8+10h]
0x14000ae24  inc     rax
0x14000ae27  mov     [rcx+28h], rax
0x14000ae2b  mov     rdx, [r8]
0x14000ae2e  cmp     [rdx+8], r8
0x14000ae32  jnz     short loc_14000AE6D
0x14000ae34  mov     rax, [r8+8]
0x14000ae38  cmp     [rax], r8
0x14000ae3b  jnz     short loc_14000AE6D
0x14000ae3d  mov     [rax], rdx
0x14000ae40  mov     [rdx+8], rax
0x14000ae44  mov     rax, [rcx+20h]
0x14000ae48  dec     dword ptr [rcx+18h]
0x14000ae4b  test    rax, rax
0x14000ae4e  jz      short loc_14000AE53
0x14000ae50  dec     dword ptr [rax+4]
0x14000ae53  cmp     [rcx+10h], rcx
0x14000ae57  jnz     short loc_14000AE60
0x14000ae59  mov     rdx, [rcx]
0x14000ae5c  mov     [rcx+10h], rdx
0x14000ae60  mov     rax, r8
0x14000ae63  retn
0x14000ae65  xor     r8d, r8d
0x14000ae68  mov     eax, r8d
0x14000ae6b  retn
0x14000ae6d  mov     ecx, 3
0x14000ae72  int     29h; Win8: RtlFailFast(ecx)
```
