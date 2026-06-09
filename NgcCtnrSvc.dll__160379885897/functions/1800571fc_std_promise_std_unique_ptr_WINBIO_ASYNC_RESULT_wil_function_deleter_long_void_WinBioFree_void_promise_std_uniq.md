# std::promise<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::~promise<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>(void)

- ea: `0x1800571fc`
- end: `0x1800572ff`
- name: `??1?$promise@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@QEAA@XZ`
- size: `259`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `7`
- tags: ``

## callers

- `0x1800290a0`
- `0x1800560f8`
- `0x1800561f8`
- `0x1800562fc`
- `0x1800563e8`
- `0x1800564cc`
- `0x180056604`
- `0x180057ef0`
- `0x180058bbc`
- `0x18007f27d`
- `0x18007f2d1`
- `0x18007f367`

## callees

- `0x18002d402`
- `0x18002eb78`
- `0x18002eca8`
- `0x180057148`
- `0x1800571fc`
- `0x180058afc`
- `0x180059184`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x1800572aa`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x1800572aa`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005728f`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005728f`

## pseudocode

```c
__int64 __fastcall std::promise<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::~promise<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>(
        _QWORD *a1)
{
  __int64 v2; // rcx
  __int128 v4; // [rsp+20h] [rbp-60h] BYREF
  void **v5; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v6[16]; // [rsp+38h] [rbp-48h] BYREF
  __int128 v7; // [rsp+48h] [rbp-38h]
  void **v8; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v9[16]; // [rsp+60h] [rbp-20h] BYREF
  __int128 v10; // [rsp+70h] [rbp-10h]

  if ( (unsigned __int8)std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::valid()
    && (!*(_QWORD *)v2 || !*(_DWORD *)(*(_QWORD *)v2 + 196LL)) )
  {
    std::logic_error::logic_error((std::logic_error *)&v5, word_1800912AA);
    v5 = &std::future_error::`vftable';
    LODWORD(v7) = 1;
    DWORD1(v7) = DWORD1(v4);
    *((_QWORD *)&v7 + 1) = &`std::_Immortalize_memcpy_image<std::_Future_error_category2>'::`2'::_Static;
    std::exception::exception((std::exception *)&v8, (const struct std::exception *)&v5);
    v8 = &std::future_error::`vftable';
    v10 = v7;
    v4 = 0;
    __ExceptionPtrCreate(&v4);
    __ExceptionPtrCopyException(&v4, &v8, &TI3_AVfuture_error_std__);
    v8 = &std::exception::`vftable';
    o___std_exception_destroy_0(v9);
    std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::_Set_exception(
      a1,
      &v4);
    v5 = &std::exception::`vftable';
    o___std_exception_destroy_0(v6);
  }
  return std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::~_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>(a1);
}

```

## disassembly

```asm
0x1800571fc  mov     [rsp-8+arg_8], rbx
0x180057201  mov     [rsp-8+arg_10], rdi
0x180057206  push    rbp
0x180057207  mov     rbp, rsp
0x18005720a  sub     rsp, 80h
0x180057211  mov     rbx, rcx
0x180057214  call    ?valid@?$_State_manager@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@QEBA_NXZ; std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::valid(void)
0x180057219  test    al, al
0x18005721b  jz      loc_1800572E3
0x180057221  mov     rax, [rcx]
0x180057224  test    rax, rax
0x180057227  jz      short loc_180057236
0x180057229  cmp     dword ptr [rax+0C4h], 0
0x180057230  jnz     loc_1800572E3
0x180057236  lea     rdx, word_1800912AA; char *
0x18005723d  lea     rcx, [rbp+var_50]; this
0x180057241  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x180057246  lea     rdi, ??_7future_error@std@@6B@; const std::future_error::`vftable'
0x18005724d  mov     [rbp+var_50], rdi
0x180057251  mov     dword ptr [rbp+var_38], 1
0x180057258  mov     eax, dword ptr [rbp+var_60+4]
0x18005725b  mov     dword ptr [rbp+var_38+4], eax
0x18005725e  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_Future_error_category2@std@@@std@@YAAEBV_Future_error_category2@1@XZ@4U?$_Constexpr_immortalize_impl@V_Future_error_category2@std@@@1@A; std::_Constexpr_immortalize_impl<std::_Future_error_category2> `std::_Immortalize_memcpy_image<std::_Future_error_category2>(void)'::`2'::_Static
0x180057265  mov     qword ptr [rbp+var_38+8], rax
0x180057269  lea     rdx, [rbp+var_50]; struct std::exception *
0x18005726d  lea     rcx, [rbp+var_28]; this
0x180057271  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180057276  mov     [rbp+var_28], rdi
0x18005727a  movups  xmm0, [rbp+var_38]
0x18005727e  movdqu  [rbp+var_10], xmm0
0x180057283  xorps   xmm1, xmm1
0x180057286  movdqu  [rbp+var_60], xmm1
0x18005728b  lea     rcx, [rbp+var_60]
0x18005728f  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180057296  nop     dword ptr [rax+rax+00h]
0x18005729b  lea     r8, _TI3?AVfuture_error@std@@; throw info for 'class std::future_error'
0x1800572a2  lea     rdx, [rbp+var_28]
0x1800572a6  lea     rcx, [rbp+var_60]
0x1800572aa  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800572b1  nop     dword ptr [rax+rax+00h]
0x1800572b6  lea     rdi, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800572bd  mov     [rbp+var_28], rdi
0x1800572c1  lea     rcx, [rbp+var_20]
0x1800572c5  call    _o___std_exception_destroy_0
0x1800572ca  lea     rdx, [rbp+var_60]
0x1800572ce  mov     rcx, rbx
0x1800572d1  call    ?_Set_exception@?$_State_manager@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@QEAAXVexception_ptr@2@_N@Z; std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::_Set_exception(std::exception_ptr,bool)
0x1800572d6  mov     [rbp+var_50], rdi
0x1800572da  lea     rcx, [rbp+var_48]
0x1800572de  call    _o___std_exception_destroy_0
0x1800572e3  mov     rcx, rbx
0x1800572e6  lea     r11, [rsp+80h+var_s0]
0x1800572ee  mov     rbx, [r11+18h]
0x1800572f2  mov     rdi, [r11+20h]
0x1800572f6  mov     rsp, r11
0x1800572f9  pop     rbp
0x1800572fa  jmp     ??1?$_State_manager@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@QEAA@XZ; std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::~_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>(void)
```
