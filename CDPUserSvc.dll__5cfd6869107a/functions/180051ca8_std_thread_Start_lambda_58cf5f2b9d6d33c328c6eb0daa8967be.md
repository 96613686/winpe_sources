# std::thread::_Start__lambda_58cf5f2b9d6d33c328c6eb0daa8967be___

- ea: `0x180051ca8`
- end: `0x180051d71`
- name: `std::thread::_Start__lambda_58cf5f2b9d6d33c328c6eb0daa8967be___`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026dd0`
- `0x180027400`

## callees

- `0x180002a14`
- `0x18002c5a0`
- `0x18003f9c0`
- `0x18003fd84`
- `0x180051ca8`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180051d6a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180051d6a`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180051d2e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180051d2e`

## pseudocode

```c
__int64 __fastcall std::thread::_Start__lambda_58cf5f2b9d6d33c328c6eb0daa8967be___(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  __int64 v6; // rax
  _QWORD *v8; // [rsp+40h] [rbp+8h] BYREF

  v4 = operator new(0x50u);
  v5 = v4;
  *v4 = 0;
  if ( v4 != a2 )
  {
    *v4 = *a2;
    *a2 = 0;
  }
  std::string::string(v4 + 1, a2 + 1);
  std::string::string(v5 + 5, a2 + 5);
  Microsoft::WRL::ComPtr<ICDPResourceHandlerCallback>::ComPtr<ICDPResourceHandlerCallback>(v5 + 9, a2 + 9);
  v8 = v5;
  v6 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be____0_,
         v5,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x180051D70LL);
  }
  v8 = 0;
  return std::unique_ptr_std::tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be____std::default_delete_std::tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be_______::_unique_ptr_std::tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be____std::default_delete_std::tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be_______(&v8);
}

```

## disassembly

```asm
0x180051ca8  mov     [rsp+arg_8], rbx
0x180051cad  mov     [rsp+arg_10], rsi
0x180051cb2  push    rdi
0x180051cb3  sub     rsp, 30h
0x180051cb7  mov     rdi, rdx
0x180051cba  mov     rsi, rcx
0x180051cbd  mov     ecx, 50h ; 'P'; Size
0x180051cc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051cc7  mov     rbx, rax
0x180051cca  mov     qword ptr [rax], 0
0x180051cd1  cmp     rax, rdi
0x180051cd4  jz      short loc_180051CE3
0x180051cd6  mov     r8, [rdi]
0x180051cd9  mov     [rax], r8
0x180051cdc  mov     qword ptr [rdi], 0
0x180051ce3  lea     rdx, [rdi+8]
0x180051ce7  lea     rcx, [rax+8]
0x180051ceb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180051cf0  lea     rdx, [rdi+28h]
0x180051cf4  lea     rcx, [rbx+28h]
0x180051cf8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180051cfd  lea     rdx, [rdi+48h]
0x180051d01  lea     rcx, [rbx+48h]
0x180051d05  call    ??0?$ComPtr@VICDPResourceHandlerCallback@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ICDPResourceHandlerCallback>::ComPtr<ICDPResourceHandlerCallback>(Microsoft::WRL::ComPtr<ICDPResourceHandlerCallback> &&)
0x180051d0a  mov     [rsp+38h+arg_0], rbx
0x180051d0f  lea     rdi, [rsi+8]
0x180051d13  mov     [rsp+38h+var_10], rdi
0x180051d18  mov     [rsp+38h+var_18], 0
0x180051d20  mov     r9, rbx
0x180051d23  lea     r8, std__thread___Invoke_std__tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be____0_
0x180051d2a  xor     edx, edx
0x180051d2c  xor     ecx, ecx
0x180051d2e  call    cs:__imp__o__beginthreadex
0x180051d34  mov     [rsi], rax
0x180051d37  test    rax, rax
0x180051d3a  jz      short loc_180051D5F
0x180051d3c  mov     [rsp+38h+arg_0], 0
0x180051d45  lea     rcx, [rsp+38h+arg_0]
0x180051d4a  call    std__unique_ptr_std__tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be____std__default_delete_std__tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be__________unique_ptr_std__tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be____std__default_delete_std__tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be_______
0x180051d4f  mov     rbx, [rsp+38h+arg_8]
0x180051d54  mov     rsi, [rsp+38h+arg_10]
0x180051d59  add     rsp, 30h
0x180051d5d  pop     rdi
0x180051d5e  retn
0x180051d5f  mov     dword ptr [rdi], 0
0x180051d65  mov     ecx, 6
0x180051d6a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
