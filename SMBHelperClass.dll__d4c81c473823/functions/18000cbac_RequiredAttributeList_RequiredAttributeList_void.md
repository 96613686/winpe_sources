# RequiredAttributeList::~RequiredAttributeList(void)

- ea: `0x18000cbac`
- end: `0x18000cc1d`
- name: `??1RequiredAttributeList@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(RequiredAttributeList *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800037e8`
- `0x1800100da`

## callees

- `0x18000cbac`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cbfb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cbfb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbd0`

## pseudocode

```c
void __fastcall RequiredAttributeList::~RequiredAttributeList(RequiredAttributeList *this)
{
  _QWORD *v1; // rbx
  _QWORD **v3; // rax
  void *v4; // rcx
  _QWORD *v5; // rdx
  _QWORD *v6; // rcx
  _QWORD *v7; // rbx

  v1 = *(_QWORD **)this;
  while ( 1 )
  {
    v1 = (_QWORD *)*v1;
    v3 = *(_QWORD ***)this;
    if ( v1 == *(_QWORD **)this )
      break;
    v4 = (void *)v1[2];
    if ( v4 )
      CoTaskMemFree(v4);
  }
  v5 = *v3;
  *v3 = v3;
  *(_QWORD *)(*(_QWORD *)this + 8LL) = *(_QWORD *)this;
  v6 = *(_QWORD **)this;
  *((_QWORD *)this + 1) = 0;
  if ( v5 != v6 )
  {
    do
    {
      v7 = (_QWORD *)*v5;
      operator delete(v5);
      v6 = *(_QWORD **)this;
      v5 = v7;
    }
    while ( v7 != *(_QWORD **)this );
  }
  operator delete(v6);
}

```

## disassembly

```asm
0x18000cbac  mov     [rsp+arg_0], rbx
0x18000cbb1  push    rdi
0x18000cbb2  sub     rsp, 20h
0x18000cbb6  mov     rbx, [rcx]
0x18000cbb9  mov     rdi, rcx
0x18000cbbc  mov     rbx, [rbx]
0x18000cbbf  mov     rax, [rdi]
0x18000cbc2  cmp     rbx, rax
0x18000cbc5  jz      short loc_18000CBD8
0x18000cbc7  mov     rcx, [rbx+10h]; pv
0x18000cbcb  test    rcx, rcx
0x18000cbce  jz      short loc_18000CBBC
0x18000cbd0  call    cs:__imp_CoTaskMemFree
0x18000cbd6  jmp     short loc_18000CBBC
0x18000cbd8  mov     rdx, [rax]
0x18000cbdb  mov     [rax], rax
0x18000cbde  mov     rax, [rdi]
0x18000cbe1  mov     [rax+8], rax
0x18000cbe5  mov     rcx, [rdi]
0x18000cbe8  mov     qword ptr [rdi+8], 0
0x18000cbf0  cmp     rdx, rcx
0x18000cbf3  jz      short loc_18000CC0C
0x18000cbf5  mov     rbx, [rdx]
0x18000cbf8  mov     rcx, rdx
0x18000cbfb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cc01  mov     rcx, [rdi]
0x18000cc04  mov     rdx, rbx
0x18000cc07  cmp     rbx, rcx
0x18000cc0a  jnz     short loc_18000CBF5
0x18000cc0c  mov     rbx, [rsp+28h+arg_0]
0x18000cc11  add     rsp, 20h
0x18000cc15  pop     rdi
0x18000cc16  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
