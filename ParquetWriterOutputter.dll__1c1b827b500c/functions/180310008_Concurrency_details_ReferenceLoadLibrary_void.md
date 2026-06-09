# Concurrency::details::ReferenceLoadLibrary(void)

- ea: `0x180310008`
- end: `0x1803100b0`
- name: `?ReferenceLoadLibrary@details@Concurrency@@YAXXZ`
- size: `168`
- prototype: `void __fastcall(Concurrency::details *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18030ffb8`
- `0x1803100b0`
- `0x180310124`

## callees

- `0x18030c3f0`
- `0x180310008`
- `0x1803104c8`
- `0x18032b080`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180310080`
- `KERNEL32!GetLastError` at `0x180310080`
- `KERNEL32!GetModuleHandleA` at `0x180310023`
- `KERNEL32!GetModuleHandleA` at `0x180310023`
- `KERNEL32!GetModuleFileNameW` at `0x180310040`
- `KERNEL32!GetModuleFileNameW` at `0x180310040`
- `KERNEL32!LoadLibraryExW` at `0x18031005b`
- `KERNEL32!LoadLibraryExW` at `0x18031005b`

## pseudocode

```c
void __fastcall Concurrency::details::ReferenceLoadLibrary(Concurrency::details *this)
{
  DWORD ModuleFileNameW; // eax
  signed int LastError; // eax
  unsigned int v3; // edx
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( (HMODULE)0x180000000LL != GetModuleHandleA(0) )
  {
    ModuleFileNameW = GetModuleFileNameW((HMODULE)0x180000000LL, Filename, 0x104u);
    if ( !ModuleFileNameW || ModuleFileNameW == 260 )
    {
      LastError = GetLastError();
      v3 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v3 = LastError;
      Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(
        (Concurrency::scheduler_resource_allocation_error *)pExceptionObject,
        v3);
      throw (Concurrency::scheduler_resource_allocation_error *)pExceptionObject;
    }
    Concurrency::details::HostModule = LoadLibraryExW(Filename, 0, 0);
  }
}

```

## disassembly

```asm
0x180310008  sub     rsp, 268h
0x18031000f  mov     rax, cs:__security_cookie
0x180310016  xor     rax, rsp
0x180310019  mov     [rsp+268h+var_18], rax
0x180310021  xor     ecx, ecx; lpModuleName
0x180310023  call    cs:__imp_GetModuleHandleA
0x180310029  lea     rcx, cs:180000000h; hModule
0x180310030  cmp     rcx, rax
0x180310033  jz      short loc_180310068
0x180310035  mov     r8d, 104h; nSize
0x18031003b  lea     rdx, [rsp+268h+Filename]; lpFilename
0x180310040  call    cs:__imp_GetModuleFileNameW
0x180310046  test    eax, eax
0x180310048  jz      short loc_180310080
0x18031004a  cmp     eax, 104h
0x18031004f  jz      short loc_180310080
0x180310051  xor     r8d, r8d; dwFlags
0x180310054  lea     rcx, [rsp+268h+Filename]; lpLibFileName
0x180310059  xor     edx, edx; hFile
0x18031005b  call    cs:__imp_LoadLibraryExW
0x180310061  mov     cs:?HostModule@details@Concurrency@@3PEAUHINSTANCE__@@EA, rax
0x180310068  mov     rcx, [rsp+268h+var_18]
0x180310070  xor     rcx, rsp; StackCookie
0x180310073  call    __security_check_cookie
0x180310078  add     rsp, 268h
0x18031007f  retn
0x180310080  call    cs:__imp_GetLastError
0x180310086  movzx   edx, ax
0x180310089  lea     rcx, [rsp+268h+pExceptionObject]; this
0x18031008e  or      edx, 80070000h
0x180310094  test    eax, eax
0x180310096  cmovle  edx, eax; int
0x180310099  call    ??0scheduler_resource_allocation_error@Concurrency@@QEAA@J@Z
0x18031009e  lea     rdx, _TI2?AVscheduler_resource_allocation_error@Concurrency@@; pThrowInfo
0x1803100a5  lea     rcx, [rsp+268h+pExceptionObject]; pExceptionObject
0x1803100aa  call    _CxxThrowException
```
