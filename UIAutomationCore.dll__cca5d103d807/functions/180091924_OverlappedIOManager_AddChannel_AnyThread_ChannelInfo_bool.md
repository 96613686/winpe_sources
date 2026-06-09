# OverlappedIOManager::AddChannel_AnyThread(ChannelInfo *,bool)

- ea: `0x180091924`
- end: `0x180091a79`
- name: `?AddChannel_AnyThread@OverlappedIOManager@@AEAAJPEAVChannelInfo@@_N@Z`
- size: `341`
- prototype: `__int64 __fastcall(OverlappedIOManager *__hidden this, struct ChannelInfo *, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180090d04`
- `0x180091868`
- `0x180092e10`

## callees

- `0x180091924`
- `0x1801334b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800919c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800919c6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180091a70`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180091a70`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180091a4f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180091a4f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180091946`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180091a65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180091946`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180091a65`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18009199b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180091a26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18009199b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180091a26`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800919e7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800919e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091962`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091962`

## string_xrefs

- `0x180091a10`: `CreateThread`
- `0x180091a09`: `Starting IO Thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OverlappedIOManager::AddChannel_AnyThread(
        OverlappedIOManager *this,
        struct ChannelInfo *a2,
        char a3)
{
  void *v6; // rsi
  int v7; // ebx
  __int64 v8; // rax
  HANDLE Thread; // rax
  HMODULE v11; // rcx
  unsigned int v12; // ebx

  WaitForSingleObject(*((HANDLE *)this + 6), 0xFFFFFFFF);
  v6 = (void *)*((_QWORD *)this + 6);
  if ( *((_QWORD *)this + 16)
    || (GetModuleHandleExW(4u, (LPCWSTR)OverlappedIOManager::StaticIoThreadProc, (HMODULE *)this + 21),
        Thread = CreateThread(0, 0, OverlappedIOManager::StaticIoThreadProc, this, 0, (LPDWORD)this + 30),
        (*((_QWORD *)this + 16) = Thread) != 0) )
  {
    v7 = *((_DWORD *)this + 30);
    if ( v7 == GetCurrentThreadId() )
    {
      *(_QWORD *)(&a2->ATSC + 1) = *((_QWORD *)this + 1);
      v8 = *((_QWORD *)this + 1);
      if ( v8 )
        *(_QWORD *)(v8 + 16) = a2;
      *((_QWORD *)this + 1) = a2;
      ++*((_DWORD *)this + 4);
      *((_DWORD *)this + 5) = 1;
    }
    else
    {
      *((_DWORD *)this + 35) = 1;
      *((_QWORD *)this + 18) = a2;
      *((_BYTE *)this + 136) = a3;
      SetEvent(*((HANDLE *)this + 7));
      if ( a3 )
        WaitForSingleObject(*((HANDLE *)this + 8), 0xFFFFFFFF);
    }
    if ( v6 )
      ReleaseMutex(v6);
    return 0;
  }
  else
  {
    v11 = (HMODULE)*((_QWORD *)this + 21);
    if ( v11 )
      FreeLibrary(v11);
    v12 = Error::Win32Error(L"CreateThread", L"Starting IO Thread");
    if ( v6 )
      ReleaseMutex(v6);
    return v12;
  }
}

