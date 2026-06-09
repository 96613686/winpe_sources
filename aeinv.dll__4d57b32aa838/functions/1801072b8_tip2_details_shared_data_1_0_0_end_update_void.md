# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x1801072b8`
- end: `0x180107439`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `385`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180051048`
- `0x180106d90`

## callees

- `0x180053020`
- `0x1800553bc`
- `0x1800561c4`
- `0x180059920`
- `0x1801072b8`
- `0x180109004`
- `0x180130010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180107417`
- `KERNEL32!LeaveCriticalSection` at `0x180107417`
- `KERNEL32!GetProcAddress` at `0x180107391`
- `KERNEL32!GetProcAddress` at `0x180107391`
- `ole32!CoTaskMemFree` at `0x180107404`
- `ole32!CoTaskMemFree` at `0x180107404`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  int v6; // ecx
  __int128 v7; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv[2]; // [rsp+48h] [rbp-B8h]
  __int128 v9; // [rsp+58h] [rbp-A8h]
  void *v10; // [rsp+70h] [rbp-90h] BYREF
  char v11; // [rsp+78h] [rbp-88h]
  int v12; // [rsp+79h] [rbp-87h] BYREF
  char v13; // [rsp+7Dh] [rbp-83h]
  char v14; // [rsp+7Eh] [rbp-82h] BYREF
  char v15; // [rsp+879h] [rbp+779h] BYREF
  int *v16; // [rsp+880h] [rbp+780h]
  char *v17; // [rsp+888h] [rbp+788h]
  char *v18; // [rsp+890h] [rbp+790h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v7 = 0;
    *(_OWORD *)pv = 0;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v16 = &v12;
    v18 = &v15;
    v12 = -2143256512;
    v13 = 0;
    v17 = &v14;
    v2 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v10, 1);
    v3 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData
      || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
          ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestUnlockData"),
          (`TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v3, 0, v2, &v7);
    }
    else
    {
      v7 = 0;
      *(_OWORD *)pv = 0;
      v9 = 0;
    }
    v6 = (int)pv[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( pv[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data((__int64 *)a1, (__int64)&v7);
    else
      *(_DWORD *)(a1 + 184) = v6;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v10);
    CoTaskMemFree(pv[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x1801072b8  push    rbp
0x1801072ba  push    rbx
0x1801072bb  push    rsi
0x1801072bc  push    rdi
0x1801072bd  lea     rbp, [rsp-7B8h]
0x1801072c5  sub     rsp, 8B8h
0x1801072cc  mov     [rsp+8D0h+var_8A0], 0FFFFFFFFFFFFFFFEh
0x1801072d5  mov     rax, cs:__security_cookie
0x1801072dc  xor     rax, rsp
0x1801072df  mov     [rbp+7D0h+var_30], rax
0x1801072e6  mov     rbx, rcx
0x1801072e9  bts     dword ptr [rcx+40h], 0Bh
0x1801072ee  cmp     qword ptr [rcx+0F0h], 0
0x1801072f6  jz      loc_18010740A
0x1801072fc  test    dword ptr [rcx+40h], 100h
0x180107303  jnz     loc_18010740A
0x180107309  xorps   xmm0, xmm0
0x18010730c  movups  [rsp+8D0h+var_898], xmm0
0x180107311  movups  xmmword ptr [rsp+8D0h+pv], xmm0
0x180107316  movups  [rsp+8D0h+var_878], xmm0
0x18010731b  mov     [rsp+8D0h+var_860], 0
0x180107324  mov     [rsp+8D0h+var_858], 0
0x180107329  lea     rax, [rsp+8D0h+var_857]
0x18010732e  mov     [rbp+7D0h+var_50], rax
0x180107335  lea     rax, [rbp+7D0h+var_57]
0x18010733c  mov     [rbp+7D0h+var_40], rax
0x180107343  mov     [rsp+8D0h+var_857], 80408040h
0x18010734b  mov     [rsp+8D0h+var_853], 0
0x180107350  lea     rax, [rsp+8D0h+var_852]
0x180107355  mov     [rbp+7D0h+var_48], rax
0x18010735c  mov     r8d, 1
0x180107362  lea     rdx, [rsp+8D0h+var_860]
0x180107367  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18010736c  mov     rdi, rax
0x18010736f  mov     rsi, [rbx+0F0h]
0x180107376  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18010737d  test    rax, rax
0x180107380  jnz     short loc_1801073B7
0x180107382  call    tip_details_GetKernelBaseModuleHandle
0x180107387  mov     rcx, rax; hModule
0x18010738a  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180107391  call    cs:__imp_GetProcAddress
0x180107397  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18010739e  test    rax, rax
0x1801073a1  jnz     short loc_1801073B7
0x1801073a3  xorps   xmm0, xmm0
0x1801073a6  movups  [rsp+8D0h+var_898], xmm0
0x1801073ab  movups  xmmword ptr [rsp+8D0h+pv], xmm0
0x1801073b0  movups  [rsp+8D0h+var_878], xmm0
0x1801073b5  jmp     short loc_1801073C9
0x1801073b7  lea     r9, [rsp+8D0h+var_898]
0x1801073bc  mov     r8, rdi
0x1801073bf  xor     edx, edx
0x1801073c1  mov     rcx, rsi
0x1801073c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801073c9  mov     rcx, [rsp+8D0h+pv]
0x1801073ce  mov     rax, rcx
0x1801073d1  shr     rax, 20h
0x1801073d5  or      [rbx+40h], eax
0x1801073d8  cmp     [rsp+8D0h+pv+8], 0
0x1801073de  jz      short loc_1801073EF
0x1801073e0  lea     rdx, [rsp+8D0h+var_898]
0x1801073e5  mov     rcx, rbx
0x1801073e8  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1801073ed  jmp     short loc_1801073F5
0x1801073ef  mov     [rbx+0B8h], ecx
0x1801073f5  lea     rcx, [rsp+8D0h+var_860]
0x1801073fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801073ff  mov     rcx, [rsp+8D0h+pv+8]; pv
0x180107404  call    cs:__imp_CoTaskMemFree
0x18010740a  dec     dword ptr [rbx+0E8h]
0x180107410  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180107417  call    cs:__imp_LeaveCriticalSection
0x18010741d  nop
0x18010741e  mov     rcx, [rbp+7D0h+var_30]
0x180107425  xor     rcx, rsp; StackCookie
0x180107428  call    __security_check_cookie
0x18010742d  add     rsp, 8B8h
0x180107434  pop     rdi
0x180107435  pop     rsi
0x180107436  pop     rbx
0x180107437  pop     rbp
0x180107438  retn
```
