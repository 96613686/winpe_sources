# std::jthread::~jthread(void)

- ea: `0x18000a8d4`
- end: `0x18000a994`
- name: `??1jthread@std@@QEAA@XZ`
- size: `192`
- prototype: `void __fastcall(std::jthread *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000abe0`
- `0x18000c694`

## callees

- `0x180002024`
- `0x18000a8d4`
- `0x18000c040`

## import_xrefs

- `msvcp_win!_Thrd_id` at `0x18000a90a`
- `msvcp_win!_Thrd_id` at `0x18000a90a`
- `msvcp_win!_Thrd_join` at `0x18000a930`
- `msvcp_win!_Thrd_join` at `0x18000a930`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a900`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a919`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a93f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a900`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a919`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a93f`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000a982`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000a982`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::jthread::~jthread(_Thrd_t *this, __int64 a2, __int64 a3)
{
  std::_Stop_state *Hnd; // rcx
  _Thrd_id_t Id; // ebx
  volatile signed __int32 *v6; // rcx
  _Thrd_t v7; // [rsp+20h] [rbp-18h] BYREF

  if ( this->_Id )
  {
    Hnd = (std::_Stop_state *)this[1]._Hnd;
    if ( Hnd )
      std::_Stop_state::_Request_stop(Hnd);
    if ( !this->_Id )
    {
      std::_Throw_Cpp_error(1);
      __debugbreak();
    }
    Id = this->_Id;
    if ( Id == _Thrd_id() )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    v7 = *this;
    if ( _Thrd_join(&v7, 0) )
    {
      std::_Throw_Cpp_error(2);
      __debugbreak();
    }
    *this = 0;
  }
  v6 = (volatile signed __int32 *)this[1]._Hnd;
  if ( v6
    && (_InterlockedExchangeAdd(v6 + 1, 0xFFFFFFFE) & 0xFFFFFFFE) == 2
    && _InterlockedExchangeAdd(v6, 0xFFFFFFFF) == 1 )
  {
    operator delete((void *)v6);
  }
  if ( this->_Id )
    _o_terminate(v6, a2, a3);
}

```

## disassembly

```asm
0x18000a8d4  mov     [rsp+arg_0], rbx
0x18000a8d9  push    rdi
0x18000a8da  sub     rsp, 30h
0x18000a8de  mov     rdi, rcx
0x18000a8e1  cmp     dword ptr [rcx+8], 0
0x18000a8e5  jz      short loc_18000A94D
0x18000a8e7  mov     rcx, [rcx+10h]; this
0x18000a8eb  test    rcx, rcx
0x18000a8ee  jz      short loc_18000A8F5
0x18000a8f0  call    ?_Request_stop@_Stop_state@std@@QEAA_NXZ; std::_Stop_state::_Request_stop(void)
0x18000a8f5  cmp     dword ptr [rdi+8], 0
0x18000a8f9  jnz     short loc_18000A907
0x18000a8fb  mov     ecx, 1
0x18000a900  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a906  int     3; Trap to Debugger
0x18000a907  mov     ebx, [rdi+8]
0x18000a90a  call    cs:__imp__Thrd_id
0x18000a910  cmp     ebx, eax
0x18000a912  jnz     short loc_18000A920
0x18000a914  mov     ecx, 5
0x18000a919  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a91f  int     3; Trap to Debugger
0x18000a920  movups  xmm0, xmmword ptr [rdi]
0x18000a923  movdqu  xmmword ptr [rsp+38h+var_18._Hnd], xmm0
0x18000a929  xor     edx, edx; int *
0x18000a92b  lea     rcx, [rsp+38h+var_18]; _Thrd_t
0x18000a930  call    cs:__imp__Thrd_join
0x18000a936  test    eax, eax
0x18000a938  jz      short loc_18000A946
0x18000a93a  mov     ecx, 2
0x18000a93f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a945  int     3; Trap to Debugger
0x18000a946  xorps   xmm0, xmm0
0x18000a949  movdqu  xmmword ptr [rdi], xmm0
0x18000a94d  mov     rcx, [rdi+10h]; Block
0x18000a951  test    rcx, rcx
0x18000a954  jz      short loc_18000A97C
0x18000a956  mov     eax, 0FFFFFFFEh
0x18000a95b  lock xadd [rcx+4], eax
0x18000a960  and     eax, 0FFFFFFFEh
0x18000a963  cmp     eax, 2
0x18000a966  jnz     short loc_18000A97C
0x18000a968  or      eax, 0FFFFFFFFh
0x18000a96b  lock xadd [rcx], eax
0x18000a96f  cmp     eax, 1
0x18000a972  jnz     short loc_18000A97C
0x18000a974  lea     edx, [rax+1Fh]
0x18000a977  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a97c  cmp     dword ptr [rdi+8], 0
0x18000a980  jz      short loc_18000A989
0x18000a982  call    cs:__imp__o_terminate
0x18000a988  nop
0x18000a989  mov     rbx, [rsp+38h+arg_0]
0x18000a98e  add     rsp, 30h
0x18000a992  pop     rdi
0x18000a993  retn
```
