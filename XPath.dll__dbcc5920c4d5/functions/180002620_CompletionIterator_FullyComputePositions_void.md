# CompletionIterator::FullyComputePositions(void)

- ea: `0x180002620`
- end: `0x18000265d`
- name: `?FullyComputePositions@CompletionIterator@@AEAAJXZ`
- size: `61`
- prototype: `__int64 __fastcall(CompletionIterator *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d30`
- `0x1800030c0`
- `0x180003100`

## callees

- `0x180002620`
- `0x180002fcc`

## pseudocode

```c
__int64 __fastcall CompletionIterator::FullyComputePositions(CompletionIterator *this)
{
  CompletionIterator *v1; // rbx
  __int64 result; // rax
  char v3; // [rsp+30h] [rbp+8h] BYREF
  char v4; // [rsp+38h] [rbp+10h] BYREF

  v1 = this;
  if ( *((_BYTE *)this + 24) )
    return 0;
  v3 = 1;
  while ( 1 )
  {
    result = CompletionIterator::TryGetNextByBaseIterator((__int64)this, (__int64)&v4, &v3);
    if ( (int)result < 0 )
      break;
    if ( (_DWORD)result || !v3 )
      return 0;
    this = v1;
  }
  return result;
}

```

## disassembly

```asm
0x180002620  push    rbx
0x180002622  sub     rsp, 20h
0x180002626  cmp     byte ptr [rcx+18h], 0
0x18000262a  mov     rbx, rcx
0x18000262d  jnz     short loc_180002655
0x18000262f  mov     [rsp+28h+arg_0], 1
0x180002634  lea     r8, [rsp+28h+arg_0]
0x180002639  lea     rdx, [rsp+28h+arg_8]
0x18000263e  call    ?TryGetNextByBaseIterator@CompletionIterator@@AEAAJPEAVIterator@?$OrderedSet@VPositionData@@@@PEA_N@Z; CompletionIterator::TryGetNextByBaseIterator(OrderedSet<PositionData>::Iterator *,bool *)
0x180002643  test    eax, eax
0x180002645  js      short loc_180002657
0x180002647  jnz     short loc_180002655
0x180002649  cmp     [rsp+28h+arg_0], 0
0x18000264e  jz      short loc_180002655
0x180002650  mov     rcx, rbx
0x180002653  jmp     short loc_180002634
0x180002655  xor     eax, eax
0x180002657  add     rsp, 20h
0x18000265b  pop     rbx
0x18000265c  retn
```
