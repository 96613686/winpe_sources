# Windows::Internal::SvcHostModule::DecrementObjectCount(void)

- ea: `0x180004f80`
- end: `0x180004fb9`
- name: `?DecrementObjectCount@SvcHostModule@Internal@Windows@@UEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(Windows::Internal::SvcHostModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004fc0`

## callees

- `0x180004f80`
- `0x180012010`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180004f90`
- `combase!__imp_CoReleaseSharedService` at `0x180004f90`

## pseudocode

```c
__int64 __fastcall Windows::Internal::SvcHostModule::DecrementObjectCount(Windows::Internal::SvcHostModule *this)
{
  unsigned int v2; // ebx

  v2 = CoReleaseSharedService(*((unsigned int *)this + 14));
  if ( !v2 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
  return v2;
}

```

## disassembly

```asm
0x180004f80  mov     [rsp+arg_0], rbx
0x180004f85  push    rdi
0x180004f86  sub     rsp, 20h
0x180004f8a  mov     rdi, rcx
0x180004f8d  mov     ecx, [rcx+38h]
0x180004f90  call    cs:__imp_CoReleaseSharedService
0x180004f96  mov     ebx, eax
0x180004f98  test    eax, eax
0x180004f9a  jnz     short loc_180004FAC
0x180004f9c  mov     rcx, [rdi+30h]
0x180004fa0  mov     rdx, [rcx]
0x180004fa3  mov     rax, [rdx+8]
0x180004fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fac  mov     eax, ebx
0x180004fae  mov     rbx, [rsp+28h+arg_0]
0x180004fb3  add     rsp, 20h
0x180004fb7  pop     rdi
0x180004fb8  retn
```
