# CRealTimePenService::RemoveWaitObjectArray(IWaitObjectArray *)

- ea: `0x180011228`
- end: `0x1800113a9`
- name: `?RemoveWaitObjectArray@CRealTimePenService@@QEAAJPEAVIWaitObjectArray@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(CRealTimePenService *__hidden this, struct IWaitObjectArray *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180063580`

## callees

- `0x180002740`
- `0x180010350`
- `0x180011228`
- `0x180066464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001124e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001124e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011380`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011380`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800112ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800112ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011279`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011279`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x1800112f3`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x180011358`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x1800112f3`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x180011358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011314`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011314`

## pseudocode

```c
__int64 __fastcall CRealTimePenService::RemoveWaitObjectArray(HANDLE ***this, HANDLE *a2)
{
  unsigned int v4; // edi
  struct _RTL_CRITICAL_SECTION *v5; // r15
  HANDLE **v6; // rsi
  __int64 v7; // r13
  HANDLE *v8; // r14
  int v9; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  signed int v12; // ebx
  HANDLE *v13; // rsi
  HANDLE **v14; // rax
  HANDLE **v15; // rbx
  ULONG_PTR dwData[2]; // [rsp+20h] [rbp-48h] BYREF
  HANDLE hObject; // [rsp+30h] [rbp-38h]
  signed int v19; // [rsp+38h] [rbp-30h]

  v4 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)(this + 3);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 3));
  v6 = *this;
  v7 = (__int64)&(*this)[(_QWORD)this[1]];
  while ( (HANDLE **)v7 != v6 )
  {
    v8 = *v6;
    if ( **v6 )
    {
      v9 = *((_DWORD *)v8 + 2);
      if ( GetCurrentThreadId() != v9 )
      {
        dwData[0] = (ULONG_PTR)v8;
        dwData[1] = (ULONG_PTR)a2;
        hObject = 0;
        v19 = 0;
        EventW = CreateEventW(0, 0, 0, 0);
        hObject = EventW;
        if ( EventW )
        {
          v12 = v19;
        }
        else
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
          v19 = v12;
          EventW = hObject;
        }
        if ( v12 >= 0 )
        {
          QueueUserAPC(CWaitProcThread::IsServingWaitObjectArrayApcProc, *v8, (ULONG_PTR)dwData);
          WPTSyncApcParam::WaitDone((WPTSyncApcParam *)dwData);
          v12 = v19;
          EventW = hObject;
        }
        if ( EventW )
          CloseHandle(EventW);
        if ( !v12 )
        {
          v13 = *v6;
          if ( *v13 )
          {
            v14 = (HANDLE **)WinMalloc(0x10u);
            v15 = v14;
            if ( v14 )
            {
              v4 = 0;
              *v14 = v13;
              v14[1] = a2;
              if ( !QueueUserAPC(CWaitProcThread::RemoveWaitObjectArrayApcProc, *v13, (ULONG_PTR)v14) )
              {
                WinFree(v15);
                v4 = -2147467259;
              }
            }
            else
            {
              v4 = -2147024882;
            }
          }
          else
          {
            v4 = -2147418113;
          }
          break;
        }
      }
    }
    ++v6;
  }
  LeaveCriticalSection(v5);
  return v4;
}

```

## disassembly

