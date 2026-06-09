# Windows::Internal::SvcHostModule::DecrementObjectCount(void)

- ea: `0x180004db0`
- end: `0x180004de9`
- name: `?DecrementObjectCount@SvcHostModule@Internal@Windows@@UEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(Windows::Internal::SvcHostModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004df0`

## callees

- `0x180004db0`
- `0x18000e010`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180004dc0`
- `combase!__imp_CoReleaseSharedService` at `0x180004dc0`

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
0x180004db0  mov     [rsp+arg_0], rbx
0x180004db5  push    rdi
0x180004db6  sub     rsp, 20h
0x180004dba  mov     rdi, rcx
0x180004dbd  mov     ecx, [rcx+38h]
0x180004dc0  call    cs:__imp_CoReleaseSharedService
0x180004dc6  mov     ebx, eax
0x180004dc8  test    eax, eax
0x180004dca  jnz     short loc_180004DDC
0x180004dcc  mov     rcx, [rdi+30h]
0x180004dd0  mov     rdx, [rcx]
0x180004dd3  mov     rax, [rdx+8]
0x180004dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ddc  mov     eax, ebx
0x180004dde  mov     rbx, [rsp+28h+arg_0]
0x180004de3  add     rsp, 20h
0x180004de7  pop     rdi
0x180004de8  retn
```
