# CHandlerCache::_FindHandlerInfo(CSyncMgrID const &,CHandlerInfo * *)

- ea: `0x180004f10`
- end: `0x180005104`
- name: `?_FindHandlerInfo@CHandlerCache@@AEAAJAEBVCSyncMgrID@@PEAPEAVCHandlerInfo@@@Z`
- size: `500`
- prototype: `HRESULT __fastcall(LPCRITICAL_SECTION lpCriticalSection, const WCHAR *, struct CHandlerInfo **)`
- caller_count: `24`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011480`
- `0x180011640`
- `0x1800117e8`
- `0x180011a50`
- `0x180011d60`
- `0x180011eb0`
- `0x180013684`
- `0x1800139a4`
- `0x180013a08`
- `0x180013bb8`
- `0x180013cd0`
- `0x180014c30`
- `0x180014ce4`
- `0x180015020`
- `0x18001522c`
- `0x1800152e0`
- `0x180015670`
- `0x180015700`
- `0x18001fa00`
- `0x18001fae0`
- `0x18001fba0`
- `0x18001fc70`
- `0x1800204a4`
- `0x18002095c`

## callees

- `0x180004f10`
- `0x180005d30`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000505d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000508a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000505d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000508a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004fc4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004fc4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004f3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004f3b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800050bb`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800050bb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000504a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000504a`

## pseudocode

```c
HRESULT __fastcall CHandlerCache::_FindHandlerInfo(
        LPCRITICAL_SECTION lpCriticalSection,
        const WCHAR *a2,
        struct CHandlerInfo **a3)
{
  HANDLE *p_OwningThread; // rdi
  int v7; // ebp
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  int v9; // ebx
  int v10; // r12d
  signed int v11; // ecx
  __int64 (__fastcall *v12)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD); // rax
  PRTL_CRITICAL_SECTION_DEBUG v13; // rbx
  __int64 v14; // rdi
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  int *v16; // rax
  int v17; // r15d
  __int64 (__fastcall *v18)(__int64, _QWORD); // rax
  __int64 v19; // rbx
  __int64 v20; // rbx
  HRESULT result; // eax
  DWORD dwindex; // [rsp+70h] [rbp+8h] BYREF
  DWORD v23; // [rsp+80h] [rbp+18h]

  p_OwningThread = &lpCriticalSection[10].OwningThread;
  v7 = 0;
  while ( 1 )
  {
    v23 = WaitForSingleObject(*p_OwningThread, 0);
    EnterCriticalSection(lpCriticalSection);
    DebugInfo = lpCriticalSection[1].DebugInfo;
    v9 = -2147024894;
    *a3 = 0;
    if ( DebugInfo )
    {
      v10 = *(_DWORD *)&DebugInfo->Type;
      v11 = 0;
      dwindex = 0;
      if ( v10 > 0 )
      {
        while ( 2 )
        {
          v12 = (__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))qword_1800701D0;
          v13 = lpCriticalSection[1].DebugInfo;
          if ( qword_1800701D0 == -1 )
          {
            GetProcFromComCtl32(&qword_1800701D0, 332);
            v12 = (__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))qword_1800701D0;
            v11 = dwindex;
          }
          if ( v12 )
            v14 = v12(v13, v11);
          else
            v14 = 0;
          v15 = *(struct _RTL_CRITICAL_SECTION **)(v14 + 48);
          *a3 = 0;
          EnterCriticalSection(v15);
          v16 = *(int **)(v14 + 40);
          if ( v16 )
            v17 = *v16;
          else
            v17 = 0;
          while ( v7 < v17 )
          {
            v18 = (__int64 (__fastcall *)(__int64, _QWORD))qword_1800701D0;
            v19 = *(_QWORD *)(v14 + 40);
            if ( qword_1800701D0 == -1 )
            {
              GetProcFromComCtl32(&qword_1800701D0, 332);
              v18 = (__int64 (__fastcall *)(__int64, _QWORD))qword_1800701D0;
            }
            if ( v18 )
              v20 = v18(v19, v7);
            else
              v20 = 0;
            if ( CompareStringW(0x7Fu, 1u, a2 + 8, -1, (PCNZWCH)(v20 + 116), -1) == 2 )
            {
              *a3 = (struct CHandlerInfo *)v20;
              _InterlockedIncrement((volatile signed __int32 *)(v20 + 2076));
              LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v14 + 48));
              v9 = 0;
              LeaveCriticalSection(lpCriticalSection);
              return v9;
            }
            ++v7;
          }
          LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v14 + 48));
          v9 = -2147024894;
          v11 = dwindex + 1;
          v7 = 0;
          dwindex = v11;
          if ( v11 < v10 )
            continue;
          break;
        }
        p_OwningThread = &lpCriticalSection[10].OwningThread;
      }
    }
    LeaveCriticalSection(lpCriticalSection);
    if ( v23 != 258 )
      return v9;
    dwindex = 0;
    result = CoWaitForMultipleHandles(0, 0x1F4u, 1u, p_OwningThread, &dwindex);
    if ( result == -2147024809 )
      return result;
  }
}

