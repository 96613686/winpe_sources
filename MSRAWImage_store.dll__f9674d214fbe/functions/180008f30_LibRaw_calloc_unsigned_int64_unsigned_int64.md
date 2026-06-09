# LibRaw::calloc(unsigned __int64,unsigned __int64)

- ea: `0x180008f30`
- end: `0x180008fec`
- name: `?calloc@LibRaw@@IEAAPEAX_K0@Z`
- size: `188`
- prototype: `void *(LibRaw *__hidden this, unsigned __int64, unsigned __int64)`
- caller_count: `52`
- callee_count: `3`
- tags: ``

## callers

- `0x180007b70`
- `0x180008330`
- `0x1800095a0`
- `0x180009d90`
- `0x18000adf0`
- `0x18000d370`
- `0x18000ed50`
- `0x18000f140`
- `0x180011370`
- `0x180011720`
- `0x180014310`
- `0x180024c40`
- `0x180027e90`
- `0x180029920`
- `0x180029b50`
- `0x180029f90`
- `0x18002cf40`
- `0x18002d8e0`
- `0x180037a70`
- `0x180038ab0`
- `0x18003fa30`
- `0x1800434c0`
- `0x180048320`
- `0x180048af0`
- `0x18004c320`
- `0x18004de00`
- `0x18004e380`
- `0x18004e570`
- `0x18004e6c0`
- `0x18004f750`
- `0x1800504e0`
- `0x180050630`
- `0x180050bd0`
- `0x180050ee0`
- `0x180052970`
- `0x180052e20`
- `0x180053070`
- `0x180053630`
- `0x180053860`
- `0x180053cc0`
- `0x18005e500`
- `0x18005f230`
- `0x180060640`
- `0x180061a90`
- `0x180065900`
- `0x18006c0e0`
- `0x180082010`
- `0x180084960`
- `0x180088f80`
- `0x18008e8c0`

## callees

- `0x180003e4c`
- `0x180008f30`
- `0x180094f5d`

## pseudocode

```c
void *__fastcall LibRaw::calloc(LibRaw *this, __int64 a2, size_t a3)
{
  unsigned __int64 v3; // r9
  void *result; // rax
  __int64 v6; // r8
  int v7; // edx
  __int64 v8; // rcx
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v3 = 1;
  if ( a3 )
    v3 = a3;
  result = calloc_0(a2 + (a3 + *((unsigned int *)this + 191758) - 1LL) / v3, a3);
  if ( !result )
  {
    pExceptionObject = 1;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  v6 = *((_QWORD *)this + 95878);
  v7 = 0;
  v8 = 0;
  while ( *(_QWORD *)(v6 + 8 * v8) )
  {
    ++v7;
    if ( ++v8 >= 511 )
    {
      if ( !*(_QWORD *)(v6 + 4088) )
        *(_QWORD *)(v6 + 4088) = result;
      pExceptionObject = 11;
      throw (LibRaw_exceptions *)&pExceptionObject;
    }
  }
  *(_QWORD *)(v6 + 8LL * v7) = result;
  return result;
}

```

## disassembly

```asm
0x180008f30  push    rbx
0x180008f32  sub     rsp, 20h
0x180008f36  mov     eax, [rcx+0BB438h]
0x180008f3c  mov     r10, rdx
0x180008f3f  dec     rax
0x180008f42  mov     r9d, 1
0x180008f48  add     rax, r8
0x180008f4b  mov     rbx, rcx
0x180008f4e  test    r8, r8
0x180008f51  cmovnz  r9, r8
0x180008f55  xor     edx, edx
0x180008f57  div     r9
0x180008f5a  mov     rdx, r8; Size
0x180008f5d  lea     rcx, [r10+rax]; Count
0x180008f61  call    calloc_0
0x180008f66  mov     r9, rax
0x180008f69  test    rax, rax
0x180008f6c  jz      short loc_180008FA7
0x180008f6e  mov     r8, [rbx+0BB430h]
0x180008f75  xor     edx, edx
0x180008f77  mov     ecx, edx
0x180008f79  nop     dword ptr [rax+00000000h]
0x180008f80  cmp     qword ptr [r8+rcx*8], 0
0x180008f85  jz      short loc_180008F97
0x180008f87  inc     edx
0x180008f89  inc     rcx
0x180008f8c  cmp     rcx, 1FFh
0x180008f93  jge     short loc_180008FC1
0x180008f95  jmp     short loc_180008F80
0x180008f97  movsxd  rax, edx
0x180008f9a  mov     [r8+rax*8], r9
0x180008f9e  mov     rax, r9
0x180008fa1  add     rsp, 20h
0x180008fa5  pop     rbx
0x180008fa6  retn
0x180008fa7  lea     rdx, _TI1?AW4LibRaw_exceptions@@; pThrowInfo
0x180008fae  mov     [rsp+28h+pExceptionObject], 1
0x180008fb6  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180008fbb  call    _CxxThrowException
0x180008fc1  cmp     qword ptr [r8+0FF8h], 0
0x180008fc9  jnz     short loc_180008FD2
0x180008fcb  mov     [r8+0FF8h], r9
0x180008fd2  lea     rdx, _TI1?AW4LibRaw_exceptions@@; pThrowInfo
0x180008fd9  mov     [rsp+28h+pExceptionObject], 0Bh
0x180008fe1  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180008fe6  call    _CxxThrowException
```
