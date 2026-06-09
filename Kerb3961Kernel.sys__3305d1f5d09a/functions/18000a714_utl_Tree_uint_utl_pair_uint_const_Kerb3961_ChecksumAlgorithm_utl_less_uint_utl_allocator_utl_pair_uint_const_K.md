# utl::_Tree<uint,utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<uint,utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>,0>(void)

- ea: `0x18000a714`
- end: `0x18000a792`
- name: `??1?$_Tree@IU?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@$0A@@utl@@IEAA@XZ`
- size: `126`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b510`
- `0x18000bab0`
- `0x18000c894`
- `0x180012b00`
- `0x180012b20`
- `0x180012b90`
- `0x180012c00`
- `0x180012c20`

## callees

- `0x18000a714`
- `0x180011b40`

## pseudocode

```c
void __fastcall utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>(
        _QWORD *a1)
{
  unsigned __int64 v1; // rbx
  _BYTE *v3; // rcx

  v1 = a1[2];
  if ( (_QWORD *)v1 != a1 )
  {
    while ( 1 )
    {
      while ( *(_UNKNOWN **)(v1 + 8) != &utl::_TreeSentinel )
        v1 = *(_QWORD *)(v1 + 8);
LABEL_7:
      if ( *(_UNKNOWN **)(v1 + 16) == &utl::_TreeSentinel )
        break;
      v1 = *(_QWORD *)(v1 + 16);
    }
    while ( 1 )
    {
      v3 = (_BYTE *)v1;
      v1 = *(_QWORD *)v1 & 0xFFFFFFFFFFFFFFFEuLL;
      Kerb3961Free(v3);
      if ( (_QWORD *)v1 == a1 )
        break;
      if ( *(_UNKNOWN **)(v1 + 8) != &utl::_TreeSentinel )
      {
        *(_QWORD *)(v1 + 8) = &utl::_TreeSentinel;
        goto LABEL_7;
      }
    }
    *a1 = a1;
    a1[1] = a1;
    a1[2] = a1;
    a1[3] = 0;
  }
}

```

## disassembly

```asm
0x18000a714  mov     [rsp+arg_0], rbx
0x18000a719  mov     [rsp+arg_8], rsi
0x18000a71e  push    rdi
0x18000a71f  sub     rsp, 20h
0x18000a723  mov     rbx, [rcx+10h]
0x18000a727  mov     rdi, rcx
0x18000a72a  cmp     rbx, rcx
0x18000a72d  jz      short loc_18000A781
0x18000a72f  lea     rsi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000a736  mov     rax, [rbx+8]
0x18000a73a  cmp     rax, rsi
0x18000a73d  jz      short loc_18000A762
0x18000a73f  mov     rbx, rax
0x18000a742  jmp     short loc_18000A736
0x18000a744  mov     rcx, rbx
0x18000a747  mov     rbx, [rbx]
0x18000a74a  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18000a74e  call    Kerb3961Free
0x18000a753  cmp     rbx, rdi
0x18000a756  jz      short loc_18000A76E
0x18000a758  cmp     [rbx+8], rsi
0x18000a75c  jz      short loc_18000A744
0x18000a75e  mov     [rbx+8], rsi
0x18000a762  cmp     [rbx+10h], rsi
0x18000a766  jz      short loc_18000A744
0x18000a768  mov     rbx, [rbx+10h]
0x18000a76c  jmp     short loc_18000A736
0x18000a76e  mov     [rdi], rdi
0x18000a771  mov     [rdi+8], rdi
0x18000a775  mov     [rdi+10h], rdi
0x18000a779  mov     qword ptr [rdi+18h], 0
0x18000a781  mov     rbx, [rsp+28h+arg_0]
0x18000a786  mov     rsi, [rsp+28h+arg_8]
0x18000a78b  add     rsp, 20h
0x18000a78f  pop     rdi
0x18000a790  retn
```
