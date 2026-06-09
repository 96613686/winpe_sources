# std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::_Set_exception(std::exception_ptr,bool)

- ea: `0x180058afc`
- end: `0x180058b66`
- name: `?_Set_exception@?$_State_manager@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800571fc`
- `0x18007f57f`

## callees

- `0x180058a30`
- `0x180058afc`
- `0x180058b6c`
- `0x180059184`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180058b5a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180058b33`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180058b33`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::_Set_exception(
        __int64 a1,
        void *a2)
{
  const void *v3; // rdx
  _BYTE **v4; // rcx
  _BYTE *v5; // rbx
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned __int8)std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::valid() )
    std::_Throw_future_error2(4);
  v5 = *v4;
  v6 = 0;
  __ExceptionPtrCopy(&v6, v3);
  std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::_Set_exception(
    v5,
    &v6);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x180058afc  mov     [rsp+arg_0], rbx
0x180058b01  mov     [rsp+arg_8], rdx
0x180058b06  push    rdi
0x180058b07  sub     rsp, 30h
0x180058b0b  mov     rdi, rdx
0x180058b0e  call    ?valid@?$_State_manager@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@QEBA_NXZ; std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::valid(void)
0x180058b13  test    al, al
0x180058b15  jnz     short loc_180058B22
0x180058b17  mov     ecx, 4
0x180058b1c  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180058b22  mov     rbx, [rcx]
0x180058b25  xorps   xmm0, xmm0
0x180058b28  movdqu  [rsp+38h+var_18], xmm0
0x180058b2e  lea     rcx, [rsp+38h+var_18]
0x180058b33  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180058b3a  nop     dword ptr [rax+rax+00h]
0x180058b3f  lea     rdx, [rsp+38h+var_18]
0x180058b44  mov     rcx, rbx
0x180058b47  call    ?_Set_exception@?$_Associated_state@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@QEAAXVexception_ptr@2@_N@Z; std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::_Set_exception(std::exception_ptr,bool)
0x180058b4c  nop
0x180058b4d  mov     rcx, rdi
0x180058b50  mov     rbx, [rsp+38h+arg_0]
0x180058b55  add     rsp, 30h
0x180058b59  pop     rdi
0x180058b5a  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
