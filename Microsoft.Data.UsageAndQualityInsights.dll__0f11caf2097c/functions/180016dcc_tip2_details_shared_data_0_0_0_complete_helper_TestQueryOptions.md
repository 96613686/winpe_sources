# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180016dcc`
- end: `0x180016ee7`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013bbc`
- `0x180013c48`
- `0x180014c40`
- `0x180015930`
- `0x18001b234`
- `0x18001c060`
- `0x18001c64c`
- `0x18001d95c`
- `0x18002b6a8`
- `0x1800366f4`
- `0x18004368c`
- `0x180046cf0`
- `0x18004c184`
- `0x1800e6bb8`
- `0x1800e75bc`
- `0x1800f4eb4`

## callees

- `0x1800033d0`
- `0x180016dcc`
- `0x1800172e4`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016e41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016e41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016e58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016e58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ec3`

## string_xrefs

- `0x180016e3a`: `kernelbase.dll`

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
0x180016dcc  mov     [rsp+arg_10], rbx
0x180016dd1  push    rbp
0x180016dd2  push    rsi
0x180016dd3  push    rdi
0x180016dd4  sub     rsp, 70h
0x180016dd8  mov     rax, cs:__security_cookie
0x180016ddf  xor     rax, rsp
0x180016de2  mov     [rsp+88h+var_28], rax
0x180016de7  mov     edi, edx
0x180016de9  mov     rbx, rcx
0x180016dec  xorps   xmm0, xmm0
0x180016def  movups  [rsp+88h+var_58], xmm0
0x180016df4  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180016df9  movups  [rsp+88h+var_38], xmm0
0x180016dfe  cmp     dword ptr [rcx+0E8h], 0
0x180016e05  jbe     short loc_180016E0A
0x180016e07  or      edi, 8
0x180016e0a  mov     esi, [rcx+0B8h]
0x180016e10  mov     rbp, [rcx+0F0h]
0x180016e17  mov     qword ptr [rcx+0F0h], 0
0x180016e22  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180016e29  test    rax, rax
0x180016e2c  jnz     short loc_180016E7E
0x180016e2e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180016e35  test    rax, rax
0x180016e38  jnz     short loc_180016E4E
0x180016e3a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180016e41  call    cs:__imp_GetModuleHandleW
0x180016e47  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180016e4e  lea     rdx, aTestquerydata; "TestQueryData"
0x180016e55  mov     rcx, rax; hModule
0x180016e58  call    cs:__imp_GetProcAddress
0x180016e5e  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180016e65  test    rax, rax
0x180016e68  jnz     short loc_180016E7E
0x180016e6a  xorps   xmm0, xmm0
0x180016e6d  movups  [rsp+88h+var_58], xmm0
0x180016e72  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180016e77  movups  [rsp+88h+var_38], xmm0
0x180016e7c  jmp     short loc_180016EBE
0x180016e7e  lea     r9, [rsp+88h+var_58]
0x180016e83  mov     r8d, esi
0x180016e86  mov     edx, edi
0x180016e88  mov     rcx, rbp
0x180016e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e90  test    eax, eax
0x180016e92  jz      short loc_180016EBE
0x180016e94  mov     rdx, [rsp+88h+pv]
0x180016e99  mov     rax, rdx
0x180016e9c  shr     rax, 20h
0x180016ea0  or      [rbx+40h], eax
0x180016ea3  cmp     [rsp+88h+pv+8], 0
0x180016ea9  jnz     short loc_180016EB1
0x180016eab  mov     [rbx+0B8h], edx
0x180016eb1  mov     rdx, qword ptr [rsp+88h+var_38]
0x180016eb6  mov     rcx, rbx
0x180016eb9  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x180016ebe  mov     rcx, [rsp+88h+pv+8]; pv
0x180016ec3  call    cs:__imp_CoTaskMemFree
0x180016ec9  nop
0x180016eca  mov     rcx, [rsp+88h+var_28]
0x180016ecf  xor     rcx, rsp; StackCookie
0x180016ed2  call    __security_check_cookie
0x180016ed7  mov     rbx, [rsp+88h+arg_10]
0x180016edf  add     rsp, 70h
0x180016ee3  pop     rdi
0x180016ee4  pop     rsi
0x180016ee5  pop     rbp
0x180016ee6  retn
```
