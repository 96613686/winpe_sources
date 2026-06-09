# CCContext::Hook(void)

- ea: `0x1800369f0`
- end: `0x180036b27`
- name: `?Hook@CCContext@@IEAAJXZ`
- size: `311`
- prototype: `__int64 __fastcall(CCContext *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002a884`

## callees

- `0x180021f84`
- `0x180025af0`
- `0x180034148`
- `0x180034220`
- `0x1800369f0`
- `0x1800372e8`
- `0x180039efc`
- `0x180063500`
- `0x180063638`
- `0x18006399c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180036b11`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180036b11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036b04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036b04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036a64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036a64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036a3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036a3c`
- `USER32!GetWindowThreadProcessId` at `0x180036a31`
- `USER32!GetWindowThreadProcessId` at `0x180036a31`

## string_xrefs

- `0x180036a7b`: `CCContext::Hook (%x): window:%x, thread:%x(cur %x), context:%x\n`

## pseudocode

```c
__int64 __fastcall CCContext::Hook(CCContext *this, int a2)
{
  HWND *v3; // rsi
  unsigned int *v5; // r15
  int v6; // ebx
  unsigned int v7; // edi
  CCContext *v8; // rcx
  __int64 v9; // rbx
  HHOOK v10; // rax
  __int64 v11; // rcx
  struct CWindowData *v12; // rbx
  int v13; // eax
  DWORD CurrentThreadId; // [rsp+20h] [rbp-48h]
  int v15; // [rsp+28h] [rbp-40h]

  v3 = (HWND *)((char *)this + 136);
  if ( !*((_QWORD *)this + 17) )
    return 1;
  CComDllModule::EnterApcSection(this, a2);
  v5 = (unsigned int *)((char *)this + 156);
  *((_DWORD *)this + 39) = GetWindowThreadProcessId(*v3, (LPDWORD)this + 37);
  v6 = *((_DWORD *)this + 37);
  if ( GetCurrentProcessId() == v6 )
  {
    v7 = 0;
    EnterCriticalSection(&CComCoClassKeyed<CCContext,unsigned long>::s_csMap);
    v15 = *((_DWORD *)this + 2);
    CurrentThreadId = GetCurrentThreadId();
    Log(L"CCContext::Hook (%x): window:%x, thread:%x(cur %x), context:%x\n", this, *v3, *v5, CurrentThreadId, v15);
    try
    {
      v9 = std::map<unsigned long,CCContext::CThreadData,std::less<unsigned long>,inkobj_allocator<std::pair<unsigned long,CCContext::CThreadData>>>::operator[]();
      if ( *(_QWORD *)v9 )
        goto LABEL_10;
      v10 = CCContext::SetThreadRobustContextWindowHook(v8, *v5);
      *(_QWORD *)v9 = v10;
      if ( !v10 )
      {
        std::_Tree<std::_Tmap_traits<unsigned long,CCContext::CThreadData,std::less<unsigned long>,inkobj_allocator<std::pair<unsigned long,CCContext::CThreadData>>,0>>::erase(
          v11,
          (char *)this + 156);
        v7 = -2147467259;
      }
      Log(L"CCContext::Hook: set hook %x\n", *(_QWORD *)v9);
      if ( !v7 )
      {
LABEL_10:
        ++*(_DWORD *)(v9 + 8);
        v12 = (struct CWindowData *)std::map<HWND__ *,CWindowData,std::less<HWND__ *>,inkobj_allocator<std::pair<HWND__ *,CWindowData>>>::operator[](
                                      v8,
                                      v3);
        std::vector<unsigned long,inkobj_allocator<unsigned long>>::push_back(v12, (char *)this + 8);
        v13 = NeedsTimer(*v3);
        UpdateWindowTrackingData(v13, *v3, v12);
      }
    }
    catch ( ... )
    {
      v7 = ReportWispException();
    }
    LeaveCriticalSection(&CComCoClassKeyed<CCContext,unsigned long>::s_csMap);
  }
  else
  {
    v7 = -2147220968;
  }
  ReleaseMutex(pHandles);
  return v7;
}

