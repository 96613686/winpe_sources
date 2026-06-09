# CCPLUserMgrBroker::RunTaskFlow(TASK_FLOW_ID,HWND__ *,IUserManager *,ushort const *)

- ea: `0x1400034a0`
- end: `0x14000352e`
- name: `?RunTaskFlow@CCPLUserMgrBroker@@UEAAJW4TASK_FLOW_ID@@PEAUHWND__@@PEAUIUserManager@@PEBG@Z`
- size: `142`
- prototype: `signed int __fastcall(__int64, unsigned int, __int64, __int64, const WCHAR *lpName)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400034a0`
- `0x140007010`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x1400034c6`
- `KERNEL32!OpenEventW` at `0x1400034c6`
- `KERNEL32!GetLastError` at `0x140003511`
- `KERNEL32!GetLastError` at `0x140003511`
- `KERNEL32!CloseHandle` at `0x1400034e5`
- `KERNEL32!CloseHandle` at `0x1400034e5`

## pseudocode

```c
// AFR coverage: OpenEventW on supplied name for cancellation/event signaling, not file read/export.
signed int __fastcall CCPLUserMgrBroker::RunTaskFlow(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        const WCHAR *lpName)
{
  HANDLE v9; // rax
  char *v10; // rcx
  HANDLE v11; // rdi
  signed int result; // eax

  v9 = OpenEventW(0x100000u, 0, lpName);
  v10 = *(char **)(a1 + 32);
  v11 = v9;
  *(_QWORD *)(a1 + 32) = 0;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  *(_QWORD *)(a1 + 32) = v11;
  if ( *(_QWORD *)(a1 - 8 + 40) )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)(a1 - 8) + 32LL))(
             a1 - 8,
             a2,
             a3,
             a4);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400034a0  push    rbx; AFR coverage: OpenEventW on supplied name for cancellation/event signaling, not file read/export.
0x1400034a2  push    rbp
0x1400034a3  push    rsi
0x1400034a4  push    rdi
0x1400034a5  push    r14
0x1400034a7  sub     rsp, 30h
0x1400034ab  mov     rbp, r8
0x1400034ae  mov     r14d, edx
0x1400034b1  mov     r8, [rsp+58h+lpName]; lpName
0x1400034b9  mov     rbx, rcx
0x1400034bc  xor     edx, edx; bInheritHandle
0x1400034be  mov     ecx, 100000h; dwDesiredAccess
0x1400034c3  mov     rsi, r9
0x1400034c6  call    cs:__imp_OpenEventW
0x1400034cc  mov     rcx, [rbx+20h]; hObject
0x1400034d0  mov     rdi, rax
0x1400034d3  mov     qword ptr [rbx+20h], 0
0x1400034db  lea     r10, [rcx-1]
0x1400034df  cmp     r10, 0FFFFFFFFFFFFFFFDh
0x1400034e3  ja      short loc_1400034EB
0x1400034e5  call    cs:__imp_CloseHandle
0x1400034eb  lea     rcx, [rbx-8]
0x1400034ef  mov     [rbx+20h], rdi
0x1400034f3  cmp     qword ptr [rcx+28h], 0
0x1400034f8  jz      short loc_140003511
0x1400034fa  mov     rax, [rcx]
0x1400034fd  mov     r9, rsi
0x140003500  mov     r8, rbp
0x140003503  mov     edx, r14d
0x140003506  mov     rax, [rax+20h]
0x14000350a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000350f  jmp     short loc_140003523
0x140003511  call    cs:__imp_GetLastError
0x140003517  test    eax, eax
0x140003519  jle     short loc_140003523
0x14000351b  movzx   eax, ax
0x14000351e  or      eax, 80070000h
0x140003523  add     rsp, 30h
0x140003527  pop     r14
0x140003529  pop     rdi
0x14000352a  pop     rsi
0x14000352b  pop     rbp
0x14000352c  pop     rbx
0x14000352d  retn
```
