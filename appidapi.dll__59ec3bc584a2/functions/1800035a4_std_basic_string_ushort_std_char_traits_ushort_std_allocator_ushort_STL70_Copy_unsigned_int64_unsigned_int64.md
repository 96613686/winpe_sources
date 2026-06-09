# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800035a4`
- end: `0x1800036f4`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `336`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003330`
- `0x18000379c`
- `0x1800038a8`
- `0x1800039e8`

## callees

- `0x180001048`
- `0x180001098`
- `0x18000227c`
- `0x180003140`
- `0x1800035a4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000368a`
- `msvcrt!memcpy_s` at `0x18000368a`

## pseudocode

```c
void __fastcall std::wstring::_Copy(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  __int64 v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r12
  void **v11; // rsi
  void *v12; // r8
  __int64 v13; // r13
  __int64 *v14; // rbp
  unsigned __int64 v15; // rcx
  __int64 *v16; // rdx
  __int64 v17; // [rsp+0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v19[80]; // [rsp+38h] [rbp-50h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 32);
    v8 = v7 >> 1;
    if ( v6 / 3 < v7 >> 1 && v7 <= 0x7FFFFFFFFFFFFFFELL - v8 )
      v4 = v8 + v7;
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else if ( 0xFFFFFFFFFFFFFFFFuLL / v9 < 2 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
      throw (std::bad_alloc *)pExceptionObject;
    }
    v10 = operator new(2 * v9);
  }
  catch ( ... )
  {
    v15 = a2 + 1;
    if ( a2 != -1 && 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)v19, 0);
      try
      {
        throw (std::bad_alloc *)v19;
      }
      catch ( ... )
      {
        v16 = &v17;
        v14 = v16;
        LOBYTE(v16) = 1;
        std::wstring::_Tidy(v14[18], v16, 0);
        throw;
      }
    }
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v10 = operator new(2 * v15);
  }
  v11 = (void **)(v5 + 8);
  if ( v3 )
  {
    if ( *(_QWORD *)(v5 + 32) < 8u )
      v12 = (void *)(v5 + 8);
    else
      v12 = *v11;
    v13 = 2 * v3;
    memcpy_s(v10, 2 * v4 + 2, v12, 2 * v3);
  }
  else
  {
    v13 = 0;
  }
  if ( *(_QWORD *)(v5 + 32) >= 8u )
    operator delete(*v11);
  *(_QWORD *)(v5 + 32) = 7;
  *v11 = v10;
  *(_QWORD *)(v5 + 32) = v4;
  if ( v4 >= 8 )
    v11 = (void **)v10;
  *(_QWORD *)(v5 + 24) = v3;
  *(_WORD *)((char *)v11 + v13) = 0;
}

```

## disassembly

```asm
0x1800035a4  mov     [rsp+arg_10], r8
0x1800035a9  mov     [rsp+arg_8], rdx
0x1800035ae  mov     [rsp+arg_0], rcx
0x1800035b3  push    rbx
0x1800035b4  push    rsi
0x1800035b5  push    rdi
0x1800035b6  push    r12
0x1800035b8  push    r13
0x1800035ba  push    r14
0x1800035bc  push    r15
0x1800035be  sub     rsp, 50h
0x1800035c2  mov     r15, r8
0x1800035c5  mov     rdi, rdx
0x1800035c8  mov     rbx, rcx
0x1800035cb  or      rdx, 7
0x1800035cf  mov     r9, 7FFFFFFFFFFFFFFEh
0x1800035d9  cmp     rdx, r9
0x1800035dc  ja      short loc_18000360C
0x1800035de  mov     rdi, rdx
0x1800035e1  mov     r8, [rcx+20h]
0x1800035e5  mov     rcx, r8
0x1800035e8  shr     rcx, 1
0x1800035eb  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800035f5  mul     rdx
0x1800035f8  shr     rdx, 1
0x1800035fb  cmp     rdx, rcx
0x1800035fe  jnb     short loc_18000360C
0x180003600  sub     r9, rcx
0x180003603  cmp     r8, r9
0x180003606  ja      short loc_18000360C
0x180003608  lea     rdi, [rcx+r8]
0x18000360c  lea     rcx, [rdi+1]
0x180003610  xor     r14d, r14d
0x180003613  test    rcx, rcx
0x180003616  jnz     short loc_180003628
0x180003618  mov     ecx, r14d
0x18000361b  add     rcx, rcx; Size
0x18000361e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003623  mov     r12, rax
0x180003626  jmp     short loc_180003660
0x180003628  xor     edx, edx
0x18000362a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000362e  div     rcx
0x180003631  cmp     rax, 2
0x180003635  jb      loc_1800036D5
0x18000363b  jmp     short loc_18000361B
0x18000363d  xor     r14d, r14d
0x180003640  mov     rbx, [rsp+88h+arg_0]
0x180003648  mov     r15, [rsp+88h+arg_10]
0x180003650  mov     rdi, [rsp+88h+arg_8]
0x180003658  mov     r12, [rsp+88h+arg_18]
0x180003660  lea     rsi, [rbx+8]
0x180003664  test    r15, r15
0x180003667  jz      short loc_180003692
0x180003669  cmp     qword ptr [rbx+20h], 8
0x18000366e  jb      short loc_180003675
0x180003670  mov     r8, [rsi]
0x180003673  jmp     short loc_180003678
0x180003675  mov     r8, rsi; Source
0x180003678  lea     r13, [r15+r15]
0x18000367c  lea     rdx, ds:2[rdi*2]; DestinationSize
0x180003684  mov     r9, r13; SourceSize
0x180003687  mov     rcx, r12; Destination
0x18000368a  call    cs:__imp_memcpy_s
0x180003690  jmp     short loc_180003696
0x180003692  lea     r13, [r15+r15]
0x180003696  cmp     qword ptr [rbx+20h], 8
0x18000369b  jb      short loc_1800036A5
0x18000369d  mov     rcx, [rsi]; Block
0x1800036a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800036a5  mov     qword ptr [rbx+20h], 7
0x1800036ad  mov     [rsi], r12
0x1800036b0  mov     [rbx+20h], rdi
0x1800036b4  cmp     rdi, 8
0x1800036b8  cmovnb  rsi, r12
0x1800036bc  mov     [rbx+18h], r15
0x1800036c0  mov     [rsi+r13], r14w
0x1800036c5  add     rsp, 50h
0x1800036c9  pop     r15
0x1800036cb  pop     r14
0x1800036cd  pop     r13
0x1800036cf  pop     r12
0x1800036d1  pop     rdi
0x1800036d2  pop     rsi
0x1800036d3  pop     rbx
0x1800036d4  retn
0x1800036d5  xor     edx, edx; char *
0x1800036d7  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800036dc  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x1800036e1  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800036e8  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800036ed  call    _CxxThrowException_0
```
