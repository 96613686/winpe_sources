# common_fsopen<wchar_t>(wchar_t const * const,wchar_t const * const,int)

- ea: `0x140023510`
- end: `0x1400235d9`
- name: `??$common_fsopen@_W@@YAPEAU_iobuf@@QEB_W0H@Z`
- size: `201`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400235dc`

## callees

- `0x1400046cc`
- `0x14000fa6c`
- `0x140011bc8`
- `0x14001ac14`
- `0x14001ac6c`
- `0x140023510`
- `0x14002404c`

## pseudocode

```c
__int64 __fastcall common_fsopen<wchar_t>(_WORD *a1, _WORD *a2, unsigned int a3)
{
  __int64 v7; // rbx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 || !a2 || !*a2 )
  {
    *(_DWORD *)sub_14000FA6C() = 22;
    invalid_parameter_noinfo();
    return 0;
  }
  if ( !*a1 )
  {
    *(_DWORD *)sub_14000FA6C() = 22;
    return 0;
  }
  __acrt_stdio_allocate_stream(&v8);
  if ( !v8 )
  {
    *(_DWORD *)sub_14000FA6C() = 24;
    return 0;
  }
  v7 = wopenfile(a1, a2, a3);
  if ( !v7 )
    __acrt_stdio_free_stream(v8);
  sub_140011BC8(v8);
  return v7;
}

```

## disassembly

```asm
0x140023510  mov     [rsp+arg_8], rbx
0x140023515  mov     [rsp+arg_10], rsi
0x14002351a  mov     [rsp+arg_18], rdi
0x14002351f  push    r14
0x140023521  sub     rsp, 30h
0x140023525  mov     esi, r8d
0x140023528  mov     rbx, rdx
0x14002352b  mov     rdi, rcx
0x14002352e  xor     r14d, r14d
0x140023531  test    rcx, rcx
0x140023534  jnz     short loc_14002355E
0x140023536  call    sub_14000FA6C
0x14002353b  mov     dword ptr [rax], 16h
0x140023541  call    _invalid_parameter_noinfo
0x140023546  xor     eax, eax
0x140023548  mov     rbx, [rsp+38h+arg_8]
0x14002354d  mov     rsi, [rsp+38h+arg_10]
0x140023552  mov     rdi, [rsp+38h+arg_18]
0x140023557  add     rsp, 30h
0x14002355b  pop     r14
0x14002355d  retn
0x14002355e  test    rbx, rbx
0x140023561  jz      short loc_140023536
0x140023563  cmp     [rdx], r14w
0x140023567  jz      short loc_140023536
0x140023569  cmp     [rcx], r14w
0x14002356d  jnz     short loc_14002357C
0x14002356f  call    sub_14000FA6C
0x140023574  mov     dword ptr [rax], 16h
0x14002357a  jmp     short loc_140023546
0x14002357c  lea     rcx, [rsp+38h+arg_0]
0x140023581  call    ?__acrt_stdio_allocate_stream@@YA?AV__crt_stdio_stream@@XZ
0x140023586  mov     r9, [rsp+38h+arg_0]
0x14002358b  test    r9, r9
0x14002358e  jnz     short loc_14002359D
0x140023590  call    sub_14000FA6C
0x140023595  mov     dword ptr [rax], 18h
0x14002359b  jmp     short loc_140023546
0x14002359d  mov     [rsp+38h+var_18], r14
0x1400235a2  mov     r8d, esi
0x1400235a5  mov     rdx, rbx
0x1400235a8  mov     rcx, rdi
0x1400235ab  call    _wopenfile
0x1400235b0  mov     rbx, rax
0x1400235b3  mov     [rsp+38h+var_18], rax
0x1400235b8  test    rbx, rbx
0x1400235bb  jnz     short loc_1400235C7
0x1400235bd  mov     rcx, [rsp+38h+arg_0]
0x1400235c2  call    ?__acrt_stdio_free_stream@@YAXV__crt_stdio_stream@@@Z
0x1400235c7  mov     rcx, [rsp+38h+arg_0]
0x1400235cc  call    sub_140011BC8
0x1400235d1  mov     rax, rbx
0x1400235d4  jmp     loc_140023548
```
