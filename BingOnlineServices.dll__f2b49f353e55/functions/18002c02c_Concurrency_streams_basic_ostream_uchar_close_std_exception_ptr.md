# Concurrency::streams::basic_ostream<uchar>::close(std::exception_ptr)

- ea: `0x18002c02c`
- end: `0x18002c17b`
- name: `?close@?$basic_ostream@E@streams@Concurrency@@QEBA?AV?$task@X@pplx@@Vexception_ptr@std@@@Z`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18002a810`

## callees

- `0x18001235c`
- `0x180012430`
- `0x180012cc0`
- `0x1800148ac`
- `0x18002c02c`
- `0x18002e244`
- `0x1800305f8`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002c15a`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002c15a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002c090`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002c090`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Concurrency::streams::basic_ostream<unsigned char>::close(__int64 a1, _QWORD *a2, void *a3)
{
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _BYTE *, __int64, __int128 *); // rbx
  _QWORD *v8; // rcx
  char v9; // bl
  __int64 v10; // rax
  char v11; // bl
  __int128 v13; // [rsp+40h] [rbp-51h] BYREF
  _BYTE v14[16]; // [rsp+50h] [rbp-41h] BYREF
  _BYTE v15[16]; // [rsp+60h] [rbp-31h] BYREF
  _BYTE v16[8]; // [rsp+70h] [rbp-21h] BYREF
  std::_Ref_count_base *v17; // [rsp+78h] [rbp-19h]
  _BYTE v18[88]; // [rsp+80h] [rbp-11h] BYREF

  if ( *(_QWORD *)a1 && *(_QWORD *)(*(_QWORD *)a1 + 8LL) )
  {
    v5 = Concurrency::streams::basic_ostream<unsigned char>::helper(a1, v16);
    v6 = *(_QWORD *)v5;
    v7 = *(__int64 (__fastcall **)(__int64, _BYTE *, __int64, __int128 *))(**(_QWORD **)v5 + 80LL);
    v13 = 0;
    __ExceptionPtrCopy(&v13, a3);
    v8 = (_QWORD *)v7(v6, v15, 2, &v13);
    v9 = 3;
  }
  else
  {
    v10 = pplx::task_options::task_options((pplx::task_options *)v18);
    v8 = (_QWORD *)pplx::task_from_result(v14, v10);
    v9 = 12;
  }
  *a2 = 0;
  a2[1] = 0;
  *a2 = *v8;
  a2[1] = v8[1];
  *v8 = 0;
  v8[1] = 0;
  v11 = v9 | 0x10;
  if ( (v11 & 8) != 0 )
  {
    v11 &= ~8u;
    pplx::task<long>::~task<long>(v14);
  }
  if ( (v11 & 4) != 0 )
  {
    v11 &= ~4u;
    pplx::task_options::~task_options((pplx::task_options *)v18);
  }
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    pplx::task<long>::~task<long>(v15);
  }
  if ( (v11 & 1) != 0 && v17 )
    std::_Ref_count_base::_Decref(v17);
  __ExceptionPtrDestroy(a3);
  return a2;
}

