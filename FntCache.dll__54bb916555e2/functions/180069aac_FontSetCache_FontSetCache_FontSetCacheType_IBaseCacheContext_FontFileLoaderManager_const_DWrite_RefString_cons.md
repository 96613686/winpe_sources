# FontSetCache::FontSetCache(FontSetCacheType,IBaseCacheContext *,FontFileLoaderManager const &,DWrite::RefString const &,DWrite::RefString const &,ComPtr<IInstalledFontFileEnumerator> &&,Win32Handle &&)

- ea: `0x180069aac`
- end: `0x180069ca2`
- name: `??0FontSetCache@@QEAA@W4FontSetCacheType@@PEAUIBaseCacheContext@@AEBVFontFileLoaderManager@@AEBVRefString@DWrite@@3$$QEAV?$ComPtr@UIInstalledFontFileEnumerator@@@@$$QEAVWin32Handle@@@Z`
- size: `502`
- prototype: `__int64 __usercall@<rax>(LPVOID lpParameter@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180069a20`

## callees

- `0x180004810`
- `0x1800217ac`
- `0x180067b10`
- `0x180068608`
- `0x180068628`
- `0x180069aac`
- `0x18006ab98`
- `0x1800a2a08`
- `0x1800ab1b0`
- `0x1800b7bc0`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180069c40`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180069c40`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180069c17`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180069c17`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
char *__fastcall FontSetCache::FontSetCache(
        char *lpParameter,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        volatile signed __int32 **a5,
        volatile signed __int32 **a6,
        __int64 *a7,
        __int64 *a8)
{
  int v10; // edi
  volatile signed __int32 **v12; // r15
  _DWORD *v13; // rcx
  __int64 v14; // r10
  bool v15; // dl
  volatile signed __int32 *v16; // rcx
  volatile signed __int32 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  bool v20; // dl
  bool v21; // dl
  HANDLE Thread; // rax
  int Error; // eax
  char pExceptionObject; // [rsp+68h] [rbp+10h] BYREF

  v10 = a2;
  v12 = a6;
  ComObjectBase<ComInterfaceList<FontSetCache,IFontSetCache>,IFontSetCache>::ComObjectBase<ComInterfaceList<FontSetCache,IFontSetCache>,IFontSetCache>(
    lpParameter,
    a2,
    a3,
    a4);
  v13 += 4;
  *v13 = _InterlockedIncrement((volatile signed __int32 *)&EventLogger::lastObjectId_);
  *((_QWORD *)lpParameter + 3) = 1919906915;
  EventLogger::LogEvent<EventTag,wchar_t const *>((_DWORD)v13, 1953394502, 1952543859, 1919906915, v14);
  *(_QWORD *)lpParameter = &FontSetCache::`vftable';
  *((_DWORD *)lpParameter + 8) = v10;
  *((_QWORD *)lpParameter + 5) = a3;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  *((_QWORD *)lpParameter + 6) = a4;
  v16 = *a5;
  *((_QWORD *)lpParameter + 7) = *a5;
  _InterlockedIncrement(v16);
  v17 = *v12;
  *((_QWORD *)lpParameter + 8) = *v12;
  _InterlockedIncrement(v17);
  v18 = *a7;
  *a7 = 0;
  *((_QWORD *)lpParameter + 9) = v18;
  v19 = *a8;
  *a8 = 0;
  *((_QWORD *)lpParameter + 10) = v19;
  *((_QWORD *)lpParameter + 11) = 0;
  *((_QWORD *)lpParameter + 12) = 0;
  *(_OWORD *)(lpParameter + 104) = 0;
  *((_QWORD *)lpParameter + 15) = 0;
  *((_DWORD *)lpParameter + 32) = 0;
  ManualResetEvent::ManualResetEvent((ManualResetEvent *)(lpParameter + 136), v15);
  *((_DWORD *)lpParameter + 36) = 1;
  lpParameter[148] = 0;
  *((_DWORD *)lpParameter + 38) = 0;
  AutoResetEvent::AutoResetEvent((AutoResetEvent *)(lpParameter + 160), v20);
  *((_DWORD *)lpParameter + 42) = 0;
  *((_QWORD *)lpParameter + 22) = 0;
  ManualResetEvent::ManualResetEvent((ManualResetEvent *)(lpParameter + 184), v21);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(lpParameter + 192);
  InitializeCriticalSection((LPCRITICAL_SECTION)(lpParameter + 216));
  *((_QWORD *)lpParameter + 32) = 0;
  Thread = CreateThread(0, 0, FontSetCache::MonitorThreadProc, lpParameter, 4u, (LPDWORD)lpParameter + 32);
  Win32Handle::Attach((Win32Handle *)(lpParameter + 120), Thread);
  if ( !*((_QWORD *)lpParameter + 15) )
  {
    Error = EventSource<ComInterfaceList<FontSetCache,IFontSetCache>,IFontSetCache>::LogLastError(
              lpParameter,
              1919906915,
              39);
    Exception::Exception((Exception *)&pExceptionObject, Error, 0);
    throw (OSException *)&pExceptionObject;
  }
  return lpParameter;
}

```

## disassembly

```asm
0x180069aac  mov     [rsp+arg_10], rbx
0x180069ab1  mov     [rsp+arg_18], rbp
0x180069ab6  mov     [rsp+arg_0], rcx
0x180069abb  push    rsi
0x180069abc  push    rdi
0x180069abd  push    r12
0x180069abf  push    r14
0x180069ac1  push    r15
0x180069ac3  sub     rsp, 30h
0x180069ac7  mov     rbp, r9
0x180069aca  mov     rsi, r8
0x180069acd  mov     edi, edx
0x180069acf  mov     r14, rcx
0x180069ad2  mov     r15, [rsp+58h+arg_28]
0x180069ada  mov     r10, [r15]
0x180069add  add     r10, 8
0x180069ae1  call    ??0?$ComObjectBase@V?$ComInterfaceList@VFontSetCache@@UIFontSetCache@@@@UIFontSetCache@@@@QEAA@XZ; ComObjectBase<ComInterfaceList<FontSetCache,IFontSetCache>,IFontSetCache>::ComObjectBase<ComInterfaceList<FontSetCache,IFontSetCache>,IFontSetCache>(void)
0x180069ae6  add     rcx, 10h
0x180069aea  mov     eax, 1
0x180069aef  lock xadd cs:?lastObjectId_@EventLogger@@0IA, eax; uint EventLogger::lastObjectId_
0x180069af7  inc     eax
0x180069af9  mov     [rcx], eax
0x180069afb  mov     ebx, 726F7463h
0x180069b00  mov     [r14+18h], rbx
0x180069b04  mov     rdx, 746553746E6F46h
0x180069b0e  mov     r8, 6574617473h
0x180069b18  mov     qword ptr [rsp+58h+dwCreationFlags], r10
0x180069b1d  mov     r9d, ebx
0x180069b20  call    ??$LogEvent@VEventTag@@PEB_W@EventLogger@@QEBAXVEventTag@@00PEB_W@Z; EventLogger::LogEvent<EventTag,wchar_t const *>(EventTag,EventTag,EventTag,wchar_t const *)
0x180069b25  nop
0x180069b26  lea     rax, ??_7FontSetCache@@6B@; const FontSetCache::`vftable'
0x180069b2d  mov     [r14], rax
0x180069b30  mov     [r14+20h], edi
0x180069b34  mov     [r14+28h], rsi
0x180069b38  xor     r12d, r12d
0x180069b3b  test    rsi, rsi
0x180069b3e  jz      short loc_180069B50
0x180069b40  mov     rax, [rsi]
0x180069b43  mov     rcx, rsi
0x180069b46  mov     rax, [rax+8]
0x180069b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b4f  nop
0x180069b50  mov     [r14+30h], rbp
0x180069b54  mov     rax, [rsp+58h+arg_20]
0x180069b5c  mov     rcx, [rax]
0x180069b5f  mov     [r14+38h], rcx
0x180069b63  lock inc dword ptr [rcx]
0x180069b66  mov     rax, [r15]
0x180069b69  mov     [r14+40h], rax
0x180069b6d  lock inc dword ptr [rax]
0x180069b70  mov     rax, [rsp+58h+arg_30]
0x180069b78  mov     rcx, [rax]
0x180069b7b  mov     [rax], r12
0x180069b7e  mov     [r14+48h], rcx
0x180069b82  mov     rax, [rsp+58h+arg_38]
0x180069b8a  mov     rcx, [rax]
0x180069b8d  mov     [rax], r12
0x180069b90  mov     [r14+50h], rcx
0x180069b94  mov     [r14+58h], r12
0x180069b98  mov     [r14+60h], r12
0x180069b9c  xorps   xmm0, xmm0
0x180069b9f  movups  xmmword ptr [r14+68h], xmm0
0x180069ba4  lea     rsi, [r14+78h]
0x180069ba8  mov     [rsi], r12
0x180069bab  lea     rdi, [r14+80h]
0x180069bb2  mov     [rdi], r12d
0x180069bb5  lea     rcx, [r14+88h]; this
0x180069bbc  call    ??0ManualResetEvent@@QEAA@_N@Z; ManualResetEvent::ManualResetEvent(bool)
0x180069bc1  nop
0x180069bc2  mov     dword ptr [r14+90h], 1
0x180069bcd  mov     [r14+94h], r12b
0x180069bd4  mov     [r14+98h], r12d
0x180069bdb  lea     rcx, [r14+0A0h]; this
0x180069be2  call    ??0AutoResetEvent@@QEAA@_N@Z; AutoResetEvent::AutoResetEvent(bool)
0x180069be7  nop
0x180069be8  mov     [r14+0A8h], r12d
0x180069bef  mov     [r14+0B0h], r12
0x180069bf6  lea     rcx, [r14+0B8h]; this
0x180069bfd  call    ??0ManualResetEvent@@QEAA@_N@Z; ManualResetEvent::ManualResetEvent(bool)
0x180069c02  nop
0x180069c03  lea     rcx, [r14+0C0h]; void *
0x180069c0a  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180069c0f  nop
0x180069c10  lea     rcx, [r14+0D8h]; lpCriticalSection
0x180069c17  call    cs:__imp_InitializeCriticalSection
0x180069c1d  nop
0x180069c1e  mov     [r14+100h], r12
0x180069c25  mov     [rsp+58h+lpThreadId], rdi; lpThreadId
0x180069c2a  mov     [rsp+58h+dwCreationFlags], 4; dwCreationFlags
0x180069c32  mov     r9, r14; lpParameter
0x180069c35  lea     r8, ?MonitorThreadProc@FontSetCache@@CAKPEAX@Z; lpStartAddress
0x180069c3c  xor     edx, edx; dwStackSize
0x180069c3e  xor     ecx, ecx; lpThreadAttributes
0x180069c40  call    cs:__imp_CreateThread
0x180069c46  mov     rdx, rax; void *
0x180069c49  mov     rcx, rsi; this
0x180069c4c  call    ?Attach@Win32Handle@@QEAAXPEAX@Z; Win32Handle::Attach(void *)
0x180069c51  cmp     [rsi], r12
0x180069c54  jnz     short loc_180069C88
0x180069c56  mov     r8d, 27h ; '''
0x180069c5c  mov     rdx, rbx
0x180069c5f  mov     rcx, r14
0x180069c62  call    ?LogLastError@?$EventSource@V?$ComInterfaceList@VFontSetCache@@UIFontSetCache@@@@UIFontSetCache@@@@QEBAJVEventTag@@I@Z; EventSource<ComInterfaceList<FontSetCache,IFontSetCache>,IFontSetCache>::LogLastError(EventTag,uint)
0x180069c67  xor     r8d, r8d; unsigned int
0x180069c6a  mov     edx, eax; int
0x180069c6c  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180069c71  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x180069c76  lea     rdx, _TI2?AVOSException@@; pThrowInfo
0x180069c7d  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180069c82  call    _CxxThrowException_0
0x180069c88  mov     rax, r14
0x180069c8b  mov     rbx, [rsp+58h+arg_10]
0x180069c90  mov     rbp, [rsp+58h+arg_18]
0x180069c95  add     rsp, 30h
0x180069c99  pop     r15
0x180069c9b  pop     r14
0x180069c9d  pop     r12
0x180069c9f  pop     rdi
0x180069ca0  pop     rsi
0x180069ca1  retn
```
