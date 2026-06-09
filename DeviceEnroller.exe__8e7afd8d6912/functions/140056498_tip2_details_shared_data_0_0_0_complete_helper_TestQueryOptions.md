# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x140056498`
- end: `0x1400565b3`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140052c80`
- `0x140052fc0`

## callees

- `0x1400042f0`
- `0x140056498`
- `0x1400569b0`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140056524`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140056524`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005650d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005650d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005658f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005658f`

## string_xrefs

- `0x140056506`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // esi
  __int64 v5; // rbp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v8; // edx
  __int128 v9; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-48h]
  __int128 v11; // [rsp+50h] [rbp-38h]

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
    goto LABEL_15;
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
LABEL_15:
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, __int128 *))ProcAddress)(v5, v2, v4, &v9) )
    {
      v8 = (int)pv[0];
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( !pv[1] )
        *(_DWORD *)(a1 + 184) = v8;
      tip2::details::shared_data<0,0,0>::evaluate_and_report(a1, v11);
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
0x140056498  mov     [rsp+arg_10], rbx
0x14005649d  push    rbp
0x14005649e  push    rsi
0x14005649f  push    rdi
0x1400564a0  sub     rsp, 70h
0x1400564a4  mov     rax, cs:__security_cookie
0x1400564ab  xor     rax, rsp
0x1400564ae  mov     [rsp+88h+var_28], rax
0x1400564b3  mov     edi, edx
0x1400564b5  mov     rbx, rcx
0x1400564b8  xorps   xmm0, xmm0
0x1400564bb  movups  [rsp+88h+var_58], xmm0
0x1400564c0  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1400564c5  movups  [rsp+88h+var_38], xmm0
0x1400564ca  cmp     dword ptr [rcx+0E8h], 0
0x1400564d1  jbe     short loc_1400564D6
0x1400564d3  or      edi, 8
0x1400564d6  mov     esi, [rcx+0B8h]
0x1400564dc  mov     rbp, [rcx+0F0h]
0x1400564e3  mov     qword ptr [rcx+0F0h], 0
0x1400564ee  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1400564f5  test    rax, rax
0x1400564f8  jnz     short loc_14005654A
0x1400564fa  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x140056501  test    rax, rax
0x140056504  jnz     short loc_14005651A
0x140056506  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14005650d  call    cs:__imp_GetModuleHandleW
0x140056513  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14005651a  lea     rdx, aTestquerydata; "TestQueryData"
0x140056521  mov     rcx, rax; hModule
0x140056524  call    cs:__imp_GetProcAddress
0x14005652a  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x140056531  test    rax, rax
0x140056534  jnz     short loc_14005654A
0x140056536  xorps   xmm0, xmm0
0x140056539  movups  [rsp+88h+var_58], xmm0
0x14005653e  movups  xmmword ptr [rsp+88h+pv], xmm0
0x140056543  movups  [rsp+88h+var_38], xmm0
0x140056548  jmp     short loc_14005658A
0x14005654a  lea     r9, [rsp+88h+var_58]
0x14005654f  mov     r8d, esi
0x140056552  mov     edx, edi
0x140056554  mov     rcx, rbp
0x140056557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005655c  test    eax, eax
0x14005655e  jz      short loc_14005658A
0x140056560  mov     rdx, [rsp+88h+pv]
0x140056565  mov     rax, rdx
0x140056568  shr     rax, 20h
0x14005656c  or      [rbx+40h], eax
0x14005656f  cmp     [rsp+88h+pv+8], 0
0x140056575  jnz     short loc_14005657D
0x140056577  mov     [rbx+0B8h], edx
0x14005657d  mov     rdx, qword ptr [rsp+88h+var_38]
0x140056582  mov     rcx, rbx
0x140056585  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x14005658a  mov     rcx, [rsp+88h+pv+8]; pv
0x14005658f  call    cs:__imp_CoTaskMemFree
0x140056595  nop
0x140056596  mov     rcx, [rsp+88h+var_28]
0x14005659b  xor     rcx, rsp; StackCookie
0x14005659e  call    __security_check_cookie
0x1400565a3  mov     rbx, [rsp+88h+arg_10]
0x1400565ab  add     rsp, 70h
0x1400565af  pop     rdi
0x1400565b0  pop     rsi
0x1400565b1  pop     rbp
0x1400565b2  retn
```
