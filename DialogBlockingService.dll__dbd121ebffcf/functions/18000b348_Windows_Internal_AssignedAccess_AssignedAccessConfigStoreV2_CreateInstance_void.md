# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::CreateInstance(void)

- ea: `0x18000b348`
- end: `0x18000b3be`
- name: `?CreateInstance@AssignedAccessConfigStoreV2@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ`
- size: `118`
- prototype: `Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 **__fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b3c4`
- `0x18000b518`
- `0x18000b8ac`

## callees

- `0x180001650`
- `0x18000b348`
- `0x18000e010`

## pseudocode

```c
Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 **__fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::CreateInstance(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 **a1)
{
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v2; // rdi
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v3; // rbx

  v2 = (Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *)operator new(0x20u);
  v3 = 0;
  *((_QWORD *)v2 + 1) = 0;
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 3) = 0;
  *(_QWORD *)v2 = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::`vftable';
  if ( Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::Initialize(v2) )
    v3 = v2;
  else
    (**(void (__fastcall ***)(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *, __int64))v2)(v2, 1);
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x18000b348  mov     [rsp+arg_0], rbx
0x18000b34d  mov     [rsp+arg_8], rsi
0x18000b352  push    rdi
0x18000b353  sub     rsp, 20h
0x18000b357  mov     rsi, rcx
0x18000b35a  mov     ecx, 20h ; ' '; Size
0x18000b35f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b364  mov     rdi, rax
0x18000b367  xor     ebx, ebx
0x18000b369  mov     rcx, rdi
0x18000b36c  mov     [rax+8], rbx
0x18000b370  mov     [rax+10h], rbx
0x18000b374  mov     [rax+18h], rbx
0x18000b378  lea     rax, ??_7AssignedAccessConfigStoreV2@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::`vftable'
0x18000b37f  mov     [rdi], rax
0x18000b382  mov     rax, cs:off_18000F428
0x18000b389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b38e  test    al, al
0x18000b390  jnz     short loc_18000B3A5
0x18000b392  mov     rax, [rdi]
0x18000b395  lea     edx, [rbx+1]
0x18000b398  mov     rcx, rdi
0x18000b39b  mov     rax, [rax]
0x18000b39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3a3  jmp     short loc_18000B3A8
0x18000b3a5  mov     rbx, rdi
0x18000b3a8  mov     [rsi], rbx
0x18000b3ab  mov     rax, rsi
0x18000b3ae  mov     rbx, [rsp+28h+arg_0]
0x18000b3b3  mov     rsi, [rsp+28h+arg_8]
0x18000b3b8  add     rsp, 20h
0x18000b3bc  pop     rdi
0x18000b3bd  retn
```
