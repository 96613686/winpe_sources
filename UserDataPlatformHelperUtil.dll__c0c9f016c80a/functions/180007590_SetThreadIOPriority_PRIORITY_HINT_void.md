# SetThreadIOPriority(_PRIORITY_HINT,void *)

- ea: `0x180007590`
- end: `0x1800075eb`
- name: `?SetThreadIOPriority@@YAJW4_PRIORITY_HINT@@PEAX@Z`
- size: `91`
- prototype: `int __fastcall(enum _PRIORITY_HINT, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180007590`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800075b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800075b9`
- `ntdll!NtSetInformationThread` at `0x1800075d4`
- `ntdll!NtSetInformationThread` at `0x1800075d4`

## pseudocode

```c
int __fastcall SetThreadIOPriority(enum _PRIORITY_HINT a1, void *a2)
{
  HANDLE CurrentThread; // r10
  int v3; // eax
  NTSTATUS v4; // eax
  int ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  CurrentThread = a2;
  if ( a1 )
  {
    if ( a1 == IoPriorityHintLow )
      v3 = 1;
    else
      v3 = 2;
  }
  else
  {
    v3 = 0;
  }
  ThreadInformation = v3;
  if ( !a2 )
    CurrentThread = GetCurrentThread();
  v4 = NtSetInformationThread(CurrentThread, ThreadIoPriority, &ThreadInformation, 4u);
  if ( v4 >= 0 )
    return 0;
  else
    return v4 | 0x10000000;
}

```

## disassembly

```asm
0x180007590  sub     rsp, 28h
0x180007594  mov     r10, rdx
0x180007597  test    ecx, ecx
0x180007599  jz      short loc_1800075AE
0x18000759b  cmp     ecx, 1
0x18000759e  jz      short loc_1800075A7
0x1800075a0  mov     eax, 2
0x1800075a5  jmp     short loc_1800075B0
0x1800075a7  mov     eax, 1
0x1800075ac  jmp     short loc_1800075B0
0x1800075ae  xor     eax, eax
0x1800075b0  mov     [rsp+28h+ThreadInformation], eax
0x1800075b4  test    rdx, rdx
0x1800075b7  jnz     short loc_1800075C2
0x1800075b9  call    cs:__imp_GetCurrentThread
0x1800075bf  mov     r10, rax
0x1800075c2  mov     r9d, 4; ThreadInformationLength
0x1800075c8  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x1800075cd  mov     rcx, r10; ThreadHandle
0x1800075d0  lea     edx, [r9+12h]; ThreadInformationClass
0x1800075d4  call    cs:__imp_NtSetInformationThread
0x1800075da  test    eax, eax
0x1800075dc  jns     short loc_1800075E4
0x1800075de  bts     eax, 1Ch
0x1800075e2  jmp     short loc_1800075E6
0x1800075e4  xor     eax, eax
0x1800075e6  add     rsp, 28h
0x1800075ea  retn
```
