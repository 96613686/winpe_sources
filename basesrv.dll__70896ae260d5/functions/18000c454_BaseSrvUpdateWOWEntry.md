# BaseSrvUpdateWOWEntry

- ea: `0x18000c454`
- end: `0x18000c5de`
- name: `BaseSrvUpdateWOWEntry`
- size: `394`
- prototype: `__int64 __fastcall(unsigned int *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000c250`

## callees

- `0x180009698`
- `0x180009730`
- `0x18000a50c`
- `0x18000a894`
- `0x18000c454`
- `0x18000e010`

## import_xrefs

- `ntdll!NtClose` at `0x18000c4e3`
- `ntdll!NtClose` at `0x18000c4e3`
- `ntdll!RtlEnterCriticalSection` at `0x18000c482`
- `ntdll!RtlEnterCriticalSection` at `0x18000c482`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c5c4`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c5c4`

## pseudocode

```c
__int64 __fastcall BaseSrvUpdateWOWEntry(unsigned int *a1, int a2)
{
  __int64 v4; // rcx
  int SharedWowRecordByTaskId; // ebx
  __int64 v6; // rsi
  _QWORD *v7; // rdi
  _QWORD *v8; // rcx
  _QWORD *i; // rax
  __int64 v10; // rcx
  bool v11; // zf
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+80h] [rbp+40h] BYREF
  PVOID P; // [rsp+88h] [rbp+48h] BYREF

  v14 = 0;
  P = 0;
  v13 = 0;
  v15 = 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  SharedWowRecordByTaskId = BaseSrvFindSharedWowRecordByTaskId(v4, *a1, &v14, &P);
  if ( SharedWowRecordByTaskId < 0 )
    goto LABEL_26;
  v6 = v14;
  if ( a2 != *(_DWORD *)(v14 + 84) )
  {
    SharedWowRecordByTaskId = -1073741811;
    goto LABEL_26;
  }
  v7 = P;
  if ( *((_WORD *)a1 + 16) )
  {
    if ( *((_WORD *)a1 + 16) == 1 )
      SharedWowRecordByTaskId = 0;
LABEL_22:
    if ( *((_WORD *)a1 + 16) == 1 )
    {
      SharedWowRecordByTaskId = BaseSrvCreatePairWaitHandles(&v13, &v15);
      if ( SharedWowRecordByTaskId >= 0 )
      {
        v11 = UserNotifyProcessCreate == 0;
        v7[1] = v13;
        v7[2] = v15;
        *((_QWORD *)a1 + 3) = v15;
        if ( !v11 )
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64))UserNotifyProcessCreate)(
            *(unsigned int *)P,
            *((unsigned int *)NtCurrentTeb()->CsrClientThread + 12),
            (unsigned int)v15,
            4);
      }
    }
    goto LABEL_26;
  }
  if ( (*((_BYTE *)a1 + 34) & 6) != 0 )
  {
    NtClose(*((HANDLE *)P + 1));
    v7[1] = 0;
  }
  if ( (*((_BYTE *)a1 + 34) & 1) == 0 && (*((_BYTE *)a1 + 34) & 2) == 0 )
    goto LABEL_22;
  v8 = *(_QWORD **)(v6 + 56);
  if ( v8 )
  {
    if ( v8 == v7 )
    {
      *(_QWORD *)(v6 + 56) = v7[4];
    }
    else
    {
      for ( i = (_QWORD *)v8[4]; i; i = (_QWORD *)i[4] )
      {
        if ( i == v7 )
        {
          v8[4] = v7[4];
          break;
        }
        v8 = i;
      }
    }
  }
  BaseSrvFreeWOWRecord(v7);
  if ( *(_QWORD *)(v6 + 56) )
    goto LABEL_22;
  SharedWowRecordByTaskId = BaseSrvDeleteSharedWowRecord(v10, v6);
  if ( SharedWowRecordByTaskId >= 0 )
    goto LABEL_22;
LABEL_26:
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return (unsigned int)SharedWowRecordByTaskId;
}

```

## disassembly

