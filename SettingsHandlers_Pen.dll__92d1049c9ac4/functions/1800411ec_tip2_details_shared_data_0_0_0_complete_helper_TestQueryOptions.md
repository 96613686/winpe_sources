# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1800411ec`
- end: `0x1800412ec`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ecbc`
- `0x18003f4f4`

## callees

- `0x1800030e0`
- `0x1800411ec`
- `0x1800416a8`
- `0x18004321c`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004125d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004125d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800412c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800412c8`

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
0x1800411ec  mov     [rsp+arg_10], rbx
0x1800411f1  push    rbp
0x1800411f2  push    rsi
0x1800411f3  push    rdi
0x1800411f4  sub     rsp, 70h
0x1800411f8  mov     rax, cs:__security_cookie
0x1800411ff  xor     rax, rsp
0x180041202  mov     [rsp+88h+var_28], rax
0x180041207  mov     edi, edx
0x180041209  mov     rbx, rcx
0x18004120c  xorps   xmm0, xmm0
0x18004120f  movups  [rsp+88h+var_58], xmm0
0x180041214  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180041219  movups  [rsp+88h+var_38], xmm0
0x18004121e  cmp     dword ptr [rcx+0E8h], 0
0x180041225  jbe     short loc_18004122A
0x180041227  or      edi, 8
0x18004122a  mov     esi, [rcx+0B8h]
0x180041230  mov     rbp, [rcx+0F0h]
0x180041237  mov     qword ptr [rcx+0F0h], 0
0x180041242  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180041249  test    rax, rax
0x18004124c  jnz     short loc_180041283
0x18004124e  call    tip_details_GetKernelBaseModuleHandle
0x180041253  mov     rcx, rax; hModule
0x180041256  lea     rdx, aTestquerydata; "TestQueryData"
0x18004125d  call    cs:__imp_GetProcAddress
0x180041263  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18004126a  test    rax, rax
0x18004126d  jnz     short loc_180041283
0x18004126f  xorps   xmm0, xmm0
0x180041272  movups  [rsp+88h+var_58], xmm0
0x180041277  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18004127c  movups  [rsp+88h+var_38], xmm0
0x180041281  jmp     short loc_1800412C3
0x180041283  lea     r9, [rsp+88h+var_58]
0x180041288  mov     r8d, esi
0x18004128b  mov     edx, edi
0x18004128d  mov     rcx, rbp
0x180041290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041295  test    eax, eax
0x180041297  jz      short loc_1800412C3
0x180041299  mov     rdx, [rsp+88h+pv]
0x18004129e  mov     rax, rdx
0x1800412a1  shr     rax, 20h
0x1800412a5  or      [rbx+40h], eax
0x1800412a8  cmp     [rsp+88h+pv+8], 0
0x1800412ae  jnz     short loc_1800412B6
0x1800412b0  mov     [rbx+0B8h], edx
0x1800412b6  mov     rdx, qword ptr [rsp+88h+var_38]
0x1800412bb  mov     rcx, rbx
0x1800412be  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x1800412c3  mov     rcx, [rsp+88h+pv+8]; pv
0x1800412c8  call    cs:__imp_CoTaskMemFree
0x1800412ce  nop
0x1800412cf  mov     rcx, [rsp+88h+var_28]
0x1800412d4  xor     rcx, rsp; StackCookie
0x1800412d7  call    __security_check_cookie
0x1800412dc  mov     rbx, [rsp+88h+arg_10]
0x1800412e4  add     rsp, 70h
0x1800412e8  pop     rdi
0x1800412e9  pop     rsi
0x1800412ea  pop     rbp
0x1800412eb  retn
```
