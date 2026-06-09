# BaseSrvFindSharedWowRecordByTaskId

- ea: `0x18000a50c`
- end: `0x18000a545`
- name: `BaseSrvFindSharedWowRecordByTaskId`
- size: `57`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000a960`
- `0x18000c2a4`
- `0x18000c454`

## callees

- `0x18000a50c`

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
0x18000a50c  mov     rcx, cs:gWowHead
0x18000a513  test    rcx, rcx
0x18000a516  jz      short loc_18000A53F
0x18000a518  mov     rax, [rcx+38h]
0x18000a51c  test    rax, rax
0x18000a51f  jz      short loc_18000A52B
0x18000a521  cmp     [rax], edx
0x18000a523  jz      short loc_18000A530
0x18000a525  mov     rax, [rax+20h]
0x18000a529  jmp     short loc_18000A51C
0x18000a52b  mov     rcx, [rcx]
0x18000a52e  jmp     short loc_18000A513
0x18000a530  mov     [r8], rcx
0x18000a533  test    r9, r9
0x18000a536  jz      short loc_18000A53B
0x18000a538  mov     [r9], rax
0x18000a53b  xor     eax, eax
0x18000a53d  retn
0x18000a53f  mov     eax, 0C0000225h
0x18000a544  retn
```
