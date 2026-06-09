# Pal::NetworkRequestInternalWinHttpService::sendRequestAsUser(_WINHTTP_URL_COMPONENTS const &,std::shared_ptr<std::vector<Pal::HttpHeader,std::allocator<Pal::HttpHeader>>> const &)

- ea: `0x180037790`
- end: `0x1800379ce`
- name: `?sendRequestAsUser@NetworkRequestInternalWinHttpService@Pal@@MEAAKAEBU_WINHTTP_URL_COMPONENTS@@AEBV?$shared_ptr@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@std@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000d090`
- `0x18000d49c`
- `0x1800126c4`
- `0x180012720`
- `0x180016500`
- `0x180019f3c`
- `0x18001b9e0`
- `0x180032c1c`
- `0x180032ce0`
- `0x180033710`
- `0x180034d84`
- `0x180037350`
- `0x180037790`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003793c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003793c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003792e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003792e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Pal::NetworkRequestInternalWinHttpService::sendRequestAsUser(
        DWORD_PTR dwContext,
        __int64 a2,
        __int64 **a3)
{
  char *v6; // r15
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  std::_Ref_count_base *v11; // rcx
  __int64 *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  void *v16; // rax
  signed int LastError; // eax
  __int128 *v18; // [rsp+20h] [rbp-59h] BYREF
  __int64 v19; // [rsp+28h] [rbp-51h] BYREF
  __int64 *v20; // [rsp+30h] [rbp-49h] BYREF
  DWORD_PTR dwContexta; // [rsp+38h] [rbp-41h]
  _BYTE v22[16]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v23; // [rsp+50h] [rbp-29h]
  __int128 v24; // [rsp+60h] [rbp-19h] BYREF
  _OWORD v25[2]; // [rsp+70h] [rbp-9h]

  if ( qword_1800F1358 )
  {
    v6 = (char *)operator new(0x28u);
    v18 = (__int128 *)v6;
    *(_OWORD *)v6 = 0;
    *((_DWORD *)v6 + 2) = 1;
    *((_DWORD *)v6 + 3) = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj2<std::vector<Pal::HttpHeader>>::`vftable';
    std::_Construct_in_place<std::vector<Pal::HttpHeader>,>(v6 + 16);
    v20 = (__int64 *)(v6 + 16);
    dwContexta = (DWORD_PTR)v6;
    v19 = 0;
    v7 = qword_1800F1358;
    v8 = **(__int64 (__fastcall ***)(__int64, __int64 *))qword_1800F1358;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    v9 = v8(v7, &v19);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v24 = *(_OWORD *)L"Windows.GenericClient";
      v25[0] = *(_OWORD *)L"GenericClient";
      *(_OWORD *)((char *)v25 + 12) = *(_OWORD *)L"cClient";
      v18 = &v24;
      *(_BYTE *)(dwContext + 464) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19) != 0;
      v13 = *a3;
      if ( *a3 && v6 + 16 != (char *)v13 )
        std::vector<Pal::HttpHeader>::_Assign_counted_range<Pal::HttpHeader *>(v6 + 16, *v13, (v13[1] - *v13) >> 6);
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 40LL))(v19);
      std::wstring::wstring(v22, v14);
      if ( v23 )
        v18 = (__int128 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
      std::vector<Pal::HttpHeader>::emplace_back<unsigned short const (&)[16],unsigned short const * &>(
        v6 + 16,
        v15,
        &v18);
      if ( v19 && (v16 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19)) != 0 )
      {
        if ( ImpersonateLoggedOnUser(v16) )
        {
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
        }
        LODWORD(v18) = LastError;
      }
      else
      {
        LODWORD(v18) = -2147023888;
      }
      v10 = Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(dwContext, a2, &v20);
      Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(&v18);
      std::wstring::_Tidy_deallocate(v22);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      v11 = (std::_Ref_count_base *)dwContexta;
      if ( !dwContexta )
        return v10;
    }
    else
    {
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        v10 = (unsigned __int16)v9;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      v11 = (std::_Ref_count_base *)v6;
    }
    std::_Ref_count_base::_Decref(v11);
    return v10;
  }
  *(_BYTE *)(dwContext + 464) = 1;
  return Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(dwContext, a2, a3);
}

```

## disassembly

```asm
0x180037790  mov     [rsp-8+arg_18], rbx
0x180037795  push    rbp
0x180037796  push    rsi
0x180037797  push    rdi
0x180037798  push    r12
0x18003779a  push    r13
0x18003779c  push    r14
0x18003779e  push    r15
0x1800377a0  lea     rbp, [rsp-27h]
0x1800377a5  sub     rsp, 0A0h
0x1800377ac  mov     rax, cs:__security_cookie
0x1800377b3  xor     rax, rsp
0x1800377b6  mov     [rbp+57h+var_40], rax
0x1800377ba  mov     r12, r8
0x1800377bd  mov     r13, rdx
0x1800377c0  mov     r14, rcx
0x1800377c3  xor     ebx, ebx
0x1800377c5  cmp     cs:qword_1800F1358, rbx
0x1800377cc  jz      loc_18003799B
0x1800377d2  lea     ecx, [rbx+28h]; Size
0x1800377d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800377da  mov     r15, rax
0x1800377dd  mov     [rbp+57h+var_B0], rax
0x1800377e1  xorps   xmm0, xmm0
0x1800377e4  movups  xmmword ptr [rax], xmm0
0x1800377e7  mov     dword ptr [rax+8], 1
0x1800377ee  mov     dword ptr [rax+0Ch], 1
0x1800377f5  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<Pal::HttpHeader>>::`vftable'
0x1800377fc  mov     [r15], rax
0x1800377ff  lea     rsi, [r15+10h]
0x180037803  mov     rcx, rsi
0x180037806  call    ??$_Construct_in_place@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@$$V@std@@YAXAEAV?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@0@@Z; std::_Construct_in_place<std::vector<Pal::HttpHeader>,>(std::vector<Pal::HttpHeader> &)
0x18003780b  mov     [rbp+57h+var_A0], rsi
0x18003780f  mov     [rbp+57h+dwContext], r15
0x180037813  mov     [rbp+57h+var_A8], rbx
0x180037817  mov     rdi, cs:qword_1800F1358
0x18003781e  mov     rax, [rdi]
0x180037821  mov     rbx, [rax]
0x180037824  lea     rcx, [rbp+57h+var_A8]
0x180037828  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003782d  lea     rdx, [rbp+57h+var_A8]
0x180037831  mov     rcx, rdi
0x180037834  mov     rax, rbx
0x180037837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003783c  mov     ebx, eax
0x18003783e  test    eax, eax
0x180037840  jns     short loc_18003786A
0x180037842  and     eax, 1FFF0000h
0x180037847  cmp     eax, 70000h
0x18003784c  jnz     short loc_180037851
0x18003784e  movzx   ebx, bx
0x180037851  lea     rcx, [rbp+57h+var_A8]
0x180037855  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003785a  nop
0x18003785b  mov     rcx, r15; this
0x18003785e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037863  mov     eax, ebx
0x180037865  jmp     loc_1800379A7
0x18003786a  movups  xmm0, xmmword ptr cs:aWindowsGeneric; "Windows.GenericClient"
0x180037871  movups  [rbp+57h+var_70], xmm0
0x180037875  movups  xmm1, xmmword ptr cs:aWindowsGeneric+10h; "GenericClient"
0x18003787c  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x180037880  movups  xmm0, xmmword ptr cs:aWindowsGeneric+1Ch; "cClient"
0x180037887  movups  xmmword ptr [rbp+57h+var_60+0Ch], xmm0
0x18003788b  lea     rax, [rbp+57h+var_70]
0x18003788f  mov     [rbp+57h+var_B0], rax
0x180037893  mov     rcx, [rbp+57h+var_A8]
0x180037897  mov     rax, [rcx]
0x18003789a  mov     rax, [rax+18h]
0x18003789e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378a3  test    rax, rax
0x1800378a6  setnz   al
0x1800378a9  mov     [r14+1D0h], al
0x1800378b0  mov     rdx, [r12]
0x1800378b4  test    rdx, rdx
0x1800378b7  jz      short loc_1800378D4
0x1800378b9  cmp     rsi, rdx
0x1800378bc  jz      short loc_1800378D4
0x1800378be  mov     r8, [rdx+8]
0x1800378c2  sub     r8, [rdx]
0x1800378c5  sar     r8, 6
0x1800378c9  mov     rdx, [rdx]
0x1800378cc  mov     rcx, rsi
0x1800378cf  call    ??$_Assign_counted_range@PEAVHttpHeader@Pal@@@?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@AEAAXPEAVHttpHeader@Pal@@_K@Z; std::vector<Pal::HttpHeader>::_Assign_counted_range<Pal::HttpHeader *>(Pal::HttpHeader *,unsigned __int64)
0x1800378d4  mov     rcx, [rbp+57h+var_A8]
0x1800378d8  mov     rax, [rcx]
0x1800378db  mov     rax, [rax+28h]
0x1800378df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378e4  mov     rdx, rax
0x1800378e7  lea     rcx, [rbp+57h+var_90]
0x1800378eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800378f0  nop
0x1800378f1  cmp     [rbp+57h+var_80], 0
0x1800378f6  jz      short loc_180037905
0x1800378f8  lea     rcx, [rbp+57h+var_90]
0x1800378fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037901  mov     [rbp+57h+var_B0], rax
0x180037905  lea     r8, [rbp+57h+var_B0]
0x180037909  mov     rcx, rsi
0x18003790c  call    ??$emplace_back@AEAY0BA@$$CBGAEAPEBG@?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@QEAAAEAVHttpHeader@Pal@@AEAY0BA@$$CBGAEAPEBG@Z; std::vector<Pal::HttpHeader>::emplace_back<ushort const (&)[16],ushort const * &>(ushort const (&)[16],ushort const * &)
0x180037911  mov     rcx, [rbp+57h+var_A8]
0x180037915  test    rcx, rcx
0x180037918  jz      short loc_180037953
0x18003791a  mov     rax, [rcx]
0x18003791d  mov     rax, [rax+18h]
0x180037921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037926  test    rax, rax
0x180037929  jz      short loc_180037953
0x18003792b  mov     rcx, rax; hToken
0x18003792e  call    cs:__imp_ImpersonateLoggedOnUser
0x180037934  test    eax, eax
0x180037936  jz      short loc_18003793C
0x180037938  xor     eax, eax
0x18003793a  jmp     short loc_18003794E
0x18003793c  call    cs:__imp_GetLastError
0x180037942  test    eax, eax
0x180037944  jle     short loc_18003794E
0x180037946  movzx   eax, ax
0x180037949  or      eax, 80070000h
0x18003794e  mov     dword ptr [rbp+57h+var_B0], eax
0x180037951  jmp     short loc_18003795A
0x180037953  mov     dword ptr [rbp+57h+var_B0], 800703F0h
0x18003795a  lea     r8, [rbp+57h+var_A0]
0x18003795e  mov     rdx, r13
0x180037961  mov     rcx, r14; dwContext
0x180037964  call    ?sendRequestAsUser@NetworkRequestInternalWinHttp@Pal@@MEAAKAEBU_WINHTTP_URL_COMPONENTS@@AEBV?$shared_ptr@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@std@@@Z; Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(_WINHTTP_URL_COMPONENTS const &,std::shared_ptr<std::vector<Pal::HttpHeader>> const &)
0x180037969  mov     ebx, eax
0x18003796b  lea     rcx, [rbp+57h+var_B0]
0x18003796f  call    ?Revert@?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAAXXZ; Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(void)
0x180037974  nop
0x180037975  lea     rcx, [rbp+57h+var_90]
0x180037979  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003797e  nop
0x18003797f  lea     rcx, [rbp+57h+var_A8]
0x180037983  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037988  nop
0x180037989  mov     rcx, [rbp+57h+dwContext]; dwContext
0x18003798d  test    rcx, rcx
0x180037990  jz      loc_180037863
0x180037996  jmp     loc_18003785E
0x18003799b  mov     byte ptr [rcx+1D0h], 1
0x1800379a2  call    ?sendRequestAsUser@NetworkRequestInternalWinHttp@Pal@@MEAAKAEBU_WINHTTP_URL_COMPONENTS@@AEBV?$shared_ptr@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@std@@@Z; Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(_WINHTTP_URL_COMPONENTS const &,std::shared_ptr<std::vector<Pal::HttpHeader>> const &)
0x1800379a7  mov     rcx, [rbp+57h+var_40]
0x1800379ab  xor     rcx, rsp; StackCookie
0x1800379ae  call    __security_check_cookie
0x1800379b3  mov     rbx, [rsp+0D0h+arg_18]
0x1800379bb  add     rsp, 0A0h
0x1800379c2  pop     r15
0x1800379c4  pop     r14
0x1800379c6  pop     r13
0x1800379c8  pop     r12
0x1800379ca  pop     rdi
0x1800379cb  pop     rsi
0x1800379cc  pop     rbp
0x1800379cd  retn
```
