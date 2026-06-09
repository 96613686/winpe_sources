# StepCompositionIterator::MoveNext(void)

- ea: `0x18000d410`
- end: `0x18000d4ac`
- name: `?MoveNext@StepCompositionIterator@@UEAAJXZ`
- size: `156`
- prototype: `__int64 __fastcall(StepCompositionIterator *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000c7cc`
- `0x18000c830`
- `0x18000d410`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall StepCompositionIterator::MoveNext(StepCompositionIterator *this)
{
  __int64 result; // rax
  int v3; // edi
  _BYTE v4[24]; // [rsp+20h] [rbp-18h] BYREF

  while ( 1 )
  {
    if ( *((_BYTE *)this + 25) )
    {
      result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 48LL))(*((_QWORD *)this + 4));
      if ( (int)result < 0 )
        return result;
      if ( (_DWORD)result )
        return 1;
      AutoContextStateSetter::AutoContextStateSetter(
        (AutoContextStateSetter *)v4,
        *((struct XPathEvaluationContext **)this + 6),
        *((struct XPathNodeIteratorBase **)this + 4));
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 96LL))(
             *((_QWORD *)this + 5),
             *((_QWORD *)this + 6));
      if ( v3 < 0 )
      {
        AutoContextStateSetter::~AutoContextStateSetter((AutoContextStateSetter *)v4);
        return (unsigned int)v3;
      }
      *((_BYTE *)this + 25) = 0;
      AutoContextStateSetter::~AutoContextStateSetter((AutoContextStateSetter *)v4);
    }
    result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 48LL))(*((_QWORD *)this + 5));
    if ( (int)result < 0 )
      return result;
    if ( !(_DWORD)result )
      break;
    *((_BYTE *)this + 25) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d410  mov     [rsp+arg_0], rbx
0x18000d415  push    rdi
0x18000d416  sub     rsp, 30h
0x18000d41a  mov     rbx, rcx
0x18000d41d  cmp     byte ptr [rbx+19h], 0
0x18000d421  jz      short loc_18000D473
0x18000d423  mov     rcx, [rbx+20h]
0x18000d427  mov     rax, [rcx]
0x18000d42a  mov     rax, [rax+30h]
0x18000d42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d433  test    eax, eax
0x18000d435  js      short loc_18000D4A1
0x18000d437  jnz     short loc_18000D498
0x18000d439  mov     r8, [rbx+20h]; struct XPathNodeIteratorBase *
0x18000d43d  lea     rcx, [rsp+38h+var_18]; this
0x18000d442  mov     rdx, [rbx+30h]; struct XPathEvaluationContext *
0x18000d446  call    ??0AutoContextStateSetter@@QEAA@PEAVXPathEvaluationContext@@PEAVXPathNodeIteratorBase@@@Z; AutoContextStateSetter::AutoContextStateSetter(XPathEvaluationContext *,XPathNodeIteratorBase *)
0x18000d44b  mov     rcx, [rbx+28h]
0x18000d44f  mov     rdx, [rbx+30h]
0x18000d453  mov     rax, [rcx]
0x18000d456  mov     rax, [rax+60h]
0x18000d45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d45f  lea     rcx, [rsp+38h+var_18]; this
0x18000d464  mov     edi, eax
0x18000d466  test    eax, eax
0x18000d468  js      short loc_18000D48F
0x18000d46a  mov     byte ptr [rbx+19h], 0
0x18000d46e  call    ??1AutoContextStateSetter@@QEAA@XZ; AutoContextStateSetter::~AutoContextStateSetter(void)
0x18000d473  mov     rcx, [rbx+28h]
0x18000d477  mov     rax, [rcx]
0x18000d47a  mov     rax, [rax+30h]
0x18000d47e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d483  test    eax, eax
0x18000d485  js      short loc_18000D4A1
0x18000d487  jz      short loc_18000D49F
0x18000d489  mov     byte ptr [rbx+19h], 1
0x18000d48d  jmp     short loc_18000D41D
0x18000d48f  call    ??1AutoContextStateSetter@@QEAA@XZ; AutoContextStateSetter::~AutoContextStateSetter(void)
0x18000d494  mov     eax, edi
0x18000d496  jmp     short loc_18000D4A1
0x18000d498  mov     eax, 1
0x18000d49d  jmp     short loc_18000D4A1
0x18000d49f  xor     eax, eax
0x18000d4a1  mov     rbx, [rsp+38h+arg_0]
0x18000d4a6  add     rsp, 30h
0x18000d4aa  pop     rdi
0x18000d4ab  retn
```
