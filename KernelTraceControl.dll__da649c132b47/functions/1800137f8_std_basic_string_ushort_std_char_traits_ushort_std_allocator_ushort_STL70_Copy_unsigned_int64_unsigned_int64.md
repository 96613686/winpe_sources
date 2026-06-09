# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800137f8`
- end: `0x180013933`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `315`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180011fb4`
- `0x180013598`
- `0x180013934`

## callees

- `0x18000252c`
- `0x1800137f8`
- `0x18002687c`
- `0x1800268f4`
- `0x180026f66`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800138f5`
- `msvcrt!memcpy_s` at `0x1800138f5`

## pseudocode

```c
_WORD *__fastcall std::wstring::_Copy(_QWORD *a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  _QWORD *v4; // rdi
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // r15
  const void *v10; // r8
  _WORD *result; // rax
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rdx
  _QWORD v14[5]; // [rsp+0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v16[72]; // [rsp+40h] [rbp-48h] BYREF
  void *v20; // [rsp+A8h] [rbp+20h]

  v14[4] = -2;
  v3 = a3;
  v4 = a1;
  v5 = a2 | 7;
  if ( (a2 | 7) <= 0x7FFFFFFFFFFFFFFELL )
  {
    v6 = a1[4];
    v7 = v6 >> 1;
    if ( v5 / 3 < v6 >> 1 && v6 <= 0x7FFFFFFFFFFFFFFELL - v7 )
      v5 = v7 + v6;
  }
  else
  {
    v5 = a2;
  }
  try
  {
    v8 = v5 + 1;
    if ( v5 == -1 )
    {
      v8 = 0;
    }
    else if ( 0xFFFFFFFFFFFFFFFFuLL / v8 < 2 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
      throw (std::bad_alloc *)pExceptionObject;
    }
    v9 = operator new(2 * v8);
  }
  catch ( ... )
  {
    try
    {
      v12 = a2 + 1;
      if ( a2 != -1 && 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)v16, 0);
        throw (std::bad_alloc *)v16;
      }
      v20 = operator new(2 * v12);
    }
    catch ( ... )
    {
      v13 = v14;
      LOBYTE(v13) = 1;
      std::wstring::_Tidy(a1, v13, 0);
      throw;
    }
    v4 = a1;
    v3 = a3;
    v5 = a2;
    v9 = v20;
  }
  if ( v3 )
  {
    if ( v4[4] < 8u )
      v10 = v4 + 1;
    else
      v10 = (const void *)v4[1];
    memcpy_s(v9, 2 * v5 + 2, v10, 2 * v3);
  }
  if ( v4[4] >= 8u )
    operator delete((void *)v4[1]);
  result = v4 + 1;
  v4[1] = v9;
  v4[4] = v5;
  v4[3] = v3;
  if ( v5 >= 8 )
    result = v9;
  result[v3] = 0;
  return result;
}

```

## disassembly

```asm
0x1800137f8  mov     rax, rsp
0x1800137fb  mov     [rax+18h], r8
0x1800137ff  mov     [rax+10h], rdx
0x180013803  mov     [rax+8], rcx
0x180013807  push    rbx
0x180013808  push    rsi
0x180013809  push    rdi
0x18001380a  push    r14
0x18001380c  push    r15
0x18001380e  sub     rsp, 60h
0x180013812  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x18001381a  mov     r14, r8
0x18001381d  mov     rdi, rcx
0x180013820  mov     rbx, rdx
0x180013823  or      rbx, 7
0x180013827  mov     r9, 7FFFFFFFFFFFFFFEh
0x180013831  cmp     rbx, r9
0x180013834  jbe     short loc_18001383B
0x180013836  mov     rbx, rdx
0x180013839  jmp     short loc_180013866
0x18001383b  mov     r8, [rcx+20h]
0x18001383f  mov     rcx, r8
0x180013842  shr     rcx, 1
0x180013845  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001384f  mul     rbx
0x180013852  shr     rdx, 1
0x180013855  cmp     rdx, rcx
0x180013858  jnb     short loc_180013866
0x18001385a  sub     r9, rcx
0x18001385d  cmp     r8, r9
0x180013860  ja      short loc_180013866
0x180013862  lea     rbx, [rcx+r8]
0x180013866  lea     rcx, [rbx+1]
0x18001386a  xor     esi, esi
0x18001386c  test    rcx, rcx
0x18001386f  jnz     short loc_180013875
0x180013871  mov     ecx, esi
0x180013873  jmp     short loc_1800138A1
0x180013875  xor     edx, edx
0x180013877  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001387b  div     rcx
0x18001387e  cmp     rax, 2
0x180013882  jnb     short loc_1800138A1
0x180013884  xor     edx, edx; char *
0x180013886  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18001388b  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180013890  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180013897  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001389c  call    _CxxThrowException_0
0x1800138a1  add     rcx, rcx; Size
0x1800138a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800138a9  mov     r15, rax
0x1800138ac  jmp     short loc_1800138D0
0x1800138ae  xor     esi, esi
0x1800138b0  mov     rdi, [rsp+88h+arg_0]
0x1800138b8  mov     r14, [rsp+88h+arg_10]
0x1800138c0  mov     rbx, [rsp+88h+arg_8]
0x1800138c8  mov     r15, [rsp+88h+arg_18]
0x1800138d0  test    r14, r14
0x1800138d3  jz      short loc_1800138FB
0x1800138d5  cmp     qword ptr [rdi+20h], 8
0x1800138da  jb      short loc_1800138E2
0x1800138dc  mov     r8, [rdi+8]
0x1800138e0  jmp     short loc_1800138E6
0x1800138e2  lea     r8, [rdi+8]; Source
0x1800138e6  lea     r9, [r14+r14]; SourceSize
0x1800138ea  lea     rdx, ds:2[rbx*2]; DestinationSize
0x1800138f2  mov     rcx, r15; Destination
0x1800138f5  call    cs:__imp_memcpy_s
0x1800138fb  cmp     qword ptr [rdi+20h], 8
0x180013900  jb      short loc_18001390B
0x180013902  mov     rcx, [rdi+8]; Block
0x180013906  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001390b  lea     rax, [rdi+8]
0x18001390f  mov     [rax], r15
0x180013912  mov     [rdi+20h], rbx
0x180013916  mov     [rdi+18h], r14
0x18001391a  cmp     rbx, 8
0x18001391e  cmovnb  rax, r15
0x180013922  mov     [rax+r14*2], si
0x180013927  add     rsp, 60h
0x18001392b  pop     r15
0x18001392d  pop     r14
0x18001392f  pop     rdi
0x180013930  pop     rsi
0x180013931  pop     rbx
0x180013932  retn
```
