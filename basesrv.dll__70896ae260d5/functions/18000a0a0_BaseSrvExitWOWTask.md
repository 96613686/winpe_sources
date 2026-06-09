# BaseSrvExitWOWTask

- ea: `0x18000a0a0`
- end: `0x18000a197`
- name: `BaseSrvExitWOWTask`
- size: `247`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180009fc0`

## callees

- `0x180009730`
- `0x18000a0a0`
- `0x18000a4e0`
- `0x18000a894`

## import_xrefs

- `ntdll!NtClose` at `0x18000a14f`
- `ntdll!NtClose` at `0x18000a14f`
- `ntdll!RtlEnterCriticalSection` at `0x18000a0c1`
- `ntdll!RtlEnterCriticalSection` at `0x18000a0c1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a178`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a178`
- `ntdll!NtSetEvent` at `0x18000a13f`
- `ntdll!NtSetEvent` at `0x18000a13f`

## pseudocode

```c
__int64 __fastcall BaseSrvExitWOWTask(__int64 a1, int a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  int SharedWowRecordByConsoleHandle; // ebx
  int v7; // edx
  HANDLE *v8; // rbx
  HANDLE *v9; // rcx
  HANDLE v10; // rdx
  HANDLE v11; // rcx
  __int64 v13; // [rsp+30h] [rbp+8h] BYREF

  v13 = 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  SharedWowRecordByConsoleHandle = BaseSrvFindSharedWowRecordByConsoleHandle(v4, *(_QWORD *)a1, &v13);
  if ( SharedWowRecordByConsoleHandle >= 0 )
  {
    if ( a2 == *(_DWORD *)(v13 + 80) )
    {
      v7 = *(_DWORD *)(a1 + 8);
      if ( v7 == -1 )
      {
        SharedWowRecordByConsoleHandle = BaseSrvDeleteSharedWowRecord(v5, v13);
      }
      else
      {
        v8 = *(HANDLE **)(v13 + 56);
        v9 = 0;
        while ( 1 )
        {
          if ( !v8 )
          {
            SharedWowRecordByConsoleHandle = -1073741275;
            goto LABEL_17;
          }
          if ( *(_DWORD *)v8 == v7 )
            break;
          v9 = v8;
          v8 = (HANDLE *)v8[4];
        }
        v10 = v8[4];
        if ( v9 )
          v9[4] = v10;
        else
          *(_QWORD *)(v13 + 56) = v10;
        v11 = v8[1];
        if ( v11 )
        {
          NtSetEvent(v11, 0);
          NtClose(v8[1]);
          v8[1] = 0;
        }
        BaseSrvFreeWOWRecord(v8);
        SharedWowRecordByConsoleHandle = 0;
      }
    }
    else
    {
      SharedWowRecordByConsoleHandle = -1073741811;
    }
  }
LABEL_17:
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return (unsigned int)SharedWowRecordByConsoleHandle;
}

```

## disassembly

```asm
0x18000a0a0  mov     [rsp+arg_8], rbx
0x18000a0a5  mov     [rsp+arg_10], rsi
0x18000a0aa  push    rdi
0x18000a0ab  sub     rsp, 20h
0x18000a0af  and     [rsp+28h+arg_0], 0
0x18000a0b5  mov     rdi, rcx
0x18000a0b8  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a0bf  mov     esi, edx
0x18000a0c1  call    cs:__imp_RtlEnterCriticalSection
0x18000a0c8  nop     dword ptr [rax+rax+00h]
0x18000a0cd  mov     rdx, [rdi]
0x18000a0d0  lea     r8, [rsp+28h+arg_0]
0x18000a0d5  call    BaseSrvFindSharedWowRecordByConsoleHandle
0x18000a0da  mov     ebx, eax
0x18000a0dc  test    eax, eax
0x18000a0de  js      loc_18000A171
0x18000a0e4  mov     rax, [rsp+28h+arg_0]
0x18000a0e9  cmp     esi, [rax+50h]
0x18000a0ec  jz      short loc_18000A0F5
0x18000a0ee  mov     ebx, 0C000000Dh
0x18000a0f3  jmp     short loc_18000A171
0x18000a0f5  mov     edx, [rdi+8]
0x18000a0f8  cmp     edx, 0FFFFFFFFh
0x18000a0fb  jnz     short loc_18000A109
0x18000a0fd  mov     rdx, rax
0x18000a100  call    BaseSrvDeleteSharedWowRecord
0x18000a105  mov     ebx, eax
0x18000a107  jmp     short loc_18000A171
0x18000a109  mov     rbx, [rax+38h]
0x18000a10d  xor     ecx, ecx
0x18000a10f  test    rbx, rbx
0x18000a112  jz      short loc_18000A16C
0x18000a114  cmp     [rbx], edx
0x18000a116  jz      short loc_18000A121
0x18000a118  mov     rcx, rbx
0x18000a11b  mov     rbx, [rbx+20h]
0x18000a11f  jmp     short loc_18000A10F
0x18000a121  mov     rdx, [rbx+20h]
0x18000a125  test    rcx, rcx
0x18000a128  jnz     short loc_18000A130
0x18000a12a  mov     [rax+38h], rdx
0x18000a12e  jmp     short loc_18000A134
0x18000a130  mov     [rcx+20h], rdx
0x18000a134  mov     rcx, [rbx+8]; EventHandle
0x18000a138  test    rcx, rcx
0x18000a13b  jz      short loc_18000A160
0x18000a13d  xor     edx, edx; PreviousState
0x18000a13f  call    cs:__imp_NtSetEvent
0x18000a146  nop     dword ptr [rax+rax+00h]
0x18000a14b  mov     rcx, [rbx+8]; Handle
0x18000a14f  call    cs:__imp_NtClose
0x18000a156  nop     dword ptr [rax+rax+00h]
0x18000a15b  and     qword ptr [rbx+8], 0
0x18000a160  mov     rcx, rbx; P
0x18000a163  call    BaseSrvFreeWOWRecord
0x18000a168  xor     ebx, ebx
0x18000a16a  jmp     short loc_18000A171
0x18000a16c  mov     ebx, 0C0000225h
0x18000a171  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a178  call    cs:__imp_RtlLeaveCriticalSection
0x18000a17f  nop     dword ptr [rax+rax+00h]
0x18000a184  mov     rsi, [rsp+28h+arg_10]
0x18000a189  mov     eax, ebx
0x18000a18b  mov     rbx, [rsp+28h+arg_8]
0x18000a190  add     rsp, 20h
0x18000a194  pop     rdi
0x18000a195  retn
```
