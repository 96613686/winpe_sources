# CRegistrySearch::operator=(CRegistrySearch const &)

- ea: `0x140011e20`
- end: `0x140011e61`
- name: `??4CRegistrySearch@@QEAAAEAV0@AEBV0@@Z`
- size: `65`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ffc0`

## pseudocode

```c
__int64 __fastcall CRegistrySearch::operator=(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  *(_DWORD *)a1 = *(_DWORD *)a2;
  CHString::operator=((const unsigned __int16 **)(a1 + 8), (const unsigned __int16 **)(a2 + 8));
  result = a1;
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a2 + 32);
  return result;
}

```

## disassembly

```asm
0x140011e20  mov     [rsp+arg_0], rbx
0x140011e25  push    rdi
0x140011e26  sub     rsp, 20h
0x140011e2a  mov     eax, [rdx]
0x140011e2c  mov     rbx, rdx
0x140011e2f  mov     [rcx], eax
0x140011e31  mov     rdi, rcx
0x140011e34  add     rcx, 8; this
0x140011e38  add     rdx, 8
0x140011e3c  call    ??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x140011e41  movups  xmm0, xmmword ptr [rbx+10h]
0x140011e45  mov     rax, rdi
0x140011e48  movups  xmmword ptr [rdi+10h], xmm0
0x140011e4c  movsd   xmm1, qword ptr [rbx+20h]
0x140011e51  mov     rbx, [rsp+28h+arg_0]
0x140011e56  movsd   qword ptr [rdi+20h], xmm1
0x140011e5b  add     rsp, 20h
0x140011e5f  pop     rdi
0x140011e60  retn
```
