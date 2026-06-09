# Concurrency::details::ResourceManager::CaptureProcessAffinity(void)

- ea: `0x180310ab0`
- end: `0x180310c38`
- name: `?CaptureProcessAffinity@ResourceManager@details@Concurrency@@CAXXZ`
- size: `392`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1803131c0`

## callees

- `0x1802f0fb0`
- `0x18030c3f0`
- `0x1803104c8`
- `0x180310584`
- `0x180310ab0`
- `0x18032b080`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180310c08`
- `KERNEL32!GetLastError` at `0x180310c08`
- `KERNEL32!GetCurrentProcess` at `0x180310ad8`
- `KERNEL32!GetCurrentProcess` at `0x180310ad8`
- `KERNEL32!GetCurrentThread` at `0x180310b1c`
- `KERNEL32!GetCurrentThread` at `0x180310b1c`
- `KERNEL32!GetProcessAffinityMask` at `0x180310aef`
- `KERNEL32!GetProcessAffinityMask` at `0x180310aef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void Concurrency::details::ResourceManager::CaptureProcessAffinity(void)
{
  HANDLE CurrentProcess; // rax
  Concurrency::details::platform *CurrentThread; // rdx
  ULONG_PTR *v2; // rbx
  __int16 v3; // cx
  ULONG_PTR v4; // rdx
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  ULONG_PTR *v7; // rax
  ULONG_PTR v8; // rcx
  signed int LastError; // eax
  unsigned int v10; // edx
  _BYTE pExceptionObject[8]; // [rsp+30h] [rbp-38h] BYREF
  __int16 v12; // [rsp+38h] [rbp-30h]

  CurrentProcess = GetCurrentProcess();
  if ( !GetProcessAffinityMask(
          CurrentProcess,
          &Concurrency::details::ResourceManager::s_processAffinityMask,
          &Concurrency::details::ResourceManager::s_systemAffinityMask) )
  {
    LastError = GetLastError();
    v10 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v10 = LastError;
    Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(
      (Concurrency::scheduler_resource_allocation_error *)pExceptionObject,
      v10);
    throw (Concurrency::scheduler_resource_allocation_error *)pExceptionObject;
  }
  if ( Concurrency::details::ResourceManager::s_processAffinityMask != Concurrency::details::ResourceManager::s_systemAffinityMask )
  {
    if ( Concurrency::details::ResourceManager::s_version < 4 )
    {
      v6 = operator new(0x10u);
      if ( v6 )
      {
        v7 = (ULONG_PTR *)operator new(0x10u);
        if ( v7 )
        {
          v8 = Concurrency::details::ResourceManager::s_processAffinityMask;
          v7[1] = 0;
          *((_WORD *)v7 + 4) = 0;
          *v7 = v8;
        }
        else
        {
          v7 = 0;
        }
        *(_WORD *)v6 = 1;
        v6[1] = v7;
      }
      else
      {
        v6 = 0;
      }
      Concurrency::details::ResourceManager::s_pProcessAffinityRestriction = v6;
    }
    else
    {
      CurrentThread = (Concurrency::details::platform *)GetCurrentThread();
      Concurrency::details::HardwareAffinity::HardwareAffinity(
        (Concurrency::details::HardwareAffinity *)pExceptionObject,
        CurrentThread);
      v2 = (ULONG_PTR *)operator new(0x10u);
      if ( v2 )
      {
        v3 = v12;
        v4 = Concurrency::details::ResourceManager::s_processAffinityMask;
        v2[1] = 0;
        *((_WORD *)v2 + 4) = v3;
        *v2 = v4;
      }
      else
      {
        v2 = 0;
      }
      v5 = operator new(0x10u);
      if ( v5 )
      {
        *(_WORD *)v5 = 1;
        v5[1] = v2;
      }
      else
      {
        v5 = 0;
      }
      Concurrency::details::ResourceManager::s_pProcessAffinityRestriction = v5;
    }
  }
}

```

## disassembly

