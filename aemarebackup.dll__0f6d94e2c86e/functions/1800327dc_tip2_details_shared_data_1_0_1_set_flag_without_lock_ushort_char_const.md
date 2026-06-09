# tip2::details::shared_data<1,0,1>::set_flag_without_lock(ushort,char const *)

- ea: `0x1800327dc`
- end: `0x180032aaf`
- name: `?set_flag_without_lock@?$shared_data@$00$0A@$00@details@tip2@@AEAAXGPEBD@Z`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180031dd0`

## callees

- `0x180004ea0`
- `0x180028028`
- `0x18002a4ec`
- `0x1800326dc`
- `0x1800327dc`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800328a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800329f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800328a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800329f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032891`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800329df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032891`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800329df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032820`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032820`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032a7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032a7e`
- `ole32!CoTaskMemFree` at `0x1800328ec`
- `ole32!CoTaskMemFree` at `0x180032923`
- `ole32!CoTaskMemFree` at `0x180032a64`
- `ole32!CoTaskMemFree` at `0x180032a6f`
- `ole32!CoTaskMemFree` at `0x1800328ec`
- `ole32!CoTaskMemFree` at `0x180032923`
- `ole32!CoTaskMemFree` at `0x180032a64`
- `ole32!CoTaskMemFree` at `0x180032a6f`

## string_xrefs

- `0x18003288a`: `kernelbase.dll`
- `0x1800329d8`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,1>::set_flag_without_lock(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r13
  __int64 v7; // r9
  __int64 *v8; // rdi
  __int64 v9; // rsi
  unsigned int v10; // r14d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  void *v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rdi
  FARPROC v16; // rax
  HMODULE v17; // rax
  int v18; // ecx
  __int128 v19; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  LPVOID v22; // [rsp+60h] [rbp-A0h] BYREF
  char v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+69h] [rbp-97h] BYREF
  char v25; // [rsp+6Dh] [rbp-93h]
  char v26; // [rsp+6Eh] [rbp-92h] BYREF
  char v27; // [rsp+869h] [rbp+769h] BYREF
  int *v28; // [rsp+870h] [rbp+770h]
  char *v29; // [rsp+878h] [rbp+778h]
  char *v30; // [rsp+880h] [rbp+780h]

  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  ++*(_DWORD *)(a1 + 232);
  v8 = (__int64 *)(a1 + 240);
  if ( (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v9 = *v8;
    if ( *v8 && *(_DWORD *)(a1 + 232) == 1 )
    {
      v19 = 0;
      *(_OWORD *)pv = 0;
      v21 = 0;
      v10 = *(_DWORD *)(a1 + 184);
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
          v19 = 0;
          *(_OWORD *)pv = 0;
          v21 = 0;
LABEL_10:
          CoTaskMemFree(pv[1]);
          goto LABEL_16;
        }
      }
      if ( !((unsigned int (__fastcall *)(__int64, __int64, _QWORD, __int128 *))ProcAddress)(v9, 1, v10, &v19) )
        goto LABEL_10;
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      v13 = pv[1];
      if ( pv[1] )
      {
        tip2::details::shared_data<1,0,1>::deserialize_data((_QWORD *)a1, (__int64)&v19);
        v13 = pv[1];
      }
      else
      {
        *(_DWORD *)(a1 + 184) = pv[0];
      }
      CoTaskMemFree(v13);
    }
    tip2::details::shared_data<1,0,1>::set_flag(a1, a2, a3);
  }
LABEL_16:
  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *v8 && (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v19 = 0;
    *(_OWORD *)pv = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v28 = &v24;
    v30 = &v27;
    v24 = -2143256512;
    v25 = 0;
    v29 = &v26;
    v14 = tip2::details::shared_data<1,0,1>::serialize_data(a1, &v22, 1, v7);
    v15 = *v8;
    v16 = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_23;
    v17 = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      v17 = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = v17;
    }
    v16 = GetProcAddress(v17, "TestUnlockData");
    `TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)v16;
    if ( v16 )
    {
LABEL_23:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))v16)(v15, 0, v14, &v19);
    }
    else
    {
      v19 = 0;
      *(_OWORD *)pv = 0;
      v21 = 0;
    }
    v18 = (int)pv[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( pv[1] )
      tip2::details::shared_data<1,0,1>::deserialize_data((_QWORD *)a1, (__int64)&v19);
    else
      *(_DWORD *)(a1 + 184) = v18;
    if ( v22 )
      CoTaskMemFree(v22);
    CoTaskMemFree(pv[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection(v6);
}

```

