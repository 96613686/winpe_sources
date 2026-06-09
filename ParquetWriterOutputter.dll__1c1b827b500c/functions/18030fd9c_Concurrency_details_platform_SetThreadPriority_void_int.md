# Concurrency::details::platform::__SetThreadPriority(void *,int)

- ea: `0x18030fd9c`
- end: `0x18030fddf`
- name: `?__SetThreadPriority@platform@details@Concurrency@@YAXPEAXH@Z`
- size: `67`
- prototype: `void __fastcall(Concurrency::details::platform *__hidden this, void *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180310ee0`
- `0x180328380`

## callees

- `0x18030fd9c`
- `0x1803104c8`
- `0x18032b080`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18030fdaf`
- `KERNEL32!GetLastError` at `0x18030fdaf`
- `KERNEL32!SetThreadPriority` at `0x18030fda0`
- `KERNEL32!SetThreadPriority` at `0x18030fda0`

## pseudocode

```c
void __fastcall Concurrency::details::platform::__SetThreadPriority(Concurrency::details::platform *this, void *a2)
{
  signed int LastError; // eax
  unsigned int v3; // edx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( !SetThreadPriority(this, (int)a2) )
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
}

```

## disassembly

```asm
0x18030fd9c  sub     rsp, 48h
0x18030fda0  call    cs:__imp_SetThreadPriority
0x18030fda6  test    eax, eax
0x18030fda8  jz      short loc_18030FDAF
0x18030fdaa  add     rsp, 48h
0x18030fdae  retn
0x18030fdaf  call    cs:__imp_GetLastError
0x18030fdb5  movzx   edx, ax
0x18030fdb8  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18030fdbd  or      edx, 80070000h
0x18030fdc3  test    eax, eax
0x18030fdc5  cmovle  edx, eax; int
0x18030fdc8  call    ??0scheduler_resource_allocation_error@Concurrency@@QEAA@J@Z; Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(long)
0x18030fdcd  lea     rdx, _TI2?AVscheduler_resource_allocation_error@Concurrency@@; pThrowInfo
0x18030fdd4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18030fdd9  call    _CxxThrowException
```