```asm
0x180310ab0  push    rdi
0x180310ab2  sub     rsp, 60h
0x180310ab6  mov     [rsp+68h+var_40], 0FFFFFFFFFFFFFFFEh
0x180310abf  mov     [rsp+68h+arg_0], rbx
0x180310ac4  mov     [rsp+68h+arg_8], rsi
0x180310ac9  mov     rax, cs:__security_cookie
0x180310ad0  xor     rax, rsp
0x180310ad3  mov     [rsp+68h+var_18], rax
0x180310ad8  call    cs:__imp_GetCurrentProcess
0x180310ade  mov     rcx, rax; hProcess
0x180310ae1  lea     r8, ?s_systemAffinityMask@ResourceManager@details@Concurrency@@0_KA; lpSystemAffinityMask
0x180310ae8  lea     rdx, ?s_processAffinityMask@ResourceManager@details@Concurrency@@0_KA; lpProcessAffinityMask
0x180310aef  call    cs:__imp_GetProcessAffinityMask
0x180310af5  xor     esi, esi
0x180310af7  test    eax, eax
0x180310af9  jz      loc_180310C08
0x180310aff  mov     rax, cs:?s_systemAffinityMask@ResourceManager@details@Concurrency@@0_KA; unsigned __int64 Concurrency::details::ResourceManager::s_systemAffinityMask
0x180310b06  cmp     cs:?s_processAffinityMask@ResourceManager@details@Concurrency@@0_KA, rax; unsigned __int64 Concurrency::details::ResourceManager::s_processAffinityMask
0x180310b0d  jz      loc_180310BEB
0x180310b13  cmp     cs:?s_version@ResourceManager@details@Concurrency@@0W4OSVersion@IResourceManager@3@A, 4; Concurrency::IResourceManager::OSVersion Concurrency::details::ResourceManager::s_version
0x180310b1a  jl      short loc_180310B90
0x180310b1c  call    cs:__imp_GetCurrentThread
0x180310b22  mov     rdx, rax; Concurrency::details::platform *
0x180310b25  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180310b2a  call    ??0HardwareAffinity@details@Concurrency@@QEAA@PEAX@Z; Concurrency::details::HardwareAffinity::HardwareAffinity(void *)
0x180310b2f  lea     edi, [rsi+10h]
0x180310b32  mov     ecx, edi; Size
0x180310b34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180310b39  mov     rbx, rax
0x180310b3c  mov     [rsp+68h+var_48], rax
0x180310b41  test    rax, rax
0x180310b44  jz      short loc_180310B61
0x180310b46  movzx   ecx, [rsp+68h+var_30]
0x180310b4b  mov     rdx, cs:?s_processAffinityMask@ResourceManager@details@Concurrency@@0_KA; unsigned __int64 Concurrency::details::ResourceManager::s_processAffinityMask
0x180310b52  xor     eax, eax
0x180310b54  mov     [rbx+8], rax
0x180310b58  mov     [rbx+8], cx
0x180310b5c  mov     [rbx], rdx
0x180310b5f  jmp     short loc_180310B64
0x180310b61  mov     rbx, rsi
0x180310b64  mov     rcx, rdi; Size
0x180310b67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180310b6c  mov     [rsp+68h+var_48], rax
0x180310b71  test    rax, rax
0x180310b74  jz      short loc_180310B84
0x180310b76  mov     ecx, 1
0x180310b7b  mov     [rax], cx
0x180310b7e  mov     [rax+8], rbx
0x180310b82  jmp     short loc_180310B87
0x180310b84  mov     rax, rsi
0x180310b87  mov     cs:?s_pProcessAffinityRestriction@ResourceManager@details@Concurrency@@0PEAUAffinityRestriction@123@EA, rax; Concurrency::details::ResourceManager::AffinityRestriction * Concurrency::details::ResourceManager::s_pProcessAffinityRestriction
0x180310b8e  jmp     short loc_180310BEB
0x180310b90  mov     edi, 10h
0x180310b95  mov     ecx, edi; Size
0x180310b97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180310b9c  mov     rbx, rax
0x180310b9f  mov     [rsp+68h+var_48], rax
0x180310ba4  test    rax, rax
0x180310ba7  jz      short loc_180310BE1
0x180310ba9  mov     ecx, edi; Size
0x180310bab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180310bb0  mov     [rsp+68h+var_48], rax
0x180310bb5  test    rax, rax
0x180310bb8  jz      short loc_180310BD0
0x180310bba  mov     rcx, cs:?s_processAffinityMask@ResourceManager@details@Concurrency@@0_KA; unsigned __int64 Concurrency::details::ResourceManager::s_processAffinityMask
0x180310bc1  xor     edx, edx
0x180310bc3  mov     [rax+8], rdx
0x180310bc7  mov     [rax+8], si
0x180310bcb  mov     [rax], rcx
0x180310bce  jmp     short loc_180310BD3
0x180310bd0  mov     rax, rsi
0x180310bd3  mov     ecx, 1
0x180310bd8  mov     [rbx], cx
0x180310bdb  mov     [rbx+8], rax
0x180310bdf  jmp     short loc_180310BE4
0x180310be1  mov     rbx, rsi
0x180310be4  mov     cs:?s_pProcessAffinityRestriction@ResourceManager@details@Concurrency@@0PEAUAffinityRestriction@123@EA, rbx; Concurrency::details::ResourceManager::AffinityRestriction * Concurrency::details::ResourceManager::s_pProcessAffinityRestriction
0x180310beb  mov     rcx, [rsp+68h+var_18]
0x180310bf0  xor     rcx, rsp; StackCookie
0x180310bf3  call    __security_check_cookie
0x180310bf8  mov     rbx, [rsp+68h+arg_0]
0x180310bfd  mov     rsi, [rsp+68h+arg_8]
0x180310c02  add     rsp, 60h
0x180310c06  pop     rdi
0x180310c07  retn
0x180310c08  call    cs:__imp_GetLastError
0x180310c0e  movzx   edx, ax
0x180310c11  or      edx, 80070000h
0x180310c17  test    eax, eax
0x180310c19  cmovle  edx, eax; int
0x180310c1c  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180310c21  call    ??0scheduler_resource_allocation_error@Concurrency@@QEAA@J@Z; Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(long)
0x180310c26  lea     rdx, _TI2?AVscheduler_resource_allocation_error@Concurrency@@; pThrowInfo
0x180310c2d  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180310c32  call    _CxxThrowException
```
