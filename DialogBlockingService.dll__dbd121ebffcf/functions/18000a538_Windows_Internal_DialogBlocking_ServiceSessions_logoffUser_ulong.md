# Windows::Internal::DialogBlocking::ServiceSessions::logoffUser(ulong)

- ea: `0x18000a538`
- end: `0x18000a654`
- name: `?logoffUser@ServiceSessions@DialogBlocking@Internal@Windows@@QEAAXK@Z`
- size: `284`
- prototype: `void __fastcall(Windows::Internal::DialogBlocking::ServiceSessions *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180006248`

## callees

- `0x180001644`
- `0x18000899c`
- `0x18000a23c`
- `0x18000a328`
- `0x18000a538`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a56d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a589`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a56d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a589`
- `msvcp_win!_Mtx_lock` at `0x18000a55e`
- `msvcp_win!_Mtx_lock` at `0x18000a55e`
- `msvcp_win!_Mtx_unlock` at `0x18000a609`
- `msvcp_win!_Mtx_unlock` at `0x18000a635`
- `msvcp_win!_Mtx_unlock` at `0x18000a609`
- `msvcp_win!_Mtx_unlock` at `0x18000a635`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::ServiceSessions::logoffUser(
        Windows::Internal::DialogBlocking::ServiceSessions *this,
        unsigned int a2)
{
  char *v4; // rbx
  char v5; // di
  __int64 *v6; // rdx
  __int64 *v7; // rcx
  char v8; // r9
  __int64 *v9; // rax
  Windows::Internal::DialogBlocking::HookProcess **v10; // rsi
  unsigned int v11; // [rsp+78h] [rbp+10h] BYREF

  v11 = a2;
  v4 = (char *)this + 16;
  if ( _Mtx_lock((Windows::Internal::DialogBlocking::ServiceSessions *)((char *)this + 16)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v4 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v5 = 1;
  v6 = *(__int64 **)(*(_QWORD *)this + 8LL);
  v7 = *(__int64 **)this;
  if ( !*((_BYTE *)v6 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v6 + 8) >= a2 )
      {
        v8 = 0;
        v7 = v6;
      }
      else
      {
        v8 = 1;
      }
      v9 = v6 + 2;
      if ( !v8 )
        v9 = v6;
      v6 = (__int64 *)*v9;
    }
    while ( !*(_BYTE *)(*v9 + 25) );
  }
  if ( !*((_BYTE *)v7 + 25) && a2 >= *((_DWORD *)v7 + 8) && v7 != *(__int64 **)this )
  {
    v10 = (Windows::Internal::DialogBlocking::HookProcess **)v7[5];
    v7[5] = 0;
    std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>::erase(
      this,
      &v11);
    if ( !v4 )
      std::_Throw_system_error(1u);
    _Mtx_unlock((_Mtx_t)v4);
    v5 = 0;
    if ( v10 )
    {
      Windows::Internal::DialogBlocking::HookMgr::~HookMgr(v10);
      operator delete(v10);
    }
  }
  if ( v5 )
    _Mtx_unlock((_Mtx_t)v4);
}

```

## disassembly

```asm
0x18000a538  mov     rax, rsp
0x18000a53b  mov     [rax+18h], rbx
0x18000a53f  mov     [rax+10h], edx
0x18000a542  push    rsi
0x18000a543  push    rdi
0x18000a544  push    r14
0x18000a546  sub     rsp, 50h
0x18000a54a  mov     esi, edx
0x18000a54c  mov     r14, rcx
0x18000a54f  lea     rbx, [rcx+10h]
0x18000a553  mov     [rax-48h], rbx
0x18000a557  mov     byte ptr [rax-40h], 0
0x18000a55b  mov     rcx, rbx; _Mtx_t
0x18000a55e  call    cs:__imp__Mtx_lock
0x18000a564  test    eax, eax
0x18000a566  jz      short loc_18000A574
0x18000a568  mov     ecx, 5
0x18000a56d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a573  int     3; Trap to Debugger
0x18000a574  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18000a57b  jnz     short loc_18000A590
0x18000a57d  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18000a584  mov     ecx, 6
0x18000a589  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a58f  int     3; Trap to Debugger
0x18000a590  mov     edi, 1
0x18000a595  mov     [rsp+68h+var_40], dil
0x18000a59a  mov     r8, [r14]
0x18000a59d  mov     rdx, [r8+8]
0x18000a5a1  xor     eax, eax
0x18000a5a3  mov     [rsp+68h+var_2C], eax
0x18000a5a7  mov     rcx, r8
0x18000a5aa  cmp     [rdx+19h], al
0x18000a5ad  jnz     short loc_18000A5D3
0x18000a5af  cmp     [rdx+20h], esi
0x18000a5b2  jnb     short loc_18000A5B9
0x18000a5b4  mov     r9b, dil
0x18000a5b7  jmp     short loc_18000A5BF
0x18000a5b9  xor     r9b, r9b
0x18000a5bc  mov     rcx, rdx
0x18000a5bf  lea     rax, [rdx+10h]
0x18000a5c3  test    r9b, r9b
0x18000a5c6  cmovz   rax, rdx
0x18000a5ca  mov     rdx, [rax]
0x18000a5cd  cmp     byte ptr [rdx+19h], 0
0x18000a5d1  jz      short loc_18000A5AF
0x18000a5d3  cmp     byte ptr [rcx+19h], 0
0x18000a5d7  jnz     short loc_18000A62D
0x18000a5d9  cmp     esi, [rcx+20h]
0x18000a5dc  jb      short loc_18000A62D
0x18000a5de  cmp     rcx, r8
0x18000a5e1  jz      short loc_18000A62D
0x18000a5e3  mov     rsi, [rcx+28h]
0x18000a5e7  mov     [rsp+68h+arg_0], rsi
0x18000a5ec  mov     qword ptr [rcx+28h], 0
0x18000a5f4  lea     rdx, [rsp+68h+arg_8]
0x18000a5f9  mov     rcx, r14
0x18000a5fc  call    ?erase@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>::erase(ulong const &)
0x18000a601  test    rbx, rbx
0x18000a604  jz      short loc_18000A64C
0x18000a606  mov     rcx, rbx; _Mtx_t
0x18000a609  call    cs:__imp__Mtx_unlock
0x18000a60f  xor     dil, dil
0x18000a612  test    rsi, rsi
0x18000a615  jz      short loc_18000A62D
0x18000a617  mov     rcx, rsi; this
0x18000a61a  call    ??1HookMgr@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookMgr::~HookMgr(void)
0x18000a61f  mov     edx, 28h ; '('; unsigned __int64
0x18000a624  mov     rcx, rsi; void *
0x18000a627  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a62c  nop
0x18000a62d  test    dil, dil
0x18000a630  jz      short loc_18000A63B
0x18000a632  mov     rcx, rbx; _Mtx_t
0x18000a635  call    cs:__imp__Mtx_unlock
0x18000a63b  mov     rbx, [rsp+68h+arg_10]
0x18000a643  add     rsp, 50h
0x18000a647  pop     r14
0x18000a649  pop     rdi
0x18000a64a  pop     rsi
0x18000a64b  retn
0x18000a64c  mov     ecx, edi
0x18000a64e  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
```
