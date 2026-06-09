# __scrt_common_main_seh(void)

- ea: `0x14000a02c`
- end: `0x14000a1a8`
- name: `?__scrt_common_main_seh@@YAHXZ`
- size: `380`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x14000a1b0`

## callees

- `0x140001fd8`
- `0x14000a02c`
- `0x14000a208`
- `0x14000a244`
- `0x14000a30c`
- `0x14000a3a4`
- `0x14000a3c8`
- `0x14000a7bc`
- `0x14000a7c4`
- `0x14000a7d8`
- `0x14000a92c`
- `0x140017b04`
- `0x1400183cc`
- `0x140018424`
- `0x14001845c`
- `0x140018710`
- `0x140018720`
- `0x140018730`
- `0x14001873c`
- `0x140018778`
- `0x140018908`
- `0x140018910`
- `0x140029bd0`

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
    sub_14000A7D8(7);
    goto LABEL_19;
  }
  v2 = 0;
  LOBYTE(v0) = _scrt_acquire_startup_lock(v1);
  v3 = (unsigned int)dword_14003DB80;
  if ( dword_14003DB80 == 1 )
  {
LABEL_19:
    sub_14000A7D8(7);
    goto LABEL_20;
  }
  if ( dword_14003DB80 )
  {
    v2 = 1;
  }
  else
  {
    dword_14003DB80 = 1;
    if ( (unsigned int)sub_14001845C(&qword_14002C490, qword_14002C4C8) )
      return 255;
    sub_140018424(&qword_14002C420, &qword_14002C488);
    dword_14003DB80 = 2;
  }
  LOBYTE(v3) = v0;
  _scrt_release_startup_lock(v3);
  v6 = (_QWORD *)sub_14000A7BC(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))v6;
  if ( *v6 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v6) )
    (*v8)(0, 2);
  v9 = (_QWORD *)sub_14000A7C4(v7);
  v11 = v9;
  if ( *v9 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v9) )
    sub_14001873C(*v11);
  v12 = (const char **)unknown_libname_45(v10);
  v14 = *(const char ***)sub_140018910(v13);
  v16 = (int *)sub_140018908(v15);
  v0 = main(*v16, v14, v12);
  if ( !(unsigned __int8)sub_14000A92C(v17) )
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
0x14000a02c  mov     [rsp+arg_0], rbx
0x14000a031  mov     [rsp+arg_8], rsi
0x14000a036  push    rdi
0x14000a037  sub     rsp, 30h
0x14000a03b  mov     ecx, 1
0x14000a040  call    __scrt_initialize_crt
0x14000a045  test    al, al
0x14000a047  jz      loc_14000A183
0x14000a04d  xor     sil, sil
0x14000a050  mov     [rsp+38h+var_18], sil
0x14000a055  call    __scrt_acquire_startup_lock
0x14000a05a  mov     bl, al
0x14000a05c  mov     ecx, cs:dword_14003DB80
0x14000a062  cmp     ecx, 1
0x14000a065  jz      loc_14000A18E
0x14000a06b  test    ecx, ecx
0x14000a06d  jnz     short loc_14000A0B9
0x14000a06f  mov     cs:dword_14003DB80, 1
0x14000a079  lea     rdx, qword_14002C4C8
0x14000a080  lea     rcx, qword_14002C490
0x14000a087  call    sub_14001845C
0x14000a08c  test    eax, eax
0x14000a08e  jz      short loc_14000A09A
0x14000a090  mov     eax, 0FFh
0x14000a095  jmp     loc_14000A173
0x14000a09a  lea     rdx, qword_14002C488
0x14000a0a1  lea     rcx, qword_14002C420
0x14000a0a8  call    sub_140018424
0x14000a0ad  mov     cs:dword_14003DB80, 2
0x14000a0b7  jmp     short loc_14000A0C1
0x14000a0b9  mov     sil, 1
0x14000a0bc  mov     [rsp+38h+var_18], sil
0x14000a0c1  mov     cl, bl
0x14000a0c3  call    __scrt_release_startup_lock
0x14000a0c8  call    sub_14000A7BC
0x14000a0cd  mov     rbx, rax
0x14000a0d0  cmp     qword ptr [rax], 0
0x14000a0d4  jz      short loc_14000A0F4
0x14000a0d6  mov     rcx, rax
0x14000a0d9  call    __scrt_is_nonwritable_in_current_image
0x14000a0de  test    al, al
0x14000a0e0  jz      short loc_14000A0F4
0x14000a0e2  xor     r8d, r8d
0x14000a0e5  lea     edx, [r8+2]
0x14000a0e9  xor     ecx, ecx
0x14000a0eb  mov     rax, [rbx]
0x14000a0ee  call    cs:__guard_dispatch_icall_fptr
0x14000a0f4  call    sub_14000A7C4
0x14000a0f9  mov     rbx, rax
0x14000a0fc  cmp     qword ptr [rax], 0
0x14000a100  jz      short loc_14000A116
0x14000a102  mov     rcx, rax
0x14000a105  call    __scrt_is_nonwritable_in_current_image
0x14000a10a  test    al, al
0x14000a10c  jz      short loc_14000A116
0x14000a10e  mov     rcx, [rbx]
0x14000a111  call    sub_14001873C
0x14000a116  call    unknown_libname_45; Microsoft VisualC 64bit universal runtime
0x14000a11b  mov     rdi, rax
0x14000a11e  call    sub_140018910
0x14000a123  mov     rbx, [rax]
0x14000a126  call    sub_140018908
0x14000a12b  mov     r8, rdi; envp
0x14000a12e  mov     rdx, rbx; argv
0x14000a131  mov     ecx, [rax]; argc
0x14000a133  call    main
0x14000a138  mov     ebx, eax
0x14000a13a  call    sub_14000A92C
0x14000a13f  test    al, al
0x14000a141  jz      short loc_14000A198
0x14000a143  test    sil, sil
0x14000a146  jnz     short loc_14000A14D
0x14000a148  call    _cexit
0x14000a14d  xor     edx, edx
0x14000a14f  mov     cl, 1
0x14000a151  call    __scrt_uninitialize_crt
0x14000a156  mov     eax, ebx
0x14000a158  jmp     short loc_14000A173
0x14000a15a  mov     ebx, eax
0x14000a15c  call    sub_14000A92C
0x14000a161  test    al, al
0x14000a163  jz      short loc_14000A1A0
0x14000a165  cmp     [rsp+38h+var_18], 0
0x14000a16a  jnz     short loc_14000A171
0x14000a16c  call    sub_140018710
0x14000a171  mov     eax, ebx
0x14000a173  mov     rbx, [rsp+38h+arg_0]
0x14000a178  mov     rsi, [rsp+38h+arg_8]
0x14000a17d  add     rsp, 30h
0x14000a181  pop     rdi
0x14000a182  retn
0x14000a183  mov     ecx, 7
0x14000a188  call    sub_14000A7D8
0x14000a18d  nop
0x14000a18e  mov     ecx, 7
0x14000a193  call    sub_14000A7D8
0x14000a198  mov     ecx, ebx; Code
0x14000a19a  call    exit
0x14000a1a0  mov     ecx, ebx; Code
0x14000a1a2  call    _exit
0x14002abf6  push    rbp
0x14002abf8  sub     rsp, 20h
0x14002abfc  mov     rbp, rdx
0x14002abff  mov     rdx, rcx
0x14002ac02  mov     rcx, [rcx]
0x14002ac05  mov     ecx, [rcx]
0x14002ac07  call    sub_140017B04
0x14002ac0c  nop
0x14002ac0d  add     rsp, 20h
0x14002ac11  pop     rbp
0x14002ac12  retn
```
