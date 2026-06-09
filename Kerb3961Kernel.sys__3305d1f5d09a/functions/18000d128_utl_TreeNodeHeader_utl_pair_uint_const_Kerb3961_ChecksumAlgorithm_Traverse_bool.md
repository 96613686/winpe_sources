# utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)

- ea: `0x18000d128`
- end: `0x18000d19b`
- name: `?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z`
- size: `115`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b510`
- `0x18000c230`
- `0x18000c894`
- `0x180010c78`
- `0x180010e6c`
- `0x180010f40`
- `0x180011330`
- `0x180011450`
- `0x180011640`

## callees

- `0x18000d128`

## pseudocode

```c
_QWORD *__fastcall utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(
        _QWORD *a1,
        unsigned __int8 a2)
{
  __int64 v2; // r9
  _QWORD *result; // rax
  unsigned __int8 v5; // dl
  _QWORD *v6; // rcx
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rcx

  v2 = a2;
  result = (_QWORD *)a1[a2 + 1];
  if ( result == (_QWORD *)&utl::_TreeSentinel )
  {
    v6 = (_QWORD *)(*a1 & 0xFFFFFFFFFFFFFFFEuLL);
    result = v6;
    if ( (_QWORD *)v6[a2 + 1] == a1 )
    {
      v7 = *v6;
      if ( (_QWORD *)*v6 != a1 )
      {
        result = (_QWORD *)(v7 & 0xFFFFFFFFFFFFFFFEuLL);
        if ( *(_QWORD **)((v7 & 0xFFFFFFFFFFFFFFFEuLL) + 8 * v2 + 8) == v6 && (_QWORD *)*result != v6 )
        {
          do
          {
            v8 = result;
            result = (_QWORD *)(*result & 0xFFFFFFFFFFFFFFFEuLL);
          }
          while ( (_QWORD *)result[v2 + 1] == v8 );
        }
      }
    }
  }
  else
  {
    v5 = a2 ^ 1;
    if ( a1 == result )
      __int2c();
    while ( (_UNKNOWN *)result[v5 + 1] != &utl::_TreeSentinel )
      result = (_QWORD *)result[v5 + 1];
  }
  return result;
}

```

## disassembly

```asm
0x18000d128  movzx   r9d, dl
0x18000d12c  lea     r10, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000d133  mov     r8, rcx
0x18000d136  mov     rax, [rcx+r9*8+8]
0x18000d13b  cmp     rax, r10
0x18000d13e  jz      short loc_18000D15D
0x18000d140  xor     dl, 1
0x18000d143  cmp     rcx, rax
0x18000d146  jnz     short loc_18000D14A
0x18000d148  int     2Ch; Windows NT - assertion failure
0x18000d14a  movzx   ecx, dl
0x18000d14d  jmp     short loc_18000D154
0x18000d14f  mov     rax, [rax+rcx*8+8]
0x18000d154  cmp     [rax+rcx*8+8], r10
0x18000d159  jnz     short loc_18000D14F
0x18000d15b  retn
0x18000d15d  mov     rcx, [rcx]
0x18000d160  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000d164  mov     rax, rcx
0x18000d167  cmp     [rcx+r9*8+8], r8
0x18000d16c  jnz     short locret_18000D19A
0x18000d16e  mov     rdx, [rcx]
0x18000d171  cmp     rdx, r8
0x18000d174  jz      short locret_18000D19A
0x18000d176  mov     rax, rdx
0x18000d179  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000d17d  cmp     [rax+r9*8+8], rcx
0x18000d182  jnz     short locret_18000D19A
0x18000d184  cmp     [rax], rcx
0x18000d187  jz      short locret_18000D19A
0x18000d189  mov     rcx, rax
0x18000d18c  mov     rax, [rax]
0x18000d18f  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000d193  cmp     [rax+r9*8+8], rcx
0x18000d198  jz      short loc_18000D189
0x18000d19a  retn
```
