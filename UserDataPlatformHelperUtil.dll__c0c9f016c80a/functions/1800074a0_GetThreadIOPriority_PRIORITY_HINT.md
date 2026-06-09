# GetThreadIOPriority(_PRIORITY_HINT *)

- ea: `0x1800074a0`
- end: `0x180007509`
- name: `?GetThreadIOPriority@@YAJPEAW4_PRIORITY_HINT@@@Z`
- size: `105`
- prototype: `int __fastcall(enum _PRIORITY_HINT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800074a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800074b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800074b1`
- `ntdll!NtQueryInformationThread` at `0x1800074d2`
- `ntdll!NtQueryInformationThread` at `0x1800074d2`

## pseudocode

```c
int __fastcall GetThreadIOPriority(enum _PRIORITY_HINT *a1)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v3; // eax
  enum _PRIORITY_HINT v5; // ecx
  int ThreadInformation; // [rsp+48h] [rbp+10h] BYREF

  ThreadInformation = 0;
  CurrentThread = GetCurrentThread();
  v3 = NtQueryInformationThread(CurrentThread, ThreadIoPriority, &ThreadInformation, 4u, 0);
  if ( v3 < 0 )
    return v3 | 0x10000000;
  if ( ThreadInformation )
  {
    if ( ThreadInformation == 1 )
      v5 = IoPriorityHintLow;
    else
      v5 = IoPriorityHintNormal;
  }
  else
  {
    v5 = IoPriorityHintVeryLow;
  }
  *a1 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800074a0  push    rbx
0x1800074a2  sub     rsp, 30h
0x1800074a6  mov     rbx, rcx
0x1800074a9  mov     [rsp+38h+ThreadInformation], 0
0x1800074b1  call    cs:__imp_GetCurrentThread
0x1800074b7  mov     r9d, 4; ThreadInformationLength
0x1800074bd  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x1800074c6  mov     rcx, rax; ThreadHandle
0x1800074c9  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1800074ce  lea     edx, [r9+12h]; ThreadInformationClass
0x1800074d2  call    cs:__imp_NtQueryInformationThread
0x1800074d8  test    eax, eax
0x1800074da  jns     short loc_1800074E2
0x1800074dc  bts     eax, 1Ch
0x1800074e0  jmp     short loc_180007503
0x1800074e2  mov     eax, [rsp+38h+ThreadInformation]
0x1800074e6  test    eax, eax
0x1800074e8  jz      short loc_1800074FD
0x1800074ea  sub     eax, 1
0x1800074ed  jz      short loc_1800074F6
0x1800074ef  mov     ecx, 2
0x1800074f4  jmp     short loc_1800074FF
0x1800074f6  mov     ecx, 1
0x1800074fb  jmp     short loc_1800074FF
0x1800074fd  xor     ecx, ecx
0x1800074ff  mov     [rbx], ecx
0x180007501  xor     eax, eax
0x180007503  add     rsp, 30h
0x180007507  pop     rbx
0x180007508  retn
```
