# Concurrency::details::ExternalContextBase::PrepareForUse(bool)

- ea: `0x18032684c`
- end: `0x18032697b`
- name: `?PrepareForUse@ExternalContextBase@details@Concurrency@@QEAAX_N@Z`
- size: `303`
- prototype: `void __fastcall(Concurrency::details::ExternalContextBase *__hidden this, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1803173f4`
- `0x1803264c0`

## callees

- `0x18030fce4`
- `0x180310124`
- `0x1803104c8`
- `0x180312b78`
- `0x18032684c`
- `0x18032b080`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18032691b`
- `KERNEL32!GetLastError` at `0x18032694b`
- `KERNEL32!GetLastError` at `0x18032691b`
- `KERNEL32!GetLastError` at `0x18032694b`
- `KERNEL32!GetCurrentProcess` at `0x180326887`
- `KERNEL32!GetCurrentProcess` at `0x180326899`
- `KERNEL32!GetCurrentProcess` at `0x180326887`
- `KERNEL32!GetCurrentProcess` at `0x180326899`
- `KERNEL32!GetCurrentThreadId` at `0x18032686c`
- `KERNEL32!GetCurrentThreadId` at `0x18032686c`
- `KERNEL32!DuplicateHandle` at `0x1803268bd`
- `KERNEL32!DuplicateHandle` at `0x1803268bd`
- `KERNEL32!GetCurrentThread` at `0x180326890`
- `KERNEL32!GetCurrentThread` at `0x180326890`

## pseudocode

```c
void __fastcall Concurrency::details::ExternalContextBase::PrepareForUse(
        Concurrency::details::ExternalContextBase *this,
        char a2)
{
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v6; // rax
  int OSVersion; // eax
  void *v8; // r9
  void *v9; // rcx
  struct _TP_WAIT *Library; // rax
  signed int LastError; // eax
  unsigned int v12; // edx
  signed int v13; // eax
  unsigned int v14; // edx
  _BYTE pExceptionObject[32]; // [rsp+40h] [rbp-28h] BYREF

  *((_BYTE *)this + 240) = a2;
  *((_DWORD *)this + 32) = GetCurrentThreadId();
  if ( !a2 )
  {
    CurrentProcess = GetCurrentProcess();
    CurrentThread = GetCurrentThread();
    v6 = GetCurrentProcess();
    if ( !DuplicateHandle(v6, CurrentThread, CurrentProcess, (LPHANDLE)this + 33, 0, 0, 2u) )
    {
      LastError = GetLastError();
      v12 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v12 = LastError;
      Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(
        (Concurrency::scheduler_resource_allocation_error *)pExceptionObject,
        v12);
      throw (Concurrency::scheduler_resource_allocation_error *)pExceptionObject;
    }
    OSVersion = Concurrency::GetOSVersion();
    v9 = (void *)*((_QWORD *)this + 33);
    if ( OSVersion < 3 )
    {
      *((_QWORD *)this + 35) = Concurrency::details::platform::__RegisterWaitForSingleObject(
                                 v9,
                                 (WAITORTIMERCALLBACK)Concurrency::details::ExternalContextBase::ImplicitDetachHandlerXP,
                                 this,
                                 v8);
    }
    else
    {
      Library = Concurrency::details::RegisterAsyncWaitAndLoadLibrary(
                  (Concurrency::details *)v9,
                  Concurrency::details::ExternalContextBase::ImplicitDetachHandler,
                  (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, unsigned int))this,
                  v8);
      *((_QWORD *)this + 35) = Library;
      if ( !Library )
      {
        v13 = GetLastError();
        v14 = (unsigned __int16)v13 | 0x80070000;
        if ( v13 <= 0 )
          v14 = v13;
        Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(
          (Concurrency::scheduler_resource_allocation_error *)pExceptionObject,
          v14);
        throw (Concurrency::scheduler_resource_allocation_error *)pExceptionObject;
      }
    }
  }
}

