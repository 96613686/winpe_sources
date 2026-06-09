# std::_Ref_count_obj2<StandardCollectorService::SessionLifetimeMonitor>::_Ref_count_obj2<StandardCollectorService::SessionLifetimeMonitor>(StandardCollectorService * &&,_GUID &,ushort &)

- ea: `0x180035f18`
- end: `0x1800360bc`
- name: `??$?0PEAVStandardCollectorService@@AEAU_GUID@@AEAG@?$_Ref_count_obj2@VSessionLifetimeMonitor@StandardCollectorService@@@std@@QEAA@$$QEAPEAVStandardCollectorService@@AEAU_GUID@@AEAG@Z`
- size: `420`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180032470`

## callees

- `0x1800357fc`
- `0x180035f18`
- `0x18004a03c`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180035f77`
- `KERNEL32!CreateEventW` at `0x180036060`
- `KERNEL32!CreateEventW` at `0x180035f77`
- `KERNEL32!CreateEventW` at `0x180036060`
- `KERNEL32!InitializeCriticalSection` at `0x180036015`
- `KERNEL32!InitializeCriticalSection` at `0x180036040`
- `KERNEL32!InitializeCriticalSection` at `0x180036015`
- `KERNEL32!InitializeCriticalSection` at `0x180036040`
- `KERNEL32!CloseHandle` at `0x180036089`
- `KERNEL32!CloseHandle` at `0x180036089`
- `KERNEL32!GetLastError` at `0x180035f8e`
- `KERNEL32!GetLastError` at `0x180035fa7`
- `KERNEL32!GetLastError` at `0x180035f8e`
- `KERNEL32!GetLastError` at `0x180035fa7`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall std::_Ref_count_obj2<StandardCollectorService::SessionLifetimeMonitor>::_Ref_count_obj2<StandardCollectorService::SessionLifetimeMonitor>(
        __int64 a1,
        __int64 *a2,
        _OWORD *a3,
        __int16 *a4)
{
  __int64 v5; // rdi
  __int16 v6; // bp
  __int64 v7; // rbx
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v10; // ecx
  _QWORD *v11; // rax
  int v12; // eax
  int pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  HANDLE hObject[6]; // [rsp+28h] [rbp-30h] BYREF

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<StandardCollectorService::SessionLifetimeMonitor>::`vftable';
  v5 = a1 + 16;
  hObject[1] = (HANDLE)(a1 + 16);
  v6 = *a4;
  v7 = *a2;
  *(_OWORD *)(a1 + 16) = *a3;
  *(_QWORD *)(a1 + 32) = -1;
  *(_DWORD *)(a1 + 40) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(v5 + 16) = EventW;
  if ( EventW )
  {
    if ( GetLastError() == 183 )
      *(_DWORD *)(v5 + 24) = 1;
  }
  else
  {
    *(_QWORD *)(v5 + 16) = -1;
    LastError = GetLastError();
    v10 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v10 = LastError;
    *(_DWORD *)(v5 + 24) = v10;
  }
  *(_QWORD *)(v5 + 32) = v7;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  *(_QWORD *)(v5 + 40) = 0;
  *(_QWORD *)(v5 + 48) = 0;
  v11 = operator new(0x20u);
  *v11 = v11;
  v11[1] = v11;
  v11[2] = v11;
  *((_WORD *)v11 + 12) = 257;
  *(_QWORD *)(v5 + 40) = v11;
  *(_OWORD *)(v5 + 56) = 0;
  *(_OWORD *)(v5 + 72) = 0;
  *(_QWORD *)(v5 + 88) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 56));
  *(_QWORD *)(v5 + 96) = 0;
  *(_QWORD *)(v5 + 104) = 0;
  *(_OWORD *)(v5 + 112) = 0;
  *(_OWORD *)(v5 + 128) = 0;
  *(_QWORD *)(v5 + 144) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 112));
  *(_BYTE *)(v5 + 152) = 0;
  *(_WORD *)(v5 + 154) = v6;
  hObject[0] = CreateEventW(0, 1, 0, 0);
  v12 = StandardCollectorService::SessionLifetimeMonitor::MonitorHandle((PVOID)v5, (struct ATL::CHandle *)hObject);
  if ( v12 < 0 )
  {
    pExceptionObject = v12;
    throw (long *)&pExceptionObject;
  }
  _mm_lfence();
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  return a1;
}

```

## disassembly

```asm
0x180035f18  mov     [rsp+arg_8], rbx
0x180035f1d  mov     [rsp+arg_10], rbp
0x180035f22  push    rsi
0x180035f23  push    rdi
0x180035f24  push    r15
0x180035f26  sub     rsp, 40h
0x180035f2a  mov     rsi, rcx
0x180035f2d  mov     r15d, 1
0x180035f33  mov     [rcx+8], r15d
0x180035f37  mov     [rcx+0Ch], r15d
0x180035f3b  lea     rax, ??_7?$_Ref_count_obj2@VSessionLifetimeMonitor@StandardCollectorService@@@std@@6B@; const std::_Ref_count_obj2<StandardCollectorService::SessionLifetimeMonitor>::`vftable'
0x180035f42  mov     [rcx], rax
0x180035f45  lea     rdi, [rcx+10h]
0x180035f49  mov     [rsp+58h+var_28], rdi
0x180035f4e  movzx   ebp, word ptr [r9]
0x180035f52  mov     rbx, [rdx]
0x180035f55  movups  xmm0, xmmword ptr [r8]
0x180035f59  movdqu  xmmword ptr [rdi], xmm0
0x180035f5d  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x180035f65  mov     dword ptr [rdi+18h], 0
0x180035f6c  xor     r9d, r9d; lpName
0x180035f6f  xor     r8d, r8d; bInitialState
0x180035f72  mov     edx, r15d; bManualReset
0x180035f75  xor     ecx, ecx; lpEventAttributes
0x180035f77  call    cs:__imp_CreateEventW
0x180035f7d  mov     [rdi+10h], rax
0x180035f81  test    rax, rax
0x180035f84  jnz     short loc_180035FA7
0x180035f86  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x180035f8e  call    cs:__imp_GetLastError
0x180035f94  movzx   ecx, ax
0x180035f97  or      ecx, 80070000h
0x180035f9d  test    eax, eax
0x180035f9f  cmovle  ecx, eax
0x180035fa2  mov     [rdi+18h], ecx
0x180035fa5  jmp     short loc_180035FB8
0x180035fa7  call    cs:__imp_GetLastError
0x180035fad  cmp     eax, 0B7h
0x180035fb2  jnz     short loc_180035FB8
0x180035fb4  mov     [rdi+18h], r15d
0x180035fb8  mov     [rdi+20h], rbx
0x180035fbc  test    rbx, rbx
0x180035fbf  jz      short loc_180035FD2
0x180035fc1  mov     rax, [rbx]
0x180035fc4  mov     rcx, rbx
0x180035fc7  mov     rax, [rax+8]
0x180035fcb  call    cs:__guard_dispatch_icall_fptr
0x180035fd1  nop
0x180035fd2  mov     qword ptr [rdi+28h], 0
0x180035fda  mov     qword ptr [rdi+30h], 0
0x180035fe2  mov     ecx, 20h ; ' '; Size
0x180035fe7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035fec  mov     [rax], rax
0x180035fef  mov     [rax+8], rax
0x180035ff3  mov     [rax+10h], rax
0x180035ff7  mov     word ptr [rax+18h], 101h
0x180035ffd  mov     [rdi+28h], rax
0x180036001  lea     rcx, [rdi+38h]; lpCriticalSection
0x180036005  xorps   xmm0, xmm0
0x180036008  xor     eax, eax
0x18003600a  movups  xmmword ptr [rcx], xmm0
0x18003600d  movups  xmmword ptr [rcx+10h], xmm0
0x180036011  mov     [rcx+20h], rax
0x180036015  call    cs:__imp_InitializeCriticalSection
0x18003601b  nop
0x18003601c  mov     qword ptr [rdi+60h], 0
0x180036024  mov     qword ptr [rdi+68h], 0
0x18003602c  lea     rcx, [rdi+70h]; lpCriticalSection
0x180036030  xorps   xmm0, xmm0
0x180036033  xor     eax, eax
0x180036035  movups  xmmword ptr [rcx], xmm0
0x180036038  movups  xmmword ptr [rcx+10h], xmm0
0x18003603c  mov     [rcx+20h], rax
0x180036040  call    cs:__imp_InitializeCriticalSection
0x180036046  nop
0x180036047  mov     byte ptr [rdi+98h], 0
0x18003604e  mov     [rdi+9Ah], bp
0x180036055  xor     r9d, r9d; lpName
0x180036058  xor     r8d, r8d; bInitialState
0x18003605b  mov     edx, r15d; bManualReset
0x18003605e  xor     ecx, ecx; lpEventAttributes
0x180036060  call    cs:__imp_CreateEventW
0x180036066  mov     [rsp+58h+hObject], rax
0x18003606b  lea     rdx, [rsp+58h+hObject]; struct ATL::CHandle *
0x180036070  mov     rcx, rdi; Context
0x180036073  call    ?MonitorHandle@SessionLifetimeMonitor@StandardCollectorService@@AEAAJAEAVCHandle@ATL@@@Z; StandardCollectorService::SessionLifetimeMonitor::MonitorHandle(ATL::CHandle &)
0x180036078  test    eax, eax
0x18003607a  js      short loc_1800360A6
0x18003607c  lfence
0x18003607f  mov     rcx, [rsp+58h+hObject]; hObject
0x180036084  test    rcx, rcx
0x180036087  jz      short loc_180036090
0x180036089  call    cs:__imp_CloseHandle
0x18003608f  nop
0x180036090  mov     rax, rsi
0x180036093  mov     rbx, [rsp+58h+arg_8]
0x180036098  mov     rbp, [rsp+58h+arg_10]
0x18003609d  add     rsp, 40h
0x1800360a1  pop     r15
0x1800360a3  pop     rdi
0x1800360a4  pop     rsi
0x1800360a5  retn
0x1800360a6  mov     [rsp+58h+pExceptionObject], eax
0x1800360aa  lea     rdx, _TI1J; pThrowInfo
0x1800360b1  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800360b6  call    _CxxThrowException_0
```
