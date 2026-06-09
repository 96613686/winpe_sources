# CGroupPolicyLog::WriteNewRecord(CGroupPolicyRecord *)

- ea: `0x18002a970`
- end: `0x18002a9d8`
- name: `?WriteNewRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(CGroupPolicyLog *__hidden this, struct CGroupPolicyRecord *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b16c`
- `0x18000b3bc`
- `0x18000c2cc`

## callees

- `0x18002a368`
- `0x18002a970`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall CGroupPolicyLog::WriteNewRecord(CGroupPolicyLog *this, struct CGroupPolicyRecord *a2)
{
  __int64 result; // rax

  if ( !*(_DWORD *)(*((_QWORD *)this + 1) + 32LL) )
    return 0;
  result = CGroupPolicyLog::AddBlankRecord(this, a2);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(struct CGroupPolicyRecord *))(*(_QWORD *)a2 + 16LL))(a2);
    if ( (int)result >= 0 )
      return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 112LL))(
               *((_QWORD *)this + 4),
               *((_QWORD *)a2 + 1),
               0,
               0,
               0);
  }
  return result;
}

```

## disassembly

```asm
0x18002a970  mov     [rsp+arg_0], rbx
0x18002a975  push    rdi
0x18002a976  sub     rsp, 30h
0x18002a97a  mov     rax, [rcx+8]
0x18002a97e  mov     rbx, rdx
0x18002a981  mov     rdi, rcx
0x18002a984  cmp     dword ptr [rax+20h], 0
0x18002a988  jnz     short loc_18002A98E
0x18002a98a  xor     eax, eax
0x18002a98c  jmp     short loc_18002A9CD
0x18002a98e  call    ?AddBlankRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@@Z; CGroupPolicyLog::AddBlankRecord(CGroupPolicyRecord *)
0x18002a993  test    eax, eax
0x18002a995  js      short loc_18002A9CD
0x18002a997  mov     rax, [rbx]
0x18002a99a  mov     rcx, rbx
0x18002a99d  mov     rax, [rax+10h]
0x18002a9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9a6  test    eax, eax
0x18002a9a8  js      short loc_18002A9CD
0x18002a9aa  mov     rcx, [rdi+20h]
0x18002a9ae  xor     r9d, r9d
0x18002a9b1  mov     rdx, [rbx+8]
0x18002a9b5  xor     r8d, r8d
0x18002a9b8  mov     [rsp+38h+var_18], 0
0x18002a9c1  mov     rax, [rcx]
0x18002a9c4  mov     rax, [rax+70h]
0x18002a9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9cd  mov     rbx, [rsp+38h+arg_0]
0x18002a9d2  add     rsp, 30h
0x18002a9d6  pop     rdi
0x18002a9d7  retn
```