```asm
0x180011228  mov     [rsp+arg_8], rbx
0x18001122d  mov     [rsp+arg_10], rsi
0x180011232  push    rdi
0x180011233  push    r12
0x180011235  push    r13
0x180011237  push    r14
0x180011239  push    r15
0x18001123b  sub     rsp, 40h
0x18001123f  mov     r12, rdx
0x180011242  mov     rbx, rcx
0x180011245  xor     edi, edi
0x180011247  lea     r15, [rcx+18h]
0x18001124b  mov     rcx, r15; lpCriticalSection
0x18001124e  call    cs:__imp_EnterCriticalSection
0x180011254  mov     rsi, [rbx]
0x180011257  mov     rax, [rbx+8]
0x18001125b  lea     r13, [rsi+rax*8]
0x18001125f  cmp     r13, rsi
0x180011262  jz      loc_18001137D
0x180011268  mov     r14, [rsi]
0x18001126b  cmp     qword ptr [r14], 0
0x18001126f  jz      loc_18001131E
0x180011275  mov     ebx, [r14+8]
0x180011279  call    cs:__imp_GetCurrentThreadId
0x18001127f  cmp     eax, ebx
0x180011281  jz      loc_18001131E
0x180011287  mov     [rsp+68h+dwData], r14
0x18001128c  mov     [rsp+68h+var_40], r12
0x180011291  mov     [rsp+68h+hObject], 0
0x18001129a  mov     [rsp+68h+var_30], 0
0x1800112a2  xor     r9d, r9d; lpName
0x1800112a5  xor     r8d, r8d; bInitialState
0x1800112a8  xor     edx, edx; bManualReset
0x1800112aa  xor     ecx, ecx; lpEventAttributes
0x1800112ac  call    cs:__imp_CreateEventW
0x1800112b2  mov     [rsp+68h+hObject], rax
0x1800112b7  test    rax, rax
0x1800112ba  jnz     short loc_1800112DC
0x1800112bc  call    cs:__imp_GetLastError
0x1800112c2  mov     ebx, eax
0x1800112c4  test    eax, eax
0x1800112c6  jle     short loc_1800112D1
0x1800112c8  movzx   ebx, ax
0x1800112cb  or      ebx, 80070000h
0x1800112d1  mov     [rsp+68h+var_30], ebx
0x1800112d5  mov     rax, [rsp+68h+hObject]
0x1800112da  jmp     short loc_1800112E0
0x1800112dc  mov     ebx, [rsp+68h+var_30]
0x1800112e0  test    ebx, ebx
0x1800112e2  js      short loc_18001130C
0x1800112e4  lea     r8, [rsp+68h+dwData]; dwData
0x1800112e9  mov     rdx, [r14]; hThread
0x1800112ec  lea     rcx, ?IsServingWaitObjectArrayApcProc@CWaitProcThread@@CAX_K@Z; pfnAPC
0x1800112f3  call    cs:__imp_QueueUserAPC
0x1800112f9  lea     rcx, [rsp+68h+dwData]; this
0x1800112fe  call    ?WaitDone@WPTSyncApcParam@@QEAAXXZ; WPTSyncApcParam::WaitDone(void)
0x180011303  mov     ebx, [rsp+68h+var_30]
0x180011307  mov     rax, [rsp+68h+hObject]
0x18001130c  test    rax, rax
0x18001130f  jz      short loc_18001131A
0x180011311  mov     rcx, rax; hObject
0x180011314  call    cs:__imp_CloseHandle
0x18001131a  test    ebx, ebx
0x18001131c  jz      short loc_180011327
0x18001131e  add     rsi, 8
0x180011322  jmp     loc_18001125F
0x180011327  mov     rsi, [rsi]
0x18001132a  cmp     qword ptr [rsi], 0
0x18001132e  jz      short loc_180011378
0x180011330  mov     ecx, 10h; unsigned __int64
0x180011335  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x18001133a  mov     rbx, rax
0x18001133d  test    rax, rax
0x180011340  jz      short loc_180011371
0x180011342  xor     edi, edi
0x180011344  mov     [rax], rsi
0x180011347  mov     [rax+8], r12
0x18001134b  mov     r8, rax; dwData
0x18001134e  mov     rdx, [rsi]; hThread
0x180011351  lea     rcx, ?RemoveWaitObjectArrayApcProc@CWaitProcThread@@CAX_K@Z; pfnAPC
0x180011358  call    cs:__imp_QueueUserAPC
0x18001135e  test    eax, eax
0x180011360  jnz     short loc_18001137D
0x180011362  mov     rcx, rbx; void *
0x180011365  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18001136a  mov     edi, 80004005h
0x18001136f  jmp     short loc_18001137D
0x180011371  mov     edi, 8007000Eh
0x180011376  jmp     short loc_18001137D
0x180011378  mov     edi, 8000FFFFh
0x18001137d  mov     rcx, r15; lpCriticalSection
0x180011380  call    cs:__imp_LeaveCriticalSection
0x180011386  nop
0x180011387  jmp     short loc_18001138D
0x180011389  mov     edi, [rsp+68h+arg_0]
0x18001138d  mov     eax, edi
0x18001138f  lea     r11, [rsp+68h+var_28]
0x180011394  mov     rbx, [r11+38h]
0x180011398  mov     rsi, [r11+40h]
0x18001139c  mov     rsp, r11
0x18001139f  pop     r15
0x1800113a1  pop     r14
0x1800113a3  pop     r13
0x1800113a5  pop     r12
0x1800113a7  pop     rdi
0x1800113a8  retn
```
