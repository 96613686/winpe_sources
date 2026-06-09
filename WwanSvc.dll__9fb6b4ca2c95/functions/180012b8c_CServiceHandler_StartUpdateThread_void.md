# CServiceHandler::StartUpdateThread(void)

- ea: `0x180012b8c`
- end: `0x180012c30`
- name: `?StartUpdateThread@CServiceHandler@@AEAAJXZ`
- size: `164`
- prototype: `__int64 __fastcall(CServiceHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180012c38`

## callees

- `0x18000e99c`
- `0x180012b8c`
- `0x18001387c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012ba3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bed`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012bd4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012bd4`

## string_xrefs

- `0x180012c0b`: `onecoreuap\net\wwan\service\core\servicemain.cpp`

## pseudocode

```c
__int64 __fastcall CServiceHandler::StartUpdateThread(CServiceHandler *this)
{
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  EventW = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 80, EventW);
  Thread = CreateThread(0, 0, CServiceHandler::_StopThreadProc, this, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 72, Thread);
  if ( *((_QWORD *)this + 9) )
    return 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\servicemain.cpp",
      (const char *)v5,
      dwCreationFlags);
  return v5;
}

```

## disassembly

```asm
0x180012b8c  mov     [rsp+arg_0], rbx
0x180012b91  push    rdi
0x180012b92  sub     rsp, 30h
0x180012b96  mov     rdi, rcx
0x180012b99  xor     r9d, r9d; lpName
0x180012b9c  xor     ecx, ecx; lpEventAttributes
0x180012b9e  xor     r8d, r8d; bInitialState
0x180012ba1  xor     edx, edx; bManualReset
0x180012ba3  call    cs:__imp_CreateEventW
0x180012ba9  mov     rdx, rax
0x180012bac  lea     rcx, [rdi+50h]
0x180012bb0  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180012bb5  mov     r9, rdi; lpParameter
0x180012bb8  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180012bc1  lea     r8, ?_StopThreadProc@CServiceHandler@@CAKPEAX@Z; lpStartAddress
0x180012bc8  mov     [rsp+38h+dwCreationFlags], 0; int
0x180012bd0  xor     edx, edx; dwStackSize
0x180012bd2  xor     ecx, ecx; lpThreadAttributes
0x180012bd4  call    cs:__imp_CreateThread
0x180012bda  mov     rdx, rax
0x180012bdd  lea     rcx, [rdi+48h]
0x180012be1  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180012be6  cmp     qword ptr [rdi+48h], 0
0x180012beb  jnz     short loc_180012C23
0x180012bed  call    cs:__imp_GetLastError
0x180012bf3  mov     ebx, eax
0x180012bf5  test    eax, eax
0x180012bf7  jle     short loc_180012C02
0x180012bf9  movzx   ebx, ax
0x180012bfc  or      ebx, 80070000h
0x180012c02  test    ebx, ebx
0x180012c04  jns     short loc_180012C1F
0x180012c06  mov     rcx, [rsp+38h]; this
0x180012c0b  lea     r8, aOnecoreuapNetW_6; "onecoreuap\\net\\wwan\\service\\core\\s"...
0x180012c12  mov     r9d, ebx; char *
0x180012c15  mov     edx, 1F1h; void *
0x180012c1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c1f  mov     eax, ebx
0x180012c21  jmp     short loc_180012C25
0x180012c23  xor     eax, eax
0x180012c25  mov     rbx, [rsp+38h+arg_0]
0x180012c2a  add     rsp, 30h
0x180012c2e  pop     rdi
0x180012c2f  retn
```
