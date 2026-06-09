# SavedStateMigrationNetwork::CalculateHash(uint &)

- ea: `0x14021bd48`
- end: `0x14021bdc0`
- name: `?CalculateHash@SavedStateMigrationNetwork@@QEAAHAEAI@Z`
- size: `120`
- prototype: `__int64 __fastcall(SavedStateMigrationNetwork *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a0700`
- `0x1400a0854`

## callees

- `0x1400a1594`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x14021bd69`
- `ntdll!RtlComputeCrc32` at `0x14021bd85`
- `ntdll!RtlComputeCrc32` at `0x14021bda1`
- `ntdll!RtlComputeCrc32` at `0x14021bd69`
- `ntdll!RtlComputeCrc32` at `0x14021bd85`
- `ntdll!RtlComputeCrc32` at `0x14021bda1`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall SavedStateMigrationNetwork::CalculateHash(SavedStateMigrationNetwork *this, unsigned int *a2)
{
  ULONG KeyEntryTableUsedBytes; // eax
  ULONG v5; // eax
  ULONG v6; // eax

  KeyEntryTableUsedBytes = SavedStateStorage::GetKeyEntryTableUsedBytes(this);
  v5 = RtlComputeCrc32(0, *((PUCHAR *)this + 18), KeyEntryTableUsedBytes);
  v6 = RtlComputeCrc32(v5, *((PUCHAR *)this + 21), *((_DWORD *)this + 45));
  *a2 = RtlComputeCrc32(v6, *((PUCHAR *)this + 24), *((_DWORD *)this + 50));
  return 1;
}

```

## disassembly

```asm
0x14021bd48  mov     [rsp+arg_0], rbx
0x14021bd4d  push    rdi
0x14021bd4e  sub     rsp, 20h
0x14021bd52  mov     rdi, rdx
0x14021bd55  mov     rbx, rcx
0x14021bd58  call    ?GetKeyEntryTableUsedBytes@SavedStateStorage@@IEAAIXZ; SavedStateStorage::GetKeyEntryTableUsedBytes(void)
0x14021bd5d  mov     rdx, [rbx+90h]; Buffer
0x14021bd64  mov     r8d, eax; Length
0x14021bd67  xor     ecx, ecx; InitialCrc
0x14021bd69  call    cs:__imp_RtlComputeCrc32
0x14021bd70  nop     dword ptr [rax+rax+00h]
0x14021bd75  mov     r8d, [rbx+0B4h]; Length
0x14021bd7c  mov     ecx, eax; InitialCrc
0x14021bd7e  mov     rdx, [rbx+0A8h]; Buffer
0x14021bd85  call    cs:__imp_RtlComputeCrc32
0x14021bd8c  nop     dword ptr [rax+rax+00h]
0x14021bd91  mov     r8d, [rbx+0C8h]; Length
0x14021bd98  mov     ecx, eax; InitialCrc
0x14021bd9a  mov     rdx, [rbx+0C0h]; Buffer
0x14021bda1  call    cs:__imp_RtlComputeCrc32
0x14021bda8  nop     dword ptr [rax+rax+00h]
0x14021bdad  mov     rbx, [rsp+28h+arg_0]
0x14021bdb2  mov     [rdi], eax
0x14021bdb4  mov     eax, 1
0x14021bdb9  add     rsp, 20h
0x14021bdbd  pop     rdi
0x14021bdbe  retn
```
