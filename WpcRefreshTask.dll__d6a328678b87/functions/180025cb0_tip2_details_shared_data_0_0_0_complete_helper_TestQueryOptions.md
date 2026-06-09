# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180025cb0`
- end: `0x180025dcb`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180020b8c`
- `0x180020c18`
- `0x1800221d4`
- `0x18002252c`
- `0x18007e778`
- `0x180081890`
- `0x18008191c`
- `0x1800819a8`
- `0x180082ad4`
- `0x180082bd8`

## callees

- `0x1800060a0`
- `0x180025cb0`
- `0x180026754`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025d3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025d3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025d25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025d25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025da7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025da7`

## string_xrefs

- `0x180025d1e`: `kernelbase.dll`

## pseudocode

```c
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
0x180025cb0  mov     [rsp+arg_10], rbx
0x180025cb5  push    rbp
0x180025cb6  push    rsi
0x180025cb7  push    rdi
0x180025cb8  sub     rsp, 70h
0x180025cbc  mov     rax, cs:__security_cookie
0x180025cc3  xor     rax, rsp
0x180025cc6  mov     [rsp+88h+var_28], rax
0x180025ccb  mov     edi, edx
0x180025ccd  mov     rbx, rcx
0x180025cd0  xorps   xmm0, xmm0
0x180025cd3  movups  [rsp+88h+var_58], xmm0
0x180025cd8  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180025cdd  movups  [rsp+88h+var_38], xmm0
0x180025ce2  cmp     dword ptr [rcx+0E8h], 0
0x180025ce9  jbe     short loc_180025CEE
0x180025ceb  or      edi, 8
0x180025cee  mov     esi, [rcx+0B8h]
0x180025cf4  mov     rbp, [rcx+0F0h]
0x180025cfb  mov     qword ptr [rcx+0F0h], 0
0x180025d06  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180025d0d  test    rax, rax
0x180025d10  jnz     short loc_180025D62
0x180025d12  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180025d19  test    rax, rax
0x180025d1c  jnz     short loc_180025D32
0x180025d1e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180025d25  call    cs:__imp_GetModuleHandleW
0x180025d2b  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180025d32  lea     rdx, aTestquerydata; "TestQueryData"
0x180025d39  mov     rcx, rax; hModule
0x180025d3c  call    cs:__imp_GetProcAddress
0x180025d42  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180025d49  test    rax, rax
0x180025d4c  jnz     short loc_180025D62
0x180025d4e  xorps   xmm0, xmm0
0x180025d51  movups  [rsp+88h+var_58], xmm0
0x180025d56  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180025d5b  movups  [rsp+88h+var_38], xmm0
0x180025d60  jmp     short loc_180025DA2
0x180025d62  lea     r9, [rsp+88h+var_58]
0x180025d67  mov     r8d, esi
0x180025d6a  mov     edx, edi
0x180025d6c  mov     rcx, rbp
0x180025d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d74  test    eax, eax
0x180025d76  jz      short loc_180025DA2
0x180025d78  mov     rdx, [rsp+88h+pv]
0x180025d7d  mov     rax, rdx
0x180025d80  shr     rax, 20h
0x180025d84  or      [rbx+40h], eax
0x180025d87  cmp     [rsp+88h+pv+8], 0
0x180025d8d  jnz     short loc_180025D95
0x180025d8f  mov     [rbx+0B8h], edx
0x180025d95  mov     rdx, qword ptr [rsp+88h+var_38]
0x180025d9a  mov     rcx, rbx
0x180025d9d  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x180025da2  mov     rcx, [rsp+88h+pv+8]; pv
0x180025da7  call    cs:__imp_CoTaskMemFree
0x180025dad  nop
0x180025dae  mov     rcx, [rsp+88h+var_28]
0x180025db3  xor     rcx, rsp; StackCookie
0x180025db6  call    __security_check_cookie
0x180025dbb  mov     rbx, [rsp+88h+arg_10]
0x180025dc3  add     rsp, 70h
0x180025dc7  pop     rdi
0x180025dc8  pop     rsi
0x180025dc9  pop     rbp
0x180025dca  retn
```
