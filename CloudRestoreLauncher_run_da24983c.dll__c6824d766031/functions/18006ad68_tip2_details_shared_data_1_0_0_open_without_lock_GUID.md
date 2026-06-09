# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x18006ad68`
- end: `0x18006ae8b`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800689f4`

## callees

- `0x18000c6e0`
- `0x18001369c`
- `0x18001ffc8`
- `0x18002374c`
- `0x1800444e8`
- `0x18006ad68`
- `0x18012d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18006adc3`
- `KERNEL32!GetProcAddress` at `0x18006adc3`
- `OLE32!CoTaskMemFree` at `0x18006ae63`
- `OLE32!CoTaskMemFree` at `0x18006ae63`

## string_xrefs

- `0x18006adbc`: `TestOpen`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::open_without_lock(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // si
  unsigned int v6; // r14d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v9; // rax
  __int64 v10; // [rsp+30h] [rbp-40h] BYREF
  __int128 v11; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+48h] [rbp-28h]
  __int128 v13; // [rsp+58h] [rbp-18h]

  v11 = 0;
  *(_OWORD *)pv = 0;
  v13 = 0;
  v5 = *(_BYTE *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestOpen'::`2'::s_pfnTestOpen;
  if ( `TestOpen'::`2'::s_pfnTestOpen
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestOpen"),
        (`TestOpen'::`2'::s_pfnTestOpen = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(a3) = v5;
    v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64, __int128 *))ProcAddress)(v6, 2097154, a3, a2, &v11);
    v10 = v9;
    if ( v9 )
    {
      *(_OWORD *)(a1 + 144) = v11;
      v10 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(
        a1 + 240,
        v9);
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( pv[1] )
        tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v11);
      else
        *(_DWORD *)(a1 + 184) = pv[0];
    }
  }
  else
  {
    v11 = 0;
    *(_OWORD *)pv = 0;
    v13 = 0;
    v10 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(&v10);
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x18006ad68  mov     [rsp-18h+arg_10], rbx
0x18006ad6d  mov     [rsp-18h+arg_18], rsi
0x18006ad72  push    rbp
0x18006ad73  push    rdi
0x18006ad74  push    r14
0x18006ad76  mov     rbp, rsp
0x18006ad79  sub     rsp, 70h
0x18006ad7d  mov     rax, cs:__security_cookie
0x18006ad84  xor     rax, rsp
0x18006ad87  mov     [rbp+var_8], rax
0x18006ad8b  mov     rdi, rdx
0x18006ad8e  mov     rbx, rcx
0x18006ad91  xorps   xmm0, xmm0
0x18006ad94  movups  [rbp+var_38], xmm0
0x18006ad98  movups  xmmword ptr [rbp+pv], xmm0
0x18006ad9c  movups  [rbp+var_18], xmm0
0x18006ada0  mov     sil, [rcx+20h]
0x18006ada4  mov     r14d, [rcx+10h]
0x18006ada8  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18006adaf  test    rax, rax
0x18006adb2  jnz     short loc_18006ADEA
0x18006adb4  call    tip_details_GetKernelBaseModuleHandle
0x18006adb9  mov     rcx, rax; hModule
0x18006adbc  lea     rdx, aTestopen; "TestOpen"
0x18006adc3  call    cs:__imp_GetProcAddress
0x18006adc9  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18006add0  test    rax, rax
0x18006add3  jnz     short loc_18006ADEA
0x18006add5  xorps   xmm0, xmm0
0x18006add8  movups  [rbp+var_38], xmm0
0x18006addc  movups  xmmword ptr [rbp+pv], xmm0
0x18006ade0  movups  [rbp+var_18], xmm0
0x18006ade4  mov     [rbp+var_40], rax
0x18006ade8  jmp     short loc_18006AE56
0x18006adea  lea     rcx, [rbp+var_38]
0x18006adee  mov     [rsp+70h+var_50], rcx
0x18006adf3  mov     r9, rdi
0x18006adf6  mov     r8b, sil
0x18006adf9  mov     edx, 200002h
0x18006adfe  mov     ecx, r14d
0x18006ae01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae06  mov     [rbp+var_40], rax
0x18006ae0a  test    rax, rax
0x18006ae0d  jz      short loc_18006AE56
0x18006ae0f  movups  xmm0, [rbp+var_38]
0x18006ae13  movdqu  xmmword ptr [rbx+90h], xmm0
0x18006ae1b  mov     [rbp+var_40], 0
0x18006ae23  lea     rcx, [rbx+0F0h]
0x18006ae2a  mov     rdx, rax
0x18006ae2d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18006ae32  mov     eax, dword ptr [rbp+pv+4]
0x18006ae35  or      [rbx+40h], eax
0x18006ae38  cmp     [rbp+pv+8], 0
0x18006ae3d  jz      short loc_18006AE4D
0x18006ae3f  lea     rdx, [rbp+var_38]
0x18006ae43  mov     rcx, rbx
0x18006ae46  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18006ae4b  jmp     short loc_18006AE56
0x18006ae4d  mov     eax, dword ptr [rbp+pv]
0x18006ae50  mov     [rbx+0B8h], eax
0x18006ae56  lea     rcx, [rbp+var_40]
0x18006ae5a  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18006ae5f  mov     rcx, [rbp+pv+8]; pv
0x18006ae63  call    cs:__imp_CoTaskMemFree
0x18006ae69  nop
0x18006ae6a  mov     rcx, [rbp+var_8]
0x18006ae6e  xor     rcx, rsp; StackCookie
0x18006ae71  call    __security_check_cookie
0x18006ae76  lea     r11, [rsp+70h+var_s0]
0x18006ae7b  mov     rbx, [r11+30h]
0x18006ae7f  mov     rsi, [r11+38h]
0x18006ae83  mov     rsp, r11
0x18006ae86  pop     r14
0x18006ae88  pop     rdi
0x18006ae89  pop     rbp
0x18006ae8a  retn
```
