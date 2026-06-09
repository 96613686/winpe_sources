# CompletionIterator::SetCurrentPosition(OrderedSet<PositionData>::Iterator &)

- ea: `0x180002dc0`
- end: `0x180002dff`
- name: `?SetCurrentPosition@CompletionIterator@@AEAAJAEAVIterator@?$OrderedSet@VPositionData@@@@@Z`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002a00`
- `0x180002d30`

## callees

- `0x180002dc0`
- `0x18000e5ac`

## pseudocode

```c
__int64 __fastcall CompletionIterator::SetCurrentPosition(__int64 a1, __int64 *a2)
{
  __int64 result; // rax
  __int64 v5; // rax

  result = XPathNavigatorInternal::InitializeAsValidPosition(
             (XPathNavigatorInternal *)(a1 + 112),
             *(struct IUnknown **)(*a2 + 24));
  if ( (int)result >= 0 )
  {
    v5 = *a2;
    *(_QWORD *)(a1 + 104) = *a2;
    *(_BYTE *)(v5 + 16) = 1;
    ++*(_DWORD *)(a1 + 28);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002dc0  mov     [rsp+arg_0], rbx
0x180002dc5  push    rdi
0x180002dc6  sub     rsp, 20h
0x180002dca  mov     rdi, rdx
0x180002dcd  mov     rbx, rcx
0x180002dd0  mov     rdx, [rdx]
0x180002dd3  add     rcx, 70h ; 'p'; this
0x180002dd7  mov     rdx, [rdx+18h]; struct IXPathNavigator *
0x180002ddb  call    ?InitializeAsValidPosition@XPathNavigatorInternal@@QEAAJPEAUIXPathNavigator@@@Z; XPathNavigatorInternal::InitializeAsValidPosition(IXPathNavigator *)
0x180002de0  test    eax, eax
0x180002de2  js      short loc_180002DF4
0x180002de4  mov     rax, [rdi]
0x180002de7  mov     [rbx+68h], rax
0x180002deb  mov     byte ptr [rax+10h], 1
0x180002def  inc     dword ptr [rbx+1Ch]
0x180002df2  xor     eax, eax
0x180002df4  mov     rbx, [rsp+28h+arg_0]
0x180002df9  add     rsp, 20h
0x180002dfd  pop     rdi
0x180002dfe  retn
```
