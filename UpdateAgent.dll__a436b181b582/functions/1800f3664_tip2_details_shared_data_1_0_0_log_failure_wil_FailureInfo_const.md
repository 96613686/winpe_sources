# tip2::details::shared_data<1,0,0>::log_failure(wil::FailureInfo const &)

- ea: `0x1800f3664`
- end: `0x1800f39a5`
- name: `?log_failure@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUFailureInfo@wil@@@Z`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ed5a0`

## callees

- `0x1800059d0`
- `0x180027358`
- `0x18008fc14`
- `0x1800f2054`
- `0x1800f3664`
- `0x1800f39ac`
- `0x1800f48d0`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f3726`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f38b5`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f3726`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f38b5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f3743`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f38d2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f3743`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f38d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f396c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f396c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f36af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f36af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f378d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f37ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f378d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f37ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3957`

## string_xrefs

- `0x1800f371f`: `kernelbase.dll`
- `0x1800f38ae`: `kernelbase.dll`

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
0x1800f3664  mov     rax, rsp
0x1800f3667  push    rbp
0x1800f3668  push    rdi
0x1800f3669  push    r12
0x1800f366b  push    r14
0x1800f366d  push    r15
0x1800f366f  lea     rbp, [rax-7D8h]
0x1800f3676  sub     rsp, 8B0h
0x1800f367d  mov     qword ptr [rsp+8D0h+var_8A0], 0FFFFFFFFFFFFFFFEh
0x1800f3686  mov     [rax+18h], rbx
0x1800f368a  mov     [rax+20h], rsi
0x1800f368e  mov     rax, cs:__security_cookie
0x1800f3695  xor     rax, rsp
0x1800f3698  mov     [rbp+7D0h+var_30], rax
0x1800f369f  mov     r12, rdx
0x1800f36a2  mov     rdi, rcx
0x1800f36a5  lea     r15, [rcx+0C0h]
0x1800f36ac  mov     rcx, r15; lpCriticalSection
0x1800f36af  call    cs:__imp_EnterCriticalSection
0x1800f36b6  nop     dword ptr [rax+rax+00h]
0x1800f36bb  inc     dword ptr [rdi+0E8h]
0x1800f36c1  lea     rsi, [rdi+0F0h]
0x1800f36c8  test    dword ptr [rdi+40h], 100h
0x1800f36cf  jnz     loc_1800F380E
0x1800f36d5  mov     rbx, [rsi]
0x1800f36d8  test    rbx, rbx
0x1800f36db  jz      loc_1800F37D6
0x1800f36e1  cmp     dword ptr [rdi+0E8h], 1
0x1800f36e8  jnz     loc_1800F37D6
0x1800f36ee  xorps   xmm0, xmm0
0x1800f36f1  movups  [rsp+8D0h+var_8A0+8], xmm0
0x1800f36f6  movups  [rsp+8D0h+var_890+8], xmm0
0x1800f36fb  movups  xmmword ptr [rsp+8D0h+pv+8], xmm0
0x1800f3700  mov     r14d, [rdi+0B8h]
0x1800f3707  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800f370e  test    rax, rax
0x1800f3711  jnz     short loc_1800F376F
0x1800f3713  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800f371a  test    rax, rax
0x1800f371d  jnz     short loc_1800F3739
0x1800f371f  lea     rcx, LibFileName; "kernelbase.dll"
0x1800f3726  call    cs:__imp_GetModuleHandleW
0x1800f372d  nop     dword ptr [rax+rax+00h]
0x1800f3732  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800f3739  lea     rdx, aTestquerydata; "TestQueryData"
0x1800f3740  mov     rcx, rax; hModule
0x1800f3743  call    cs:__imp_GetProcAddress
0x1800f374a  nop     dword ptr [rax+rax+00h]
0x1800f374f  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800f3756  test    rax, rax
0x1800f3759  jnz     short loc_1800F376F
0x1800f375b  xorps   xmm0, xmm0
0x1800f375e  movups  [rsp+8D0h+var_8A0+8], xmm0
0x1800f3763  movups  [rsp+8D0h+var_890+8], xmm0
0x1800f3768  movups  xmmword ptr [rsp+8D0h+pv+8], xmm0
0x1800f376d  jmp     short loc_1800F3788
0x1800f376f  lea     r9, [rsp+8D0h+var_8A0+8]
0x1800f3774  mov     r8d, r14d
0x1800f3777  mov     edx, 1
0x1800f377c  mov     rcx, rbx
0x1800f377f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3784  test    eax, eax
0x1800f3786  jnz     short loc_1800F379B
0x1800f3788  mov     rcx, qword ptr [rsp+8D0h+pv]; pv
0x1800f378d  call    cs:__imp_CoTaskMemFree
0x1800f3794  nop     dword ptr [rax+rax+00h]
0x1800f3799  jmp     short loc_1800F380E
0x1800f379b  mov     eax, dword ptr [rsp+8D0h+var_890+0Ch]
0x1800f379f  or      [rdi+40h], eax
0x1800f37a2  mov     rcx, qword ptr [rsp+8D0h+pv]; pv
0x1800f37a7  test    rcx, rcx
0x1800f37aa  jz      short loc_1800F37C0
0x1800f37ac  lea     rdx, [rsp+8D0h+var_8A0+8]
0x1800f37b1  mov     rcx, rdi
0x1800f37b4  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800f37b9  mov     rcx, qword ptr [rsp+8D0h+pv]
0x1800f37be  jmp     short loc_1800F37CA
0x1800f37c0  mov     eax, dword ptr [rsp+8D0h+var_890+8]
0x1800f37c4  mov     [rdi+0B8h], eax
0x1800f37ca  call    cs:__imp_CoTaskMemFree
0x1800f37d1  nop     dword ptr [rax+rax+00h]
0x1800f37d6  xorps   xmm0, xmm0
0x1800f37d9  movdqu  [rbp+7D0h+var_7C8], xmm0
0x1800f37de  mov     rdx, r12; struct wil::FailureInfo *
0x1800f37e1  lea     rcx, [rsp+8D0h+var_860]; this
0x1800f37e6  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x1800f37eb  lea     rcx, [rdi+48h]
0x1800f37ef  lea     rdx, [rsp+8D0h+var_860]
0x1800f37f4  call    ?push_back@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N$$QEAVStoredFailureInfo@wil@@@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(wil::StoredFailureInfo &&)
0x1800f37f9  mov     bl, al
0x1800f37fb  lea     rcx, [rsp+8D0h+var_860]; this
0x1800f3800  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x1800f3805  test    bl, bl
0x1800f3807  jnz     short loc_1800F380E
0x1800f3809  bts     dword ptr [rdi+40h], 14h
0x1800f380e  bts     dword ptr [rdi+40h], 0Bh
0x1800f3813  cmp     qword ptr [rsi], 0
0x1800f3817  jz      loc_1800F3963
0x1800f381d  test    dword ptr [rdi+40h], 100h
0x1800f3824  jnz     loc_1800F3963
0x1800f382a  xorps   xmm0, xmm0
0x1800f382d  movups  [rsp+8D0h+var_8A0+8], xmm0
0x1800f3832  movups  [rsp+8D0h+var_890+8], xmm0
0x1800f3837  movups  xmmword ptr [rsp+8D0h+pv+8], xmm0
0x1800f383c  mov     [rsp+8D0h+var_860], 0
0x1800f3845  mov     [rsp+8D0h+var_858], 0
0x1800f384a  lea     rax, [rsp+8D0h+var_857]
0x1800f384f  mov     [rbp+7D0h+var_50], rax
0x1800f3856  lea     rax, [rbp+7D0h+var_57]
0x1800f385d  mov     [rbp+7D0h+var_40], rax
0x1800f3864  mov     [rsp+8D0h+var_857], 80408040h
0x1800f386c  mov     [rsp+8D0h+var_853], 0
0x1800f3871  lea     rax, [rsp+8D0h+var_852]
0x1800f3876  mov     [rbp+7D0h+var_48], rax
0x1800f387d  mov     r8d, 1
0x1800f3883  lea     rdx, [rsp+8D0h+var_860]
0x1800f3888  mov     rcx, rdi
0x1800f388b  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800f3890  mov     rbx, rax
0x1800f3893  mov     rsi, [rsi]
0x1800f3896  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800f389d  test    rax, rax
0x1800f38a0  jnz     short loc_1800F38FE
0x1800f38a2  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800f38a9  test    rax, rax
0x1800f38ac  jnz     short loc_1800F38C8
0x1800f38ae  lea     rcx, LibFileName; "kernelbase.dll"
0x1800f38b5  call    cs:__imp_GetModuleHandleW
0x1800f38bc  nop     dword ptr [rax+rax+00h]
0x1800f38c1  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800f38c8  lea     rdx, aTestunlockdata; "TestUnlockData"
0x1800f38cf  mov     rcx, rax; hModule
0x1800f38d2  call    cs:__imp_GetProcAddress
0x1800f38d9  nop     dword ptr [rax+rax+00h]
0x1800f38de  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800f38e5  test    rax, rax
0x1800f38e8  jnz     short loc_1800F38FE
0x1800f38ea  xorps   xmm0, xmm0
0x1800f38ed  movups  [rsp+8D0h+var_8A0+8], xmm0
0x1800f38f2  movups  [rsp+8D0h+var_890+8], xmm0
0x1800f38f7  movups  xmmword ptr [rsp+8D0h+pv+8], xmm0
0x1800f38fc  jmp     short loc_1800F3910
0x1800f38fe  lea     r9, [rsp+8D0h+var_8A0+8]
0x1800f3903  mov     r8, rbx
0x1800f3906  xor     edx, edx
0x1800f3908  mov     rcx, rsi
0x1800f390b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3910  mov     rcx, qword ptr [rsp+8D0h+var_890+8]
0x1800f3915  mov     rax, rcx
0x1800f3918  shr     rax, 20h
0x1800f391c  or      [rdi+40h], eax
0x1800f391f  cmp     qword ptr [rsp+8D0h+pv], 0
0x1800f3925  jz      short loc_1800F3936
0x1800f3927  lea     rdx, [rsp+8D0h+var_8A0+8]
0x1800f392c  mov     rcx, rdi
0x1800f392f  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800f3934  jmp     short loc_1800F393C
0x1800f3936  mov     [rdi+0B8h], ecx
0x1800f393c  mov     rcx, [rsp+8D0h+var_860]; pv
0x1800f3941  test    rcx, rcx
0x1800f3944  jz      short loc_1800F3952
0x1800f3946  call    cs:__imp_CoTaskMemFree
0x1800f394d  nop     dword ptr [rax+rax+00h]
0x1800f3952  mov     rcx, qword ptr [rsp+8D0h+pv]; pv
0x1800f3957  call    cs:__imp_CoTaskMemFree
0x1800f395e  nop     dword ptr [rax+rax+00h]
0x1800f3963  dec     dword ptr [rdi+0E8h]
0x1800f3969  mov     rcx, r15; lpCriticalSection
0x1800f396c  call    cs:__imp_LeaveCriticalSection
0x1800f3973  nop     dword ptr [rax+rax+00h]
0x1800f3978  nop
0x1800f3979  mov     rcx, [rbp+7D0h+var_30]
0x1800f3980  xor     rcx, rsp; StackCookie
0x1800f3983  call    __security_check_cookie
0x1800f3988  lea     r11, [rsp+8D0h+var_20]
0x1800f3990  mov     rbx, [r11+40h]
0x1800f3994  mov     rsi, [r11+48h]
0x1800f3998  mov     rsp, r11
0x1800f399b  pop     r15
0x1800f399d  pop     r14
0x1800f399f  pop     r12
0x1800f39a1  pop     rdi
0x1800f39a2  pop     rbp
0x1800f39a3  retn
```
