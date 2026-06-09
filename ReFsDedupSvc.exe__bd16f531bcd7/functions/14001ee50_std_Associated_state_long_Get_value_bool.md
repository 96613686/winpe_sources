# std::_Associated_state<long>::_Get_value(bool)

- ea: `0x14001ee50`
- end: `0x14001ef43`
- name: `?_Get_value@?$_Associated_state@J@std@@UEAAAEAJ_N@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001ef50`

## callees

- `0x140016074`
- `0x140016d88`
- `0x14001ee50`
- `0x14001f184`
- `0x14001f980`
- `0x140020560`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x14001eedf`
- `msvcp_win!_Cnd_wait` at `0x14001eedf`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14001ee91`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14001eef7`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14001ee91`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14001eef7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14001eeb0`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14001ef16`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14001eeb0`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14001ef16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Associated_state<long>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

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
  std::_Associated_state<long>::_Maybe_run_deferred_function(a1, v7);
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
0x14001ee50  push    rbp
0x14001ee52  push    rbx
0x14001ee53  push    rsi
0x14001ee54  push    rdi
0x14001ee55  mov     rbp, rsp
0x14001ee58  sub     rsp, 48h
0x14001ee5c  mov     bl, dl
0x14001ee5e  mov     rdi, rcx
0x14001ee61  lea     rdx, [rcx+20h]
0x14001ee65  lea     rcx, [rbp+var_18]
0x14001ee69  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x14001ee6e  nop
0x14001ee6f  lea     rsi, [rdi+0B8h]
0x14001ee76  test    bl, bl
0x14001ee78  jz      short loc_14001EE8A
0x14001ee7a  cmp     byte ptr [rsi], 0
0x14001ee7d  jz      short loc_14001EE8A
0x14001ee7f  mov     ecx, 2
0x14001ee84  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x14001ee8a  lea     rbx, [rdi+10h]
0x14001ee8e  mov     rcx, rbx
0x14001ee91  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14001ee98  nop     dword ptr [rax+rax+00h]
0x14001ee9d  test    al, al
0x14001ee9f  jz      short loc_14001EEC6
0x14001eea1  xorps   xmm0, xmm0
0x14001eea4  movdqu  [rbp+var_28], xmm0
0x14001eea9  mov     rdx, rbx
0x14001eeac  lea     rcx, [rbp+var_28]
0x14001eeb0  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14001eeb7  nop     dword ptr [rax+rax+00h]
0x14001eebc  lea     rcx, [rbp+var_28]
0x14001eec0  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x14001eec5  int     3; Trap to Debugger
0x14001eec6  mov     byte ptr [rsi], 1
0x14001eec9  lea     rdx, [rbp+var_18]
0x14001eecd  mov     rcx, rdi
0x14001eed0  call    ?_Maybe_run_deferred_function@?$_Associated_state@J@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<long>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x14001eed5  jmp     short loc_14001EEEB
0x14001eed7  mov     rdx, [rbp+var_18]; _Mtx_t
0x14001eedb  lea     rcx, [rdi+70h]; _Cnd_t
0x14001eedf  call    cs:__imp__Cnd_wait
0x14001eee6  nop     dword ptr [rax+rax+00h]
0x14001eeeb  cmp     dword ptr [rdi+0BCh], 0
0x14001eef2  jz      short loc_14001EED7
0x14001eef4  mov     rcx, rbx
0x14001eef7  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14001eefe  nop     dword ptr [rax+rax+00h]
0x14001ef03  test    al, al
0x14001ef05  jz      short loc_14001EF2C
0x14001ef07  xorps   xmm0, xmm0
0x14001ef0a  movdqu  [rbp+var_28], xmm0
0x14001ef0f  mov     rdx, rbx
0x14001ef12  lea     rcx, [rbp+var_28]
0x14001ef16  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14001ef1d  nop     dword ptr [rax+rax+00h]
0x14001ef22  lea     rcx, [rbp+var_28]
0x14001ef26  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x14001ef2b  nop
0x14001ef2c  lea     rcx, [rbp+var_18]
0x14001ef30  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x14001ef35  lea     rax, [rdi+0Ch]
0x14001ef39  add     rsp, 48h
0x14001ef3d  pop     rdi
0x14001ef3e  pop     rsi
0x14001ef3f  pop     rbx
0x14001ef40  pop     rbp
0x14001ef41  retn
```
