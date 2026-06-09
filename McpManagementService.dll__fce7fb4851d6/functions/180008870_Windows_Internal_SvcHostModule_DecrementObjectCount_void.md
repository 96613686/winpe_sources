# Windows::Internal::SvcHostModule::DecrementObjectCount(void)

- ea: `0x180008870`
- end: `0x1800088a9`
- name: `?DecrementObjectCount@SvcHostModule@Internal@Windows@@UEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(Windows::Internal::SvcHostModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800088b0`

## callees

- `0x180008870`
- `0x18002b010`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180008880`
- `combase!__imp_CoReleaseSharedService` at `0x180008880`

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
0x180008870  mov     [rsp+arg_0], rbx
0x180008875  push    rdi
0x180008876  sub     rsp, 20h
0x18000887a  mov     rdi, rcx
0x18000887d  mov     ecx, [rcx+38h]
0x180008880  call    cs:__imp_CoReleaseSharedService
0x180008886  mov     ebx, eax
0x180008888  test    eax, eax
0x18000888a  jnz     short loc_18000889C
0x18000888c  mov     rcx, [rdi+30h]
0x180008890  mov     rdx, [rcx]
0x180008893  mov     rax, [rdx+8]
0x180008897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000889c  mov     eax, ebx
0x18000889e  mov     rbx, [rsp+28h+arg_0]
0x1800088a3  add     rsp, 20h
0x1800088a7  pop     rdi
0x1800088a8  retn
```
