# CHandlerCache::ExecuteAction(SYNCMGR_HANDLERACTIONS,CSyncMgrID const &,HWND__ *,bool,SYNCMGR_CONTROL_FLAGS)

- ea: `0x180013bb8`
- end: `0x180013cc8`
- name: `?ExecuteAction@CHandlerCache@@QEAAJW4SYNCMGR_HANDLERACTIONS@@AEBVCSyncMgrID@@PEAUHWND__@@_NW4SYNCMGR_CONTROL_FLAGS@@@Z`
- size: `272`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180012bec`
- `0x18001f8a0`

## callees

- `0x180004f10`
- `0x1800074a4`
- `0x180012e54`
- `0x180013bb8`
- `0x180016d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013c0a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013c0a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013ca2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013ca2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013caf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013caf`

## pseudocode

```c
__int64 __fastcall CHandlerCache::ExecuteAction(
        struct _RTL_CRITICAL_SECTION *a1,
        unsigned int a2,
        const WCHAR *a3,
        __int64 a4,
        char a5,
        int a6)
{
  HRESULT Error; // ebx
  char v11; // si
  HANDLE EventW; // rdi
  HRESULT v14; // [rsp+40h] [rbp-58h] BYREF
  struct CHandlerInfo *v15; // [rsp+48h] [rbp-50h] BYREF

  Error = -2147023781;
  if ( _InterlockedExchange(&dword_18006FE54, dword_18006FE54) )
  {
    if ( (a6 & 1) != 0 )
    {
      v11 = 1;
      EventW = CreateEventW(0, 1, 0, 0);
      if ( !EventW )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          return (unsigned int)Error;
      }
    }
    else
    {
      EventW = 0;
      v11 = 0;
    }
    v14 = 0;
    v15 = 0;
    Error = CHandlerCache::_FindHandlerInfo(a1, a3, &v15);
    if ( Error >= 0 )
    {
      Error = CHandlerInfo::ExecuteAction(v15, a2, a3, a4, a5, a6, EventW, &v14);
      CHandlerInfo::Release(v15);
    }
    if ( v11 == 1 )
    {
      if ( Error >= 0 )
      {
        WaitForSingleObject(EventW, 0xFFFFFFFF);
        Error = v14;
      }
      CloseHandle(EventW);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180013bb8  push    rbx
0x180013bba  push    rbp
0x180013bbb  push    rsi
0x180013bbc  push    rdi
0x180013bbd  push    r12
0x180013bbf  push    r13
0x180013bc1  push    r14
0x180013bc3  push    r15
0x180013bc5  sub     rsp, 58h
0x180013bc9  mov     eax, cs:dword_18006FE54
0x180013bcf  mov     r12, r9
0x180013bd2  xchg    eax, cs:dword_18006FE54
0x180013bd8  mov     r14, r8
0x180013bdb  mov     r13d, edx
0x180013bde  mov     r15, rcx
0x180013be1  mov     ebx, 8007045Bh
0x180013be6  test    eax, eax
0x180013be8  jz      loc_180013CB5
0x180013bee  mov     ebp, [rsp+98h+arg_28]
0x180013bf5  test    bpl, 1
0x180013bf9  jz      short loc_180013C29
0x180013bfb  xor     r9d, r9d; lpName
0x180013bfe  xor     r8d, r8d; bInitialState
0x180013c01  xor     ecx, ecx; lpEventAttributes
0x180013c03  mov     sil, 1
0x180013c06  lea     edx, [r9+1]; bManualReset
0x180013c0a  call    cs:__imp_CreateEventW
0x180013c10  mov     rdi, rax
0x180013c13  test    rax, rax
0x180013c16  jnz     short loc_180013C2E
0x180013c18  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180013c1d  mov     ebx, eax
0x180013c1f  test    eax, eax
0x180013c21  js      loc_180013CB5
0x180013c27  jmp     short loc_180013C2E
0x180013c29  xor     edi, edi
0x180013c2b  xor     sil, sil
0x180013c2e  lea     r8, [rsp+98h+var_50]; struct CHandlerInfo **
0x180013c33  mov     [rsp+98h+var_58], 0
0x180013c3b  mov     rdx, r14; struct CSyncMgrID *
0x180013c3e  mov     [rsp+98h+var_50], 0
0x180013c47  mov     rcx, r15; lpCriticalSection
0x180013c4a  call    ?_FindHandlerInfo@CHandlerCache@@AEAAJAEBVCSyncMgrID@@PEAPEAVCHandlerInfo@@@Z; CHandlerCache::_FindHandlerInfo(CSyncMgrID const &,CHandlerInfo * *)
0x180013c4f  mov     ebx, eax
0x180013c51  test    eax, eax
0x180013c53  js      short loc_180013C92
0x180013c55  mov     rcx, [rsp+98h+var_50]
0x180013c5a  lea     rax, [rsp+98h+var_58]
0x180013c5f  mov     [rsp+98h+var_60], rax
0x180013c64  mov     r9, r12
0x180013c67  mov     al, [rsp+98h+arg_20]
0x180013c6e  mov     r8, r14
0x180013c71  mov     [rsp+98h+var_68], rdi
0x180013c76  mov     edx, r13d
0x180013c79  mov     [rsp+98h+var_70], ebp
0x180013c7d  mov     [rsp+98h+var_78], al
0x180013c81  call    ?ExecuteAction@CHandlerInfo@@QEAAJW4SYNCMGR_HANDLERACTIONS@@AEBVCSyncMgrID@@PEAUHWND__@@_NW4SYNCMGR_CONTROL_FLAGS@@PEAXPEAJ@Z; CHandlerInfo::ExecuteAction(SYNCMGR_HANDLERACTIONS,CSyncMgrID const &,HWND__ *,bool,SYNCMGR_CONTROL_FLAGS,void *,long *)
0x180013c86  mov     rcx, [rsp+98h+var_50]; this
0x180013c8b  mov     ebx, eax
0x180013c8d  call    ?Release@CHandlerInfo@@QEAAKXZ; CHandlerInfo::Release(void)
0x180013c92  cmp     sil, 1
0x180013c96  jnz     short loc_180013CB5
0x180013c98  test    ebx, ebx
0x180013c9a  js      short loc_180013CAC
0x180013c9c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013c9f  mov     rcx, rdi; hHandle
0x180013ca2  call    cs:__imp_WaitForSingleObject
0x180013ca8  mov     ebx, [rsp+98h+var_58]
0x180013cac  mov     rcx, rdi; hObject
0x180013caf  call    cs:__imp_CloseHandle
0x180013cb5  mov     eax, ebx
0x180013cb7  add     rsp, 58h
0x180013cbb  pop     r15
0x180013cbd  pop     r14
0x180013cbf  pop     r13
0x180013cc1  pop     r12
0x180013cc3  pop     rdi
0x180013cc4  pop     rsi
0x180013cc5  pop     rbp
0x180013cc6  pop     rbx
0x180013cc7  retn
```
