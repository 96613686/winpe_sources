# CSyncService::Start(void)

- ea: `0x180021980`
- end: `0x180021a1f`
- name: `?Start@CSyncService@@UEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(CSyncService *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180012d1c`
- `0x180021980`

## import_xrefs

- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x1800219f8`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x1800219f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800219c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800219c6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800219a0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800219a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021a04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021a04`

## string_xrefs

- `0x18002198d`: `Local\SyncServiceThread`

## pseudocode

```c
__int64 __fastcall CSyncService::Start(CSyncService *this)
{
  unsigned int v2; // ebx
  HANDLE MutexW; // rax
  DWORD LastError; // eax
  void *v5; // rcx

  v2 = -2147024713;
  MutexW = CreateMutexW(0, 1, L"Local\\SyncServiceThread");
  *((_QWORD *)this + 2) = MutexW;
  if ( MutexW )
  {
    LastError = GetLastError();
    v5 = (void *)*((_QWORD *)this + 2);
    if ( LastError == 183 )
    {
      CloseHandle(v5);
      *((_QWORD *)this + 2) = 0;
    }
    else
    {
      *((_BYTE *)this + 8) = 0;
      if ( !WaitForSingleObject(v5, 0) )
      {
        v2 = 0;
        RegisterClassObjects();
      }
      *((_QWORD *)this + 4) = SHCreateWorkerWindowW(CSyncService::s_HiddenWindowProc, 0, 0, 0, 0, 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180021980  mov     [rsp+arg_0], rbx
0x180021985  push    rdi
0x180021986  sub     rsp, 30h
0x18002198a  mov     rdi, rcx
0x18002198d  lea     r8, aLocalSyncservi; "Local\\SyncServiceThread"
0x180021994  xor     ecx, ecx; lpMutexAttributes
0x180021996  mov     edx, 1; bInitialOwner
0x18002199b  mov     ebx, 800700B7h
0x1800219a0  call    cs:__imp_CreateMutexW
0x1800219a6  mov     [rdi+10h], rax
0x1800219aa  test    rax, rax
0x1800219ad  jz      short loc_180021A12
0x1800219af  call    cs:__imp_GetLastError
0x1800219b5  mov     rcx, [rdi+10h]; hObject
0x1800219b9  cmp     eax, 0B7h
0x1800219be  jz      short loc_180021A04
0x1800219c0  xor     edx, edx; dwMilliseconds
0x1800219c2  mov     byte ptr [rdi+8], 0
0x1800219c6  call    cs:__imp_WaitForSingleObject
0x1800219cc  test    eax, eax
0x1800219ce  jnz     short loc_1800219D7
0x1800219d0  xor     ebx, ebx
0x1800219d2  call    ?RegisterClassObjects@@YAJXZ; RegisterClassObjects(void)
0x1800219d7  mov     [rsp+38h+var_10], 0
0x1800219e0  lea     rcx, ?s_HiddenWindowProc@CSyncService@@CA_JPEAUHWND__@@I_K_J@Z; CSyncService::s_HiddenWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800219e7  xor     r9d, r9d
0x1800219ea  mov     [rsp+38h+var_18], 0
0x1800219f3  xor     r8d, r8d
0x1800219f6  xor     edx, edx
0x1800219f8  call    cs:__imp_SHCreateWorkerWindowW
0x1800219fe  mov     [rdi+20h], rax
0x180021a02  jmp     short loc_180021A12
0x180021a04  call    cs:__imp_CloseHandle
0x180021a0a  mov     qword ptr [rdi+10h], 0
0x180021a12  mov     eax, ebx
0x180021a14  mov     rbx, [rsp+38h+arg_0]
0x180021a19  add     rsp, 30h
0x180021a1d  pop     rdi
0x180021a1e  retn
```
