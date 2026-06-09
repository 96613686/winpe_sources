# Windows::Internal::SvcHostModule::DecrementObjectCount(void)

- ea: `0x180007960`
- end: `0x180007999`
- name: `?DecrementObjectCount@SvcHostModule@Internal@Windows@@UEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(Windows::Internal::SvcHostModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800079a0`

## callees

- `0x180007960`
- `0x180026010`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180007970`
- `combase!__imp_CoReleaseSharedService` at `0x180007970`

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
0x180007960  mov     [rsp+arg_0], rbx
0x180007965  push    rdi
0x180007966  sub     rsp, 20h
0x18000796a  mov     rdi, rcx
0x18000796d  mov     ecx, [rcx+38h]
0x180007970  call    cs:__imp_CoReleaseSharedService
0x180007976  mov     ebx, eax
0x180007978  test    eax, eax
0x18000797a  jnz     short loc_18000798C
0x18000797c  mov     rcx, [rdi+30h]
0x180007980  mov     rdx, [rcx]
0x180007983  mov     rax, [rdx+8]
0x180007987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000798c  mov     eax, ebx
0x18000798e  mov     rbx, [rsp+28h+arg_0]
0x180007993  add     rsp, 20h
0x180007997  pop     rdi
0x180007998  retn
```
