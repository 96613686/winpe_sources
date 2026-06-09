# tip2::details::shared_data<1,0,0>::log_failure(wil::FailureInfo const &)

- ea: `0x18007d54c`
- end: `0x18007d88d`
- name: `?log_failure@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUFailureInfo@wil@@@Z`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180077480`

## callees

- `0x1800031d0`
- `0x18000990c`
- `0x18000bb6c`
- `0x18007bf34`
- `0x18007d54c`
- `0x18007d894`
- `0x18007e7c0`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007d62b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007d7ba`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007d62b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007d7ba`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18007d60e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18007d79d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18007d60e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18007d79d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d854`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d854`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d597`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d675`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d82e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d83f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d675`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d82e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d83f`

## string_xrefs

- `0x18007d607`: `kernelbase.dll`
- `0x18007d796`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::log_failure(__int64 a1, const struct wil::FailureInfo *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  __int64 *v5; // rsi
  __int64 v6; // rbx
  unsigned int v7; // r14d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  void *v10; // rcx
  char v11; // bl
  __int64 v12; // rbx
  __int64 v13; // rsi
  FARPROC v14; // rax
  HMODULE v15; // rax
  int v16; // ecx
  __int128 v17; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B8h]
  __int128 pv_8; // [rsp+60h] [rbp-A8h]
  LPVOID v20; // [rsp+78h] [rbp-90h] BYREF
  char v21; // [rsp+80h] [rbp-88h]
  int v22; // [rsp+81h] [rbp-87h] BYREF
  char v23; // [rsp+85h] [rbp-83h]
  char v24; // [rsp+86h] [rbp-82h] BYREF
  __int128 v25; // [rsp+110h] [rbp+8h]
  char v26; // [rsp+881h] [rbp+779h] BYREF
  int *v27; // [rsp+888h] [rbp+780h]
  char *v28; // [rsp+890h] [rbp+788h]
  char *v29; // [rsp+898h] [rbp+790h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  ++*(_DWORD *)(a1 + 232);
  v5 = (__int64 *)(a1 + 240);
  if ( (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v6 = *v5;
    if ( *v5 && *(_DWORD *)(a1 + 232) == 1 )
    {
      v17 = 0;
      v18 = 0;
      pv_8 = 0;
      v7 = *(_DWORD *)(a1 + 184);
      ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
      if ( !`TestQueryData'::`2'::s_pfnTestQueryData )
      {
        ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
        if ( !g_tip_details_kernelbaseModuleHandle )
        {
          ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
          g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
        }
        ProcAddress = GetProcAddress(ModuleHandleW, "TestQueryData");
        `TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress;
        if ( !ProcAddress )
        {
          v17 = 0;
          v18 = 0;
          pv_8 = 0;
LABEL_10:
          CoTaskMemFree(*((LPVOID *)&v18 + 1));
          goto LABEL_17;
        }
      }
      if ( !((unsigned int (__fastcall *)(__int64, __int64, _QWORD, __int128 *))ProcAddress)(v6, 1, v7, &v17) )
        goto LABEL_10;
      *(_DWORD *)(a1 + 64) |= DWORD1(v18);
      v10 = (void *)*((_QWORD *)&v18 + 1);
      if ( *((_QWORD *)&v18 + 1) )
      {
        tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v17);
        v10 = (void *)*((_QWORD *)&v18 + 1);
      }
      else
      {
        *(_DWORD *)(a1 + 184) = v18;
      }
      CoTaskMemFree(v10);
    }
    v25 = 0;
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)&v20, a2);
    v11 = tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(a1 + 72, &v20);
    wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)&v20);
    if ( !v11 )
      *(_DWORD *)(a1 + 64) |= 0x100000u;
  }
LABEL_17:
  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *v5 && (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v17 = 0;
    v18 = 0;
    pv_8 = 0;
    v20 = 0;
    v21 = 0;
    v27 = &v22;
    v29 = &v26;
    v22 = -2143256512;
    v23 = 0;
    v28 = &v24;
    v12 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v20, 1);
    v13 = *v5;
    v14 = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_24;
    v15 = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      v15 = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = v15;
    }
    v14 = GetProcAddress(v15, "TestUnlockData");
    `TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)v14;
    if ( v14 )
    {
LABEL_24:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))v14)(v13, 0, v12, &v17);
    }
    else
    {
      v17 = 0;
      v18 = 0;
      pv_8 = 0;
    }
    v16 = v18;
    *(_DWORD *)(a1 + 64) |= DWORD1(v18);
    if ( *((_QWORD *)&v18 + 1) )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v17);
    else
      *(_DWORD *)(a1 + 184) = v16;
    if ( v20 )
      CoTaskMemFree(v20);
    CoTaskMemFree(*((LPVOID *)&v18 + 1));
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x18007d54c  mov     rax, rsp
0x18007d54f  push    rbp
0x18007d550  push    rdi
0x18007d551  push    r12
0x18007d553  push    r14
0x18007d555  push    r15
0x18007d557  lea     rbp, [rax-7D8h]
0x18007d55e  sub     rsp, 8B0h
0x18007d565  mov     qword ptr [rsp+8D0h+var_8A0], 0FFFFFFFFFFFFFFFEh
0x18007d56e  mov     [rax+18h], rbx
0x18007d572  mov     [rax+20h], rsi
0x18007d576  mov     rax, cs:__security_cookie
0x18007d57d  xor     rax, rsp
0x18007d580  mov     [rbp+7D0h+var_30], rax
0x18007d587  mov     r12, rdx
0x18007d58a  mov     rdi, rcx
0x18007d58d  lea     r15, [rcx+0C0h]
0x18007d594  mov     rcx, r15; lpCriticalSection
0x18007d597  call    cs:__imp_EnterCriticalSection
0x18007d59e  nop     dword ptr [rax+rax+00h]
0x18007d5a3  inc     dword ptr [rdi+0E8h]
0x18007d5a9  lea     rsi, [rdi+0F0h]
0x18007d5b0  test    dword ptr [rdi+40h], 100h
0x18007d5b7  jnz     loc_18007D6F6
0x18007d5bd  mov     rbx, [rsi]
0x18007d5c0  test    rbx, rbx
0x18007d5c3  jz      loc_18007D6BE
0x18007d5c9  cmp     dword ptr [rdi+0E8h], 1
0x18007d5d0  jnz     loc_18007D6BE
0x18007d5d6  xorps   xmm0, xmm0
0x18007d5d9  movups  [rsp+8D0h+var_8A0+8], xmm0
0x18007d5de  movups  [rsp+8D0h+var_890+8], xmm0
0x18007d5e3  movups  xmmword ptr [rsp+8D0h+pv+8], xmm0
0x18007d5e8  mov     r14d, [rdi+0B8h]
0x18007d5ef  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18007d5f6  test    rax, rax
0x18007d5f9  jnz     short loc_18007D657
0x18007d5fb  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18007d602  test    rax, rax
0x18007d605  jnz     short loc_18007D621
0x18007d607  lea     rcx, LibFileName; "kernelbase.dll"
0x18007d60e  call    cs:__imp_GetModuleHandleW
0x18007d615  nop     dword ptr [rax+rax+00h]
0x18007d61a  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18007d621  lea     rdx, aTestquerydata; "TestQueryData"
0x18007d628  mov     rcx, rax; hModule
0x18007d62b  call    cs:__imp_GetProcAddress
0x18007d632  nop     dword ptr [rax+rax+00h]
0x18007d637  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18007d63e  test    rax, rax
0x18007d641  jnz     short loc_18007D657
0x18007d643  xorps   xmm0, xmm0
0x18007d646  movups  [rsp+8D0h+var_8A0+8], xmm0
0x18007d64b  movups  [rsp+8D0h+var_890+8], xmm0
0x18007d650  movups  xmmword ptr [rsp+8D0h+pv+8], xmm0
0x18007d655  jmp     short loc_18007D670
0x18007d657  lea     r9, [rsp+8D0h+var_8A0+8]
0x18007d65c  mov     r8d, r14d
0x18007d65f  mov     edx, 1
0x18007d664  mov     rcx, rbx
0x18007d667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d66c  test    eax, eax
0x18007d66e  jnz     short loc_18007D683
0x18007d670  mov     rcx, qword ptr [rsp+8D0h+pv]; pv
0x18007d675  call    cs:__imp_CoTaskMemFree
0x18007d67c  nop     dword ptr [rax+rax+00h]
0x18007d681  jmp     short loc_18007D6F6
0x18007d683  mov     eax, dword ptr [rsp+8D0h+var_890+0Ch]
0x18007d687  or      [rdi+40h], eax
0x18007d68a  mov     rcx, qword ptr [rsp+8D0h+pv]; pv
0x18007d68f  test    rcx, rcx
0x18007d692  jz      short loc_18007D6A8
0x18007d694  lea     rdx, [rsp+8D0h+var_8A0+8]
0x18007d699  mov     rcx, rdi
0x18007d69c  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18007d6a1  mov     rcx, qword ptr [rsp+8D0h+pv]
0x18007d6a6  jmp     short loc_18007D6B2
0x18007d6a8  mov     eax, dword ptr [rsp+8D0h+var_890+8]
0x18007d6ac  mov     [rdi+0B8h], eax
0x18007d6b2  call    cs:__imp_CoTaskMemFree
0x18007d6b9  nop     dword ptr [rax+rax+00h]
0x18007d6be  xorps   xmm0, xmm0
0x18007d6c1  movdqu  [rbp+7D0h+var_7C8], xmm0
0x18007d6c6  mov     rdx, r12; struct wil::FailureInfo *
0x18007d6c9  lea     rcx, [rsp+8D0h+var_860]; this
0x18007d6ce  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18007d6d3  lea     rcx, [rdi+48h]
0x18007d6d7  lea     rdx, [rsp+8D0h+var_860]
0x18007d6dc  call    ?push_back@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N$$QEAVStoredFailureInfo@wil@@@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(wil::StoredFailureInfo &&)
0x18007d6e1  mov     bl, al
0x18007d6e3  lea     rcx, [rsp+8D0h+var_860]; this
0x18007d6e8  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x18007d6ed  test    bl, bl
0x18007d6ef  jnz     short loc_18007D6F6
0x18007d6f1  bts     dword ptr [rdi+40h], 14h
0x18007d6f6  bts     dword ptr [rdi+40h], 0Bh
0x18007d6fb  cmp     qword ptr [rsi], 0
0x18007d6ff  jz      loc_18007D84B
0x18007d705  test    dword ptr [rdi+40h], 100h
0x18007d70c  jnz     loc_18007D84B
0x18007d712  xorps   xmm0, xmm0
0x18007d715  movups  [rsp+8D0h+var_8A0+8], xmm0
0x18007d71a  movups  [rsp+8D0h+var_890+8], xmm0
0x18007d71f  movups  xmmword ptr [rsp+8D0h+pv+8], xmm0
0x18007d724  mov     [rsp+8D0h+var_860], 0
0x18007d72d  mov     [rsp+8D0h+var_858], 0
0x18007d732  lea     rax, [rsp+8D0h+var_857]
0x18007d737  mov     [rbp+7D0h+var_50], rax
0x18007d73e  lea     rax, [rbp+7D0h+var_57]
0x18007d745  mov     [rbp+7D0h+var_40], rax
0x18007d74c  mov     [rsp+8D0h+var_857], 80408040h
0x18007d754  mov     [rsp+8D0h+var_853], 0
0x18007d759  lea     rax, [rsp+8D0h+var_852]
0x18007d75e  mov     [rbp+7D0h+var_48], rax
0x18007d765  mov     r8d, 1
0x18007d76b  lea     rdx, [rsp+8D0h+var_860]
0x18007d770  mov     rcx, rdi
0x18007d773  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18007d778  mov     rbx, rax
0x18007d77b  mov     rsi, [rsi]
0x18007d77e  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18007d785  test    rax, rax
0x18007d788  jnz     short loc_18007D7E6
0x18007d78a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18007d791  test    rax, rax
0x18007d794  jnz     short loc_18007D7B0
0x18007d796  lea     rcx, LibFileName; "kernelbase.dll"
0x18007d79d  call    cs:__imp_GetModuleHandleW
0x18007d7a4  nop     dword ptr [rax+rax+00h]
0x18007d7a9  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18007d7b0  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18007d7b7  mov     rcx, rax; hModule
0x18007d7ba  call    cs:__imp_GetProcAddress
0x18007d7c1  nop     dword ptr [rax+rax+00h]
0x18007d7c6  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18007d7cd  test    rax, rax
0x18007d7d0  jnz     short loc_18007D7E6
0x18007d7d2  xorps   xmm0, xmm0
0x18007d7d5  movups  [rsp+8D0h+var_8A0+8], xmm0
0x18007d7da  movups  [rsp+8D0h+var_890+8], xmm0
0x18007d7df  movups  xmmword ptr [rsp+8D0h+pv+8], xmm0
0x18007d7e4  jmp     short loc_18007D7F8
0x18007d7e6  lea     r9, [rsp+8D0h+var_8A0+8]
0x18007d7eb  mov     r8, rbx
0x18007d7ee  xor     edx, edx
0x18007d7f0  mov     rcx, rsi
0x18007d7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7f8  mov     rcx, qword ptr [rsp+8D0h+var_890+8]
0x18007d7fd  mov     rax, rcx
0x18007d800  shr     rax, 20h
0x18007d804  or      [rdi+40h], eax
0x18007d807  cmp     qword ptr [rsp+8D0h+pv], 0
0x18007d80d  jz      short loc_18007D81E
0x18007d80f  lea     rdx, [rsp+8D0h+var_8A0+8]
0x18007d814  mov     rcx, rdi
0x18007d817  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18007d81c  jmp     short loc_18007D824
0x18007d81e  mov     [rdi+0B8h], ecx
0x18007d824  mov     rcx, [rsp+8D0h+var_860]; pv
0x18007d829  test    rcx, rcx
0x18007d82c  jz      short loc_18007D83A
0x18007d82e  call    cs:__imp_CoTaskMemFree
0x18007d835  nop     dword ptr [rax+rax+00h]
0x18007d83a  mov     rcx, qword ptr [rsp+8D0h+pv]; pv
0x18007d83f  call    cs:__imp_CoTaskMemFree
0x18007d846  nop     dword ptr [rax+rax+00h]
0x18007d84b  dec     dword ptr [rdi+0E8h]
0x18007d851  mov     rcx, r15; lpCriticalSection
0x18007d854  call    cs:__imp_LeaveCriticalSection
0x18007d85b  nop     dword ptr [rax+rax+00h]
0x18007d860  nop
0x18007d861  mov     rcx, [rbp+7D0h+var_30]
0x18007d868  xor     rcx, rsp; StackCookie
0x18007d86b  call    __security_check_cookie
0x18007d870  lea     r11, [rsp+8D0h+var_20]
0x18007d878  mov     rbx, [r11+40h]
0x18007d87c  mov     rsi, [r11+48h]
0x18007d880  mov     rsp, r11
0x18007d883  pop     r15
0x18007d885  pop     r14
0x18007d887  pop     r12
0x18007d889  pop     rdi
0x18007d88a  pop     rbp
0x18007d88b  retn
```
