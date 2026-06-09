# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180021d70`
- end: `0x180021e70`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001851c`
- `0x180021d14`

## callees

- `0x180016410`
- `0x180021d70`
- `0x180026fac`
- `0x180037780`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021de1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021de1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021e4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021e4c`

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
0x180021d70  mov     [rsp+arg_10], rbx
0x180021d75  push    rbp
0x180021d76  push    rsi
0x180021d77  push    rdi
0x180021d78  sub     rsp, 70h
0x180021d7c  mov     rax, cs:__security_cookie
0x180021d83  xor     rax, rsp
0x180021d86  mov     [rsp+88h+var_28], rax
0x180021d8b  mov     edi, edx
0x180021d8d  mov     rbx, rcx
0x180021d90  xorps   xmm0, xmm0
0x180021d93  movups  [rsp+88h+var_58], xmm0
0x180021d98  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180021d9d  movups  [rsp+88h+var_38], xmm0
0x180021da2  cmp     dword ptr [rcx+0E8h], 0
0x180021da9  jbe     short loc_180021DAE
0x180021dab  or      edi, 8
0x180021dae  mov     esi, [rcx+0B8h]
0x180021db4  mov     rbp, [rcx+0F0h]
0x180021dbb  mov     qword ptr [rcx+0F0h], 0
0x180021dc6  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180021dcd  test    rax, rax
0x180021dd0  jnz     short loc_180021E07
0x180021dd2  call    tip_details_GetKernelBaseModuleHandle
0x180021dd7  mov     rcx, rax; hModule
0x180021dda  lea     rdx, aTestquerydata; "TestQueryData"
0x180021de1  call    cs:__imp_GetProcAddress
0x180021de7  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180021dee  test    rax, rax
0x180021df1  jnz     short loc_180021E07
0x180021df3  xorps   xmm0, xmm0
0x180021df6  movups  [rsp+88h+var_58], xmm0
0x180021dfb  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180021e00  movups  [rsp+88h+var_38], xmm0
0x180021e05  jmp     short loc_180021E47
0x180021e07  lea     r9, [rsp+88h+var_58]
0x180021e0c  mov     r8d, esi
0x180021e0f  mov     edx, edi
0x180021e11  mov     rcx, rbp
0x180021e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e19  test    eax, eax
0x180021e1b  jz      short loc_180021E47
0x180021e1d  mov     rdx, [rsp+88h+pv]
0x180021e22  mov     rax, rdx
0x180021e25  shr     rax, 20h
0x180021e29  or      [rbx+40h], eax
0x180021e2c  cmp     [rsp+88h+pv+8], 0
0x180021e32  jnz     short loc_180021E3A
0x180021e34  mov     [rbx+0B8h], edx
0x180021e3a  mov     rdx, qword ptr [rsp+88h+var_38]
0x180021e3f  mov     rcx, rbx
0x180021e42  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x180021e47  mov     rcx, [rsp+88h+pv+8]; pv
0x180021e4c  call    cs:__imp_CoTaskMemFree
0x180021e52  nop
0x180021e53  mov     rcx, [rsp+88h+var_28]
0x180021e58  xor     rcx, rsp; StackCookie
0x180021e5b  call    __security_check_cookie
0x180021e60  mov     rbx, [rsp+88h+arg_10]
0x180021e68  add     rsp, 70h
0x180021e6c  pop     rdi
0x180021e6d  pop     rsi
0x180021e6e  pop     rbp
0x180021e6f  retn
```
