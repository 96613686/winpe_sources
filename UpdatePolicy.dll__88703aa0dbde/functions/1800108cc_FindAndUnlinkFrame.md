# _FindAndUnlinkFrame

- ea: `0x1800108cc`
- end: `0x18001091f`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800134f0`
- `0x1800136f0`

## callees

- `0x18000ecf4`
- `0x1800108cc`
- `0x180011058`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort();
  while ( 1 )
  {
    v3 = *(_QWORD *)(v2 + 8);
    if ( a1 == v2 )
      break;
    v2 = *(_QWORD *)(v2 + 8);
    if ( !v3 )
      goto LABEL_7;
  }
  result = _vcrt_getptd();
  *(_QWORD *)(result + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x1800108cc  mov     [rsp+arg_0], rbx
0x1800108d1  push    rdi
0x1800108d2  sub     rsp, 20h
0x1800108d6  mov     rdi, rcx
0x1800108d9  call    __vcrt_getptd
0x1800108de  cmp     rdi, [rax+58h]
0x1800108e2  jnz     short loc_180010919
0x1800108e4  call    __vcrt_getptd
0x1800108e9  mov     rdx, [rax+58h]
0x1800108ed  test    rdx, rdx
0x1800108f0  jz      short loc_180010919
0x1800108f2  mov     rbx, [rdx+8]
0x1800108f6  cmp     rdi, rdx
0x1800108f9  jz      short loc_180010905
0x1800108fb  mov     rdx, rbx
0x1800108fe  test    rbx, rbx
0x180010901  jz      short loc_180010919
0x180010903  jmp     short loc_1800108F2
0x180010905  call    __vcrt_getptd
0x18001090a  mov     [rax+58h], rbx
0x18001090e  mov     rbx, [rsp+28h+arg_0]
0x180010913  add     rsp, 20h
0x180010917  pop     rdi
0x180010918  retn
0x180010919  call    abort
```
