# Windows::Internal::SvcHostModule::DecrementObjectCount(void)

- ea: `0x180009870`
- end: `0x1800098a9`
- name: `?DecrementObjectCount@SvcHostModule@Internal@Windows@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(Windows::Internal::SvcHostModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800098b0`

## callees

- `0x180009870`
- `0x180048010`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180009880`
- `combase!__imp_CoReleaseSharedService` at `0x180009880`

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
0x180009870  mov     [rsp+arg_0], rbx
0x180009875  push    rdi
0x180009876  sub     rsp, 20h
0x18000987a  mov     rdi, rcx
0x18000987d  mov     ecx, [rcx+38h]
0x180009880  call    cs:__imp_CoReleaseSharedService
0x180009886  mov     ebx, eax
0x180009888  test    eax, eax
0x18000988a  jnz     short loc_18000989C
0x18000988c  mov     rcx, [rdi+30h]
0x180009890  mov     rdx, [rcx]
0x180009893  mov     rax, [rdx+8]
0x180009897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000989c  mov     eax, ebx
0x18000989e  mov     rbx, [rsp+28h+arg_0]
0x1800098a3  add     rsp, 20h
0x1800098a7  pop     rdi
0x1800098a8  retn
```
