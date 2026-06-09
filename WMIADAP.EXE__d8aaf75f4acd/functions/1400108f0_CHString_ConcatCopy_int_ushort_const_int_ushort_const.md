# CHString::ConcatCopy(int,ushort const *,int,ushort const *)

- ea: `0x1400108f0`
- end: `0x1400109c7`
- name: `?ConcatCopy@CHString@@IEAAXHPEBGH0@Z`
- size: `215`
- prototype: `void __fastcall(CHString *this, int, const unsigned __int16 *, int, const unsigned __int16 *Src)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x140010230`
- `0x1400102b0`
- `0x140010320`
- `0x1400103b0`
- `0x140010420`
- `0x1400109d0`

## callees

- `0x1400027e1`
- `0x14000298c`
- `0x1400061a0`
- `0x14000787c`
- `0x140010630`
- `0x1400108f0`

## pseudocode

```c
void __fastcall CHString::ConcatCopy(
        CHString *this,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        const unsigned __int16 *Src)
{
  __int64 v5; // rdi
  size_t Size; // [rsp+20h] [rbp-20h] BYREF
  size_t v10; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v11[2]; // [rsp+30h] [rbp-10h] BYREF
  int pExceptionObject; // [rsp+68h] [rbp+28h] BYREF

  v5 = a2;
  if ( a2 < 0 || a4 < 0 )
  {
    pExceptionObject = 87;
    throw (SafeIntException *)&pExceptionObject;
  }
  SafeInt<unsigned __int64>::SafeInt<unsigned __int64>(&v10, (unsigned int)a2);
  SafeInt<unsigned __int64>::SafeInt<unsigned __int64>(v11, (unsigned int)a4);
  SafeInt<unsigned __int64>::SafeInt<unsigned __int64>(&Size, (unsigned int)(v5 + a4));
  if ( Size )
  {
    CHString::AllocBuffer(this, Size);
    SafeInt<unsigned __int64>::operator*<unsigned __int64>(&v10, (__int64)&Size);
    SafeInt<unsigned __int64>::operator*<unsigned __int64>(v11, (__int64)&v10);
    memcpy_0(*(void **)this, a3, Size);
    memcpy_0((void *)(*(_QWORD *)this + 2 * v5), Src, v10);
  }
}

```

## disassembly

```asm
0x1400108f0  mov     [rsp-18h+arg_0], rbx
0x1400108f5  mov     [rsp-18h+arg_10], rsi
0x1400108fa  push    rbp
0x1400108fb  push    rdi
0x1400108fc  push    r14
0x1400108fe  mov     rbp, rsp
0x140010901  sub     rsp, 40h
0x140010905  movsxd  rdi, edx
0x140010908  mov     ebx, r9d
0x14001090b  mov     r14, r8
0x14001090e  mov     rsi, rcx
0x140010911  test    edx, edx
0x140010913  js      loc_1400109AF
0x140010919  test    ebx, ebx
0x14001091b  js      loc_1400109AF
0x140010921  mov     edx, edi
0x140010923  lea     rcx, [rbp+var_18]
0x140010927  call    ??$?0H@?$SafeInt@_K@@QEAA@H@Z; SafeInt<unsigned __int64>::SafeInt<unsigned __int64>(int)
0x14001092c  mov     edx, ebx
0x14001092e  lea     rcx, [rbp+var_10]
0x140010932  call    ??$?0H@?$SafeInt@_K@@QEAA@H@Z; SafeInt<unsigned __int64>::SafeInt<unsigned __int64>(int)
0x140010937  lea     edx, [rdi+rbx]
0x14001093a  lea     rcx, [rbp+Size]
0x14001093e  call    ??$?0H@?$SafeInt@_K@@QEAA@H@Z; SafeInt<unsigned __int64>::SafeInt<unsigned __int64>(int)
0x140010943  mov     rdx, [rbp+Size]; int
0x140010947  test    rdx, rdx
0x14001094a  jz      short loc_14001099C
0x14001094c  mov     rcx, rsi; this
0x14001094f  call    ?AllocBuffer@CHString@@IEAAXH@Z; CHString::AllocBuffer(int)
0x140010954  mov     ebx, 2
0x140010959  lea     rdx, [rbp+Size]
0x14001095d  mov     r8d, ebx
0x140010960  lea     rcx, [rbp+var_18]
0x140010964  call    ??$?D_K@?$SafeInt@_K@@QEAA?AV0@_K@Z; SafeInt<unsigned __int64>::operator*<unsigned __int64>(unsigned __int64)
0x140010969  mov     r8d, ebx
0x14001096c  lea     rdx, [rbp+var_18]
0x140010970  lea     rcx, [rbp+var_10]
0x140010974  call    ??$?D_K@?$SafeInt@_K@@QEAA?AV0@_K@Z; SafeInt<unsigned __int64>::operator*<unsigned __int64>(unsigned __int64)
0x140010979  mov     r8, [rbp+Size]; Size
0x14001097d  mov     rdx, r14; Src
0x140010980  mov     rcx, [rsi]; void *
0x140010983  call    memcpy_0
0x140010988  mov     rax, [rsi]
0x14001098b  mov     r8, [rbp+var_18]; Size
0x14001098f  mov     rdx, [rbp+Src]; Src
0x140010993  lea     rcx, [rax+rdi*2]; void *
0x140010997  call    memcpy_0
0x14001099c  mov     rbx, [rsp+40h+arg_0]
0x1400109a1  mov     rsi, [rsp+40h+arg_10]
0x1400109a6  add     rsp, 40h
0x1400109aa  pop     r14
0x1400109ac  pop     rdi
0x1400109ad  pop     rbp
0x1400109ae  retn
0x1400109af  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x1400109b6  mov     [rbp+pExceptionObject], 57h ; 'W'
0x1400109bd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400109c1  call    _CxxThrowException_0
```
