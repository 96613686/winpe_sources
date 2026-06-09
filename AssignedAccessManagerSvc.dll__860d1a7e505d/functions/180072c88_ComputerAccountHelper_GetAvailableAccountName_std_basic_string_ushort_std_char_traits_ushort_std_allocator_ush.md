# ComputerAccountHelper::GetAvailableAccountName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::function<bool (std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)>)

- ea: `0x180072c88`
- end: `0x180072e77`
- name: `?GetAvailableAccountName@ComputerAccountHelper@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@3@@Z`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a264`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010c98`
- `0x18002001c`
- `0x18002729c`
- `0x180072c88`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072cdc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072cdc`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180072e70`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180072e70`

## string_xrefs

- `0x180072cef`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\computeraccounthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ComputerAccountHelper::GetAvailableAccountName(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT v5; // eax
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __m128i si128; // xmm6
  __int64 v11; // rcx
  __int64 v12; // rax
  int (__fastcall *v13)(__int64, __int64, _QWORD *); // r9
  __int64 v14; // r10
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  int ppv; // [rsp+20h] [rbp-60h]
  LPVOID v20; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v21[2]; // [rsp+38h] [rbp-48h] BYREF
  _OWORD v22[2]; // [rsp+48h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v21[1] = a3;
  v20 = 0;
  v5 = CoCreateInstance(&CLSID_LocalUserAccounts, 0, 3u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &v20);
  v6 = v5;
  if ( v5 >= 0 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v22[0] = 0;
      v22[1] = si128;
      LOWORD(v22[0]) = 0;
      v11 = *(_QWORD *)(a3 + 56);
      if ( !v11 )
      {
        std::_Xbad_function_call();
        JUMPOUT(0x180072E76LL);
      }
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v11 + 16LL))(v11, v22) )
        break;
      v21[0] = 0;
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
      if ( v13(v14, v12, v21) < 0 )
      {
        std::wstring::operator=(a2, v22);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v21);
        break;
      }
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v21);
      std::wstring::_Tidy_deallocate(v22);
    }
    std::wstring::_Tidy_deallocate(v22);
    if ( *(_QWORD *)(a2 + 16) )
    {
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v20);
      v18 = *(_QWORD *)(a3 + 56);
      if ( v18 )
      {
        LOBYTE(v17) = v18 != a3;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 32LL))(v18, v17);
        *(_QWORD *)(a3 + 56) = 0;
      }
      return 0;
    }
    else
    {
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v20);
      v16 = *(_QWORD *)(a3 + 56);
      if ( v16 )
      {
        LOBYTE(v15) = v16 != a3;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 32LL))(v16, v15);
        *(_QWORD *)(a3 + 56) = 0;
      }
      return 2147500037LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\computeraccounthelper.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v20);
    v8 = *(_QWORD *)(a3 + 56);
    if ( v8 )
    {
      LOBYTE(v7) = v8 != a3;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, v7);
      *(_QWORD *)(a3 + 56) = 0;
    }
    return v6;
  }
}

```

## disassembly

