# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetFlightRing(void)

- ea: `0x180021404`
- end: `0x1800216cd`
- name: `?GetFlightRing@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA?AUhstring@6@XZ`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update`

## callers

- `0x1800213b0`

## callees

- `0x180002dc0`
- `0x180003984`
- `0x1800039d8`
- `0x180004b90`
- `0x180005954`
- `0x180008a80`
- `0x180008adc`
- `0x180008cec`
- `0x180008e28`
- `0x18001d428`
- `0x18001f214`
- `0x18001f318`
- `0x18001f378`
- `0x180021404`
- `0x180022cd0`
- `0x1800233a4`
- `0x1800257c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800214cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800215dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800214cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800215dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
winrt::impl *__fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetFlightRing(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1,
        winrt::impl *a2)
{
  bool IsIotCoreEdition; // al
  const WCHAR *v5; // rax
  LPCWSTR v6; // r8
  unsigned int ValueW; // eax
  unsigned int v8; // r8d
  winrt::impl *result; // rax
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rsi
  _QWORD *v12; // rbx
  const WCHAR *v13; // rax
  LPCWSTR v14; // r8
  PVOID pvData; // r10
  unsigned int v16; // eax
  unsigned int v17; // r8d
  const unsigned __int16 *v18; // rax
  const struct winrt::impl::slim_source_location *v19; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-C8h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-C8h]
  DWORD pcbData; // [rsp+40h] [rbp-A8h] BYREF
  winrt::impl *v23[2]; // [rsp+48h] [rbp-A0h] BYREF
  winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *v24; // [rsp+58h] [rbp-90h]
  const wil::ResultException *v25; // [rsp+60h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+68h] [rbp-80h] BYREF
  _BYTE v27[24]; // [rsp+80h] [rbp-68h] BYREF
  char v28[24]; // [rsp+98h] [rbp-50h] BYREF
  void *Src[2]; // [rsp+B0h] [rbp-38h] BYREF
  unsigned __int64 v30; // [rsp+C0h] [rbp-28h]
  unsigned __int64 v31; // [rsp+C8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v24 = a1;
  v23[0] = a2;
  IsIotCoreEdition = winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsIotCoreEdition(a1);
  try
  {
    if ( !IsIotCoreEdition )
    {
      winrt::Windows::System::Update::factory_implementation::hresult_not_supported::hresult_not_supported((winrt::Windows::System::Update::factory_implementation::hresult_not_supported *)pExceptionObject);
      throw (winrt::Windows::System::Update::factory_implementation::hresult_not_supported *)pExceptionObject;
    }
    if ( !winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::HasSystemManagementCapability(a1) )
    {
      v19 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v28);
      winrt::hresult_access_denied::hresult_access_denied((winrt::hresult_access_denied *)v27, v19);
      throw (winrt::hresult_access_denied *)v27;
    }
    *(_OWORD *)Src = 0;
    v30 = 0;
    v31 = 7;
    LOWORD(Src[0]) = 0;
    pcbData = 0;
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042A90);
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042A50);
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v5, v6, 2u, 0, 0, &pcbData);
    if ( ValueW == 2 )
    {
      *(_QWORD *)a2 = 0;
      std::wstring::_Tidy_deallocate(Src);
      result = a2;
    }
    else
    {
      if ( ValueW )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x365, v8, (const char *)ValueW, pdwType);
      v10 = (unsigned __int64)pcbData >> 1;
      v11 = v30;
      if ( v30 <= v10 && v31 != v10 )
      {
        if ( v31 >= v10 )
        {
          if ( v10 <= 7 && v31 > 7 )
          {
            v12 = Src[0];
            memcpy_0(Src, Src[0], 2 * v30 + 2);
            std::_Deallocate<16>(v12, 2 * v31 + 2);
            v31 = 7;
          }
        }
        else
        {
          std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(Src);
          v30 = v11;
        }
      }
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042A90);
      v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042A50);
      v16 = RegGetValueW(HKEY_LOCAL_MACHINE, v13, v14, 2u, 0, pvData, &pcbData);
      if ( v16 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x369, v17, (const char *)v16, pdwTypea);
      v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      winrt::hstring::hstring((winrt::hstring *)v23, v18);
      winrt::hstring::hstring(a2, v23);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v23);
      std::wstring::_Tidy_deallocate(Src);
      result = a2;
    }
  }
  catch ( const wil::ResultException *v25 )
  {
    *((_DWORD *)v24 + 14) = wil::ResultException::GetErrorCode(v25);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180021404  mov     [rsp+arg_10], rbx
0x180021409  mov     [rsp+arg_18], rsi
0x18002140e  push    rdi
0x18002140f  sub     rsp, 0E0h
0x180021416  mov     rax, cs:__security_cookie
0x18002141d  xor     rax, rsp
0x180021420  mov     [rsp+0E8h+var_18], rax
0x180021428  mov     rdi, rdx
0x18002142b  mov     rbx, rcx
0x18002142e  mov     [rsp+0E8h+var_90], rcx
0x180021433  mov     [rsp+0E8h+var_A0], rdx
0x180021438  call    ?IsIotCoreEdition@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsIotCoreEdition(void)
0x18002143d  test    al, al
0x18002143f  jz      loc_18002165C
0x180021445  mov     rcx, rbx; this
0x180021448  call    ?HasSystemManagementCapability@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::HasSystemManagementCapability(void)
0x18002144d  test    al, al
0x18002144f  jz      loc_180021677
0x180021455  xorps   xmm0, xmm0
0x180021458  movups  xmmword ptr [rsp+0E8h+Src], xmm0
0x180021460  mov     [rsp+0E8h+var_28], 0
0x18002146c  mov     [rsp+0E8h+var_20], 7
0x180021478  xor     eax, eax
0x18002147a  mov     word ptr [rsp+0E8h+Src], ax
0x180021482  mov     [rsp+0E8h+var_A8], eax
0x180021486  lea     rcx, qword_180042A90
0x18002148d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021492  mov     r8, rax
0x180021495  lea     rcx, qword_180042A50
0x18002149c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800214a1  mov     rdx, rax; lpSubKey
0x1800214a4  lea     rax, [rsp+0E8h+var_A8]
0x1800214a9  mov     [rsp+0E8h+pcbData], rax; pcbData
0x1800214ae  mov     [rsp+0E8h+pvData], 0; pvData
0x1800214b7  mov     [rsp+0E8h+pdwType], 0; unsigned int
0x1800214c0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800214c7  mov     r9d, 2; dwFlags
0x1800214cd  call    cs:__imp_RegGetValueW
0x1800214d3  cmp     eax, 2
0x1800214d6  jnz     short loc_1800214F2
0x1800214d8  xor     eax, eax
0x1800214da  mov     [rdi], rax
0x1800214dd  lea     rcx, [rsp+0E8h+Src]
0x1800214e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800214ea  mov     rax, rdi
0x1800214ed  jmp     loc_180021637
0x1800214f2  test    eax, eax
0x1800214f4  jnz     loc_1800216A9
0x1800214fa  mov     eax, [rsp+0E8h+var_A8]
0x1800214fe  shr     rax, 1
0x180021501  mov     rsi, [rsp+0E8h+var_28]
0x180021509  cmp     rsi, rax
0x18002150c  ja      short loc_18002158A
0x18002150e  mov     rcx, [rsp+0E8h+var_20]
0x180021516  cmp     rcx, rax
0x180021519  jz      short loc_18002158A
0x18002151b  jnb     short loc_18002153A
0x18002151d  sub     rax, rsi
0x180021520  mov     rdx, rax
0x180021523  lea     rcx, [rsp+0E8h+Src]; Src
0x18002152b  call    ??$_Reallocate_grow_by@V_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(unsigned __int64,_lambda_7f96eb1dcf99da5daec8c2467d2d5499_)
0x180021530  mov     [rsp+0E8h+var_28], rsi
0x180021538  jmp     short loc_18002158A
0x18002153a  cmp     rax, 7
0x18002153e  ja      short loc_18002158A
0x180021540  cmp     rcx, 7
0x180021544  jbe     short loc_18002158A
0x180021546  mov     rbx, [rsp+0E8h+Src]
0x18002154e  lea     r8, ds:2[rsi*2]; Size
0x180021556  mov     rdx, rbx; Src
0x180021559  lea     rcx, [rsp+0E8h+Src]; void *
0x180021561  call    memcpy_0
0x180021566  mov     rdx, [rsp+0E8h+var_20]
0x18002156e  lea     rdx, ds:2[rdx*2]
0x180021576  mov     rcx, rbx
0x180021579  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002157e  mov     [rsp+0E8h+var_20], 7
0x18002158a  lea     rcx, [rsp+0E8h+Src]
0x180021592  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021597  mov     r10, rax
0x18002159a  lea     rcx, qword_180042A90
0x1800215a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800215a6  mov     r8, rax
0x1800215a9  lea     rcx, qword_180042A50
0x1800215b0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800215b5  mov     rdx, rax; lpSubKey
0x1800215b8  lea     rax, [rsp+0E8h+var_A8]
0x1800215bd  mov     [rsp+0E8h+pcbData], rax; pcbData
0x1800215c2  mov     [rsp+0E8h+pvData], r10; pvData
0x1800215c7  mov     [rsp+0E8h+pdwType], 0; unsigned int
0x1800215d0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800215d7  mov     r9d, 2; dwFlags
0x1800215dd  call    cs:__imp_RegGetValueW
0x1800215e3  mov     rcx, [rsp+0E8h]; this
0x1800215eb  test    eax, eax
0x1800215ed  jnz     loc_1800216BE
0x1800215f3  lea     rcx, [rsp+0E8h+Src]
0x1800215fb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021600  mov     rdx, rax; unsigned __int16 *
0x180021603  lea     rcx, [rsp+0E8h+var_A0]; this
0x180021608  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18002160d  nop
0x18002160e  lea     rdx, [rsp+0E8h+var_A0]; struct winrt::hstring *
0x180021613  mov     rcx, rdi; this
0x180021616  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18002161b  nop
0x18002161c  lea     rcx, [rsp+0E8h+var_A0]
0x180021621  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180021626  nop
0x180021627  lea     rcx, [rsp+0E8h+Src]
0x18002162f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021634  mov     rax, rdi
0x180021637  mov     rcx, [rsp+0E8h+var_18]
0x18002163f  xor     rcx, rsp; StackCookie
0x180021642  call    __security_check_cookie
0x180021647  lea     r11, [rsp+0E8h+var_8]
0x18002164f  mov     rbx, [r11+20h]
0x180021653  mov     rsi, [r11+28h]
0x180021657  mov     rsp, r11
0x18002165a  pop     rdi
0x18002165b  retn
0x18002165c  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x180021661  call    ??0hresult_not_supported@factory_implementation@Update@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::Update::factory_implementation::hresult_not_supported::hresult_not_supported(void)
0x180021666  lea     rdx, _TI2?AUhresult_not_supported@factory_implementation@Update@System@Windows@winrt@@; pThrowInfo
0x18002166d  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180021672  call    _CxxThrowException_0
0x180021677  lea     rcx, [rsp+0E8h+var_50]
0x18002167f  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180021684  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180021687  lea     rcx, [rsp+0E8h+var_68]; this
0x18002168f  call    ??0hresult_access_denied@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::impl::slim_source_location const &)
0x180021694  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x18002169b  lea     rcx, [rsp+0E8h+var_68]; pExceptionObject
0x1800216a3  call    _CxxThrowException_0
0x1800216a9  mov     rcx, [rsp+0E8h]; this
0x1800216b1  mov     r9d, eax; char *
0x1800216b4  mov     edx, 365h; void *
0x1800216b9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800216be  mov     r9d, eax; char *
0x1800216c1  mov     edx, 369h; void *
0x1800216c6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
