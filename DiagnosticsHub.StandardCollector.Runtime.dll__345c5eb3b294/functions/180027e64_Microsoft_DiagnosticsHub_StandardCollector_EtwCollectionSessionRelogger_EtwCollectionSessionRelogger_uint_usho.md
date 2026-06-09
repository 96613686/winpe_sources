# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::EtwCollectionSessionRelogger(uint,ushort const *,ushort const *)

- ea: `0x180027e64`
- end: `0x18002809e`
- name: `??0EtwCollectionSessionRelogger@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@IPEBG0@Z`
- size: `570`
- prototype: `_QWORD(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020338`

## callees

- `0x180002604`
- `0x1800084d0`
- `0x180027e64`
- `0x18004a03c`
- `0x18004ad58`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180027f5f`
- `KERNEL32!CreateEventW` at `0x180027fc1`
- `KERNEL32!CreateEventW` at `0x180027f5f`
- `KERNEL32!CreateEventW` at `0x180027fc1`
- `KERNEL32!InitializeCriticalSection` at `0x180027efd`
- `KERNEL32!InitializeCriticalSection` at `0x180027efd`
- `KERNEL32!GetLastError` at `0x180027f78`
- `KERNEL32!GetLastError` at `0x180027f94`
- `KERNEL32!GetLastError` at `0x180027fda`
- `KERNEL32!GetLastError` at `0x180027ff6`
- `KERNEL32!GetLastError` at `0x180027f78`
- `KERNEL32!GetLastError` at `0x180027f94`
- `KERNEL32!GetLastError` at `0x180027fda`
- `KERNEL32!GetLastError` at `0x180027ff6`
- `OLEAUT32!__imp_SysAllocString` at `0x180028043`
- `OLEAUT32!__imp_SysAllocString` at `0x18002805a`
- `OLEAUT32!__imp_SysAllocString` at `0x180028043`
- `OLEAUT32!__imp_SysAllocString` at `0x18002805a`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *__fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::EtwCollectionSessionRelogger(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  _QWORD *v8; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v11; // ecx
  HANDLE v12; // rax
  signed int v13; // eax
  unsigned int v14; // ecx
  BSTR v16; // rax
  BSTR v17; // rax
  int pExceptionObject; // [rsp+58h] [rbp+10h] BYREF

  *((_DWORD *)this + 4) = 1;
  *((_QWORD *)this + 1) = &CModuleRefCount::`vftable';
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef) >= 0x7FFFFFFF )
    __fastfail(0xEu);
  DiagHubCommon::HubTask<long,0>::HubTask<long,0>((char *)this + 24);
  *(_QWORD *)this = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `ITraceEventCallback'};
  *((_QWORD *)this + 1) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `CModuleRefCount'};
  *((_QWORD *)this + 3) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `DiagHubCommon::HubTask<long,0>'};
  *((_DWORD *)this + 34) = a2;
  *((_OWORD *)this + 9) = 0;
  *((_OWORD *)this + 10) = 0;
  *((_QWORD *)this + 22) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  v8 = operator new(0x10u);
  v8[1] = 0;
  *((_QWORD *)this + 23) = v8;
  *v8 = (char *)this + 184;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = -1;
  *((_DWORD *)this + 62) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 30) = EventW;
  if ( EventW )
  {
    if ( GetLastError() == 183 )
      *((_DWORD *)this + 62) = 1;
  }
  else
  {
    *((_QWORD *)this + 30) = -1;
    LastError = GetLastError();
    v11 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v11 = LastError;
    *((_DWORD *)this + 62) = v11;
  }
  *((_QWORD *)this + 32) = -1;
  *((_DWORD *)this + 66) = 0;
  v12 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 32) = v12;
  if ( v12 )
  {
    if ( GetLastError() == 183 )
      *((_DWORD *)this + 66) = 1;
  }
  else
  {
    *((_QWORD *)this + 32) = -1;
    v13 = GetLastError();
    v14 = (unsigned __int16)v13 | 0x80070000;
    if ( v13 <= 0 )
      v14 = v13;
    *((_DWORD *)this + 66) = v14;
  }
  if ( a4 )
  {
    v16 = SysAllocString(a4);
    *((_QWORD *)this + 34) = v16;
    if ( !v16 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    *((_QWORD *)this + 34) = 0;
  }
  if ( a3 )
  {
    v17 = SysAllocString(a3);
    *((_QWORD *)this + 35) = v17;
    if ( !v17 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    *((_QWORD *)this + 35) = 0;
  }
  if ( !a3 || !a4 )
  {
    pExceptionObject = -2147467261;
    throw (long *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180027e64  mov     [rsp+arg_10], rbx
0x180027e69  mov     [rsp+arg_0], rcx
0x180027e6e  push    rbp
0x180027e6f  push    rsi
0x180027e70  push    rdi
0x180027e71  push    r14
0x180027e73  push    r15
0x180027e75  sub     rsp, 20h
0x180027e79  mov     rsi, r9
0x180027e7c  mov     rbp, r8
0x180027e7f  mov     r14d, edx
0x180027e82  mov     rdi, rcx
0x180027e85  mov     r15d, 1
0x180027e8b  mov     [rcx+10h], r15d
0x180027e8f  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x180027e96  mov     [rcx+8], rax
0x180027e9a  mov     eax, r15d
0x180027e9d  lock xadd cs:?s_ulcModuleRef@CModuleRefCount@@0KA, eax; ulong CModuleRefCount::s_ulcModuleRef
0x180027ea5  add     eax, r15d
0x180027ea8  cmp     eax, 7FFFFFFFh
0x180027ead  jb      short loc_180027EB5
0x180027eaf  lea     ecx, [r15+0Dh]
0x180027eb3  int     29h; Win8: RtlFailFast(ecx)
0x180027eb5  lea     rcx, [rdi+18h]
0x180027eb9  call    ??0?$HubTask@J$0A@@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HubTask<long,0>::HubTask<long,0>(void)
0x180027ebe  nop
0x180027ebf  lea     rax, ??_7EtwCollectionSessionRelogger@StandardCollector@DiagnosticsHub@Microsoft@@6BITraceEventCallback@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `ITraceEventCallback'}
0x180027ec6  mov     [rdi], rax
0x180027ec9  lea     rax, ??_7EtwCollectionSessionRelogger@StandardCollector@DiagnosticsHub@Microsoft@@6BCModuleRefCount@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `CModuleRefCount'}
0x180027ed0  mov     [rdi+8], rax
0x180027ed4  lea     rax, ??_7EtwCollectionSessionRelogger@StandardCollector@DiagnosticsHub@Microsoft@@6B?$HubTask@J$0A@@DiagHubCommon@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `DiagHubCommon::HubTask<long,0>'}
0x180027edb  mov     [rdi+18h], rax
0x180027edf  mov     [rdi+88h], r14d
0x180027ee6  lea     rcx, [rdi+90h]; lpCriticalSection
0x180027eed  xorps   xmm0, xmm0
0x180027ef0  xor     eax, eax
0x180027ef2  movups  xmmword ptr [rcx], xmm0
0x180027ef5  movups  xmmword ptr [rcx+10h], xmm0
0x180027ef9  mov     [rcx+20h], rax
0x180027efd  call    cs:__imp_InitializeCriticalSection
0x180027f03  nop
0x180027f04  lea     rbx, [rdi+0B8h]
0x180027f0b  xor     r14d, r14d
0x180027f0e  mov     [rbx], r14
0x180027f11  mov     [rbx+8], r14
0x180027f15  mov     [rbx+10h], r14
0x180027f19  mov     [rbx+18h], r14
0x180027f1d  mov     [rbx+20h], r14
0x180027f21  lea     ecx, [r14+10h]; Size
0x180027f25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027f2a  mov     [rax+8], r14
0x180027f2e  mov     [rbx], rax
0x180027f31  mov     [rax], rbx
0x180027f34  mov     [rdi+0E0h], r14
0x180027f3b  mov     [rdi+0E8h], r14
0x180027f42  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180027f46  mov     [rdi+0F0h], rbx
0x180027f4d  mov     [rdi+0F8h], r14d
0x180027f54  xor     r9d, r9d; lpName
0x180027f57  xor     r8d, r8d; bInitialState
0x180027f5a  mov     edx, r15d; bManualReset
0x180027f5d  xor     ecx, ecx; lpEventAttributes
0x180027f5f  call    cs:__imp_CreateEventW
0x180027f65  mov     [rdi+0F0h], rax
0x180027f6c  test    rax, rax
0x180027f6f  jnz     short loc_180027F94
0x180027f71  mov     [rdi+0F0h], rbx
0x180027f78  call    cs:__imp_GetLastError
0x180027f7e  movzx   ecx, ax
0x180027f81  or      ecx, 80070000h
0x180027f87  test    eax, eax
0x180027f89  cmovle  ecx, eax
0x180027f8c  mov     [rdi+0F8h], ecx
0x180027f92  jmp     short loc_180027FA8
0x180027f94  call    cs:__imp_GetLastError
0x180027f9a  cmp     eax, 0B7h
0x180027f9f  jnz     short loc_180027FA8
0x180027fa1  mov     [rdi+0F8h], r15d
0x180027fa8  mov     [rdi+100h], rbx
0x180027faf  mov     [rdi+108h], r14d
0x180027fb6  xor     r9d, r9d; lpName
0x180027fb9  xor     r8d, r8d; bInitialState
0x180027fbc  mov     edx, r15d; bManualReset
0x180027fbf  xor     ecx, ecx; lpEventAttributes
0x180027fc1  call    cs:__imp_CreateEventW
0x180027fc7  mov     [rdi+100h], rax
0x180027fce  test    rax, rax
0x180027fd1  jnz     short loc_180027FF6
0x180027fd3  mov     [rdi+100h], rbx
0x180027fda  call    cs:__imp_GetLastError
0x180027fe0  movzx   ecx, ax
0x180027fe3  or      ecx, 80070000h
0x180027fe9  test    eax, eax
0x180027feb  cmovle  ecx, eax
0x180027fee  mov     [rdi+108h], ecx
0x180027ff4  jmp     short loc_18002800A
0x180027ff6  call    cs:__imp_GetLastError
0x180027ffc  cmp     eax, 0B7h
0x180028001  jnz     short loc_18002800A
0x180028003  mov     [rdi+108h], r15d
0x18002800a  test    rsi, rsi
0x18002800d  jnz     short loc_180028040
0x18002800f  mov     [rdi+110h], r14
0x180028016  test    rbp, rbp
0x180028019  jnz     short loc_180028057
0x18002801b  mov     [rdi+118h], r14
0x180028022  test    rbp, rbp
0x180028025  jz      short loc_18002806E
0x180028027  test    rsi, rsi
0x18002802a  jz      short loc_18002806E
0x18002802c  mov     rax, rdi
0x18002802f  mov     rbx, [rsp+48h+arg_10]
0x180028034  add     rsp, 20h
0x180028038  pop     r15
0x18002803a  pop     r14
0x18002803c  pop     rdi
0x18002803d  pop     rsi
0x18002803e  pop     rbp
0x18002803f  retn
0x180028040  mov     rcx, rsi; psz
0x180028043  call    cs:__imp_SysAllocString
0x180028049  mov     [rdi+110h], rax
0x180028050  test    rax, rax
0x180028053  jz      short loc_180028088
0x180028055  jmp     short loc_180028016
0x180028057  mov     rcx, rbp; psz
0x18002805a  call    cs:__imp_SysAllocString
0x180028060  mov     [rdi+118h], rax
0x180028067  test    rax, rax
0x18002806a  jz      short loc_180028093
0x18002806c  jmp     short loc_180028022
0x18002806e  mov     [rsp+48h+pExceptionObject], 80004003h
0x180028076  lea     rdx, _TI1J; pThrowInfo
0x18002807d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180028082  call    _CxxThrowException_0
0x180028088  mov     ecx, 8007000Eh; int
0x18002808d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180028093  mov     ecx, 8007000Eh; int
0x180028098  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
