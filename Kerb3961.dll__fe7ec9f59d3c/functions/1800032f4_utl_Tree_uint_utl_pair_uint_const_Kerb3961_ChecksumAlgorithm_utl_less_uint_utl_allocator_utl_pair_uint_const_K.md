# utl::_Tree<uint,utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<uint,utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>,0>(void)

- ea: `0x1800032f4`
- end: `0x180003378`
- name: `??1?$_Tree@IU?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@$0A@@utl@@IEAA@XZ`
- size: `132`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a2a0`
- `0x18000afb0`
- `0x18000b210`
- `0x18000b840`
- `0x18000d1ec`
- `0x18000dd60`
- `0x18001d4c0`
- `0x18001d4e0`
- `0x18001d500`
- `0x18001d570`
- `0x18001d5e0`

## callees

- `0x180001d64`
- `0x1800032f4`

## pseudocode

```c
void __fastcall utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>::~_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>,0>(
        _QWORD *a1)
{
  unsigned __int64 v1; // rbx
  void *v3; // rcx

  v1 = a1[2];
  if ( (_QWORD *)v1 != a1 )
  {
    while ( 1 )
    {
      while ( *(void ***)(v1 + 8) != &utl::_TreeSentinel )
        v1 = *(_QWORD *)(v1 + 8);
LABEL_7:
      if ( *(void ***)(v1 + 16) == &utl::_TreeSentinel )
        break;
      v1 = *(_QWORD *)(v1 + 16);
    }
    while ( 1 )
    {
      v3 = (void *)v1;
      v1 = *(_QWORD *)v1 & 0xFFFFFFFFFFFFFFFEuLL;
      operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
      if ( (_QWORD *)v1 == a1 )
        break;
      if ( *(void ***)(v1 + 8) != &utl::_TreeSentinel )
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
0x1800032f4  mov     [rsp+arg_0], rbx
0x1800032f9  mov     [rsp+arg_8], rsi
0x1800032fe  push    rdi
0x1800032ff  sub     rsp, 20h
0x180003303  mov     rbx, [rcx+10h]
0x180003307  mov     rdi, rcx
0x18000330a  cmp     rbx, rcx
0x18000330d  jz      short loc_180003368
0x18000330f  lea     rsi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180003316  mov     rax, [rbx+8]
0x18000331a  cmp     rax, rsi
0x18000331d  jz      short loc_180003349
0x18000331f  mov     rbx, rax
0x180003322  jmp     short loc_180003316
0x180003324  mov     rcx, rbx; void *
0x180003327  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000332e  mov     rbx, [rbx]
0x180003331  and     rbx, 0FFFFFFFFFFFFFFFEh
0x180003335  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000333a  cmp     rbx, rdi
0x18000333d  jz      short loc_180003355
0x18000333f  cmp     [rbx+8], rsi
0x180003343  jz      short loc_180003324
0x180003345  mov     [rbx+8], rsi
0x180003349  cmp     [rbx+10h], rsi
0x18000334d  jz      short loc_180003324
0x18000334f  mov     rbx, [rbx+10h]
0x180003353  jmp     short loc_180003316
0x180003355  mov     [rdi], rdi
0x180003358  mov     [rdi+8], rdi
0x18000335c  mov     [rdi+10h], rdi
0x180003360  mov     qword ptr [rdi+18h], 0
0x180003368  mov     rbx, [rsp+28h+arg_0]
0x18000336d  mov     rsi, [rsp+28h+arg_8]
0x180003372  add     rsp, 20h
0x180003376  pop     rdi
0x180003377  retn
```
