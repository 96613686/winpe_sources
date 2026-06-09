# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18001aa38`
- end: `0x18001ab38`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001aa0c`
- `0x18001b6a0`

## callees

- `0x180003c20`
- `0x18001aa38`
- `0x18001afd8`
- `0x18001d3e4`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001aaa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001aaa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ab14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ab14`

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
0x18001aa38  mov     [rsp+arg_10], rbx
0x18001aa3d  push    rbp
0x18001aa3e  push    rsi
0x18001aa3f  push    rdi
0x18001aa40  sub     rsp, 70h
0x18001aa44  mov     rax, cs:__security_cookie
0x18001aa4b  xor     rax, rsp
0x18001aa4e  mov     [rsp+88h+var_28], rax
0x18001aa53  mov     edi, edx
0x18001aa55  mov     rbx, rcx
0x18001aa58  xorps   xmm0, xmm0
0x18001aa5b  movups  [rsp+88h+var_58], xmm0
0x18001aa60  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18001aa65  movups  [rsp+88h+var_38], xmm0
0x18001aa6a  cmp     dword ptr [rcx+0E8h], 0
0x18001aa71  jbe     short loc_18001AA76
0x18001aa73  or      edi, 8
0x18001aa76  mov     esi, [rcx+0B8h]
0x18001aa7c  mov     rbp, [rcx+0F0h]
0x18001aa83  mov     qword ptr [rcx+0F0h], 0
0x18001aa8e  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18001aa95  test    rax, rax
0x18001aa98  jnz     short loc_18001AACF
0x18001aa9a  call    tip_details_GetKernelBaseModuleHandle
0x18001aa9f  mov     rcx, rax; hModule
0x18001aaa2  lea     rdx, aTestquerydata; "TestQueryData"
0x18001aaa9  call    cs:__imp_GetProcAddress
0x18001aaaf  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18001aab6  test    rax, rax
0x18001aab9  jnz     short loc_18001AACF
0x18001aabb  xorps   xmm0, xmm0
0x18001aabe  movups  [rsp+88h+var_58], xmm0
0x18001aac3  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18001aac8  movups  [rsp+88h+var_38], xmm0
0x18001aacd  jmp     short loc_18001AB0F
0x18001aacf  lea     r9, [rsp+88h+var_58]
0x18001aad4  mov     r8d, esi
0x18001aad7  mov     edx, edi
0x18001aad9  mov     rcx, rbp
0x18001aadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aae1  test    eax, eax
0x18001aae3  jz      short loc_18001AB0F
0x18001aae5  mov     rdx, [rsp+88h+pv]
0x18001aaea  mov     rax, rdx
0x18001aaed  shr     rax, 20h
0x18001aaf1  or      [rbx+40h], eax
0x18001aaf4  cmp     [rsp+88h+pv+8], 0
0x18001aafa  jnz     short loc_18001AB02
0x18001aafc  mov     [rbx+0B8h], edx
0x18001ab02  mov     rdx, qword ptr [rsp+88h+var_38]
0x18001ab07  mov     rcx, rbx
0x18001ab0a  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18001ab0f  mov     rcx, [rsp+88h+pv+8]; pv
0x18001ab14  call    cs:__imp_CoTaskMemFree
0x18001ab1a  nop
0x18001ab1b  mov     rcx, [rsp+88h+var_28]
0x18001ab20  xor     rcx, rsp; StackCookie
0x18001ab23  call    __security_check_cookie
0x18001ab28  mov     rbx, [rsp+88h+arg_10]
0x18001ab30  add     rsp, 70h
0x18001ab34  pop     rdi
0x18001ab35  pop     rsi
0x18001ab36  pop     rbp
0x18001ab37  retn
```
