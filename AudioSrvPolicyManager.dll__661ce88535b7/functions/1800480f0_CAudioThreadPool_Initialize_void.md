# CAudioThreadPool::Initialize(void)

- ea: `0x1800480f0`
- end: `0x18004817a`
- name: `?Initialize@CAudioThreadPool@@QEAAJXZ`
- size: `138`
- prototype: `__int64 __fastcall(CAudioThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180048180`

## callees

- `0x1800480f0`
- `0x180048274`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004811d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004811d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18004810e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18004810e`
- `ntdll!RtlDllShutdownInProgress` at `0x1800480fd`
- `ntdll!RtlDllShutdownInProgress` at `0x1800480fd`

## pseudocode

```c
__int64 __fastcall CAudioThreadPool::Initialize(CAudioThreadPool *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  unsigned int v4; // ebx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int LastError; // eax

  if ( RtlDllShutdownInProgress() )
  {
    v4 = -2147023781;
LABEL_7:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v3, v4);
    }
    return v4;
  }
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 10) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    v4 = 0;
    *((_QWORD *)this + 3) = ThreadpoolCleanupGroup;
    *((_QWORD *)this + 4) = 0;
    return v4;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_7;
  return v4;
}

```

## disassembly

```asm
0x1800480f0  mov     [rsp+arg_0], rbx
0x1800480f5  push    rdi
0x1800480f6  sub     rsp, 20h
0x1800480fa  mov     rdi, rcx
0x1800480fd  call    cs:__imp_RtlDllShutdownInProgress
0x180048103  test    al, al
0x180048105  jz      short loc_18004810E
0x180048107  mov     ebx, 8007045Bh
0x18004810c  jmp     short loc_180048136
0x18004810e  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180048114  mov     [rdi+50h], rax
0x180048118  test    rax, rax
0x18004811b  jnz     short loc_180048163
0x18004811d  call    cs:__imp_GetLastError
0x180048123  mov     ebx, eax
0x180048125  test    eax, eax
0x180048127  jle     short loc_180048132
0x180048129  movzx   ebx, ax
0x18004812c  or      ebx, 80070000h
0x180048132  test    ebx, ebx
0x180048134  jns     short loc_18004816D
0x180048136  mov     rcx, cs:WPP_GLOBAL_Control
0x18004813d  lea     rax, WPP_GLOBAL_Control
0x180048144  cmp     rcx, rax
0x180048147  jz      short loc_18004816D
0x180048149  test    byte ptr [rcx+1Ch], 4
0x18004814d  jz      short loc_18004816D
0x18004814f  cmp     byte ptr [rcx+19h], 2
0x180048153  jb      short loc_18004816D
0x180048155  mov     rcx, [rcx+10h]
0x180048159  mov     r9d, ebx
0x18004815c  call    WPP_SF_d
0x180048161  jmp     short loc_18004816D
0x180048163  xor     ebx, ebx
0x180048165  mov     [rdi+18h], rax
0x180048169  mov     [rdi+20h], rbx
0x18004816d  mov     eax, ebx
0x18004816f  mov     rbx, [rsp+28h+arg_0]
0x180048174  add     rsp, 20h
0x180048178  pop     rdi
0x180048179  retn
```
