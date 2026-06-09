# BaseSrvAddWowTask

- ea: `0x1800086cc`
- end: `0x1800087aa`
- name: `BaseSrvAddWowTask`
- size: `222`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18000abe0`

## callees

- `0x180008394`
- `0x180008528`
- `0x1800086cc`
- `0x18000abb4`
- `0x18000b400`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800086fa`
- `ntdll!RtlEnterCriticalSection` at `0x18000874e`
- `ntdll!RtlEnterCriticalSection` at `0x1800086fa`
- `ntdll!RtlEnterCriticalSection` at `0x18000874e`
- `ntdll!RtlLeaveCriticalSection` at `0x180008733`
- `ntdll!RtlLeaveCriticalSection` at `0x18000878e`
- `ntdll!RtlLeaveCriticalSection` at `0x180008733`
- `ntdll!RtlLeaveCriticalSection` at `0x18000878e`

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
      SharedWowRecordByPid = BaseSrvAddSharedWowTask(v3);
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
0x1800086cc  mov     [rsp+arg_8], rbx
0x1800086d1  push    rbp
0x1800086d2  push    rsi
0x1800086d3  push    rdi
0x1800086d4  sub     rsp, 20h
0x1800086d8  mov     ebp, [rcx+8]
0x1800086db  lea     rsi, [rcx+40h]
0x1800086df  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x1800086e6  mov     [rsp+38h+arg_0], 0
0x1800086ef  mov     edi, edx
0x1800086f1  mov     [rsp+38h+arg_10], 0
0x1800086fa  call    cs:__imp_RtlEnterCriticalSection
0x180008701  nop     dword ptr [rax+rax+00h]
0x180008706  lea     rdx, [rsp+38h+arg_0]
0x18000870b  mov     ecx, ebp
0x18000870d  call    BaseSrvGetConsoleRecordByPid
0x180008712  mov     ebx, eax
0x180008714  test    eax, eax
0x180008716  js      short loc_18000872C
0x180008718  mov     rdx, [rsp+38h+arg_0]
0x18000871d  cmp     [rdx+2Ch], edi
0x180008720  jnz     short loc_180008782
0x180008722  mov     rcx, rsi
0x180008725  call    BaseSrvAddSepWowTask
0x18000872a  mov     ebx, eax
0x18000872c  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180008733  call    cs:__imp_RtlLeaveCriticalSection
0x18000873a  nop     dword ptr [rax+rax+00h]
0x18000873f  test    ebx, ebx
0x180008741  js      short loc_180008747
0x180008743  xor     eax, eax
0x180008745  jmp     short loc_18000879C
0x180008747  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000874e  call    cs:__imp_RtlEnterCriticalSection
0x180008755  nop     dword ptr [rax+rax+00h]
0x18000875a  lea     rdx, [rsp+38h+arg_10]
0x18000875f  mov     ecx, ebp
0x180008761  call    BaseSrvGetSharedWowRecordByPid
0x180008766  mov     ebx, eax
0x180008768  test    eax, eax
0x18000876a  js      short loc_180008787
0x18000876c  mov     rdx, [rsp+38h+arg_10]
0x180008771  cmp     [rdx+50h], edi
0x180008774  jnz     short loc_180008782
0x180008776  mov     rcx, rsi
0x180008779  call    BaseSrvAddSharedWowTask
0x18000877e  mov     ebx, eax
0x180008780  jmp     short loc_180008787
0x180008782  mov     ebx, 0C000000Dh
0x180008787  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000878e  call    cs:__imp_RtlLeaveCriticalSection
0x180008795  nop     dword ptr [rax+rax+00h]
0x18000879a  mov     eax, ebx
0x18000879c  mov     rbx, [rsp+38h+arg_8]
0x1800087a1  add     rsp, 20h
0x1800087a5  pop     rdi
0x1800087a6  pop     rsi
0x1800087a7  pop     rbp
0x1800087a8  retn
```
