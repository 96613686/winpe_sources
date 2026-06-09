# BaseSrvUpdateWOWEntry

- ea: `0x18000c820`
- end: `0x18000c9ba`
- name: `BaseSrvUpdateWOWEntry`
- size: `410`
- prototype: `__int64 __fastcall(unsigned int *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000c620`

## callees

- `0x18000996c`
- `0x180009a08`
- `0x18000a790`
- `0x18000ab1c`
- `0x18000c820`
- `0x18000e010`

## import_xrefs

- `ntdll!NtClose` at `0x18000c8bb`
- `ntdll!NtClose` at `0x18000c8bb`
- `ntdll!RtlEnterCriticalSection` at `0x18000c85a`
- `ntdll!RtlEnterCriticalSection` at `0x18000c85a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c9a0`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c9a0`

## pseudocode

```c
__int64 __fastcall BaseSrvUpdateWOWEntry(unsigned int *a1, int a2)
{
  __int64 v4; // rcx
  int SharedWowRecordByTaskId; // edi
  __int64 v6; // rsi
  _QWORD *v7; // rbx
  _QWORD *v8; // rcx
  _QWORD *i; // rax
  __int64 v10; // rcx
  bool v11; // zf
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+80h] [rbp+40h] BYREF
  PVOID P; // [rsp+88h] [rbp+48h] BYREF

  v15 = 0;
  P = 0;
  v13 = 0;
  v14 = 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  SharedWowRecordByTaskId = BaseSrvFindSharedWowRecordByTaskId(v4, *a1, &v15, &P);
  if ( SharedWowRecordByTaskId < 0 )
    goto LABEL_27;
  v6 = v15;
  if ( a2 != *(_DWORD *)(v15 + 84) )
  {
    SharedWowRecordByTaskId = -1073741811;
    goto LABEL_27;
  }
  v7 = P;
  if ( *((_WORD *)a1 + 16) )
  {
    if ( *((_WORD *)a1 + 16) == 1 )
      SharedWowRecordByTaskId = 0;
LABEL_23:
    if ( *((_WORD *)a1 + 16) == 1 )
    {
      SharedWowRecordByTaskId = BaseSrvCreatePairWaitHandles(&v13, &v14);
      if ( SharedWowRecordByTaskId >= 0 )
      {
        v11 = UserNotifyProcessCreate == 0;
        v7[1] = v13;
        v7[2] = v14;
        *((_QWORD *)a1 + 3) = v14;
        if ( !v11 )
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64))UserNotifyProcessCreate)(
            *(unsigned int *)v7,
            *((unsigned int *)NtCurrentTeb()->CsrClientThread + 12),
            (unsigned int)v14,
            4);
      }
    }
    goto LABEL_27;
  }
  if ( (*((_BYTE *)a1 + 34) & 6) != 0 )
  {
    NtClose(*((HANDLE *)P + 1));
    v7[1] = 0;
  }
  if ( (*((_BYTE *)a1 + 34) & 1) == 0 && (*((_BYTE *)a1 + 34) & 2) == 0 )
    goto LABEL_23;
  if ( v6 )
  {
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
  }
  BaseSrvFreeWOWRecord(v7);
  if ( *(_QWORD *)(v6 + 56) )
    goto LABEL_23;
  SharedWowRecordByTaskId = BaseSrvDeleteSharedWowRecord(v10, v6);
  if ( SharedWowRecordByTaskId >= 0 )
    goto LABEL_23;
LABEL_27:
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return (unsigned int)SharedWowRecordByTaskId;
}

