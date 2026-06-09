# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18002189c`
- end: `0x1800219b7`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800139c8`
- `0x180013a54`
- `0x180013ae0`
- `0x180013b6c`
- `0x18001438c`
- `0x18001448c`
- `0x18001b7fc`
- `0x18001f1c4`
- `0x18001f604`
- `0x18001f998`
- `0x18001fd50`
- `0x180027bf4`
- `0x180027c80`
- `0x180027d0c`
- `0x180027d98`
- `0x180028844`
- `0x18002bc5c`
- `0x18002bf50`
- `0x18002d050`

## callees

- `0x180002590`
- `0x18002189c`
- `0x18002275c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021911`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021911`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021928`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021928`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021993`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021993`

## string_xrefs

- `0x18002190a`: `kernelbase.dll`

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
0x18002189c  mov     [rsp+arg_10], rbx
0x1800218a1  push    rbp
0x1800218a2  push    rsi
0x1800218a3  push    rdi
0x1800218a4  sub     rsp, 70h
0x1800218a8  mov     rax, cs:__security_cookie
0x1800218af  xor     rax, rsp
0x1800218b2  mov     [rsp+88h+var_28], rax
0x1800218b7  mov     edi, edx
0x1800218b9  mov     rbx, rcx
0x1800218bc  xorps   xmm0, xmm0
0x1800218bf  movups  [rsp+88h+var_58], xmm0
0x1800218c4  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800218c9  movups  [rsp+88h+var_38], xmm0
0x1800218ce  cmp     dword ptr [rcx+0E8h], 0
0x1800218d5  jbe     short loc_1800218DA
0x1800218d7  or      edi, 8
0x1800218da  mov     esi, [rcx+0B8h]
0x1800218e0  mov     rbp, [rcx+0F0h]
0x1800218e7  mov     qword ptr [rcx+0F0h], 0
0x1800218f2  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800218f9  test    rax, rax
0x1800218fc  jnz     short loc_18002194E
0x1800218fe  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180021905  test    rax, rax
0x180021908  jnz     short loc_18002191E
0x18002190a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180021911  call    cs:__imp_GetModuleHandleW
0x180021917  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002191e  lea     rdx, aTestquerydata; "TestQueryData"
0x180021925  mov     rcx, rax; hModule
0x180021928  call    cs:__imp_GetProcAddress
0x18002192e  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180021935  test    rax, rax
0x180021938  jnz     short loc_18002194E
0x18002193a  xorps   xmm0, xmm0
0x18002193d  movups  [rsp+88h+var_58], xmm0
0x180021942  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180021947  movups  [rsp+88h+var_38], xmm0
0x18002194c  jmp     short loc_18002198E
0x18002194e  lea     r9, [rsp+88h+var_58]
0x180021953  mov     r8d, esi
0x180021956  mov     edx, edi
0x180021958  mov     rcx, rbp
0x18002195b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021960  test    eax, eax
0x180021962  jz      short loc_18002198E
0x180021964  mov     rdx, [rsp+88h+pv]
0x180021969  mov     rax, rdx
0x18002196c  shr     rax, 20h
0x180021970  or      [rbx+40h], eax
0x180021973  cmp     [rsp+88h+pv+8], 0
0x180021979  jnz     short loc_180021981
0x18002197b  mov     [rbx+0B8h], edx
0x180021981  mov     rdx, qword ptr [rsp+88h+var_38]
0x180021986  mov     rcx, rbx
0x180021989  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18002198e  mov     rcx, [rsp+88h+pv+8]; pv
0x180021993  call    cs:__imp_CoTaskMemFree
0x180021999  nop
0x18002199a  mov     rcx, [rsp+88h+var_28]
0x18002199f  xor     rcx, rsp; StackCookie
0x1800219a2  call    __security_check_cookie
0x1800219a7  mov     rbx, [rsp+88h+arg_10]
0x1800219af  add     rsp, 70h
0x1800219b3  pop     rdi
0x1800219b4  pop     rsi
0x1800219b5  pop     rbp
0x1800219b6  retn
```
