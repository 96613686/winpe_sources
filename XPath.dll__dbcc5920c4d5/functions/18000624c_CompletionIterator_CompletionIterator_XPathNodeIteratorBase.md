# CompletionIterator::CompletionIterator(XPathNodeIteratorBase *)

- ea: `0x18000624c`
- end: `0x1800062f4`
- name: `??0CompletionIterator@@AEAA@PEAVXPathNodeIteratorBase@@@Z`
- size: `168`
- prototype: `CompletionIterator *__fastcall(CompletionIterator *__hidden this, struct XPathNodeIteratorBase *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800081e4`

## callees

- `0x1800032f4`
- `0x18000624c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000629b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000629b`

## pseudocode

```c
CompletionIterator *__fastcall CompletionIterator::CompletionIterator(
        CompletionIterator *this,
        struct XPathNodeIteratorBase *a2)
{
  CompletionIterator *result; // rax

  XPathNodeIteratorBase::XPathNodeIteratorBase(this);
  *(_QWORD *)this = &CompletionIterator::`vftable'{for `IXPathNodeIterator'};
  *((_BYTE *)this + 24) = 0;
  *((_QWORD *)this + 1) = &CompletionIterator::`vftable'{for `XPathExpressionBase'};
  *((_DWORD *)this + 7) = 0;
  *((_QWORD *)this + 4) = &HASH_TABLE<PositionData,PositionData *>::`vftable';
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  InitializeSRWLock((PSRWLOCK)this + 7);
  *((_BYTE *)this + 64) = 0;
  *((_QWORD *)this + 4) = &OrderedSet<PositionData>::`vftable';
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2 + 4);
  *((_QWORD *)this + 13) = 0;
  result = this;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_BYTE *)this + 128) = 0;
  *((_DWORD *)this + 31) = 7;
  return result;
}

```

## disassembly

```asm
0x18000624c  mov     [rsp+arg_0], rbx
0x180006251  mov     [rsp+arg_8], rsi
0x180006256  push    rdi
0x180006257  sub     rsp, 20h
0x18000625b  mov     rdi, rdx
0x18000625e  mov     rbx, rcx
0x180006261  call    ??0XPathNodeIteratorBase@@QEAA@XZ; XPathNodeIteratorBase::XPathNodeIteratorBase(void)
0x180006266  xor     esi, esi
0x180006268  lea     rax, ??_7CompletionIterator@@6BIXPathNodeIterator@@@; const CompletionIterator::`vftable'{for `IXPathNodeIterator'}
0x18000626f  mov     [rbx], rax
0x180006272  lea     rcx, [rbx+38h]; SRWLock
0x180006276  mov     [rbx+18h], sil
0x18000627a  lea     rax, ??_7CompletionIterator@@6BXPathExpressionBase@@@; const CompletionIterator::`vftable'{for `XPathExpressionBase'}
0x180006281  mov     [rbx+8], rax
0x180006285  lea     rax, ??_7?$HASH_TABLE@VPositionData@@PEAV1@@@6B@; const HASH_TABLE<PositionData,PositionData *>::`vftable'
0x18000628c  mov     [rbx+1Ch], esi
0x18000628f  mov     [rbx+20h], rax
0x180006293  mov     [rbx+28h], rsi
0x180006297  mov     [rbx+30h], rsi
0x18000629b  call    cs:__imp_InitializeSRWLock
0x1800062a1  mov     [rbx+40h], sil
0x1800062a5  lea     rax, ??_7?$OrderedSet@VPositionData@@@@6B@; const OrderedSet<PositionData>::`vftable'
0x1800062ac  mov     [rbx+20h], rax
0x1800062b0  mov     [rbx+48h], esi
0x1800062b3  mov     [rbx+50h], rsi
0x1800062b7  mov     [rbx+58h], rsi
0x1800062bb  mov     [rbx+60h], rdi
0x1800062bf  test    rdi, rdi
0x1800062c2  jz      short loc_1800062C8
0x1800062c4  lock inc dword ptr [rdi+10h]
0x1800062c8  mov     [rbx+68h], rsi
0x1800062cc  mov     rax, rbx
0x1800062cf  mov     [rbx+70h], rsi
0x1800062d3  mov     [rbx+78h], esi
0x1800062d6  mov     [rbx+80h], sil
0x1800062dd  mov     rsi, [rsp+28h+arg_8]
0x1800062e2  mov     dword ptr [rbx+7Ch], 7
0x1800062e9  mov     rbx, [rsp+28h+arg_0]
0x1800062ee  add     rsp, 20h
0x1800062f2  pop     rdi
0x1800062f3  retn
```
