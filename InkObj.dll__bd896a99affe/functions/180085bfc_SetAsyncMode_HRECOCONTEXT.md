# SetAsyncMode(HRECOCONTEXT__ *)

- ea: `0x180085bfc`
- end: `0x180085d41`
- name: `?SetAsyncMode@@YAJPEAUHRECOCONTEXT__@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(HRECOCONTEXT ArgList)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180069d70`
- `0x1800861a8`
- `0x1800a4810`

## callees

- `0x180085bfc`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180085cf3`
- `msvcrt!_beginthreadex` at `0x180085cf3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180085c67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180085c86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180085d05`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180085c67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180085c86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180085d05`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180085c35`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180085c35`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180085c55`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180085c55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085c90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085d0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085c90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085d0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085d21`

## pseudocode

```c
__int64 __fastcall SetAsyncMode(HRECOCONTEXT ArgList)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  HANDLE EventW; // rax
  _QWORD *v5; // rax
  uintptr_t v6; // rax
  void *v7; // rcx

  if ( !ArgList )
    return 2147500035LL;
  if ( *((_QWORD *)ArgList + 2) )
    return 2147746356LL;
  v3 = (struct _RTL_CRITICAL_SECTION *)(ArgList + 12);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(ArgList + 12), 0x8001FA0u) )
    return 2147942414LL;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)ArgList + 4) = EventW;
  if ( !EventW )
  {
    DeleteCriticalSection(v3);
    return 2147942414LL;
  }
  v5 = CoTaskMemAlloc(0x20u);
  *((_QWORD *)ArgList + 5) = v5;
  if ( !v5 )
  {
    DeleteCriticalSection(v3);
    CloseHandle(*((HANDLE *)ArgList + 4));
    *((_QWORD *)ArgList + 4) = 0;
    return 2147942414LL;
  }
  *v5 = 0;
  *(_QWORD *)(*((_QWORD *)ArgList + 5) + 8LL) = 0;
  *(_DWORD *)(*((_QWORD *)ArgList + 5) + 16LL) = 0;
  *(_DWORD *)(*((_QWORD *)ArgList + 5) + 20LL) = 0;
  *(_DWORD *)(*((_QWORD *)ArgList + 5) + 24LL) = 0;
  v6 = _beginthreadex(0, 0, (_beginthreadex_proc_type)BackgroundProcess, ArgList, 0, (unsigned int *)ArgList + 6);
  *((_QWORD *)ArgList + 2) = v6;
  if ( !v6 )
  {
    DeleteCriticalSection(v3);
    CloseHandle(*((HANDLE *)ArgList + 4));
    v7 = (void *)*((_QWORD *)ArgList + 5);
    *((_QWORD *)ArgList + 4) = 0;
    CoTaskMemFree(v7);
    *((_QWORD *)ArgList + 5) = 0;
    return 2147942414LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180085bfc  mov     [rsp+arg_0], rbx
0x180085c01  push    rdi
0x180085c02  sub     rsp, 30h
0x180085c06  mov     rbx, rcx
0x180085c09  test    rcx, rcx
0x180085c0c  jnz     short loc_180085C18
0x180085c0e  mov     eax, 80004003h
0x180085c13  jmp     loc_180085D36
0x180085c18  cmp     qword ptr [rcx+10h], 0
0x180085c1d  jz      short loc_180085C29
0x180085c1f  mov     eax, 80040234h
0x180085c24  jmp     loc_180085D36
0x180085c29  lea     rdi, [rcx+30h]
0x180085c2d  mov     edx, 8001FA0h; dwSpinCount
0x180085c32  mov     rcx, rdi; lpCriticalSection
0x180085c35  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180085c3b  test    eax, eax
0x180085c3d  jnz     short loc_180085C49
0x180085c3f  mov     eax, 8007000Eh
0x180085c44  jmp     loc_180085D36
0x180085c49  xor     r9d, r9d; lpName
0x180085c4c  xor     r8d, r8d; bInitialState
0x180085c4f  xor     ecx, ecx; lpEventAttributes
0x180085c51  lea     edx, [r9+1]; bManualReset
0x180085c55  call    cs:__imp_CreateEventW
0x180085c5b  mov     [rbx+20h], rax
0x180085c5f  test    rax, rax
0x180085c62  jnz     short loc_180085C6F
0x180085c64  mov     rcx, rdi; lpCriticalSection
0x180085c67  call    cs:__imp_DeleteCriticalSection
0x180085c6d  jmp     short loc_180085C3F
0x180085c6f  mov     ecx, 20h ; ' '; cb
0x180085c74  call    cs:__imp_CoTaskMemAlloc
0x180085c7a  mov     [rbx+28h], rax
0x180085c7e  test    rax, rax
0x180085c81  jnz     short loc_180085CA0
0x180085c83  mov     rcx, rdi; lpCriticalSection
0x180085c86  call    cs:__imp_DeleteCriticalSection
0x180085c8c  mov     rcx, [rbx+20h]; hObject
0x180085c90  call    cs:__imp_CloseHandle
0x180085c96  mov     qword ptr [rbx+20h], 0
0x180085c9e  jmp     short loc_180085C3F
0x180085ca0  mov     qword ptr [rax], 0
0x180085ca7  lea     r8, ?BackgroundProcess@@YAIPEAX@Z; StartAddress
0x180085cae  mov     rax, [rbx+28h]
0x180085cb2  mov     r9, rbx; ArgList
0x180085cb5  xor     edx, edx; StackSize
0x180085cb7  xor     ecx, ecx; Security
0x180085cb9  mov     qword ptr [rax+8], 0
0x180085cc1  mov     rax, [rbx+28h]
0x180085cc5  mov     dword ptr [rax+10h], 0
0x180085ccc  mov     rax, [rbx+28h]
0x180085cd0  mov     dword ptr [rax+14h], 0
0x180085cd7  mov     rax, [rbx+28h]
0x180085cdb  mov     dword ptr [rax+18h], 0
0x180085ce2  lea     rax, [rbx+18h]
0x180085ce6  mov     [rsp+38h+ThrdAddr], rax; ThrdAddr
0x180085ceb  mov     [rsp+38h+InitFlag], 0; InitFlag
0x180085cf3  call    cs:__imp__beginthreadex
0x180085cf9  mov     [rbx+10h], rax
0x180085cfd  test    rax, rax
0x180085d00  jnz     short loc_180085D34
0x180085d02  mov     rcx, rdi; lpCriticalSection
0x180085d05  call    cs:__imp_DeleteCriticalSection
0x180085d0b  mov     rcx, [rbx+20h]; hObject
0x180085d0f  call    cs:__imp_CloseHandle
0x180085d15  mov     rcx, [rbx+28h]; pv
0x180085d19  mov     qword ptr [rbx+20h], 0
0x180085d21  call    cs:__imp_CoTaskMemFree
0x180085d27  mov     qword ptr [rbx+28h], 0
0x180085d2f  jmp     loc_180085C3F
0x180085d34  xor     eax, eax
0x180085d36  mov     rbx, [rsp+38h+arg_0]
0x180085d3b  add     rsp, 30h
0x180085d3f  pop     rdi
0x180085d40  retn
```
