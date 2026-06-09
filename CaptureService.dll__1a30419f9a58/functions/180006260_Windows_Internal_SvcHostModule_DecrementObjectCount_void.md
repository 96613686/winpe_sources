# Windows::Internal::SvcHostModule::DecrementObjectCount(void)

- ea: `0x180006260`
- end: `0x180006299`
- name: `?DecrementObjectCount@SvcHostModule@Internal@Windows@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(Windows::Internal::SvcHostModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800062a0`

## callees

- `0x180006260`
- `0x180022010`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180006270`
- `combase!__imp_CoReleaseSharedService` at `0x180006270`

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
0x180006260  mov     [rsp+arg_0], rbx
0x180006265  push    rdi
0x180006266  sub     rsp, 20h
0x18000626a  mov     rdi, rcx
0x18000626d  mov     ecx, [rcx+38h]
0x180006270  call    cs:__imp_CoReleaseSharedService
0x180006276  mov     ebx, eax
0x180006278  test    eax, eax
0x18000627a  jnz     short loc_18000628C
0x18000627c  mov     rcx, [rdi+30h]
0x180006280  mov     rdx, [rcx]
0x180006283  mov     rax, [rdx+8]
0x180006287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000628c  mov     eax, ebx
0x18000628e  mov     rbx, [rsp+28h+arg_0]
0x180006293  add     rsp, 20h
0x180006297  pop     rdi
0x180006298  retn
```
