# CRPCServiceManager::WaitForServiceTermination(void)

- ea: `0x180012580`
- end: `0x18001262a`
- name: `?WaitForServiceTermination@CRPCServiceManager@@QEAAKXZ`
- size: `170`
- prototype: `__int64 __fastcall(CRPCServiceManager *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000dd00`

## callees

- `0x180012580`
- `0x18001af7c`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800125ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012612`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800125ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012601`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012601`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125f2`

## pseudocode

```c
__int64 __fastcall CRPCServiceManager::WaitForServiceTermination(CRPCServiceManager *this)
{
  int v2; // edx
  __int64 v3; // rcx
  DWORD v4; // esi
  int v5; // ebx
  int v6; // edx
  __int64 v7; // rcx

  if ( *(_DWORD *)&gDebugLevel )
    _DebugMsg(4, 0xCB9u);
  v4 = WaitForSingleObject(*((HANDLE *)this + 8), 0xFFFFFFFF);
  if ( *(_DWORD *)&gDebugLevel )
    _DebugMsg(4, 0xCBAu);
  if ( !v4 )
  {
    LogTime(v3, v2);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    *((_DWORD *)this + 33) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    v5 = *((_DWORD *)this + 34);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( v5 )
      v4 = WaitForSingleObject(*((HANDLE *)this + 10), 0xFFFFFFFF);
    LogTime(v7, v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180012580  push    rbx
0x180012582  push    rbp
0x180012583  push    rsi
0x180012584  push    rdi
0x180012585  sub     rsp, 28h
0x180012589  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180012590  mov     rbp, rcx
0x180012593  mov     ebx, 4
0x180012598  jz      short loc_1800125A6
0x18001259a  mov     edx, 0CB9h; unsigned int
0x18001259f  mov     ecx, ebx; unsigned int
0x1800125a1  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800125a6  mov     rcx, [rbp+40h]; hHandle
0x1800125aa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800125ad  call    cs:__imp_WaitForSingleObject
0x1800125b3  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x1800125ba  mov     esi, eax
0x1800125bc  jz      short loc_1800125CA
0x1800125be  mov     edx, 0CBAh; unsigned int
0x1800125c3  mov     ecx, ebx; unsigned int
0x1800125c5  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800125ca  test    esi, esi
0x1800125cc  jnz     short loc_18001261F
0x1800125ce  call    ?LogTime@@YAXXZ; LogTime(void)
0x1800125d3  lea     rdi, [rbp+58h]
0x1800125d7  mov     rcx, rdi; lpCriticalSection
0x1800125da  call    cs:__imp_EnterCriticalSection
0x1800125e0  mov     rcx, rdi; lpCriticalSection
0x1800125e3  mov     [rbp+84h], esi
0x1800125e9  call    cs:__imp_LeaveCriticalSection
0x1800125ef  mov     rcx, rdi; lpCriticalSection
0x1800125f2  call    cs:__imp_EnterCriticalSection
0x1800125f8  mov     ebx, [rbp+88h]
0x1800125fe  mov     rcx, rdi; lpCriticalSection
0x180012601  call    cs:__imp_LeaveCriticalSection
0x180012607  test    ebx, ebx
0x180012609  jz      short loc_18001261A
0x18001260b  mov     rcx, [rbp+50h]; hHandle
0x18001260f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012612  call    cs:__imp_WaitForSingleObject
0x180012618  mov     esi, eax
0x18001261a  call    ?LogTime@@YAXXZ; LogTime(void)
0x18001261f  mov     eax, esi
0x180012621  add     rsp, 28h
0x180012625  pop     rdi
0x180012626  pop     rsi
0x180012627  pop     rbp
0x180012628  pop     rbx
0x180012629  retn
```
