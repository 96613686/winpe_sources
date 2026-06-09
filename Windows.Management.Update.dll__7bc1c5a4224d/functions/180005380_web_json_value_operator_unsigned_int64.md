# web::json::value::operator[](unsigned __int64)

- ea: `0x180005380`
- end: `0x180005411`
- name: `??Avalue@json@web@@QEAAAEAV012@_K@Z`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180018440`
- `0x180026778`

## callees

- `0x180002cfc`
- `0x180005380`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall web::json::value::operator[](_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rcx

  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 88LL))(*a1) == 5 )
  {
    v4 = operator new(0x20u);
    if ( v4 )
    {
      *v4 = &web::json::details::_Array::`vftable';
      v4[1] = 0;
      v4[2] = 0;
      v4[3] = 0;
    }
    else
    {
      v4 = 0;
    }
    v5 = *a1;
    *a1 = v4;
    if ( v5 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 192LL))(v5, 1);
  }
  return (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 32LL))(*a1, a2);
}

```

## disassembly

```asm
0x180005380  mov     [rsp+arg_8], rbx
0x180005385  push    rdi
0x180005386  sub     rsp, 20h
0x18000538a  mov     rbx, rcx
0x18000538d  mov     rdi, rdx
0x180005390  mov     rcx, [rcx]
0x180005393  mov     rax, [rcx]
0x180005396  mov     rax, [rax+58h]
0x18000539a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539f  cmp     eax, 5
0x1800053a2  jnz     short loc_1800053F5
0x1800053a4  mov     ecx, 20h ; ' '; Size
0x1800053a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800053ae  mov     [rsp+28h+arg_0], rax
0x1800053b3  test    rax, rax
0x1800053b6  jz      short loc_1800053D2
0x1800053b8  lea     rcx, ??_7_Array@details@json@web@@6B@; const web::json::details::_Array::`vftable'
0x1800053bf  mov     [rax], rcx
0x1800053c2  xor     ecx, ecx
0x1800053c4  mov     [rax+8], rcx
0x1800053c8  mov     [rax+10h], rcx
0x1800053cc  mov     [rax+18h], rcx
0x1800053d0  jmp     short loc_1800053D6
0x1800053d2  xor     ecx, ecx
0x1800053d4  mov     eax, ecx
0x1800053d6  mov     rcx, [rbx]
0x1800053d9  mov     [rbx], rax
0x1800053dc  test    rcx, rcx
0x1800053df  jz      short loc_1800053F5
0x1800053e1  mov     rax, [rcx]
0x1800053e4  mov     edx, 1
0x1800053e9  mov     rax, [rax+0C0h]
0x1800053f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f5  mov     rcx, [rbx]
0x1800053f8  mov     rdx, rdi
0x1800053fb  mov     rax, [rcx]
0x1800053fe  mov     rax, [rax+20h]
0x180005402  mov     rbx, [rsp+28h+arg_8]
0x180005407  add     rsp, 20h
0x18000540b  pop     rdi
0x18000540c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