```asm
0x180072c88  mov     [rsp-18h+arg_0], rbx
0x180072c8d  push    rbp
0x180072c8e  push    rsi
0x180072c8f  push    rdi
0x180072c90  mov     rbp, rsp
0x180072c93  sub     rsp, 80h
0x180072c9a  movaps  [rsp+80h+var_10], xmm6
0x180072c9f  mov     rax, cs:__security_cookie
0x180072ca6  xor     rax, rsp
0x180072ca9  mov     [rbp+var_18], rax
0x180072cad  mov     rbx, r8
0x180072cb0  mov     rsi, rdx
0x180072cb3  mov     [rbp+var_40], rbx
0x180072cb7  mov     [rbp+var_50], 0
0x180072cbf  lea     rax, [rbp+var_50]
0x180072cc3  mov     qword ptr [rsp+80h+ppv], rax; int
0x180072cc8  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x180072ccf  xor     edx, edx; pUnkOuter
0x180072cd1  lea     r8d, [rdx+3]; dwClsContext
0x180072cd5  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x180072cdc  call    cs:__imp_CoCreateInstance
0x180072ce2  mov     edi, eax
0x180072ce4  test    eax, eax
0x180072ce6  jns     short loc_180072D54
0x180072ce8  mov     rcx, [rbp+18h]; this
0x180072cec  mov     r9d, eax; char *
0x180072cef  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180072cf6  mov     edx, 12h; void *
0x180072cfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072d00  nop
0x180072d01  lea     rcx, [rbp+var_50]
0x180072d05  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072d0a  nop
0x180072d0b  mov     rcx, [rbx+38h]
0x180072d0f  test    rcx, rcx
0x180072d12  jz      short loc_180072D2E
0x180072d14  mov     rax, [rcx]
0x180072d17  cmp     rcx, rbx
0x180072d1a  setnz   dl
0x180072d1d  mov     rax, [rax+20h]
0x180072d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072d26  mov     qword ptr [rbx+38h], 0
0x180072d2e  mov     eax, edi
0x180072d30  mov     rcx, [rbp+var_18]
0x180072d34  xor     rcx, rsp; StackCookie
0x180072d37  call    __security_check_cookie
0x180072d3c  mov     rbx, [rsp+80h+arg_0]
0x180072d44  movaps  xmm6, [rsp+80h+var_10]
0x180072d49  add     rsp, 80h
0x180072d50  pop     rdi
0x180072d51  pop     rsi
0x180072d52  pop     rbp
0x180072d53  retn
0x180072d54  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180072d5c  xorps   xmm0, xmm0
0x180072d5f  movups  [rbp+var_38], xmm0
0x180072d63  movdqu  [rbp+var_28], xmm6
0x180072d68  xor     eax, eax
0x180072d6a  mov     word ptr [rbp+var_38], ax
0x180072d6e  mov     rcx, [rbx+38h]
0x180072d72  test    rcx, rcx
0x180072d75  jz      loc_180072E70
0x180072d7b  mov     rax, [rcx]
0x180072d7e  lea     rdx, [rbp+var_38]
0x180072d82  mov     rax, [rax+10h]
0x180072d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072d8b  test    al, al
0x180072d8d  jz      short loc_180072DF8
0x180072d8f  mov     [rbp+var_48], 0
0x180072d97  mov     r10, [rbp+var_50]
0x180072d9b  mov     rax, [r10]
0x180072d9e  mov     r9, [rax+48h]
0x180072da2  mov     [rbp+var_48], 0
0x180072daa  lea     rcx, [rbp+var_38]
0x180072dae  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180072db3  mov     rdx, rax
0x180072db6  lea     r8, [rbp+var_48]
0x180072dba  mov     rcx, r10
0x180072dbd  mov     rax, r9
0x180072dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072dc5  test    eax, eax
0x180072dc7  js      short loc_180072DE1
0x180072dc9  lea     rcx, [rbp+var_48]
0x180072dcd  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072dd2  nop
0x180072dd3  lea     rcx, [rbp+var_38]
0x180072dd7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180072ddc  jmp     loc_180072D5C
0x180072de1  lea     rdx, [rbp+var_38]
0x180072de5  mov     rcx, rsi
0x180072de8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180072ded  nop
0x180072dee  lea     rcx, [rbp+var_48]
0x180072df2  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072df7  nop
0x180072df8  lea     rcx, [rbp+var_38]
0x180072dfc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180072e01  nop
0x180072e02  lea     rcx, [rbp+var_50]
0x180072e06  cmp     qword ptr [rsi+10h], 0
0x180072e0b  jnz     short loc_180072E40
0x180072e0d  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072e12  nop
0x180072e13  mov     rcx, [rbx+38h]
0x180072e17  test    rcx, rcx
0x180072e1a  jz      short loc_180072E36
0x180072e1c  mov     rax, [rcx]
0x180072e1f  cmp     rcx, rbx
0x180072e22  setnz   dl
0x180072e25  mov     rax, [rax+20h]
0x180072e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e2e  mov     qword ptr [rbx+38h], 0
0x180072e36  mov     eax, 80004005h
0x180072e3b  jmp     loc_180072D30
0x180072e40  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072e45  nop
0x180072e46  mov     rcx, [rbx+38h]
0x180072e4a  test    rcx, rcx
0x180072e4d  jz      short loc_180072E69
0x180072e4f  mov     rax, [rcx]
0x180072e52  cmp     rcx, rbx
0x180072e55  setnz   dl
0x180072e58  mov     rax, [rax+20h]
0x180072e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e61  mov     qword ptr [rbx+38h], 0
0x180072e69  xor     eax, eax
0x180072e6b  jmp     loc_180072D30
0x180072e70  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
