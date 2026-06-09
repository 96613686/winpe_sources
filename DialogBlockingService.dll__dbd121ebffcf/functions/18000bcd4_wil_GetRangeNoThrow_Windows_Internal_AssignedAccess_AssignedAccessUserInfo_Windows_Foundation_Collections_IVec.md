# wil::GetRangeNoThrow<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *>(Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *> *,long *)

- ea: `0x18000bcd4`
- end: `0x18000bd23`
- name: `??$GetRangeNoThrow@PEAVAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@wil@@YA?AV?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@0@PEAU?$IVectorView@PEAVAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@PEAJ@Z`
- size: `79`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ba5c`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall wil::GetRangeNoThrow<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *>(
        __int64 a1,
        __int64 a2)
{
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 16) = a1 + 24;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 24) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 56LL))(a2, a1 + 8);
  return a1;
}

```

## disassembly

```asm
0x18000bcd4  mov     [rsp+arg_0], rbx
0x18000bcd9  push    rdi
0x18000bcda  sub     rsp, 20h
0x18000bcde  lea     rax, [rcx+18h]
0x18000bce2  mov     [rcx], rdx
0x18000bce5  mov     [rcx+10h], rax
0x18000bce9  mov     rbx, rax
0x18000bcec  mov     qword ptr [rcx+20h], 0
0x18000bcf4  mov     r8, rdx
0x18000bcf7  mov     dword ptr [rax], 0
0x18000bcfd  mov     rdi, rcx
0x18000bd00  mov     rax, [rdx]
0x18000bd03  lea     rdx, [rcx+8]
0x18000bd07  mov     rcx, r8
0x18000bd0a  mov     rax, [rax+38h]
0x18000bd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd13  mov     [rbx], eax
0x18000bd15  mov     rax, rdi
0x18000bd18  mov     rbx, [rsp+28h+arg_0]
0x18000bd1d  add     rsp, 20h
0x18000bd21  pop     rdi
0x18000bd22  retn
```
