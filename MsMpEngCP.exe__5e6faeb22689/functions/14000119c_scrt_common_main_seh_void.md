# __scrt_common_main_seh(void)

- ea: `0x14000119c`
- end: `0x140001318`
- name: `?__scrt_common_main_seh@@YAHXZ`
- size: `380`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001320`

## callees

- `0x140001000`
- `0x14000119c`
- `0x140001370`
- `0x1400013ac`
- `0x140001474`
- `0x14000150c`
- `0x140001530`
- `0x1400016dc`
- `0x1400016e4`
- `0x1400016f8`
- `0x14000184c`
- `0x140004590`
- `0x140004e0c`
- `0x140004e64`
- `0x140004e9c`
- `0x140005150`
- `0x140005160`
- `0x140005170`
- `0x14000517c`
- `0x1400051b8`
- `0x140005238`
- `0x140005240`
- `0x14000cfb0`

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
    sub_1400016F8(7);
    goto LABEL_19;
  }
  v2 = 0;
  LOBYTE(v0) = _scrt_acquire_startup_lock(v1);
  v3 = (unsigned int)dword_140019AF0;
  if ( dword_140019AF0 == 1 )
  {
LABEL_19:
    sub_1400016F8(7);
    goto LABEL_20;
  }
  if ( dword_140019AF0 )
  {
    v2 = 1;
  }
  else
  {
    dword_140019AF0 = 1;
    if ( (unsigned int)sub_140004E9C(&qword_14000F2B0, &qword_14000F2E8) )
      return 255;
    sub_140004E64(&qword_14000F298, &qword_14000F2A8);
    dword_140019AF0 = 2;
  }
  LOBYTE(v3) = v0;
  _scrt_release_startup_lock(v3);
  v6 = (_QWORD *)sub_1400016DC(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))v6;
  if ( *v6 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v6) )
    (*v8)(0, 2);
  v9 = (_QWORD *)sub_1400016E4(v7);
  v11 = v9;
  if ( *v9 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v9) )
    sub_14000517C(*v11);
  v12 = (const char **)unknown_libname_13(v10);
  v14 = *(const char ***)sub_140005240(v13);
  v16 = (int *)sub_140005238(v15);
  v0 = main(*v16, v14, v12);
  if ( !(unsigned __int8)sub_14000184C(v17) )
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
0x14000119c  mov     [rsp+arg_0], rbx
0x1400011a1  mov     [rsp+arg_8], rsi
0x1400011a6  push    rdi
0x1400011a7  sub     rsp, 30h
0x1400011ab  mov     ecx, 1
0x1400011b0  call    __scrt_initialize_crt
0x1400011b5  test    al, al
0x1400011b7  jz      loc_1400012F3
0x1400011bd  xor     sil, sil
0x1400011c0  mov     [rsp+38h+var_18], sil
0x1400011c5  call    __scrt_acquire_startup_lock
0x1400011ca  mov     bl, al
0x1400011cc  mov     ecx, cs:dword_140019AF0
0x1400011d2  cmp     ecx, 1
0x1400011d5  jz      loc_1400012FE
0x1400011db  test    ecx, ecx
0x1400011dd  jnz     short loc_140001229
0x1400011df  mov     cs:dword_140019AF0, 1
0x1400011e9  lea     rdx, qword_14000F2E8
0x1400011f0  lea     rcx, qword_14000F2B0
0x1400011f7  call    sub_140004E9C
0x1400011fc  test    eax, eax
0x1400011fe  jz      short loc_14000120A
0x140001200  mov     eax, 0FFh
0x140001205  jmp     loc_1400012E3
0x14000120a  lea     rdx, qword_14000F2A8
0x140001211  lea     rcx, qword_14000F298
0x140001218  call    sub_140004E64
0x14000121d  mov     cs:dword_140019AF0, 2
0x140001227  jmp     short loc_140001231
0x140001229  mov     sil, 1
0x14000122c  mov     [rsp+38h+var_18], sil
0x140001231  mov     cl, bl
0x140001233  call    __scrt_release_startup_lock
0x140001238  call    sub_1400016DC
0x14000123d  mov     rbx, rax
0x140001240  cmp     qword ptr [rax], 0
0x140001244  jz      short loc_140001264
0x140001246  mov     rcx, rax
0x140001249  call    __scrt_is_nonwritable_in_current_image
0x14000124e  test    al, al
0x140001250  jz      short loc_140001264
0x140001252  xor     r8d, r8d
0x140001255  lea     edx, [r8+2]
0x140001259  xor     ecx, ecx
0x14000125b  mov     rax, [rbx]
0x14000125e  call    cs:__guard_dispatch_icall_fptr
0x140001264  call    sub_1400016E4
0x140001269  mov     rbx, rax
0x14000126c  cmp     qword ptr [rax], 0
0x140001270  jz      short loc_140001286
0x140001272  mov     rcx, rax
0x140001275  call    __scrt_is_nonwritable_in_current_image
0x14000127a  test    al, al
0x14000127c  jz      short loc_140001286
0x14000127e  mov     rcx, [rbx]
0x140001281  call    sub_14000517C
0x140001286  call    unknown_libname_13; Microsoft VisualC 64bit universal runtime
0x14000128b  mov     rdi, rax
0x14000128e  call    sub_140005240
0x140001293  mov     rbx, [rax]
0x140001296  call    sub_140005238
0x14000129b  mov     r8, rdi; envp
0x14000129e  mov     rdx, rbx; argv
0x1400012a1  mov     ecx, [rax]; argc
0x1400012a3  call    main
0x1400012a8  mov     ebx, eax
0x1400012aa  call    sub_14000184C
0x1400012af  test    al, al
0x1400012b1  jz      short loc_140001308
0x1400012b3  test    sil, sil
0x1400012b6  jnz     short loc_1400012BD
0x1400012b8  call    _cexit
0x1400012bd  xor     edx, edx
0x1400012bf  mov     cl, 1
0x1400012c1  call    __scrt_uninitialize_crt
0x1400012c6  mov     eax, ebx
0x1400012c8  jmp     short loc_1400012E3
0x1400012ca  mov     ebx, eax
0x1400012cc  call    sub_14000184C
0x1400012d1  test    al, al
0x1400012d3  jz      short loc_140001310
0x1400012d5  cmp     [rsp+38h+var_18], 0
0x1400012da  jnz     short loc_1400012E1
0x1400012dc  call    sub_140005150
0x1400012e1  mov     eax, ebx
0x1400012e3  mov     rbx, [rsp+38h+arg_0]
0x1400012e8  mov     rsi, [rsp+38h+arg_8]
0x1400012ed  add     rsp, 30h
0x1400012f1  pop     rdi
0x1400012f2  retn
0x1400012f3  mov     ecx, 7
0x1400012f8  call    sub_1400016F8
0x1400012fd  nop
0x1400012fe  mov     ecx, 7
0x140001303  call    sub_1400016F8
0x140001308  mov     ecx, ebx; Code
0x14000130a  call    exit
0x140001310  mov     ecx, ebx; Code
0x140001312  call    _exit
0x14000dc60  push    rbp
0x14000dc62  sub     rsp, 20h
0x14000dc66  mov     rbp, rdx
0x14000dc69  mov     rdx, rcx
0x14000dc6c  mov     rcx, [rcx]
0x14000dc6f  mov     ecx, [rcx]
0x14000dc71  call    sub_140004590
0x14000dc76  nop
0x14000dc77  add     rsp, 20h
0x14000dc7b  pop     rbp
0x14000dc7c  retn
```
