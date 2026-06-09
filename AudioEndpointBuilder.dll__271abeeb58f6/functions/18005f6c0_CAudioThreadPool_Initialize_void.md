# CAudioThreadPool::Initialize(void)

- ea: `0x18005f6c0`
- end: `0x18005f756`
- name: `?Initialize@CAudioThreadPool@@QEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(CAudioThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005f75c`

## callees

- `0x180029024`
- `0x18005f6c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f6ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f6ed`
- `ntdll!RtlDllShutdownInProgress` at `0x18005f6cd`
- `ntdll!RtlDllShutdownInProgress` at `0x18005f6cd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18005f6de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18005f6de`

## pseudocode

```c
__int64 __fastcall CAudioThreadPool::Initialize(CAudioThreadPool *this)
{
  unsigned int v2; // ebx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int LastError; // eax

  if ( RtlDllShutdownInProgress() )
  {
    v2 = -2147023781;
LABEL_7:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_59645097987a3a1d89299ed4bf796b10_Traceguids);
    }
    return v2;
  }
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 10) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    v2 = 0;
    *((_QWORD *)this + 3) = ThreadpoolCleanupGroup;
    *((_QWORD *)this + 4) = 0;
    return v2;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( (v2 & 0x80000000) != 0 )
    goto LABEL_7;
  return v2;
}

```

## disassembly

```asm
0x18005f6c0  mov     [rsp+arg_0], rbx
0x18005f6c5  push    rdi
0x18005f6c6  sub     rsp, 20h
0x18005f6ca  mov     rdi, rcx
0x18005f6cd  call    cs:__imp_RtlDllShutdownInProgress
0x18005f6d3  test    al, al
0x18005f6d5  jz      short loc_18005F6DE
0x18005f6d7  mov     ebx, 8007045Bh
0x18005f6dc  jmp     short loc_18005F706
0x18005f6de  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18005f6e4  mov     [rdi+50h], rax
0x18005f6e8  test    rax, rax
0x18005f6eb  jnz     short loc_18005F73F
0x18005f6ed  call    cs:__imp_GetLastError
0x18005f6f3  mov     ebx, eax
0x18005f6f5  test    eax, eax
0x18005f6f7  jle     short loc_18005F702
0x18005f6f9  movzx   ebx, ax
0x18005f6fc  or      ebx, 80070000h
0x18005f702  test    ebx, ebx
0x18005f704  jns     short loc_18005F749
0x18005f706  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f70d  lea     rax, WPP_GLOBAL_Control
0x18005f714  cmp     rcx, rax
0x18005f717  jz      short loc_18005F749
0x18005f719  test    byte ptr [rcx+1Ch], 4
0x18005f71d  jz      short loc_18005F749
0x18005f71f  cmp     byte ptr [rcx+19h], 2
0x18005f723  jb      short loc_18005F749
0x18005f725  mov     rcx, [rcx+10h]
0x18005f729  lea     r8, WPP_59645097987a3a1d89299ed4bf796b10_Traceguids
0x18005f730  mov     edx, 0Ah
0x18005f735  mov     r9d, ebx
0x18005f738  call    WPP_SF_d
0x18005f73d  jmp     short loc_18005F749
0x18005f73f  xor     ebx, ebx
0x18005f741  mov     [rdi+18h], rax
0x18005f745  mov     [rdi+20h], rbx
0x18005f749  mov     eax, ebx
0x18005f74b  mov     rbx, [rsp+28h+arg_0]
0x18005f750  add     rsp, 20h
0x18005f754  pop     rdi
0x18005f755  retn
```
