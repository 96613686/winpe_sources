# BaseSrvFreeAndRemoveBatRecord

- ea: `0x180006cd0`
- end: `0x180006d22`
- name: `BaseSrvFreeAndRemoveBatRecord`
- size: `82`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005ed0`
- `0x180006c30`

## callees

- `0x180006cd0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006d15`

## pseudocode

```c
void __fastcall BaseSrvFreeAndRemoveBatRecord(_QWORD *a1)
{
  _QWORD *v1; // r8
  _QWORD *v2; // rdx
  __int64 v3; // rax

  v1 = (_QWORD *)BatRecordHead;
  v2 = 0;
  if ( BatRecordHead )
  {
    while ( 1 )
    {
      v3 = v1[2];
      if ( v1 == a1 )
        break;
      v2 = v1;
      v1 = (_QWORD *)v1[2];
      if ( !v3 )
        return;
    }
    if ( v2 )
      v2[2] = v3;
    else
      BatRecordHead = v1[2];
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x180006cd0  mov     r8, cs:BatRecordHead
0x180006cd7  xor     edx, edx
0x180006cd9  test    r8, r8
0x180006cdc  jz      short locret_180006D21
0x180006cde  mov     rax, [r8+10h]
0x180006ce2  cmp     r8, rcx
0x180006ce5  jz      short loc_180006CF4
0x180006ce7  mov     rdx, r8
0x180006cea  mov     r8, rax
0x180006ced  test    rax, rax
0x180006cf0  jnz     short loc_180006CDE
0x180006cf2  jmp     short locret_180006D21
0x180006cf4  test    rdx, rdx
0x180006cf7  jz      short loc_180006CFF
0x180006cf9  mov     [rdx+10h], rax
0x180006cfd  jmp     short loc_180006D06
0x180006cff  mov     cs:BatRecordHead, rax
0x180006d06  mov     rcx, gs:60h
0x180006d0f  xor     edx, edx
0x180006d11  mov     rcx, [rcx+30h]
0x180006d15  jmp     cs:__imp_RtlFreeHeap
0x180006d21  retn
```
