# Windows::Internal::ServiceModule::`vector deleting destructor'(uint)

- ea: `0x180004b74`
- end: `0x180004be4`
- name: `??_EServiceModule@Internal@Windows@@UEAAPEAXI@Z`
- size: `112`
- prototype: `Windows::Internal::ServiceModule *__fastcall(Windows::Internal::ServiceModule *this, __int64, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800048c0`

## callees

- `0x180001b6c`
- `0x1800043a0`
- `0x180004b74`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x180004bbd`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x180004bbd`

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
    operator delete(this, (const struct std::nothrow_t *)0x38);
  return this;
}

```

## disassembly

```asm
0x180004b74  mov     [rsp+arg_0], rbx
0x180004b79  push    rdi
0x180004b7a  sub     rsp, 20h
0x180004b7e  mov     edi, edx
0x180004b80  mov     rbx, rcx
0x180004b83  add     rcx, 28h ; '('; this
0x180004b87  call    ??1?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(void)
0x180004b8c  lea     rax, ??_7ServiceModuleBase@Internal@Windows@@6B@; const Windows::Internal::ServiceModuleBase::`vftable'
0x180004b93  mov     [rbx], rax
0x180004b96  mov     rcx, [rbx+18h]
0x180004b9a  test    rcx, rcx
0x180004b9d  jz      short loc_180004BB4
0x180004b9f  mov     qword ptr [rbx+18h], 0
0x180004ba7  mov     rax, [rcx]
0x180004baa  mov     rax, [rax+10h]
0x180004bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb3  nop
0x180004bb4  mov     rcx, [rbx+8]
0x180004bb8  test    rcx, rcx
0x180004bbb  jz      short loc_180004BC3
0x180004bbd  call    cs:__imp_CoDecrementMTAUsage
0x180004bc3  test    dil, 1
0x180004bc7  jz      short loc_180004BD6
0x180004bc9  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x180004bce  mov     rcx, rbx; void *
0x180004bd1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004bd6  mov     rax, rbx
0x180004bd9  mov     rbx, [rsp+28h+arg_0]
0x180004bde  add     rsp, 20h
0x180004be2  pop     rdi
0x180004be3  retn
```
