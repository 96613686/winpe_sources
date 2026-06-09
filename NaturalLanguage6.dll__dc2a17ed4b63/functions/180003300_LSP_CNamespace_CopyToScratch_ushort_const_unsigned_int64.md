# LSP::CNamespace::CopyToScratch(ushort const *,unsigned __int64)

- ea: `0x180003300`
- end: `0x18000340e`
- name: `?CopyToScratch@CNamespace@LSP@@IEBAPEAGPEBG_K@Z`
- size: `270`
- prototype: `unsigned __int16 *__fastcall(LSP::CNamespace *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002a90`
- `0x18005b330`
- `0x18005b490`

## callees

- `0x180003300`
- `0x180035640`
- `0x18003ed6c`
- `0x18005b8e0`

## import_xrefs

- `msvcrt!realloc` at `0x1800033a6`
- `msvcrt!realloc` at `0x1800033a6`

## pseudocode

```c
unsigned __int16 *__fastcall LSP::CNamespace::CopyToScratch(
        LSP::CNamespace *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // r9
  void **v4; // rdi
  unsigned __int64 v5; // rsi
  _WORD *v8; // r8
  _WORD *v9; // rcx
  __int64 v10; // rdx
  void *v12; // rbx
  _BYTE pExceptionObject[104]; // [rsp+20h] [rbp-68h] BYREF
  const void *retaddr; // [rsp+88h] [rbp+0h]

  v3 = *((_QWORD *)this + 11);
  v4 = (void **)((char *)this + 80);
  v5 = a3;
  if ( a3 >= v3 )
  {
    v12 = realloc(*v4, 2 * a3 + 200);
    ThrowIfFailed(v12);
    v3 = v5 + 1;
    *v4 = v12;
    *((_QWORD *)this + 11) = v5 + 1;
  }
  v8 = *v4;
  if ( !v3 )
  {
    v10 = 2147942487LL;
LABEL_16:
    CNLException::CNLException((CNLException *)pExceptionObject, v10, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  if ( v3 > 0x7FFFFFFF )
  {
    v10 = 2147942487LL;
    *v8 = 0;
    goto LABEL_12;
  }
  if ( v5 > 0x7FFFFFFE )
  {
    v10 = 2147942487LL;
    *v8 = 0;
    goto LABEL_16;
  }
  do
  {
    if ( !v5 )
      break;
    if ( !*a2 )
      break;
    *v8++ = *a2++;
    --v5;
    --v3;
  }
  while ( v3 );
  v9 = v8 - 1;
  if ( v3 )
    v9 = v8;
  v10 = v3 == 0 ? 0x8007007A : 0;
  *v9 = 0;
LABEL_12:
  if ( (int)v10 < 0 )
    goto LABEL_16;
  return (unsigned __int16 *)*v4;
}

```

## disassembly

```asm
0x180003300  push    rbx
0x180003302  push    rbp
0x180003303  push    rsi
0x180003304  push    rdi
0x180003305  push    r14
0x180003307  sub     rsp, 60h
0x18000330b  mov     r9, [rcx+58h]
0x18000330f  lea     rdi, [rcx+50h]
0x180003313  mov     rsi, r8
0x180003316  mov     r14, rdx
0x180003319  mov     rbp, rcx
0x18000331c  cmp     r8, r9
0x18000331f  jnb     short loc_18000339B
0x180003321  mov     r8, [rdi]
0x180003324  xor     r10d, r10d
0x180003327  test    r9, r9
0x18000332a  jz      loc_1800033FB
0x180003330  cmp     r9, 7FFFFFFFh
0x180003337  ja      loc_1800033C7
0x18000333d  cmp     rsi, 7FFFFFFEh
0x180003344  ja      loc_1800033CE
0x18000334a  test    rsi, rsi
0x18000334d  jz      short loc_18000336D
0x18000334f  movzx   eax, word ptr [r14]
0x180003353  test    ax, ax
0x180003356  jz      short loc_18000336D
0x180003358  mov     [r8], ax
0x18000335c  add     r14, 2
0x180003360  add     r8, 2
0x180003364  dec     rsi
0x180003367  sub     r9, 1
0x18000336b  jnz     short loc_18000334A
0x18000336d  test    r9, r9
0x180003370  lea     rcx, [r8-2]
0x180003374  cmovnz  rcx, r8
0x180003378  neg     r9
0x18000337b  sbb     edx, edx
0x18000337d  not     edx
0x18000337f  and     edx, 8007007Ah
0x180003385  mov     [rcx], r10w
0x180003389  test    edx, edx
0x18000338b  js      short loc_1800033D7
0x18000338d  mov     rax, [rdi]
0x180003390  add     rsp, 60h
0x180003394  pop     r14
0x180003396  pop     rdi
0x180003397  pop     rsi
0x180003398  pop     rbp
0x180003399  pop     rbx
0x18000339a  retn
0x18000339b  mov     rcx, [rdi]; Block
0x18000339e  lea     rdx, ds:0C8h[r8*2]; Size
0x1800033a6  call    cs:__imp_realloc
0x1800033ac  mov     rcx, rax; void *
0x1800033af  mov     rbx, rax
0x1800033b2  call    ?ThrowIfFailed@@YAXPEBX@Z; ThrowIfFailed(void const *)
0x1800033b7  lea     r9, [rsi+1]
0x1800033bb  mov     [rdi], rbx
0x1800033be  mov     [rbp+58h], r9
0x1800033c2  jmp     loc_180003321
0x1800033c7  mov     edx, 80070057h
0x1800033cc  jmp     short loc_180003405
0x1800033ce  mov     edx, 80070057h; int
0x1800033d3  mov     [r8], r10w
0x1800033d7  mov     r8, [rsp+88h]; void *
0x1800033df  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800033e4  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800033e9  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800033f0  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800033f5  call    _CxxThrowException_0
0x1800033fb  mov     edx, 80070057h
0x180003400  test    r9, r9
0x180003403  jz      short loc_1800033D7
0x180003405  mov     [r8], r10w
0x180003409  jmp     loc_180003389
```
