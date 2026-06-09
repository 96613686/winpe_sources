# GetThreadWaitChain

- ea: `0x180036f30`
- end: `0x18003719e`
- name: `GetThreadWaitChain`
- size: `622`
- prototype: `BOOL __stdcall(HWCT WctHandle, DWORD_PTR Context, DWORD Flags, DWORD ThreadId, LPDWORD NodeCount, PWAITCHAIN_NODE_INFO NodeInfoArray, LPBOOL IsCycle)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x18001fe24`
- `0x180036f30`
- `0x1800371a4`
- `0x1800371c0`
- `0x1800371f4`
- `0x180037230`
- `0x1800376a8`
- `0x18005ccb0`
- `0x18005e2e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036ff8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036ff8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003708c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003708c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003714d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003714d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003705e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003705e`

## pseudocode

```c
BOOL __stdcall GetThreadWaitChain(
        HWCT WctHandle,
        DWORD_PTR Context,
        DWORD Flags,
        DWORD ThreadId,
        LPDWORD NodeCount,
        PWAITCHAIN_NODE_INFO NodeInfoArray,
        LPBOOL IsCycle)
{
  unsigned int *v10; // rbx
  struct _WAITCHAIN_NODE_INFO *v11; // r14
  int *v12; // r15
  struct WCT_ENTRY *v13; // rax
  struct WCT_ENTRY *v14; // rsi
  _QWORD *v15; // rdi
  DWORD_PTR v16; // rax
  __int64 CurrentModule; // rax
  DWORD ThreadWaitChain; // ebx
  HMODULE phModule[2]; // [rsp+30h] [rbp-10h] BYREF
  _QWORD *v21; // [rsp+80h] [rbp+40h] BYREF
  DWORD_PTR v22; // [rsp+88h] [rbp+48h]

  v22 = Context;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  if ( !WctHandle
    || (Flags & 0xFFFFFFF0) != 0
    || (v10 = NodeCount) == 0
    || *NodeCount - 1 > 0xF
    || (v11 = NodeInfoArray) == 0
    || (v12 = IsCycle) == 0
    || (v13 = WctFindAndReferenceEntry(WctHandle), (v14 = v13) == 0) )
  {
    ThreadWaitChain = 87;
    goto LABEL_29;
  }
  if ( *((_DWORD *)v13 + 6) != 1 )
  {
    ThreadWaitChain = WctGetThreadWaitChain(v13, Flags, ThreadId, v10, v11, v12);
LABEL_21:
    if ( ThreadWaitChain == 997 )
      goto LABEL_23;
    goto LABEL_22;
  }
  v15 = HeapAlloc(g_hWerheap, 0, 0x38u);
  if ( v15 )
  {
    v15[2] = 0;
    v15[6] = 0;
    v16 = v22;
    *v15 = v14;
    v15[1] = v16;
    *((_DWORD *)v15 + 4) = Flags;
    *((_DWORD *)v15 + 5) = ThreadId;
    v15[3] = v10;
    v15[4] = v11;
    v15[5] = v12;
    v21 = v15;
    CurrentModule = WctGetCurrentModule(phModule);
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::operator=(
      v15 + 6,
      CurrentModule);
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(phModule);
    if ( !v15[6] )
    {
      ThreadWaitChain = GetLastError();
      utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(&v21);
      goto LABEL_21;
    }
    phModule[0] = (HMODULE)CreateThread(0, 0, WctGetThreadWaitChainWorker, v15, 0, 0);
    if ( phModule[0] != (HMODULE)-1LL && phModule[0] != 0 )
    {
      v21 = 0;
      ThreadWaitChain = 997;
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(phModule);
      utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(&v21);
      goto LABEL_29;
    }
    ThreadWaitChain = 8;
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(phModule);
  }
  else
  {
    v21 = 0;
    ThreadWaitChain = 8;
  }
  utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(&v21);
LABEL_22:
  WctDereferenceEntry(v14);
LABEL_23:
  if ( !ThreadWaitChain )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, 0);
    return 1;
  }
LABEL_29:
  SetLastError(ThreadWaitChain);
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, ThreadWaitChain);
  return 0;
}

```

## disassembly

