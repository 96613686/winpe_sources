# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::DoesTargetProfileExist(ushort const *)

- ea: `0x18000b518`
- end: `0x18000b678`
- name: `?DoesTargetProfileExist@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@QEAA_NPEBG@Z`
- size: `352`
- prototype: `char __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000ab90`

## callees

- `0x18000b1f4`
- `0x18000b2cc`
- `0x18000b348`
- `0x18000b518`
- `0x18000e010`

## pseudocode

```c
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::DoesTargetProfileExist(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *this,
        const unsigned __int16 *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64); // rsi
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v5; // rdi
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v6; // r14
  bool v7; // zf
  _QWORD *v8; // r15
  __int64 v9; // rbp
  unsigned int v10; // ebx
  char v11; // bl
  _QWORD v13[3]; // [rsp+20h] [rbp-58h] BYREF
  char v14; // [rsp+38h] [rbp-40h] BYREF
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v15; // [rsp+80h] [rbp+8h] BYREF
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v16; // [rsp+88h] [rbp+10h] BYREF
  void (__fastcall ***v17)(_QWORD, __int64); // [rsp+90h] [rbp+18h] BYREF

  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::CreateInstance(&v17);
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::CreateInstance(&v15);
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::CreateInstance(&v16);
  v4 = v17;
  v5 = v15;
  v6 = v16;
  if ( !v17 || !v15 )
  {
LABEL_8:
    v7 = v6 == 0;
    goto LABEL_9;
  }
  v7 = v16 == 0;
  if ( !v16 )
  {
LABEL_9:
    if ( !v7 )
      (**(void (__fastcall ***)(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *, __int64))v6)(v6, 1);
    if ( v5 )
      (**(void (__fastcall ***)(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *, __int64))v5)(v5, 1);
    if ( v4 )
      (**v4)(v4, 1);
    return 0;
  }
  v13[0] = v17;
  v8 = v13;
  v13[1] = v15;
  v13[2] = v16;
  while ( 1 )
  {
    v9 = *v8;
    v10 = *((_DWORD *)this + 6);
    if ( v10 <= (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 32LL))(*v8) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v9 + 8LL))(v9, a2) )
        break;
    }
    if ( ++v8 == (_QWORD *)&v14 )
      goto LABEL_8;
  }
  v11 = 1;
  if ( v6 )
    (**(void (__fastcall ***)(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *, __int64))v6)(v6, 1);
  if ( v5 )
    (**(void (__fastcall ***)(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *, __int64))v5)(v5, 1);
  if ( v4 )
    (**v4)(v4, 1);
  return v11;
}

```

## disassembly

```asm
0x18000b518  mov     rax, rsp
0x18000b51b  mov     [rax+20h], rbx
0x18000b51f  push    rbp
0x18000b520  push    rsi
0x18000b521  push    rdi
0x18000b522  push    r12
0x18000b524  push    r13
0x18000b526  push    r14
0x18000b528  push    r15
0x18000b52a  sub     rsp, 40h
0x18000b52e  mov     r13, rcx
0x18000b531  mov     r12, rdx
0x18000b534  lea     rcx, [rax+18h]
0x18000b538  call    ?CreateInstance@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::CreateInstance(void)
0x18000b53d  lea     rcx, [rsp+78h+arg_0]
0x18000b545  call    ?CreateInstance@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::CreateInstance(void)
0x18000b54a  lea     rcx, [rsp+78h+arg_8]
0x18000b552  call    ?CreateInstance@AssignedAccessConfigStoreV2@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::CreateInstance(void)
0x18000b557  mov     rsi, [rsp+78h+arg_10]
0x18000b55f  mov     rdi, [rsp+78h+arg_0]
0x18000b567  mov     r14, [rsp+78h+arg_8]
0x18000b56f  test    rsi, rsi
0x18000b572  jz      short loc_18000B5D2
0x18000b574  test    rdi, rdi
0x18000b577  jz      short loc_18000B5D2
0x18000b579  test    r14, r14
0x18000b57c  jz      short loc_18000B5D5
0x18000b57e  mov     [rsp+78h+var_58], rsi
0x18000b583  lea     r15, [rsp+78h+var_58]
0x18000b588  mov     [rsp+78h+var_50], rdi
0x18000b58d  mov     [rsp+78h+var_48], r14
0x18000b592  mov     rbp, [r15]
0x18000b595  mov     ebx, [r13+18h]
0x18000b599  mov     rcx, rbp
0x18000b59c  mov     rax, [rbp+0]
0x18000b5a0  mov     rax, [rax+20h]
0x18000b5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a9  cmp     ebx, eax
0x18000b5ab  ja      short loc_18000B5C4
0x18000b5ad  mov     rax, [rbp+0]
0x18000b5b1  mov     rdx, r12
0x18000b5b4  mov     rcx, rbp
0x18000b5b7  mov     rax, [rax+8]
0x18000b5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c0  test    al, al
0x18000b5c2  jnz     short loc_18000B632
0x18000b5c4  add     r15, 8
0x18000b5c8  lea     rax, [rsp+78h+var_40]
0x18000b5cd  cmp     r15, rax
0x18000b5d0  jnz     short loc_18000B592
0x18000b5d2  test    r14, r14
0x18000b5d5  mov     ebx, 1
0x18000b5da  jz      short loc_18000B5EC
0x18000b5dc  mov     rax, [r14]
0x18000b5df  mov     edx, ebx
0x18000b5e1  mov     rcx, r14
0x18000b5e4  mov     rax, [rax]
0x18000b5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5ec  test    rdi, rdi
0x18000b5ef  jz      short loc_18000B601
0x18000b5f1  mov     rax, [rdi]
0x18000b5f4  mov     edx, ebx
0x18000b5f6  mov     rcx, rdi
0x18000b5f9  mov     rax, [rax]
0x18000b5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b601  test    rsi, rsi
0x18000b604  jz      short loc_18000B616
0x18000b606  mov     rax, [rsi]
0x18000b609  mov     edx, ebx
0x18000b60b  mov     rcx, rsi
0x18000b60e  mov     rax, [rax]
0x18000b611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b616  xor     bl, bl
0x18000b618  mov     al, bl
0x18000b61a  mov     rbx, [rsp+78h+arg_18]
0x18000b622  add     rsp, 40h
0x18000b626  pop     r15
0x18000b628  pop     r14
0x18000b62a  pop     r13
0x18000b62c  pop     r12
0x18000b62e  pop     rdi
0x18000b62f  pop     rsi
0x18000b630  pop     rbp
0x18000b631  retn
0x18000b632  mov     ebx, 1
0x18000b637  test    r14, r14
0x18000b63a  jz      short loc_18000B64C
0x18000b63c  mov     rax, [r14]
0x18000b63f  mov     edx, ebx
0x18000b641  mov     rcx, r14
0x18000b644  mov     rax, [rax]
0x18000b647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b64c  test    rdi, rdi
0x18000b64f  jz      short loc_18000B661
0x18000b651  mov     rax, [rdi]
0x18000b654  mov     edx, ebx
0x18000b656  mov     rcx, rdi
0x18000b659  mov     rax, [rax]
0x18000b65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b661  test    rsi, rsi
0x18000b664  jz      short loc_18000B618
0x18000b666  mov     rax, [rsi]
0x18000b669  mov     edx, ebx
0x18000b66b  mov     rcx, rsi
0x18000b66e  mov     rax, [rax]
0x18000b671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b676  jmp     short loc_18000B618
```
