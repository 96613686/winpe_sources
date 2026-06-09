# BaseSrvFreeAndRemoveBatRecord

- ea: `0x180006a40`
- end: `0x180006a93`
- name: `BaseSrvFreeAndRemoveBatRecord`
- size: `83`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005c70`
- `0x1800069a0`

## callees

- `0x180006a40`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006a86`

## pseudocode

```c
void __fastcall BaseSrvFreeAndRemoveBatRecord(_QWORD *a1)
{
  _QWORD *v1; // r8
  _QWORD *v2; // rdx

  v1 = (_QWORD *)BatRecordHead;
  v2 = 0;
  if ( BatRecordHead )
  {
    while ( v1 != a1 )
    {
      v2 = v1;
      v1 = (_QWORD *)v1[2];
      if ( !v1 )
        return;
    }
    if ( v2 )
      v2[2] = v1[2];
    else
      BatRecordHead = v1[2];
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x180006a40  mov     r8, cs:BatRecordHead
0x180006a47  xor     edx, edx
0x180006a49  test    r8, r8
0x180006a4c  jz      short locret_180006A92
0x180006a4e  cmp     r8, rcx
0x180006a51  jz      short loc_180006A61
0x180006a53  mov     rdx, r8
0x180006a56  mov     r8, [r8+10h]
0x180006a5a  test    r8, r8
0x180006a5d  jnz     short loc_180006A4E
0x180006a5f  jmp     short locret_180006A92
0x180006a61  mov     rax, [r8+10h]
0x180006a65  test    rdx, rdx
0x180006a68  jz      short loc_180006A70
0x180006a6a  mov     [rdx+10h], rax
0x180006a6e  jmp     short loc_180006A77
0x180006a70  mov     cs:BatRecordHead, rax
0x180006a77  mov     rcx, gs:60h
0x180006a80  xor     edx, edx
0x180006a82  mov     rcx, [rcx+30h]
0x180006a86  jmp     cs:__imp_RtlFreeHeap
0x180006a92  retn
```
