# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::DoesGroupConfigExist(void)

- ea: `0x18000b3c4`
- end: `0x18000b510`
- name: `?DoesGroupConfigExist@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@QEAA_NXZ`
- size: `332`
- prototype: `char __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000ab90`

## callees

- `0x18000b1f4`
- `0x18000b2cc`
- `0x18000b348`
- `0x18000b3c4`
- `0x18000e010`

## pseudocode

```c
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::DoesGroupConfigExist(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rdi
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v3; // rsi
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v4; // r14
  bool v5; // zf
  _QWORD *v6; // r15
  __int64 v7; // rbp
  unsigned int v8; // ebx
  char v9; // bl
  _QWORD v11[3]; // [rsp+20h] [rbp-58h] BYREF
  char v12; // [rsp+38h] [rbp-40h] BYREF
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v13; // [rsp+80h] [rbp+8h] BYREF
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v14; // [rsp+88h] [rbp+10h] BYREF
  void (__fastcall ***v15)(_QWORD, __int64); // [rsp+90h] [rbp+18h] BYREF

  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::CreateInstance(&v15);
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::CreateInstance(&v13);
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::CreateInstance(&v14);
  v2 = v15;
  v3 = v13;
  v4 = v14;
  if ( !v15 || !v13 )
  {
LABEL_8:
    v5 = v4 == 0;
    goto LABEL_9;
  }
  v5 = v14 == 0;
  if ( !v14 )
  {
LABEL_9:
    if ( !v5 )
      (**(void (__fastcall ***)(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *, __int64))v4)(v4, 1);
    if ( v3 )
      (**(void (__fastcall ***)(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *, __int64))v3)(v3, 1);
    if ( v2 )
      (**v2)(v2, 1);
    return 0;
  }
  v11[0] = v15;
  v6 = v11;
  v11[1] = v13;
  v11[2] = v14;
  while ( 1 )
  {
    v7 = *v6;
    v8 = *((_DWORD *)this + 6);
    if ( v8 <= (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 32LL))(*v6) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7) )
        break;
    }
    if ( ++v6 == (_QWORD *)&v12 )
      goto LABEL_8;
  }
  v9 = 1;
  if ( v4 )
    (**(void (__fastcall ***)(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *, __int64))v4)(v4, 1);
  if ( v3 )
    (**(void (__fastcall ***)(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *, __int64))v3)(v3, 1);
  if ( v2 )
    (**v2)(v2, 1);
  return v9;
}

```

## disassembly

```asm
0x18000b3c4  mov     rax, rsp
0x18000b3c7  push    rbx
0x18000b3c8  push    rbp
0x18000b3c9  push    rsi
0x18000b3ca  push    rdi
0x18000b3cb  push    r13
0x18000b3cd  push    r14
0x18000b3cf  push    r15
0x18000b3d1  sub     rsp, 40h
0x18000b3d5  mov     r13, rcx
0x18000b3d8  lea     rcx, [rax+18h]
0x18000b3dc  call    ?CreateInstance@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::CreateInstance(void)
0x18000b3e1  lea     rcx, [rsp+78h+arg_0]
0x18000b3e9  call    ?CreateInstance@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::CreateInstance(void)
0x18000b3ee  lea     rcx, [rsp+78h+arg_8]
0x18000b3f6  call    ?CreateInstance@AssignedAccessConfigStoreV2@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::CreateInstance(void)
0x18000b3fb  mov     rdi, [rsp+78h+arg_10]
0x18000b403  mov     rsi, [rsp+78h+arg_0]
0x18000b40b  mov     r14, [rsp+78h+arg_8]
0x18000b413  test    rdi, rdi
0x18000b416  jz      short loc_18000B473
0x18000b418  test    rsi, rsi
0x18000b41b  jz      short loc_18000B473
0x18000b41d  test    r14, r14
0x18000b420  jz      short loc_18000B476
0x18000b422  mov     [rsp+78h+var_58], rdi
0x18000b427  lea     r15, [rsp+78h+var_58]
0x18000b42c  mov     [rsp+78h+var_50], rsi
0x18000b431  mov     [rsp+78h+var_48], r14
0x18000b436  mov     rbp, [r15]
0x18000b439  mov     ebx, [r13+18h]
0x18000b43d  mov     rcx, rbp
0x18000b440  mov     rax, [rbp+0]
0x18000b444  mov     rax, [rax+20h]
0x18000b448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b44d  cmp     ebx, eax
0x18000b44f  ja      short loc_18000B465
0x18000b451  mov     rax, [rbp+0]
0x18000b455  mov     rcx, rbp
0x18000b458  mov     rax, [rax+10h]
0x18000b45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b461  test    al, al
0x18000b463  jnz     short loc_18000B4CA
0x18000b465  add     r15, 8
0x18000b469  lea     rax, [rsp+78h+var_40]
0x18000b46e  cmp     r15, rax
0x18000b471  jnz     short loc_18000B436
0x18000b473  test    r14, r14
0x18000b476  mov     ebx, 1
0x18000b47b  jz      short loc_18000B48D
0x18000b47d  mov     rax, [r14]
0x18000b480  mov     edx, ebx
0x18000b482  mov     rcx, r14
0x18000b485  mov     rax, [rax]
0x18000b488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b48d  test    rsi, rsi
0x18000b490  jz      short loc_18000B4A2
0x18000b492  mov     rax, [rsi]
0x18000b495  mov     edx, ebx
0x18000b497  mov     rcx, rsi
0x18000b49a  mov     rax, [rax]
0x18000b49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4a2  test    rdi, rdi
0x18000b4a5  jz      short loc_18000B4B7
0x18000b4a7  mov     rax, [rdi]
0x18000b4aa  mov     edx, ebx
0x18000b4ac  mov     rcx, rdi
0x18000b4af  mov     rax, [rax]
0x18000b4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4b7  xor     bl, bl
0x18000b4b9  mov     al, bl
0x18000b4bb  add     rsp, 40h
0x18000b4bf  pop     r15
0x18000b4c1  pop     r14
0x18000b4c3  pop     r13
0x18000b4c5  pop     rdi
0x18000b4c6  pop     rsi
0x18000b4c7  pop     rbp
0x18000b4c8  pop     rbx
0x18000b4c9  retn
0x18000b4ca  mov     ebx, 1
0x18000b4cf  test    r14, r14
0x18000b4d2  jz      short loc_18000B4E4
0x18000b4d4  mov     rax, [r14]
0x18000b4d7  mov     edx, ebx
0x18000b4d9  mov     rcx, r14
0x18000b4dc  mov     rax, [rax]
0x18000b4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4e4  test    rsi, rsi
0x18000b4e7  jz      short loc_18000B4F9
0x18000b4e9  mov     rax, [rsi]
0x18000b4ec  mov     edx, ebx
0x18000b4ee  mov     rcx, rsi
0x18000b4f1  mov     rax, [rax]
0x18000b4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f9  test    rdi, rdi
0x18000b4fc  jz      short loc_18000B4B9
0x18000b4fe  mov     rax, [rdi]
0x18000b501  mov     edx, ebx
0x18000b503  mov     rcx, rdi
0x18000b506  mov     rax, [rax]
0x18000b509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b50e  jmp     short loc_18000B4B9
```
