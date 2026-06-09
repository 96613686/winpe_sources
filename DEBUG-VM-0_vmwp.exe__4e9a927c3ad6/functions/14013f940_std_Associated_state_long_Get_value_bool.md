# std::_Associated_state<long>::_Get_value(bool)

- ea: `0x14013f940`
- end: `0x14013fa54`
- name: `?_Get_value@?$_Associated_state@J@std@@UEAAAEAJ_N@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400e1600`
- `0x1400e183c`
- `0x140132940`
- `0x14013f940`
- `0x14013fa6c`
- `0x14013fd20`
- `0x14013ffc0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14013f996`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14013f9fc`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14013f996`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14013f9fc`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14013f9b5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14013fa1b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14013f9b5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14013fa1b`
- `msvcp_win!_Cnd_wait` at `0x14013f9e4`
- `msvcp_win!_Cnd_wait` at `0x14013f9e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Associated_state<long>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-38h] BYREF
  _Mtx_t v7[2]; // [rsp+30h] [rbp-28h] BYREF

  *(_OWORD *)v7 = 0;
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 32);
  v4 = (_BYTE *)(a1 + 184);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    std::rethrow_exception(&v6);
    __debugbreak();
  }
  *v4 = 1;
  std::_Associated_state<int>::_Maybe_run_deferred_function(a1, v7);
  while ( !*(_DWORD *)(a1 + 188) )
    _Cnd_wait((_Cnd_t)(a1 + 112), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    std::rethrow_exception(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 12;
}

```

## disassembly

```asm
0x14013f940  push    rbp
0x14013f942  push    rbx
0x14013f943  push    rsi
0x14013f944  push    rdi
0x14013f945  mov     rbp, rsp
0x14013f948  sub     rsp, 58h
0x14013f94c  mov     rax, cs:__security_cookie
0x14013f953  xor     rax, rsp
0x14013f956  mov     [rbp+var_18], rax
0x14013f95a  mov     bl, dl
0x14013f95c  mov     rdi, rcx
0x14013f95f  xorps   xmm0, xmm0
0x14013f962  movups  xmmword ptr [rbp+var_28], xmm0
0x14013f966  lea     rdx, [rcx+20h]
0x14013f96a  lea     rcx, [rbp+var_28]
0x14013f96e  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x14013f973  nop
0x14013f974  lea     rsi, [rdi+0B8h]
0x14013f97b  test    bl, bl
0x14013f97d  jz      short loc_14013F98F
0x14013f97f  cmp     byte ptr [rsi], 0
0x14013f982  jz      short loc_14013F98F
0x14013f984  mov     ecx, 2
0x14013f989  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x14013f98f  lea     rbx, [rdi+10h]
0x14013f993  mov     rcx, rbx
0x14013f996  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14013f99d  nop     dword ptr [rax+rax+00h]
0x14013f9a2  test    al, al
0x14013f9a4  jz      short loc_14013F9CB
0x14013f9a6  xorps   xmm0, xmm0
0x14013f9a9  movdqu  [rbp+var_38], xmm0
0x14013f9ae  mov     rdx, rbx
0x14013f9b1  lea     rcx, [rbp+var_38]
0x14013f9b5  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14013f9bc  nop     dword ptr [rax+rax+00h]
0x14013f9c1  lea     rcx, [rbp+var_38]
0x14013f9c5  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x14013f9ca  int     3; Trap to Debugger
0x14013f9cb  mov     byte ptr [rsi], 1
0x14013f9ce  lea     rdx, [rbp+var_28]
0x14013f9d2  mov     rcx, rdi
0x14013f9d5  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x14013f9da  jmp     short loc_14013F9F0
0x14013f9dc  mov     rdx, [rbp+var_28]; _Mtx_t
0x14013f9e0  lea     rcx, [rdi+70h]; _Cnd_t
0x14013f9e4  call    cs:__imp__Cnd_wait
0x14013f9eb  nop     dword ptr [rax+rax+00h]
0x14013f9f0  cmp     dword ptr [rdi+0BCh], 0
0x14013f9f7  jz      short loc_14013F9DC
0x14013f9f9  mov     rcx, rbx
0x14013f9fc  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14013fa03  nop     dword ptr [rax+rax+00h]
0x14013fa08  test    al, al
0x14013fa0a  jz      short loc_14013FA31
0x14013fa0c  xorps   xmm0, xmm0
0x14013fa0f  movdqu  [rbp+var_38], xmm0
0x14013fa14  mov     rdx, rbx
0x14013fa17  lea     rcx, [rbp+var_38]
0x14013fa1b  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14013fa22  nop     dword ptr [rax+rax+00h]
0x14013fa27  lea     rcx, [rbp+var_38]
0x14013fa2b  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x14013fa30  nop
0x14013fa31  lea     rcx, [rbp+var_28]
0x14013fa35  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x14013fa3a  lea     rax, [rdi+0Ch]
0x14013fa3e  mov     rcx, [rbp+var_18]
0x14013fa42  xor     rcx, rsp; StackCookie
0x14013fa45  call    __security_check_cookie
0x14013fa4a  add     rsp, 58h
0x14013fa4e  pop     rdi
0x14013fa4f  pop     rsi
0x14013fa50  pop     rbx
0x14013fa51  pop     rbp
0x14013fa52  retn
```