```

## disassembly

```asm
0x180004f10  mov     [rsp+arg_8], rbx
0x180004f15  push    rbp
0x180004f16  push    rsi
0x180004f17  push    rdi
0x180004f18  push    r12
0x180004f1a  push    r13
0x180004f1c  push    r14
0x180004f1e  push    r15
0x180004f20  sub     rsp, 30h
0x180004f24  mov     r14, r8
0x180004f27  lea     rdi, [rcx+1A0h]
0x180004f2e  mov     r13, rdx
0x180004f31  mov     rsi, rcx
0x180004f34  xor     ebp, ebp
0x180004f36  mov     rcx, [rdi]; hHandle
0x180004f39  xor     edx, edx; dwMilliseconds
0x180004f3b  call    cs:__imp_WaitForSingleObject
0x180004f41  mov     rcx, rsi; lpCriticalSection
0x180004f44  mov     [rsp+68h+arg_10], eax
0x180004f4b  call    cs:__imp_EnterCriticalSection
0x180004f51  mov     rcx, [rsi+28h]
0x180004f55  mov     ebx, 80070002h
0x180004f5a  mov     [r14], rbp
0x180004f5d  test    rcx, rcx
0x180004f60  jz      loc_180005087
0x180004f66  mov     r12d, [rcx]
0x180004f69  mov     ecx, ebp
0x180004f6b  mov     [rsp+68h+dwindex], ecx
0x180004f6f  test    r12d, r12d
0x180004f72  jle     loc_180005087
0x180004f78  mov     rax, cs:qword_1800701D0
0x180004f7f  mov     rbx, [rsi+28h]
0x180004f83  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004f87  jnz     short loc_180004FA5
0x180004f89  mov     edx, 14Ch
0x180004f8e  lea     rcx, qword_1800701D0
0x180004f95  call    _GetProcFromComCtl32
0x180004f9a  mov     rax, cs:qword_1800701D0
0x180004fa1  mov     ecx, [rsp+68h+dwindex]
0x180004fa5  test    rax, rax
0x180004fa8  jz      short loc_180004FBA
0x180004faa  movsxd  rdx, ecx
0x180004fad  mov     rcx, rbx
0x180004fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb5  mov     rdi, rax
0x180004fb8  jmp     short loc_180004FBD
0x180004fba  mov     rdi, rbp
0x180004fbd  mov     rcx, [rdi+30h]; lpCriticalSection
0x180004fc1  mov     [r14], rbp
0x180004fc4  call    cs:__imp_EnterCriticalSection
0x180004fca  mov     rax, [rdi+28h]
0x180004fce  test    rax, rax
0x180004fd1  jz      short loc_180004FD8
0x180004fd3  mov     r15d, [rax]
0x180004fd6  jmp     short loc_180004FE0
0x180004fd8  mov     r15d, ebp
0x180004fdb  nop     dword ptr [rax+rax+00h]
0x180004fe0  cmp     ebp, r15d
0x180004fe3  jge     short loc_180005059
0x180004fe5  mov     rax, cs:qword_1800701D0
0x180004fec  mov     rbx, [rdi+28h]
0x180004ff0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004ff4  jnz     short loc_18000500E
0x180004ff6  mov     edx, 14Ch
0x180004ffb  lea     rcx, qword_1800701D0
0x180005002  call    _GetProcFromComCtl32
0x180005007  mov     rax, cs:qword_1800701D0
0x18000500e  test    rax, rax
0x180005011  jz      short loc_180005023
0x180005013  movsxd  rdx, ebp
0x180005016  mov     rcx, rbx
0x180005019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000501e  mov     rbx, rax
0x180005021  jmp     short loc_180005025
0x180005023  xor     ebx, ebx
0x180005025  lea     rax, [rbx+74h]
0x180005029  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180005031  lea     r8, [r13+10h]; lpString1
0x180005035  mov     [rsp+68h+lpString2], rax; lpString2
0x18000503a  mov     edx, 1; dwCmpFlags
0x18000503f  mov     ecx, 7Fh; Locale
0x180005044  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000504a  call    cs:__imp_CompareStringW
0x180005050  cmp     eax, 2
0x180005053  jz      short loc_1800050CE
0x180005055  inc     ebp
0x180005057  jmp     short loc_180004FE0
0x180005059  mov     rcx, [rdi+30h]; lpCriticalSection
0x18000505d  call    cs:__imp_LeaveCriticalSection
0x180005063  mov     ecx, [rsp+68h+dwindex]
0x180005067  mov     ebx, 80070002h
0x18000506c  inc     ecx
0x18000506e  mov     ebp, 0
0x180005073  mov     [rsp+68h+dwindex], ecx
0x180005077  cmp     ecx, r12d
0x18000507a  jl      loc_180004F78
0x180005080  lea     rdi, [rsi+1A0h]
0x180005087  mov     rcx, rsi; lpCriticalSection
0x18000508a  call    cs:__imp_LeaveCriticalSection
0x180005090  cmp     [rsp+68h+arg_10], 102h
0x18000509b  jnz     short loc_1800050ED
0x18000509d  lea     rax, [rsp+68h+dwindex]
0x1800050a2  mov     [rsp+68h+dwindex], ebp
0x1800050a6  mov     r9, rdi; pHandles
0x1800050a9  mov     [rsp+68h+lpString2], rax; lpdwindex
0x1800050ae  mov     edx, 1F4h; dwTimeout
0x1800050b3  xor     ecx, ecx; dwFlags
0x1800050b5  mov     r8d, 1; cHandles
0x1800050bb  call    cs:__imp_CoWaitForMultipleHandles
0x1800050c1  cmp     eax, 80070057h
0x1800050c6  jnz     loc_180004F36
0x1800050cc  jmp     short loc_1800050EF
0x1800050ce  mov     [r14], rbx
0x1800050d1  lock inc dword ptr [rbx+81Ch]
0x1800050d8  mov     rcx, [rdi+30h]; lpCriticalSection
0x1800050dc  call    cs:__imp_LeaveCriticalSection
0x1800050e2  mov     rcx, rsi; lpCriticalSection
0x1800050e5  xor     ebx, ebx
0x1800050e7  call    cs:__imp_LeaveCriticalSection
0x1800050ed  mov     eax, ebx
0x1800050ef  mov     rbx, [rsp+68h+arg_8]
0x1800050f4  add     rsp, 30h
0x1800050f8  pop     r15
0x1800050fa  pop     r14
0x1800050fc  pop     r13
0x1800050fe  pop     r12
0x180005100  pop     rdi
0x180005101  pop     rsi
0x180005102  pop     rbp
0x180005103  retn
```
