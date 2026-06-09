# __scrt_common_main_seh(void)

- ea: `0x140051f0c`
- end: `0x140052088`
- name: `?__scrt_common_main_seh@@YAHXZ`
- size: `380`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140052090`

## callees

- `0x140018428`
- `0x1400517e4`
- `0x140051820`
- `0x1400518e8`
- `0x140051980`
- `0x1400519a4`
- `0x140051f0c`
- `0x1400528e4`
- `0x140052a38`
- `0x140052bf4`
- `0x140052bfc`
- `0x1400705b8`
- `0x14007099c`
- `0x1400709ac`
- `0x1400709bc`
- `0x1400709c8`
- `0x140070a04`
- `0x1400710d8`
- `0x140071894`
- `0x1400718cc`
- `0x140071978`
- `0x140071980`
- `0x14007fbb0`

## pseudocode

```c
__int64 __fastcall __scrt_common_main_seh()
{
  unsigned int v0; // ebx
  __int64 v1; // rcx
  char v2; // si
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rbx
  const char **v12; // rdi
  __int64 v13; // rcx
  const char **v14; // rbx
  __int64 v15; // rcx
  int *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
  {
    sub_1400528E4(7);
    goto LABEL_19;
  }
  v2 = 0;
  LOBYTE(v0) = _scrt_acquire_startup_lock(v1);
  v3 = (unsigned int)dword_1400C3C40;
  if ( dword_1400C3C40 == 1 )
  {
LABEL_19:
    sub_1400528E4(7);
    goto LABEL_20;
  }
  if ( dword_1400C3C40 )
  {
    v2 = 1;
  }
  else
  {
    dword_1400C3C40 = 1;
    if ( (unsigned int)sub_1400718CC(&qword_140089038, qword_140089080) )
      return 255;
    sub_140071894(&qword_1400886F8, qword_140088FE0);
    dword_1400C3C40 = 2;
  }
  LOBYTE(v3) = v0;
  _scrt_release_startup_lock(v3);
  v6 = (_QWORD *)sub_140052BF4(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))v6;
  if ( *v6 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v6) )
    (*v8)(0, 2);
  v9 = (_QWORD *)sub_140052BFC(v7);
  v11 = v9;
  if ( *v9 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v9) )
    sub_1400709C8(*v11);
  v12 = (const char **)unknown_libname_92(v10);
  v14 = *(const char ***)sub_140071980(v13);
  v16 = (int *)sub_140071978(v15);
  v0 = main(*v16, v14, v12);
  if ( !(unsigned __int8)sub_140052A38(v17) )
LABEL_20:
    exit(v0);
  if ( !v2 )
    cexit();
  LOBYTE(v18) = 1;
  _scrt_uninitialize_crt(v18, 0);
  return v0;
}

