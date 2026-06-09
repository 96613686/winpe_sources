# CWinThread::CreateThread(ulong,uint,_SECURITY_ATTRIBUTES *)

- ea: `0x180070c80`
- end: `0x180070ddd`
- name: `?CreateThread@CWinThread@@QEAAHKIPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `349`
- prototype: `int(CWinThread *__hidden this, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180070b20`
- `0x180070be0`

## callees

- `0x180011480`
- `0x18002da20`
- `0x180070c80`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180070d30`
- `msvcrt!_beginthreadex` at `0x180070d30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070d6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070d97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070db8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070dca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070d6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070d97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070db8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070dca`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180070d7b`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180070d7b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180070d52`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180070d52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070d61`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070d8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070d61`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070d8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180070cd4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180070cea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180070cd4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180070cea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180070dab`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180070dab`

## pseudocode

```c
__int64 __fastcall CWinThread::CreateThread(CWinThread *this, int a2, unsigned int a3, struct _SECURITY_ATTRIBUTES *a4)
{
  HANDLE EventW; // rax
  void *v9; // rax
  HANDLE v10; // rcx
  _QWORD ArgList[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v13; // [rsp+40h] [rbp-30h]
  HANDLE hObject[2]; // [rsp+50h] [rbp-20h]
  __int64 v15; // [rsp+60h] [rbp-10h]

  if ( *((_QWORD *)this + 11) )
    AfxThrowInvalidArgException();
  v15 = 0;
  v13 = 0;
  ArgList[0] = CThreadLocal<_AFX_THREAD_STATE>::GetData();
  ArgList[1] = this;
  hObject[0] = CreateEventW(0, 1, 0, 0);
  EventW = CreateEventW(0, 1, 0, 0);
  hObject[1] = EventW;
  LODWORD(v13) = a2;
  if ( hObject[0] )
  {
    if ( EventW )
    {
      v9 = (void *)_beginthreadex(a4, a3, _AfxThreadEntry, ArgList, a2 | 4u, (unsigned int *)this + 24);
      *((_QWORD *)this + 11) = v9;
      if ( v9 )
      {
        ResumeThread(v9);
        WaitForSingleObject(hObject[0], 0xFFFFFFFF);
        CloseHandle(hObject[0]);
        if ( (a2 & 4) != 0 )
          SuspendThread(*((HANDLE *)this + 11));
        if ( !(_DWORD)v15 )
        {
          SetEvent(hObject[1]);
          return 1;
        }
        WaitForSingleObject(*((HANDLE *)this + 11), 0xFFFFFFFF);
        CloseHandle(*((HANDLE *)this + 11));
        *((_QWORD *)this + 11) = 0;
      }
      else
      {
        CloseHandle(hObject[0]);
      }
      v10 = hObject[1];
      goto LABEL_16;
    }
    CloseHandle(hObject[0]);
    EventW = hObject[1];
  }
  if ( EventW )
  {
    v10 = EventW;
LABEL_16:
    CloseHandle(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180070c80  push    rbp
0x180070c82  push    rbx
0x180070c83  push    rsi
0x180070c84  push    rdi
0x180070c85  push    r14
0x180070c87  mov     rbp, rsp
0x180070c8a  sub     rsp, 70h
0x180070c8e  cmp     qword ptr [rcx+58h], 0
0x180070c93  mov     rsi, r9
0x180070c96  mov     r14d, r8d
0x180070c99  mov     edi, edx
0x180070c9b  mov     rbx, rcx
0x180070c9e  jz      short loc_180070CA6
0x180070ca0  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180070ca6  xorps   xmm0, xmm0
0x180070ca9  xor     eax, eax
0x180070cab  movups  [rbp+ArgList], xmm0
0x180070caf  mov     [rbp+var_10], rax
0x180070cb3  movups  [rbp+var_30], xmm0
0x180070cb7  movups  xmmword ptr [rbp+hObject], xmm0
0x180070cbb  call    ?GetData@?$CThreadLocal@V_AFX_THREAD_STATE@@@@QEAAPEAV_AFX_THREAD_STATE@@XZ; CThreadLocal<_AFX_THREAD_STATE>::GetData(void)
0x180070cc0  xor     r9d, r9d; lpName
0x180070cc3  mov     qword ptr [rbp+ArgList], rax
0x180070cc7  xor     r8d, r8d; bInitialState
0x180070cca  mov     qword ptr [rbp+ArgList+8], rbx
0x180070cce  xor     ecx, ecx; lpEventAttributes
0x180070cd0  lea     edx, [r9+1]; bManualReset
0x180070cd4  call    cs:__imp_CreateEventW
0x180070cda  xor     r9d, r9d; lpName
0x180070cdd  xor     r8d, r8d; bInitialState
0x180070ce0  xor     ecx, ecx; lpEventAttributes
0x180070ce2  mov     [rbp+hObject], rax
0x180070ce6  lea     edx, [r9+1]; bManualReset
0x180070cea  call    cs:__imp_CreateEventW
0x180070cf0  mov     rcx, [rbp+hObject]; hObject
0x180070cf4  mov     [rbp+hObject+8], rax
0x180070cf8  mov     dword ptr [rbp+var_30], edi
0x180070cfb  test    rcx, rcx
0x180070cfe  jz      loc_180070DC2
0x180070d04  test    rax, rax
0x180070d07  jz      loc_180070DB8
0x180070d0d  mov     ecx, edi
0x180070d0f  lea     rax, [rbx+60h]
0x180070d13  or      ecx, 4
0x180070d16  mov     [rsp+70h+ThrdAddr], rax; ThrdAddr
0x180070d1b  mov     [rsp+70h+InitFlag], ecx; InitFlag
0x180070d1f  lea     r9, [rbp+ArgList]; ArgList
0x180070d23  mov     rcx, rsi; Security
0x180070d26  lea     r8, ?_AfxThreadEntry@@YAIPEAX@Z; StartAddress
0x180070d2d  mov     edx, r14d; StackSize
0x180070d30  call    cs:__imp__beginthreadex
0x180070d36  mov     [rbx+58h], rax
0x180070d3a  test    rax, rax
0x180070d3d  jnz     short loc_180070D4F
0x180070d3f  mov     rcx, [rbp+hObject]; hObject
0x180070d43  call    cs:__imp_CloseHandle
0x180070d49  mov     rcx, [rbp+hObject+8]
0x180070d4d  jmp     short loc_180070DCA
0x180070d4f  mov     rcx, rax; hThread
0x180070d52  call    cs:__imp_ResumeThread
0x180070d58  mov     rcx, [rbp+hObject]; hHandle
0x180070d5c  or      esi, 0FFFFFFFFh
0x180070d5f  mov     edx, esi; dwMilliseconds
0x180070d61  call    cs:__imp_WaitForSingleObject
0x180070d67  mov     rcx, [rbp+hObject]; hObject
0x180070d6b  call    cs:__imp_CloseHandle
0x180070d71  test    dil, 4
0x180070d75  jz      short loc_180070D81
0x180070d77  mov     rcx, [rbx+58h]; hThread
0x180070d7b  call    cs:__imp_SuspendThread
0x180070d81  cmp     dword ptr [rbp+var_10], 0
0x180070d85  jz      short loc_180070DA7
0x180070d87  mov     rcx, [rbx+58h]; hHandle
0x180070d8b  mov     edx, esi; dwMilliseconds
0x180070d8d  call    cs:__imp_WaitForSingleObject
0x180070d93  mov     rcx, [rbx+58h]; hObject
0x180070d97  call    cs:__imp_CloseHandle
0x180070d9d  mov     qword ptr [rbx+58h], 0
0x180070da5  jmp     short loc_180070D49
0x180070da7  mov     rcx, [rbp+hObject+8]; hEvent
0x180070dab  call    cs:__imp_SetEvent
0x180070db1  mov     eax, 1
0x180070db6  jmp     short loc_180070DD2
0x180070db8  call    cs:__imp_CloseHandle
0x180070dbe  mov     rax, [rbp+hObject+8]
0x180070dc2  test    rax, rax
0x180070dc5  jz      short loc_180070DD0
0x180070dc7  mov     rcx, rax; hObject
0x180070dca  call    cs:__imp_CloseHandle
0x180070dd0  xor     eax, eax
0x180070dd2  add     rsp, 70h
0x180070dd6  pop     r14
0x180070dd8  pop     rdi
0x180070dd9  pop     rsi
0x180070dda  pop     rbx
0x180070ddb  pop     rbp
0x180070ddc  retn
```