```

## disassembly

```asm
0x1800369f0  push    rbx
0x1800369f2  push    rsi
0x1800369f3  push    rdi
0x1800369f4  push    r12
0x1800369f6  push    r14
0x1800369f8  push    r15
0x1800369fa  sub     rsp, 38h
0x1800369fe  mov     r14, rcx
0x180036a01  lea     rsi, [rcx+88h]
0x180036a08  cmp     qword ptr [rsi], 0
0x180036a0c  jnz     short loc_180036A18
0x180036a0e  mov     eax, 1
0x180036a13  jmp     loc_180036B19
0x180036a18  call    ?EnterApcSection@CComDllModule@@QEAAXH@Z; CComDllModule::EnterApcSection(int)
0x180036a1d  lea     r15, [r14+9Ch]
0x180036a24  lea     rbx, [r14+94h]
0x180036a2b  mov     rdx, rbx; lpdwProcessId
0x180036a2e  mov     rcx, [rsi]; hWnd
0x180036a31  call    cs:__imp_GetWindowThreadProcessId
0x180036a37  mov     [r15], eax
0x180036a3a  mov     ebx, [rbx]
0x180036a3c  call    cs:__imp_GetCurrentProcessId
0x180036a42  cmp     eax, ebx
0x180036a44  jz      short loc_180036A50
0x180036a46  mov     edi, 80040218h
0x180036a4b  jmp     loc_180036B0A
0x180036a50  xor     edi, edi
0x180036a52  lea     rcx, ?s_csMap@?$CComCoClassKeyed@VCCContext@@K@@2VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x180036a59  call    cs:__imp_EnterCriticalSection
0x180036a5f  nop
0x180036a60  mov     ebx, [r14+8]
0x180036a64  call    cs:__imp_GetCurrentThreadId
0x180036a6a  mov     [rsp+68h+var_40], ebx
0x180036a6e  mov     [rsp+68h+var_48], eax
0x180036a72  mov     r9d, [r15]
0x180036a75  mov     r8, [rsi]
0x180036a78  mov     rdx, r14
0x180036a7b  lea     rcx, aCccontextHookX; "CCContext::Hook (%x): window:%x, thread"...
0x180036a82  call    ?Log@@YAXPEBGZZ; Log(ushort const *,...)
0x180036a87  mov     rdx, r15
0x180036a8a  call    ??A?$map@KVCThreadData@CCContext@@U?$less@K@std@@V?$inkobj_allocator@U?$pair@KVCThreadData@CCContext@@@std@@@@@std@@QEAAAEAVCThreadData@CCContext@@AEBK@Z; std::map<ulong,CCContext::CThreadData,std::less<ulong>,inkobj_allocator<std::pair<ulong,CCContext::CThreadData>>>::operator[](ulong const &)
0x180036a8f  mov     rbx, rax
0x180036a92  cmp     [rax], rdi
0x180036a95  jnz     short loc_180036AC7
0x180036a97  mov     edx, [r15]; unsigned int
0x180036a9a  call    ?SetThreadRobustContextWindowHook@CCContext@@IEAAPEAUHHOOK__@@K@Z; CCContext::SetThreadRobustContextWindowHook(ulong)
0x180036a9f  mov     [rbx], rax
0x180036aa2  test    rax, rax
0x180036aa5  jnz     short loc_180036AB4
0x180036aa7  mov     rdx, r15
0x180036aaa  call    ?erase@?$_Tree@V?$_Tmap_traits@KVCThreadData@CCContext@@U?$less@K@std@@V?$inkobj_allocator@U?$pair@KVCThreadData@CCContext@@@std@@@@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,CCContext::CThreadData,std::less<ulong>,inkobj_allocator<std::pair<ulong,CCContext::CThreadData>>,0>>::erase(ulong const &)
0x180036aaf  mov     edi, 80004005h
0x180036ab4  mov     rdx, [rbx]
0x180036ab7  lea     rcx, aCccontextHookS; "CCContext::Hook: set hook %x\n"
0x180036abe  call    ?Log@@YAXPEBGZZ; Log(ushort const *,...)
0x180036ac3  test    edi, edi
0x180036ac5  jnz     short loc_180036AF7
0x180036ac7  inc     dword ptr [rbx+8]
0x180036aca  mov     rdx, rsi
0x180036acd  call    ??A?$map@PEAUHWND__@@VCWindowData@@U?$less@PEAUHWND__@@@std@@V?$inkobj_allocator@U?$pair@PEAUHWND__@@VCWindowData@@@std@@@@@std@@QEAAAEAVCWindowData@@AEBQEAUHWND__@@@Z; std::map<HWND__ *,CWindowData,std::less<HWND__ *>,inkobj_allocator<std::pair<HWND__ *,CWindowData>>>::operator[](HWND__ * const &)
0x180036ad2  mov     rbx, rax
0x180036ad5  lea     rdx, [r14+8]
0x180036ad9  mov     rcx, rax
0x180036adc  call    ?push_back@?$vector@KV?$inkobj_allocator@K@@@std@@QEAAXAEBK@Z; std::vector<ulong,inkobj_allocator<ulong>>::push_back(ulong const &)
0x180036ae1  mov     rcx, [rsi]; hWnd
0x180036ae4  call    ?NeedsTimer@@YAHPEAUHWND__@@@Z; NeedsTimer(HWND__ *)
0x180036ae9  mov     r8, rbx; struct CWindowData *
0x180036aec  mov     rdx, [rsi]; HWND
0x180036aef  mov     ecx, eax; int
0x180036af1  call    ?UpdateWindowTrackingData@@YAXHPEAUHWND__@@AEAVCWindowData@@@Z; UpdateWindowTrackingData(int,HWND__ *,CWindowData &)
0x180036af6  nop
0x180036af7  jmp     short loc_180036AFD
0x180036af9  mov     edi, [rsp+68h+arg_0]
0x180036afd  lea     rcx, ?s_csMap@?$CComCoClassKeyed@VCCContext@@K@@2VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x180036b04  call    cs:__imp_LeaveCriticalSection
0x180036b0a  mov     rcx, cs:pHandles; hMutex
0x180036b11  call    cs:__imp_ReleaseMutex
0x180036b17  mov     eax, edi
0x180036b19  add     rsp, 38h
0x180036b1d  pop     r15
0x180036b1f  pop     r14
0x180036b21  pop     r12
0x180036b23  pop     rdi
0x180036b24  pop     rsi
0x180036b25  pop     rbx
0x180036b26  retn
```
