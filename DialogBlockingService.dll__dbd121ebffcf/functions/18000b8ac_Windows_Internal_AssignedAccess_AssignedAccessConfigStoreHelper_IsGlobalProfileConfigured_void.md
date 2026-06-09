# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::IsGlobalProfileConfigured(void)

- ea: `0x18000b8ac`
- end: `0x18000b9f8`
- name: `?IsGlobalProfileConfigured@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@QEAA_NXZ`
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
- `0x18000b8ac`
- `0x18000e010`

## pseudocode

```c
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::IsGlobalProfileConfigured(
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
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) )
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
0x18000b8ac  mov     rax, rsp
0x18000b8af  push    rbx
0x18000b8b0  push    rbp
0x18000b8b1  push    rsi
0x18000b8b2  push    rdi
0x18000b8b3  push    r13
0x18000b8b5  push    r14
0x18000b8b7  push    r15
0x18000b8b9  sub     rsp, 40h
0x18000b8bd  mov     r13, rcx
0x18000b8c0  lea     rcx, [rax+18h]
0x18000b8c4  call    ?CreateInstance@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::CreateInstance(void)
0x18000b8c9  lea     rcx, [rsp+78h+arg_0]
0x18000b8d1  call    ?CreateInstance@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::CreateInstance(void)
0x18000b8d6  lea     rcx, [rsp+78h+arg_8]
0x18000b8de  call    ?CreateInstance@AssignedAccessConfigStoreV2@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::CreateInstance(void)
0x18000b8e3  mov     rdi, [rsp+78h+arg_10]
0x18000b8eb  mov     rsi, [rsp+78h+arg_0]
0x18000b8f3  mov     r14, [rsp+78h+arg_8]
0x18000b8fb  test    rdi, rdi
0x18000b8fe  jz      short loc_18000B95B
0x18000b900  test    rsi, rsi
0x18000b903  jz      short loc_18000B95B
0x18000b905  test    r14, r14
0x18000b908  jz      short loc_18000B95E
0x18000b90a  mov     [rsp+78h+var_58], rdi
0x18000b90f  lea     r15, [rsp+78h+var_58]
0x18000b914  mov     [rsp+78h+var_50], rsi
0x18000b919  mov     [rsp+78h+var_48], r14
0x18000b91e  mov     rbp, [r15]
0x18000b921  mov     ebx, [r13+18h]
0x18000b925  mov     rcx, rbp
0x18000b928  mov     rax, [rbp+0]
0x18000b92c  mov     rax, [rax+20h]
0x18000b930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b935  cmp     ebx, eax
0x18000b937  ja      short loc_18000B94D
0x18000b939  mov     rax, [rbp+0]
0x18000b93d  mov     rcx, rbp
0x18000b940  mov     rax, [rax+18h]
0x18000b944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b949  test    al, al
0x18000b94b  jnz     short loc_18000B9B2
0x18000b94d  add     r15, 8
0x18000b951  lea     rax, [rsp+78h+var_40]
0x18000b956  cmp     r15, rax
0x18000b959  jnz     short loc_18000B91E
0x18000b95b  test    r14, r14
0x18000b95e  mov     ebx, 1
0x18000b963  jz      short loc_18000B975
0x18000b965  mov     rax, [r14]
0x18000b968  mov     edx, ebx
0x18000b96a  mov     rcx, r14
0x18000b96d  mov     rax, [rax]
0x18000b970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b975  test    rsi, rsi
0x18000b978  jz      short loc_18000B98A
0x18000b97a  mov     rax, [rsi]
0x18000b97d  mov     edx, ebx
0x18000b97f  mov     rcx, rsi
0x18000b982  mov     rax, [rax]
0x18000b985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b98a  test    rdi, rdi
0x18000b98d  jz      short loc_18000B99F
0x18000b98f  mov     rax, [rdi]
0x18000b992  mov     edx, ebx
0x18000b994  mov     rcx, rdi
0x18000b997  mov     rax, [rax]
0x18000b99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b99f  xor     bl, bl
0x18000b9a1  mov     al, bl
0x18000b9a3  add     rsp, 40h
0x18000b9a7  pop     r15
0x18000b9a9  pop     r14
0x18000b9ab  pop     r13
0x18000b9ad  pop     rdi
0x18000b9ae  pop     rsi
0x18000b9af  pop     rbp
0x18000b9b0  pop     rbx
0x18000b9b1  retn
0x18000b9b2  mov     ebx, 1
0x18000b9b7  test    r14, r14
0x18000b9ba  jz      short loc_18000B9CC
0x18000b9bc  mov     rax, [r14]
0x18000b9bf  mov     edx, ebx
0x18000b9c1  mov     rcx, r14
0x18000b9c4  mov     rax, [rax]
0x18000b9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9cc  test    rsi, rsi
0x18000b9cf  jz      short loc_18000B9E1
0x18000b9d1  mov     rax, [rsi]
0x18000b9d4  mov     edx, ebx
0x18000b9d6  mov     rcx, rsi
0x18000b9d9  mov     rax, [rax]
0x18000b9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9e1  test    rdi, rdi
0x18000b9e4  jz      short loc_18000B9A1
0x18000b9e6  mov     rax, [rdi]
0x18000b9e9  mov     edx, ebx
0x18000b9eb  mov     rcx, rdi
0x18000b9ee  mov     rax, [rax]
0x18000b9f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f6  jmp     short loc_18000B9A1
```
