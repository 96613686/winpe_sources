# BaseSrvRemoveDOSRecord

- ea: `0x18000be3c`
- end: `0x18000be76`
- name: `BaseSrvRemoveDOSRecord`
- size: `58`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b380`
- `0x18000c088`

## callees

- `0x18000be3c`

## pseudocode

```c
void __fastcall BaseSrvRemoveDOSRecord(__int64 a1, _QWORD *a2)
{
  _QWORD **v2; // r8
  _QWORD *i; // rax

  if ( a1 )
  {
    v2 = *(_QWORD ***)(a1 + 72);
    if ( v2 == a2 )
    {
      *(_QWORD *)(a1 + 72) = *a2;
    }
    else if ( v2 )
    {
      for ( i = *v2; i; i = (_QWORD *)*i )
      {
        if ( i == a2 )
        {
          *v2 = (_QWORD *)*a2;
          return;
        }
        v2 = (_QWORD **)i;
      }
    }
  }
}

```

## disassembly

```asm
0x18000be3c  test    rcx, rcx
0x18000be3f  jz      short locret_18000BE75
0x18000be41  mov     r8, [rcx+48h]
0x18000be45  cmp     r8, rdx
0x18000be48  jnz     short loc_18000BE53
0x18000be4a  mov     rax, [rdx]
0x18000be4d  mov     [rcx+48h], rax
0x18000be51  retn
0x18000be53  test    r8, r8
0x18000be56  jz      short locret_18000BE75
0x18000be58  mov     rax, [r8]
0x18000be5b  jmp     short loc_18000BE68
0x18000be5d  cmp     rax, rdx
0x18000be60  jz      short loc_18000BE6F
0x18000be62  mov     r8, rax
0x18000be65  mov     rax, [rax]
0x18000be68  test    rax, rax
0x18000be6b  jnz     short loc_18000BE5D
0x18000be6d  retn
0x18000be6f  mov     rax, [rdx]
0x18000be72  mov     [r8], rax
0x18000be75  retn
```
