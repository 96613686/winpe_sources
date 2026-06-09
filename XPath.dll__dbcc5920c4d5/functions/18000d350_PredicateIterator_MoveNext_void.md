# PredicateIterator::MoveNext(void)

- ea: `0x18000d350`
- end: `0x18000d3e3`
- name: `?MoveNext@PredicateIterator@@UEAAJXZ`
- size: `147`
- prototype: `__int64 __fastcall(PredicateIterator *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000c7cc`
- `0x18000c830`
- `0x18000d350`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall PredicateIterator::MoveNext(PredicateIterator *this)
{
  __int64 i; // rcx
  __int64 result; // rax
  __int64 v4; // rcx
  __int64 v5; // rdx
  int v6; // ebx
  _BYTE v7[24]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+40h] [rbp+8h] BYREF

  for ( i = *((_QWORD *)this + 3); ; i = *((_QWORD *)this + 3) )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 48LL))(i);
    if ( (_DWORD)result == 1 )
      break;
    if ( (int)result < 0 )
      return result;
    AutoContextStateSetter::AutoContextStateSetter(
      (AutoContextStateSetter *)v7,
      *((struct XPathEvaluationContext **)this + 5),
      *((struct XPathNodeIteratorBase **)this + 3));
    v4 = *((_QWORD *)this + 4);
    v5 = *((_QWORD *)this + 5);
    v8 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v4 + 80LL))(v4, v5, &v8);
    if ( v6 < 0 )
      goto LABEL_8;
    if ( v8 )
    {
      v6 = 0;
LABEL_8:
      AutoContextStateSetter::~AutoContextStateSetter((AutoContextStateSetter *)v7);
      return (unsigned int)v6;
    }
    AutoContextStateSetter::~AutoContextStateSetter((AutoContextStateSetter *)v7);
  }
  return 1;
}

```

## disassembly

```asm
0x18000d350  mov     [rsp+arg_8], rbx
0x18000d355  push    rdi
0x18000d356  sub     rsp, 30h
0x18000d35a  mov     rdi, rcx
0x18000d35d  mov     rcx, [rcx+18h]
0x18000d361  mov     rax, [rcx]
0x18000d364  mov     rax, [rax+30h]
0x18000d368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d36d  cmp     eax, 1
0x18000d370  jz      short loc_18000D3D3
0x18000d372  test    eax, eax
0x18000d374  js      short loc_18000D3D8
0x18000d376  mov     r8, [rdi+18h]; struct XPathNodeIteratorBase *
0x18000d37a  lea     rcx, [rsp+38h+var_18]; this
0x18000d37f  mov     rdx, [rdi+28h]; struct XPathEvaluationContext *
0x18000d383  call    ??0AutoContextStateSetter@@QEAA@PEAVXPathEvaluationContext@@PEAVXPathNodeIteratorBase@@@Z; AutoContextStateSetter::AutoContextStateSetter(XPathEvaluationContext *,XPathNodeIteratorBase *)
0x18000d388  mov     rcx, [rdi+20h]
0x18000d38c  lea     r8, [rsp+38h+arg_0]
0x18000d391  mov     rdx, [rdi+28h]
0x18000d395  mov     [rsp+38h+arg_0], 0
0x18000d39a  mov     rax, [rcx]
0x18000d39d  mov     rax, [rax+50h]
0x18000d3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a6  mov     ebx, eax
0x18000d3a8  test    eax, eax
0x18000d3aa  js      short loc_18000D3C5
0x18000d3ac  cmp     [rsp+38h+arg_0], 0
0x18000d3b1  jnz     short loc_18000D3C3
0x18000d3b3  lea     rcx, [rsp+38h+var_18]; this
0x18000d3b8  call    ??1AutoContextStateSetter@@QEAA@XZ; AutoContextStateSetter::~AutoContextStateSetter(void)
0x18000d3bd  mov     rcx, [rdi+18h]
0x18000d3c1  jmp     short loc_18000D361
0x18000d3c3  xor     ebx, ebx
0x18000d3c5  lea     rcx, [rsp+38h+var_18]; this
0x18000d3ca  call    ??1AutoContextStateSetter@@QEAA@XZ; AutoContextStateSetter::~AutoContextStateSetter(void)
0x18000d3cf  mov     eax, ebx
0x18000d3d1  jmp     short loc_18000D3D8
0x18000d3d3  mov     eax, 1
0x18000d3d8  mov     rbx, [rsp+38h+arg_8]
0x18000d3dd  add     rsp, 30h
0x18000d3e1  pop     rdi
0x18000d3e2  retn
```
