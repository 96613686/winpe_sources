# TextVirtualizationInternal::DoReconnect(void)

- ea: `0x180013690`
- end: `0x180013750`
- name: `?DoReconnect@TextVirtualizationInternal@@UEAAJXZ`
- size: `192`
- prototype: `__int64 __fastcall(TextVirtualizationInternal *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180002240`
- `0x180007404`
- `0x1800132f0`
- `0x180013690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013711`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013711`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001371d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001371d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800136a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800136a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013730`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800136ed`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800136ed`

## pseudocode

```c
__int64 __fastcall TextVirtualizationInternal::DoReconnect(TextVirtualizationInternal *this)
{
  DWORD CurrentProcessId; // eax
  unsigned int v2; // eax
  unsigned int v3; // ebx
  char *EventW; // rdi
  WCHAR Name[8]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v7; // [rsp+30h] [rbp-38h]
  __int128 v8; // [rsp+40h] [rbp-28h]
  int v9; // [rsp+50h] [rbp-18h]
  unsigned __int64 retaddr; // [rsp+68h] [rbp+0h]

  CurrentProcessId = GetCurrentProcessId();
  v9 = 0;
  *(_OWORD *)Name = 0;
  v7 = 0;
  v8 = 0;
  v2 = StringCchPrintfW(Name, 0x1Au, L"Local\\IshShutdown%08x", CurrentProcessId);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 == -2147024882 )
      TerminateProcessOnMemoryExhaustion(0);
    FailFastWithHR(v3, retaddr, 0x23u);
  }
  EventW = (char *)CreateEventW(0, 0, 0, Name);
  SetEvent(EventW);
  if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(EventW);
  return v3;
}

```

## disassembly

```asm
0x180013690  mov     [rsp+arg_0], rbx
0x180013695  push    rdi
0x180013696  sub     rsp, 60h
0x18001369a  mov     rax, cs:__security_cookie
0x1800136a1  xor     rax, rsp
0x1800136a4  mov     [rsp+68h+var_10], rax
0x1800136a9  call    cs:__imp_GetCurrentProcessId
0x1800136af  xor     ecx, ecx
0x1800136b1  lea     r8, aLocalIshshutdo; "Local\\IshShutdown%08x"
0x1800136b8  xorps   xmm0, xmm0
0x1800136bb  mov     [rsp+68h+var_18], ecx
0x1800136bf  mov     r9d, eax
0x1800136c2  movups  xmmword ptr [rsp+68h+Name], xmm0
0x1800136c7  lea     edx, [rcx+1Ah]; unsigned __int64
0x1800136ca  lea     rcx, [rsp+68h+Name]; Buffer
0x1800136cf  movups  [rsp+68h+var_38], xmm0
0x1800136d4  movups  [rsp+68h+var_28], xmm0
0x1800136d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800136de  mov     ebx, eax
0x1800136e0  test    eax, eax
0x1800136e2  jz      short loc_180013705
0x1800136e4  cmp     eax, 8007000Eh
0x1800136e9  jnz     short loc_1800136F3
0x1800136eb  xor     ecx, ecx; FailedAllocationSize
0x1800136ed  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x1800136f3  mov     rdx, [rsp+68h]; unsigned __int64
0x1800136f8  mov     r8d, 23h ; '#'; unsigned __int64
0x1800136fe  mov     ecx, ebx; int
0x180013700  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x180013705  lea     r9, [rsp+68h+Name]; lpName
0x18001370a  xor     r8d, r8d; bInitialState
0x18001370d  xor     edx, edx; bManualReset
0x18001370f  xor     ecx, ecx; lpEventAttributes
0x180013711  call    cs:__imp_CreateEventW
0x180013717  mov     rcx, rax; hEvent
0x18001371a  mov     rdi, rax
0x18001371d  call    cs:__imp_SetEvent
0x180013723  lea     rcx, [rdi-1]
0x180013727  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001372b  ja      short loc_180013736
0x18001372d  mov     rcx, rdi; hObject
0x180013730  call    cs:__imp_CloseHandle
0x180013736  mov     eax, ebx
0x180013738  mov     rcx, [rsp+68h+var_10]
0x18001373d  xor     rcx, rsp; StackCookie
0x180013740  call    __security_check_cookie
0x180013745  mov     rbx, [rsp+68h+arg_0]
0x18001374a  add     rsp, 60h
0x18001374e  pop     rdi
0x18001374f  retn
```
