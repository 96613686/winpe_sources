# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1800d2214`
- end: `0x1800d2314`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039228`
- `0x180092544`

## callees

- `0x18008cf7c`
- `0x180095130`
- `0x1800d2214`
- `0x1800d24b4`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d2285`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d2285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d22f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d22f0`

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
0x1800d2214  mov     [rsp+arg_10], rbx
0x1800d2219  push    rbp
0x1800d221a  push    rsi
0x1800d221b  push    rdi
0x1800d221c  sub     rsp, 70h
0x1800d2220  mov     rax, cs:__security_cookie
0x1800d2227  xor     rax, rsp
0x1800d222a  mov     [rsp+88h+var_28], rax
0x1800d222f  mov     edi, edx
0x1800d2231  mov     rbx, rcx
0x1800d2234  xorps   xmm0, xmm0
0x1800d2237  movups  [rsp+88h+var_58], xmm0
0x1800d223c  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800d2241  movups  [rsp+88h+var_38], xmm0
0x1800d2246  cmp     dword ptr [rcx+0E8h], 0
0x1800d224d  jbe     short loc_1800D2252
0x1800d224f  or      edi, 8
0x1800d2252  mov     esi, [rcx+0B8h]
0x1800d2258  mov     rbp, [rcx+0F0h]
0x1800d225f  mov     qword ptr [rcx+0F0h], 0
0x1800d226a  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800d2271  test    rax, rax
0x1800d2274  jnz     short loc_1800D22AB
0x1800d2276  call    tip_details_GetKernelBaseModuleHandle
0x1800d227b  mov     rcx, rax; hModule
0x1800d227e  lea     rdx, aTestquerydata; "TestQueryData"
0x1800d2285  call    cs:__imp_GetProcAddress
0x1800d228b  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800d2292  test    rax, rax
0x1800d2295  jnz     short loc_1800D22AB
0x1800d2297  xorps   xmm0, xmm0
0x1800d229a  movups  [rsp+88h+var_58], xmm0
0x1800d229f  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800d22a4  movups  [rsp+88h+var_38], xmm0
0x1800d22a9  jmp     short loc_1800D22EB
0x1800d22ab  lea     r9, [rsp+88h+var_58]
0x1800d22b0  mov     r8d, esi
0x1800d22b3  mov     edx, edi
0x1800d22b5  mov     rcx, rbp
0x1800d22b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d22bd  test    eax, eax
0x1800d22bf  jz      short loc_1800D22EB
0x1800d22c1  mov     rdx, [rsp+88h+pv]
0x1800d22c6  mov     rax, rdx
0x1800d22c9  shr     rax, 20h
0x1800d22cd  or      [rbx+40h], eax
0x1800d22d0  cmp     [rsp+88h+pv+8], 0
0x1800d22d6  jnz     short loc_1800D22DE
0x1800d22d8  mov     [rbx+0B8h], edx
0x1800d22de  mov     rdx, qword ptr [rsp+88h+var_38]
0x1800d22e3  mov     rcx, rbx
0x1800d22e6  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x1800d22eb  mov     rcx, [rsp+88h+pv+8]; pv
0x1800d22f0  call    cs:__imp_CoTaskMemFree
0x1800d22f6  nop
0x1800d22f7  mov     rcx, [rsp+88h+var_28]
0x1800d22fc  xor     rcx, rsp; StackCookie
0x1800d22ff  call    __security_check_cookie
0x1800d2304  mov     rbx, [rsp+88h+arg_10]
0x1800d230c  add     rsp, 70h
0x1800d2310  pop     rdi
0x1800d2311  pop     rsi
0x1800d2312  pop     rbp
0x1800d2313  retn
```
