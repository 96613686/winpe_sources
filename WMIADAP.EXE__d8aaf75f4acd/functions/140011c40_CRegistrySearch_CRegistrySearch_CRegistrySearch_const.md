# CRegistrySearch::CRegistrySearch(CRegistrySearch const &)

- ea: `0x140011c40`
- end: `0x140011c81`
- name: `??0CRegistrySearch@@QEAA@AEBV0@@Z`
- size: `65`
- prototype: `CRegistrySearch *__fastcall(CRegistrySearch *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000fc80`

## pseudocode

```c
CRegistrySearch *__fastcall CRegistrySearch::CRegistrySearch(CRegistrySearch *this, unsigned __int16 **a2)
{
  CRegistrySearch *result; // rax

  *(_DWORD *)this = *(_DWORD *)a2;
  CHString::CHString((CRegistrySearch *)((char *)this + 8), a2 + 1);
  result = this;
  *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
  *((_QWORD *)this + 4) = a2[4];
  return result;
}

```

## disassembly

```asm
0x140011c40  mov     [rsp+arg_0], rbx
0x140011c45  push    rdi
0x140011c46  sub     rsp, 20h
0x140011c4a  mov     eax, [rdx]
0x140011c4c  mov     rbx, rdx
0x140011c4f  mov     [rcx], eax
0x140011c51  mov     rdi, rcx
0x140011c54  add     rcx, 8; this
0x140011c58  add     rdx, 8; struct CHString *
0x140011c5c  call    ??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x140011c61  movups  xmm0, xmmword ptr [rbx+10h]
0x140011c65  mov     rax, rdi
0x140011c68  movups  xmmword ptr [rdi+10h], xmm0
0x140011c6c  movsd   xmm1, qword ptr [rbx+20h]
0x140011c71  mov     rbx, [rsp+28h+arg_0]
0x140011c76  movsd   qword ptr [rdi+20h], xmm1
0x140011c7b  add     rsp, 20h
0x140011c7f  pop     rdi
0x140011c80  retn
```
