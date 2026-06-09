# tip2::details::shared_data<1,0,1>::complete_helper(TestQueryOptions)

- ea: `0x180027e30`
- end: `0x180027f5a`
- name: `?complete_helper@?$shared_data@$00$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `298`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001359c`
- `0x180026a18`

## callees

- `0x180004ea0`
- `0x180027e30`
- `0x180028028`
- `0x1800284cc`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027ec1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027ec1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027eaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027eaa`
- `ole32!CoTaskMemFree` at `0x180027f32`
- `ole32!CoTaskMemFree` at `0x180027f32`

## string_xrefs

- `0x180027ea3`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,1>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // esi
  __int64 v5; // r14
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v8; // ecx
  __int128 v9; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-30h]
  __int128 v11; // [rsp+50h] [rbp-20h]

  v2 = a2;
  v9 = 0;
  *(_OWORD *)pv = 0;
  v11 = 0;
  if ( *(_DWORD *)(a1 + 232) )
    v2 = a2 | 8;
  v4 = *(_DWORD *)(a1 + 184);
  v5 = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a1 + 240) = 0;
  ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
  if ( `TestQueryData'::`2'::s_pfnTestQueryData )
    goto LABEL_16;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestQueryData");
  `TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_16:
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, __int128 *))ProcAddress)(v5, v2, v4, &v9) )
    {
      v8 = (int)pv[0];
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( pv[1] )
        tip2::details::shared_data<1,0,1>::deserialize_data(a1, &v9);
      else
        *(_DWORD *)(a1 + 184) = v8;
      tip2::details::shared_data<1,0,1>::evaluate_and_report(a1, v11);
    }
  }
  else
  {
    v9 = 0;
    *(_OWORD *)pv = 0;
    v11 = 0;
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x180027e30  mov     [rsp-18h+arg_10], rbx
0x180027e35  mov     [rsp-18h+arg_18], rsi
0x180027e3a  push    rbp
0x180027e3b  push    rdi
0x180027e3c  push    r14
0x180027e3e  mov     rbp, rsp
0x180027e41  sub     rsp, 70h
0x180027e45  mov     rax, cs:__security_cookie
0x180027e4c  xor     rax, rsp
0x180027e4f  mov     [rbp+var_10], rax
0x180027e53  mov     edi, edx
0x180027e55  mov     rbx, rcx
0x180027e58  xorps   xmm0, xmm0
0x180027e5b  movups  [rbp+var_40], xmm0
0x180027e5f  movups  xmmword ptr [rbp+pv], xmm0
0x180027e63  movups  [rbp+var_20], xmm0
0x180027e67  cmp     dword ptr [rcx+0E8h], 0
0x180027e6e  jbe     short loc_180027E73
0x180027e70  or      edi, 8
0x180027e73  mov     esi, [rcx+0B8h]
0x180027e79  mov     r14, [rcx+0F0h]
0x180027e80  mov     qword ptr [rcx+0F0h], 0
0x180027e8b  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180027e92  test    rax, rax
0x180027e95  jnz     short loc_180027EE4
0x180027e97  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180027e9e  test    rax, rax
0x180027ea1  jnz     short loc_180027EB7
0x180027ea3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180027eaa  call    cs:__imp_GetModuleHandleW
0x180027eb0  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180027eb7  lea     rdx, aTestquerydata; "TestQueryData"
0x180027ebe  mov     rcx, rax; hModule
0x180027ec1  call    cs:__imp_GetProcAddress
0x180027ec7  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180027ece  test    rax, rax
0x180027ed1  jnz     short loc_180027EE4
0x180027ed3  xorps   xmm0, xmm0
0x180027ed6  movups  [rbp+var_40], xmm0
0x180027eda  movups  xmmword ptr [rbp+pv], xmm0
0x180027ede  movups  [rbp+var_20], xmm0
0x180027ee2  jmp     short loc_180027F2E
0x180027ee4  lea     r9, [rbp+var_40]
0x180027ee8  mov     r8d, esi
0x180027eeb  mov     edx, edi
0x180027eed  mov     rcx, r14
0x180027ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ef5  test    eax, eax
0x180027ef7  jz      short loc_180027F2E
0x180027ef9  mov     rcx, [rbp+pv]
0x180027efd  mov     rax, rcx
0x180027f00  shr     rax, 20h
0x180027f04  or      [rbx+40h], eax
0x180027f07  cmp     [rbp+pv+8], 0
0x180027f0c  jz      short loc_180027F1C
0x180027f0e  lea     rdx, [rbp+var_40]
0x180027f12  mov     rcx, rbx
0x180027f15  call    ?deserialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,1>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180027f1a  jmp     short loc_180027F22
0x180027f1c  mov     [rbx+0B8h], ecx
0x180027f22  mov     rdx, qword ptr [rbp+var_20]
0x180027f26  mov     rcx, rbx
0x180027f29  call    ?evaluate_and_report@?$shared_data@$00$0A@$00@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,1>::evaluate_and_report(__int64)
0x180027f2e  mov     rcx, [rbp+pv+8]; pv
0x180027f32  call    cs:__imp_CoTaskMemFree
0x180027f38  nop
0x180027f39  mov     rcx, [rbp+var_10]
0x180027f3d  xor     rcx, rsp; StackCookie
0x180027f40  call    __security_check_cookie
0x180027f45  lea     r11, [rsp+70h+var_s0]
0x180027f4a  mov     rbx, [r11+30h]
0x180027f4e  mov     rsi, [r11+38h]
0x180027f52  mov     rsp, r11
0x180027f55  pop     r14
0x180027f57  pop     rdi
0x180027f58  pop     rbp
0x180027f59  retn
```
