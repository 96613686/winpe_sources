# std::_Associated_state<int>::_Associated_state<int>(std::_Deleter_base<int> *)

- ea: `0x180011568`
- end: `0x1800115e3`
- name: `??0?$_Associated_state@H@std@@QEAA@PEAU?$_Deleter_base@H@1@@Z`
- size: `123`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d73c`
- `0x180031d7c`

## callees

- `0x180011fd0`
- `0x1800121a8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180011596`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180011596`

## pseudocode

```c
__int64 __fastcall std::_Associated_state<int>::_Associated_state<int>(__int64 a1)
{
  _QWORD *v2; // rcx
  int v3; // edx
  __int64 result; // rax

  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &std::_Associated_state<int>::`vftable';
  v2 = (_QWORD *)(a1 + 16);
  v2[1] = 0;
  *v2 = 0;
  __ExceptionPtrCreate(v2);
  std::_Mutex_base::_Mutex_base((std::_Mutex_base *)(a1 + 32), v3);
  std::condition_variable::condition_variable((std::condition_variable *)(a1 + 112));
  result = a1;
  *(_BYTE *)(a1 + 184) = 0;
  *(_DWORD *)(a1 + 188) = 0;
  *(_WORD *)(a1 + 192) = 0;
  *(_BYTE *)(a1 + 194) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  return result;
}

```

## disassembly

```asm
0x180011568  push    rbx
0x18001156a  sub     rsp, 20h
0x18001156e  mov     qword ptr [rcx+8], 1
0x180011576  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x18001157d  mov     [rcx], rax
0x180011580  mov     rbx, rcx
0x180011583  add     rcx, 10h
0x180011587  mov     qword ptr [rcx+8], 0
0x18001158f  mov     qword ptr [rcx], 0
0x180011596  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001159c  lea     rcx, [rbx+20h]; this
0x1800115a0  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x1800115a5  lea     rcx, [rbx+70h]; this
0x1800115a9  call    ??0condition_variable@std@@QEAA@XZ; std::condition_variable::condition_variable(void)
0x1800115ae  mov     rax, rbx
0x1800115b1  mov     byte ptr [rbx+0B8h], 0
0x1800115b8  mov     dword ptr [rbx+0BCh], 0
0x1800115c2  mov     word ptr [rbx+0C0h], 0
0x1800115cb  mov     byte ptr [rbx+0C2h], 0
0x1800115d2  mov     qword ptr [rbx+0C8h], 0
0x1800115dd  add     rsp, 20h
0x1800115e1  pop     rbx
0x1800115e2  retn
```
