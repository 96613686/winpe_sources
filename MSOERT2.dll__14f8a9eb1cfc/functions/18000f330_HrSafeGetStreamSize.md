# HrSafeGetStreamSize

- ea: `0x18000f330`
- end: `0x18000f3a7`
- name: `HrSafeGetStreamSize`
- size: `119`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000f1a0`
- `0x18000f330`
- `0x18000f410`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall HrSafeGetStreamSize(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  __int64 v5; // rdx
  unsigned int v6; // [rsp+60h] [rbp+18h] BYREF
  __int64 v7; // [rsp+68h] [rbp+20h] BYREF

  v6 = 0;
  v7 = 0;
  result = HrGetStreamPos(a1, &v6);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)a1 + 40LL))(a1, 0, 2, &v7);
    if ( (int)result >= 0 )
    {
      v5 = v6;
      *a2 = v7;
      return HrStreamSeekSet(a1, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f330  mov     rax, rsp
0x18000f333  mov     [rax+8], rbx
0x18000f337  push    rdi
0x18000f338  sub     rsp, 40h
0x18000f33c  mov     rdi, rdx
0x18000f33f  mov     dword ptr [rax+18h], 0
0x18000f346  lea     rdx, [rax+18h]
0x18000f34a  mov     qword ptr [rax+20h], 0
0x18000f352  mov     rbx, rcx
0x18000f355  mov     [rsp+48h+var_18], 0
0x18000f35e  call    HrGetStreamPos
0x18000f363  test    eax, eax
0x18000f365  js      short loc_18000F39C
0x18000f367  mov     rax, [rbx]
0x18000f36a  lea     r9, [rsp+48h+arg_18]
0x18000f36f  mov     rdx, [rsp+48h+var_18]
0x18000f374  mov     r8d, 2
0x18000f37a  mov     rcx, rbx
0x18000f37d  mov     rax, [rax+28h]
0x18000f381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f386  test    eax, eax
0x18000f388  js      short loc_18000F39C
0x18000f38a  mov     eax, dword ptr [rsp+48h+arg_18]
0x18000f38e  mov     rcx, rbx
0x18000f391  mov     edx, [rsp+48h+arg_10]
0x18000f395  mov     [rdi], eax
0x18000f397  call    HrStreamSeekSet
0x18000f39c  mov     rbx, [rsp+48h+arg_0]
0x18000f3a1  add     rsp, 40h
0x18000f3a5  pop     rdi
0x18000f3a6  retn
```
