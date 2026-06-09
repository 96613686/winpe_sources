# std::promise<void>::~promise<void>(void)

- ea: `0x1800383d0`
- end: `0x1800385a0`
- name: `??1?$promise@X@std@@QEAA@XZ`
- size: `464`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180038cc4`
- `0x1800395b4`
- `0x180039a5c`
- `0x18003ae00`
- `0x18003b858`
- `0x1804fbac9`
- `0x1804fbb55`
- `0x1804fbb94`
- `0x1804fbe51`

## callees

- `0x180035b0c`
- `0x1800377b0`
- `0x1800383d0`
- `0x1804f99e0`

## import_xrefs

- `VCRUNTIME140!__std_exception_destroy` at `0x1800384d6`
- `VCRUNTIME140!__std_exception_destroy` at `0x18003852f`
- `VCRUNTIME140!__std_exception_destroy` at `0x1800384d6`
- `VCRUNTIME140!__std_exception_destroy` at `0x18003852f`
- `VCRUNTIME140!__std_exception_copy` at `0x180038467`
- `VCRUNTIME140!__std_exception_copy` at `0x180038494`
- `VCRUNTIME140!__std_exception_copy` at `0x180038467`
- `VCRUNTIME140!__std_exception_copy` at `0x180038494`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180038521`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180038521`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003850b`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003850b`
- `MSVCP140!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x1800384c8`
- `MSVCP140!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x1800384c8`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800384b3`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800384b3`

## pseudocode

```c
__int64 __fastcall std::promise<void>::~promise<void>(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rdi
  __int64 v4; // rcx
  __int64 (__fastcall ***v5)(_QWORD, __int64); // r8
  __int128 v6; // [rsp+28h] [rbp-19h] BYREF
  __int128 v7; // [rsp+38h] [rbp-9h] BYREF
  void **v8; // [rsp+48h] [rbp+7h]
  __int128 v9; // [rsp+50h] [rbp+Fh] BYREF
  __int128 v10; // [rsp+60h] [rbp+1Fh]
  void **v11; // [rsp+70h] [rbp+2Fh] BYREF
  _OWORD v12[2]; // [rsp+78h] [rbp+37h] BYREF

  result = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 && (!*(_BYTE *)(a1 + 8) || !*(_BYTE *)(result + 184)) && !*(_DWORD *)(result + 188) )
  {
    LODWORD(v7) = 1;
    *((_QWORD *)&v7 + 1) = &`std::_Immortalize_memcpy_image<std::_Future_error_category2>'::`2'::_Static;
    v8 = &std::exception::`vftable';
    v9 = 0;
    *(_QWORD *)&v6 = byte_1806ADF48;
    BYTE8(v6) = 1;
    *(_DWORD *)((char *)&v6 + 9) = 0;
    *(_WORD *)((char *)&v6 + 13) = 0;
    HIBYTE(v6) = 0;
    __std_exception_copy(&v6, &v9);
    v8 = &std::future_error::`vftable';
    v10 = v7;
    v11 = &std::exception::`vftable';
    v12[0] = 0;
    __std_exception_copy(&v9, v12);
    v11 = &std::future_error::`vftable';
    v12[1] = v10;
    v6 = 0;
    __ExceptionPtrCreate(&v6);
    __ExceptionPtrCopyException(&v6, &v11, &TI3_AVfuture_error_std__);
    v11 = &std::exception::`vftable';
    __std_exception_destroy(v12);
    v3 = *(_QWORD *)a1;
    if ( !*(_QWORD *)a1 || *(_BYTE *)(a1 + 8) && *(_BYTE *)(v3 + 184) )
      std::_Throw_future_error2(4);
    v7 = 0;
    __ExceptionPtrCopy(&v7, &v6);
    std::_Associated_state<int>::_Set_exception(v3, &v7);
    __ExceptionPtrDestroy(&v6);
    v8 = &std::exception::`vftable';
    result = __std_exception_destroy(&v9);
  }
  v4 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 8), 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      v5 = *(__int64 (__fastcall ****)(_QWORD, __int64))(v4 + 200);
      if ( v5 )
        return (**v5)(*(_QWORD *)(v4 + 200), v4);
      else
        return (**(__int64 (__fastcall ***)(__int64, __int64))v4)(v4, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800383d0  mov     rax, rsp
0x1800383d3  mov     [rax+10h], rbx
0x1800383d7  mov     [rax+18h], rdi
0x1800383db  mov     [rax+20h], r15
0x1800383df  push    rbp
0x1800383e0  lea     rbp, [rax-5Fh]
0x1800383e4  sub     rsp, 90h
0x1800383eb  mov     rbx, rcx
0x1800383ee  mov     rax, [rcx]
0x1800383f1  test    rax, rax
0x1800383f4  jz      loc_180038535
0x1800383fa  cmp     byte ptr [rcx+8], 0
0x1800383fe  jz      short loc_18003840D
0x180038400  cmp     byte ptr [rax+0B8h], 0
0x180038407  jnz     loc_180038535
0x18003840d  cmp     dword ptr [rax+0BCh], 0
0x180038414  jnz     loc_180038535
0x18003841a  mov     dword ptr [rbp+57h+var_60], 1
0x180038421  mov     eax, dword ptr [rbp+57h+var_60+4]
0x180038424  mov     dword ptr [rbp+57h+var_60+4], eax
0x180038427  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_Future_error_category2@std@@@std@@YAAEBV_Future_error_category2@1@XZ@4V21@B; std::_Future_error_category2 const `std::_Immortalize_memcpy_image<std::_Future_error_category2>(void)'::`2'::_Static
0x18003842e  mov     qword ptr [rbp+57h+var_60+8], rax
0x180038432  lea     r15, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180038439  mov     [rbp+57h+var_50], r15
0x18003843d  xorps   xmm0, xmm0
0x180038440  movups  [rbp+57h+var_48], xmm0
0x180038444  lea     rax, byte_1806ADF48
0x18003844b  mov     qword ptr [rbp+57h+var_70], rax
0x18003844f  mov     byte ptr [rbp+57h+var_70+8], 1
0x180038453  xor     eax, eax
0x180038455  mov     dword ptr [rbp+57h+var_70+9], eax
0x180038458  mov     word ptr [rbp+57h+var_70+0Dh], ax
0x18003845c  mov     byte ptr [rbp+57h+var_70+0Fh], al
0x18003845f  lea     rdx, [rbp+57h+var_48]
0x180038463  lea     rcx, [rbp+57h+var_70]
0x180038467  call    cs:__imp___std_exception_copy
0x18003846d  lea     rdi, ??_7future_error@std@@6B@; const std::future_error::`vftable'
0x180038474  mov     [rbp+57h+var_50], rdi
0x180038478  movaps  xmm0, [rbp+57h+var_60]
0x18003847c  movdqu  [rbp+57h+var_38], xmm0
0x180038481  mov     [rbp+57h+var_28], r15
0x180038485  xorps   xmm0, xmm0
0x180038488  movups  [rbp+57h+var_20], xmm0
0x18003848c  lea     rdx, [rbp+57h+var_20]
0x180038490  lea     rcx, [rbp+57h+var_48]
0x180038494  call    cs:__imp___std_exception_copy
0x18003849a  mov     [rbp+57h+var_28], rdi
0x18003849e  movups  xmm0, [rbp+57h+var_38]
0x1800384a2  movdqu  [rbp+57h+var_10], xmm0
0x1800384a7  xorps   xmm1, xmm1
0x1800384aa  movdqu  [rbp+57h+var_70], xmm1
0x1800384af  lea     rcx, [rbp+57h+var_70]
0x1800384b3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800384b9  lea     r8, _TI3?AVfuture_error@std@@; throw info for 'class std::future_error'
0x1800384c0  lea     rdx, [rbp+57h+var_28]
0x1800384c4  lea     rcx, [rbp+57h+var_70]
0x1800384c8  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800384ce  mov     [rbp+57h+var_28], r15
0x1800384d2  lea     rcx, [rbp+57h+var_20]
0x1800384d6  call    cs:__imp___std_exception_destroy
0x1800384dc  mov     rdi, [rbx]
0x1800384df  test    rdi, rdi
0x1800384e2  jz      loc_180038595
0x1800384e8  cmp     byte ptr [rbx+8], 0
0x1800384ec  jz      short loc_1800384FB
0x1800384ee  cmp     byte ptr [rdi+0B8h], 0
0x1800384f5  jnz     loc_180038595
0x1800384fb  xorps   xmm0, xmm0
0x1800384fe  movdqu  [rbp+57h+var_60], xmm0
0x180038503  lea     rdx, [rbp+57h+var_70]
0x180038507  lea     rcx, [rbp+57h+var_60]
0x18003850b  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180038511  lea     rdx, [rbp+57h+var_60]
0x180038515  mov     rcx, rdi
0x180038518  call    ?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z; std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)
0x18003851d  lea     rcx, [rbp+57h+var_70]
0x180038521  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180038527  mov     [rbp+57h+var_50], r15
0x18003852b  lea     rcx, [rbp+57h+var_48]
0x18003852f  call    cs:__imp___std_exception_destroy
0x180038535  mov     rcx, [rbx]
0x180038538  test    rcx, rcx
0x18003853b  jz      short loc_18003857C
0x18003853d  or      eax, 0FFFFFFFFh
0x180038540  lock xadd [rcx+8], eax
0x180038545  cmp     eax, 1
0x180038548  jnz     short loc_18003857C
0x18003854a  mov     r8, [rcx+0C8h]
0x180038551  test    r8, r8
0x180038554  jz      short loc_18003856A
0x180038556  mov     rax, [r8]
0x180038559  mov     rdx, rcx
0x18003855c  mov     rcx, r8
0x18003855f  mov     rax, [rax]
0x180038562  call    cs:__guard_dispatch_icall_fptr
0x180038568  jmp     short loc_18003857C
0x18003856a  mov     rax, [rcx]
0x18003856d  mov     edx, 1
0x180038572  mov     rax, [rax]
0x180038575  call    cs:__guard_dispatch_icall_fptr
0x18003857b  nop
0x18003857c  lea     r11, [rsp+90h+var_s0]
0x180038584  mov     rbx, [r11+18h]
0x180038588  mov     rdi, [r11+20h]
0x18003858c  mov     r15, [r11+28h]
0x180038590  mov     rsp, r11
0x180038593  pop     rbp
0x180038594  retn
0x180038595  mov     ecx, 4
0x18003859a  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
