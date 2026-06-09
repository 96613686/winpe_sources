# common_fsopen<wchar_t>(wchar_t const * const,wchar_t const * const,int)

- ea: `0x140016ec4`
- end: `0x140016f8d`
- name: `??$common_fsopen@_W@@YAPEAU_iobuf@@QEB_W0H@Z`
- size: `201`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140016f90`

## callees

- `0x14001609c`
- `0x140016ea0`
- `0x140016ec4`
- `0x14001b1f8`
- `0x14001bdb8`
- `0x14001be10`
- `0x14001cca0`

## pseudocode

```c
__int64 __fastcall common_fsopen<wchar_t>(_WORD *a1, _WORD *a2, unsigned int a3)
{
  __int64 v7; // rbx
  FILE *File; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 || !a2 || !*a2 )
  {
    *(_DWORD *)sub_140016EA0() = 22;
    invalid_parameter_noinfo();
    return 0;
  }
  if ( !*a1 )
  {
    *(_DWORD *)sub_140016EA0() = 22;
    return 0;
  }
  __acrt_stdio_allocate_stream(&File);
  if ( !File )
  {
    *(_DWORD *)sub_140016EA0() = 24;
    return 0;
  }
  v7 = wopenfile(a1, a2, a3);
  if ( !v7 )
    __acrt_stdio_free_stream(File);
  unlock_file(File);
  return v7;
}

```

## disassembly

```asm
0x140016ec4  mov     [rsp+arg_8], rbx
0x140016ec9  mov     [rsp+arg_10], rsi
0x140016ece  mov     [rsp+arg_18], rdi
0x140016ed3  push    r14
0x140016ed5  sub     rsp, 30h
0x140016ed9  mov     esi, r8d
0x140016edc  mov     rbx, rdx
0x140016edf  mov     rdi, rcx
0x140016ee2  xor     r14d, r14d
0x140016ee5  test    rcx, rcx
0x140016ee8  jnz     short loc_140016F12
0x140016eea  call    sub_140016EA0
0x140016eef  mov     dword ptr [rax], 16h
0x140016ef5  call    _invalid_parameter_noinfo
0x140016efa  xor     eax, eax
0x140016efc  mov     rbx, [rsp+38h+arg_8]
0x140016f01  mov     rsi, [rsp+38h+arg_10]
0x140016f06  mov     rdi, [rsp+38h+arg_18]
0x140016f0b  add     rsp, 30h
0x140016f0f  pop     r14
0x140016f11  retn
0x140016f12  test    rbx, rbx
0x140016f15  jz      short loc_140016EEA
0x140016f17  cmp     [rdx], r14w
0x140016f1b  jz      short loc_140016EEA
0x140016f1d  cmp     [rcx], r14w
0x140016f21  jnz     short loc_140016F30
0x140016f23  call    sub_140016EA0
0x140016f28  mov     dword ptr [rax], 16h
0x140016f2e  jmp     short loc_140016EFA
0x140016f30  lea     rcx, [rsp+38h+File]
0x140016f35  call    ?__acrt_stdio_allocate_stream@@YA?AV__crt_stdio_stream@@XZ
0x140016f3a  mov     r9, [rsp+38h+File]
0x140016f3f  test    r9, r9
0x140016f42  jnz     short loc_140016F51
0x140016f44  call    sub_140016EA0
0x140016f49  mov     dword ptr [rax], 18h
0x140016f4f  jmp     short loc_140016EFA
0x140016f51  mov     [rsp+38h+var_18], r14
0x140016f56  mov     r8d, esi
0x140016f59  mov     rdx, rbx
0x140016f5c  mov     rcx, rdi
0x140016f5f  call    _wopenfile
0x140016f64  mov     rbx, rax
0x140016f67  mov     [rsp+38h+var_18], rax
0x140016f6c  test    rbx, rbx
0x140016f6f  jnz     short loc_140016F7B
0x140016f71  mov     rcx, [rsp+38h+File]
0x140016f76  call    ?__acrt_stdio_free_stream@@YAXV__crt_stdio_stream@@@Z
0x140016f7b  mov     rcx, [rsp+38h+File]; File
0x140016f80  call    _unlock_file
0x140016f85  mov     rax, rbx
0x140016f88  jmp     loc_140016EFC
```
