# BaseSrvAddWowTask

- ea: `0x1800083dc`
- end: `0x1800084b4`
- name: `BaseSrvAddWowTask`
- size: `216`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18000a960`

## callees

- `0x18000806c`
- `0x18000821c`
- `0x1800083dc`
- `0x18000a92c`
- `0x18000b160`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180008404`
- `ntdll!RtlEnterCriticalSection` at `0x180008458`
- `ntdll!RtlEnterCriticalSection` at `0x180008404`
- `ntdll!RtlEnterCriticalSection` at `0x180008458`
- `ntdll!RtlLeaveCriticalSection` at `0x18000843d`
- `ntdll!RtlLeaveCriticalSection` at `0x180008498`
- `ntdll!RtlLeaveCriticalSection` at `0x18000843d`
- `ntdll!RtlLeaveCriticalSection` at `0x180008498`

## pseudocode

```c
__int64 __fastcall BaseSrvAddWowTask(__int64 a1, int a2)
{
  unsigned int v2; // ebp
  __int64 v3; // rsi
  int ConsoleRecordByPid; // ebx
  int SharedWowRecordByPid; // ebx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v2 = *(_DWORD *)(a1 + 8);
  v3 = a1 + 64;
  v8 = 0;
  v9 = 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  ConsoleRecordByPid = BaseSrvGetConsoleRecordByPid(v2, &v8);
  if ( ConsoleRecordByPid >= 0 )
  {
    if ( *(_DWORD *)(v8 + 44) != a2 )
      goto LABEL_9;
    ConsoleRecordByPid = BaseSrvAddSepWowTask(v3, v8);
  }
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  if ( ConsoleRecordByPid >= 0 )
    return 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  SharedWowRecordByPid = BaseSrvGetSharedWowRecordByPid(v2, &v9);
  if ( SharedWowRecordByPid >= 0 )
  {
    if ( *(_DWORD *)(v9 + 80) == a2 )
    {
      SharedWowRecordByPid = BaseSrvAddSharedWowTask(v3, v9);
      goto LABEL_10;
    }
LABEL_9:
    SharedWowRecordByPid = -1073741811;
  }
LABEL_10:
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return (unsigned int)SharedWowRecordByPid;
}

```

## disassembly

```asm
0x1800083dc  mov     [rsp+arg_8], rbx
0x1800083e1  push    rbp
0x1800083e2  push    rsi
0x1800083e3  push    rdi
0x1800083e4  sub     rsp, 20h
0x1800083e8  mov     ebp, [rcx+8]
0x1800083eb  lea     rsi, [rcx+40h]
0x1800083ef  and     [rsp+38h+arg_0], 0
0x1800083f5  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x1800083fc  and     [rsp+38h+arg_10], 0
0x180008402  mov     edi, edx
0x180008404  call    cs:__imp_RtlEnterCriticalSection
0x18000840b  nop     dword ptr [rax+rax+00h]
0x180008410  lea     rdx, [rsp+38h+arg_0]
0x180008415  mov     ecx, ebp
0x180008417  call    BaseSrvGetConsoleRecordByPid
0x18000841c  mov     ebx, eax
0x18000841e  test    eax, eax
0x180008420  js      short loc_180008436
0x180008422  mov     rdx, [rsp+38h+arg_0]
0x180008427  cmp     [rdx+2Ch], edi
0x18000842a  jnz     short loc_18000848C
0x18000842c  mov     rcx, rsi
0x18000842f  call    BaseSrvAddSepWowTask
0x180008434  mov     ebx, eax
0x180008436  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000843d  call    cs:__imp_RtlLeaveCriticalSection
0x180008444  nop     dword ptr [rax+rax+00h]
0x180008449  test    ebx, ebx
0x18000844b  js      short loc_180008451
0x18000844d  xor     eax, eax
0x18000844f  jmp     short loc_1800084A6
0x180008451  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180008458  call    cs:__imp_RtlEnterCriticalSection
0x18000845f  nop     dword ptr [rax+rax+00h]
0x180008464  lea     rdx, [rsp+38h+arg_10]
0x180008469  mov     ecx, ebp
0x18000846b  call    BaseSrvGetSharedWowRecordByPid
0x180008470  mov     ebx, eax
0x180008472  test    eax, eax
0x180008474  js      short loc_180008491
0x180008476  mov     rdx, [rsp+38h+arg_10]
0x18000847b  cmp     [rdx+50h], edi
0x18000847e  jnz     short loc_18000848C
0x180008480  mov     rcx, rsi
0x180008483  call    BaseSrvAddSharedWowTask
0x180008488  mov     ebx, eax
0x18000848a  jmp     short loc_180008491
0x18000848c  mov     ebx, 0C000000Dh
0x180008491  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180008498  call    cs:__imp_RtlLeaveCriticalSection
0x18000849f  nop     dword ptr [rax+rax+00h]
0x1800084a4  mov     eax, ebx
0x1800084a6  mov     rbx, [rsp+38h+arg_8]
0x1800084ab  add     rsp, 20h
0x1800084af  pop     rdi
0x1800084b0  pop     rsi
0x1800084b1  pop     rbp
0x1800084b2  retn
```
