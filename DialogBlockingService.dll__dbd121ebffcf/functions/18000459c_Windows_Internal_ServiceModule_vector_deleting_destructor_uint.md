# Windows::Internal::ServiceModule::`vector deleting destructor'(uint)

- ea: `0x18000459c`
- end: `0x18000460c`
- name: `??_EServiceModule@Internal@Windows@@UEAAPEAXI@Z`
- size: `112`
- prototype: `Windows::Internal::ServiceModule *__fastcall(Windows::Internal::ServiceModule *this, __int64, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180004380`

## callees

- `0x180001644`
- `0x180003c6c`
- `0x18000459c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800045e5`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800045e5`

## pseudocode

```c
Windows::Internal::ServiceModule *__fastcall Windows::Internal::ServiceModule::`vector deleting destructor'(
        Windows::Internal::ServiceModule *this,
        __int64 a2,
        const unsigned __int16 *a3,
        bool a4)
{
  char v4; // di
  __int64 v6; // rcx

  v4 = a2;
  Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(
    (Windows::Internal::ServiceModule *)((char *)this + 40),
    a2,
    a3,
    a4);
  *(_QWORD *)this = &Windows::Internal::ServiceModuleBase::`vftable';
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    *((_QWORD *)this + 3) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( *((_QWORD *)this + 1) )
    CoDecrementMTAUsage();
  if ( (v4 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000459c  mov     [rsp+arg_0], rbx
0x1800045a1  push    rdi
0x1800045a2  sub     rsp, 20h
0x1800045a6  mov     edi, edx
0x1800045a8  mov     rbx, rcx
0x1800045ab  add     rcx, 28h ; '('; this
0x1800045af  call    ??1?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(void)
0x1800045b4  lea     rax, ??_7ServiceModuleBase@Internal@Windows@@6B@; const Windows::Internal::ServiceModuleBase::`vftable'
0x1800045bb  mov     [rbx], rax
0x1800045be  mov     rcx, [rbx+18h]
0x1800045c2  test    rcx, rcx
0x1800045c5  jz      short loc_1800045DC
0x1800045c7  mov     qword ptr [rbx+18h], 0
0x1800045cf  mov     rax, [rcx]
0x1800045d2  mov     rax, [rax+10h]
0x1800045d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045db  nop
0x1800045dc  mov     rcx, [rbx+8]
0x1800045e0  test    rcx, rcx
0x1800045e3  jz      short loc_1800045EB
0x1800045e5  call    cs:__imp_CoDecrementMTAUsage
0x1800045eb  test    dil, 1
0x1800045ef  jz      short loc_1800045FE
0x1800045f1  mov     edx, 38h ; '8'; unsigned __int64
0x1800045f6  mov     rcx, rbx; void *
0x1800045f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800045fe  mov     rax, rbx
0x180004601  mov     rbx, [rsp+28h+arg_0]
0x180004606  add     rsp, 20h
0x18000460a  pop     rdi
0x18000460b  retn
```
