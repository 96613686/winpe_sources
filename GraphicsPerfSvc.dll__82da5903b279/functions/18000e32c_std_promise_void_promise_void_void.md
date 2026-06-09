# std::promise<void>::promise<void>(void)

- ea: `0x18000e32c`
- end: `0x18000e3db`
- name: `??0?$promise@X@std@@QEAA@XZ`
- size: `175`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003510`

## callees

- `0x180003ebc`
- `0x18000e444`
- `0x18000e478`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000e374`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000e374`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *std::promise<void>::promise<void>()
{
  _QWORD *v0; // rbx
  int v1; // edx
  __int64 *result; // rax

  v0 = operator new(0xD0u);
  *v0 = &std::_Associated_state<int>::`vftable';
  v0[1] = 1;
  v0[2] = 0;
  v0[3] = 0;
  __ExceptionPtrCreate(v0 + 2);
  std::_Mutex_base::_Mutex_base((std::_Mutex_base *)(v0 + 4), v1);
  std::condition_variable::condition_variable((std::condition_variable *)(v0 + 14));
  *((_BYTE *)v0 + 184) = 0;
  result = &g::StartEtwThread;
  *((_DWORD *)v0 + 47) = 0;
  *((_WORD *)v0 + 96) = 0;
  *((_BYTE *)v0 + 194) = 0;
  v0[25] = 0;
  g::StartEtwThread = (__int64)v0;
  byte_180042DC8 = 0;
  byte_180042DD0 = 0;
  return result;
}

```

## disassembly

```asm
0x18000e32c  mov     [rsp+arg_8], rbx
0x18000e331  push    rsi
0x18000e332  sub     rsp, 20h
0x18000e336  mov     ecx, 0D0h; Size
0x18000e33b  lea     rsi, ?StartEtwThread@g@@3V?$promise@X@std@@A; std::promise<void> g::StartEtwThread
0x18000e342  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e347  mov     [rsp+28h+arg_0], rax
0x18000e34c  mov     rbx, rax
0x18000e34f  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x18000e356  lea     rcx, [rbx+10h]
0x18000e35a  mov     [rbx], rax
0x18000e35d  mov     qword ptr [rbx+8], 1
0x18000e365  mov     qword ptr [rcx], 0
0x18000e36c  mov     qword ptr [rcx+8], 0
0x18000e374  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000e37a  lea     rcx, [rbx+20h]; this
0x18000e37e  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x18000e383  lea     rcx, [rbx+70h]; this
0x18000e387  call    ??0condition_variable@std@@QEAA@XZ; std::condition_variable::condition_variable(void)
0x18000e38c  mov     byte ptr [rbx+0B8h], 0
0x18000e393  mov     rax, rsi
0x18000e396  mov     dword ptr [rbx+0BCh], 0
0x18000e3a0  mov     word ptr [rbx+0C0h], 0
0x18000e3a9  mov     byte ptr [rbx+0C2h], 0
0x18000e3b0  mov     qword ptr [rbx+0C8h], 0
0x18000e3bb  mov     cs:?StartEtwThread@g@@3V?$promise@X@std@@A, rbx; std::promise<void> g::StartEtwThread
0x18000e3c2  mov     rbx, [rsp+28h+arg_8]
0x18000e3c7  mov     cs:byte_180042DC8, 0
0x18000e3ce  mov     cs:byte_180042DD0, 0
0x18000e3d5  add     rsp, 20h
0x18000e3d9  pop     rsi
0x18000e3da  retn
```
