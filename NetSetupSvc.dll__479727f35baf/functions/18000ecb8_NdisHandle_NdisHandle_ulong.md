# NdisHandle::NdisHandle(ulong)

- ea: `0x18000ecb8`
- end: `0x18000ed39`
- name: `??0NdisHandle@@QEAA@K@Z`
- size: `129`
- prototype: `NdisHandle *__fastcall(NdisHandle *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000ee50`
- `0x18000efd0`

## callees

- `0x1800032e4`
- `0x180008c78`
- `0x18000ecb8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ecf5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ecf5`

## pseudocode

```c
NdisHandle *__fastcall NdisHandle::NdisHandle(NdisHandle *this)
{
  HANDLE FileW; // rcx
  _BYTE pExceptionObject[224]; // [rsp+48h] [rbp-E0h] BYREF

  FileW = CreateFileW(L"\\\\.\\NDIS", 0x40000000u, 7u, 0, 3u, 0, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, 6);
    throw (Win32Exception *)pExceptionObject;
  }
  *(_QWORD *)this = FileW;
  return this;
}

```

## disassembly

```asm
0x18000ecb8  push    rbx
0x18000ecba  sub     rsp, 120h
0x18000ecc1  xor     r9d, r9d; lpSecurityAttributes
0x18000ecc4  mov     [rsp+128h+var_E8], rcx
0x18000ecc9  mov     rbx, rcx
0x18000eccc  mov     [rsp+128h+hTemplateFile], 0; hTemplateFile
0x18000ecd5  mov     [rsp+128h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000ecdd  lea     rcx, FileName; "\\\\.\\NDIS"
0x18000ece4  mov     edx, 40000000h; dwDesiredAccess
0x18000ece9  mov     [rsp+128h+dwCreationDisposition], 3; dwCreationDisposition
0x18000ecf1  lea     r8d, [r9+7]; dwShareMode
0x18000ecf5  call    cs:__imp_CreateFileW
0x18000ecfb  mov     rcx, rax
0x18000ecfe  inc     rax
0x18000ed01  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000ed07  jnz     short loc_18000ED2A
0x18000ed09  mov     edx, 6; int
0x18000ed0e  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18000ed13  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18000ed18  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18000ed1f  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18000ed24  call    _CxxThrowException_0
0x18000ed2a  mov     [rbx], rcx
0x18000ed2d  mov     rax, rbx
0x18000ed30  add     rsp, 120h
0x18000ed37  pop     rbx
0x18000ed38  retn
```
