# Concurrency::details::WinRT::Initialize(void)

- ea: `0x18031fa1c`
- end: `0x18031fb51`
- name: `?Initialize@WinRT@details@Concurrency@@SAXXZ`
- size: `309`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1803148a0`

## callees

- `0x18030fec8`
- `0x1803104c8`
- `0x18031fa1c`
- `0x18032b080`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18031fac1`
- `KERNEL32!GetLastError` at `0x18031faf1`
- `KERNEL32!GetLastError` at `0x18031fb21`
- `KERNEL32!GetLastError` at `0x18031fac1`
- `KERNEL32!GetLastError` at `0x18031faf1`
- `KERNEL32!GetLastError` at `0x18031fb21`
- `KERNEL32!GetProcAddress` at `0x18031fa5b`
- `KERNEL32!GetProcAddress` at `0x18031fa90`
- `KERNEL32!GetProcAddress` at `0x18031fa5b`
- `KERNEL32!GetProcAddress` at `0x18031fa90`
- `KERNEL32!GetModuleHandleW` at `0x18031fa4b`
- `KERNEL32!GetModuleHandleW` at `0x18031fa80`
- `KERNEL32!GetModuleHandleW` at `0x18031fa4b`
- `KERNEL32!GetModuleHandleW` at `0x18031fa80`
- `KERNEL32!LoadLibraryExW` at `0x18031fa32`
- `KERNEL32!LoadLibraryExW` at `0x18031fa32`

## string_xrefs

- `0x18031fa25`: `combase.dll`
- `0x18031fa44`: `combase.dll`
- `0x18031fa72`: `combase.dll`

## pseudocode

```c
void Concurrency::details::WinRT::Initialize(void)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  HMODULE v2; // rax
  FARPROC v3; // rax
  signed int LastError; // eax
  unsigned int v5; // edx
  signed int v6; // eax
  unsigned int v7; // edx
  signed int v8; // eax
  unsigned int v9; // edx
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v12[40]; // [rsp+60h] [rbp-28h] BYREF

  Concurrency::details::WinRT::m_hModule = LoadLibraryExW(L"combase.dll", 0, 0x800u);
  if ( !Concurrency::details::WinRT::m_hModule )
  {
    LastError = GetLastError();
    v5 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v5 = LastError;
    Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(
      (Concurrency::scheduler_resource_allocation_error *)pExceptionObject,
      v5);
    throw (Concurrency::scheduler_resource_allocation_error *)pExceptionObject;
  }
  ModuleHandleW = GetModuleHandleW(L"combase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RoInitialize");
  if ( !ProcAddress )
  {
    v6 = GetLastError();
    v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v6 <= 0 )
      v7 = v6;
    Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(
      (Concurrency::scheduler_resource_allocation_error *)v11,
      v7);
    throw (Concurrency::scheduler_resource_allocation_error *)v11;
  }
  Concurrency::details::WinRT::s_pfn_RoInitialize = Concurrency::details::Security::EncodePointer(ProcAddress);
  v2 = GetModuleHandleW(L"combase.dll");
  v3 = GetProcAddress(v2, "RoUninitialize");
  if ( !v3 )
  {
    v8 = GetLastError();
    v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v9 = v8;
    Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(
      (Concurrency::scheduler_resource_allocation_error *)v12,
      v9);
    throw (Concurrency::scheduler_resource_allocation_error *)v12;
  }
  Concurrency::details::WinRT::s_pfn_RoUninitialize = Concurrency::details::Security::EncodePointer(v3);
  _InterlockedExchange(&Concurrency::details::WinRT::s_fInitialized, 1);
}

```

## disassembly