```asm
0x18000c454  push    rbp
0x18000c456  push    rbx
0x18000c457  push    rsi
0x18000c458  push    rdi
0x18000c459  push    r14
0x18000c45b  mov     rbp, rsp
0x18000c45e  sub     rsp, 40h
0x18000c462  and     [rbp+arg_0], 0
0x18000c467  mov     r14, rcx
0x18000c46a  and     [rbp+P], 0
0x18000c46f  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c476  and     [rbp+var_10], 0
0x18000c47b  mov     edi, edx
0x18000c47d  and     [rbp+arg_10], 0
0x18000c482  call    cs:__imp_RtlEnterCriticalSection
0x18000c489  nop     dword ptr [rax+rax+00h]
0x18000c48e  mov     edx, [r14]
0x18000c491  lea     r9, [rbp+P]
0x18000c495  lea     r8, [rbp+arg_0]
0x18000c499  call    BaseSrvFindSharedWowRecordByTaskId
0x18000c49e  mov     ebx, eax
0x18000c4a0  test    eax, eax
0x18000c4a2  js      loc_18000C5BD
0x18000c4a8  mov     rsi, [rbp+arg_0]
0x18000c4ac  cmp     edi, [rsi+54h]
0x18000c4af  jz      short loc_18000C4BB
0x18000c4b1  mov     ebx, 0C000000Dh
0x18000c4b6  jmp     loc_18000C5BD
0x18000c4bb  movzx   ecx, word ptr [r14+20h]
0x18000c4c0  mov     rdi, [rbp+P]
0x18000c4c4  test    ecx, ecx
0x18000c4c6  jz      short loc_18000C4D8
0x18000c4c8  cmp     ecx, 1
0x18000c4cb  jnz     loc_18000C558
0x18000c4d1  xor     ebx, ebx
0x18000c4d3  jmp     loc_18000C558
0x18000c4d8  test    byte ptr [r14+22h], 6
0x18000c4dd  jz      short loc_18000C4F4
0x18000c4df  mov     rcx, [rdi+8]; Handle
0x18000c4e3  call    cs:__imp_NtClose
0x18000c4ea  nop     dword ptr [rax+rax+00h]
0x18000c4ef  and     qword ptr [rdi+8], 0
0x18000c4f4  test    byte ptr [r14+22h], 1
0x18000c4f9  jnz     short loc_18000C502
0x18000c4fb  test    byte ptr [r14+22h], 2
0x18000c500  jz      short loc_18000C558
0x18000c502  mov     rcx, [rsi+38h]
0x18000c506  test    rcx, rcx
0x18000c509  jz      short loc_18000C53B
0x18000c50b  cmp     rcx, rdi
0x18000c50e  jnz     short loc_18000C51A
0x18000c510  mov     rax, [rdi+20h]
0x18000c514  mov     [rsi+38h], rax
0x18000c518  jmp     short loc_18000C53B
0x18000c51a  mov     rax, [rcx+20h]
0x18000c51e  jmp     short loc_18000C52C
0x18000c520  cmp     rax, rdi
0x18000c523  jz      short loc_18000C533
0x18000c525  mov     rcx, rax
0x18000c528  mov     rax, [rax+20h]
0x18000c52c  test    rax, rax
0x18000c52f  jnz     short loc_18000C520
0x18000c531  jmp     short loc_18000C53B
0x18000c533  mov     rax, [rdi+20h]
0x18000c537  mov     [rcx+20h], rax
0x18000c53b  mov     rcx, rdi; P
0x18000c53e  call    BaseSrvFreeWOWRecord
0x18000c543  cmp     qword ptr [rsi+38h], 0
0x18000c548  jnz     short loc_18000C558
0x18000c54a  mov     rdx, rsi
0x18000c54d  call    BaseSrvDeleteSharedWowRecord
0x18000c552  mov     ebx, eax
0x18000c554  test    eax, eax
0x18000c556  js      short loc_18000C5BD
0x18000c558  cmp     word ptr [r14+20h], 1
0x18000c55e  jnz     short loc_18000C5BD
0x18000c560  lea     rdx, [rbp+arg_10]
0x18000c564  lea     rcx, [rbp+var_10]
0x18000c568  call    BaseSrvCreatePairWaitHandles
0x18000c56d  mov     ebx, eax
0x18000c56f  test    eax, eax
0x18000c571  js      short loc_18000C5BD
0x18000c573  cmp     cs:UserNotifyProcessCreate, 0
0x18000c57b  mov     rax, [rbp+var_10]
0x18000c57f  mov     [rdi+8], rax
0x18000c583  mov     rax, [rbp+arg_10]
0x18000c587  mov     [rdi+10h], rax
0x18000c58b  mov     rax, [rbp+arg_10]
0x18000c58f  mov     [r14+18h], rax
0x18000c593  jz      short loc_18000C5BD
0x18000c595  mov     rdx, gs:70h
0x18000c59e  mov     r9d, 4
0x18000c5a4  mov     rcx, [rbp+P]
0x18000c5a8  mov     r8d, dword ptr [rbp+arg_10]
0x18000c5ac  mov     rax, cs:UserNotifyProcessCreate
0x18000c5b3  mov     edx, [rdx+30h]
0x18000c5b6  mov     ecx, [rcx]
0x18000c5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5bd  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c5c4  call    cs:__imp_RtlLeaveCriticalSection
0x18000c5cb  nop     dword ptr [rax+rax+00h]
0x18000c5d0  mov     eax, ebx
0x18000c5d2  add     rsp, 40h
0x18000c5d6  pop     r14
0x18000c5d8  pop     rdi
0x18000c5d9  pop     rsi
0x18000c5da  pop     rbx
0x18000c5db  pop     rbp
0x18000c5dc  retn
```
