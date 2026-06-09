# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180004e60`
- end: `0x180004ff5`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `405`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004920`
- `0x180004c88`
- `0x180004d80`
- `0x180005000`
- `0x180005140`
- `0x180005780`
- `0x180010a78`

## callees

- `0x180004e60`
- `0x180005284`
- `0x180011a64`
- `0x180013294`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180004f9f`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180004f9f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004f3d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004f3d`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(_QWORD *a1, unsigned __int64 a2, __int64 a3)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  _QWORD *v9; // rsi
  _QWORD *result; // rax
  _QWORD pExceptionObject[12]; // [rsp+28h] [rbp-60h] BYREF
  const char *v12; // [rsp+A8h] [rbp+20h] BYREF

  v4 = a2;
  v5 = a1;
  if ( (a2 | 7) <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = a2 | 7;
    v6 = a1[3];
    v7 = v6 >> 1;
    if ( v6 >> 1 > (a2 | 7) / 3 )
    {
      v4 = v7 + v6;
      if ( v6 > 0x7FFFFFFFFFFFFFFELL - v7 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  v8 = v4 + 1;
  if ( v4 == -1 )
  {
    v9 = 0;
  }
  else if ( v8 > 0x7FFFFFFFFFFFFFFFLL || (v9 = operator new(2 * v8)) == 0 )
  {
    v12 = 0;
    exception::exception((exception *)pExceptionObject, &v12);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  if ( a3 )
  {
    if ( v5[3] >= 8u )
      std::char_traits<unsigned short>::copy(v9, *v5, a3);
    else
      std::char_traits<unsigned short>::copy(v9, v5, a3);
  }
  if ( v5[3] >= 8u )
    operator delete((void *)*v5);
  v5[3] = 7;
  result = v5 + 2;
  *v5 = v9;
  v5[3] = v4;
  if ( v4 >= 8 )
    v5 = v9;
  *result = a3;
  *((_WORD *)v5 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x180004e60  mov     [rsp+arg_10], r8
0x180004e65  mov     [rsp+arg_8], rdx
0x180004e6a  mov     [rsp+arg_0], rcx
0x180004e6f  push    rbx
0x180004e70  push    rsi
0x180004e71  push    rdi
0x180004e72  push    r14
0x180004e74  push    r15
0x180004e76  sub     rsp, 60h
0x180004e7a  mov     [rsp+88h+var_68], 0FFFFFFFFFFFFFFFEh
0x180004e83  mov     r14, r8
0x180004e86  mov     rbx, rdx
0x180004e89  mov     rdi, rcx
0x180004e8c  mov     r9, rdx
0x180004e8f  or      r9, 7
0x180004e93  mov     r10, 7FFFFFFFFFFFFFFEh
0x180004e9d  cmp     r9, r10
0x180004ea0  ja      short loc_180004EC8
0x180004ea2  mov     rbx, r9
0x180004ea5  mov     r8, [rcx+18h]
0x180004ea9  mov     rcx, r8
0x180004eac  shr     rcx, 1
0x180004eaf  mov     rax, 0AAAAAAAAAAAAAAABh
0x180004eb9  mul     r9
0x180004ebc  shr     rdx, 1
0x180004ebf  cmp     rcx, rdx
0x180004ec2  ja      loc_180004F6C
0x180004ec8  lea     rcx, [rbx+1]
0x180004ecc  test    rcx, rcx
0x180004ecf  jz      loc_180004FC2
0x180004ed5  mov     rax, 7FFFFFFFFFFFFFFFh
0x180004edf  cmp     rcx, rax
0x180004ee2  ja      loc_180004F87
0x180004ee8  add     rcx, rcx; Size
0x180004eeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ef0  mov     rsi, rax
0x180004ef3  test    rax, rax
0x180004ef6  jz      loc_180004F87
0x180004efc  xor     r15d, r15d
0x180004eff  test    r14, r14
0x180004f02  jnz     short loc_180004F45
0x180004f04  cmp     qword ptr [rdi+18h], 8
0x180004f09  jnb     short loc_180004F3A
0x180004f0b  mov     qword ptr [rdi+18h], 7
0x180004f13  lea     rax, [rdi+10h]
0x180004f17  mov     [rdi], rsi
0x180004f1a  mov     [rdi+18h], rbx
0x180004f1e  cmp     rbx, 8
0x180004f22  cmovnb  rdi, rsi
0x180004f26  mov     [rax], r14
0x180004f29  mov     [rdi+r14*2], r15w
0x180004f2e  add     rsp, 60h
0x180004f32  pop     r15
0x180004f34  pop     r14
0x180004f36  pop     rdi
0x180004f37  pop     rsi
0x180004f38  pop     rbx
0x180004f39  retn
0x180004f3a  mov     rcx, [rdi]
0x180004f3d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004f43  jmp     short loc_180004F0B
0x180004f45  cmp     qword ptr [rdi+18h], 8
0x180004f4a  jnb     short loc_180004F5C
0x180004f4c  mov     rdx, rdi
0x180004f4f  mov     r8, r14
0x180004f52  mov     rcx, rsi
0x180004f55  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180004f5a  jmp     short loc_180004F04
0x180004f5c  mov     rdx, [rdi]
0x180004f5f  mov     r8, r14
0x180004f62  mov     rcx, rsi
0x180004f65  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180004f6a  jmp     short loc_180004F04
0x180004f6c  mov     rax, r10
0x180004f6f  sub     rax, rcx
0x180004f72  cmp     r8, rax
0x180004f75  lea     rbx, [rcx+r8]
0x180004f79  jbe     loc_180004EC8
0x180004f7f  mov     rbx, r10
0x180004f82  jmp     loc_180004EC8
0x180004f87  xor     r15d, r15d
0x180004f8a  mov     [rsp+88h+arg_18], r15
0x180004f92  lea     rdx, [rsp+88h+arg_18]
0x180004f9a  lea     rcx, [rsp+88h+pExceptionObject]
0x180004f9f  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180004fa5  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180004fac  mov     [rsp+88h+pExceptionObject], rax
0x180004fb1  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180004fb8  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180004fbd  call    _CxxThrowException_0
0x180004fc2  xor     r15d, r15d
0x180004fc5  mov     esi, r15d
0x180004fc8  jmp     loc_180004EFF
0x180004fcd  xor     r15d, r15d
0x180004fd0  mov     rdi, [rsp+88h+arg_0]
0x180004fd8  mov     r14, [rsp+88h+arg_10]
0x180004fe0  mov     rbx, [rsp+88h+arg_8]
0x180004fe8  mov     rsi, [rsp+88h+arg_18]
0x180004ff0  jmp     loc_180004EFF
```