```

## disassembly

```asm
0x180091924  mov     [rsp+arg_8], rbx
0x180091929  mov     [rsp+arg_10], rbp
0x18009192e  push    rsi
0x18009192f  push    rdi
0x180091930  push    r14
0x180091932  sub     rsp, 30h
0x180091936  mov     r14b, r8b
0x180091939  mov     rbp, rdx
0x18009193c  mov     rdi, rcx
0x18009193f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180091942  mov     rcx, [rcx+30h]; hHandle
0x180091946  call    cs:__imp_WaitForSingleObject
0x18009194c  mov     rsi, [rdi+30h]
0x180091950  mov     [rsp+48h+arg_0], rsi
0x180091955  lea     rbx, [rdi+78h]
0x180091959  cmp     qword ptr [rbx+8], 0
0x18009195e  jz      short loc_1800919B6
0x180091960  mov     ebx, [rbx]
0x180091962  call    cs:__imp_GetCurrentThreadId
0x180091968  cmp     ebx, eax
0x18009196a  jnz     loc_180091A33
0x180091970  mov     rax, [rdi+8]
0x180091974  mov     [rbp+8], rax
0x180091978  mov     rax, [rdi+8]
0x18009197c  test    rax, rax
0x18009197f  jz      short loc_180091985
0x180091981  mov     [rax+10h], rbp
0x180091985  mov     [rdi+8], rbp
0x180091989  inc     dword ptr [rdi+10h]
0x18009198c  mov     dword ptr [rdi+14h], 1
0x180091993  test    rsi, rsi
0x180091996  jz      short loc_1800919A1
0x180091998  mov     rcx, rsi; hMutex
0x18009199b  call    cs:__imp_ReleaseMutex
0x1800919a1  xor     eax, eax
0x1800919a3  mov     rbx, [rsp+48h+arg_8]
0x1800919a8  mov     rbp, [rsp+48h+arg_10]
0x1800919ad  add     rsp, 30h
0x1800919b1  pop     r14
0x1800919b3  pop     rdi
0x1800919b4  pop     rsi
0x1800919b5  retn
0x1800919b6  lea     r8, [rbx+30h]; phModule
0x1800919ba  lea     rdx, ?StaticIoThreadProc@OverlappedIOManager@@CAKPEAX@Z; lpModuleName
0x1800919c1  mov     ecx, 4; dwFlags
0x1800919c6  call    cs:__imp_GetModuleHandleExW
0x1800919cc  mov     [rsp+48h+lpThreadId], rbx; lpThreadId
0x1800919d1  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800919d9  mov     r9, rdi; lpParameter
0x1800919dc  lea     r8, ?StaticIoThreadProc@OverlappedIOManager@@CAKPEAX@Z; lpStartAddress
0x1800919e3  xor     edx, edx; dwStackSize
0x1800919e5  xor     ecx, ecx; lpThreadAttributes
0x1800919e7  call    cs:__imp_CreateThread
0x1800919ed  mov     [rdi+80h], rax
0x1800919f4  test    rax, rax
0x1800919f7  jnz     loc_180091960
0x1800919fd  mov     rcx, [rdi+0A8h]; hLibModule
0x180091a04  test    rcx, rcx
0x180091a07  jnz     short loc_180091A70
0x180091a09  lea     rdx, aStartingIoThre; "Starting IO Thread"
0x180091a10  lea     rcx, aCreatethread; "CreateThread"
0x180091a17  call    ?Win32Error@Error@@SAJPEBG0@Z; Error::Win32Error(ushort const *,ushort const *)
0x180091a1c  mov     ebx, eax
0x180091a1e  test    rsi, rsi
0x180091a21  jz      short loc_180091A2C
0x180091a23  mov     rcx, rsi; hMutex
0x180091a26  call    cs:__imp_ReleaseMutex
0x180091a2c  mov     eax, ebx
0x180091a2e  jmp     loc_1800919A3
0x180091a33  mov     dword ptr [rdi+8Ch], 1
0x180091a3d  mov     [rdi+90h], rbp
0x180091a44  mov     [rdi+88h], r14b
0x180091a4b  mov     rcx, [rdi+38h]; hEvent
0x180091a4f  call    cs:__imp_SetEvent
0x180091a55  test    r14b, r14b
0x180091a58  jz      loc_180091993
0x180091a5e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180091a61  mov     rcx, [rdi+40h]; hHandle
0x180091a65  call    cs:__imp_WaitForSingleObject
0x180091a6b  jmp     loc_180091993
0x180091a70  call    cs:__imp_FreeLibrary
0x180091a76  jmp     short loc_180091A09
```
