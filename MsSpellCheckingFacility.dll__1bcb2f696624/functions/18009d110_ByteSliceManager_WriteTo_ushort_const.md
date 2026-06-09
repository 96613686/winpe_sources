# ByteSliceManager::WriteTo(ushort const *)

- ea: `0x18009d110`
- end: `0x18009d1e0`
- name: `?WriteTo@ByteSliceManager@@UEBAXPEBG@Z`
- size: `208`
- prototype: `void __fastcall(ByteSliceManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18009c8b0`

## callees

- `0x180059744`
- `0x18005a400`
- `0x180061320`
- `0x18009d8a4`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009d1ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009d1ab`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18009d1a2`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18009d1a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009d175`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009d175`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ByteSliceManager::WriteTo(ByteSliceManager *this, const unsigned __int16 *a2, int *a3, bool a4)
{
  LPCWSTR v5; // r10
  HANDLE FileW; // rbx
  int v7[4]; // [rsp+40h] [rbp-E8h] BYREF
  GUID v8; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v9[80]; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE v10[96]; // [rsp+B0h] [rbp-78h] BYREF

  v7[0] = 0;
  CExceptionSetup::CExceptionSetup((CExceptionSetup *)v10, v7, a3, a4);
  FileW = CreateFileW(v5, 0x40000000u, 0, 0, 2u, 0x80000000, 0);
  *(_QWORD *)&v8.Data1 = FileW;
  ThrowIfFailed(FileW);
  try
  {
    (*(void (**)(void))(*(_QWORD *)this + 16LL))();
    FlushFileBuffers(FileW);
    CloseHandle(FileW);
    CExceptionSetup::~CExceptionSetup((CExceptionSetup *)v10);
  }
  catch ( CNLException v9 )
  {
    FlushFileBuffers(*(HANDLE *)&v8.Data1);
    CloseHandle(*(HANDLE *)&v8.Data1);
    v8 = GUID_NULL;
    CNLException::HandleIt((CNLException *)v9, (struct CExceptionSetup *)v10, &v8);
    CNLException::Throw((CNLException *)v9);
  }
}

```

## disassembly

```asm
0x18009d110  mov     r11, rsp
0x18009d113  mov     [r11+18h], rbx
0x18009d117  push    rdi
0x18009d118  sub     rsp, 120h
0x18009d11f  mov     rax, cs:__security_cookie
0x18009d126  xor     rax, rsp
0x18009d129  mov     [rsp+128h+var_18], rax
0x18009d131  mov     r10, rdx
0x18009d134  mov     rdi, rcx
0x18009d137  mov     [rsp+128h+var_E8], 0
0x18009d13f  lea     rdx, [rsp+128h+var_E8]; int *
0x18009d144  lea     rcx, [r11-78h]; this
0x18009d148  call    ??0CExceptionSetup@@QEAA@PEAJPEAH_N@Z; CExceptionSetup::CExceptionSetup(long *,int *,bool)
0x18009d14d  nop
0x18009d14e  mov     [rsp+128h+hTemplateFile], 0; hTemplateFile
0x18009d157  mov     [rsp+128h+dwFlagsAndAttributes], 80000000h; dwFlagsAndAttributes
0x18009d15f  mov     [rsp+128h+dwCreationDisposition], 2; dwCreationDisposition
0x18009d167  xor     r9d, r9d; lpSecurityAttributes
0x18009d16a  xor     r8d, r8d; dwShareMode
0x18009d16d  mov     edx, 40000000h; dwDesiredAccess
0x18009d172  mov     rcx, r10; lpFileName
0x18009d175  call    cs:__imp_CreateFileW
0x18009d17b  mov     rbx, rax
0x18009d17e  mov     qword ptr [rsp+128h+var_D8], rax
0x18009d183  mov     rcx, rax; void *
0x18009d186  call    ?ThrowIfFailed@@YAXPEBX@Z; ThrowIfFailed(void const *)
0x18009d18b  nop
0x18009d18c  mov     rdx, [rdi]
0x18009d18f  mov     rax, [rdx+10h]
0x18009d193  mov     rdx, rbx
0x18009d196  mov     rcx, rdi
0x18009d199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d19e  nop
0x18009d19f  mov     rcx, rbx; hFile
0x18009d1a2  call    cs:__imp_FlushFileBuffers
0x18009d1a8  mov     rcx, rbx; hObject
0x18009d1ab  call    cs:__imp_CloseHandle
0x18009d1b1  nop
0x18009d1b2  lea     rcx, [rsp+128h+var_78]; this
0x18009d1ba  call    ??1CExceptionSetup@@QEAA@XZ; CExceptionSetup::~CExceptionSetup(void)
0x18009d1bf  mov     rcx, [rsp+128h+var_18]
0x18009d1c7  xor     rcx, rsp; StackCookie
0x18009d1ca  call    __security_check_cookie
0x18009d1cf  mov     rbx, [rsp+128h+arg_10]
0x18009d1d7  add     rsp, 120h
0x18009d1de  pop     rdi
0x18009d1df  retn
```
