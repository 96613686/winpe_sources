# std::promise<long>::promise<long>(void)

- ea: `0x180004dc0`
- end: `0x180004e61`
- name: `??0?$promise@J@std@@QEAA@XZ`
- size: `161`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007534`

## callees

- `0x180002a94`
- `0x1800051c8`
- `0x180005274`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180004e04`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180004e04`

## pseudocode

```c
__int64 __fastcall std::promise<long>::promise<long>(__int64 a1)
{
  _QWORD *v2; // rbx
  int v3; // edx
  __int64 result; // rax

  v2 = operator new(0xD0u);
  *v2 = &std::_Associated_state<long>::`vftable';
  v2[1] = 1;
  v2[2] = 0;
  v2[3] = 0;
  __ExceptionPtrCreate(v2 + 2);
  std::_Mutex_base::_Mutex_base((std::_Mutex_base *)(v2 + 4), v3);
  std::condition_variable::condition_variable((std::condition_variable *)(v2 + 14));
  *((_BYTE *)v2 + 184) = 0;
  result = a1;
  *((_DWORD *)v2 + 47) = 0;
  *((_WORD *)v2 + 96) = 0;
  *((_BYTE *)v2 + 194) = 0;
  v2[25] = 0;
  *(_QWORD *)a1 = v2;
  *(_BYTE *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180004dc0  mov     [rsp+arg_8], rbx
0x180004dc5  push    rdi
0x180004dc6  sub     rsp, 20h
0x180004dca  mov     rdi, rcx
0x180004dcd  mov     ecx, 0D0h; Size
0x180004dd2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004dd7  mov     [rsp+28h+arg_0], rax
0x180004ddc  mov     rbx, rax
0x180004ddf  lea     rax, ??_7?$_Associated_state@J@std@@6B@; const std::_Associated_state<long>::`vftable'
0x180004de6  lea     rcx, [rbx+10h]
0x180004dea  mov     [rbx], rax
0x180004ded  mov     qword ptr [rbx+8], 1
0x180004df5  mov     qword ptr [rcx], 0
0x180004dfc  mov     qword ptr [rcx+8], 0
0x180004e04  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180004e0a  lea     rcx, [rbx+20h]; this
0x180004e0e  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x180004e13  lea     rcx, [rbx+70h]; this
0x180004e17  call    ??0condition_variable@std@@QEAA@XZ; std::condition_variable::condition_variable(void)
0x180004e1c  mov     byte ptr [rbx+0B8h], 0
0x180004e23  mov     rax, rdi
0x180004e26  mov     dword ptr [rbx+0BCh], 0
0x180004e30  mov     word ptr [rbx+0C0h], 0
0x180004e39  mov     byte ptr [rbx+0C2h], 0
0x180004e40  mov     qword ptr [rbx+0C8h], 0
0x180004e4b  mov     [rdi], rbx
0x180004e4e  mov     rbx, [rsp+28h+arg_8]
0x180004e53  mov     byte ptr [rdi+8], 0
0x180004e57  mov     byte ptr [rdi+10h], 0
0x180004e5b  add     rsp, 20h
0x180004e5f  pop     rdi
0x180004e60  retn
```
