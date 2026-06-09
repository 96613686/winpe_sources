# BaseSrvFindSharedWowRecordByTaskId

- ea: `0x18000a790`
- end: `0x18000a7c9`
- name: `BaseSrvFindSharedWowRecordByTaskId`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000abe0`
- `0x18000c678`
- `0x18000c820`

## callees

- `0x18000a790`

## pseudocode

```c
__int64 __fastcall BaseSrvFindSharedWowRecordByTaskId(__int64 a1, int a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v4; // rcx
  __int64 i; // rax

  v4 = (_QWORD *)gWowHead;
LABEL_2:
  if ( !v4 )
    return 3221226021LL;
  for ( i = v4[7]; ; i = *(_QWORD *)(i + 32) )
  {
    if ( !i )
    {
      v4 = (_QWORD *)*v4;
      goto LABEL_2;
    }
    if ( *(_DWORD *)i == a2 )
      break;
  }
  *a3 = v4;
  if ( a4 )
    *a4 = i;
  return 0;
}

```

## disassembly

```asm
0x18000a790  mov     rcx, cs:gWowHead
0x18000a797  test    rcx, rcx
0x18000a79a  jz      short loc_18000A7C3
0x18000a79c  mov     rax, [rcx+38h]
0x18000a7a0  test    rax, rax
0x18000a7a3  jz      short loc_18000A7AF
0x18000a7a5  cmp     [rax], edx
0x18000a7a7  jz      short loc_18000A7B4
0x18000a7a9  mov     rax, [rax+20h]
0x18000a7ad  jmp     short loc_18000A7A0
0x18000a7af  mov     rcx, [rcx]
0x18000a7b2  jmp     short loc_18000A797
0x18000a7b4  mov     [r8], rcx
0x18000a7b7  test    r9, r9
0x18000a7ba  jz      short loc_18000A7BF
0x18000a7bc  mov     [r9], rax
0x18000a7bf  xor     eax, eax
0x18000a7c1  retn
0x18000a7c3  mov     eax, 0C0000225h
0x18000a7c8  retn
```
