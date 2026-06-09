# CBroker::SebRpcEventState::UpdateRefcount(uchar)

- ea: `0x180016de0`
- end: `0x180016eac`
- name: `?UpdateRefcount@SebRpcEventState@CBroker@@QEAAKE@Z`
- size: `204`
- prototype: `unsigned int __fastcall(CBroker::SebRpcEventState *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015b10`

## callees

- `0x180016de0`
- `0x18001cf50`
- `0x1800223e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016e0a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016e0a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016e83`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016e83`
- `ntdll!RtlPublishWnfStateData` at `0x180016e70`
- `ntdll!RtlPublishWnfStateData` at `0x180016e70`
- `ntdll!RtlNtStatusToDosError` at `0x180016e78`
- `ntdll!RtlNtStatusToDosError` at `0x180016e78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016e10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016e10`

## pseudocode

```c
__int64 __fastcall CBroker::SebRpcEventState::UpdateRefcount(CBroker::SebRpcEventState *this, char a2)
{
  char v4; // cl
  unsigned __int8 v5; // dl
  NTSTATUS v6; // eax
  ULONG v7; // ebx
  _DWORD v9[1024]; // [rsp+30h] [rbp-1018h] BYREF

  RtlAcquireSRWLockExclusive(this);
  GetCurrentThreadId();
  v4 = *((_BYTE *)this + 8);
  v9[1] = -1;
  v5 = v4 + 1;
  if ( !a2 )
    v5 = v4 - 1;
  *((_BYTE *)this + 8) = v5;
  if ( v5 <= 1u )
    v9[0] = v5 != 0 ? 3 : 1;
  else
    v9[0] = (v5 != 0 ? 3 : 1) | (v5 << 14);
  v6 = RtlPublishWnfStateData(*(_QWORD *)((char *)this + 12), 0, v9, 8, 0);
  v7 = RtlNtStatusToDosError(v6);
  RtlReleaseSRWLockExclusive(this);
  return v7;
}

```

## disassembly

```asm
0x180016de0  mov     [rsp+arg_8], rbx
0x180016de5  push    rdi
0x180016de6  mov     eax, 1040h
0x180016deb  call    _alloca_probe
0x180016df0  sub     rsp, rax
0x180016df3  mov     rax, cs:__security_cookie
0x180016dfa  xor     rax, rsp
0x180016dfd  mov     [rsp+1048h+var_18], rax
0x180016e05  mov     bl, dl
0x180016e07  mov     rdi, rcx
0x180016e0a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180016e10  call    cs:__imp_GetCurrentThreadId
0x180016e16  mov     cl, [rdi+8]
0x180016e19  mov     [rsp+1048h+var_1014], 0FFFFFFFFh
0x180016e21  lea     eax, [rcx-1]
0x180016e24  inc     cl
0x180016e26  movzx   edx, cl
0x180016e29  test    bl, bl
0x180016e2b  movzx   eax, al
0x180016e2e  cmovz   edx, eax
0x180016e31  mov     al, dl
0x180016e33  mov     [rdi+8], dl
0x180016e36  neg     al
0x180016e38  sbb     ecx, ecx
0x180016e3a  and     ecx, 2
0x180016e3d  inc     ecx
0x180016e3f  cmp     dl, 1
0x180016e42  jbe     short loc_180016E52
0x180016e44  movzx   eax, dl
0x180016e47  shl     eax, 0Eh
0x180016e4a  or      eax, ecx
0x180016e4c  mov     [rsp+1048h+var_1018], eax
0x180016e50  jmp     short loc_180016E56
0x180016e52  mov     [rsp+1048h+var_1018], ecx
0x180016e56  mov     rcx, [rdi+0Ch]
0x180016e5a  lea     r8, [rsp+1048h+var_1018]
0x180016e5f  mov     r9d, 8
0x180016e65  mov     [rsp+1048h+var_1028], 0
0x180016e6e  xor     edx, edx
0x180016e70  call    cs:__imp_RtlPublishWnfStateData
0x180016e76  mov     ecx, eax; Status
0x180016e78  call    cs:__imp_RtlNtStatusToDosError
0x180016e7e  mov     rcx, rdi
0x180016e81  mov     ebx, eax
0x180016e83  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180016e89  mov     eax, ebx
0x180016e8b  mov     rcx, [rsp+1048h+var_18]
0x180016e93  xor     rcx, rsp; StackCookie
0x180016e96  call    __security_check_cookie
0x180016e9b  mov     rbx, [rsp+1048h+arg_8]
0x180016ea3  add     rsp, 1040h
0x180016eaa  pop     rdi
0x180016eab  retn
```
