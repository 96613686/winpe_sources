# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1800176d0`
- end: `0x1800177d0`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800177d8`
- `0x180019668`

## callees

- `0x180002b20`
- `0x1800176d0`
- `0x180017eb8`
- `0x18001d36c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017741`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177ac`

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
0x1800176d0  mov     [rsp+arg_10], rbx
0x1800176d5  push    rbp
0x1800176d6  push    rsi
0x1800176d7  push    rdi
0x1800176d8  sub     rsp, 70h
0x1800176dc  mov     rax, cs:__security_cookie
0x1800176e3  xor     rax, rsp
0x1800176e6  mov     [rsp+88h+var_28], rax
0x1800176eb  mov     edi, edx
0x1800176ed  mov     rbx, rcx
0x1800176f0  xorps   xmm0, xmm0
0x1800176f3  movups  [rsp+88h+var_58], xmm0
0x1800176f8  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800176fd  movups  [rsp+88h+var_38], xmm0
0x180017702  cmp     dword ptr [rcx+0E8h], 0
0x180017709  jbe     short loc_18001770E
0x18001770b  or      edi, 8
0x18001770e  mov     esi, [rcx+0B8h]
0x180017714  mov     rbp, [rcx+0F0h]
0x18001771b  mov     qword ptr [rcx+0F0h], 0
0x180017726  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18001772d  test    rax, rax
0x180017730  jnz     short loc_180017767
0x180017732  call    tip_details_GetKernelBaseModuleHandle
0x180017737  mov     rcx, rax; hModule
0x18001773a  lea     rdx, aTestquerydata; "TestQueryData"
0x180017741  call    cs:__imp_GetProcAddress
0x180017747  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18001774e  test    rax, rax
0x180017751  jnz     short loc_180017767
0x180017753  xorps   xmm0, xmm0
0x180017756  movups  [rsp+88h+var_58], xmm0
0x18001775b  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180017760  movups  [rsp+88h+var_38], xmm0
0x180017765  jmp     short loc_1800177A7
0x180017767  lea     r9, [rsp+88h+var_58]
0x18001776c  mov     r8d, esi
0x18001776f  mov     edx, edi
0x180017771  mov     rcx, rbp
0x180017774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017779  test    eax, eax
0x18001777b  jz      short loc_1800177A7
0x18001777d  mov     rdx, [rsp+88h+pv]
0x180017782  mov     rax, rdx
0x180017785  shr     rax, 20h
0x180017789  or      [rbx+40h], eax
0x18001778c  cmp     [rsp+88h+pv+8], 0
0x180017792  jnz     short loc_18001779A
0x180017794  mov     [rbx+0B8h], edx
0x18001779a  mov     rdx, qword ptr [rsp+88h+var_38]
0x18001779f  mov     rcx, rbx
0x1800177a2  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x1800177a7  mov     rcx, [rsp+88h+pv+8]; pv
0x1800177ac  call    cs:__imp_CoTaskMemFree
0x1800177b2  nop
0x1800177b3  mov     rcx, [rsp+88h+var_28]
0x1800177b8  xor     rcx, rsp; StackCookie
0x1800177bb  call    __security_check_cookie
0x1800177c0  mov     rbx, [rsp+88h+arg_10]
0x1800177c8  add     rsp, 70h
0x1800177cc  pop     rdi
0x1800177cd  pop     rsi
0x1800177ce  pop     rbp
0x1800177cf  retn
```