```

## disassembly

```asm
0x18032684c  mov     [rsp+arg_0], rbx
0x180326851  mov     [rsp+arg_8], rsi
0x180326856  mov     [rsp+arg_10], rdi
0x18032685b  push    r14
0x18032685d  sub     rsp, 60h
0x180326861  mov     bl, dl
0x180326863  mov     [rcx+0F0h], dl
0x180326869  mov     rsi, rcx
0x18032686c  call    cs:__imp_GetCurrentThreadId
0x180326872  mov     [rsi+80h], eax
0x180326878  test    bl, bl
0x18032687a  jnz     loc_180326904
0x180326880  lea     r14, [rsi+108h]
0x180326887  call    cs:__imp_GetCurrentProcess
0x18032688d  mov     rdi, rax
0x180326890  call    cs:__imp_GetCurrentThread
0x180326896  mov     rbx, rax
0x180326899  call    cs:__imp_GetCurrentProcess
0x18032689f  mov     [rsp+68h+dwOptions], 2; dwOptions
0x1803268a7  mov     r9, r14; lpTargetHandle
0x1803268aa  and     [rsp+68h+var_40], 0
0x1803268af  mov     rcx, rax; hSourceProcessHandle
0x1803268b2  and     [rsp+68h+var_48], 0
0x1803268b7  mov     r8, rdi; hTargetProcessHandle
0x1803268ba  mov     rdx, rbx; hSourceHandle
0x1803268bd  call    cs:__imp_DuplicateHandle
0x1803268c3  test    eax, eax
0x1803268c5  jz      short loc_18032691B
0x1803268c7  call    ?GetOSVersion@Concurrency@@YA?AW4OSVersion@IResourceManager@1@XZ; Concurrency::GetOSVersion(void)
0x1803268cc  mov     rcx, [r14]; hObject
0x1803268cf  mov     r8, rsi; Context
0x1803268d2  cmp     eax, 3
0x1803268d5  jl      short loc_1803268F1
0x1803268d7  lea     rdx, ?ImplicitDetachHandler@ExternalContextBase@details@Concurrency@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; void *
0x1803268de  call    ?RegisterAsyncWaitAndLoadLibrary@details@Concurrency@@YAPEAU_TP_WAIT@@PEAXP6AXPEAU_TP_CALLBACK_INSTANCE@@0PEAU3@K@Z0@Z; Concurrency::details::RegisterAsyncWaitAndLoadLibrary(void *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,ulong),void *)
0x1803268e3  mov     [rsi+118h], rax
0x1803268ea  test    rax, rax
0x1803268ed  jz      short loc_18032694B
0x1803268ef  jmp     short loc_180326904
0x1803268f1  lea     rdx, ?ImplicitDetachHandlerXP@ExternalContextBase@details@Concurrency@@CAXPEAXE@Z; Callback
0x1803268f8  call    ?__RegisterWaitForSingleObject@platform@details@Concurrency@@YAPEAXPEAXP6AX0E@Z0@Z; Concurrency::details::platform::__RegisterWaitForSingleObject(void *,void (*)(void *,uchar),void *)
0x1803268fd  mov     [rsi+118h], rax
0x180326904  lea     r11, [rsp+68h+var_8]
0x180326909  mov     rbx, [r11+10h]
0x18032690d  mov     rsi, [r11+18h]
0x180326911  mov     rdi, [r11+20h]
0x180326915  mov     rsp, r11
0x180326918  pop     r14
0x18032691a  retn
0x18032691b  call    cs:__imp_GetLastError
0x180326921  movzx   edx, ax
0x180326924  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180326929  or      edx, 80070000h
0x18032692f  test    eax, eax
0x180326931  cmovle  edx, eax; int
0x180326934  call    ??0scheduler_resource_allocation_error@Concurrency@@QEAA@J@Z; Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(long)
0x180326939  lea     rdx, _TI2?AVscheduler_resource_allocation_error@Concurrency@@; pThrowInfo
0x180326940  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180326945  call    _CxxThrowException
0x18032694b  call    cs:__imp_GetLastError
0x180326951  movzx   edx, ax
0x180326954  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180326959  or      edx, 80070000h
0x18032695f  test    eax, eax
0x180326961  cmovle  edx, eax; int
0x180326964  call    ??0scheduler_resource_allocation_error@Concurrency@@QEAA@J@Z; Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(long)
0x180326969  lea     rdx, _TI2?AVscheduler_resource_allocation_error@Concurrency@@; pThrowInfo
0x180326970  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180326975  call    _CxxThrowException
```
