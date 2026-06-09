# Concurrency::details::platform::__SetThreadGroupAffinity(void *,_GROUP_AFFINITY const *)

- ea: `0x18030fd48`
- end: `0x18030fd9b`
- name: `?__SetThreadGroupAffinity@platform@details@Concurrency@@YAHPEAXPEBU_GROUP_AFFINITY@@@Z`
- size: `83`
- prototype: `__int64 __fastcall(HANDLE hThread, void *, const struct _GROUP_AFFINITY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180310aa0`

## callees

- `0x18030fd48`
- `0x18030fec8`
- `0x180312b78`
- `0x180358070`

## import_xrefs

- `KERNEL32!SetThreadAffinityMask` at `0x18030fd85`
- `KERNEL32!SetThreadAffinityMask` at `0x18030fd85`

## pseudocode

```c
__int64 __fastcall Concurrency::details::platform::__SetThreadGroupAffinity(
        HANDLE hThread,
        DWORD_PTR *a2,
        const struct _GROUP_AFFINITY *a3)
{
  void (__fastcall *v5)(HANDLE, DWORD_PTR *, _QWORD); // rax

  if ( (int)Concurrency::GetOSVersion(hThread, a2, a3) < 4 )
  {
    SetThreadAffinityMask(hThread, *a2);
  }
  else
  {
    v5 = (void (__fastcall *)(HANDLE, DWORD_PTR *, _QWORD))Concurrency::details::Security::EncodePointer(qword_1804C6EF8);
    v5(hThread, a2, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x18030fd48  mov     [rsp+arg_0], rbx
0x18030fd4d  push    rdi
0x18030fd4e  sub     rsp, 20h
0x18030fd52  mov     rbx, rdx
0x18030fd55  mov     rdi, rcx
0x18030fd58  call    ?GetOSVersion@Concurrency@@YA?AW4OSVersion@IResourceManager@1@XZ; Concurrency::GetOSVersion(void)
0x18030fd5d  cmp     eax, 4
0x18030fd60  jl      short loc_18030FD7F
0x18030fd62  mov     rcx, cs:qword_1804C6EF8; void *
0x18030fd69  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x18030fd6e  xor     r8d, r8d
0x18030fd71  mov     rdx, rbx
0x18030fd74  mov     rcx, rdi
0x18030fd77  call    cs:__guard_dispatch_icall_fptr
0x18030fd7d  jmp     short loc_18030FD8B
0x18030fd7f  mov     rdx, [rbx]; dwThreadAffinityMask
0x18030fd82  mov     rcx, rdi; hThread
0x18030fd85  call    cs:__imp_SetThreadAffinityMask
0x18030fd8b  mov     rbx, [rsp+28h+arg_0]
0x18030fd90  mov     eax, 1
0x18030fd95  add     rsp, 20h
0x18030fd99  pop     rdi
0x18030fd9a  retn
```
