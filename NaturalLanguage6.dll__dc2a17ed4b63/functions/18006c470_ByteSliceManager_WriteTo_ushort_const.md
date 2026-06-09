# ByteSliceManager::WriteTo(ushort const *)

- ea: `0x18006c470`
- end: `0x18006c549`
- name: `?WriteTo@ByteSliceManager@@UEBAXPEBG@Z`
- size: `217`
- prototype: `void(ByteSliceManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18006bd20`

## callees

- `0x18003c174`
- `0x18005b8e0`
- `0x18005d6a0`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c514`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c4de`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c4de`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18006c50b`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18006c50b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ByteSliceManager::WriteTo(ByteSliceManager *this, const unsigned __int16 *a2, int *a3)
{
  HANDLE FileW; // rbx
  int v6[4]; // [rsp+40h] [rbp-D8h] BYREF
  GUID v7; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v8; // [rsp+60h] [rbp-B8h]
  _DWORD v9[16]; // [rsp+70h] [rbp-A8h] BYREF
  _BYTE v10[80]; // [rsp+B0h] [rbp-68h] BYREF
  void *retaddr; // [rsp+118h] [rbp+0h]

  v8 = -2;
  v6[0] = 0;
  CExceptionSetup::CExceptionSetup((CExceptionSetup *)v10, v6, a3);
  FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x80000000, 0);
  *(_QWORD *)&v7.Data1 = FileW;
  ThrowIfFailed(FileW);
  try
  {
    (*(void (__fastcall **)(ByteSliceManager *, HANDLE))(*(_QWORD *)this + 16LL))(this, FileW);
  }
  catch ( CNLException v9 )
  {
    FlushFileBuffers(*(HANDLE *)&v7.Data1);
    CloseHandle(*(HANDLE *)&v7.Data1);
    ImxTraceCatch(0, v9[2], retaddr);
    v7 = GUID_NULL;
    CNLException::HandleIt((CNLException *)v9, (struct CExceptionSetup *)v10, &v7);
    CNLException::Throw((CNLException *)v9);
  }
  FlushFileBuffers(FileW);
  CloseHandle(FileW);
  CExceptionSetup::~CExceptionSetup((CExceptionSetup *)v10);
}

```

## disassembly

```asm
0x18006c470  mov     r11, rsp
0x18006c473  push    rdi
0x18006c474  sub     rsp, 110h
0x18006c47b  mov     [rsp+118h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18006c484  mov     [r11+18h], rbx
0x18006c488  mov     rax, cs:__security_cookie
0x18006c48f  xor     rax, rsp
0x18006c492  mov     [rsp+118h+var_18], rax
0x18006c49a  mov     rbx, rdx
0x18006c49d  mov     rdi, rcx
0x18006c4a0  mov     [rsp+118h+var_D8], 0
0x18006c4a8  lea     rdx, [rsp+118h+var_D8]; int *
0x18006c4ad  lea     rcx, [r11-68h]; this
0x18006c4b1  call    ??0CExceptionSetup@@QEAA@PEAJPEAH@Z; CExceptionSetup::CExceptionSetup(long *,int *)
0x18006c4b6  nop
0x18006c4b7  mov     [rsp+118h+hTemplateFile], 0; hTemplateFile
0x18006c4c0  mov     [rsp+118h+dwFlagsAndAttributes], 80000000h; dwFlagsAndAttributes
0x18006c4c8  mov     [rsp+118h+dwCreationDisposition], 2; dwCreationDisposition
0x18006c4d0  xor     r9d, r9d; lpSecurityAttributes
0x18006c4d3  xor     r8d, r8d; dwShareMode
0x18006c4d6  mov     edx, 40000000h; dwDesiredAccess
0x18006c4db  mov     rcx, rbx; lpFileName
0x18006c4de  call    cs:__imp_CreateFileW
0x18006c4e4  mov     rbx, rax
0x18006c4e7  mov     qword ptr [rsp+118h+var_C8], rax
0x18006c4ec  mov     rcx, rax; void *
0x18006c4ef  call    ?ThrowIfFailed@@YAXPEBX@Z; ThrowIfFailed(void const *)
0x18006c4f4  nop
0x18006c4f5  mov     rdx, [rdi]
0x18006c4f8  mov     rax, [rdx+10h]
0x18006c4fc  mov     rdx, rbx
0x18006c4ff  mov     rcx, rdi
0x18006c502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c507  nop
0x18006c508  mov     rcx, rbx; hFile
0x18006c50b  call    cs:__imp_FlushFileBuffers
0x18006c511  mov     rcx, rbx; hObject
0x18006c514  call    cs:__imp_CloseHandle
0x18006c51a  nop
0x18006c51b  lea     rcx, [rsp+118h+var_68]; this
0x18006c523  call    ??1CExceptionSetup@@QEAA@XZ; CExceptionSetup::~CExceptionSetup(void)
0x18006c528  mov     rcx, [rsp+118h+var_18]
0x18006c530  xor     rcx, rsp; StackCookie
0x18006c533  call    __security_check_cookie
0x18006c538  mov     rbx, [rsp+118h+arg_10]
0x18006c540  add     rsp, 110h
0x18006c547  pop     rdi
0x18006c548  retn
```
