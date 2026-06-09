# std::thread::_Start__lambda_bd4ddfa317c149460230ee2d95f307a6___

- ea: `0x18003f5e8`
- end: `0x18003f6a4`
- name: `std::thread::_Start__lambda_bd4ddfa317c149460230ee2d95f307a6___`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026c00`

## callees

- `0x180002a14`
- `0x18002c5a0`
- `0x18003f5e8`
- `0x18003f9c0`
- `0x18003fd54`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003f69d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003f69d`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003f661`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003f661`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start__lambda_bd4ddfa317c149460230ee2d95f307a6___(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  __int64 v6; // rax
  _QWORD *v8; // [rsp+40h] [rbp+8h] BYREF

  v4 = operator new(0x30u);
  v5 = v4;
  *v4 = 0;
  if ( v4 != a2 )
  {
    *v4 = *a2;
    *a2 = 0;
  }
  std::string::string(v4 + 1, a2 + 1);
  Microsoft::WRL::ComPtr<ICDPResourceHandlerCallback>::ComPtr<ICDPResourceHandlerCallback>(v5 + 5, a2 + 5);
  v8 = v5;
  v6 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_bd4ddfa317c149460230ee2d95f307a6____0_,
         v5,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18003F6A3LL);
  }
  v8 = 0;
  return std::unique_ptr_std::tuple__lambda_6fb49a10711b8db59b2629181fe46722____std::default_delete_std::tuple__lambda_6fb49a10711b8db59b2629181fe46722_______::_unique_ptr_std::tuple__lambda_6fb49a10711b8db59b2629181fe46722____std::default_delete_std::tuple__lambda_6fb49a10711b8db59b2629181fe46722_______(&v8);
}

```

## disassembly

```asm
0x18003f5e8  mov     [rsp+arg_8], rbx
0x18003f5ed  mov     [rsp+arg_10], rsi
0x18003f5f2  push    rdi
0x18003f5f3  sub     rsp, 30h
0x18003f5f7  mov     rdi, rdx
0x18003f5fa  mov     rsi, rcx
0x18003f5fd  mov     ecx, 30h ; '0'; Size
0x18003f602  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f607  mov     rbx, rax
0x18003f60a  mov     qword ptr [rax], 0
0x18003f611  cmp     rax, rdi
0x18003f614  jz      short loc_18003F623
0x18003f616  mov     r8, [rdi]
0x18003f619  mov     [rax], r8
0x18003f61c  mov     qword ptr [rdi], 0
0x18003f623  lea     rdx, [rdi+8]
0x18003f627  lea     rcx, [rax+8]
0x18003f62b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x18003f630  lea     rdx, [rdi+28h]
0x18003f634  lea     rcx, [rbx+28h]
0x18003f638  call    ??0?$ComPtr@VICDPResourceHandlerCallback@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ICDPResourceHandlerCallback>::ComPtr<ICDPResourceHandlerCallback>(Microsoft::WRL::ComPtr<ICDPResourceHandlerCallback> &&)
0x18003f63d  mov     [rsp+38h+arg_0], rbx
0x18003f642  lea     rdi, [rsi+8]
0x18003f646  mov     [rsp+38h+var_10], rdi
0x18003f64b  mov     [rsp+38h+var_18], 0
0x18003f653  mov     r9, rbx
0x18003f656  lea     r8, std__thread___Invoke_std__tuple__lambda_bd4ddfa317c149460230ee2d95f307a6____0_
0x18003f65d  xor     edx, edx
0x18003f65f  xor     ecx, ecx
0x18003f661  call    cs:__imp__o__beginthreadex
0x18003f667  mov     [rsi], rax
0x18003f66a  test    rax, rax
0x18003f66d  jz      short loc_18003F692
0x18003f66f  mov     [rsp+38h+arg_0], 0
0x18003f678  lea     rcx, [rsp+38h+arg_0]
0x18003f67d  call    std__unique_ptr_std__tuple__lambda_6fb49a10711b8db59b2629181fe46722____std__default_delete_std__tuple__lambda_6fb49a10711b8db59b2629181fe46722__________unique_ptr_std__tuple__lambda_6fb49a10711b8db59b2629181fe46722____std__default_delete_std__tuple__lambda_6fb49a10711b8db59b2629181fe46722_______
0x18003f682  mov     rbx, [rsp+38h+arg_8]
0x18003f687  mov     rsi, [rsp+38h+arg_10]
0x18003f68c  add     rsp, 30h
0x18003f690  pop     rdi
0x18003f691  retn
0x18003f692  mov     dword ptr [rdi], 0
0x18003f698  mov     ecx, 6
0x18003f69d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
