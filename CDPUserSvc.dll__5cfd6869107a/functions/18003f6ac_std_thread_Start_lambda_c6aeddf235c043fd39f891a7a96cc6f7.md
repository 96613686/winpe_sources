# std::thread::_Start__lambda_c6aeddf235c043fd39f891a7a96cc6f7___

- ea: `0x18003f6ac`
- end: `0x18003f775`
- name: `std::thread::_Start__lambda_c6aeddf235c043fd39f891a7a96cc6f7___`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026670`

## callees

- `0x180002a14`
- `0x18002c5a0`
- `0x18003f6ac`
- `0x18003f9c0`
- `0x18003fd84`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003f76e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003f76e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003f732`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003f732`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start__lambda_c6aeddf235c043fd39f891a7a96cc6f7___(__int64 a1, _QWORD *a2)
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
         std::thread::_Invoke_std::tuple__lambda_c6aeddf235c043fd39f891a7a96cc6f7____0_,
         v5,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18003F774LL);
  }
  v8 = 0;
  return std::unique_ptr_std::tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be____std::default_delete_std::tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be_______::_unique_ptr_std::tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be____std::default_delete_std::tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be_______(&v8);
}

```

## disassembly

```asm
0x18003f6ac  mov     [rsp+arg_8], rbx
0x18003f6b1  mov     [rsp+arg_10], rsi
0x18003f6b6  push    rdi
0x18003f6b7  sub     rsp, 30h
0x18003f6bb  mov     rdi, rdx
0x18003f6be  mov     rsi, rcx
0x18003f6c1  mov     ecx, 50h ; 'P'; Size
0x18003f6c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f6cb  mov     rbx, rax
0x18003f6ce  mov     qword ptr [rax], 0
0x18003f6d5  cmp     rax, rdi
0x18003f6d8  jz      short loc_18003F6E7
0x18003f6da  mov     r8, [rdi]
0x18003f6dd  mov     [rax], r8
0x18003f6e0  mov     qword ptr [rdi], 0
0x18003f6e7  lea     rdx, [rdi+8]
0x18003f6eb  lea     rcx, [rax+8]
0x18003f6ef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x18003f6f4  lea     rdx, [rdi+28h]
0x18003f6f8  lea     rcx, [rbx+28h]
0x18003f6fc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x18003f701  lea     rdx, [rdi+48h]
0x18003f705  lea     rcx, [rbx+48h]
0x18003f709  call    ??0?$ComPtr@VICDPResourceHandlerCallback@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ICDPResourceHandlerCallback>::ComPtr<ICDPResourceHandlerCallback>(Microsoft::WRL::ComPtr<ICDPResourceHandlerCallback> &&)
0x18003f70e  mov     [rsp+38h+arg_0], rbx
0x18003f713  lea     rdi, [rsi+8]
0x18003f717  mov     [rsp+38h+var_10], rdi
0x18003f71c  mov     [rsp+38h+var_18], 0
0x18003f724  mov     r9, rbx
0x18003f727  lea     r8, std__thread___Invoke_std__tuple__lambda_c6aeddf235c043fd39f891a7a96cc6f7____0_
0x18003f72e  xor     edx, edx
0x18003f730  xor     ecx, ecx
0x18003f732  call    cs:__imp__o__beginthreadex
0x18003f738  mov     [rsi], rax
0x18003f73b  test    rax, rax
0x18003f73e  jz      short loc_18003F763
0x18003f740  mov     [rsp+38h+arg_0], 0
0x18003f749  lea     rcx, [rsp+38h+arg_0]
0x18003f74e  call    std__unique_ptr_std__tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be____std__default_delete_std__tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be__________unique_ptr_std__tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be____std__default_delete_std__tuple__lambda_58cf5f2b9d6d33c328c6eb0daa8967be_______
0x18003f753  mov     rbx, [rsp+38h+arg_8]
0x18003f758  mov     rsi, [rsp+38h+arg_10]
0x18003f75d  add     rsp, 30h
0x18003f761  pop     rdi
0x18003f762  retn
0x18003f763  mov     dword ptr [rdi], 0
0x18003f769  mov     ecx, 6
0x18003f76e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
