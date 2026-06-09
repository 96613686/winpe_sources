# DecThreadCount(char const *,ulong)

- ea: `0x1800130b8`
- end: `0x180013131`
- name: `?DecThreadCount@@YAXPEBDK@Z`
- size: `121`
- prototype: `void __fastcall(const char *, char, int)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a1c0`
- `0x18000bc10`
- `0x18000be70`
- `0x18000c850`
- `0x18000e038`
- `0x180011284`
- `0x180011750`
- `0x180011c90`
- `0x180011fa0`
- `0x180012110`
- `0x1800123a0`
- `0x180012a40`
- `0x180012b90`
- `0x180012de0`

## callees

- `0x1800130b8`
- `0x180013640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800130e8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800130e8`

## pseudocode

```c
void __fastcall DecThreadCount(const char *a1, char a2, int a3)
{
  signed __int32 v5; // ebx

  v5 = _InterlockedDecrement((volatile signed __int32 *)&g_cThreads);
  if ( !v5 && g_ThreadsCompletedEvent )
    SetEvent(g_ThreadsCompletedEvent);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, a3, v5, (__int64)a1, a2);
}

```

## disassembly

```asm
0x1800130b8  mov     [rsp+arg_0], rbx
0x1800130bd  mov     [rsp+arg_8], rsi
0x1800130c2  push    rdi
0x1800130c3  sub     rsp, 30h
0x1800130c7  mov     edi, edx
0x1800130c9  mov     rsi, rcx
0x1800130cc  or      ebx, 0FFFFFFFFh
0x1800130cf  lock xadd cs:?g_cThreads@@3KA, ebx; ulong g_cThreads
0x1800130d7  sub     ebx, 1
0x1800130da  jnz     short loc_1800130EE
0x1800130dc  mov     rcx, cs:?g_ThreadsCompletedEvent@@3PEAXEA; hEvent
0x1800130e3  test    rcx, rcx
0x1800130e6  jz      short loc_1800130EE
0x1800130e8  call    cs:__imp_SetEvent
0x1800130ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130f5  lea     rax, WPP_GLOBAL_Control
0x1800130fc  cmp     rcx, rax
0x1800130ff  jz      short loc_180013121
0x180013101  test    byte ptr [rcx+1Ch], 8
0x180013105  jz      short loc_180013121
0x180013107  mov     rcx, [rcx+10h]
0x18001310b  mov     edx, 0Fh
0x180013110  mov     [rsp+38h+var_10], edi
0x180013114  mov     r9d, ebx
0x180013117  mov     [rsp+38h+var_18], rsi
0x18001311c  call    WPP_SF_dsd
0x180013121  mov     rbx, [rsp+38h+arg_0]
0x180013126  mov     rsi, [rsp+38h+arg_8]
0x18001312b  add     rsp, 30h
0x18001312f  pop     rdi
0x180013130  retn
```
