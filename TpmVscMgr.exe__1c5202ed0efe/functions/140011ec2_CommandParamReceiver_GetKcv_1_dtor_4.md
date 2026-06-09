# _CommandParamReceiver::GetKcv_::_1_::dtor$4

- ea: `0x140011ec2`
- end: `0x140011eeb`
- name: `_CommandParamReceiver::GetKcv_::_1_::dtor$4`
- size: `41`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140008524`
- `0x140011ec2`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::GetKcv_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 112) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 112) &= ~1u;
    return std::vector<unsigned char,wil::secure_allocator<unsigned char>>::~vector<unsigned char,wil::secure_allocator<unsigned char>>(*(_QWORD *)(a2 + 248));
  }
  return result;
}

```

## disassembly

```asm
0x140011ec2  push    rbp
0x140011ec4  sub     rsp, 20h
0x140011ec8  mov     rbp, rdx
0x140011ecb  mov     eax, [rbp+70h]
0x140011ece  and     eax, 1
0x140011ed1  test    eax, eax
0x140011ed3  jz      short loc_140011EE5
0x140011ed5  and     dword ptr [rbp+70h], 0FFFFFFFEh
0x140011ed9  mov     rcx, [rbp+0F8h]
0x140011ee0  call    ??1?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::~vector<uchar,wil::secure_allocator<uchar>>(void)
0x140011ee5  add     rsp, 20h
0x140011ee9  pop     rbp
0x140011eea  retn
```
