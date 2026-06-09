# Concurrency::create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358___

- ea: `0x18000f0a8`
- end: `0x18000f126`
- name: `Concurrency::create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358___`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000eab0`

## callees

- `0x18000e664`
- `0x18000fd1c`
- `0x180010138`
- `0x1800101d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall Concurrency::create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358___(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  void *v7; // [rsp+28h] [rbp-30h] BYREF
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+40h] [rbp-18h]
  void *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 0;
  v9 = 0;
  v7 = retaddr;
  *(_BYTE *)(a3 + 48) = 1;
  Concurrency::details::_TaskCreationCallstack::operator=((_QWORD *)(a3 + 56), &v7);
  std::vector<void *>::~vector<void *>((char **)&v8);
  Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358___(a1, a2, a3);
  Concurrency::task_options::~task_options((char **)a3);
  return a1;
}

```

## disassembly

```asm
0x18000f0a8  mov     r11, rsp
0x18000f0ab  mov     [r11+8], rbx
0x18000f0af  mov     [r11+10h], rsi
0x18000f0b3  mov     [r11+18h], r8
0x18000f0b7  push    rdi
0x18000f0b8  sub     rsp, 50h
0x18000f0bc  mov     rsi, r8
0x18000f0bf  mov     rbx, rdx
0x18000f0c2  mov     rdi, rcx
0x18000f0c5  mov     rax, [rsp+58h]
0x18000f0ca  xorps   xmm0, xmm0
0x18000f0cd  movdqu  [rsp+58h+var_28], xmm0
0x18000f0d3  mov     qword ptr [r11-18h], 0
0x18000f0db  mov     [r11-30h], rax
0x18000f0df  mov     byte ptr [r8+30h], 1
0x18000f0e4  lea     rcx, [r8+38h]
0x18000f0e8  lea     rdx, [r11-30h]
0x18000f0ec  call    ??4_TaskCreationCallstack@details@Concurrency@@QEAAAEAV012@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::operator=(Concurrency::details::_TaskCreationCallstack const &)
0x18000f0f1  nop
0x18000f0f2  lea     rcx, [rsp+58h+var_28]
0x18000f0f7  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x18000f0fc  mov     r8, rsi
0x18000f0ff  mov     rdx, rbx
0x18000f102  mov     rcx, rdi
0x18000f105  call    Concurrency__task_void___task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358___
0x18000f10a  nop
0x18000f10b  mov     rcx, rsi; this
0x18000f10e  call    ??1task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::~task_options(void)
0x18000f113  mov     rax, rdi
0x18000f116  mov     rbx, [rsp+58h+arg_0]
0x18000f11b  mov     rsi, [rsp+58h+arg_8]
0x18000f120  add     rsp, 50h
0x18000f124  pop     rdi
0x18000f125  retn
```
