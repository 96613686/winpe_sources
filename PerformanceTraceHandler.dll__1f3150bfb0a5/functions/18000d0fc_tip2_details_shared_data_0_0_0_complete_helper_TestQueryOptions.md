# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18000d0fc`
- end: `0x18000d1fc`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b49c`
- `0x180012e28`

## callees

- `0x180002c00`
- `0x18000d0fc`
- `0x18000d5ec`
- `0x18000eb28`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d16d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d16d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1d8`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // esi
  __int64 v5; // rbp
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
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
  if ( `TestQueryData'::`2'::s_pfnTestQueryData
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestQueryData"),
        (`TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress) != 0) )
  {
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
0x18000d0fc  mov     [rsp+arg_10], rbx
0x18000d101  push    rbp
0x18000d102  push    rsi
0x18000d103  push    rdi
0x18000d104  sub     rsp, 70h
0x18000d108  mov     rax, cs:__security_cookie
0x18000d10f  xor     rax, rsp
0x18000d112  mov     [rsp+88h+var_28], rax
0x18000d117  mov     edi, edx
0x18000d119  mov     rbx, rcx
0x18000d11c  xorps   xmm0, xmm0
0x18000d11f  movups  [rsp+88h+var_58], xmm0
0x18000d124  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18000d129  movups  [rsp+88h+var_38], xmm0
0x18000d12e  cmp     dword ptr [rcx+0E8h], 0
0x18000d135  jbe     short loc_18000D13A
0x18000d137  or      edi, 8
0x18000d13a  mov     esi, [rcx+0B8h]
0x18000d140  mov     rbp, [rcx+0F0h]
0x18000d147  mov     qword ptr [rcx+0F0h], 0
0x18000d152  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18000d159  test    rax, rax
0x18000d15c  jnz     short loc_18000D193
0x18000d15e  call    tip_details_GetKernelBaseModuleHandle
0x18000d163  mov     rcx, rax; hModule
0x18000d166  lea     rdx, aTestquerydata; "TestQueryData"
0x18000d16d  call    cs:__imp_GetProcAddress
0x18000d173  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18000d17a  test    rax, rax
0x18000d17d  jnz     short loc_18000D193
0x18000d17f  xorps   xmm0, xmm0
0x18000d182  movups  [rsp+88h+var_58], xmm0
0x18000d187  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18000d18c  movups  [rsp+88h+var_38], xmm0
0x18000d191  jmp     short loc_18000D1D3
0x18000d193  lea     r9, [rsp+88h+var_58]
0x18000d198  mov     r8d, esi
0x18000d19b  mov     edx, edi
0x18000d19d  mov     rcx, rbp
0x18000d1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1a5  test    eax, eax
0x18000d1a7  jz      short loc_18000D1D3
0x18000d1a9  mov     rdx, [rsp+88h+pv]
0x18000d1ae  mov     rax, rdx
0x18000d1b1  shr     rax, 20h
0x18000d1b5  or      [rbx+40h], eax
0x18000d1b8  cmp     [rsp+88h+pv+8], 0
0x18000d1be  jnz     short loc_18000D1C6
0x18000d1c0  mov     [rbx+0B8h], edx
0x18000d1c6  mov     rdx, qword ptr [rsp+88h+var_38]
0x18000d1cb  mov     rcx, rbx
0x18000d1ce  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18000d1d3  mov     rcx, [rsp+88h+pv+8]; pv
0x18000d1d8  call    cs:__imp_CoTaskMemFree
0x18000d1de  nop
0x18000d1df  mov     rcx, [rsp+88h+var_28]
0x18000d1e4  xor     rcx, rsp; StackCookie
0x18000d1e7  call    __security_check_cookie
0x18000d1ec  mov     rbx, [rsp+88h+arg_10]
0x18000d1f4  add     rsp, 70h
0x18000d1f8  pop     rdi
0x18000d1f9  pop     rsi
0x18000d1fa  pop     rbp
0x18000d1fb  retn
```