```asm
0x180036f30  mov     [rsp-38h+arg_10], rbx
0x180036f35  mov     [rsp-38h+arg_8], rdx
0x180036f3a  push    rbp
0x180036f3b  push    rsi
0x180036f3c  push    rdi
0x180036f3d  push    r12
0x180036f3f  push    r13
0x180036f41  push    r14
0x180036f43  push    r15
0x180036f45  mov     rbp, rsp
0x180036f48  sub     rsp, 40h
0x180036f4c  mov     r13d, r9d
0x180036f4f  mov     r12d, r8d
0x180036f52  mov     rdi, rcx
0x180036f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f5c  lea     rax, WPP_GLOBAL_Control
0x180036f63  cmp     rcx, rax
0x180036f66  jz      short loc_180036F83
0x180036f68  test    byte ptr [rcx+1Ch], 4
0x180036f6c  jz      short loc_180036F83
0x180036f6e  mov     rcx, [rcx+10h]
0x180036f72  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180036f79  mov     edx, 42h ; 'B'
0x180036f7e  call    WPP_SF_
0x180036f83  test    rdi, rdi
0x180036f86  jz      loc_180037146
0x180036f8c  test    r12d, 0FFFFFFF0h
0x180036f93  jnz     loc_180037146
0x180036f99  mov     rbx, [rbp+NodeCount]
0x180036f9d  test    rbx, rbx
0x180036fa0  jz      loc_180037146
0x180036fa6  mov     eax, [rbx]
0x180036fa8  dec     eax
0x180036faa  cmp     eax, 0Fh
0x180036fad  ja      loc_180037146
0x180036fb3  mov     r14, [rbp+NodeInfoArray]
0x180036fb7  test    r14, r14
0x180036fba  jz      loc_180037146
0x180036fc0  mov     r15, [rbp+IsCycle]
0x180036fc4  test    r15, r15
0x180036fc7  jz      loc_180037146
0x180036fcd  mov     rcx, rdi; void *
0x180036fd0  call    ?WctFindAndReferenceEntry@@YAPEAUWCT_ENTRY@@PEAX@Z; WctFindAndReferenceEntry(void *)
0x180036fd5  mov     rsi, rax
0x180036fd8  test    rax, rax
0x180036fdb  jz      loc_180037146
0x180036fe1  cmp     dword ptr [rax+18h], 1
0x180036fe5  jnz     loc_1800370DF
0x180036feb  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180036ff2  xor     edx, edx; dwFlags
0x180036ff4  lea     r8d, [rdx+38h]; dwBytes
0x180036ff8  call    cs:__imp_HeapAlloc
0x180036ffe  mov     rdi, rax
0x180037001  xor     eax, eax
0x180037003  test    rdi, rdi
0x180037006  jz      loc_1800370CB
0x18003700c  mov     [rdi+10h], rax
0x180037010  lea     rcx, [rbp+phModule]; phModule
0x180037014  mov     [rdi+30h], rax
0x180037018  mov     rax, [rbp+arg_8]
0x18003701c  mov     [rdi], rsi
0x18003701f  mov     [rdi+8], rax
0x180037023  mov     [rdi+10h], r12d
0x180037027  mov     [rdi+14h], r13d
0x18003702b  mov     [rdi+18h], rbx
0x18003702f  mov     [rdi+20h], r14
0x180037033  mov     [rdi+28h], r15
0x180037037  mov     [rbp+arg_0], rdi
0x18003703b  call    ?WctGetCurrentModule@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@XZ; WctGetCurrentModule(void)
0x180037040  mov     rdx, rax
0x180037043  lea     rcx, [rdi+30h]
0x180037047  call    ??4?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::operator=(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> &&)
0x18003704c  lea     rcx, [rbp+phModule]
0x180037050  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x180037055  xor     r14d, r14d
0x180037058  cmp     [rdi+30h], r14
0x18003705c  jnz     short loc_180037074
0x18003705e  call    cs:__imp_GetLastError
0x180037064  lea     rcx, [rbp+arg_0]
0x180037068  mov     ebx, eax
0x18003706a  call    ??1?$unique_ptr@UWCT_QUERY_CONTEXT@@U?$default_delete@UWCT_QUERY_CONTEXT@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(void)
0x18003706f  jmp     loc_1800370FC
0x180037074  mov     [rsp+40h+lpThreadId], r14; lpThreadId
0x180037079  lea     r8, ?WctGetThreadWaitChainWorker@@YAKPEAX@Z; lpStartAddress
0x180037080  mov     r9, rdi; lpParameter
0x180037083  mov     [rsp+40h+dwCreationFlags], r14d; dwCreationFlags
0x180037088  xor     edx, edx; dwStackSize
0x18003708a  xor     ecx, ecx; lpThreadAttributes
0x18003708c  call    cs:__imp_CreateThread
0x180037092  mov     [rbp+phModule], rax
0x180037096  lea     rcx, [rbp+phModule]
0x18003709a  inc     rax
0x18003709d  cmp     rax, 1
0x1800370a1  ja      short loc_1800370AF
0x1800370a3  mov     ebx, 8
0x1800370a8  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800370ad  jmp     short loc_1800370D4
0x1800370af  mov     [rbp+arg_0], r14
0x1800370b3  mov     ebx, 3E5h
0x1800370b8  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800370bd  lea     rcx, [rbp+arg_0]
0x1800370c1  call    ??1?$unique_ptr@UWCT_QUERY_CONTEXT@@U?$default_delete@UWCT_QUERY_CONTEXT@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(void)
0x1800370c6  jmp     loc_18003714B
0x1800370cb  mov     [rbp+arg_0], rax
0x1800370cf  mov     ebx, 8
0x1800370d4  lea     rcx, [rbp+arg_0]
0x1800370d8  call    ??1?$unique_ptr@UWCT_QUERY_CONTEXT@@U?$default_delete@UWCT_QUERY_CONTEXT@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>::~unique_ptr<WCT_QUERY_CONTEXT,utl::default_delete<WCT_QUERY_CONTEXT>>(void)
0x1800370dd  jmp     short loc_180037104
0x1800370df  mov     [rsp+40h+lpThreadId], r15; int *
0x1800370e4  mov     r9, rbx; unsigned int *
0x1800370e7  mov     r8d, r13d; unsigned int
0x1800370ea  mov     qword ptr [rsp+40h+dwCreationFlags], r14; struct _WAITCHAIN_NODE_INFO *
0x1800370ef  mov     edx, r12d; unsigned int
0x1800370f2  mov     rcx, rsi; struct WCT_ENTRY *
0x1800370f5  call    ?WctGetThreadWaitChain@@YAKPEAUWCT_ENTRY@@KKPEAKPEAU_WAITCHAIN_NODE_INFO@@PEAH@Z; WctGetThreadWaitChain(WCT_ENTRY *,ulong,ulong,ulong *,_WAITCHAIN_NODE_INFO *,int *)
0x1800370fa  mov     ebx, eax
0x1800370fc  cmp     ebx, 3E5h
0x180037102  jz      short loc_18003710C
0x180037104  mov     rcx, rsi; struct WCT_ENTRY *
0x180037107  call    ?WctDereferenceEntry@@YAHPEAUWCT_ENTRY@@@Z; WctDereferenceEntry(WCT_ENTRY *)
0x18003710c  test    ebx, ebx
0x18003710e  jnz     short loc_18003714B
0x180037110  mov     rcx, cs:WPP_GLOBAL_Control
0x180037117  lea     rax, WPP_GLOBAL_Control
0x18003711e  cmp     rcx, rax
0x180037121  jz      short loc_18003713F
0x180037123  test    byte ptr [rcx+1Ch], 4
0x180037127  jz      short loc_18003713F
0x180037129  mov     rcx, [rcx+10h]
0x18003712d  lea     edx, [rbx+44h]
0x180037130  xor     r9d, r9d
0x180037133  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003713a  call    WPP_SF_d
0x18003713f  mov     eax, 1
0x180037144  jmp     short loc_180037186
0x180037146  mov     ebx, 57h ; 'W'
0x18003714b  mov     ecx, ebx; dwErrCode
0x18003714d  call    cs:__imp_SetLastError
0x180037153  mov     rcx, cs:WPP_GLOBAL_Control
0x18003715a  lea     rax, WPP_GLOBAL_Control
0x180037161  cmp     rcx, rax
0x180037164  jz      short loc_180037184
0x180037166  test    byte ptr [rcx+1Ch], 4
0x18003716a  jz      short loc_180037184
0x18003716c  mov     rcx, [rcx+10h]
0x180037170  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180037177  mov     edx, 43h ; 'C'
0x18003717c  mov     r9d, ebx
0x18003717f  call    WPP_SF_d
0x180037184  xor     eax, eax
0x180037186  mov     rbx, [rsp+40h+arg_10]
0x18003718e  add     rsp, 40h
0x180037192  pop     r15
0x180037194  pop     r14
0x180037196  pop     r13
0x180037198  pop     r12
0x18003719a  pop     rdi
0x18003719b  pop     rsi
0x18003719c  pop     rbp
0x18003719d  retn
```
