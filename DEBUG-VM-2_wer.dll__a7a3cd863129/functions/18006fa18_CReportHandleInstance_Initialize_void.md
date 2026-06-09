# CReportHandleInstance::Initialize(void)

- ea: `0x18006fa18`
- end: `0x18006fabb`
- name: `?Initialize@CReportHandleInstance@@QEAAJXZ`
- size: `163`
- prototype: `__int64 __fastcall(CReportHandleInstance *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180030fc0`
- `0x18004015c`

## callees

- `0x18000716c`
- `0x180007e34`
- `0x18006fa18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fa5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fa5e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fa41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fa86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fa41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fa86`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006faa8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006faa8`

## pseudocode

```c
__int64 __fastcall CReportHandleInstance::Initialize(CReportHandleInstance *this)
{
  HANDLE *v1; // rbx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  HANDLE v6; // rax

  v1 = (HANDLE *)((char *)this + 56);
  if ( (*((_QWORD *)this + 7) == -1 || *((_QWORD *)this + 7) == 0)
    && (EventW = CreateEventW(0, 1, 1, 0),
        tlx::unique_any<tlx::file_handle_traits>::reset(v1, EventW),
        *v1 == (HANDLE)-1LL || (char *)*v1 + 1 == HANDLE_FLAG_INHERIT)
    || (*((_QWORD *)this + 8) == -1 || *((_QWORD *)this + 8) == 0)
    && (v6 = CreateEventW(0, 1, 0, 0),
        tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 64, v6),
        *((_QWORD *)this + 8) == -1 || *((_QWORD *)this + 8) == 0) )
  {
    LastError = GetLastError();
    return ERROR_HR_FROM_WIN32(LastError);
  }
  else
  {
    SetEvent(*v1);
    return 0;
  }
}

```

## disassembly

```asm
0x18006fa18  mov     [rsp+arg_0], rbx
0x18006fa1d  push    rdi
0x18006fa1e  sub     rsp, 20h
0x18006fa22  lea     rbx, [rcx+38h]
0x18006fa26  mov     rdi, rcx
0x18006fa29  mov     rax, [rbx]
0x18006fa2c  inc     rax
0x18006fa2f  cmp     rax, 1
0x18006fa33  ja      short loc_18006FA6D
0x18006fa35  xor     r9d, r9d; lpName
0x18006fa38  xor     ecx, ecx; lpEventAttributes
0x18006fa3a  lea     edx, [r9+1]; bManualReset
0x18006fa3e  mov     r8d, edx; bInitialState
0x18006fa41  call    cs:__imp_CreateEventW
0x18006fa47  mov     rdx, rax
0x18006fa4a  mov     rcx, rbx
0x18006fa4d  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18006fa52  mov     rax, [rbx]
0x18006fa55  inc     rax
0x18006fa58  cmp     rax, 1
0x18006fa5c  ja      short loc_18006FA6D
0x18006fa5e  call    cs:__imp_GetLastError
0x18006fa64  mov     ecx, eax; unsigned int
0x18006fa66  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006fa6b  jmp     short loc_18006FAB0
0x18006fa6d  mov     rax, [rdi+40h]
0x18006fa71  inc     rax
0x18006fa74  cmp     rax, 1
0x18006fa78  ja      short loc_18006FAA5
0x18006fa7a  xor     r9d, r9d; lpName
0x18006fa7d  xor     r8d, r8d; bInitialState
0x18006fa80  xor     ecx, ecx; lpEventAttributes
0x18006fa82  lea     edx, [r9+1]; bManualReset
0x18006fa86  call    cs:__imp_CreateEventW
0x18006fa8c  mov     rdx, rax
0x18006fa8f  lea     rcx, [rdi+40h]
0x18006fa93  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18006fa98  mov     rax, [rdi+40h]
0x18006fa9c  inc     rax
0x18006fa9f  cmp     rax, 1
0x18006faa3  jbe     short loc_18006FA5E
0x18006faa5  mov     rcx, [rbx]; hEvent
0x18006faa8  call    cs:__imp_SetEvent
0x18006faae  xor     eax, eax
0x18006fab0  mov     rbx, [rsp+28h+arg_0]
0x18006fab5  add     rsp, 20h
0x18006fab9  pop     rdi
0x18006faba  retn
```
