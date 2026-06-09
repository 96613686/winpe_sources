# Windows::Internal::SvcHostModule::DecrementObjectCount(void)

- ea: `0x18000be90`
- end: `0x18000bec9`
- name: `?DecrementObjectCount@SvcHostModule@Internal@Windows@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(Windows::Internal::SvcHostModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bed0`

## callees

- `0x18000be90`
- `0x18005e010`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x18000bea0`
- `combase!__imp_CoReleaseSharedService` at `0x18000bea0`

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
0x18000be90  mov     [rsp+arg_0], rbx
0x18000be95  push    rdi
0x18000be96  sub     rsp, 20h
0x18000be9a  mov     rdi, rcx
0x18000be9d  mov     ecx, [rcx+38h]
0x18000bea0  call    cs:__imp_CoReleaseSharedService
0x18000bea6  mov     ebx, eax
0x18000bea8  test    eax, eax
0x18000beaa  jnz     short loc_18000BEBC
0x18000beac  mov     rcx, [rdi+30h]
0x18000beb0  mov     rdx, [rcx]
0x18000beb3  mov     rax, [rdx+8]
0x18000beb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bebc  mov     eax, ebx
0x18000bebe  mov     rbx, [rsp+28h+arg_0]
0x18000bec3  add     rsp, 20h
0x18000bec7  pop     rdi
0x18000bec8  retn
```
