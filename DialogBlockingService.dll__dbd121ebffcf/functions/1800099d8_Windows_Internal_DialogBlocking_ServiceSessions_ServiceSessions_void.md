# Windows::Internal::DialogBlocking::ServiceSessions::~ServiceSessions(void)

- ea: `0x1800099d8`
- end: `0x180009b25`
- name: `??1ServiceSessions@DialogBlocking@Internal@Windows@@QEAA@XZ`
- size: `333`
- prototype: `void __fastcall(Windows::Internal::DialogBlocking::ServiceSessions *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004140`
- `0x180006890`
- `0x180007fa0`

## callees

- `0x180001650`
- `0x180003e18`
- `0x180009010`
- `0x1800099d8`
- `0x18000a23c`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180009a29`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180009a45`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180009a29`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180009a45`
- `msvcp_win!_Mtx_lock` at `0x180009a1a`
- `msvcp_win!_Mtx_lock` at `0x180009a1a`
- `msvcp_win!_Mtx_unlock` at `0x180009a84`
- `msvcp_win!_Mtx_unlock` at `0x180009a84`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::ServiceSessions::~ServiceSessions(
        Windows::Internal::DialogBlocking::ServiceSessions *this)
{
  _QWORD *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 *v5; // rbx
  __int64 v6; // rsi
  __int64 **v7; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int128 v10; // [rsp+20h] [rbp-18h] BYREF

  v10 = 0;
  v2 = operator new(0x30u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *(_QWORD *)&v10 = v2;
  if ( _Mtx_lock((Windows::Internal::DialogBlocking::ServiceSessions *)((char *)this + 16)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)this + 23) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 23) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  if ( this != (Windows::Internal::DialogBlocking::ServiceSessions *)&v10 )
  {
    v3 = *(_QWORD *)this;
    *(_QWORD *)this = v10;
    *(_QWORD *)&v10 = v3;
    v4 = *((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = *((_QWORD *)&v10 + 1);
    *((_QWORD *)&v10 + 1) = v4;
  }
  if ( this == (Windows::Internal::DialogBlocking::ServiceSessions *)-16LL )
    std::_Throw_system_error(1);
  _Mtx_unlock((Windows::Internal::DialogBlocking::ServiceSessions *)((char *)this + 16));
  v5 = *(__int64 **)v10;
  while ( !*((_BYTE *)v5 + 25) )
  {
    v6 = v5[5];
    if ( *(_BYTE *)(v6 + 4) )
      Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(*(Windows::Internal::DialogBlocking::HookProcess **)(v6 + 24));
    Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(*(Windows::Internal::DialogBlocking::HookProcess **)(v6 + 32));
    v7 = (__int64 **)v5[2];
    if ( *((_BYTE *)v7 + 25) )
    {
      for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25) && v5 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v5 = i;
      v5 = i;
    }
    else
    {
      v5 = (__int64 *)v5[2];
      for ( j = *v7; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v5 = j;
    }
  }
  std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>((void **)&v10);
  std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>((void **)this);
}

```

## disassembly

```asm
0x1800099d8  mov     [rsp+arg_0], rbx
0x1800099dd  mov     [rsp+arg_8], rsi
0x1800099e2  push    rdi
0x1800099e3  sub     rsp, 30h
0x1800099e7  mov     rdi, rcx
0x1800099ea  xorps   xmm0, xmm0
0x1800099ed  movdqu  [rsp+38h+var_18], xmm0
0x1800099f3  mov     ecx, 30h ; '0'; Size
0x1800099f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800099fd  mov     [rax], rax
0x180009a00  mov     [rax+8], rax
0x180009a04  mov     [rax+10h], rax
0x180009a08  mov     word ptr [rax+18h], 101h
0x180009a0e  mov     qword ptr [rsp+38h+var_18], rax
0x180009a13  lea     rbx, [rdi+10h]
0x180009a17  mov     rcx, rbx; _Mtx_t
0x180009a1a  call    cs:__imp__Mtx_lock
0x180009a20  test    eax, eax
0x180009a22  jz      short loc_180009A30
0x180009a24  mov     ecx, 5
0x180009a29  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180009a2f  int     3; Trap to Debugger
0x180009a30  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180009a37  jnz     short loc_180009A4C
0x180009a39  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180009a40  mov     ecx, 6
0x180009a45  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180009a4b  int     3; Trap to Debugger
0x180009a4c  lea     rax, [rsp+38h+var_18]
0x180009a51  cmp     rdi, rax
0x180009a54  jz      short loc_180009A78
0x180009a56  mov     rdx, [rdi]
0x180009a59  mov     rax, qword ptr [rsp+38h+var_18]
0x180009a5e  mov     [rdi], rax
0x180009a61  mov     qword ptr [rsp+38h+var_18], rdx
0x180009a66  mov     rdx, [rdi+8]
0x180009a6a  mov     rax, qword ptr [rsp+38h+var_18+8]
0x180009a6f  mov     [rdi+8], rax
0x180009a73  mov     qword ptr [rsp+38h+var_18+8], rdx
0x180009a78  test    rbx, rbx
0x180009a7b  jz      loc_180009B1A
0x180009a81  mov     rcx, rbx; _Mtx_t
0x180009a84  call    cs:__imp__Mtx_unlock
0x180009a8a  mov     rbx, qword ptr [rsp+38h+var_18]
0x180009a8f  mov     rbx, [rbx]
0x180009a92  cmp     byte ptr [rbx+19h], 0
0x180009a96  jnz     short loc_180009AF9
0x180009a98  mov     rsi, [rbx+28h]
0x180009a9c  cmp     byte ptr [rsi+4], 0
0x180009aa0  jz      short loc_180009AAB
0x180009aa2  mov     rcx, [rsi+18h]; this
0x180009aa6  call    ?ResetHookProcess@HookProcess@DialogBlocking@Internal@Windows@@QEAAXXZ; Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(void)
0x180009aab  mov     rcx, [rsi+20h]; this
0x180009aaf  call    ?ResetHookProcess@HookProcess@DialogBlocking@Internal@Windows@@QEAAXXZ; Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(void)
0x180009ab4  mov     rcx, [rbx+10h]
0x180009ab8  cmp     byte ptr [rcx+19h], 0
0x180009abc  jz      short loc_180009ADC
0x180009abe  mov     rax, [rbx+8]
0x180009ac2  jmp     short loc_180009AD1
0x180009ac4  cmp     rbx, [rax+10h]
0x180009ac8  jnz     short loc_180009AD7
0x180009aca  mov     rbx, rax
0x180009acd  mov     rax, [rax+8]
0x180009ad1  cmp     byte ptr [rax+19h], 0
0x180009ad5  jz      short loc_180009AC4
0x180009ad7  mov     rbx, rax
0x180009ada  jmp     short loc_180009A92
0x180009adc  mov     rbx, rcx
0x180009adf  mov     rcx, [rcx]
0x180009ae2  cmp     byte ptr [rcx+19h], 0
0x180009ae6  jnz     short loc_180009A92
0x180009ae8  mov     rbx, rcx
0x180009aeb  mov     rax, [rcx]
0x180009aee  mov     rcx, rax
0x180009af1  cmp     byte ptr [rax+19h], 0
0x180009af5  jz      short loc_180009AE8
0x180009af7  jmp     short loc_180009A92
0x180009af9  lea     rcx, [rsp+38h+var_18]
0x180009afe  call    ??1?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>(void)
0x180009b03  mov     rcx, rdi
0x180009b06  mov     rbx, [rsp+38h+arg_0]
0x180009b0b  mov     rsi, [rsp+38h+arg_8]
0x180009b10  add     rsp, 30h
0x180009b14  pop     rdi
0x180009b15  jmp     ??1?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>(void)
0x180009b1a  mov     ecx, 1
0x180009b1f  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
```
