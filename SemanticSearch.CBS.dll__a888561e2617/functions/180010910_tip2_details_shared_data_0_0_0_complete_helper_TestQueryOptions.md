# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180010910`
- end: `0x180010a20`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `272`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `12`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a710`
- `0x18000afa0`
- `0x18000b2a0`
- `0x18000fc60`
- `0x18001a180`
- `0x18001bcf0`
- `0x180033f70`
- `0x180034400`
- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`

## callees

- `0x180010910`
- `0x1800112a0`
- `0x18004c070`
- `0x18005e260`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180010990`
- `KERNEL32!GetProcAddress` at `0x180010990`
- `KERNEL32!GetModuleHandleW` at `0x180010979`
- `KERNEL32!GetModuleHandleW` at `0x180010979`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800109fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800109fc`

## string_xrefs

- `0x180010972`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v4; // esi
  __int64 v5; // rbp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v8; // edx
  __int128 v9; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-48h]
  __int128 v11; // [rsp+50h] [rbp-38h]

  v9 = 0;
  *(_OWORD *)pv = 0;
  v11 = 0;
  v4 = *(_DWORD *)(a1 + 184);
  v5 = *(_QWORD *)(a1 + 232);
  *(_QWORD *)(a1 + 232) = 0;
  ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
  if ( `TestQueryData'::`2'::s_pfnTestQueryData )
    goto LABEL_13;
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
LABEL_13:
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, __int128 *))ProcAddress)(v5, a2, v4, &v9) )
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
0x180010910  mov     [rsp+arg_10], rbx
0x180010915  push    rbp
0x180010916  push    rsi
0x180010917  push    rdi
0x180010918  sub     rsp, 70h
0x18001091c  mov     rax, cs:__security_cookie
0x180010923  xor     rax, rsp
0x180010926  mov     [rsp+88h+var_28], rax
0x18001092b  mov     edi, edx
0x18001092d  mov     rbx, rcx
0x180010930  xorps   xmm0, xmm0
0x180010933  movups  [rsp+88h+var_58], xmm0
0x180010938  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18001093d  movups  [rsp+88h+var_38], xmm0
0x180010942  mov     esi, [rcx+0B8h]
0x180010948  mov     rbp, [rcx+0E8h]
0x18001094f  mov     qword ptr [rcx+0E8h], 0
0x18001095a  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180010961  test    rax, rax
0x180010964  jnz     short loc_1800109B6
0x180010966  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001096d  test    rax, rax
0x180010970  jnz     short loc_180010986
0x180010972  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180010979  call    cs:__imp_GetModuleHandleW
0x18001097f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180010986  lea     rdx, aTestquerydata; "TestQueryData"
0x18001098d  mov     rcx, rax; hModule
0x180010990  call    cs:__imp_GetProcAddress
0x180010996  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18001099d  test    rax, rax
0x1800109a0  jnz     short loc_1800109B6
0x1800109a2  xorps   xmm0, xmm0
0x1800109a5  movups  [rsp+88h+var_58], xmm0
0x1800109aa  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800109af  movups  [rsp+88h+var_38], xmm0
0x1800109b4  jmp     short loc_1800109F7
0x1800109b6  lea     r9, [rsp+88h+var_58]
0x1800109bb  mov     r8d, esi
0x1800109be  mov     edx, edi
0x1800109c0  mov     rcx, rbp
0x1800109c3  call    cs:__guard_dispatch_icall_fptr
0x1800109c9  test    eax, eax
0x1800109cb  jz      short loc_1800109F7
0x1800109cd  mov     rdx, [rsp+88h+pv]
0x1800109d2  mov     rax, rdx
0x1800109d5  shr     rax, 20h
0x1800109d9  or      [rbx+40h], eax
0x1800109dc  cmp     [rsp+88h+pv+8], 0
0x1800109e2  jnz     short loc_1800109EA
0x1800109e4  mov     [rbx+0B8h], edx
0x1800109ea  mov     rdx, qword ptr [rsp+88h+var_38]
0x1800109ef  mov     rcx, rbx
0x1800109f2  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x1800109f7  mov     rcx, [rsp+88h+pv+8]; pv
0x1800109fc  call    cs:__imp_CoTaskMemFree
0x180010a02  nop
0x180010a03  mov     rcx, [rsp+88h+var_28]
0x180010a08  xor     rcx, rsp; StackCookie
0x180010a0b  call    __security_check_cookie
0x180010a10  mov     rbx, [rsp+88h+arg_10]
0x180010a18  add     rsp, 70h
0x180010a1c  pop     rdi
0x180010a1d  pop     rsi
0x180010a1e  pop     rbp
0x180010a1f  retn
```
