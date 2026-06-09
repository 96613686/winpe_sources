# std::_Associated_state<int>::_Associated_state<int>(std::_Deleter_base<int> *)

- ea: `0x18001d7e0`
- end: `0x18001d85b`
- name: `??0?$_Associated_state@H@std@@QEAA@PEAU?$_Deleter_base@H@1@@Z`
- size: `123`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c69c`
- `0x18001c7a0`
- `0x18001c8a4`

## callees

- `0x18001db00`
- `0x18001dcb0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001d80e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001d80e`

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
0x18001d7e0  push    rbx
0x18001d7e2  sub     rsp, 20h
0x18001d7e6  mov     qword ptr [rcx+8], 1
0x18001d7ee  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x18001d7f5  mov     [rcx], rax
0x18001d7f8  mov     rbx, rcx
0x18001d7fb  add     rcx, 10h
0x18001d7ff  mov     qword ptr [rcx+8], 0
0x18001d807  mov     qword ptr [rcx], 0
0x18001d80e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001d814  lea     rcx, [rbx+20h]; this
0x18001d818  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x18001d81d  lea     rcx, [rbx+70h]; this
0x18001d821  call    ??0condition_variable@std@@QEAA@XZ; std::condition_variable::condition_variable(void)
0x18001d826  mov     rax, rbx
0x18001d829  mov     byte ptr [rbx+0B8h], 0
0x18001d830  mov     dword ptr [rbx+0BCh], 0
0x18001d83a  mov     word ptr [rbx+0C0h], 0
0x18001d843  mov     byte ptr [rbx+0C2h], 0
0x18001d84a  mov     qword ptr [rbx+0C8h], 0
0x18001d855  add     rsp, 20h
0x18001d859  pop     rbx
0x18001d85a  retn
```
