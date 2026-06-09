# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18000d178`
- end: `0x18000d278`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d280`
- `0x18000e090`

## callees

- `0x180004c70`
- `0x18000a17c`
- `0x18000d178`
- `0x18000daac`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d1e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d1e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d254`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d254`

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
0x18000d178  mov     [rsp+arg_10], rbx
0x18000d17d  push    rbp
0x18000d17e  push    rsi
0x18000d17f  push    rdi
0x18000d180  sub     rsp, 70h
0x18000d184  mov     rax, cs:__security_cookie
0x18000d18b  xor     rax, rsp
0x18000d18e  mov     [rsp+88h+var_28], rax
0x18000d193  mov     edi, edx
0x18000d195  mov     rbx, rcx
0x18000d198  xorps   xmm0, xmm0
0x18000d19b  movups  [rsp+88h+var_58], xmm0
0x18000d1a0  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18000d1a5  movups  [rsp+88h+var_38], xmm0
0x18000d1aa  cmp     dword ptr [rcx+0E8h], 0
0x18000d1b1  jbe     short loc_18000D1B6
0x18000d1b3  or      edi, 8
0x18000d1b6  mov     esi, [rcx+0B8h]
0x18000d1bc  mov     rbp, [rcx+0F0h]
0x18000d1c3  mov     qword ptr [rcx+0F0h], 0
0x18000d1ce  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18000d1d5  test    rax, rax
0x18000d1d8  jnz     short loc_18000D20F
0x18000d1da  call    tip_details_GetKernelBaseModuleHandle
0x18000d1df  mov     rcx, rax; hModule
0x18000d1e2  lea     rdx, aTestquerydata; "TestQueryData"
0x18000d1e9  call    cs:__imp_GetProcAddress
0x18000d1ef  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18000d1f6  test    rax, rax
0x18000d1f9  jnz     short loc_18000D20F
0x18000d1fb  xorps   xmm0, xmm0
0x18000d1fe  movups  [rsp+88h+var_58], xmm0
0x18000d203  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18000d208  movups  [rsp+88h+var_38], xmm0
0x18000d20d  jmp     short loc_18000D24F
0x18000d20f  lea     r9, [rsp+88h+var_58]
0x18000d214  mov     r8d, esi
0x18000d217  mov     edx, edi
0x18000d219  mov     rcx, rbp
0x18000d21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d221  test    eax, eax
0x18000d223  jz      short loc_18000D24F
0x18000d225  mov     rdx, [rsp+88h+pv]
0x18000d22a  mov     rax, rdx
0x18000d22d  shr     rax, 20h
0x18000d231  or      [rbx+40h], eax
0x18000d234  cmp     [rsp+88h+pv+8], 0
0x18000d23a  jnz     short loc_18000D242
0x18000d23c  mov     [rbx+0B8h], edx
0x18000d242  mov     rdx, qword ptr [rsp+88h+var_38]
0x18000d247  mov     rcx, rbx
0x18000d24a  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18000d24f  mov     rcx, [rsp+88h+pv+8]; pv
0x18000d254  call    cs:__imp_CoTaskMemFree
0x18000d25a  nop
0x18000d25b  mov     rcx, [rsp+88h+var_28]
0x18000d260  xor     rcx, rsp; StackCookie
0x18000d263  call    __security_check_cookie
0x18000d268  mov     rbx, [rsp+88h+arg_10]
0x18000d270  add     rsp, 70h
0x18000d274  pop     rdi
0x18000d275  pop     rsi
0x18000d276  pop     rbp
0x18000d277  retn
```
