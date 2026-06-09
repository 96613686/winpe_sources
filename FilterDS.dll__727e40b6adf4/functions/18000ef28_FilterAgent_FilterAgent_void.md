# FilterAgent::~FilterAgent(void)

- ea: `0x18000ef28`
- end: `0x18000ef6f`
- name: `??1FilterAgent@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(FilterAgent *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000db14`
- `0x18000dbe0`
- `0x18000dc0c`
- `0x18000f82c`
- `0x18000fe3c`
- `0x1800104e4`
- `0x180011204`

## callees

- `0x18000ef28`
- `0x180024010`

## pseudocode

```c
void __fastcall FilterAgent::~FilterAgent(FilterAgent *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  __int64 v3; // rcx

  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
  {
    *((_QWORD *)this + 1) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
}

```

## disassembly

```asm
0x18000ef28  push    rbx
0x18000ef2a  sub     rsp, 20h
0x18000ef2e  mov     rbx, rcx
0x18000ef31  mov     rcx, [rcx+10h]
0x18000ef35  test    rcx, rcx
0x18000ef38  jz      short loc_18000EF4B
0x18000ef3a  mov     rax, [rcx]
0x18000ef3d  mov     edx, 1
0x18000ef42  mov     rax, [rax]
0x18000ef45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef4a  nop
0x18000ef4b  mov     rcx, [rbx+8]
0x18000ef4f  test    rcx, rcx
0x18000ef52  jz      short loc_18000EF69
0x18000ef54  mov     qword ptr [rbx+8], 0
0x18000ef5c  mov     rax, [rcx]
0x18000ef5f  mov     rax, [rax+10h]
0x18000ef63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef68  nop
0x18000ef69  add     rsp, 20h
0x18000ef6d  pop     rbx
0x18000ef6e  retn
```
