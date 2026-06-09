# StepIteratorBase::MoveToNextTagNodesInDocumentOrderUntilAscendToDepth(XPathNavigatorInternal &,ulong)

- ea: `0x18000d5a4`
- end: `0x18000d60e`
- name: `?MoveToNextTagNodesInDocumentOrderUntilAscendToDepth@StepIteratorBase@@KAJAEAVXPathNavigatorInternal@@K@Z`
- size: `106`
- prototype: `__int64 __fastcall(struct XPathNavigatorInternal *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000d240`
- `0x18000d270`

## callees

- `0x18000d5a4`
- `0x18000e668`
- `0x18000e6a8`

## pseudocode

```c
__int64 __fastcall StepIteratorBase::MoveToNextTagNodesInDocumentOrderUntilAscendToDepth(
        struct XPathNavigatorInternal *this,
        unsigned int a2)
{
  __int64 result; // rax

  result = XPathNavigatorInternal::MoveNavigatorAndUpdateState(
             this,
             0,
             0,
             (__int64 (__fastcall *)(_QWORD)) IXPathNavigator::`vcall'{136,{flat}});
  if ( (_DWORD)result == 1 )
  {
    while ( *((_DWORD *)this + 2) > a2 )
    {
      result = XPathNavigatorInternal::MoveNavigatorAndUpdateState(
                 this,
                 0,
                 0,
                 (__int64 (__fastcall *)(_QWORD)) IXPathNavigator::`vcall'{152,{flat}});
      if ( (_DWORD)result == 1 )
      {
        result = XPathNavigatorInternal::MoveNavigatorAndUpdateState(
                   this,
                   (__int64 (__fastcall *)(_QWORD)) IXPathNavigator::`vcall'{160,{flat}});
        if ( (int)result >= 0 )
          continue;
      }
      return result;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000d5a4  mov     [rsp+arg_0], rbx
0x18000d5a9  push    rdi
0x18000d5aa  sub     rsp, 20h
0x18000d5ae  mov     edi, edx
0x18000d5b0  lea     r9, ??_9IXPathNavigator@@$BII@AA; [thunk]: IXPathNavigator::`vcall'{136,{flat}}
0x18000d5b7  xor     edx, edx
0x18000d5b9  xor     r8d, r8d
0x18000d5bc  mov     rbx, rcx
0x18000d5bf  call    ?MoveNavigatorAndUpdateState@XPathNavigatorInternal@@AEAAJPEBG0P8IXPathNavigator@@EAAJ00@Z@Z; XPathNavigatorInternal::MoveNavigatorAndUpdateState(ushort const *,ushort const *,long (IXPathNavigator::*)(ushort const *,ushort const *))
0x18000d5c4  cmp     eax, 1
0x18000d5c7  jnz     short loc_18000D603
0x18000d5c9  mov     eax, [rbx+8]
0x18000d5cc  cmp     eax, edi
0x18000d5ce  jbe     short loc_18000D5FE
0x18000d5d0  lea     r9, ??_9IXPathNavigator@@$BJI@AA; [thunk]: IXPathNavigator::`vcall'{152,{flat}}
0x18000d5d7  xor     r8d, r8d
0x18000d5da  xor     edx, edx
0x18000d5dc  mov     rcx, rbx; this
0x18000d5df  call    ?MoveNavigatorAndUpdateState@XPathNavigatorInternal@@AEAAJPEBG0P8IXPathNavigator@@EAAJ00@Z@Z; XPathNavigatorInternal::MoveNavigatorAndUpdateState(ushort const *,ushort const *,long (IXPathNavigator::*)(ushort const *,ushort const *))
0x18000d5e4  cmp     eax, 1
0x18000d5e7  jnz     short loc_18000D603
0x18000d5e9  lea     rdx, ??_9IXPathNavigator@@$BKA@AA; [thunk]: IXPathNavigator::`vcall'{160,{flat}}
0x18000d5f0  mov     rcx, rbx; this
0x18000d5f3  call    ?MoveNavigatorAndUpdateState@XPathNavigatorInternal@@AEAAJP8IXPathNavigator@@EAAJXZ@Z; XPathNavigatorInternal::MoveNavigatorAndUpdateState(long (IXPathNavigator::*)(void))
0x18000d5f8  test    eax, eax
0x18000d5fa  jns     short loc_18000D5C9
0x18000d5fc  jmp     short loc_18000D603
0x18000d5fe  mov     eax, 1
0x18000d603  mov     rbx, [rsp+28h+arg_0]
0x18000d608  add     rsp, 20h
0x18000d60c  pop     rdi
0x18000d60d  retn
```