```

## disassembly

```asm
0x140051f0c  mov     [rsp+arg_0], rbx
0x140051f11  mov     [rsp+arg_8], rsi
0x140051f16  push    rdi
0x140051f17  sub     rsp, 30h
0x140051f1b  mov     ecx, 1
0x140051f20  call    __scrt_initialize_crt
0x140051f25  test    al, al
0x140051f27  jz      loc_140052063
0x140051f2d  xor     sil, sil
0x140051f30  mov     [rsp+38h+var_18], sil
0x140051f35  call    __scrt_acquire_startup_lock
0x140051f3a  mov     bl, al
0x140051f3c  mov     ecx, cs:dword_1400C3C40
0x140051f42  cmp     ecx, 1
0x140051f45  jz      loc_14005206E
0x140051f4b  test    ecx, ecx
0x140051f4d  jnz     short loc_140051F99
0x140051f4f  mov     cs:dword_1400C3C40, 1
0x140051f59  lea     rdx, qword_140089080
0x140051f60  lea     rcx, qword_140089038
0x140051f67  call    sub_1400718CC
0x140051f6c  test    eax, eax
0x140051f6e  jz      short loc_140051F7A
0x140051f70  mov     eax, 0FFh
0x140051f75  jmp     loc_140052053
0x140051f7a  lea     rdx, qword_140088FE0
0x140051f81  lea     rcx, qword_1400886F8
0x140051f88  call    sub_140071894
0x140051f8d  mov     cs:dword_1400C3C40, 2
0x140051f97  jmp     short loc_140051FA1
0x140051f99  mov     sil, 1
0x140051f9c  mov     [rsp+38h+var_18], sil
0x140051fa1  mov     cl, bl
0x140051fa3  call    __scrt_release_startup_lock
0x140051fa8  call    sub_140052BF4
0x140051fad  mov     rbx, rax
0x140051fb0  cmp     qword ptr [rax], 0
0x140051fb4  jz      short loc_140051FD4
0x140051fb6  mov     rcx, rax
0x140051fb9  call    __scrt_is_nonwritable_in_current_image
0x140051fbe  test    al, al
0x140051fc0  jz      short loc_140051FD4
0x140051fc2  xor     r8d, r8d
0x140051fc5  lea     edx, [r8+2]
0x140051fc9  xor     ecx, ecx
0x140051fcb  mov     rax, [rbx]
0x140051fce  call    cs:__guard_dispatch_icall_fptr
0x140051fd4  call    sub_140052BFC
0x140051fd9  mov     rbx, rax
0x140051fdc  cmp     qword ptr [rax], 0
0x140051fe0  jz      short loc_140051FF6
0x140051fe2  mov     rcx, rax
0x140051fe5  call    __scrt_is_nonwritable_in_current_image
0x140051fea  test    al, al
0x140051fec  jz      short loc_140051FF6
0x140051fee  mov     rcx, [rbx]
0x140051ff1  call    sub_1400709C8
0x140051ff6  call    unknown_libname_92; Microsoft VisualC 64bit universal runtime
0x140051ffb  mov     rdi, rax
0x140051ffe  call    sub_140071980
0x140052003  mov     rbx, [rax]
0x140052006  call    sub_140071978
0x14005200b  mov     r8, rdi; envp
0x14005200e  mov     rdx, rbx; argv
0x140052011  mov     ecx, [rax]; argc
0x140052013  call    main
0x140052018  mov     ebx, eax
0x14005201a  call    sub_140052A38
0x14005201f  test    al, al
0x140052021  jz      short loc_140052078
0x140052023  test    sil, sil
0x140052026  jnz     short loc_14005202D
0x140052028  call    _cexit
0x14005202d  xor     edx, edx
0x14005202f  mov     cl, 1
0x140052031  call    __scrt_uninitialize_crt
0x140052036  mov     eax, ebx
0x140052038  jmp     short loc_140052053
0x14005203a  mov     ebx, eax
0x14005203c  call    sub_140052A38
0x140052041  test    al, al
0x140052043  jz      short loc_140052080
0x140052045  cmp     [rsp+38h+var_18], 0
0x14005204a  jnz     short loc_140052051
0x14005204c  call    sub_14007099C
0x140052051  mov     eax, ebx
0x140052053  mov     rbx, [rsp+38h+arg_0]
0x140052058  mov     rsi, [rsp+38h+arg_8]
0x14005205d  add     rsp, 30h
0x140052061  pop     rdi
0x140052062  retn
0x140052063  mov     ecx, 7
0x140052068  call    sub_1400528E4
0x14005206d  nop
0x14005206e  mov     ecx, 7
0x140052073  call    sub_1400528E4
0x140052078  mov     ecx, ebx; Code
0x14005207a  call    exit
0x140052080  mov     ecx, ebx; Code
0x140052082  call    _exit
0x14008523f  push    rbp
0x140085241  sub     rsp, 20h
0x140085245  mov     rbp, rdx
0x140085248  mov     rdx, rcx
0x14008524b  mov     rcx, [rcx]
0x14008524e  mov     ecx, [rcx]
0x140085250  call    sub_1400705B8
0x140085255  nop
0x140085256  add     rsp, 20h
0x14008525a  pop     rbp
0x14008525b  retn
```