```asm
0x18031fa1c  sub     rsp, 88h
0x18031fa23  xor     edx, edx; hFile
0x18031fa25  lea     rcx, LibFileName; "combase.dll"
0x18031fa2c  mov     r8d, 800h; dwFlags
0x18031fa32  call    cs:__imp_LoadLibraryExW
0x18031fa38  mov     cs:?m_hModule@WinRT@details@Concurrency@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Concurrency::details::WinRT::m_hModule
0x18031fa3f  test    rax, rax
0x18031fa42  jz      short loc_18031FAC1
0x18031fa44  lea     rcx, LibFileName; "combase.dll"
0x18031fa4b  call    cs:__imp_GetModuleHandleW
0x18031fa51  mov     rcx, rax; hModule
0x18031fa54  lea     rdx, aRoinitialize; "RoInitialize"
0x18031fa5b  call    cs:__imp_GetProcAddress
0x18031fa61  test    rax, rax
0x18031fa64  jz      loc_18031FAF1
0x18031fa6a  mov     rcx, rax; void *
0x18031fa6d  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x18031fa72  lea     rcx, LibFileName; "combase.dll"
0x18031fa79  mov     cs:?s_pfn_RoInitialize@WinRT@details@Concurrency@@0P6AJW4RO_INIT_TYPE@@@ZEA, rax; long (*Concurrency::details::WinRT::s_pfn_RoInitialize)(RO_INIT_TYPE)
0x18031fa80  call    cs:__imp_GetModuleHandleW
0x18031fa86  mov     rcx, rax; hModule
0x18031fa89  lea     rdx, aRouninitialize_0; "RoUninitialize"
0x18031fa90  call    cs:__imp_GetProcAddress
0x18031fa96  test    rax, rax
0x18031fa99  jz      loc_18031FB21
0x18031fa9f  mov     rcx, rax; void *
0x18031faa2  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x18031faa7  mov     cs:?s_pfn_RoUninitialize@WinRT@details@Concurrency@@0P6AXXZEA, rax; void (*Concurrency::details::WinRT::s_pfn_RoUninitialize)(void)
0x18031faae  mov     eax, 1
0x18031fab3  xchg    eax, cs:?s_fInitialized@WinRT@details@Concurrency@@0JC; long volatile Concurrency::details::WinRT::s_fInitialized
0x18031fab9  add     rsp, 88h
0x18031fac0  retn
0x18031fac1  call    cs:__imp_GetLastError
0x18031fac7  movzx   edx, ax
0x18031faca  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18031facf  or      edx, 80070000h
0x18031fad5  test    eax, eax
0x18031fad7  cmovle  edx, eax; int
0x18031fada  call    ??0scheduler_resource_allocation_error@Concurrency@@QEAA@J@Z; Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(long)
0x18031fadf  lea     rdx, _TI2?AVscheduler_resource_allocation_error@Concurrency@@; pThrowInfo
0x18031fae6  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18031faeb  call    _CxxThrowException
0x18031faf1  call    cs:__imp_GetLastError
0x18031faf7  movzx   edx, ax
0x18031fafa  lea     rcx, [rsp+88h+var_48]; this
0x18031faff  or      edx, 80070000h
0x18031fb05  test    eax, eax
0x18031fb07  cmovle  edx, eax; int
0x18031fb0a  call    ??0scheduler_resource_allocation_error@Concurrency@@QEAA@J@Z; Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(long)
0x18031fb0f  lea     rdx, _TI2?AVscheduler_resource_allocation_error@Concurrency@@; pThrowInfo
0x18031fb16  lea     rcx, [rsp+88h+var_48]; pExceptionObject
0x18031fb1b  call    _CxxThrowException
0x18031fb21  call    cs:__imp_GetLastError
0x18031fb27  movzx   edx, ax
0x18031fb2a  lea     rcx, [rsp+88h+var_28]; this
0x18031fb2f  or      edx, 80070000h
0x18031fb35  test    eax, eax
0x18031fb37  cmovle  edx, eax; int
0x18031fb3a  call    ??0scheduler_resource_allocation_error@Concurrency@@QEAA@J@Z; Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(long)
0x18031fb3f  lea     rdx, _TI2?AVscheduler_resource_allocation_error@Concurrency@@; pThrowInfo
0x18031fb46  lea     rcx, [rsp+88h+var_28]; pExceptionObject
0x18031fb4b  call    _CxxThrowException
```
