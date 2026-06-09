# Microsoft::WRL::ComPtr<IUnknown>::`vector deleting destructor'(uint)

- ea: `0x18000f018`
- end: `0x18000f064`
- name: `??_E?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAPEAXI@Z`
- size: `76`
- prototype: `void *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a6d0`
- `0x18000efd8`

## callees

- `0x18000f018`
- `0x18000f06c`
- `0x180013814`

## pseudocode

```c
void *__fastcall Microsoft::WRL::ComPtr<IUnknown>::`vector deleting destructor'(__int64 a1)
{
  void *v1; // rdi
  __int64 v2; // rbx
  _QWORD *i; // rsi

  v1 = (void *)(a1 - 8);
  v2 = *(_QWORD *)(a1 - 8);
  for ( i = (_QWORD *)(a1 + 8 * v2); v2; --v2 )
    Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(--i);
  operator delete(v1);
  return v1;
}

```

## disassembly

```asm
0x18000f018  mov     [rsp+arg_0], rbx
0x18000f01d  mov     [rsp+arg_8], rsi
0x18000f022  push    rdi
0x18000f023  sub     rsp, 20h
0x18000f027  lea     rdi, [rcx-8]
0x18000f02b  mov     rbx, [rdi]
0x18000f02e  lea     rsi, [rcx+rbx*8]
0x18000f032  test    rbx, rbx
0x18000f035  jz      short loc_18000F049
0x18000f037  sub     rsi, 8
0x18000f03b  mov     rcx, rsi
0x18000f03e  call    ??1?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(void)
0x18000f043  sub     rbx, 1
0x18000f047  jnz     short loc_18000F037
0x18000f049  mov     rcx, rdi; Block
0x18000f04c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f051  mov     rbx, [rsp+28h+arg_0]
0x18000f056  mov     rax, rdi
0x18000f059  mov     rsi, [rsp+28h+arg_8]
0x18000f05e  add     rsp, 20h
0x18000f062  pop     rdi
0x18000f063  retn
```
