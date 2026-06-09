# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001444`
- end: `0x180001579`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180001760`
- `0x180001850`

## callees

- `0x180001048`
- `0x180001098`
- `0x180001444`
- `0x180001f12`
- `0x18000227c`
- `0x180003140`

## pseudocode

```c
void __fastcall std::string::_Copy(__int64 a1, unsigned __int64 a2, rsize_t a3)
{
  rsize_t v3; // r14
  unsigned __int64 v4; // rdi
  __int64 v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  size_t v9; // rcx
  void *v10; // r15
  void **v11; // rsi
  void *v12; // r8
  size_t v13; // rcx
  _QWORD *v14; // rbp
  _QWORD *v15; // rdx
  _QWORD v16[5]; // [rsp+0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v18[72]; // [rsp+40h] [rbp-48h] BYREF

  v16[4] = -2;
  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 32);
    v8 = v7 >> 1;
    if ( v6 / 3 < v7 >> 1 && v7 <= -2LL - v8 )
      v4 = v8 + v7;
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 != -1 && !(0xFFFFFFFFFFFFFFFFuLL / v9) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
      throw (std::bad_alloc *)pExceptionObject;
    }
    v10 = operator new(v9);
  }
  catch ( ... )
  {
    v13 = a2 + 1;
    if ( a2 != -1 && !(0xFFFFFFFFFFFFFFFFuLL / v13) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)v18, 0);
      try
      {
        throw (std::bad_alloc *)v18;
      }
      catch ( ... )
      {
        v15 = v16;
        v14 = v15;
        LOBYTE(v15) = 1;
        std::string::_Tidy(v14[18], v15, 0);
        throw;
      }
    }
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v10 = operator new(v13);
  }
  v11 = (void **)(v5 + 8);
  if ( v3 )
  {
    if ( *(_QWORD *)(v5 + 32) < 0x10u )
      v12 = (void *)(v5 + 8);
    else
      v12 = *v11;
    memcpy_s_0(v10, v4 + 1, v12, v3);
  }
  if ( *(_QWORD *)(v5 + 32) >= 0x10u )
    operator delete(*v11);
  *(_QWORD *)(v5 + 32) = 15;
  *(_BYTE *)v11 = 0;
  *v11 = v10;
  *(_QWORD *)(v5 + 32) = v4;
  if ( v4 >= 0x10 )
    v11 = (void **)v10;
  *(_QWORD *)(v5 + 24) = v3;
  *((_BYTE *)v11 + v3) = 0;
}

```

## disassembly

```asm
0x180001444  mov     rax, rsp
0x180001447  mov     [rax+18h], r8
0x18000144b  mov     [rax+10h], rdx
0x18000144f  mov     [rax+8], rcx
0x180001453  push    rbx
0x180001454  push    rsi
0x180001455  push    rdi
0x180001456  push    r14
0x180001458  push    r15
0x18000145a  sub     rsp, 60h
0x18000145e  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x180001466  mov     r14, r8
0x180001469  mov     rdi, rdx
0x18000146c  mov     rbx, rcx
0x18000146f  or      rdx, 0Fh
0x180001473  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000147a  cmp     rdx, r9
0x18000147d  ja      short loc_1800014AD
0x18000147f  mov     rdi, rdx
0x180001482  mov     r8, [rcx+20h]
0x180001486  mov     rcx, r8
0x180001489  shr     rcx, 1
0x18000148c  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001496  mul     rdx
0x180001499  shr     rdx, 1
0x18000149c  cmp     rdx, rcx
0x18000149f  jnb     short loc_1800014AD
0x1800014a1  sub     r9, rcx
0x1800014a4  cmp     r8, r9
0x1800014a7  ja      short loc_1800014AD
0x1800014a9  lea     rdi, [rcx+r8]
0x1800014ad  lea     rcx, [rdi+1]; Size
0x1800014b1  test    rcx, rcx
0x1800014b4  jnz     short loc_1800014C0
0x1800014b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800014bb  mov     r15, rax
0x1800014be  jmp     short loc_1800014F5
0x1800014c0  xor     edx, edx
0x1800014c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800014c6  div     rcx
0x1800014c9  cmp     rax, 1
0x1800014cd  jb      loc_18000155A
0x1800014d3  jmp     short loc_1800014B6
0x1800014d5  mov     rbx, [rsp+88h+arg_0]
0x1800014dd  mov     r14, [rsp+88h+arg_10]
0x1800014e5  mov     rdi, [rsp+88h+arg_8]
0x1800014ed  mov     r15, [rsp+88h+arg_18]
0x1800014f5  lea     rsi, [rbx+8]
0x1800014f9  test    r14, r14
0x1800014fc  jz      short loc_18000151C
0x1800014fe  cmp     qword ptr [rbx+20h], 10h
0x180001503  jb      short loc_18000150A
0x180001505  mov     r8, [rsi]
0x180001508  jmp     short loc_18000150D
0x18000150a  mov     r8, rsi; Source
0x18000150d  lea     rdx, [rdi+1]; DestinationSize
0x180001511  mov     r9, r14; SourceSize
0x180001514  mov     rcx, r15; Destination
0x180001517  call    memcpy_s_0
0x18000151c  cmp     qword ptr [rbx+20h], 10h
0x180001521  jb      short loc_18000152B
0x180001523  mov     rcx, [rsi]; Block
0x180001526  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000152b  mov     qword ptr [rbx+20h], 0Fh
0x180001533  mov     byte ptr [rsi], 0
0x180001536  mov     [rsi], r15
0x180001539  mov     [rbx+20h], rdi
0x18000153d  cmp     rdi, 10h
0x180001541  cmovnb  rsi, r15
0x180001545  mov     [rbx+18h], r14
0x180001549  mov     byte ptr [rsi+r14], 0
0x18000154e  add     rsp, 60h
0x180001552  pop     r15
0x180001554  pop     r14
0x180001556  pop     rdi
0x180001557  pop     rsi
0x180001558  pop     rbx
0x180001559  retn
0x18000155a  xor     edx, edx; char *
0x18000155c  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180001561  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180001566  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000156d  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180001572  call    _CxxThrowException_0
```
