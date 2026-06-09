# IncThreadCount(char const *,ulong)

- ea: `0x180013138`
- end: `0x1800131b5`
- name: `?IncThreadCount@@YAXPEBDK@Z`
- size: `125`
- prototype: `void __fastcall(const char *, char, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011284`
- `0x180011c90`
- `0x180011fa0`
- `0x180012b90`
- `0x180012de0`

## callees

- `0x180013138`
- `0x180013640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001316c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001316c`

## pseudocode

```c
void __fastcall IncThreadCount(const char *a1, char a2, int a3)
{
  signed __int32 v5; // ebx

  v5 = _InterlockedIncrement((volatile signed __int32 *)&g_cThreads);
  if ( v5 == 1 && g_ThreadsCompletedEvent )
    ResetEvent(g_ThreadsCompletedEvent);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, a3, v5, (__int64)a1, a2);
}

```

## disassembly

```asm
0x180013138  mov     [rsp+arg_0], rbx
0x18001313d  mov     [rsp+arg_8], rsi
0x180013142  push    rdi
0x180013143  sub     rsp, 30h
0x180013147  mov     edi, edx
0x180013149  mov     rsi, rcx
0x18001314c  mov     ebx, 1
0x180013151  lock xadd cs:?g_cThreads@@3KA, ebx; ulong g_cThreads
0x180013159  inc     ebx
0x18001315b  cmp     ebx, 1
0x18001315e  jnz     short loc_180013172
0x180013160  mov     rcx, cs:?g_ThreadsCompletedEvent@@3PEAXEA; hEvent
0x180013167  test    rcx, rcx
0x18001316a  jz      short loc_180013172
0x18001316c  call    cs:__imp_ResetEvent
0x180013172  mov     rcx, cs:WPP_GLOBAL_Control
0x180013179  lea     rax, WPP_GLOBAL_Control
0x180013180  cmp     rcx, rax
0x180013183  jz      short loc_1800131A5
0x180013185  test    byte ptr [rcx+1Ch], 8
0x180013189  jz      short loc_1800131A5
0x18001318b  mov     rcx, [rcx+10h]
0x18001318f  mov     edx, 0Eh
0x180013194  mov     [rsp+38h+var_10], edi
0x180013198  mov     r9d, ebx
0x18001319b  mov     [rsp+38h+var_18], rsi
0x1800131a0  call    WPP_SF_dsd
0x1800131a5  mov     rbx, [rsp+38h+arg_0]
0x1800131aa  mov     rsi, [rsp+38h+arg_8]
0x1800131af  add     rsp, 30h
0x1800131b3  pop     rdi
0x1800131b4  retn
```
