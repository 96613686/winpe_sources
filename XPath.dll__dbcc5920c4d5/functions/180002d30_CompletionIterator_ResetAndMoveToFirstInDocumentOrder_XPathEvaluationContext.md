# CompletionIterator::ResetAndMoveToFirstInDocumentOrder(XPathEvaluationContext *)

- ea: `0x180002d30`
- end: `0x180002db8`
- name: `?ResetAndMoveToFirstInDocumentOrder@CompletionIterator@@UEAAJPEAVXPathEvaluationContext@@@Z`
- size: `136`
- prototype: `__int64 __fastcall(CompletionIterator *__hidden this, struct XPathEvaluationContext *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180002d30`
- `0x180002dc0`
- `0x180002e08`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CompletionIterator::ResetAndMoveToFirstInDocumentOrder(
        CompletionIterator *this,
        struct XPathEvaluationContext *a2)
{
  __int64 result; // rax
  int v4; // eax
  unsigned int v5; // ecx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  result = (*(__int64 (__fastcall **)(CompletionIterator *, struct XPathEvaluationContext *))(*(_QWORD *)this + 96LL))(
             this,
             a2);
  if ( (int)result >= 0 )
  {
    result = CompletionIterator::FullyComputePositions(this);
    if ( (int)result >= 0 )
    {
      if ( *((_DWORD *)this + 13) )
      {
        v6 = 0;
        result = OrderedSet<PositionData>::SortList((char *)this + 32);
        if ( (int)result >= 0 )
        {
          v6 = *((_QWORD *)this + 10);
          v4 = CompletionIterator::SetCurrentPosition(this, &v6);
          v5 = 0;
          if ( v4 < 0 )
            return (unsigned int)v4;
          return v5;
        }
      }
      else
      {
        return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002d30  mov     [rsp+arg_8], rbx
0x180002d35  push    rdi
0x180002d36  sub     rsp, 20h
0x180002d3a  mov     rax, [rcx]
0x180002d3d  mov     rdi, rcx
0x180002d40  mov     rax, [rax+60h]
0x180002d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d49  test    eax, eax
0x180002d4b  js      short loc_180002DAD
0x180002d4d  mov     rcx, rdi; this
0x180002d50  call    ?FullyComputePositions@CompletionIterator@@AEAAJXZ; CompletionIterator::FullyComputePositions(void)
0x180002d55  test    eax, eax
0x180002d57  js      short loc_180002DAD
0x180002d59  cmp     dword ptr [rdi+34h], 0
0x180002d5d  jnz     short loc_180002D66
0x180002d5f  mov     eax, 1
0x180002d64  jmp     short loc_180002DAD
0x180002d66  lea     rcx, [rdi+20h]
0x180002d6a  mov     [rsp+28h+arg_0], 0
0x180002d73  call    ?SortList@?$OrderedSet@VPositionData@@@@AEAAJXZ; OrderedSet<PositionData>::SortList(void)
0x180002d78  test    eax, eax
0x180002d7a  js      short loc_180002DAD
0x180002d7c  mov     rax, [rdi+50h]
0x180002d80  xor     ecx, ecx
0x180002d82  test    rax, rax
0x180002d85  jz      short loc_180002D92
0x180002d87  test    ecx, ecx
0x180002d89  jz      short loc_180002D92
0x180002d8b  mov     rax, [rax]
0x180002d8e  dec     ecx
0x180002d90  jmp     short loc_180002D82
0x180002d92  lea     rdx, [rsp+28h+arg_0]
0x180002d97  mov     [rsp+28h+arg_0], rax
0x180002d9c  mov     rcx, rdi
0x180002d9f  call    ?SetCurrentPosition@CompletionIterator@@AEAAJAEAVIterator@?$OrderedSet@VPositionData@@@@@Z; CompletionIterator::SetCurrentPosition(OrderedSet<PositionData>::Iterator &)
0x180002da4  xor     ecx, ecx
0x180002da6  test    eax, eax
0x180002da8  cmovs   ecx, eax
0x180002dab  mov     eax, ecx
0x180002dad  mov     rbx, [rsp+28h+arg_8]
0x180002db2  add     rsp, 20h
0x180002db6  pop     rdi
0x180002db7  retn
```
