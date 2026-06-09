# Concurrency::task_options::~task_options(void)

- ea: `0x140015e84`
- end: `0x140015f15`
- name: `??1task_options@Concurrency@@QEAA@XZ`
- size: `145`
- prototype: `void __fastcall(Concurrency::task_options *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140013a2c`
- `0x140015f1c`
- `0x14001c760`
- `0x14001c9d0`
- `0x140032dbb`
- `0x140032fbf`
- `0x140033a53`
- `0x140033aa9`

## callees

- `0x140015e84`
- `0x140035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::task_options::~task_options(Concurrency::task_options *this)
{
  unsigned __int64 v2; // rcx
  volatile signed __int32 *v3; // rcx
  volatile signed __int32 *v4; // rbx

  v2 = *((_QWORD *)this + 4);
  if ( v2 >= 2 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v3 && _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  *((_QWORD *)this + 3) = 0;
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
}

```

## disassembly

```asm
0x140015e84  push    rbx
0x140015e86  sub     rsp, 20h
0x140015e8a  mov     rbx, rcx
0x140015e8d  mov     rcx, [rcx+20h]
0x140015e91  cmp     rcx, 2
0x140015e95  jb      short loc_140015EA4
0x140015e97  mov     rax, [rcx]
0x140015e9a  mov     rax, [rax+10h]
0x140015e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ea3  nop
0x140015ea4  mov     rcx, [rbx+18h]
0x140015ea8  test    rcx, rcx
0x140015eab  jz      short loc_140015EC6
0x140015ead  or      eax, 0FFFFFFFFh
0x140015eb0  lock xadd [rcx+8], eax
0x140015eb5  cmp     eax, 1
0x140015eb8  jnz     short loc_140015EC6
0x140015eba  mov     rax, [rcx]
0x140015ebd  mov     rax, [rax+8]
0x140015ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ec6  mov     qword ptr [rbx+18h], 0
0x140015ece  mov     rbx, [rbx+8]
0x140015ed2  test    rbx, rbx
0x140015ed5  jz      short loc_140015F0F
0x140015ed7  or      eax, 0FFFFFFFFh
0x140015eda  lock xadd [rbx+8], eax
0x140015edf  cmp     eax, 1
0x140015ee2  jnz     short loc_140015F0F
0x140015ee4  mov     rax, [rbx]
0x140015ee7  mov     rcx, rbx
0x140015eea  mov     rax, [rax]
0x140015eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ef2  or      eax, 0FFFFFFFFh
0x140015ef5  lock xadd [rbx+0Ch], eax
0x140015efa  cmp     eax, 1
0x140015efd  jnz     short loc_140015F0F
0x140015eff  mov     rax, [rbx]
0x140015f02  mov     rcx, rbx
0x140015f05  mov     rax, [rax+8]
0x140015f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015f0e  nop
0x140015f0f  add     rsp, 20h
0x140015f13  pop     rbx
0x140015f14  retn
```