```

## disassembly

```asm
0x18002c02c  mov     rax, rsp
0x18002c02f  mov     [rax+8], rbx
0x18002c033  mov     [rax+20h], rsi
0x18002c037  mov     [rax+18h], r8
0x18002c03b  push    rbp
0x18002c03c  push    rdi
0x18002c03d  push    r14
0x18002c03f  lea     rbp, [rax-5Fh]
0x18002c043  sub     rsp, 0D0h
0x18002c04a  mov     r14, r8
0x18002c04d  mov     rsi, rdx
0x18002c050  mov     [rbp+57h+var_B0], 0
0x18002c057  mov     rax, [rcx]
0x18002c05a  test    rax, rax
0x18002c05d  jz      short loc_18002C0B9
0x18002c05f  cmp     qword ptr [rax+8], 0
0x18002c064  jz      short loc_18002C0B9
0x18002c066  lea     rdx, [rbp+57h+var_78]
0x18002c06a  call    ?helper@?$basic_ostream@E@streams@Concurrency@@AEBA?AV?$shared_ptr@V?$basic_ostream_helper@E@details@streams@Concurrency@@@std@@XZ; Concurrency::streams::basic_ostream<uchar>::helper(void)
0x18002c06f  nop
0x18002c070  mov     [rbp+57h+var_B0], 1
0x18002c077  mov     rdi, [rax]
0x18002c07a  mov     rax, [rdi]
0x18002c07d  mov     rbx, [rax+50h]
0x18002c081  xorps   xmm0, xmm0
0x18002c084  movdqu  [rbp+57h+var_A8], xmm0
0x18002c089  mov     rdx, r14
0x18002c08c  lea     rcx, [rbp+57h+var_A8]
0x18002c090  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002c096  lea     r9, [rbp+57h+var_A8]
0x18002c09a  mov     r8d, 2
0x18002c0a0  lea     rdx, [rbp+57h+var_88]
0x18002c0a4  mov     rcx, rdi
0x18002c0a7  mov     rax, rbx
0x18002c0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0af  mov     rcx, rax
0x18002c0b2  mov     ebx, 3
0x18002c0b7  jmp     short loc_18002C0DE
0x18002c0b9  lea     rcx, [rbp+57h+var_68]; this
0x18002c0bd  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18002c0c2  nop
0x18002c0c3  mov     [rbp+57h+var_B0], 4
0x18002c0ca  mov     rdx, rax
0x18002c0cd  lea     rcx, [rbp+57h+var_98]
0x18002c0d1  call    ?task_from_result@pplx@@YA?AV?$task@X@1@AEBVtask_options@1@@Z; pplx::task_from_result(pplx::task_options const &)
0x18002c0d6  mov     rcx, rax
0x18002c0d9  mov     ebx, 0Ch
0x18002c0de  mov     qword ptr [rsi], 0
0x18002c0e5  mov     qword ptr [rsi+8], 0
0x18002c0ed  mov     rax, [rcx]
0x18002c0f0  mov     [rsi], rax
0x18002c0f3  mov     rax, [rcx+8]
0x18002c0f7  mov     [rsi+8], rax
0x18002c0fb  mov     qword ptr [rcx], 0
0x18002c102  mov     qword ptr [rcx+8], 0
0x18002c10a  or      ebx, 10h
0x18002c10d  test    bl, 8
0x18002c110  jz      short loc_18002C11F
0x18002c112  and     ebx, 0FFFFFFF7h
0x18002c115  lea     rcx, [rbp+57h+var_98]; void *
0x18002c119  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002c11e  nop
0x18002c11f  test    bl, 4
0x18002c122  jz      short loc_18002C131
0x18002c124  and     ebx, 0FFFFFFFBh
0x18002c127  lea     rcx, [rbp+57h+var_68]; this
0x18002c12b  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x18002c130  nop
0x18002c131  test    bl, 2
0x18002c134  jz      short loc_18002C143
0x18002c136  and     ebx, 0FFFFFFFDh
0x18002c139  lea     rcx, [rbp+57h+var_88]; void *
0x18002c13d  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002c142  nop
0x18002c143  test    bl, 1
0x18002c146  jz      short loc_18002C157
0x18002c148  mov     rcx, [rbp+57h+var_70]; this
0x18002c14c  test    rcx, rcx
0x18002c14f  jz      short loc_18002C157
0x18002c151  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c156  nop
0x18002c157  mov     rcx, r14
0x18002c15a  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002c160  mov     rax, rsi
0x18002c163  lea     r11, [rsp+0E0h+var_10]
0x18002c16b  mov     rbx, [r11+20h]
0x18002c16f  mov     rsi, [r11+38h]
0x18002c173  mov     rsp, r11
0x18002c176  pop     r14
0x18002c178  pop     rdi
0x18002c179  pop     rbp
0x18002c17a  retn
```
