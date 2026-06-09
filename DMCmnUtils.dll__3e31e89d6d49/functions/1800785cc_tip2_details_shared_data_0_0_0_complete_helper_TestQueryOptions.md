# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1800785cc`
- end: `0x1800786d9`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800749b4`
- `0x1800759c0`

## callees

- `0x180007270`
- `0x1800785cc`
- `0x180078c24`
- `0x18007a2fc`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007863d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007863d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800786ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800786ae`

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
0x1800785cc  mov     [rsp+arg_10], rbx
0x1800785d1  push    rbp
0x1800785d2  push    rsi
0x1800785d3  push    rdi
0x1800785d4  sub     rsp, 70h
0x1800785d8  mov     rax, cs:__security_cookie
0x1800785df  xor     rax, rsp
0x1800785e2  mov     [rsp+88h+var_28], rax
0x1800785e7  mov     edi, edx
0x1800785e9  mov     rbx, rcx
0x1800785ec  xorps   xmm0, xmm0
0x1800785ef  movups  [rsp+88h+var_58], xmm0
0x1800785f4  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800785f9  movups  [rsp+88h+var_38], xmm0
0x1800785fe  cmp     dword ptr [rcx+0E8h], 0
0x180078605  jbe     short loc_18007860A
0x180078607  or      edi, 8
0x18007860a  mov     esi, [rcx+0B8h]
0x180078610  mov     rbp, [rcx+0F0h]
0x180078617  mov     qword ptr [rcx+0F0h], 0
0x180078622  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180078629  test    rax, rax
0x18007862c  jnz     short loc_180078669
0x18007862e  call    tip_details_GetKernelBaseModuleHandle
0x180078633  mov     rcx, rax; hModule
0x180078636  lea     rdx, aTestquerydata; "TestQueryData"
0x18007863d  call    cs:__imp_GetProcAddress
0x180078644  nop     dword ptr [rax+rax+00h]
0x180078649  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180078650  test    rax, rax
0x180078653  jnz     short loc_180078669
0x180078655  xorps   xmm0, xmm0
0x180078658  movups  [rsp+88h+var_58], xmm0
0x18007865d  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180078662  movups  [rsp+88h+var_38], xmm0
0x180078667  jmp     short loc_1800786A9
0x180078669  lea     r9, [rsp+88h+var_58]
0x18007866e  mov     r8d, esi
0x180078671  mov     edx, edi
0x180078673  mov     rcx, rbp
0x180078676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007867b  test    eax, eax
0x18007867d  jz      short loc_1800786A9
0x18007867f  mov     rdx, [rsp+88h+pv]
0x180078684  mov     rax, rdx
0x180078687  shr     rax, 20h
0x18007868b  or      [rbx+40h], eax
0x18007868e  cmp     [rsp+88h+pv+8], 0
0x180078694  jnz     short loc_18007869C
0x180078696  mov     [rbx+0B8h], edx
0x18007869c  mov     rdx, qword ptr [rsp+88h+var_38]
0x1800786a1  mov     rcx, rbx
0x1800786a4  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x1800786a9  mov     rcx, [rsp+88h+pv+8]; pv
0x1800786ae  call    cs:__imp_CoTaskMemFree
0x1800786b5  nop     dword ptr [rax+rax+00h]
0x1800786ba  nop
0x1800786bb  mov     rcx, [rsp+88h+var_28]
0x1800786c0  xor     rcx, rsp; StackCookie
0x1800786c3  call    __security_check_cookie
0x1800786c8  mov     rbx, [rsp+88h+arg_10]
0x1800786d0  add     rsp, 70h
0x1800786d4  pop     rdi
0x1800786d5  pop     rsi
0x1800786d6  pop     rbp
0x1800786d7  retn
```
