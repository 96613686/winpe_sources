# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::CreateInstance(void)

- ea: `0x18000b2cc`
- end: `0x18000b342`
- name: `?CreateInstance@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ`
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
- `0x18000b2cc`
- `0x18000e010`

## pseudocode

```c
Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 **__fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::CreateInstance(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 **a1)
{
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v2; // rdi
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v3; // rbx

  v2 = (Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *)operator new(0x20u);
  v3 = 0;
  *(_QWORD *)v2 = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::`vftable';
  *((_QWORD *)v2 + 1) = 0;
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 3) = 0;
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
0x18000b2cc  mov     [rsp+arg_0], rbx
0x18000b2d1  mov     [rsp+arg_8], rsi
0x18000b2d6  push    rdi
0x18000b2d7  sub     rsp, 20h
0x18000b2db  mov     rsi, rcx
0x18000b2de  mov     ecx, 20h ; ' '; Size
0x18000b2e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b2e8  mov     rdi, rax
0x18000b2eb  xor     ebx, ebx
0x18000b2ed  lea     rax, ??_7AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::`vftable'
0x18000b2f4  mov     rcx, rdi
0x18000b2f7  mov     [rdi], rax
0x18000b2fa  mov     [rdi+8], rbx
0x18000b2fe  mov     [rdi+10h], rbx
0x18000b302  mov     [rdi+18h], rbx
0x18000b306  mov     rax, cs:off_18000F458
0x18000b30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b312  test    al, al
0x18000b314  jnz     short loc_18000B329
0x18000b316  mov     rax, [rdi]
0x18000b319  lea     edx, [rbx+1]
0x18000b31c  mov     rcx, rdi
0x18000b31f  mov     rax, [rax]
0x18000b322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b327  jmp     short loc_18000B32C
0x18000b329  mov     rbx, rdi
0x18000b32c  mov     [rsi], rbx
0x18000b32f  mov     rax, rsi
0x18000b332  mov     rbx, [rsp+28h+arg_0]
0x18000b337  mov     rsi, [rsp+28h+arg_8]
0x18000b33c  add     rsp, 20h
0x18000b340  pop     rdi
0x18000b341  retn
```
