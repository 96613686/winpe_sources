# tip2::details::shared_data<1,0,1>::open_without_lock(_GUID *)

- ea: `0x180032528`
- end: `0x1800326d4`
- name: `?open_without_lock@?$shared_data@$00$0A@$00@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800319b0`

## callees

- `0x180004ea0`
- `0x1800137f8`
- `0x180028028`
- `0x180032528`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003259e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032652`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003259e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032652`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032587`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003263b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032587`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003263b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003266e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003266e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032614`
- `ole32!CoTaskMemFree` at `0x1800326ac`
- `ole32!CoTaskMemFree` at `0x1800326ac`

## string_xrefs

- `0x180032580`: `kernelbase.dll`
- `0x180032634`: `kernelbase.dll`
- `0x180032594`: `TestOpen`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,1>::open_without_lock(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // si
  unsigned int v6; // r14d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v9; // r14
  __int64 v10; // rdi
  DWORD LastError; // esi
  FARPROC v12; // rax
  HMODULE v13; // rax
  __int64 v14; // [rsp+30h] [rbp-40h] BYREF
  __int128 v15; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+48h] [rbp-28h]
  __int128 v17; // [rsp+58h] [rbp-18h]

  v15 = 0;
  *(_OWORD *)pv = 0;
  v17 = 0;
  v5 = *(_BYTE *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestOpen'::`2'::s_pfnTestOpen;
  if ( `TestOpen'::`2'::s_pfnTestOpen )
    goto LABEL_6;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestOpen");
  `TestOpen'::`2'::s_pfnTestOpen = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_6:
    LOBYTE(a3) = v5;
    v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64, __int128 *))ProcAddress)(v6, 2097154, a3, a2, &v15);
    v14 = v9;
    if ( v9 )
    {
      *(_OWORD *)(a1 + 144) = v15;
      v14 = 0;
      v10 = *(_QWORD *)(a1 + 240);
      if ( v10 )
      {
        LastError = GetLastError();
        v12 = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
        if ( `TestClose'::`2'::s_pfnTestClose )
          goto LABEL_12;
        v13 = g_tip_details_kernelbaseModuleHandle;
        if ( !g_tip_details_kernelbaseModuleHandle )
        {
          v13 = GetModuleHandleW(L"kernelbase.dll");
          g_tip_details_kernelbaseModuleHandle = v13;
        }
        v12 = GetProcAddress(v13, "TestClose");
        `TestClose'::`2'::s_pfnTestClose = (__int64)v12;
        if ( v12 )
LABEL_12:
          ((void (__fastcall *)(__int64))v12)(v10);
        SetLastError(LastError);
      }
      *(_QWORD *)(a1 + 240) = v9;
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( pv[1] )
        tip2::details::shared_data<1,0,1>::deserialize_data((_QWORD *)a1, (__int64)&v15);
      else
        *(_DWORD *)(a1 + 184) = pv[0];
    }
  }
  else
  {
    v15 = 0;
    *(_OWORD *)pv = 0;
    v17 = 0;
    v14 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(&v14);
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x180032528  mov     [rsp-18h+arg_10], rbx
0x18003252d  mov     [rsp-18h+arg_18], rsi
0x180032532  push    rbp
0x180032533  push    rdi
0x180032534  push    r14
0x180032536  mov     rbp, rsp
0x180032539  sub     rsp, 70h
0x18003253d  mov     rax, cs:__security_cookie
0x180032544  xor     rax, rsp
0x180032547  mov     [rbp+var_8], rax
0x18003254b  mov     rdi, rdx
0x18003254e  mov     rbx, rcx
0x180032551  xorps   xmm0, xmm0
0x180032554  movups  [rbp+var_38], xmm0
0x180032558  movups  xmmword ptr [rbp+pv], xmm0
0x18003255c  movups  [rbp+var_18], xmm0
0x180032560  mov     sil, [rcx+20h]
0x180032564  mov     r14d, [rcx+10h]
0x180032568  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18003256f  test    rax, rax
0x180032572  jnz     short loc_1800325C8
0x180032574  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18003257b  test    rax, rax
0x18003257e  jnz     short loc_180032594
0x180032580  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180032587  call    cs:__imp_GetModuleHandleW
0x18003258d  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180032594  lea     rdx, aTestopen; "TestOpen"
0x18003259b  mov     rcx, rax; hModule
0x18003259e  call    cs:__imp_GetProcAddress
0x1800325a4  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x1800325ab  test    rax, rax
0x1800325ae  jnz     short loc_1800325C8
0x1800325b0  xorps   xmm0, xmm0
0x1800325b3  movups  [rbp+var_38], xmm0
0x1800325b7  movups  xmmword ptr [rbp+pv], xmm0
0x1800325bb  movups  [rbp+var_18], xmm0
0x1800325bf  mov     [rbp+var_40], rax
0x1800325c3  jmp     loc_18003269F
0x1800325c8  lea     rcx, [rbp+var_38]
0x1800325cc  mov     [rsp+70h+var_50], rcx
0x1800325d1  mov     r9, rdi
0x1800325d4  mov     r8b, sil
0x1800325d7  mov     edx, 200002h
0x1800325dc  mov     ecx, r14d
0x1800325df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325e4  mov     r14, rax
0x1800325e7  mov     [rbp+var_40], rax
0x1800325eb  test    rax, rax
0x1800325ee  jz      loc_18003269F
0x1800325f4  movups  xmm0, [rbp+var_38]
0x1800325f8  movdqu  xmmword ptr [rbx+90h], xmm0
0x180032600  mov     [rbp+var_40], 0
0x180032608  mov     rdi, [rbx+0F0h]
0x18003260f  test    rdi, rdi
0x180032612  jz      short loc_180032674
0x180032614  call    cs:__imp_GetLastError
0x18003261a  mov     esi, eax
0x18003261c  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180032623  test    rax, rax
0x180032626  jnz     short loc_180032664
0x180032628  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18003262f  test    rax, rax
0x180032632  jnz     short loc_180032648
0x180032634  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003263b  call    cs:__imp_GetModuleHandleW
0x180032641  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180032648  lea     rdx, aTestclose; "TestClose"
0x18003264f  mov     rcx, rax; hModule
0x180032652  call    cs:__imp_GetProcAddress
0x180032658  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18003265f  test    rax, rax
0x180032662  jz      short loc_18003266C
0x180032664  mov     rcx, rdi
0x180032667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003266c  mov     ecx, esi; dwErrCode
0x18003266e  call    cs:__imp_SetLastError
0x180032674  mov     [rbx+0F0h], r14
0x18003267b  mov     eax, dword ptr [rbp+pv+4]
0x18003267e  or      [rbx+40h], eax
0x180032681  cmp     [rbp+pv+8], 0
0x180032686  jz      short loc_180032696
0x180032688  lea     rdx, [rbp+var_38]
0x18003268c  mov     rcx, rbx
0x18003268f  call    ?deserialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,1>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180032694  jmp     short loc_18003269F
0x180032696  mov     eax, dword ptr [rbp+pv]
0x180032699  mov     [rbx+0B8h], eax
0x18003269f  lea     rcx, [rbp+var_40]
0x1800326a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x1800326a8  mov     rcx, [rbp+pv+8]; pv
0x1800326ac  call    cs:__imp_CoTaskMemFree
0x1800326b2  nop
0x1800326b3  mov     rcx, [rbp+var_8]
0x1800326b7  xor     rcx, rsp; StackCookie
0x1800326ba  call    __security_check_cookie
0x1800326bf  lea     r11, [rsp+70h+var_s0]
0x1800326c4  mov     rbx, [r11+30h]
0x1800326c8  mov     rsi, [r11+38h]
0x1800326cc  mov     rsp, r11
0x1800326cf  pop     r14
0x1800326d1  pop     rdi
0x1800326d2  pop     rbp
0x1800326d3  retn
```