```

## disassembly

```asm
0x18000c820  push    rbp
0x18000c822  push    rbx
0x18000c823  push    rsi
0x18000c824  push    rdi
0x18000c825  push    r14
0x18000c827  mov     rbp, rsp
0x18000c82a  sub     rsp, 40h
0x18000c82e  mov     r14, rcx
0x18000c831  mov     [rbp+arg_10], 0
0x18000c839  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c840  mov     [rbp+P], 0
0x18000c848  mov     ebx, edx
0x18000c84a  mov     [rbp+var_10], 0
0x18000c852  mov     [rbp+arg_0], 0
0x18000c85a  call    cs:__imp_RtlEnterCriticalSection
0x18000c861  nop     dword ptr [rax+rax+00h]
0x18000c866  mov     edx, [r14]
0x18000c869  lea     r9, [rbp+P]
0x18000c86d  lea     r8, [rbp+arg_10]
0x18000c871  call    BaseSrvFindSharedWowRecordByTaskId
0x18000c876  mov     edi, eax
0x18000c878  test    eax, eax
0x18000c87a  js      loc_18000C999
0x18000c880  mov     rsi, [rbp+arg_10]
0x18000c884  cmp     ebx, [rsi+54h]
0x18000c887  jz      short loc_18000C893
0x18000c889  mov     edi, 0C000000Dh
0x18000c88e  jmp     loc_18000C999
0x18000c893  movzx   ecx, word ptr [r14+20h]
0x18000c898  mov     rbx, [rbp+P]
0x18000c89c  test    ecx, ecx
0x18000c89e  jz      short loc_18000C8B0
0x18000c8a0  cmp     ecx, 1
0x18000c8a3  jnz     loc_18000C938
0x18000c8a9  xor     edi, edi
0x18000c8ab  jmp     loc_18000C938
0x18000c8b0  test    byte ptr [r14+22h], 6
0x18000c8b5  jz      short loc_18000C8CF
0x18000c8b7  mov     rcx, [rbx+8]; Handle
0x18000c8bb  call    cs:__imp_NtClose
0x18000c8c2  nop     dword ptr [rax+rax+00h]
0x18000c8c7  mov     qword ptr [rbx+8], 0
0x18000c8cf  test    byte ptr [r14+22h], 1
0x18000c8d4  jnz     short loc_18000C8DD
0x18000c8d6  test    byte ptr [r14+22h], 2
0x18000c8db  jz      short loc_18000C938
0x18000c8dd  test    rsi, rsi
0x18000c8e0  jz      short loc_18000C91B
0x18000c8e2  mov     rcx, [rsi+38h]
0x18000c8e6  test    rcx, rcx
0x18000c8e9  jz      short loc_18000C91B
0x18000c8eb  cmp     rcx, rbx
0x18000c8ee  jnz     short loc_18000C8FA
0x18000c8f0  mov     rax, [rbx+20h]
0x18000c8f4  mov     [rsi+38h], rax
0x18000c8f8  jmp     short loc_18000C91B
0x18000c8fa  mov     rax, [rcx+20h]
0x18000c8fe  jmp     short loc_18000C90C
0x18000c900  cmp     rax, rbx
0x18000c903  jz      short loc_18000C913
0x18000c905  mov     rcx, rax
0x18000c908  mov     rax, [rax+20h]
0x18000c90c  test    rax, rax
0x18000c90f  jnz     short loc_18000C900
0x18000c911  jmp     short loc_18000C91B
0x18000c913  mov     rax, [rbx+20h]
0x18000c917  mov     [rcx+20h], rax
0x18000c91b  mov     rcx, rbx; P
0x18000c91e  call    BaseSrvFreeWOWRecord
0x18000c923  cmp     qword ptr [rsi+38h], 0
0x18000c928  jnz     short loc_18000C938
0x18000c92a  mov     rdx, rsi
0x18000c92d  call    BaseSrvDeleteSharedWowRecord
0x18000c932  mov     edi, eax
0x18000c934  test    eax, eax
0x18000c936  js      short loc_18000C999
0x18000c938  cmp     word ptr [r14+20h], 1
0x18000c93e  jnz     short loc_18000C999
0x18000c940  lea     rdx, [rbp+arg_0]
0x18000c944  lea     rcx, [rbp+var_10]
0x18000c948  call    BaseSrvCreatePairWaitHandles
0x18000c94d  mov     edi, eax
0x18000c94f  test    eax, eax
0x18000c951  js      short loc_18000C999
0x18000c953  cmp     cs:UserNotifyProcessCreate, 0
0x18000c95b  mov     rax, [rbp+var_10]
0x18000c95f  mov     [rbx+8], rax
0x18000c963  mov     rax, [rbp+arg_0]
0x18000c967  mov     [rbx+10h], rax
0x18000c96b  mov     rax, [rbp+arg_0]
0x18000c96f  mov     [r14+18h], rax
0x18000c973  jz      short loc_18000C999
0x18000c975  mov     rdx, gs:70h
0x18000c97e  mov     r9d, 4
0x18000c984  mov     r8d, dword ptr [rbp+arg_0]
0x18000c988  mov     ecx, [rbx]
0x18000c98a  mov     rax, cs:UserNotifyProcessCreate
0x18000c991  mov     edx, [rdx+30h]
0x18000c994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c999  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c9a0  call    cs:__imp_RtlLeaveCriticalSection
0x18000c9a7  nop     dword ptr [rax+rax+00h]
0x18000c9ac  mov     eax, edi
0x18000c9ae  add     rsp, 40h
0x18000c9b2  pop     r14
0x18000c9b4  pop     rdi
0x18000c9b5  pop     rsi
0x18000c9b6  pop     rbx
0x18000c9b7  pop     rbp
0x18000c9b8  retn
```
