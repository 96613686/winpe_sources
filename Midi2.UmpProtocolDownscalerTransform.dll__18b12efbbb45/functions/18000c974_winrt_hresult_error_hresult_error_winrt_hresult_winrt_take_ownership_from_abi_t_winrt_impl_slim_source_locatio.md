# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x18000c974`
- end: `0x18000cbb4`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `576`
- prototype: ``
- caller_count: `14`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000c868`
- `0x18000c8d4`
- `0x18000c8fc`
- `0x18000c924`
- `0x18000c94c`
- `0x18000cbbc`
- `0x18000cc28`
- `0x18000cc50`
- `0x18000cc78`
- `0x18000cce4`
- `0x18000cd0c`
- `0x18000cd78`
- `0x18000cda0`
- `0x180011a4c`

## callees

- `0x180003ab0`
- `0x180003b04`
- `0x180003b1c`
- `0x180003b40`
- `0x180003b55`
- `0x180009ce8`
- `0x18000c974`
- `0x1800115e4`
- `0x1800116c4`
- `0x180011e0c`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000cbad`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000cbad`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000cb00`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000cb00`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 *v7; // rbx
  BSTR v8; // r14
  __int64 v9; // r15
  __int64 v10; // rdi
  void (__fastcall *v11)(__int64, __int64); // r14
  void (__fastcall ***v12)(_QWORD, __int64 *, BSTR *); // rcx
  volatile signed __int32 *v13; // rbx
  UINT v14; // r14d
  BSTR v15; // r15
  OLECHAR *v16; // rbx
  const char *v17; // rdx
  int v18; // eax
  HANDLE ProcessHeap; // rax
  BSTR pbstr; // [rsp+20h] [rbp-10h] BYREF
  BSTR v22; // [rsp+28h] [rbp-8h] BYREF
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp+30h] BYREF

  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = -1430532899;
  *(_DWORD *)(a1 + 12) = a2;
  v7 = (__int64 *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  if ( pperrinfo )
  {
    pbstr = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, BSTR *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &pbstr);
    v8 = pbstr;
    v22 = pbstr;
  }
  else
  {
    v22 = 0;
    v8 = 0;
  }
  if ( v7 == (__int64 *)&v22 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v22);
  }
  else
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
    *v7 = (__int64)v8;
    v9 = (__int64)v8;
  }
  if ( v9 )
  {
    v10 = *v7;
    v11 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*v7 + 32LL);
    if ( *(_QWORD *)a1 )
    {
      WINRT_IMPL_SysFreeString(*(BSTR *)a1);
      *(_QWORD *)a1 = 0;
    }
    v11(v10, a1);
    v12 = (void (__fastcall ***)(_QWORD, __int64 *, BSTR *))*v7;
    if ( *v7 )
    {
      pbstr = 0;
      (**v12)(v12, winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>, &pbstr);
      if ( pbstr )
      {
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstr + 40LL))(pbstr, 0);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pbstr);
      }
    }
  }
  else
  {
    pbstr = 0;
    if ( pperrinfo )
    {
      ((void (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &pbstr);
      v13 = 0;
      if ( pbstr )
      {
        v14 = SysStringLen_0(pbstr);
        v15 = pbstr;
        v16 = &pbstr[v14 - 1];
        if ( v14 )
        {
          while ( (unsigned int)_o_iswspace(*v16) )
          {
            --v16;
            if ( !--v14 )
              goto LABEL_21;
          }
          v13 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)v14, v17);
          memcpy_s((void *const)(v13 + 7), 2LL * v14, v15, 2LL * v14);
        }
        else
        {
LABEL_21:
          v13 = 0;
        }
      }
    }
    else
    {
      v13 = 0;
    }
    winrt::hresult_error::originate(a1, a2, v13, a4);
    if ( v13 )
    {
      v18 = _InterlockedDecrement(v13 + 6);
      if ( v18 )
      {
        if ( v18 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v13);
      }
    }
    if ( pbstr )
      WINRT_IMPL_SysFreeString(pbstr);
  }
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000c974  mov     [rsp-28h+arg_8], rbx
0x18000c979  mov     [rsp-28h+arg_10], rsi
0x18000c97e  push    rbp
0x18000c97f  push    rdi
0x18000c980  push    r12
0x18000c982  push    r14
0x18000c984  push    r15
0x18000c986  mov     rbp, rsp
0x18000c989  sub     rsp, 30h
0x18000c98d  mov     r12, r9
0x18000c990  mov     edi, edx
0x18000c992  mov     rsi, rcx
0x18000c995  mov     qword ptr [rcx], 0
0x18000c99c  mov     dword ptr [rcx+8], 0AABBCCDDh
0x18000c9a3  mov     [rcx+0Ch], edx
0x18000c9a6  lea     rbx, [rcx+10h]
0x18000c9aa  mov     qword ptr [rbx], 0
0x18000c9b1  mov     [rbp+pperrinfo], 0
0x18000c9b9  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000c9bd  xor     ecx, ecx; dwReserved
0x18000c9bf  call    GetErrorInfo_0
0x18000c9c4  mov     rcx, [rbp+pperrinfo]
0x18000c9c8  test    rcx, rcx
0x18000c9cb  jnz     short loc_18000C9D6
0x18000c9cd  mov     [rbp+var_8], rcx
0x18000c9d1  xor     r14d, r14d
0x18000c9d4  jmp     short loc_18000C9FC
0x18000c9d6  mov     [rbp+pbstr], 0
0x18000c9de  mov     rax, [rcx]
0x18000c9e1  lea     r8, [rbp+pbstr]
0x18000c9e5  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x18000c9ec  mov     rax, [rax]
0x18000c9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9f4  mov     r14, [rbp+pbstr]
0x18000c9f8  mov     [rbp+var_8], r14
0x18000c9fc  lea     rax, [rbp+var_8]
0x18000ca00  cmp     rbx, rax
0x18000ca03  jz      short loc_18000CA1B
0x18000ca05  cmp     qword ptr [rbx], 0
0x18000ca09  jz      short loc_18000CA13
0x18000ca0b  mov     rcx, rbx
0x18000ca0e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ca13  mov     [rbx], r14
0x18000ca16  mov     r15, r14
0x18000ca19  jmp     short loc_18000CA2C
0x18000ca1b  mov     r15, [rbx]
0x18000ca1e  test    r14, r14
0x18000ca21  jz      short loc_18000CA2C
0x18000ca23  lea     rcx, [rbp+var_8]
0x18000ca27  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ca2c  test    r15, r15
0x18000ca2f  jz      loc_18000CAB8
0x18000ca35  mov     rdi, [rbx]
0x18000ca38  mov     rax, [rdi]
0x18000ca3b  mov     r14, [rax+20h]
0x18000ca3f  mov     rcx, [rsi]; bstrString
0x18000ca42  test    rcx, rcx
0x18000ca45  jz      short loc_18000CA53
0x18000ca47  call    WINRT_IMPL_SysFreeString
0x18000ca4c  mov     qword ptr [rsi], 0
0x18000ca53  mov     rdx, rsi
0x18000ca56  mov     rcx, rdi
0x18000ca59  mov     rax, r14
0x18000ca5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca61  mov     rcx, [rbx]
0x18000ca64  test    rcx, rcx
0x18000ca67  jz      loc_18000CB7F
0x18000ca6d  mov     [rbp+pbstr], 0
0x18000ca75  mov     rax, [rcx]
0x18000ca78  lea     r8, [rbp+pbstr]
0x18000ca7c  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x18000ca83  mov     rax, [rax]
0x18000ca86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca8b  mov     rcx, [rbp+pbstr]
0x18000ca8f  mov     [rbp+pbstr], rcx
0x18000ca93  test    rcx, rcx
0x18000ca96  jz      loc_18000CB7F
0x18000ca9c  mov     rax, [rcx]
0x18000ca9f  xor     edx, edx
0x18000caa1  mov     rax, [rax+28h]
0x18000caa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caaa  lea     rcx, [rbp+pbstr]
0x18000caae  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000cab3  jmp     loc_18000CB7F
0x18000cab8  mov     [rbp+pbstr], 0
0x18000cac0  mov     rcx, [rbp+pperrinfo]
0x18000cac4  test    rcx, rcx
0x18000cac7  jz      short loc_18000CB3A
0x18000cac9  mov     rax, [rcx]
0x18000cacc  lea     rdx, [rbp+pbstr]
0x18000cad0  mov     rax, [rax+28h]
0x18000cad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cad9  xor     ebx, ebx
0x18000cadb  mov     rcx, [rbp+pbstr]; pbstr
0x18000cadf  test    rcx, rcx
0x18000cae2  jz      short loc_18000CB3C
0x18000cae4  call    SysStringLen_0
0x18000cae9  mov     r14d, eax
0x18000caec  mov     r15, [rbp+pbstr]
0x18000caf0  mov     ebx, eax
0x18000caf2  dec     rbx
0x18000caf5  lea     rbx, [r15+rbx*2]
0x18000caf9  test    eax, eax
0x18000cafb  jz      short loc_18000CB14
0x18000cafd  movzx   ecx, word ptr [rbx]
0x18000cb00  call    cs:__imp__o_iswspace
0x18000cb06  test    eax, eax
0x18000cb08  jz      short loc_18000CB18
0x18000cb0a  sub     rbx, 2
0x18000cb0e  add     r14d, 0FFFFFFFFh
0x18000cb12  jnz     short loc_18000CAFD
0x18000cb14  xor     ebx, ebx
0x18000cb16  jmp     short loc_18000CB3C
0x18000cb18  mov     ecx, r14d; this
0x18000cb1b  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18000cb20  mov     rbx, rax
0x18000cb23  mov     edx, r14d
0x18000cb26  add     rdx, rdx; DestinationSize
0x18000cb29  lea     rcx, [rax+1Ch]; Destination
0x18000cb2d  mov     r9, rdx; SourceSize
0x18000cb30  mov     r8, r15; Source
0x18000cb33  call    memcpy_s
0x18000cb38  jmp     short loc_18000CB16
0x18000cb3a  xor     ebx, ebx
0x18000cb3c  mov     r9, r12
0x18000cb3f  mov     r8, rbx
0x18000cb42  mov     edx, edi
0x18000cb44  mov     rcx, rsi
0x18000cb47  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18000cb4c  test    rbx, rbx
0x18000cb4f  jz      short loc_18000CB71
0x18000cb51  or      eax, 0FFFFFFFFh
0x18000cb54  lock xadd [rbx+18h], eax
0x18000cb59  sub     eax, 1
0x18000cb5c  jnz     short loc_18000CBA9
0x18000cb5e  nop
0x18000cb5f  call    WINRT_IMPL_GetProcessHeap
0x18000cb64  mov     rcx, rax; hHeap
0x18000cb67  mov     r8, rbx; lpMem
0x18000cb6a  xor     edx, edx; dwFlags
0x18000cb6c  call    WINRT_IMPL_HeapFree
0x18000cb71  mov     rcx, [rbp+pbstr]; bstrString
0x18000cb75  test    rcx, rcx
0x18000cb78  jz      short loc_18000CB7F
0x18000cb7a  call    WINRT_IMPL_SysFreeString
0x18000cb7f  cmp     [rbp+pperrinfo], 0
0x18000cb84  jz      short loc_18000CB8F
0x18000cb86  lea     rcx, [rbp+pperrinfo]
0x18000cb8a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000cb8f  mov     rax, rsi
0x18000cb92  mov     rbx, [rsp+30h+arg_8]
0x18000cb97  mov     rsi, [rsp+30h+arg_10]
0x18000cb9c  add     rsp, 30h
0x18000cba0  pop     r15
0x18000cba2  pop     r14
0x18000cba4  pop     r12
0x18000cba6  pop     rdi
0x18000cba7  pop     rbp
0x18000cba8  retn
0x18000cba9  test    eax, eax
0x18000cbab  jns     short loc_18000CB71
0x18000cbad  call    cs:__imp_abort
```
