# winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::Lookup(void *,void * *)

- ea: `0x18000c2d0`
- end: `0x18000c3b9`
- name: `?Lookup@?$produce@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IMap@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAXPEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000c2d0`
- `0x18000c890`
- `0x18000e420`
- `0x180010200`
- `0x180034ef0`
- `0x180036f4c`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::Lookup(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // r15
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rbx
  _BYTE v11[16]; // [rsp+28h] [rbp-70h] BYREF
  __int64 v12; // [rsp+38h] [rbp-60h]
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v14; // [rsp+58h] [rbp-40h] BYREF

  v14 = a2;
  v4 = 0;
  *a3 = 0;
  v5 = a1 - 16;
  if ( !a1 )
    v5 = 0;
  v6 = 0;
  if ( v5 != -40 )
    v6 = v5;
  std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(
    v6 + 48,
    v11,
    &v14);
  v8 = v12;
  if ( *(_BYTE *)(v12 + 25) || (unsigned __int8)std::less<winrt::hstring>::operator()(v7, &v14, (__int64 *)(v12 + 32)) )
    v8 = *(_QWORD *)(v6 + 48);
  if ( v5 != -40 )
    v4 = v5;
  if ( v8 == *(_QWORD *)(v4 + 48) )
  {
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  v9 = *(_QWORD *)(v8 + 40);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*(_QWORD *)(v8 + 40));
  *a3 = v9;
  return 0;
}

```

## disassembly

```asm
0x18000c2d0  mov     [rsp+arg_18], rbx
0x18000c2d5  push    rsi
0x18000c2d6  push    rdi
0x18000c2d7  push    r12
0x18000c2d9  push    r14
0x18000c2db  push    r15
0x18000c2dd  sub     rsp, 70h
0x18000c2e1  mov     rax, cs:__security_cookie
0x18000c2e8  xor     rax, rsp
0x18000c2eb  mov     [rsp+98h+var_38], rax
0x18000c2f0  mov     r14, r8
0x18000c2f3  mov     [rsp+98h+var_40], rdx
0x18000c2f8  xor     ebx, ebx
0x18000c2fa  mov     [r8], rbx
0x18000c2fd  lea     rsi, [rcx-10h]
0x18000c301  test    rcx, rcx
0x18000c304  cmovz   rsi, rbx
0x18000c308  lea     r12, [rsi+28h]
0x18000c30c  mov     r15d, ebx
0x18000c30f  test    r12, r12
0x18000c312  cmovnz  r15, rsi
0x18000c316  lea     r8, [rsp+98h+var_40]
0x18000c31b  lea     rdx, [rsp+98h+var_70]
0x18000c320  lea     rcx, [r15+30h]
0x18000c324  call    ??$_Find_lower_bound@Uhstring@winrt@@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@PEAX@std@@@1@AEBUhstring@winrt@@@Z; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(winrt::hstring const &)
0x18000c329  mov     rdi, [rsp+98h+var_60]
0x18000c32e  cmp     [rdi+19h], bl
0x18000c331  jnz     short loc_18000C345
0x18000c333  lea     r8, [rdi+20h]
0x18000c337  lea     rdx, [rsp+98h+var_40]
0x18000c33c  call    ??R?$less@Uhstring@winrt@@@std@@QEBA_NAEBUhstring@winrt@@0@Z; std::less<winrt::hstring>::operator()(winrt::hstring const &,winrt::hstring const &)
0x18000c341  test    al, al
0x18000c343  jz      short loc_18000C349
0x18000c345  mov     rdi, [r15+30h]
0x18000c349  test    r12, r12
0x18000c34c  cmovnz  rbx, rsi
0x18000c350  cmp     rdi, [rbx+30h]
0x18000c354  jz      short loc_18000C39C
0x18000c356  mov     rbx, [rdi+28h]
0x18000c35a  test    rbx, rbx
0x18000c35d  jz      short loc_18000C36F
0x18000c35f  mov     rax, [rbx]
0x18000c362  mov     rcx, rbx
0x18000c365  mov     rax, [rax+8]
0x18000c369  call    cs:__guard_dispatch_icall_fptr
0x18000c36f  mov     [r14], rbx
0x18000c372  xor     eax, eax
0x18000c374  jmp     short loc_18000C37A
0x18000c376  mov     eax, [rsp+98h+var_78]
0x18000c37a  mov     rcx, [rsp+98h+var_38]
0x18000c37f  xor     rcx, rsp; StackCookie
0x18000c382  call    __security_check_cookie
0x18000c387  mov     rbx, [rsp+98h+arg_18]
0x18000c38f  add     rsp, 70h
0x18000c393  pop     r15
0x18000c395  pop     r14
0x18000c397  pop     r12
0x18000c399  pop     rdi
0x18000c39a  pop     rsi
0x18000c39b  retn
0x18000c39c  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18000c3a1  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x18000c3a6  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18000c3ad  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000c3b2  call    _CxxThrowException
```
