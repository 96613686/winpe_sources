# Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::~DedicatedThreadRequestDispatcher(void)

- ea: `0x18001b794`
- end: `0x18001b856`
- name: `??1DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@UEAA@XZ`
- size: `194`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bfe0`

## callees

- `0x18000fa08`
- `0x180012130`
- `0x18001b794`
- `0x18001b930`
- `0x18001f140`

## import_xrefs

- `msvcp_win!_Thrd_id` at `0x18001b7ea`
- `msvcp_win!_Thrd_id` at `0x18001b7ea`
- `msvcp_win!_Thrd_join` at `0x18001b810`
- `msvcp_win!_Thrd_join` at `0x18001b810`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001b7e0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001b7f9`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001b81f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001b7e0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001b7f9`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001b81f`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18001b7cb`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18001b7cb`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::~DedicatedThreadRequestDispatcher(
        HANDLE *this)
{
  char *v2; // rsi
  _Thrd_t *v3; // rdi
  int v4; // ebx
  _Thrd_t v5; // [rsp+20h] [rbp-18h] BYREF

  *this = &Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::`vftable';
  Microsoft::Bluetooth::Foundation::Details::CountdownEvent::WaitForZero((Microsoft::Bluetooth::Foundation::Details::CountdownEvent *)(this + 7));
  v2 = (char *)(this + 4);
  PostQueuedCompletionStatus(this[4], 0, 0x14C4EF3Fu, 0);
  v3 = (_Thrd_t *)(this + 5);
  if ( !*((_DWORD *)this + 12) )
  {
    std::_Throw_Cpp_error(1);
    __debugbreak();
  }
  v4 = *((_DWORD *)this + 12);
  if ( v4 == _Thrd_id() )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  v5 = *v3;
  if ( _Thrd_join(&v5, 0) )
  {
    std::_Throw_Cpp_error(2);
    __debugbreak();
  }
  *v3 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v2,
    0);
  std::thread::~thread((std::thread *)v3);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v2);
}

```

## disassembly

```asm
0x18001b794  mov     [rsp+arg_0], rbx
0x18001b799  mov     [rsp+arg_8], rsi
0x18001b79e  push    rdi
0x18001b79f  sub     rsp, 30h
0x18001b7a3  mov     rbx, rcx
0x18001b7a6  lea     rax, ??_7DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::`vftable'
0x18001b7ad  mov     [rcx], rax
0x18001b7b0  add     rcx, 38h ; '8'; this
0x18001b7b4  call    ?WaitForZero@CountdownEvent@Details@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::Details::CountdownEvent::WaitForZero(void)
0x18001b7b9  lea     rsi, [rbx+20h]
0x18001b7bd  xor     r9d, r9d; lpOverlapped
0x18001b7c0  xor     edx, edx; dwNumberOfBytesTransferred
0x18001b7c2  mov     r8d, 14C4EF3Fh; dwCompletionKey
0x18001b7c8  mov     rcx, [rsi]; CompletionPort
0x18001b7cb  call    cs:__imp_PostQueuedCompletionStatus
0x18001b7d1  lea     rdi, [rbx+28h]
0x18001b7d5  cmp     dword ptr [rdi+8], 0
0x18001b7d9  jnz     short loc_18001B7E7
0x18001b7db  mov     ecx, 1
0x18001b7e0  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001b7e6  int     3; Trap to Debugger
0x18001b7e7  mov     ebx, [rdi+8]
0x18001b7ea  call    cs:__imp__Thrd_id
0x18001b7f0  cmp     ebx, eax
0x18001b7f2  jnz     short loc_18001B800
0x18001b7f4  mov     ecx, 5
0x18001b7f9  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001b7ff  int     3; Trap to Debugger
0x18001b800  movups  xmm0, xmmword ptr [rdi]
0x18001b803  movdqu  xmmword ptr [rsp+38h+var_18._Hnd], xmm0
0x18001b809  xor     edx, edx; int *
0x18001b80b  lea     rcx, [rsp+38h+var_18]; _Thrd_t
0x18001b810  call    cs:__imp__Thrd_join
0x18001b816  test    eax, eax
0x18001b818  jz      short loc_18001B826
0x18001b81a  mov     ecx, 2
0x18001b81f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001b825  int     3; Trap to Debugger
0x18001b826  xorps   xmm0, xmm0
0x18001b829  movdqu  xmmword ptr [rdi], xmm0
0x18001b82d  xor     edx, edx
0x18001b82f  mov     rcx, rsi
0x18001b832  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001b837  mov     rcx, rdi; this
0x18001b83a  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18001b83f  mov     rcx, rsi
0x18001b842  mov     rbx, [rsp+38h+arg_0]
0x18001b847  mov     rsi, [rsp+38h+arg_8]
0x18001b84c  add     rsp, 30h
0x18001b850  pop     rdi
0x18001b851  jmp     ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
```
