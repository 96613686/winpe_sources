# StringEnumerationMatcher::~StringEnumerationMatcher(void)

- ea: `0x18000a98c`
- end: `0x18000aa12`
- name: `??1StringEnumerationMatcher@@QEAA@XZ`
- size: `134`
- prototype: `void __fastcall(StringEnumerationMatcher *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000a690`
- `0x180010da8`

## callees

- `0x18000a98c`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a9f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a9f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aa0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a9ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a9ad`

## pseudocode

```c
void __fastcall StringEnumerationMatcher::~StringEnumerationMatcher(StringEnumerationMatcher *this)
{
  _QWORD *v2; // rbx
  void *v3; // rcx
  __int64 v4; // rcx
  _QWORD *v5; // rdx
  void *v6; // rcx
  _QWORD *v7; // rbx

  v2 = *(_QWORD **)this;
  while ( 1 )
  {
    v2 = (_QWORD *)*v2;
    if ( v2 == *(_QWORD **)this )
      break;
    v3 = (void *)v2[2];
    if ( v3 )
      CoTaskMemFree(v3);
  }
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = **(_QWORD ***)this;
  **(_QWORD **)this = *(_QWORD *)this;
  *(_QWORD *)(*(_QWORD *)this + 8LL) = *(_QWORD *)this;
  *((_QWORD *)this + 1) = 0;
  v6 = *(void **)this;
  if ( v5 != *(_QWORD **)this )
  {
    do
    {
      v7 = (_QWORD *)*v5;
      operator delete(v5);
      v5 = v7;
      v6 = *(void **)this;
    }
    while ( v7 != *(_QWORD **)this );
  }
  operator delete(v6);
}

```

## disassembly

```asm
0x18000a98c  mov     [rsp+arg_0], rbx
0x18000a991  push    rdi
0x18000a992  sub     rsp, 20h
0x18000a996  mov     rdi, rcx
0x18000a999  mov     rbx, [rcx]
0x18000a99c  mov     rbx, [rbx]
0x18000a99f  cmp     rbx, [rdi]
0x18000a9a2  jz      short loc_18000A9B5
0x18000a9a4  mov     rcx, [rbx+10h]; pv
0x18000a9a8  test    rcx, rcx
0x18000a9ab  jz      short loc_18000A99C
0x18000a9ad  call    cs:__imp_CoTaskMemFree
0x18000a9b3  jmp     short loc_18000A99C
0x18000a9b5  mov     rcx, [rdi+48h]
0x18000a9b9  test    rcx, rcx
0x18000a9bc  jz      short loc_18000A9CA
0x18000a9be  mov     rax, [rcx]
0x18000a9c1  mov     rax, [rax+10h]
0x18000a9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9ca  mov     rax, [rdi]
0x18000a9cd  mov     rdx, [rax]
0x18000a9d0  mov     [rax], rax
0x18000a9d3  mov     rax, [rdi]
0x18000a9d6  mov     [rax+8], rax
0x18000a9da  mov     qword ptr [rdi+8], 0
0x18000a9e2  mov     rcx, [rdi]
0x18000a9e5  cmp     rdx, rcx
0x18000a9e8  jz      short loc_18000AA01
0x18000a9ea  mov     rbx, [rdx]
0x18000a9ed  mov     rcx, rdx
0x18000a9f0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a9f6  mov     rdx, rbx
0x18000a9f9  mov     rcx, [rdi]
0x18000a9fc  cmp     rbx, rcx
0x18000a9ff  jnz     short loc_18000A9EA
0x18000aa01  mov     rbx, [rsp+28h+arg_0]
0x18000aa06  add     rsp, 20h
0x18000aa0a  pop     rdi
0x18000aa0b  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
