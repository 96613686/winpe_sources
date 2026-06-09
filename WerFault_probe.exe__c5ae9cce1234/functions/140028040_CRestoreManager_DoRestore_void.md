# CRestoreManager::DoRestore(void)

- ea: `0x140028040`
- end: `0x1400280f4`
- name: `?DoRestore@CRestoreManager@@MEAAXXZ`
- size: `180`
- prototype: `void __fastcall(CRestoreManager *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140014474`
- `0x140028040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400280c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400280c9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14002807c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14002807c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002809a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002809a`

## pseudocode

```c
void __fastcall CRestoreManager::DoRestore(CRestoreManager *this)
{
  HANDLE Thread; // rax
  void *v3; // rcx
  DWORD LastError; // eax

  if ( *((_QWORD *)this + 729) == -1 || *((_QWORD *)this + 729) == 0 )
  {
    Thread = CreateThread(0, 0, CRestoreManager::static_DoRestoreThreadProc, this, 0, 0);
    v3 = (void *)*((_QWORD *)this + 729);
    *((_QWORD *)this + 729) = Thread;
    if ( (unsigned __int64)v3 + 1 > 1 )
      CloseHandle(v3);
    if ( (*((_QWORD *)this + 729) == -1 || *((_QWORD *)this + 729) == 0)
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, LastError);
    }
  }
}

```

## disassembly

```asm
0x140028040  push    rbx
0x140028042  sub     rsp, 30h
0x140028046  mov     rax, [rcx+16C8h]
0x14002804d  mov     rbx, rcx
0x140028050  inc     rax
0x140028053  cmp     rax, 1
0x140028057  ja      loc_1400280EE
0x14002805d  mov     r9, rcx; lpParameter
0x140028060  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x140028069  xor     ecx, ecx; lpThreadAttributes
0x14002806b  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140028073  lea     r8, ?static_DoRestoreThreadProc@CRestoreManager@@KAKPEAX@Z; lpStartAddress
0x14002807a  xor     edx, edx; dwStackSize
0x14002807c  call    cs:__imp_CreateThread
0x140028082  mov     rcx, [rbx+16C8h]; hObject
0x140028089  mov     [rbx+16C8h], rax
0x140028090  lea     rax, [rcx+1]
0x140028094  cmp     rax, 1
0x140028098  jbe     short loc_1400280A0
0x14002809a  call    cs:__imp_CloseHandle
0x1400280a0  mov     rax, [rbx+16C8h]
0x1400280a7  inc     rax
0x1400280aa  cmp     rax, 1
0x1400280ae  ja      short loc_1400280EE
0x1400280b0  mov     rax, cs:WPP_GLOBAL_Control
0x1400280b7  lea     rcx, WPP_GLOBAL_Control
0x1400280be  cmp     rax, rcx
0x1400280c1  jz      short loc_1400280EE
0x1400280c3  test    byte ptr [rax+1Ch], 1
0x1400280c7  jz      short loc_1400280EE
0x1400280c9  call    cs:__imp_GetLastError
0x1400280cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400280d6  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x1400280dd  mov     edx, 16h
0x1400280e2  mov     r9d, eax
0x1400280e5  mov     rcx, [rcx+10h]
0x1400280e9  call    WPP_SF_d
0x1400280ee  add     rsp, 30h
0x1400280f2  pop     rbx
0x1400280f3  retn
```
