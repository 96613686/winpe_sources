# CDesktopManager::PostEventMessage(uint,unsigned __int64,__int64)

- ea: `0x1800926e0`
- end: `0x180092797`
- name: `?PostEventMessage@CDesktopManager@@QEAAJI_K_J@Z`
- size: `183`
- prototype: `int(CDesktopManager *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800b0410`
- `0x1800b04a8`

## callees

- `0x18001f43c`
- `0x1800926e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092758`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180092731`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180092731`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18009273e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18009273e`
- `USER32!PostThreadMessageW` at `0x18009274e`
- `USER32!PostThreadMessageW` at `0x18009274e`

## pseudocode

```c
__int64 __fastcall CDesktopManager::PostEventMessage(HANDLE *this, UINT a2, WPARAM a3, LPARAM a4)
{
  signed int v8; // ebx
  DWORD ThreadId; // eax
  signed int LastError; // eax
  unsigned int v12; // [rsp+20h] [rbp-38h]

  if ( this[142] )
  {
    SetLastError(0);
    ThreadId = GetThreadId(this[142]);
    if ( PostThreadMessageW(ThreadId, a2, a3, a4) )
      return 0;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v12 = 2641;
    if ( v8 >= 0 )
      v8 = -2003304445;
  }
  else
  {
    v8 = -2147467259;
    v12 = 2638;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1800F74CC, 1u, v8, v12, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800926e0  push    rbx
0x1800926e2  push    rbp
0x1800926e3  push    rsi
0x1800926e4  push    rdi
0x1800926e5  sub     rsp, 38h
0x1800926e9  cmp     qword ptr [rcx+470h], 0
0x1800926f1  mov     rdi, r9
0x1800926f4  mov     rsi, r8
0x1800926f7  mov     ebp, edx
0x1800926f9  mov     rbx, rcx
0x1800926fc  jnz     short loc_18009272F
0x1800926fe  mov     [rsp+58h+var_30], 0; void *
0x180092707  mov     ebx, 80004005h
0x18009270c  mov     [rsp+58h+var_38], 0A4Eh; unsigned int
0x180092714  mov     r8d, 1; unsigned int
0x18009271a  lea     rdx, dword_1800F74CC; int *
0x180092721  mov     r9d, ebx; int
0x180092724  lea     ecx, [r8+13h]; unsigned int
0x180092728  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18009272d  jmp     short loc_18009278C
0x18009272f  xor     ecx, ecx; dwErrCode
0x180092731  call    cs:__imp_SetLastError
0x180092737  mov     rcx, [rbx+470h]; Thread
0x18009273e  call    cs:__imp_GetThreadId
0x180092744  mov     r9, rdi; lParam
0x180092747  mov     r8, rsi; wParam
0x18009274a  mov     ecx, eax; idThread
0x18009274c  mov     edx, ebp; Msg
0x18009274e  call    cs:__imp_PostThreadMessageW
0x180092754  test    eax, eax
0x180092756  jnz     short loc_18009278A
0x180092758  call    cs:__imp_GetLastError
0x18009275e  mov     ebx, eax
0x180092760  test    eax, eax
0x180092762  jle     short loc_18009276D
0x180092764  movzx   ebx, ax
0x180092767  or      ebx, 80070000h
0x18009276d  test    ebx, ebx
0x18009276f  mov     [rsp+58h+var_30], 0
0x180092778  mov     eax, 88980003h
0x18009277d  mov     [rsp+58h+var_38], 0A51h
0x180092785  cmovns  ebx, eax
0x180092788  jmp     short loc_180092714
0x18009278a  xor     ebx, ebx
0x18009278c  mov     eax, ebx
0x18009278e  add     rsp, 38h
0x180092792  pop     rdi
0x180092793  pop     rsi
0x180092794  pop     rbp
0x180092795  pop     rbx
0x180092796  retn
```
