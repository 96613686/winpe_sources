# CRestoreManager::DoRestore(void)

- ea: `0x140029ae0`
- end: `0x140029ba7`
- name: `?DoRestore@CRestoreManager@@MEAAXXZ`
- size: `199`
- prototype: `void __fastcall(CRestoreManager *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140014f14`
- `0x140029ae0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029b75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029b75`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140029b1c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140029b1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029b40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029b40`

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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, LastError);
    }
  }
}

```

## disassembly

```asm
0x140029ae0  push    rbx
0x140029ae2  sub     rsp, 30h
0x140029ae6  mov     rax, [rcx+16C8h]
0x140029aed  mov     rbx, rcx
0x140029af0  inc     rax
0x140029af3  cmp     rax, 1
0x140029af7  ja      loc_140029BA0
0x140029afd  mov     r9, rcx; lpParameter
0x140029b00  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x140029b09  xor     ecx, ecx; lpThreadAttributes
0x140029b0b  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140029b13  lea     r8, ?static_DoRestoreThreadProc@CRestoreManager@@KAKPEAX@Z; lpStartAddress
0x140029b1a  xor     edx, edx; dwStackSize
0x140029b1c  call    cs:__imp_CreateThread
0x140029b23  nop     dword ptr [rax+rax+00h]
0x140029b28  mov     rcx, [rbx+16C8h]; hObject
0x140029b2f  mov     [rbx+16C8h], rax
0x140029b36  lea     rax, [rcx+1]
0x140029b3a  cmp     rax, 1
0x140029b3e  jbe     short loc_140029B4C
0x140029b40  call    cs:__imp_CloseHandle
0x140029b47  nop     dword ptr [rax+rax+00h]
0x140029b4c  mov     rax, [rbx+16C8h]
0x140029b53  inc     rax
0x140029b56  cmp     rax, 1
0x140029b5a  ja      short loc_140029BA0
0x140029b5c  mov     rax, cs:WPP_GLOBAL_Control
0x140029b63  lea     rcx, WPP_GLOBAL_Control
0x140029b6a  cmp     rax, rcx
0x140029b6d  jz      short loc_140029BA0
0x140029b6f  test    byte ptr [rax+1Ch], 1
0x140029b73  jz      short loc_140029BA0
0x140029b75  call    cs:__imp_GetLastError
0x140029b7c  nop     dword ptr [rax+rax+00h]
0x140029b81  mov     rcx, cs:WPP_GLOBAL_Control
0x140029b88  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x140029b8f  mov     edx, 16h
0x140029b94  mov     r9d, eax
0x140029b97  mov     rcx, [rcx+10h]
0x140029b9b  call    WPP_SF_d
0x140029ba0  add     rsp, 30h
0x140029ba4  pop     rbx
0x140029ba5  retn
```
