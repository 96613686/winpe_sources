# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180026128`
- end: `0x180026243`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a0ac`
- `0x180025460`

## callees

- `0x180002240`
- `0x180026128`
- `0x180026494`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800261b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800261b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002619d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002619d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002621f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002621f`

## string_xrefs

- `0x180026196`: `kernelbase.dll`

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
0x180026128  mov     [rsp+arg_10], rbx
0x18002612d  push    rbp
0x18002612e  push    rsi
0x18002612f  push    rdi
0x180026130  sub     rsp, 70h
0x180026134  mov     rax, cs:__security_cookie
0x18002613b  xor     rax, rsp
0x18002613e  mov     [rsp+88h+var_28], rax
0x180026143  mov     edi, edx
0x180026145  mov     rbx, rcx
0x180026148  xorps   xmm0, xmm0
0x18002614b  movups  [rsp+88h+var_58], xmm0
0x180026150  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180026155  movups  [rsp+88h+var_38], xmm0
0x18002615a  cmp     dword ptr [rcx+0E8h], 0
0x180026161  jbe     short loc_180026166
0x180026163  or      edi, 8
0x180026166  mov     esi, [rcx+0B8h]
0x18002616c  mov     rbp, [rcx+0F0h]
0x180026173  mov     qword ptr [rcx+0F0h], 0
0x18002617e  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180026185  test    rax, rax
0x180026188  jnz     short loc_1800261DA
0x18002618a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180026191  test    rax, rax
0x180026194  jnz     short loc_1800261AA
0x180026196  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002619d  call    cs:__imp_GetModuleHandleW
0x1800261a3  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800261aa  lea     rdx, aTestquerydata; "TestQueryData"
0x1800261b1  mov     rcx, rax; hModule
0x1800261b4  call    cs:__imp_GetProcAddress
0x1800261ba  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800261c1  test    rax, rax
0x1800261c4  jnz     short loc_1800261DA
0x1800261c6  xorps   xmm0, xmm0
0x1800261c9  movups  [rsp+88h+var_58], xmm0
0x1800261ce  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800261d3  movups  [rsp+88h+var_38], xmm0
0x1800261d8  jmp     short loc_18002621A
0x1800261da  lea     r9, [rsp+88h+var_58]
0x1800261df  mov     r8d, esi
0x1800261e2  mov     edx, edi
0x1800261e4  mov     rcx, rbp
0x1800261e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261ec  test    eax, eax
0x1800261ee  jz      short loc_18002621A
0x1800261f0  mov     rdx, [rsp+88h+pv]
0x1800261f5  mov     rax, rdx
0x1800261f8  shr     rax, 20h
0x1800261fc  or      [rbx+40h], eax
0x1800261ff  cmp     [rsp+88h+pv+8], 0
0x180026205  jnz     short loc_18002620D
0x180026207  mov     [rbx+0B8h], edx
0x18002620d  mov     rdx, qword ptr [rsp+88h+var_38]
0x180026212  mov     rcx, rbx
0x180026215  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18002621a  mov     rcx, [rsp+88h+pv+8]; pv
0x18002621f  call    cs:__imp_CoTaskMemFree
0x180026225  nop
0x180026226  mov     rcx, [rsp+88h+var_28]
0x18002622b  xor     rcx, rsp; StackCookie
0x18002622e  call    __security_check_cookie
0x180026233  mov     rbx, [rsp+88h+arg_10]
0x18002623b  add     rsp, 70h
0x18002623f  pop     rdi
0x180026240  pop     rsi
0x180026241  pop     rbp
0x180026242  retn
```