## disassembly

```asm
0x1800327dc  mov     [rsp-8+arg_8], rbx
0x1800327e1  push    rbp
0x1800327e2  push    rsi
0x1800327e3  push    rdi
0x1800327e4  push    r12
0x1800327e6  push    r13
0x1800327e8  push    r14
0x1800327ea  push    r15
0x1800327ec  lea     rbp, [rsp-7A0h]
0x1800327f4  sub     rsp, 8A0h
0x1800327fb  mov     rax, cs:__security_cookie
0x180032802  xor     rax, rsp
0x180032805  mov     [rbp+7D0h+var_40], rax
0x18003280c  mov     r12, r8
0x18003280f  movzx   r15d, dx
0x180032813  mov     rbx, rcx
0x180032816  lea     r13, [rcx+0C0h]
0x18003281d  mov     rcx, r13; lpCriticalSection
0x180032820  call    cs:__imp_EnterCriticalSection
0x180032826  inc     dword ptr [rbx+0E8h]
0x18003282c  lea     rdi, [rbx+0F0h]
0x180032833  test    dword ptr [rbx+40h], 100h
0x18003283a  jnz     loc_180032938
0x180032840  mov     rsi, [rdi]
0x180032843  test    rsi, rsi
0x180032846  jz      loc_180032929
0x18003284c  cmp     dword ptr [rbx+0E8h], 1
0x180032853  jnz     loc_180032929
0x180032859  xorps   xmm0, xmm0
0x18003285c  movups  [rsp+8D0h+var_8A0], xmm0
0x180032861  movups  xmmword ptr [rsp+8D0h+pv], xmm0
0x180032866  movups  [rsp+8D0h+var_880], xmm0
0x18003286b  mov     r14d, [rbx+0B8h]
0x180032872  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180032879  test    rax, rax
0x18003287c  jnz     short loc_1800328CE
0x18003287e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180032885  test    rax, rax
0x180032888  jnz     short loc_18003289E
0x18003288a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180032891  call    cs:__imp_GetModuleHandleW
0x180032897  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18003289e  lea     rdx, aTestquerydata; "TestQueryData"
0x1800328a5  mov     rcx, rax; hModule
0x1800328a8  call    cs:__imp_GetProcAddress
0x1800328ae  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800328b5  test    rax, rax
0x1800328b8  jnz     short loc_1800328CE
0x1800328ba  xorps   xmm0, xmm0
0x1800328bd  movups  [rsp+8D0h+var_8A0], xmm0
0x1800328c2  movups  xmmword ptr [rsp+8D0h+pv], xmm0
0x1800328c7  movups  [rsp+8D0h+var_880], xmm0
0x1800328cc  jmp     short loc_1800328E7
0x1800328ce  lea     r9, [rsp+8D0h+var_8A0]
0x1800328d3  mov     r8d, r14d
0x1800328d6  mov     edx, 1
0x1800328db  mov     rcx, rsi
0x1800328de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328e3  test    eax, eax
0x1800328e5  jnz     short loc_1800328F4
0x1800328e7  mov     rcx, [rsp+8D0h+pv+8]; pv
0x1800328ec  call    cs:__imp_CoTaskMemFree
0x1800328f2  jmp     short loc_180032938
0x1800328f4  mov     eax, dword ptr [rsp+8D0h+pv+4]
0x1800328f8  or      [rbx+40h], eax
0x1800328fb  mov     rcx, [rsp+8D0h+pv+8]; pv
0x180032900  test    rcx, rcx
0x180032903  jz      short loc_180032919
0x180032905  lea     rdx, [rsp+8D0h+var_8A0]
0x18003290a  mov     rcx, rbx
0x18003290d  call    ?deserialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,1>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180032912  mov     rcx, [rsp+8D0h+pv+8]
0x180032917  jmp     short loc_180032923
0x180032919  mov     eax, dword ptr [rsp+8D0h+pv]
0x18003291d  mov     [rbx+0B8h], eax
0x180032923  call    cs:__imp_CoTaskMemFree
0x180032929  mov     r8, r12
0x18003292c  movzx   edx, r15w
0x180032930  mov     rcx, rbx
0x180032933  call    ?set_flag@?$shared_data@$00$0A@$00@details@tip2@@QEAAXGPEBD@Z; tip2::details::shared_data<1,0,1>::set_flag(ushort,char const *)
0x180032938  bts     dword ptr [rbx+40h], 0Bh
0x18003293d  cmp     qword ptr [rdi], 0
0x180032941  jz      loc_180032A75
0x180032947  test    dword ptr [rbx+40h], 100h
0x18003294e  jnz     loc_180032A75
0x180032954  xorps   xmm0, xmm0
0x180032957  movups  [rsp+8D0h+var_8A0], xmm0
0x18003295c  movups  xmmword ptr [rsp+8D0h+pv], xmm0
0x180032961  movups  [rsp+8D0h+var_880], xmm0
0x180032966  mov     [rsp+8D0h+var_870], 0
0x18003296f  mov     [rsp+8D0h+var_868], 0
0x180032974  lea     rax, [rsp+8D0h+var_867]
0x180032979  mov     [rbp+7D0h+var_60], rax
0x180032980  lea     rax, [rbp+7D0h+var_67]
0x180032987  mov     [rbp+7D0h+var_50], rax
0x18003298e  mov     [rsp+8D0h+var_867], 80408040h
0x180032996  mov     [rsp+8D0h+var_863], 0
0x18003299b  lea     rax, [rsp+8D0h+var_862]
0x1800329a0  mov     [rbp+7D0h+var_58], rax
0x1800329a7  mov     r8d, 1
0x1800329ad  lea     rdx, [rsp+8D0h+var_870]
0x1800329b2  mov     rcx, rbx
0x1800329b5  call    ?serialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800329ba  mov     rsi, rax
0x1800329bd  mov     rdi, [rdi]
0x1800329c0  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800329c7  test    rax, rax
0x1800329ca  jnz     short loc_180032A1C
0x1800329cc  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800329d3  test    rax, rax
0x1800329d6  jnz     short loc_1800329EC
0x1800329d8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800329df  call    cs:__imp_GetModuleHandleW
0x1800329e5  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800329ec  lea     rdx, aTestunlockdata; "TestUnlockData"
0x1800329f3  mov     rcx, rax; hModule
0x1800329f6  call    cs:__imp_GetProcAddress
0x1800329fc  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180032a03  test    rax, rax
0x180032a06  jnz     short loc_180032A1C
0x180032a08  xorps   xmm0, xmm0
0x180032a0b  movups  [rsp+8D0h+var_8A0], xmm0
0x180032a10  movups  xmmword ptr [rsp+8D0h+pv], xmm0
0x180032a15  movups  [rsp+8D0h+var_880], xmm0
0x180032a1a  jmp     short loc_180032A2E
0x180032a1c  lea     r9, [rsp+8D0h+var_8A0]
0x180032a21  mov     r8, rsi
0x180032a24  xor     edx, edx
0x180032a26  mov     rcx, rdi
0x180032a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a2e  mov     rcx, [rsp+8D0h+pv]
0x180032a33  mov     rax, rcx
0x180032a36  shr     rax, 20h
0x180032a3a  or      [rbx+40h], eax
0x180032a3d  cmp     [rsp+8D0h+pv+8], 0
0x180032a43  jz      short loc_180032A54
0x180032a45  lea     rdx, [rsp+8D0h+var_8A0]
0x180032a4a  mov     rcx, rbx
0x180032a4d  call    ?deserialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,1>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180032a52  jmp     short loc_180032A5A
0x180032a54  mov     [rbx+0B8h], ecx
0x180032a5a  mov     rcx, [rsp+8D0h+var_870]; pv
0x180032a5f  test    rcx, rcx
0x180032a62  jz      short loc_180032A6A
0x180032a64  call    cs:__imp_CoTaskMemFree
0x180032a6a  mov     rcx, [rsp+8D0h+pv+8]; pv
0x180032a6f  call    cs:__imp_CoTaskMemFree
0x180032a75  dec     dword ptr [rbx+0E8h]
0x180032a7b  mov     rcx, r13; lpCriticalSection
0x180032a7e  call    cs:__imp_LeaveCriticalSection
0x180032a84  nop
0x180032a85  mov     rcx, [rbp+7D0h+var_40]
0x180032a8c  xor     rcx, rsp; StackCookie
0x180032a8f  call    __security_check_cookie
0x180032a94  mov     rbx, [rsp+8D0h+arg_8]
0x180032a9c  add     rsp, 8A0h
0x180032aa3  pop     r15
0x180032aa5  pop     r14
0x180032aa7  pop     r13
0x180032aa9  pop     r12
0x180032aab  pop     rdi
0x180032aac  pop     rsi
0x180032aad  pop     rbp
0x180032aae  retn
```
